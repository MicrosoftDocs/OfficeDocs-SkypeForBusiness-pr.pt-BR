---
title: Alta disponibilidade do Servidor back-end no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c559aacb-4e1d-4e78-9582-41f966ad418d
description: 'Saiba mais sobre as opções de alta disponibilidade do Servidor #A0 com suporte no Skype for Business Server, incluindo Grupos de Disponibilidade AlwaysOn, Instâncias de Cluster de Failover AlwaysOn, espelhamento de banco de dados e clustering de failover sql.'
ms.openlocfilehash: bbb55ded0d5ce1127f5dcab829907c533cc6316e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802921"
---
# <a name="back-end-server-high-availability-in-skype-for-business-server"></a>Alta disponibilidade do Servidor back-end no Skype for Business Server
 
Saiba mais sobre as opções de alta disponibilidade do Servidor #A0 com suporte no Skype for Business Server, incluindo Grupos de Disponibilidade AlwaysOn, Instâncias de Cluster de Failover AlwaysOn, espelhamento de banco de dados e clustering de failover sql.
  
Para aprimorar a alta disponibilidade dos servidores back-end, você tem quatro opções:
  
- Espelhamento do banco de dados
    
- Grupos de disponibilidade AlwaysOn
    
- Instâncias de Cluster de Failover AlwaysOn (FCI)
    
- Clustering de failover sql
    
O uso de uma dessas soluções é opcional, mas é recomendável para manter a continuidade de negócios da sua organização. Caso contrário, ter um único servidor de banco de dados inogressado pode causar a perda de dados significativos do Skype for Business Server. 
  
Você pode configurar o espelhamento de banco de dados usando apenas o Construtor de Topologias. Para Grupos de Disponibilidade AlwaysOn, Instâncias de Cluster de Failover AlwaysOn ou clustering de failover SQL, você usa o SQL Server para criar a solução de alta disponibilidade e, em seguida, pode usar o Construtor de Topologias para associá-lo a um pool de Front-End.
  
Se você usar a alta disponibilidade do Servidor back-end em um pool de front-end emparelhado com outro pool de front-end para recuperação de desastres, deverá usar a mesma solução de alta disponibilidade de Back End em ambos os pools. 
  
## <a name="database-mirroring"></a>Espelhamento do banco de dados

O Skype for Business Server dá suporte ao espelhamento com o seguinte software de banco de dados:
  
- SQL Server 2019, Enterprise Edition e Standard Edition

- SQL Server 2017, Enterprise Edition e Standard Edition

- SQL Server 2016, Enterprise Edition e Standard Edition

- SQL Server 2014, Enterprise Edition e Standard Edition
    
- SQL Server 2012 SP2 e CU2, Enterprise Edition e Standard Edition
    

> [!NOTE]
> O espelhamento sql está disponível no Skype for Business Server 2015, mas não é mais suportado no Skype for Business Server 2019. Os grupos de disponibilidade AlwaysOn, instâncias de cluster de failover AlwaysOn (FCI) e métodos de clustering de failover SQL são as únicas opções com suporte com o Skype for Business Server 2019.
    
O espelhamento assíncrono de banco de dados não é suportado para alta disponibilidade do Servidor back-end no Skype for Business Server. No restante deste documento, o espelhamento de banco de dados significa espelhamento síncrono de banco de dados, a menos que seja explicitamente declarado de outra forma. 
  
Quando você implanta o espelhamento de banco de dados em um pool de Front-End, todos os bancos de dados do Skype for Business Server no pool são espelhados, incluindo o armazenamento de Gerenciamento Central, se ele estiver localizado nesse pool, bem como o banco de dados de aplicativo do Grupo de Resposta e o banco de dados de aplicativos estacionamento de chamada, se esses aplicativos estão sendo executados no pool. 
  
Com o espelhamento de banco de dados, você não precisa usar o armazenamento compartilhado para os servidores. Cada servidor mantém sua cópia dos bancos de dados no armazenamento local. 
  
Você pode optar por implantar o espelhamento de banco de dados com ou sem uma testemunha. Recomendamos usar uma testemunha porque habilita o failover do Servidor de Back-End como automático. De outra forma, um administrador deve invocar manualmente o failover. Observe que mesmo se uma testemunha é implantada, um administrador pode invocar manualmente o failover do Servidor de Back-End, se necessário.
  
