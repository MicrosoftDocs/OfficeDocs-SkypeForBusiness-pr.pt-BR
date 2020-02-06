---
title: Iniciar ou interromper captura de log CLS no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 0512b9ce-7f5b-48eb-a79e-f3498bacf2de
description: 'Resumo: saiba como iniciar ou parar uma sessão de captura de log de serviço de log centralizada no Skype for Business Server 2015.'
ms.openlocfilehash: 4d8c40c2fdb648497997fbd4a69dc49af4685b43
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816560"
---
# <a name="start-or-stop-cls-log-capture-in-skype-for-business-server-2015"></a>Iniciar ou interromper captura de log CLS no Skype for Business Server 2015
 
**Resumo:** Saiba como iniciar ou parar uma sessão de captura de log de serviço de log centralizada no Skype for Business Server 2015.
  
Para capturar logs de rastreamento usando o serviço de log centralizado, você emite um comando para começar a fazer logon em um ou mais computadores e pools. Você também pode emitir parâmetros que definem quais computadores ou pools, quais cenários executar (por exemplo, AlwaysOn, outro cenário predefinido ou um cenário que você criou), quais componentes do Skype for Business Server (por exemplo, S4, SipStack) devem ser rastreados.
  
Para capturar informação certa, é necessário usar o cenário correto para coletar informação relevante ao problema. No serviço de log centralizado, um cenário é o conceito de ativar o registro em log com base em uma coleção de componentes do servidor, níveis de log e sinalizadores, que é muito mais eficiente e útil do que ter que definir esses elementos em uma base por servidor. Você define e especifica um cenário para executar e o cenário é executado consistentemente em todos os servidores e pools no escopo da infraestrutura.
  
O cenário padrão é chamado de **AlwaysOn**. O objetivo do AlwaysOn é executar o cenários constantemente, conforme o nome do cenário implica. O cenário AlwaysOn coleta informações de nível informativo (observe que o nível de log informativo inclui Fatal, Erro e Aviso, além das mensagens informativas) para boa parte da maioria dos componentes de servidor comum. AlwaysOn coleta informações antes, durante e após o problema ocorrer. Isso difere drasticamente do comportamento típico das ferramentas de log anteriores, como o OCSLogger. É possível executar OCSLogger após o problema ocorrer, dificultando seus esforços para resolução de problemas, pois os dados que você tem são reativos, não proativos. Se AlwaysOn não tem a informação que você está procurando a fim de indicar o componente do problema e um curso de ação para corrigi-lo (o que provavelmente não leva em conta a amplitude e profundidade dos provedores em AlwaysOn), ele indicará um nível adequado de informação para determinar o que mais deve ser feito, como criar um novo cenário, juntar outras informações, realizar uma busca diferente para coletar informações mais detalhadas, e assim por diante.
  
O serviço de log centralizado oferece duas maneiras de emitir comandos. Vários tópicos se concentraram de acordo com o uso do Windows PowerShell por meio do Shell de gerenciamento do Skype for Business Server. A capacidade de usar diversas configurações e comandos complexos favorece o Windows PowerShell para o uso centralizado do serviço de registro em log. Como o Windows PowerShell por meio do Shell de gerenciamento do Skype for Business Server é praticamente onipresente para todas as funções do Skype for Business Server, somente os comandos do Windows PowerShell são discutidos. 
  
### <a name="to-run-start-csclslogging-with-windows-powershell-using-basic-commands"></a>Para executar Start-CsClsLogging com o Windows PowerShell usando comandos básicos

1. Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.
    
2. Inicie um cenário de log com o serviço de log centralizado digitando o seguinte:
    
   ```PowerShell
   Start-CsClsLogging -Scenario <name of scenario>
   ```

    Por exemplo, para iniciar o cenário **AlwaysOn**, digite:
    
   ```PowerShell
   Start-CsClsLogging -Scenario AlwaysOn
   ```

    > [!NOTE]
    > O cenário AlwaysOn não tem uma duração padrão. Este cenário será executado até que o pare precisamente com o cmdlet **Stop-CsClsLogging**. Para detalhes, consulte [Stop-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/stop-csclslogging?view=skype-ps). Para todos os outros cenários, a duração padrão é 4 horas. 
  
