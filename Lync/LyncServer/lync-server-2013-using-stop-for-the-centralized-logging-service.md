---
title: 'Lync Server 2013: usando stop para o serviço de registro em log centralizado'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Stop for the Centralized Logging Service
ms:assetid: 09ac093e-8f30-4874-84b4-12548ac8c898
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687964(v=OCS.15)
ms:contentKeyID: 49733549
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ed971c014eb62f539dcb6551a78066a3462688ac
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529958"
---
# <a name="using-stop-for-the-centralized-logging-service-in-lync-server-2013"></a><span data-ttu-id="56f26-102">Usando stop para o serviço de registro em log centralizado no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="56f26-102">Using Stop for the Centralized Logging Service in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="56f26-103">_**Última modificação do tópico:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="56f26-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="56f26-104">É possível parar uma sessão de registro em log em execução no momento com o cmdlet Stop-CsClsLogging.</span><span class="sxs-lookup"><span data-stu-id="56f26-104">You can stop a currently running logging session with the Stop-CsClsLogging cmdlet.</span></span> <span data-ttu-id="56f26-105">Geralmente, não há muitas situações nas quais é necessário parar uma sessão de registro em log.</span><span class="sxs-lookup"><span data-stu-id="56f26-105">Generally, there aren’t many situations in which you would need to stop a logging session.</span></span> <span data-ttu-id="56f26-106">Por exemplo, é possível pesquisar logs e alterar as configurações sem antes precisar parar o registro em log.</span><span class="sxs-lookup"><span data-stu-id="56f26-106">For example, you can search logs and change configurations without first needing to stop logging.</span></span> <span data-ttu-id="56f26-107">Se você tiver dois cenários em execução, por exemplo AlwaysOn e UserReplicator, e for necessário coletar informações relacionadas à Autenticação, será necessário parar um dos outros cenários (em um escopo global, site, pool ou computador) antes de poder iniciar a execução do cenário de Autenticação.</span><span class="sxs-lookup"><span data-stu-id="56f26-107">If you have two scenarios running, for example AlwaysOn and UserReplicator, and you need to collect information related to Authentication, you will need to stop one of the other scenarios (at a global, site, pool or computer scope) before you can start running to Authentication scenario.</span></span> <span data-ttu-id="56f26-108">Para obter detalhes, consulte [Stop-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/Stop-CsClsLogging).</span><span class="sxs-lookup"><span data-stu-id="56f26-108">For details, see [Stop-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/Stop-CsClsLogging).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="56f26-109">Ao determinar quais cenários podem ser executados em uma determinada implantação, pool ou computador, é necessário se lembrar de que você está limitado à execução de dois cenários <STRONG>por computador</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="56f26-109">When determining what scenarios you can run on a given deployment, pool or computer, you need to remember that you are limited to running two scenarios <STRONG>per computer</STRONG>.</span></span> <span data-ttu-id="56f26-110">Se você estiver registrando em log uma atividade em um pool, trate um pool como uma entidade única.</span><span class="sxs-lookup"><span data-stu-id="56f26-110">If you are logging activity on a pool, you should treat a pool as a single entity.</span></span> <span data-ttu-id="56f26-111">Na maioria dos casos, não faria sentido executar cenários diferentes em cada computador em um pool.</span><span class="sxs-lookup"><span data-stu-id="56f26-111">In most cases, it would not make sense to run different scenarios on each computer in a pool.</span></span> <span data-ttu-id="56f26-112">Não faz sentido analisar o problema sobre o qual você está coletando dados e pensar sobre qual cenário faz mais sentido em um determinado computador na implantação geral.</span><span class="sxs-lookup"><span data-stu-id="56f26-112">It does make sense to look at the problem that you are collecting data about and think about what scenario makes the most sense on a given computer in the overall deployment.</span></span> <span data-ttu-id="56f26-113">Por exemplo, se você considerar o cenário userreplicator, haveria muito pouco valor na execução do userreplicador em um servidor de borda ou em um pool de borda.</span><span class="sxs-lookup"><span data-stu-id="56f26-113">For example, if you consider the UserReplicator scenario, there would be very little value in running UserReplicator on an Edge Server or Edge pool.</span></span><BR><span data-ttu-id="56f26-p103">Depois de entender o problema e o escopo do impacto, faça escolhas cuidadosas sobre quais cenários executar em quais computadores e pools. Embora o cenário AlwaysOn faça sentido para um aplicativo de escopo amplo, pois coleta informações sobre uma ampla variedade de provedores, cenários específicos têm valor de aplicativo apenas em computadores ou pools específicos. Além disso, tome cuidado ao iniciar aleatoriamente uma sessão de registro em log sem antes entender o valor de um determinado cenário. Se você usar o cenário errado ou se usar um cenário apropriado para a tarefa e aplicar o cenário ao escopo errado (seja global, site, pool ou computador), poderá receber dados questionáveis e não muito úteis—como se não tivesse executado o cenário.</span><span class="sxs-lookup"><span data-stu-id="56f26-p103">After you understand the problem and the scope of the impact, you should make careful choices about what scenarios to run on which computers and pools. While the AlwaysOn scenario makes sense for a wide scope application because it collects information on a wide variety of providers, specific scenarios only have application value on specific computers or pools. Also, you should take caution when randomly starting up a logging session without first understanding the value of a given scenario. If you use the wrong scenario, or if you use a scenario that is appropriate for the task and you apply the scenario at the wrong scope (be it global, site, pool, or computer), you can get questionable data that is not very useful—as if you didn't run the scenario at all.</span></span>



