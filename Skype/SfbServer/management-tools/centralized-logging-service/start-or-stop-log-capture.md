---
title: Iniciar ou interromper captura de log CLS no Skype for Business Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 0512b9ce-7f5b-48eb-a79e-f3498bacf2de
description: 'Resumo: Saiba como iniciar ou parar uma sessão de captura do log de Centralized Logging Service no Skype para Business Server 2015.'
ms.openlocfilehash: c0b65fddcb5036cf41866ce79d82ae0bc49a79e3
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/04/2018
ms.locfileid: "25373761"
---
# <a name="start-or-stop-cls-log-capture-in-skype-for-business-server-2015"></a>Iniciar ou interromper captura de log CLS no Skype for Business Server 2015
 
**Resumo:** Saiba como iniciar ou parar uma sessão de captura do log de Centralized Logging Service no Skype para Business Server 2015.
  
Para capturar logs de rastreamento usando the Centralized Logging Service, você emitir um comando para iniciar o registro em um ou mais computadores e pools. Você também emitir parâmetros que definem quais computadores ou pools, quais cenários para executar (por exemplo, AlwaysOn, outra situação predefinida ou um cenário que você criou), qual Skype para componentes de servidor de negócios (por exemplo, S4, SipStack) para rastreamento.
  
Para capturar informação certa, é necessário usar o cenário correto para coletar informação relevante ao problema. In the Centralized Logging Service, um cenário é o conceito de ativar registro em log com base em uma coleção de componentes de servidor, os níveis de log e sinalizadores, que é muito mais eficiente e úteis que precisar definir esses elementos em uma base por servidor. Você define e especifica um cenário para executar e o cenário é executado consistentemente em todos os servidores e pools no escopo da infraestrutura.
  
O cenário padrão é chamado de **AlwaysOn**. O objetivo do AlwaysOn é executar o cenários constantemente, conforme o nome do cenário implica. O cenário AlwaysOn coleta informações de nível informativo (observe que o nível de log informativo inclui Fatal, Erro e Aviso, além das mensagens informativas) para boa parte da maioria dos componentes de servidor comum. AlwaysOn coleta informações antes, durante e após o problema ocorrer. Isso difere drasticamente do comportamento típico das ferramentas de log anteriores, como o OCSLogger. É possível executar OCSLogger após o problema ocorrer, dificultando seus esforços para resolução de problemas, pois os dados que você tem são reativos, não proativos. Se AlwaysOn não tem a informação que você está procurando a fim de indicar o componente do problema e um curso de ação para corrigi-lo (o que provavelmente não leva em conta a amplitude e profundidade dos provedores em AlwaysOn), ele indicará um nível adequado de informação para determinar o que mais deve ser feito, como criar um novo cenário, juntar outras informações, realizar uma busca diferente para coletar informações mais detalhadas, e assim por diante.
  
The Centralized Logging Service oferece duas maneiras de comandos do problema. Um número de tópicos foram se concentra em usando o Windows PowerShell por meio do Skype do Shell de gerenciamento do servidor de negócios. A capacidade de usar um número de comandos e configurações complexas melhora o Windows PowerShell para uso do serviço de registro em log centralizado. Como o Windows PowerShell por meio do Skype do Shell de gerenciamento do servidor de negócios é quase onipresente para todas as funções em Skype para Business Server, somente os comandos do Windows PowerShell são abordados. 
  
### <a name="to-run-start-csclslogging-with-windows-powershell-using-basic-commands"></a>Para executar Start-CsClsLogging com usando comandos básicos do Windows PowerShell

1. Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.
    
2. Inicie um cenário de log com the Centralized Logging Service digitando o seguinte:
    
   ```
   Start-CsClsLogging -Scenario <name of scenario>
   ```

    Por exemplo, para iniciar o cenário **AlwaysOn**, digite:
    
   ```
   Start-CsClsLogging -Scenario AlwaysOn
   ```

    > [!NOTE]
    > O cenário AlwaysOn não tem uma duração padrão. Este cenário será executado até você pará-lo explicitamente com o cmdlet **Stop-CsClsLogging** . Para obter detalhes, consulte [Stop-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/stop-csclslogging?view=skype-ps). Para todos os outros cenários, a duração padrão é 4 horas. 
  
3. Pressione Enter para executar o comando. 
    
    > [!NOTE]
    > Pode levar algum tempo (30 a 60 segundos) para que os comandos sejam executados e recebam o status dos computadores em sua implantação. 
  
     ![Executando Start-CsClsLogging.](../../media/Ops_CLS_Show_and_Start_ClsLogging.jpg)
  
4. Para iniciar outro cenários, use o cmdlet **Start-CsClsLogging** com o nome do cenário adicional para executar o seguinte (por exemplo, o cenário **autenticação**):
    
   ```
   Start-CsClsLogging -Scenario Authentication
   ```

    > [!IMPORTANT]
    > É possível ter um total de dois cenários sendo executados em qualquer computador a qualquer momento. Se o comando for de escopo global, todos os computadores em sua implantação executarão o(s) cenário(s). Para iniciar um terceiro cenário, você deve parar o log no escopo de computador, pool, site ou global em que você queira executar o novo cenário. Caso tenho iniciado um escopo global, é possível parar o log em um ou ambos cenários em um ou mais computadores e pools. 
  
### <a name="to-run-start-csclslogging-with-windows-powershell-using-advanced-commands"></a>Para executar Start-CsClsLogging com o Windows PowerShell usando comandos avançados

1. Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.
    
