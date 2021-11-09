---
title: Alta disponibilidade do Servidor Back-End no Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: c559aacb-4e1d-4e78-9582-41f966ad418d
description: Saiba mais sobre as opções de alta disponibilidade do Servidor Back-End com suporte no Skype for Business Server, incluindo Grupos de Disponibilidade AlwaysOn, Instâncias de Cluster de Failover AlwaysOn, espelhamento de banco de dados e SQL clustering de failover.
ms.openlocfilehash: 9e7b06fc1894c67d6d4cee1e2ec04bf910181df5
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60847174"
---
# <a name="back-end-server-high-availability-in-skype-for-business-server"></a>Alta disponibilidade do Servidor Back-End no Skype for Business Server
 
Saiba mais sobre as opções de alta disponibilidade do Servidor Back-End com suporte no Skype for Business Server, incluindo Grupos de Disponibilidade AlwaysOn, Instâncias de Cluster de Failover AlwaysOn, espelhamento de banco de dados e SQL clustering de failover.
  
Para melhorar a alta disponibilidade para seus Servidores Back-End, você tem quatro opções:
  
- Espelhamento do banco de dados
    
- Grupos de disponibilidade AlwaysOn
    
- Instâncias de Cluster de Failover AlwaysOn (FCI)
    
- SQL clustering de failover
    
Usar uma dessas soluções é opcional, mas é recomendável manter a continuidade de negócios da sua organização. Caso contrário, ter um único servidor de banco de dados para baixo pode causar a perda de dados Skype for Business Server significativos. 
  
Você pode configurar o espelhamento de banco de dados usando apenas o Construtor de Topologias. Para Grupos de Disponibilidade AlwaysOn, Instâncias de Cluster de Failover AlwaysOn ou SQL de failover, você usa o SQL Server para criar a solução de alta disponibilidade e, em seguida, pode usar o Construtor de Topologias para associá-lo a um pool de Front-End.
  
Se você usar o Servidor Back-End de alta disponibilidade em um pool de Front-End que está emparelhado com outro pool de Front-End para recuperação de desastres, use a mesma solução de alta disponibilidade de Back End em ambos os pools. 
  
## <a name="database-mirroring"></a>Espelhamento do banco de dados

Skype for Business Server o espelhamento com o seguinte software de banco de dados:
  
- SQL Server 2019, tanto Edição Enterprise quanto Edição Standard

- SQL Server 2017, tanto Edição Enterprise quanto Edição Standard

- SQL Server 2016, tanto Edição Enterprise quanto Edição Standard

- SQL Server 2014, tanto Edição Enterprise quanto Edição Standard
    
- SQL Server 2012 SP2 e CU2, Edição Enterprise e Edição Standard
    

> [!NOTE]
> SQL O espelhamento está disponível no Skype for Business Server 2015, mas não tem mais suporte no Skype for Business Server 2019. Os métodos de cluster de cluster AlwaysOn Availability Groups, FCI (Instâncias de Cluster de Failover AlwaysOn) e SQL de failover são as únicas opções suportadas com Skype for Business Server 2019.
    
O espelhamento de banco de dados assíncrono não é suportado para alta disponibilidade do Servidor Back End no Skype for Business Server. No restante deste documento, espelhamento de banco de dados significa espelhamento de banco de dados síncrono, a menos que seja explicitamente declarado. 
  
Quando você implanta o espelhamento de banco de dados em um pool de Front-End, todos os bancos de dados Skype for Business Server no pool são espelhados, incluindo o armazenamento de Gerenciamento Central, se ele estiver localizado neste pool, bem como o banco de dados de aplicativos do Grupo de Resposta e o banco de dados de aplicativos estacionamento de chamada, se esses aplicativos estão sendo executados no pool. 
  
Com o espelhamento de banco de dados, você não precisa usar o armazenamento compartilhado para os servidores. Cada servidor mantém sua cópia dos bancos de dados no armazenamento local. 
  
Você pode optar por implantar o espelhamento de banco de dados com ou sem uma testemunha. Recomendamos usar uma testemunha porque habilita o failover do Servidor de Back-End como automático. De outra forma, um administrador deve invocar manualmente o failover. Observe que mesmo se uma testemunha é implantada, um administrador pode invocar manualmente o failover do Servidor de Back-End, se necessário.
  
