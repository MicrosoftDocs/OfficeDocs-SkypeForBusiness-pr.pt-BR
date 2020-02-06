---
title: Back-end Server alta disponibilidade no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c559aacb-4e1d-4e78-9582-41f966ad418d
description: Saiba mais sobre as opções de alta disponibilidade do servidor back-end com suporte no Skype for Business Server, incluindo grupos de disponibilidade AlwaysOn, instâncias de cluster de failover AlwaysOn, espelhamento de banco de dados e cluster de failover de SQL.
ms.openlocfilehash: a0aeb53aea0ee2eab25875de0fddbfd0fc26d90a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815949"
---
# <a name="back-end-server-high-availability-in-skype-for-business-server"></a>Back-end Server alta disponibilidade no Skype for Business Server
 
Saiba mais sobre as opções de alta disponibilidade do servidor back-end com suporte no Skype for Business Server, incluindo grupos de disponibilidade AlwaysOn, instâncias de cluster de failover AlwaysOn, espelhamento de banco de dados e cluster de failover de SQL.
  
Há quatro opções para aumentar a alta disponibilidade dos Servidores Back-End:
  
- Espelhamento de banco de dados
    
- Grupos de Disponibilidade Sempre Visíveis
    
- Instâncias de cluster de failover do AlwaysOn (FCI)
    
- Clustering de failover do SQL
    
O uso de uma dessas soluções é opcional, mas é recomendada para manter a continuidade de negócio da sua organização. Caso contrário, o uso de um único servidor de banco de dados pode causar perda de dados significativos do Skype for Business Server. 
  
Você pode configurar o espelhamento de banco de dados usando somente o construtor de topologias. Para grupos de disponibilidade AlwaysOn, instâncias de cluster de failover AlwaysOn ou cluster de failover do SQL, use o SQL Server para criar a solução de alta disponibilidade, então você pode usar o construtor de topologias para associá-lo a um pool de front-ends.
  
Se você usa a alta disponibilidade do servidor back-end em um pool de front-ends que está emparelhado com outro pool de front-end para recuperação de desastres, use a mesma solução de alta disponibilidade de back-end nos dois pools. 
  
## <a name="database-mirroring"></a>Espelhamento de banco de dados

O Skype for Business Server é compatível com o espelhamento com o seguinte software de banco de dados:
  
- SQL Server 2019, edição Enterprise e Standard Edition

- SQL Server 2017, edição Enterprise e Standard Edition

- SQL Server 2016, edição Enterprise e Standard Edition

- SQL Server 2014, edição Enterprise e Standard Edition
    
- SQL Server 2012 SP2 e CU2, edição Enterprise e Standard Edition
    

> [!NOTE]
> O espelhamento do SQL está disponível no Skype for Business Server 2015, mas não é mais compatível com o Skype for Business Server 2019. Os grupos de disponibilidade AlwaysOn, as instâncias de cluster de failover AlwaysOn (FCI) e os métodos de cluster de failover do SQL são preferidos com o Skype for Business Server 2019.
    
O espelhamento de banco de dados assíncrono não é compatível com o back-end de alta disponibilidade do servidor do Skype for Business. No restante deste documento, o termo espelhamento de banco de dados significa espelhamento sincronizado de banco de dados, salvo quando especificado o contrário. 
  
Quando você implanta o espelhamento de banco de dados em um pool de front-end, todos os bancos de dados do Skype for Business Server no pool são espelhados, incluindo o repositório de gerenciamento central, se estiverem localizados nesse pool, bem como o banco de dados do aplicativo de grupo de resposta e o estacionamento de chamada banco de dados do aplicativo, se esses aplicativos estiverem sendo executados no pool. 
  
Com o espelhamento de banco de dados, não é necessário usar o armazenamento compartilhado para os servidores. Cada servidor mantém sua cópia dos bancos de dados no armazenamento local. 
  
Você pode escolher implantar espelhamento de banco de dados com ou sem uma testemunha. Recomendamos usar uma testemunha porque isso habilita o failover do Servidor Back-End como automático. Caso contrário, um administrador terá que invocar manualmente o failover. Observe que mesmo se uma testemunha for implantada, um administrador pode invocar manualmente o failover do Servidor Back-End, se necessário.
  
Se você usar uma testemunha, poderá utilizar uma única testemunha para vários pares de Servidores Back-End. Não há correspondência exata entre testemunhas e pares de Servidores Back-End. As implantações que usam uma única testemunha para vários pares de Servidores Back-End não são tão resilientes quanto as topologias com uma testemunha separada para cada par de Servidores Back-End. 
  
