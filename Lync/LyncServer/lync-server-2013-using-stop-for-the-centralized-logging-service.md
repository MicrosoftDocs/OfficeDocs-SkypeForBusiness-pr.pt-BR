---
title: 'Lync Server 2013: usando a parada para o serviço de log centralizado'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using Stop for the Centralized Logging Service
ms:assetid: 09ac093e-8f30-4874-84b4-12548ac8c898
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687964(v=OCS.15)
ms:contentKeyID: 49733549
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 521328b688f90ca591abddb3e59e7d49ae771b15
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844459"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-stop-for-the-centralized-logging-service-in-lync-server-2013"></a>Usar stop para o serviço de log centralizado no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-11-01_

É possível parar uma sessão de registro em log em execução no momento com o cmdlet Stop-CsClsLogging. Geralmente, não há muitas situações nas quais é necessário parar uma sessão de registro em log. Por exemplo, é possível pesquisar logs e alterar as configurações sem antes precisar pará-lo. Se você tiver dois cenários em execução, como o AlwaysOn e o UserReplicator, e for necessário coletar informações relacionadas à Autenticação, será necessário parar um dos outros cenários (em um escopo global, site, pool ou computador) antes de poder iniciar a execução do cenário de Autenticação. Para obter detalhes, consulte [Stop-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/Stop-CsClsLogging).

<div>


> [!NOTE]  
> Ao determinar quais cenários você pode executar em uma determinada implantação, pool ou computador, você precisa se lembrar de que está limitado a executar dois cenários <STRONG>por computador</STRONG>. Se você estiver registrando em log uma atividade em um pool, trate o pool como uma entidade única. Na maioria dos casos, não faria sentido executar cenários diferentes em cada computador em um pool. Não faz sentido analisar o problema sobre o qual você está coletando dados e pensar sobre qual cenário faz mais sentido em um determinado computador na implantação geral. Por exemplo, se você considerar o cenário userreplicator, haveria um valor muito baixo na execução do userreplicator em um servidor de borda ou em um pool de bordas.<BR>Depois de entender o problema e o escopo do impacto, faça escolhas cuidadosas sobre quais cenários executar em quais computadores e pools. Embora o cenário AlwaysOn faça sentido para um aplicativo de escopo amplo, pois coleta informações sobre uma ampla variedade de provedores, cenários específicos têm valor de aplicativo apenas em computadores ou pools específicos. Além disso, tome cuidado ao iniciar aleatoriamente uma sessão de registro em log sem antes entender o valor de um determinado cenário. Se você usar o cenário errado ou se usar um cenário apropriado para a tarefa e aplicar o cenário ao escopo errado (seja global, site, pool ou computador), poderá receber dados questionáveis e não muito úteis – como se não tivesse executado o cenário.



</div>

Para controlar as funções do serviço de log centralizado usando o Shell de gerenciamento do Lync Server, você deve ser membro do grupo de segurança CsAdministrator ou do controle de acesso baseado em função do CsServerAdministrator (RBAC) ou uma função RBAC personalizada que contenha qualquer um desses dois grupos. Para retornar uma lista de todas as funções RBAC às quais esse cmdlet foi atribuído (incluindo qualquer função RBAC personalizada que você criou), execute o seguinte comando no Shell de gerenciamento do Lync Server ou no prompt do Windows PowerShell:

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Lync Server 2013 cmdlet"}

Por exemplo:

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

<div>

## <a name="to-stop-a-currently-running-centralized-logging-service-session"></a>Para parar uma sessão de serviço de log centralizado em execução no momento

1.  Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.

2.  Consulte o serviço de log centralizado para descobrir quais cenários estão sendo executados digitando o seguinte:
    
        Show-CsClsLogging
    
    ![Console do Windows PowerShell após chamar show-CSCL] (images/JJ687964.eb190c32-529c-4277-a731-52c47d22d8fa(OCS.15).jpg "Console do Windows PowerShell após chamar show-CSCL")
    
    O resultado de Show-CsClsLogging é um resumo dos cenários em execução e em qual escopo eles estão em execução. Para obter detalhes, consulte [Show-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/Show-CsClsLogging).

3.  Para interromper uma sessão de registro em log atualmente em execução com um cenário específico, digite:
    
        Stop-CsClsLogging -Scenario <scenario name> -Computers <comma separated list of fully qualified computer names> -Pools <comma separated list of fully qualified pool names>
    
    Por exemplo:
    
        Stop-CsClsLogging -Scenario UserReplicator -Pools pool01.contoso.net
    
    Esse comando interromperá o registro em log com o cenário UserReplicator em pool01.contoso.net.
    
    <div>
    

    > [!NOTE]  
    > Os logs criados durante a sessão de registro em log usando o cenário UserReplicator não são excluídos. O registro em log ainda está disponível para execução de pesquisas usando o comando Search-CsClsLogging. Para obter detalhes, consulte <A href="https://docs.microsoft.com/powershell/module/skype/Search-CsClsLogging">Search-CsClsLogging</A>.

    
    </div>

Agindo como o comando acompanhante para Start-CsClsLogging, o cmdlet Stop-CsClsLogging encerra a sessão de registro em log, definida pelos cenários, e retém os logs criados pela sessão de registro em log. É possível executar dois cenários em um determinado computador a qualquer momento. O método de parar um cenário para coletar informações usando outro cenário é uma tarefa comum que pode ser executada durante grande parte das soluções de problemas de carga de trabalho.

</div>

<div>

## <a name="see-also"></a>Confira também


[Usar o Start para o serviço de log centralizado para capturar logs no Lync Server 2013](lync-server-2013-using-start-for-the-centralized-logging-service-to-capture-logs.md)  


[Visão geral do serviço de log centralizado no Lync Server 2013](lync-server-2013-overview-of-the-centralized-logging-service.md)  


[Show-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/Show-CsClsLogging)  
[Start-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/Start-CsClsLogging)  
[Parar-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/Stop-CsClsLogging)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