3. Pressione Enter para executar o comando. 
    
    > [!NOTE]
    > Pode levar algum tempo (30 a 60 segundos) para que os comandos sejam executados e recebam o status dos computadores em sua implantação. 
  
     ![Executando Start-CsClsLogging.](../../media/Ops_CLS_Show_and_Start_ClsLogging.jpg)
  
4. Para iniciar outro cenários, use o cmdlet **Start-CsClsLogging** com o nome do cenário adicional para executar o seguinte (por exemplo, o cenário **Autenticação**):
    
   ```PowerShell
   Start-CsClsLogging -Scenario Authentication
   ```

    > [!IMPORTANT]
    > É possível ter um total de dois cenários sendo executados em qualquer computador a qualquer momento. Se o comando for de escopo global, todos os computadores em sua implantação executarão o(s) cenário(s). Para iniciar um terceiro cenário, você deve parar o log no escopo de computador, pool, site ou global em que você queira executar o novo cenário. Caso tenho iniciado um escopo global, é possível parar o log em um ou ambos cenários em um ou mais computadores e pools. 
  
### <a name="to-run-start-csclslogging-with-windows-powershell-using-advanced-commands"></a>Para executar Start-CsClsLogging com o Windows PowerShell usando comandos avançados

1. Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.
    
2. Estão disponíveis parâmetros adicionais para gerenciar os comandos de log. Você pode usar-Duration para ajustar o período de tempo que o cenário deve executar. Você também pode definir-computadores, uma lista de nomes de domínio totalmente qualificados do computador (FQDNs) separados por uma vírgula ou pools, uma lista de FQDNs separados por vírgula para os pools nos quais você deseja executar o logon.
    
    Você inicia uma sessão de log para o cenário UserReplicator no pool "pool01.contoso.net". Você também define duração da sessão de log em 8 horas. Para isso, digite:
    
   ```PowerShell
   Start-CsClsLogging -Scenario UserReplicator -Duration 8:00 -Pools "pool01.contoso.net"
   ```

    O execução com sucesso deste cenário devolve um resultado como o seguinte:
    
     ![Executando Start-CsClsLogging.](../../media/Ops_CsClsLogging_UserReplicator_Exp.jpg)
  
Observe que, neste exemplo, o cenário AlwaysOn é executado e o cenário UserReplicator também está sendo executado. 
    
## <a name="stop-the-centralized-logging-service-log-capture"></a>Interrompa a captura do log do Serviço de Registro em Log Centralizado
<a name="stop"> </a>

É possível parar uma sessão de registro em log em execução no momento com o cmdlet Stop-CsClsLogging. Geralmente, não há muitas situações em que você precisaria parar uma sessão de log. Por exemplo, é possível pesquisar logs e alterar as configurações sem antes precisar pará-lo. Se você tiver dois cenários em execução, como o AlwaysOn e o UserReplicator, e for necessário coletar informações relacionadas à Autenticação, será necessário parar um dos outros cenários (em um escopo global, site, pool ou computador) antes de poder iniciar a execução do cenário de Autenticação. Para obter detalhes, consulte [Stop-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/stop-csclslogging?view=skype-ps).
  
> [!NOTE]
> Ao determinar quais cenários podem ser executados em uma determinada implantação, pool ou computador, é necessário se lembrar de que você está limitado à execução de dois cenários **por computador**. Se você estiver registrando em log uma atividade em um pool, trate o pool como uma entidade única. Na maioria dos casos, não faria sentido executar cenários diferentes em cada computador em um pool. Não faz sentido analisar o problema sobre o qual você está coletando dados e pensar sobre qual cenário faz mais sentido em um determinado computador na implantação geral. Por exemplo, se você considerar o cenário userreplicator, haveria um valor muito baixo na execução do userreplicator em um servidor de borda ou em um pool de bordas. 
  