</div>

<span data-ttu-id="56f26-118">Para controlar as funções de serviço de registro centralizado usando o Shell de gerenciamento do Lync Server, você deve ser membro dos grupos de segurança do controle de acesso baseado em função do CsAdministrator ou do CsServerAdministrator, ou uma função RBAC personalizada que contenha um desses dois grupos.</span><span class="sxs-lookup"><span data-stu-id="56f26-118">To control the Centralized Logging Service functions by using the Lync Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="56f26-119">Para retornar uma lista de todas as funções RBAC às quais este cmdlet foi atribuído (incluindo qualquer função RBAC personalizada que você criou sozinho), execute o seguinte comando no Shell de gerenciamento do Lync Server ou no prompt do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="56f26-119">To return a list of all the RBAC roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Lync Server Management Shell or the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Lync Server 2013 cmdlet"}

<span data-ttu-id="56f26-120">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="56f26-120">For example:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

<div>

## <a name="to-stop-a-currently-running-centralized-logging-service-session"></a><span data-ttu-id="56f26-121">Para interromper uma sessão de serviço de registro em log centralizado no momento</span><span class="sxs-lookup"><span data-stu-id="56f26-121">To stop a currently running Centralized Logging Service session</span></span>

1.  <span data-ttu-id="56f26-122">Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="56f26-122">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="56f26-123">Consulte o serviço de registro em log centralizado para saber quais cenários estão sendo executados, digitando o seguinte:</span><span class="sxs-lookup"><span data-stu-id="56f26-123">Query the Centralized Logging Service to find out what scenarios are currently running by typing the following:</span></span>
    
        Show-CsClsLogging
    
    <span data-ttu-id="56f26-124">![Console do Windows PowerShell depois de chamar show-CsCl](images/JJ687964.eb190c32-529c-4277-a731-52c47d22d8fa(OCS.15).jpg "Console do Windows PowerShell depois de chamar Show-CsCl")</span><span class="sxs-lookup"><span data-stu-id="56f26-124">![Windows PowerShell console after calling Show-CsCl](images/JJ687964.eb190c32-529c-4277-a731-52c47d22d8fa(OCS.15).jpg "Windows PowerShell console after calling Show-CsCl")</span></span>
    
    <span data-ttu-id="56f26-125">O resultado de Show-CsClsLogging é um resumo dos cenários em execução e em qual escopo eles estão em execução.</span><span class="sxs-lookup"><span data-stu-id="56f26-125">The result of Show-CsClsLogging is a summary of the scenarios that are running and what scope they are running in.</span></span> <span data-ttu-id="56f26-126">Para obter detalhes, consulte [Show-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/Show-CsClsLogging).</span><span class="sxs-lookup"><span data-stu-id="56f26-126">For details, see [Show-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/Show-CsClsLogging).</span></span>