Se você usar uma testemunha, é possível utilizar uma única testemunha para vários pares de Servidores de Back-End. Não há correspondência exata entre testemunhas e pares de Servidores de Back-End. As implantações usam uma única testemunha para vários pares de Servidores de Back-End não são tão resilientes quanto topologias com uma testemunha separada para cada par de Servidor de Back-End. 
  
### <a name="guidelines-for-planning-back-end-server-mirroring"></a>Diretrizes para planejar o espelhamento do Servidor back-end

Em geral, a configuração do espelhamento SQL entre os dois servidores back-end com uma testemunha requer:
  
- A versão do SQL Server do servidor primário deve dar suporte ao espelhamento SQL.
    
- Que o principal, o espelho e a testemunha (se implantada) tenham a mesma versão do SQL Server. 
    
- Que o principal e o espelho tenham a mesma edição do SQL Server. A testemunha pode ter uma edição diferente.
    
Para práticas recomendadas do SQL em termos de quais versões SQL são suportadas para uma função Testemunha, consulte "Testemunha de espelhamento de banco de  [dados"](https://go.microsoft.com/fwlink/p/?LinkId=247345) na Biblioteca MSDN.
  
Antes de configurar o espelhamento do servidor, você deve primeiro configurar as permissões do banco de dados SQL corretamente. Para obter detalhes, consulte "Configurar contas de logon para espelhamento de banco de dados ou grupos de disponibilidade  [AlwaysOn (SQL Server)"](https://go.microsoft.com/fwlink/p/?LinkId=268454).
  
Com o espelhamento SQL, o modo de recuperação de banco de dados fica sempre definido como **Completo**, o que significa que você deve monitorar de perto o tamanho dos logs de transações, fazendo backup regular deles para evitar o esgotamento do espaço em disco dos servidores back-end. A frequência dos backups dos logs de transações depende da taxa de expansão dos logs, que, por sua vez, depende das transações do banco de dados provenientes de atividades de usuários no pool front-end. Recomendamos que você determine a expansão dos logs de transação esperada para a carga de trabalho de implantação do Lync, de modo que seja possível realizar um planejamento adequado. Os artigos a seguir fornecem mais informações sobre o gerenciamento de logs e backups do SQL:
  
> [!IMPORTANT]
> O uso do Construtor de Topologias ou cmdlets para configurar e remover o espelhamento SQL é suportado somente quando os servidores primário, espelho e testemunha (se desejado) pertencem ao mesmo domínio. Caso deseje configurar o espelhamento SQL entre servidores de domínios diferentes, consulte a documentação do SQL Server. 

> [!NOTE]
> O espelhamento sql está disponível no Skype for Business Server 2015, mas não é mais suportado no Skype for Business Server 2019. Os grupos de disponibilidade AlwaysOn, instâncias de cluster de failover AlwaysOn (FCI) e métodos de cluster de failover SQL são preferenciais com o Skype for Business Server 2019.
  
### <a name="recovery-time-for-automatic-back-end-server-failover-with-database-mirroring"></a>Tempo de recuperação para failover automático do Servidor back-end com espelhamento de banco de dados

Para failover automático de Back End com espelhamento de banco de dados, o destino de engenharia para objetivo de tempo de recuperação (RTO) é de 5 minutos. Devido ao espelhamento síncrono do banco de dados, não antecipamos a perda de dados durante falhas do Servidor back-end, exceto em raras ocasiões em que tanto os Servidores de Front End quanto o Servidor de Back End caiam simultaneamente enquanto os dados estão sendo movidos entre os servidores. A meta de engenharia para o objetivo de ponto de recuperação (RPO) é de 5 minutos.
  
### <a name="user-experience-during-back-end-server-failure-with-database-mirroring"></a>Experiência do usuário durante falha do Servidor back-end com espelhamento de banco de dados

Experiência do usuário durante uma falha depende da natureza falha e da sua topologia.
  
Se você usar o espelhamento de banco de dados e tiver uma testemunha configurada, e a entidade falhar, o failover do Servidor back-end ocorrerá de forma automática e rápida. Os usuários ativos não devem observar muita interrupção em suas sessões contínuas.
  
Se não há uma testemunha configurada, pode levar algum tempo para o administrador invocar manualmente o failover. Durante este tempo, os usuários ativos podem ser afetados. Eles continuam suas sessões normalmente por cerca de 30 minutos. Se o primário ainda não for restaurado ou se um administrador não tiver falhado no backup, os usuários serão alternados para o modo resiliência, o que significa que eles não poderão executar tarefas que exigem uma alteração persistente no Lync Server (como adicionar um contato).
  
Se o diretor e o Servidor de Back-End espelho falharem ou se um destes servidores e a testemunha falharem, o Servidor de Back-End se tornará indisponível (mesmo se o diretor ainda estiver funcionando). Neste caso, os usuários ativos são mudados para o modo Resiliência após algum tempo.
  
## <a name="alwayson-availability-groups-and-alwayson-failover-cluster-instances"></a>Grupos de Disponibilidade AlwaysOn e Instâncias de Cluster de Failover AlwaysOn

O Skype for Business Server dá suporte a Grupos de Disponibilidade AlwaysOn apenas como ativo/passivo, não ativo/ativo. 
  
Para usar Grupos de Disponibilidade AlwaysOn ou Instâncias de Cluster de Failover AlwaysOn, primeiro use o SQL Server para configurar e configurar a solução de alta disponibilidade. Em seguida, você pode usar o Construtor de Topologias para associá-lo a um pool de Front-End.

O Skype for Business Server dá suporte ao AlwaysOn com o seguinte software de banco de dados:

- SQL Server 2019 Enterprise Edition

- SQL Server 2019 Standard Edition com limitações, confira a observação abaixo

- SQL Server 2017 Enterprise Edition

- SQL Server 2017 Standard Edition com limitações, confira a observação abaixo

- SQL Server 2016 Enterprise Edition

- SQL Server 2016 Standard Edition com limitações, confira a observação abaixo

- SQL Server 2014 Enterprise Edition
    
- SQL Server 2012 SP2 e CU2 Enterprise Edition

> [!NOTE]
> O SQL Server 2019, 2017 e 2016 são as únicas versões com suporte do Skype for Business Server 2019.

> [!NOTE]
> Grupos de Disponibilidade  Always On não são suportados nas edições Sql 2016, 2017 e 2019 Standard, mas você pode usar Instâncias de Cluster de Failover Always On. Confira [edições e recursos com suporte do SQL Server 2016](https://docs.microsoft.com/sql/sql-server/editions-and-components-of-sql-server-2016?view=sql-server-2017) para saber mais.
  
> [!IMPORTANT]
> Os nomes das instâncias de várias instâncias do Grupo de Disponibilidade AlwaysOn devem ser os mesmos. 
  
Para ver as etapas para implantar grupos de disponibilidade AlwaysOn, consulte Implantar um grupo de disponibilidade AlwaysOn em um [servidor back-end no Skype for Business Server.](../../deploy/deploy-high-availability-and-disaster-recovery/alwayson-availability-group.md)
  
## <a name="sql-server-failover-clustering"></a>SQL Server Failover Clustering

O Skype for Business Server suporta clustering de failover do SQL Server com o seguinte software de banco de dados:
  
- SQL Server 2019, Enterprise Edition e Standard Edition

- SQL Server 2017, Enterprise Edition e Standard Edition

- SQL Server 2016, Enterprise Edition e Standard Edition

- SQL Server 2014, Enterprise Edition e Standard Edition
    
- SQL Server 2012 SP2 e CU2, Enterprise Edition e Standard Edition

Para usar o cluster de failover sql, você deve primeiro configurar e configurar o cluster do SQL Server antes de implantar seu pool de Front-End. Para obter as práticas recomendadas e instruções de configuração para clustering de failover no SQL Server 2012, consulte [https://technet.microsoft.com/library/hh231721.aspx](https://technet.microsoft.com/library/hh231721.aspx) .

> [!NOTE]
> O SQL Server 2019, 2017 e o SQL Server 2016 são as únicas versões com suporte do Skype for Business Server 2019.
    
Para usar o cluster de failover sql, você deve primeiro configurar e configurar o cluster do SQL Server antes de implantar seu pool de Front-End. Para obter as práticas recomendadas e as instruções de configuração para clustering de failover no SQL Server 2014 e 2016, confira [https://technet.microsoft.com/library/hh231721.aspx](https://technet.microsoft.com/library/hh231721.aspx) . Para clustering de failover no SQL Server 2008, consulte [https://technet.microsoft.com/library/ms189134(v=sql.105).aspx](https://technet.microsoft.com/library/ms189134%28v=sql.105%29.aspx) .
  
Ao instalar o SQL Server, você deve instalar o SQL Server Management Studio para gerenciar os locais para o banco de daods e os locais para o arquivo de log. O SQL Server Management Studio é instalado como um componente opcional ao instalar o SQL Server.
  