Depois de entender o problema e o escopo do impacto, faça escolhas cuidadosas sobre quais cenários executar em quais computadores e pools. Embora o cenário AlwaysOn faça sentido para um aplicativo de escopo amplo, pois coleta informações sobre uma ampla variedade de provedores, cenários específicos têm valor de aplicativo apenas em computadores ou pools específicos. Além disso, tome cuidado ao iniciar aleatoriamente uma sessão de registro em log sem antes entender o valor de um determinado cenário. Se você usar o cenário errado ou se usar um cenário apropriado para a tarefa e aplicar o cenário ao escopo errado (seja global, site, pool ou computador), poderá receber dados questionáveis e não muito úteis – como se não tivesse executado o cenário.
  
Para controlar as funções de serviço de log centralizado usando o Shell de gerenciamento do Skype for Business Server, você deve ser membro do grupo de segurança CsAdministrator ou do controle de acesso baseado em função do CsServerAdministrator (RBAC) ou uma função RBAC personalizada que contenha um desses dois grupos. Para retornar uma lista de todas as funções RBAC às quais esse cmdlet foi atribuído (incluindo qualquer função RBAC personalizada que você criou), execute o seguinte comando no Shell de gerenciamento do Skype for Business Server ou no prompt do Windows PowerShell:
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

Por exemplo:
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

> [!NOTE]
> Você deve estar se perguntando: agora que habilitou o registro em log, onde os logs são mantidos? Como você acessará as informações armazenadas nos logs usando consultas do Shell de gerenciamento enviadas aos agentes CLS e poderá gerar os resultados para vários formatos de arquivo possíveis, em que em cada servidor um agente CLS mantém seus registros não é realmente importante saber.  Os arquivos de log podem ser salvos em um local que você especifica e lido e analisado usando uma variedade de ferramentas, incluindo **Snooper. exe** e qualquer ferramenta que possa ler um arquivo de texto, como o **Notepad. exe**. O Snooper. exe faz parte das ferramentas de depuração do Skype for Business Server 2015 e está disponível como um [download da Web](https://go.microsoft.com/fwlink/p/?LinkId=285257).

### <a name="to-stop-a-currently-running-centralized-logging-service-session"></a>Para parar uma sessão de serviço de log centralizado em execução no momento

1. Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.
    
2. Consulte o serviço de log centralizado para descobrir quais cenários estão sendo executados digitando o seguinte:
    
   ```PowerShell
   Show-CsClsLogging
   ```

   ![Console do Windows PowerShell após chamar show-CsCl](../../media/Ops_Show_Stop_CsClsLogging.jpg)
  
   O resultado de Show-CsClsLogging é um resumo dos cenários em execução e em qual escopo eles estão em execução. Para obter detalhes, consulte [Show-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/show-csclslogging?view=skype-ps).
    
3. Para interromper uma sessão de registro em log atualmente em execução com um cenário específico, digite:
    
   ```PowerShell
   Stop-CsClsLogging -Scenario <scenario name> -Computers <comma separated list of fully qualified computer names> -Pools <comma separated list of fully qualified pool names>
   ```
   Por exemplo:
    
   ```PowerShell
   Stop-CsClsLogging -Scenario UserReplicator -Pools pool01.contoso.net
   ```

   Esse comando interromperá o registro em log com o cenário UserReplicator em pool01.contoso.net.
    
    > [!NOTE]
    > Os logs criados durante a sessão de registro em log usando o cenário UserReplicator não são excluídos. O registro em log ainda está disponível para execução de pesquisas usando o comando Search-CsClsLogging. Para obter detalhes, consulte [Search-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/search-csclslogging?view=skype-ps). 
  
Agindo como o comando acompanhante para Start-CsClsLogging, o cmdlet Stop-CsClsLogging encerra a sessão de registro em log, definida pelos cenários, e retém os logs criados pela sessão de registro em log. É possível executar dois cenários em um determinado computador a qualquer momento. O método de parar um cenário para coletar informações usando outro cenário é uma tarefa comum que pode ser executada durante grande parte das soluções de problemas de carga de trabalho.
## <a name="see-also"></a>Confira também
<a name="stop"> </a>

[Centralized Logging Service in Skype for Business 2015](centralized-logging-service.md)