### <a name="guidelines-for-planning-back-end-server-mirroring"></a>Diretrizes para o planejamento de espelhamento do Servidor Back-End

Em geral, a configuração do espelhamento SQL entre os dois Servidores Back-End com uma testemunha requer:
  
- A versão do servidor primário do SQL Server deve dar suporte ao espelhamento do SQL.
    
- Que o principal, o espelho e a testemunha (se implantada) tenham a mesma versão do SQL Server. 
    
- Que o principal e o espelho tenham a mesma edição do SQL Server. A testemunha pode ter uma edição diferente.
    
Para as práticas recomendadas do SQL em termos de quais versões do SQL são compatíveis com uma função de testemunha, consulte ["testemunha de espelhamento de banco de dados"](https://go.microsoft.com/fwlink/p/?LinkId=247345) na biblioteca MSDN.
  
Antes de configurar o espelhamento do servidor você deve configurar as permissões do banco de dados SQL corretamente. Para obter detalhes, consulte ["configurar contas de logon para o espelhamento de banco de dados ou grupos de disponibilidade AlwaysOn (SQL Server)"](https://go.microsoft.com/fwlink/p/?LinkId=268454).
  
Com o espelhamento SQL, o modo de recuperação de banco de dados fica sempre definido como **Completo**, o que significa que você deve monitorar de perto o tamanho dos logs de transações, fazendo backup regular para evitar o esgotamento do espaço em disco dos Servidores Back-End. A frequência dos backups dos logs de transações depende da taxa de expansão dos logs, que, por sua vez, depende das transações do banco de dados provenientes de atividades de usuários no Pool de Front-Ends. Recomendamos que você determine a expansão dos logs de transação que é esperada para a carga de trabalho de implantação do Lync para que seja possível realizar um planejamento adequado. Os artigos a seguir fornecem mais informações sobre o gerenciamento de logs e backups do SQL:
  
> [!IMPORTANT]
> Usar o construtor de topologias ou cmdlets para configurar e remover o espelhamento do SQL só tem suporte quando os servidores primário, espelho e testemunha (se desejado) pertencem ao mesmo domínio. Se quiser configurar o espelhamento SQL entre servidores de domínios diferentes, consulte a documentação do SQL Server. 

> [!NOTE]
> O espelhamento do SQL está disponível no Skype for Business Server 2015, mas não é mais compatível com o Skype for Business Server 2019. Os grupos de disponibilidade AlwaysOn, as instâncias de cluster de failover AlwaysOn (FCI) e os métodos de cluster de failover do SQL são preferidos com o Skype for Business Server 2019.
  
### <a name="recovery-time-for-automatic-back-end-server-failover-with-database-mirroring"></a>Tempo de recuperação para failover automático do Servidor Back-End com espelhamento de banco de dados

Para o failover automático do Servidor Back-End com espelhamento de banco de dados, a meta de engenharia para o objetivo de tempo de recuperação (RTO) é de 5 minutos. Como o espelhamento de banco de dados é síncrono, não há previsão de perda de dados durante as falhas do Servidor Back-End, exceto nas raras ocasiões em que tanto os Servidores Front-End como o Servidor Back-End ficam inativos simultaneamente enquanto os dados são movidos entre eles. A meta de engenharia para o objetivo do ponto de recuperação (RPO) é de 5 minutos.
  
### <a name="user-experience-during-back-end-server-failure-with-database-mirroring"></a>Experiência do usuário durante falha do Servidor Back-End com espelhamento de banco de dados

A experiência do usuário durante uma falha depende da natureza da falha e da topologia.
  
Se você usa o espelhamento de banco de dados com uma testemunha configurada e o servidor principal falhar, o failover do Servidor Back-End é executado rápida e automaticamente. Os usuários ativos não devem notar a interrupção em suas sessões contínuas.
  
Se não houver uma testemunha configurada, pode levar algum tempo para o administrador invocar manualmente o failover. Durante este tempo, os usuários ativos podem ser afetados. Eles continuam suas sessões normalmente por cerca de 30 minutos. Se o principal ainda não for restaurado ou se um administrador não tiver failover para o backup, os usuários terão alternado para o modo de resiliência, o que significa que eles não poderão executar tarefas que exijam uma alteração persistente no Lync Server (como adicionar um contato).
  
Se o servidor principal e o Servidor Back-End espelho falharem ou se um desses servidores e a testemunha falharem, o Servidor Back-End se tornará indisponível (mesmo se o servidor principal ainda estiver funcionando). Nesse caso, os usuários ativos serão transferidos para o modo de Resiliência após um certo tempo.
  
## <a name="alwayson-availability-groups-and-alwayson-failover-cluster-instances"></a>Grupos de disponibilidade AlwaysOn e instâncias do cluster de failover AlwaysOn

O Skype for Business Server é compatível com os grupos de disponibilidade AlwaysOn apenas como ativos/passivos, não ativos/ativos. 
  
Para usar os grupos de disponibilidade AlwaysOn ou instâncias de cluster de failover AlwaysOn, você primeiro usa o SQL Server para configurar e configurar a solução de alta disponibilidade. Em seguida, você pode usar o construtor de topologias para associá-lo a um pool de front-end.

O Skype for Business Server é compatível com o AlwaysOn com o seguinte software de banco de dados:

- SQL Server 2019 Enterprise Edition

- SQL Server 2019 Standard Edition com limitações, consulte nota abaixo

- SQL Server 2017 Enterprise Edition

- SQL Server 2017 Standard Edition com limitações, consulte nota abaixo

- SQL Server 2016 Enterprise Edition

- SQL Server 2016 Standard Edition com limitações, consulte nota abaixo

- SQL Server 2014 Enterprise Edition
    
- SQL Server 2012 SP2 e CU2 Enterprise Edition

> [!NOTE]
> O SQL Server 2019, o 2017 e o 2016 são as únicas versões aceitas pelo Skype for Business Server 2019.

> [!NOTE]
> **Não** há suporte para grupos de disponibilidade AlwaysOn nas edições do SQL 2016, 2017 e 2019 Standard, mas você pode usar instâncias de cluster de failover sempre em failover. Veja as [edições e os recursos com suporte do SQL Server 2016](https://docs.microsoft.com/sql/sql-server/editions-and-components-of-sql-server-2016?view=sql-server-2017) para saber mais.
  
> [!IMPORTANT]
> Os nomes de instâncias para várias instâncias do grupo de disponibilidade AlwaysOn devem ser iguais. 
  
Para ver as etapas de implantação dos grupos de disponibilidade AlwaysOn, consulte [implantar um grupo de disponibilidade AlwaysOn em um servidor back-end no Skype for Business Server](../../deploy/deploy-high-availability-and-disaster-recovery/alwayson-availability-group.md).
  
## <a name="sql-server-failover-clustering"></a>Clustering de Failover do SQL Server

O Skype for Business Server oferece suporte ao cluster de failover do SQL Server com o seguinte software de banco de dados:
  
- SQL Server 2019, edição Enterprise e Standard Edition

- SQL Server 2017, edição Enterprise e Standard Edition

- SQL Server 2016, edição Enterprise e Standard Edition

- SQL Server 2014, edição Enterprise e Standard Edition
    
- SQL Server 2012 SP2 e CU2, edição Enterprise e Standard Edition

Para usar o cluster de failover do SQL, você deve primeiro configurar e configurar o cluster do SQL Server antes de implantar seu pool de front-ends. Para obter práticas recomendadas e instruções de configuração para clustering de failover no SQL [https://technet.microsoft.com/library/hh231721.aspx](https://technet.microsoft.com/library/hh231721.aspx)Server 2012, consulte.

> [!NOTE]
> O SQL Server 2019, o 2017 e o SQL Server 2016 são as únicas versões compatíveis com o Skype for Business Server 2019.
    
Para usar o cluster de failover do SQL, você deve primeiro configurar e configurar o cluster do SQL Server antes de implantar seu pool de front-ends. Para obter práticas recomendadas e instruções de configuração para clustering de failover no SQL Server 2014 [https://technet.microsoft.com/library/hh231721.aspx](https://technet.microsoft.com/library/hh231721.aspx)e 2016, consulte. Para o cluster de failover no SQL Server 2008, [https://technet.microsoft.com/library/ms189134(v=sql.105).aspx](https://technet.microsoft.com/library/ms189134%28v=sql.105%29.aspx)consulte.
  
Ao instalar o SQL Server, o SQL Server Management Studio deve ser instalado para gerenciar os locais de bases de dados e arquivos de log. O SQL Server Management Studio é instalado como componente opcional quando da instalação do SQL Server.
  