3.  <span data-ttu-id="56f26-127">Para interromper uma sessão de registro em log atualmente em execução com um cenário específico, digite:</span><span class="sxs-lookup"><span data-stu-id="56f26-127">To stop a currently running logging session with a specific scenario, type:</span></span>
    
        Stop-CsClsLogging -Scenario <scenario name> -Computers <comma separated list of fully qualified computer names> -Pools <comma separated list of fully qualified pool names>
    
    <span data-ttu-id="56f26-128">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="56f26-128">For example:</span></span>
    
        Stop-CsClsLogging -Scenario UserReplicator -Pools pool01.contoso.net
    
    <span data-ttu-id="56f26-129">Esse comando interromperá o registro em log com o cenário UserReplicatior em pool01.contoso.net.</span><span class="sxs-lookup"><span data-stu-id="56f26-129">This command will stop logging with the UserReplicatior scenario on pool01.contoso.net.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="56f26-130">Os logs criados durante a sessão de registro em log usando o cenário UserReplicator não são excluídos.</span><span class="sxs-lookup"><span data-stu-id="56f26-130">Logs created during this logging session using the UserReplicator scenario are not deleted.</span></span> <span data-ttu-id="56f26-131">O registro em log ainda está disponível para execução de pesquisas usando o comando Search-CsClsLogging.</span><span class="sxs-lookup"><span data-stu-id="56f26-131">The logging is still available for you to execute searches against using the Search-CsClsLogging command.</span></span> <span data-ttu-id="56f26-132">Para obter detalhes, consulte <A href="https://docs.microsoft.com/powershell/module/skype/Search-CsClsLogging">Search-CsClsLogging</A>.</span><span class="sxs-lookup"><span data-stu-id="56f26-132">For details, see <A href="https://docs.microsoft.com/powershell/module/skype/Search-CsClsLogging">Search-CsClsLogging</A>.</span></span>

    
    </div>

<span data-ttu-id="56f26-p107">Agindo como o comando acompanhante para Start-CsClsLogging, o cmdlet Stop-CsClsLogging encerra a sessão de registro em log, definida pelos cenários, e retém os logs criados pela sessão de registro em log. É possível executar dois cenários em um determinado computador a qualquer momento. O método de parar um cenário para coletar informações usando outro cenário é uma tarefa comum que pode ser executada durante grande parte das soluções de problemas de carga de trabalho.</span><span class="sxs-lookup"><span data-stu-id="56f26-p107">Acting as the companion command to Start-CsClsLogging, the Stop-CsClsLogging cmdlet ends the logging session, defined by scenarios, and retains the logs created by the logging session. You can run two scenarios on a given computer at any time. The method of stopping one scenario to gather information using another scenario is a common task that you can perform during most workload troubleshooting.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="56f26-136">Confira também</span><span class="sxs-lookup"><span data-stu-id="56f26-136">See Also</span></span>


[<span data-ttu-id="56f26-137">Usando iniciar para o serviço de registro em log centralizado para capturar logs no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="56f26-137">Using Start for the Centralized Logging Service to capture logs in Lync Server 2013</span></span>](lync-server-2013-using-start-for-the-centralized-logging-service-to-capture-logs.md)  


[<span data-ttu-id="56f26-138">Visão geral do serviço de registro em log centralizado no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="56f26-138">Overview of the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-overview-of-the-centralized-logging-service.md)  


[<span data-ttu-id="56f26-139">Show-CsClsLogging</span><span class="sxs-lookup"><span data-stu-id="56f26-139">Show-CsClsLogging</span></span>](https://docs.microsoft.com/powershell/module/skype/Show-CsClsLogging)  
[<span data-ttu-id="56f26-140">Start-CsClsLogging</span><span class="sxs-lookup"><span data-stu-id="56f26-140">Start-CsClsLogging</span></span>](https://docs.microsoft.com/powershell/module/skype/Start-CsClsLogging)  
[<span data-ttu-id="56f26-141">Stop-CsClsLogging</span><span class="sxs-lookup"><span data-stu-id="56f26-141">Stop-CsClsLogging</span></span>](https://docs.microsoft.com/powershell/module/skype/Stop-CsClsLogging)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