2. Estão disponíveis parâmetros adicionais para gerenciar os comandos de log. Você pode usar - duração para ajustar o período de tempo para o cenário para executar. Você também pode definir - computadores, uma lista de nomes de domínio totalmente qualificado do computador (FQDNs) separados por uma vírgula, ou - lista de FQDNs dos pools que você deseja executar o logon de separado de Pools, uma vírgula.
    
    Você inicia uma sessão de log para o cenário UserReplicator no pool "pool01.contoso.net". Você também define duração da sessão de log em 8 horas. Para isso, digite:
    
   ```
   Start-CsClsLogging -Scenario UserReplicator -Duration 8:00 -Pools "pool01.contoso.net"
   ```

    O execução com sucesso deste cenário devolve um resultado como o seguinte:
    
     ![Executando Start-CsClsLogging.](../../media/Ops_CsClsLogging_UserReplicator_Exp.jpg)
  
Observe que, neste exemplo, o cenário AlwaysOn é executado e o cenário UserReplicator também está sendo executado. 
    
## <a name="stop-the-centralized-logging-service-log-capture"></a>Interrompa a captura do log do Serviço de Registro em Log Centralizado
<a name="stop"> </a>

É possível parar uma sessão de registro em log em execução no momento com o cmdlet Stop-CsClsLogging. Em geral, não existem várias situações em que você precisaria interromper uma sessão de log. Por exemplo, é possível pesquisar logs e alterar as configurações sem antes precisar pará-lo. Se você tiver dois cenários em execução, como o AlwaysOn e o UserReplicator, e for necessário coletar informações relacionadas à Autenticação, será necessário parar um dos outros cenários (em um escopo global, site, pool ou computador) antes de poder iniciar a execução do cenário de Autenticação. Para obter detalhes, consulte [Stop-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/stop-csclslogging?view=skype-ps).
  
> [!NOTE]
> Ao determinar quais cenários podem ser executados em uma determinada implantação, pool ou computador, é necessário se lembrar de que você está limitado à execução de dois cenários **por computador**. Se você estiver registrando em log uma atividade em um pool, trate o pool como uma entidade única. Na maioria dos casos, não faria sentido executar cenários diferentes em cada computador em um pool. Não faz sentido analisar o problema sobre o qual você está coletando dados e pensar sobre qual cenário faz mais sentido em um determinado computador na implantação geral. Por exemplo, se você considerar o cenário userreplicator também, seria haver muito pouco valor na execução userreplicator também em um servidor de borda ou pool de borda. 
  
Depois de entender o problema e o escopo do impacto, faça escolhas cuidadosas sobre quais cenários executar em quais computadores e pools. Embora o cenário AlwaysOn faça sentido para um aplicativo de escopo amplo, pois coleta informações sobre uma ampla variedade de provedores, cenários específicos têm valor de aplicativo apenas em computadores ou pools específicos. Além disso, tome cuidado ao iniciar aleatoriamente uma sessão de registro em log sem antes entender o valor de um determinado cenário. Se você usar o cenário errado ou se usar um cenário apropriado para a tarefa e aplicar o cenário ao escopo errado (seja global, site, pool ou computador), poderá receber dados questionáveis e não muito úteis – como se não tivesse executado o cenário.
  
Para controlar as funções Centralized Logging Service usando o Skype do Shell de gerenciamento do servidor de negócios, você deve ser um membro do CsAdministrator ou os grupos de segurança CsServerAdministrator acesso baseado em função (RBAC) de controle ou uma função RBAC personalizada que contém qualquer um desses dois grupos. Para retornar uma lista de todas as funções RBAC que este cmdlet foi atribuído ao (incluindo qualquer funções de RBAC personalizadas que você criou a mesmo), execute o seguinte comando do Skype para Business Server Management Shell ou o prompt do Windows PowerShell:
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

Por exemplo:
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

### <a name="to-stop-a-currently-running-centralized-logging-service-session"></a>Para interromper uma sessão de Centralized Logging Service atualmente em execução

1. Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.
    
2. Consulte the Centralized Logging Service para descobrir quais cenários estão atualmente em execução digitando o seguinte:
    
   ```
   Show-CsClsLogging
   ```

   ![Console do Windows PowerShell após a chamada a Show-CsCl](../../media/Ops_Show_Stop_CsClsLogging.jpg)
  
   O resultado de Show-CsClsLogging é um resumo dos cenários em execução e em qual escopo eles estão em execução. Para obter detalhes, consulte [Show-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/show-csclslogging?view=skype-ps).
    
3. Para interromper uma sessão de registro em log atualmente em execução com um cenário específico, digite:
    
   ```
   Stop-CsClsLogging -Scenario <scenario name> -Computers <comma separated list of fully qualified computer names> -Pools <comma separated list of fully qualified pool names>
   ```
   Por exemplo:
    
   ```
   Stop-CsClsLogging -Scenario UserReplicator -Pools pool01.contoso.net
   ```

   Esse comando interromperá o registro em log com o cenário UserReplicator em pool01.contoso.net.
    
    > [!NOTE]
    > Os logs criados durante a sessão de registro em log usando o cenário UserReplicator não são excluídos. O registro em log ainda está disponível para execução de pesquisas usando o comando Search-CsClsLogging. Para obter detalhes, consulte [Search-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/search-csclslogging?view=skype-ps). 
  
Agindo como o comando acompanhante para Start-CsClsLogging, o cmdlet Stop-CsClsLogging encerra a sessão de registro em log, definida pelos cenários, e retém os logs criados pela sessão de registro em log. É possível executar dois cenários em um determinado computador a qualquer momento. O método de parar um cenário para coletar informações usando outro cenário é uma tarefa comum que pode ser executada durante grande parte das soluções de problemas de carga de trabalho.
## <a name="see-also"></a>Ver também
<a name="stop"> </a>

[Serviço centralizado de registro em log no Skype for Business 2015](centralized-logging-service.md)