Se você usar uma testemunha, é possível utilizar uma única testemunha para vários pares de Servidores de Back-End. Não há correspondência exata entre testemunhas e pares de Servidores de Back-End. As implantações usam uma única testemunha para vários pares de Servidores de Back-End não são tão resilientes quanto topologias com uma testemunha separada para cada par de Servidor de Back-End. 
  
### <a name="guidelines-for-planning-back-end-server-mirroring"></a>Diretrizes para o planejamento do espelhamento do Servidor Back-End

Em geral, a configuração do espelhamento SQL entre os dois servidores back-end com uma testemunha requer:
  
- A versão do servidor principal do SQL Server deve dar suporte SQL espelhamento.
    
- Que o principal, o espelho e a testemunha (se implantada) tenham a mesma versão do SQL Server. 
    
- Que o principal e o espelho tenham a mesma edição do SQL Server. A testemunha pode ter uma edição diferente.
    
Para SQL práticas recomendadas em termos de quais versões SQL são suportadas para uma função Testemunha, consulte ["Testemunha de Espelhamento](/sql/database-engine/database-mirroring/database-mirroring-witness) de Banco de Dados" no Biblioteca MSDN.
  
Antes de configurar o espelhamento do servidor, você deve primeiro configurar SQL de banco de dados corretamente. Para obter detalhes, consulte ["Set Up Login Accounts for Database Mirroring or AlwaysOn Availability Groups (SQL Server)"](/sql/database-engine/database-mirroring/set-up-login-accounts-database-mirroring-always-on-availability).
  
Com o espelhamento SQL, o modo de recuperação de banco de dados fica sempre definido como **Completo**, o que significa que você deve monitorar de perto o tamanho dos logs de transações, fazendo backup regular deles para evitar o esgotamento do espaço em disco dos servidores back-end. A frequência dos backups dos logs de transações depende da taxa de expansão dos logs, que, por sua vez, depende das transações do banco de dados provenientes de atividades de usuários no pool front-end. Recomendamos que você determine a expansão dos logs de transação esperada para a carga de trabalho de implantação do Lync, de modo que seja possível realizar um planejamento adequado. Os artigos a seguir fornecem mais informações sobre o gerenciamento de logs e backups do SQL:
  
> [!IMPORTANT]
> Usar o Construtor de Topologias ou cmdlets para configurar e remover SQL espelhamento só é suportado quando os servidores primário, espelho e testemunha (se desejado) pertencem ao mesmo domínio. Caso deseje configurar o espelhamento SQL entre servidores de domínios diferentes, consulte a documentação do SQL Server. 

> [!NOTE]
> SQL O espelhamento está disponível no Skype for Business Server 2015, mas não tem mais suporte no Skype for Business Server 2019. Os grupos de disponibilidade AlwaysOn, Instâncias de Cluster de Failover AlwaysOn (FCI) e SQL de clustering de failover são preferenciais com o Skype for Business Server 2019.
  
### <a name="recovery-time-for-automatic-back-end-server-failover-with-database-mirroring"></a>Tempo de recuperação para failover automático do Servidor back-end com espelhamento de banco de dados

Para failover automático de Back-End com espelhamento de banco de dados, o destino de engenharia para o objetivo de tempo de recuperação (RTO) é de 5 minutos. Devido ao espelhamento síncrono do banco de dados, não antecipamos a perda de dados durante falhas do Servidor back-end, exceto em raras ocasiões em que os Servidores Front-End e o Servidor Back-End são baixados simultaneamente enquanto os dados estão sendo movidos entre os servidores. A meta de engenharia para o objetivo de ponto de recuperação (RPO) é de 5 minutos.
  
### <a name="user-experience-during-back-end-server-failure-with-database-mirroring"></a>Experiência do usuário durante falha do Servidor Back-End com espelhamento de banco de dados

Experiência do usuário durante uma falha depende da natureza falha e da sua topologia.
  
Se você usar o espelhamento de banco de dados e tiver uma testemunha configurada, e a entidade principal falhar, o failover do Servidor back-end acontecerá automaticamente e rapidamente. Os usuários ativos não devem observar muita interrupção em suas sessões contínuas.
  
Se não há uma testemunha configurada, pode levar algum tempo para o administrador invocar manualmente o failover. Durante este tempo, os usuários ativos podem ser afetados. Eles continuam suas sessões normalmente por cerca de 30 minutos. Se o principal ainda não for restaurado ou um administrador não tiver falhado no backup, os usuários serão alternados para o modo resiliência, o que significa que eles não podem executar tarefas que exigem uma alteração persistente no Lync Server (como adicionar um contato).
  
Se o diretor e o Servidor de Back-End espelho falharem ou se um destes servidores e a testemunha falharem, o Servidor de Back-End se tornará indisponível (mesmo se o diretor ainda estiver funcionando). Neste caso, os usuários ativos são mudados para o modo Resiliência após algum tempo.
  
## <a name="alwayson-availability-groups-and-alwayson-failover-cluster-instances"></a>Grupos de Disponibilidade AlwaysOn e Instâncias de Cluster de Failover AlwaysOn

Skype for Business Server dá suporte a Grupos de Disponibilidade AlwaysOn apenas como ativo/passivo, não ativo/ativo. 
  
Para usar Grupos de Disponibilidade AlwaysOn ou Instâncias de Cluster de Failover AlwaysOn, primeiro use SQL Server para configurar e configurar a solução de alta disponibilidade. Em seguida, você pode usar o Construtor de Topologias para associá-lo a um pool de Front-End.

Skype for Business Server suporta AlwaysOn com o seguinte software de banco de dados:

- SQL Server 2019 Edição Enterprise

- SQL Server 2019 Edição Standard com limitações, consulte observação abaixo

- SQL Server 2017 Edição Enterprise

- SQL Server 2017 Edição Standard com limitações, consulte observação abaixo

- SQL Server 2016 Edição Enterprise

- SQL Server 2016 Edição Standard com limitações, consulte observação abaixo

- SQL Server 2014 Edição Enterprise
    
- SQL Server 2012 SP2 e CU2 Edição Enterprise

> [!NOTE]
> SQL Server 2019, 2017 e 2016 são as únicas versões suportadas pelo Skype for Business Server 2019.

> [!NOTE]
> Os Grupos de  Disponibilidade Always On não são suportados nas Edições Padrão SQL 2016, 2017 e 2019, mas você pode usar Instâncias de Cluster de Failover Always On. Consulte [edições e recursos com suporte do SQL Server 2016](/sql/sql-server/editions-and-components-of-sql-server-2016?view=sql-server-2017) para saber mais.
  
> [!IMPORTANT]
> Os nomes de instância para várias instâncias do Grupo de Disponibilidade AlwaysOn devem ser os mesmos. 
  
Para etapas para implantar Grupos de Disponibilidade AlwaysOn, consulte [Deploy an AlwaysOn Availability Group on a Back End Server in Skype for Business Server](../../deploy/deploy-high-availability-and-disaster-recovery/alwayson-availability-group.md).
  
## <a name="sql-server-failover-clustering"></a>SQL Server Failover Clustering

Skype for Business Server suporta SQL Server de failover com o seguinte software de banco de dados:
  
- SQL Server 2019, tanto Edição Enterprise quanto Edição Standard

- SQL Server 2017, tanto Edição Enterprise quanto Edição Standard

- SQL Server 2016, tanto Edição Enterprise quanto Edição Standard

- SQL Server 2014, tanto Edição Enterprise quanto Edição Standard
    
- SQL Server 2012 SP2 e CU2, Edição Enterprise e Edição Standard

Para usar SQL cluster de failover, você deve primeiro configurar e configurar o cluster SQL Server antes de implantar seu pool de Front-End. Para obter as práticas recomendadas e instruções de instalação para cluster de failover no SQL Server 2012, consulte [https://technet.microsoft.com/library/hh231721.aspx](/sql/sql-server/failover-clusters/install/sql-server-failover-cluster-installation) .

> [!NOTE]
> SQL Server 2019, 2017 e SQL Server 2016 são as únicas versões suportadas pelo Skype for Business Server 2019.
    
Para usar SQL cluster de failover, você deve primeiro configurar e configurar o cluster SQL Server antes de implantar seu pool de Front-End. Para obter as práticas recomendadas e instruções de instalação para cluster de failover no SQL Server 2014 e 2016, consulte [https://technet.microsoft.com/library/hh231721.aspx](/sql/sql-server/failover-clusters/install/sql-server-failover-cluster-installation) . Para cluster de failover no SQL Server 2008, consulte [https://technet.microsoft.com/library/ms189134(v=sql.105).aspx](/previous-versions/sql/sql-server-2008-r2/ms189134(v=sql.105)) .
  
Ao instalar o SQL Server, você deve instalar o SQL Server Management Studio para gerenciar os locais para o banco de daods e os locais para o arquivo de log. O SQL Server Management Studio é instalado como um componente opcional ao instalar o SQL Server.
