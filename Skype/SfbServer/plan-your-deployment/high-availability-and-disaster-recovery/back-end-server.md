---
title: Back End alta disponibilidade do servidor no Skype para Business Server
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c559aacb-4e1d-4e78-9582-41f966ad418d
description: Saiba mais sobre as opções de alta disponibilidade do servidor Back-End compatíveis com o Skype para Business Server, incluindo grupos de disponibilidade AlwaysOn, instâncias de Cluster de Failover AlwaysOn, espelhamento de banco de dados e cluster de failover do SQL.
ms.openlocfilehash: 5f95ea1a1a856db945e1d0fac5683b1fb8c4c02e
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32214100"
---
# <a name="back-end-server-high-availability-in-skype-for-business-server"></a>Back End alta disponibilidade do servidor no Skype para Business Server
 
Saiba mais sobre as opções de alta disponibilidade do servidor Back-End compatíveis com o Skype para Business Server, incluindo grupos de disponibilidade AlwaysOn, instâncias de Cluster de Failover AlwaysOn, espelhamento de banco de dados e cluster de failover do SQL.
  
Há quatro opções para aumentar a alta disponibilidade dos Servidores Back-End:
  
- Espelhamento de banco de dados
    
- Grupos de Disponibilidade Sempre Visíveis
    
- Instâncias de Cluster de Failover AlwaysOn (FCI)
    
- Clustering de failover do SQL
    
O uso de uma dessas soluções é opcional, mas é recomendada para manter a continuidade de negócio da sua organização. Caso contrário, ter um servidor de banco de dados único descer na poderia causar a perda de Skype significativa para os dados do servidor de negócios. 
  
É possível configurar o espelhamento de banco de dados usando apenas o construtor de topologias. Para grupos de disponibilidade AlwaysOn, instâncias de Cluster de Failover AlwaysOn ou cluster de failover do SQL, SQL Server é usado para criar a solução de alta disponibilidade e, em seguida, você pode usar o construtor de topologias para associá-lo a um pool de Front-End.
  
Se você usar a alta disponibilidade do servidor Back-End em um pool de Front-End é juntamente com outro pool de Front-End para recuperação de desastres, você deve usar a mesma solução de alta disponibilidade de Back-End em ambos os pools. 
  
## <a name="database-mirroring"></a>Espelhamento de banco de dados

Skype para Business Server suporta espelhamento com o software de banco de dados a seguir:
  
- SQL Server 2016, Enterprise Edition e Standard Edition

- SQL Server de 2014, Enterprise Edition e Standard Edition
    
- SQL Server 2012 SP2 e CU2, Enterprise Edition e Standard Edition
    

> [!NOTE]
> SQL Server 2016 é a única versão suportada pelo Skype para Business Server 2019.
    
Espelhamento de banco de dados assíncrono não é suportado para alta disponibilidade do servidor Back-End no Skype para Business Server. No restante deste documento, o termo espelhamento de banco de dados significa espelhamento sincronizado de banco de dados, salvo quando especificado o contrário. 
  
Quando você implanta o espelhamento de banco de dados em um pool de Front-End, todas as Skype para bancos de dados do servidor de negócios no pool são espelhados, incluindo o repositório de gerenciamento Central, se ele está localizado neste pool, bem como o banco de dados de aplicativo do grupo de resposta e estacionamento de chamada aplicativo banco de dados, se esses aplicativos estão sendo executados no pool. 
  
Com o espelhamento de banco de dados, não é necessário usar o armazenamento compartilhado para os servidores. Cada servidor mantém sua cópia dos bancos de dados no armazenamento local. 
  
Você pode escolher implantar espelhamento de banco de dados com ou sem uma testemunha. Recomendamos usar uma testemunha porque isso habilita o failover do Servidor Back-End como automático. Caso contrário, um administrador terá que invocar manualmente o failover. Observe que mesmo se uma testemunha for implantada, um administrador pode invocar manualmente o failover do Servidor Back-End, se necessário.
  
Se você usar uma testemunha, poderá utilizar uma única testemunha para vários pares de Servidores Back-End. Não há correspondência exata entre testemunhas e pares de Servidores Back-End. As implantações que usam uma única testemunha para vários pares de Servidores Back-End não são tão resilientes quanto as topologias com uma testemunha separada para cada par de Servidores Back-End. 
  
### <a name="guidelines-for-planning-back-end-server-mirroring"></a>Diretrizes para o planejamento de espelhamento do Servidor Back-End

Em geral, a configuração do espelhamento SQL entre os dois Servidores Back-End com uma testemunha requer:
  
- Versão do servidor principal do SQL Server deve oferecer suporte a espelhamento SQL.
    
- Que o principal, o espelho e a testemunha (se implantada) tenham a mesma versão do SQL Server. 
    
- Que o principal e o espelho tenham a mesma edição do SQL Server. A testemunha pode ter uma edição diferente.
    
Para as práticas recomendadas do SQL em termos de quais versões do SQL são suportadas para uma função de testemunha, consulte ["testemunha de espelhamento de banco de dados"](https://go.microsoft.com/fwlink/p/?LinkId=247345) na biblioteca MSDN.
  
Antes de configurar o espelhamento do servidor você deve configurar as permissões do banco de dados SQL corretamente. Para obter detalhes, consulte ["Configurar as contas de logon para o espelhamento de banco de dados ou grupos de disponibilidade AlwaysOn (SQL Server)"](https://go.microsoft.com/fwlink/p/?LinkId=268454).
  
Com o espelhamento SQL, o modo de recuperação de banco de dados fica sempre definido como **Completo**, o que significa que você deve monitorar de perto o tamanho dos logs de transações, fazendo backup regular para evitar o esgotamento do espaço em disco dos Servidores Back-End. A frequência dos backups dos logs de transações depende da taxa de expansão dos logs, que, por sua vez, depende das transações do banco de dados provenientes de atividades de usuários no Pool de Front-Ends. Recomendamos que você determine a expansão dos logs de transação que é esperada para a carga de trabalho de implantação do Lync para que seja possível realizar um planejamento adequado. Os artigos a seguir fornecem mais informações sobre o gerenciamento de logs e backups do SQL:
  
> [!IMPORTANT]
> Usando o construtor de topologia ou cmdlets para configurar e remover SQL espelhamento é aceito somente quando o principal, espelho e servidores de testemunha (se desejar) pertencem ao mesmo domínio. Se quiser configurar o espelhamento SQL entre servidores de domínios diferentes, consulte a documentação do SQL Server. 

> [!NOTE]
> Espelhamento do SQL está disponível no Skype para Business Server 2015, mas não é mais suportado no Skype para Business Server 2019. Os métodos de cluster de failover de grupos de disponibilidade AlwaysOn, instâncias de Cluster de Failover AlwaysOn (FCI) e SQL terão preferência com Skype para Business Server 2019.
  
### <a name="recovery-time-for-automatic-back-end-server-failover-with-database-mirroring"></a>Tempo de recuperação para failover automático do Servidor Back-End com espelhamento de banco de dados

Para o failover automático do Servidor Back-End com espelhamento de banco de dados, a meta de engenharia para o objetivo de tempo de recuperação (RTO) é de 5 minutos. Como o espelhamento de banco de dados é síncrono, não há previsão de perda de dados durante as falhas do Servidor Back-End, exceto nas raras ocasiões em que tanto os Servidores Front-End como o Servidor Back-End ficam inativos simultaneamente enquanto os dados são movidos entre eles. A meta de engenharia para o objetivo do ponto de recuperação (RPO) é de 5 minutos.
  
### <a name="user-experience-during-back-end-server-failure-with-database-mirroring"></a>Experiência do usuário durante falha do Servidor Back-End com espelhamento de banco de dados

A experiência do usuário durante uma falha depende da natureza da falha e da topologia.
  
Se você usa o espelhamento de banco de dados com uma testemunha configurada e o servidor principal falhar, o failover do Servidor Back-End é executado rápida e automaticamente. Os usuários ativos não devem notar a interrupção em suas sessões contínuas.
  
Se não houver uma testemunha configurada, pode levar algum tempo para o administrador invocar manualmente o failover. Durante este tempo, os usuários ativos podem ser afetados. Eles continuam suas sessões normalmente por cerca de 30 minutos. Se ainda não o principal é restaurado ou um administrador não realizou failover para o backup, em seguida, os usuários serão alternados para modo de resiliência, que significa que eles são não é possível executar as tarefas que exigem uma alteração persistente no Lync Server (por exemplo, a adição de um contato).
  
Se o servidor principal e o Servidor Back-End espelho falharem ou se um desses servidores e a testemunha falharem, o Servidor Back-End se tornará indisponível (mesmo se o servidor principal ainda estiver funcionando). Nesse caso, os usuários ativos serão transferidos para o modo de Resiliência após um certo tempo.
  
## <a name="alwayson-availability-groups-and-alwayson-failover-cluster-instances"></a>Grupos de disponibilidade AlwaysOn e instâncias do cluster de failover AlwaysOn

Grupos de disponibilidade AlwaysOn e instâncias de Cluster de Failover AlwaysOn são suportadas apenas no SQL Server 2014 Enterprise Edition e Enterprise Edition do SQL Server 2012. Skype para Business Server oferece suporte a grupos de disponibilidade do AlwaysOn apenas como ativos/passivos, não ativa/ativa. 
  
Para usar grupos de disponibilidade do AlwaysOn ou instâncias de Cluster de Failover AlwaysOn, você primeiro usar SQL Server para instalar e configurar a solução de alta disponibilidade. Em seguida, você pode usar o construtor de topologias para associá-lo a um pool de Front-End.
  
> [!IMPORTANT]
> Nomes de instância para várias instâncias do grupo de disponibilidade do AlwaysOn devem ser o mesmo. 
  
Para obter etapas para a implantação de grupos de disponibilidade AlwaysOn, consulte [Deploy um grupo de disponibilidade do AlwaysOn em um servidor Back-End no Skype para Business Server](../../deploy/deploy-high-availability-and-disaster-recovery/alwayson-availability-group.md).
  
## <a name="sql-server-failover-clustering"></a>Clustering de Failover do SQL Server

Skype para Business Server suporta cluster com os seguintes softwares de banco de dados de failover do SQL Server:
  
- SQL Server 2017, Enterprise Edition e Standard Edition

- SQL Server 2016, Enterprise Edition e Standard Edition

- SQL Server de 2014, Enterprise Edition e Standard Edition
    
- SQL Server 2012 SP2 e CU2, Enterprise Edition e Standard Edition

Para usar o cluster de failover do SQL, primeiro você deve configurar e configurar o cluster do SQL Server antes de implantar o seu pool de Front-End. Para obter instruções de instalação para failover clusters no SQL Server 2012 e práticas recomendadas, consulte [https://technet.microsoft.com/en-us/library/hh231721.aspx](https://technet.microsoft.com/en-us/library/hh231721.aspx).

> [!NOTE]
> 2017 do SQL Server e SQL Server 2016 são as únicas versões suportadas pelo Skype para Business Server 2019.
    
Para usar o cluster de failover do SQL, primeiro você deve configurar e configurar o cluster do SQL Server antes de implantar o seu pool de Front-End. Para obter instruções de instalação para failover clusters em SQL Server 2014 e 2016 e práticas recomendadas, consulte [https://technet.microsoft.com/en-us/library/hh231721.aspx](https://technet.microsoft.com/en-us/library/hh231721.aspx). Para o cluster de failover do SQL Server 2008, consulte [https://technet.microsoft.com/en-us/library/ms189134(v=sql.105).aspx](https://technet.microsoft.com/en-us/library/ms189134%28v=sql.105%29.aspx).
  
Ao instalar o SQL Server, o SQL Server Management Studio deve ser instalado para gerenciar os locais de bases de dados e arquivos de log. O SQL Server Management Studio é instalado como componente opcional quando da instalação do SQL Server.
  

