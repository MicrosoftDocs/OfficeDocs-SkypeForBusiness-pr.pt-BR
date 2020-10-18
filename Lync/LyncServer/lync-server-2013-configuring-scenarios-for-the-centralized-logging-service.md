---
title: 'Lync Server 2013: Configurando cenários para o serviço de registro em log centralizado'
description: 'Lync Server 2013: Configurando cenários para o serviço de registro em log centralizado.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring scenarios for the Centralized Logging Service
ms:assetid: 6c3bf826-e7fd-4002-95dc-01020641ef01
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688085(v=OCS.15)
ms:contentKeyID: 49733682
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1bf3f569ae8d2596f735851ae3d5d6c55f022b09
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575857"
---
# <a name="configuring-scenarios-for-the-centralized-logging-service-in-lync-server-2013"></a><span data-ttu-id="a2af1-103">Configurando cenários para o serviço de registro em log centralizado no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a2af1-103">Configuring scenarios for the Centralized Logging Service in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a2af1-104">_**Última modificação do tópico:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="a2af1-104">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="a2af1-105">Os cenários definem o escopo (ou seja, global, site, pool ou computador) e quais provedores usar no serviço de registro em log centralizado.</span><span class="sxs-lookup"><span data-stu-id="a2af1-105">Scenarios define the scope (that is, global, site, pool, or computer) and what providers to use in the Centralized Logging Service.</span></span> <span data-ttu-id="a2af1-106">Usando cenários, você habilita e desabilita o rastreamento nos provedores (por exemplo, S4, SIPStack, mensagens instantâneas e presença).</span><span class="sxs-lookup"><span data-stu-id="a2af1-106">By using scenarios, you enable or disable tracing on providers (for example, S4, SIPStack, IM, and Presence).</span></span> <span data-ttu-id="a2af1-107">Ao configurar um cenário, você pode agrupar todos os provedores de determinado conjunto lógico que tratam um problema específico.</span><span class="sxs-lookup"><span data-stu-id="a2af1-107">By configuring a scenario, you can group all of the providers for a given logical collection that address a specific problem condition.</span></span> <span data-ttu-id="a2af1-108">Se você achar que um cenário precisa ser modificado para atender às suas necessidades de solução de problemas e log, as ferramentas de depuração do Lync Server 2013 fornecem um módulo do Windows PowerShell chamado *ClsController. psm1* que contém uma função chamada *Edit-CsClsScenario*.</span><span class="sxs-lookup"><span data-stu-id="a2af1-108">If you find that a scenario needs to be modified to meet your troubleshooting and logging needs, the Lync Server 2013 Debug Tools provides you a Windows PowerShell module named *ClsController.psm1* that contains a function named *Edit-CsClsScenario*.</span></span> <span data-ttu-id="a2af1-109">A finalidade desse módulo é editar as propriedades do cenário nomeado.</span><span class="sxs-lookup"><span data-stu-id="a2af1-109">The purpose of the module is to edit the properties of the named scenario.</span></span> <span data-ttu-id="a2af1-110">Neste tópico, serão fornecidos exemplos de como esse módulo funciona.</span><span class="sxs-lookup"><span data-stu-id="a2af1-110">Examples of how this module works are provided in this topic.</span></span> <span data-ttu-id="a2af1-111">As ferramentas de depuração do Lync Server 2013 são baixadas do seguinte link: [https://go.microsoft.com/fwlink/?LinkId=285257](https://go.microsoft.com/fwlink/?linkid=285257)</span><span class="sxs-lookup"><span data-stu-id="a2af1-111">The Lync Server 2013 Debug Tools are downloaded from the following link: [https://go.microsoft.com/fwlink/?LinkId=285257](https://go.microsoft.com/fwlink/?linkid=285257)</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="a2af1-112">Para qualquer dado escopo (global, site, pool ou computador), é possível executar no máximo dois cenários por vez.</span><span class="sxs-lookup"><span data-stu-id="a2af1-112">For any given scope—site, global, pool or computer—you can run a maximum of two scenarios at any given time.</span></span> <span data-ttu-id="a2af1-113">Para determinar quais cenários estão em execução no momento, use o Windows PowerShell e o <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsClsScenario">Get-CsClsScenario</A>.</span><span class="sxs-lookup"><span data-stu-id="a2af1-113">To determine which scenarios are currently running, use Windows PowerShell and <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsClsScenario">Get-CsClsScenario</A>.</span></span> <span data-ttu-id="a2af1-114">Usando o Windows PowerShell e o <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsClsScenario">set-CsClsScenario</A>, você pode alterar dinamicamente quais cenários estão em execução.</span><span class="sxs-lookup"><span data-stu-id="a2af1-114">By using Windows PowerShell and <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsClsScenario">Set-CsClsScenario</A>, you can dynamically change which scenarios are running.</span></span> <span data-ttu-id="a2af1-115">Você pode modificar quais cenários estão em execução durante uma sessão de registro em log para ajustar ou refinar os dados coletados e de quais provedores.</span><span class="sxs-lookup"><span data-stu-id="a2af1-115">You can modify which scenarios are running during a logging session to adjust or refine the data you are collecting and from which providers.</span></span>



</div>

<span data-ttu-id="a2af1-116">Para executar as funções de serviço de registro em log centralizado usando o Shell de gerenciamento do Lync Server, você deve ser membro dos grupos de segurança do controle de acesso baseado em função do CsAdministrator ou do CsServerAdministrator, ou uma função RBAC personalizada que contenha um desses dois grupos.</span><span class="sxs-lookup"><span data-stu-id="a2af1-116">To run the Centralized Logging Service functions by using the Lync Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="a2af1-117">Para retornar uma lista de todas as funções RBAC às quais este cmdlet foi atribuído, incluindo qualquer função RBAC personalizada que você criou sozinho, execute o seguinte comando no Shell de gerenciamento do Lync Server ou no prompt do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="a2af1-117">To return a list of all the RBAC roles this cmdlet has been assigned to, including any custom RBAC roles you have created yourself, run the following command from the Lync Server Management Shell or the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Lync Server 2013 cmdlet"}

<span data-ttu-id="a2af1-118">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="a2af1-118">For example:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

<span data-ttu-id="a2af1-119">O restante deste tópico se concentra em como definir um cenário, modificar um cenário, recuperar quais cenários estão em execução, remover um cenário e especificar o que um cenário contém para otimizar a solução de problemas.</span><span class="sxs-lookup"><span data-stu-id="a2af1-119">The remainder of this topic focuses on how to define a scenario, modify a scenario, retrieve what scenarios are running, remove a scenario, and specify what a scenario contains to optimize your troubleshooting.</span></span> <span data-ttu-id="a2af1-120">Há duas maneiras de emitir comandos de serviço de registro centralizado.</span><span class="sxs-lookup"><span data-stu-id="a2af1-120">There are two ways to issue Centralized Logging Service commands.</span></span> <span data-ttu-id="a2af1-121">Você pode usar o CLSController.exe localizado, por padrão, no diretório C: Arquivos de \\ programas \\ comuns \\ do Microsoft Lync Server 2013 \\ CLSAgent.</span><span class="sxs-lookup"><span data-stu-id="a2af1-121">You can use the CLSController.exe that is located, by default, in the directory C:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\CLSAgent.</span></span> <span data-ttu-id="a2af1-122">Ou você pode usar o Shell de gerenciamento do Lync Server para emitir comandos do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a2af1-122">Or, you can use the Lync Server Management Shell to issue Windows PowerShell commands.</span></span> <span data-ttu-id="a2af1-123">A distinção importante é que, quando você usa CLSController.exe na linha de comando, há uma seleção finita de cenários disponíveis.</span><span class="sxs-lookup"><span data-stu-id="a2af1-123">The important distinction is that when you use CLSController.exe at the command line there is a finite selection of scenarios available.</span></span> <span data-ttu-id="a2af1-124">Ao usar o Windows PowerShell, você pode definir novos cenários para usar em suas sessões de registro em log.</span><span class="sxs-lookup"><span data-stu-id="a2af1-124">When you use Windows PowerShell, you can define new scenarios for use in your logging sessions.</span></span>

<span data-ttu-id="a2af1-125">Como apresentado na [visão geral do serviço de registro em log centralizado no Lync Server 2013](lync-server-2013-overview-of-the-centralized-logging-service.md), os elementos de um cenário são:</span><span class="sxs-lookup"><span data-stu-id="a2af1-125">As introduced in [Overview of the Centralized Logging Service in Lync Server 2013](lync-server-2013-overview-of-the-centralized-logging-service.md), the elements of a scenario are:</span></span>

  - <span data-ttu-id="a2af1-126">**Provedores**     Se você estiver familiarizado com o OCSLogger, os provedores são os componentes que você escolhe para informar ao OCSLogger o que o mecanismo de rastreamento deve coletar logs.</span><span class="sxs-lookup"><span data-stu-id="a2af1-126">**Providers**   If you are familiar with OCSLogger, providers are the components that you choose to tell OCSLogger what the tracing engine should collect logs from.</span></span> <span data-ttu-id="a2af1-127">Os provedores são os mesmos componentes e, em muitos casos, têm o mesmo nome que os componentes do OCSLogger.</span><span class="sxs-lookup"><span data-stu-id="a2af1-127">The providers are the same components, and in many cases have the same name as the components in OCSLogger.</span></span> <span data-ttu-id="a2af1-128">Se você não estiver familiarizado com o OCSLogger, os provedores são componentes específicos de função de servidor que o serviço de registro em log centralizado pode coletar logs.</span><span class="sxs-lookup"><span data-stu-id="a2af1-128">If you are not familiar with OCSLogger, providers are server role specific components that the Centralized Logging Service can collect logs from.</span></span> <span data-ttu-id="a2af1-129">Para obter detalhes sobre a configuração de provedores, consulte [Configuring Providers for central Logging Service in Lync Server 2013](lync-server-2013-configuring-providers-for-centralized-logging-service.md).</span><span class="sxs-lookup"><span data-stu-id="a2af1-129">For details about the configuration of providers, see [Configuring providers for Centralized Logging Service in Lync Server 2013](lync-server-2013-configuring-providers-for-centralized-logging-service.md).</span></span>

  - <span data-ttu-id="a2af1-130">**Identity**     O parâmetro – Identity define o escopo e o nome do cenário.</span><span class="sxs-lookup"><span data-stu-id="a2af1-130">**Identity**   The parameter –Identity sets the scope and name of the scenario.</span></span> <span data-ttu-id="a2af1-131">Por exemplo, você pode definir um escopo "global" e identificar o cenário como “LyssServiceScenario”.</span><span class="sxs-lookup"><span data-stu-id="a2af1-131">For example, you could set a scope of “global” and identify the scenario with “LyssServiceScenario”.</span></span> <span data-ttu-id="a2af1-132">Ao combinar os dois, você define a identidade (por exemplo, “global/LyssServiceScenario”).</span><span class="sxs-lookup"><span data-stu-id="a2af1-132">When you combine the two, you define the Identity (for example, “global/LyssServiceScenario”).</span></span>
    
    <span data-ttu-id="a2af1-p107">Opcionalmente, você pode usar os parâmetros –Name e –Parent. Você define o parâmetro Name para identificar exclusivamente o cenário. Se usá-lo, também deverá usar Parent para adicionar o cenário ao escopo global ou site.</span><span class="sxs-lookup"><span data-stu-id="a2af1-p107">Optionally, you can use the –Name and –Parent parameters. You define the Name parameter to uniquely identify the scenario. If you use Name, you must also use Parent to add the scenario to either global or site.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="a2af1-136">Se você usar os parâmetros Name e Parent, não poderá usar o parâmetro <STRONG>–Identity</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="a2af1-136">If you use the Name and Parent parameters, you cannot use the <STRONG>–Identity</STRONG> parameter.</span></span>

    
    </div>

<div>

## <a name="to-create-a-new-scenario-with-the-new-csclsscenario-cmdlet"></a><span data-ttu-id="a2af1-137">Para criar um novo cenário com o cmdlet New-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="a2af1-137">To create a new scenario with the New-CsClsScenario cmdlet</span></span>

1.  <span data-ttu-id="a2af1-138">Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="a2af1-138">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="a2af1-139">Para criar um novo cenário para uma sessão de registro em log, use [New-CsClsProvider](https://docs.microsoft.com/powershell/module/skype/New-CsClsProvider) e defina o nome do cenário (ou seja, como ele será identificado exclusivamente).</span><span class="sxs-lookup"><span data-stu-id="a2af1-139">To create a new scenario for a logging session, use [New-CsClsProvider](https://docs.microsoft.com/powershell/module/skype/New-CsClsProvider) and define the name of the scenario (that is, how it will be uniquely identified).</span></span> <span data-ttu-id="a2af1-140">Escolha um tipo de formato de registro em log entre WPP (ou seja, o pré-processador de rastreamento de software do Windows, que é o padrão), EventLog (ou seja, o formato de log de eventos do Windows) ou IISLog (ou seja, o arquivo de formato ASCII baseado no formato de arquivo de log do IIS).</span><span class="sxs-lookup"><span data-stu-id="a2af1-140">Choose a type of logging format from WPP (that is, Windows software tracing preprocessor and is the default), EventLog (that is, Windows event log format), or IISLog (that is, ASCII format file based on the IIS log file format).</span></span> <span data-ttu-id="a2af1-141">Em seguida, defina o nível (conforme definido em Níveis de registro em log neste tópico) e os sinalizadores (conforme definido em Sinalizadores neste tópico).</span><span class="sxs-lookup"><span data-stu-id="a2af1-141">Next, define Level (as the defined under Logging Levels in this topic), and Flags (as defined under Flags in this topic).</span></span>
    
    <span data-ttu-id="a2af1-142">Para este cenário de exemplo, usaremos LyssProvider como a variável de provedor de exemplo.</span><span class="sxs-lookup"><span data-stu-id="a2af1-142">For this example scenario, we use LyssProvider as the example provider variable.</span></span>
    
    <span data-ttu-id="a2af1-143">Para criar um cenário usando as opções definidas, digite:</span><span class="sxs-lookup"><span data-stu-id="a2af1-143">To create a scenario using the options defined, type:</span></span>
    
        New-CsClsScenario -Identity <scope>/<unique scenario name> -Provider <provider variable>
    
    <span data-ttu-id="a2af1-144">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="a2af1-144">For example:</span></span>
    
        New-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider $LyssProvider
    
    <span data-ttu-id="a2af1-145">Formato alternativo usando –Name e –Parent:</span><span class="sxs-lookup"><span data-stu-id="a2af1-145">The alternate format using –Name and –Parent:</span></span>
    
        New-CsClsScenario -Name "LyssServiceScenario" -Parent "site:Redmond" -Provider $LyssProvider

</div>

<div>

## <a name="to-create-a-new-scenario-with-multiple-providers-with-the-new-csclsscenario-cmdlet"></a><span data-ttu-id="a2af1-146">Para criar um novo cenário com vários provedores usando o cmdlet New-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="a2af1-146">To create a new scenario with multiple providers with the New-CsClsScenario cmdlet</span></span>

1.  <span data-ttu-id="a2af1-147">Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="a2af1-147">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="a2af1-148">Há um limite de dois cenários por escopo.</span><span class="sxs-lookup"><span data-stu-id="a2af1-148">You are limited to two scenarios per scope.</span></span> <span data-ttu-id="a2af1-149">No entanto, não há um limite quanto ao número de provedores.</span><span class="sxs-lookup"><span data-stu-id="a2af1-149">However, you are not limited to a set number of providers.</span></span> <span data-ttu-id="a2af1-150">Neste exemplo, suponha que criamos três provedores e você deseja atribuir todos eles ao cenário que está definindo.</span><span class="sxs-lookup"><span data-stu-id="a2af1-150">In this example, assume that we have created three providers, and you want to assign all three to the scenario you are defining.</span></span> <span data-ttu-id="a2af1-151">Os nomes das variáveis dos provedores são LyssProvider, ABServerProvider e SIPStackProvider.</span><span class="sxs-lookup"><span data-stu-id="a2af1-151">The provider variable names are LyssProvider, ABServerProvider, and SIPStackProvider.</span></span> <span data-ttu-id="a2af1-152">Para definir e atribuir vários provedores a um cenário, digite o seguinte em um shell de gerenciamento do Lync Server ou prompt de comando do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="a2af1-152">To define and assign multiple providers to a scenario, type the following at a Lync Server Management Shell or Windows PowerShell command prompt:</span></span>
    
        New-CsClsScenario -Identity "site:Redmond/CollectDataScenario" -Provider @{Add=$LyssProvider, $ABServerProvider,  $SIPStackProvider}
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a2af1-153">Como é conhecido no Windows PowerShell, a Convenção para criar uma tabela de hash de valores usando <CODE>@{&lt;variable&gt;=&lt;value1&gt;, &lt;value2&gt;, &lt;value&gt;...}</CODE> é conhecida como <EM>splatting</EM>.</span><span class="sxs-lookup"><span data-stu-id="a2af1-153">As it is known in Windows PowerShell, the convention for creating a hash table of values using <CODE>@{&lt;variable&gt;=&lt;value1&gt;, &lt;value2&gt;, &lt;value&gt;...}</CODE> is known as <EM>splatting</EM>.</span></span> <span data-ttu-id="a2af1-154">Para obter detalhes sobre o splatting no Windows PowerShell, consulte <A href="https://go.microsoft.com/fwlink/p/?linkid=267760">https://go.microsoft.com/fwlink/p/?LinkId=267760</A> .</span><span class="sxs-lookup"><span data-stu-id="a2af1-154">For details about splatting in Windows PowerShell, see <A href="https://go.microsoft.com/fwlink/p/?linkid=267760">https://go.microsoft.com/fwlink/p/?LinkId=267760</A>.</span></span>

    
    </div>

</div>

<div>

## <a name="to-modify-an-existing-scenario-with-the-set-csclsscenario-cmdlet"></a><span data-ttu-id="a2af1-155">Para modificar um cenário existente com o cmdlet Set-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="a2af1-155">To modify an existing scenario with the Set-CsClsScenario cmdlet</span></span>

1.  <span data-ttu-id="a2af1-156">Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="a2af1-156">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="a2af1-p111">Há um limite de dois cenários por escopo. Você pode alterar quais cenários estão em execução a qualquer momento, mesmo quando uma sessão de coleta de log está em andamento. Se você redefinir os cenários em execução, a sessão de registro em log atual parará de usar o cenário que foi removido e começará a usar o novo cenário. No entanto, as informações de log que já foram coletadas com o cenário removido permanecerão nos logs coletados. Para definir um novo cenário, faça o seguinte (pressupondo a adição de um provedor já definido chamado “S4Provider”):</span><span class="sxs-lookup"><span data-stu-id="a2af1-p111">You are limited to two scenarios per scope. You can change which scenarios are running at any time, even when a logging capture session is in process. If you redefine the running scenarios, the current logging session will stop using the scenario that was removed and then begin using the new scenario. However, the logging information that was captured with the removed scenario remains in the captured logs. To define a new scenario, do the following (that is, assuming the addition of an already defined provider named “S4Provider”):</span></span>
    
        Set-CsClsScenario -Identity <name of scope and scenario defined by New-CsClsScenario> -Provider @{Add=<new provider to add>}
    
    <span data-ttu-id="a2af1-162">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="a2af1-162">For example:</span></span>
    
        Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Add=$S4Provider}
    
    <span data-ttu-id="a2af1-p112">Se você desejar substituir provedores, defina um único provedor ou uma lista separada por vírgulas de provedores para substituir o conjunto atual. Se você desejar substituir apenas um de vários provedores, adicione os provedores atuais junto com os novos provedores para criar um novo conjunto de provedores que contenha os provedores novos e existentes. Para substituir todos os provedores por um novo conjunto, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="a2af1-p112">If you want to replace providers, define a single provider or a comma separated list of providers to replace the current set. If you only want to replace one of many providers, add the current providers with the new providers to create a new set of providers that contains both new providers and existing providers. To replace all providers with a new set, type the following:</span></span>
    
        Set-CsClsScenario -Identity <name of scope and scenario defined by New-CsClsScenario> -Provider @{Replace=<providers to replace existing provider set>}
    
    <span data-ttu-id="a2af1-166">Por exemplo, para substituir o conjunto atual de $LyssProvider, $ABServerProvider e $SIPStackProvider por $LyssServiceProvider:</span><span class="sxs-lookup"><span data-stu-id="a2af1-166">For example, to replace the current set of $LyssProvider, $ABServerProvider, and $SIPStackProvider with $LyssServiceProvider:</span></span>
    
        Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Replace=$LyssServiceProvider}
    
    <span data-ttu-id="a2af1-167">Para substituir apenas o provedor $LyssProvider do conjunto atual de $LyssProvider, $ABServerProvider e $SIPStackProvider por $LyssServiceProvider, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="a2af1-167">To replace just the $LyssProvider provider from the current set of $LyssProvider, $ABServerProvider, and $SIPStackProvider with $LyssServiceProvider, type the following:</span></span>
    
        Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Replace=$LyssServiceProvider, $ABServerProvider, $SIPStackProvider}

</div>

<div>

## <a name="to-remove-an-existing-scenario-with-the-remove-csclsscenario-cmdlet"></a><span data-ttu-id="a2af1-168">Para remover um cenário existente com o cmdlet Remove-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="a2af1-168">To remove an existing scenario with the Remove-CsClsScenario cmdlet</span></span>

1.  <span data-ttu-id="a2af1-169">Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="a2af1-169">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="a2af1-170">Se você desejar remover um cenário que foi definido anteriormente, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="a2af1-170">If you want to remove a scenario that has been previously defined, type the following:</span></span>
    
        Remove-CsClsScenario -Identity <name of scope and scenario>
    
    <span data-ttu-id="a2af1-171">Por exemplo, para remover o cenário definido site:Redmond/LyssServiceScenario:</span><span class="sxs-lookup"><span data-stu-id="a2af1-171">For example, to remove the defined scenario site:Redmond/LyssServiceScenario:</span></span>
    
        Remove-CsClsScenario -Identity "site:Redmond/LyssServiceScenario"

<span data-ttu-id="a2af1-172">O cmdlet **Remove-CsClsScenario** remove o cenário especificado, mas os rastreamentos que foram coletados ainda estarão disponíveis nos logs para pesquisa.</span><span class="sxs-lookup"><span data-stu-id="a2af1-172">The **Remove-CsClsScenario** cmdlet removes the specified scenario, but the traces that have been captured are still available in the logs for you to search on.</span></span>

</div>

<div>

## <a name="to-load-and-unload-the-edit-csclsscenario-cmdlet-using-the-clscontrollerpsm1-module"></a><span data-ttu-id="a2af1-173">Para carregar e descarregar o cmdlet Edit-CsClsScenario usando o módulo ClsController.psm1</span><span class="sxs-lookup"><span data-stu-id="a2af1-173">To load and unload the Edit-CsClsScenario cmdlet using the ClsController.psm1 module</span></span>

1.  <span data-ttu-id="a2af1-174">Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="a2af1-174">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="a2af1-175">O módulo ClsController.psm1 é fornecido como um download da Web separado.</span><span class="sxs-lookup"><span data-stu-id="a2af1-175">The ClsController.psm1 module is provided as a separate Web download.</span></span> <span data-ttu-id="a2af1-176">O módulo faz parte das ferramentas de depuração do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a2af1-176">The module is part of the Lync Server 2013 Debugging tools.</span></span> <span data-ttu-id="a2af1-177">Por padrão, as ferramentas de depuração são instaladas no diretório C:\Program Files\Lync Server 2013\Debugging Tools.</span><span class="sxs-lookup"><span data-stu-id="a2af1-177">By default, the debugging tools are installed in the directory C:\Program Files\Lync Server 2013\Debugging Tools.</span></span>

    
    </div>

2.  <span data-ttu-id="a2af1-178">No Windows PowerShell, digite:</span><span class="sxs-lookup"><span data-stu-id="a2af1-178">From the Windows PowerShell, type:</span></span>
    
        Import-Module "C:\Program Files\Lync Server 2013\Debugging Tools\ClsController.psm1"
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="a2af1-179">O carregamento bem-sucedido do módulo retorna ao prompt de comando do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a2af1-179">Successful loading of the module returns you to the Windows PowerShell command prompt.</span></span> <span data-ttu-id="a2af1-180">Para confirmar que o módulo está carregado e que o Edit-CsClsScenario está disponível, digite <CODE>Get-Help Edit-CsClsScenario</CODE> .</span><span class="sxs-lookup"><span data-stu-id="a2af1-180">To confirm that the module is loaded and that Edit-CsClsScenario is available, type <CODE>Get-Help Edit-CsClsScenario</CODE>.</span></span> <span data-ttu-id="a2af1-181">Você deverá ver a sinopse básica da sintaxe de EditCsClsScenario.</span><span class="sxs-lookup"><span data-stu-id="a2af1-181">You should see the basic synopsis of the syntax for EditCsClsScenario.</span></span>

    
    </div>

3.  <span data-ttu-id="a2af1-182">Para descarregar os módulos, digite:</span><span class="sxs-lookup"><span data-stu-id="a2af1-182">To unload the modules, type:</span></span>
    
        Remove-Module ClsController
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="a2af1-183">O descarregamento bem-sucedido do módulo retorna ao prompt de comando do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a2af1-183">Successful unloading of the module returns you to the Windows PowerShell command prompt.</span></span> <span data-ttu-id="a2af1-184">Para confirmar que o módulo é descarregado, digite <CODE>Get-Help Edit-CsClsScenario</CODE> .</span><span class="sxs-lookup"><span data-stu-id="a2af1-184">To confirm that the module is unloaded, type <CODE>Get-Help Edit-CsClsScenario</CODE>.</span></span> <span data-ttu-id="a2af1-185">O Windows PowerShell tentará localizar a ajuda para o cmdlet e falhará.</span><span class="sxs-lookup"><span data-stu-id="a2af1-185">Windows PowerShell will attempt to locate the help for the cmdlet and fail.</span></span>

    
    </div>

</div>

<div>

## <a name="to-remove-an-existing-provider-from-a-scenario-with-the-edit-clscontroller-module"></a><span data-ttu-id="a2af1-186">Para remover um provedor existente de um cenário com o módulo Edit-ClsController</span><span class="sxs-lookup"><span data-stu-id="a2af1-186">To remove an existing provider from a scenario with the Edit-ClsController module</span></span>

1.  <span data-ttu-id="a2af1-187">Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="a2af1-187">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="a2af1-188">Para remover um provedor do cenário AlwaysOn, digite:</span><span class="sxs-lookup"><span data-stu-id="a2af1-188">To remove a provider from the AlwaysOn scenario, type:</span></span>
    
        Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to remove> -Remove
    
    <span data-ttu-id="a2af1-189">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="a2af1-189">For Example:</span></span>
    
        Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Remove
    
    <span data-ttu-id="a2af1-p116">Os parâmetros ScenarioName e ProviderName são posicionais (ou seja, devem ser definidos na posição esperada na linha de comando). O nome do parâmetro não precisa ser explicitamente definido se o nome do cenário estiver na segunda ou na terceira posição em relação ao nome do cmdlet na primeira posição. Usando essas informações, o comando anterior seria digitado como:</span><span class="sxs-lookup"><span data-stu-id="a2af1-p116">The parameters ScenarioName and ProviderName are positional (that is, they must be defined in the expected position in the command line) parameters. The parameter name does not have to be explicitly defined if the scenario name is in position two and the provider is in position three, relative to the name of the cmdlet as position one. Using this information, the previous command would be typed as:</span></span>
    
        Edit-CsClsScenario AlwaysOn ChatServer -Remove
    
    <span data-ttu-id="a2af1-p117">A colocação posicional dos valores de parâmetro aplica-se somente a –Scenario e –Provider. Todos os outros parâmetros devem ser definidos explicitamente.</span><span class="sxs-lookup"><span data-stu-id="a2af1-p117">The positional placing of the parameter values applies only to –Scenario and –Provider. All other parameters must be explicitly defined.</span></span>

</div>

<div>

## <a name="to-add-a-provider-to-a-scenario-with-the-edit-clscontroller-module"></a><span data-ttu-id="a2af1-195">Para adicionar um provedor a um cenário com o cmdlet Edit-ClsController</span><span class="sxs-lookup"><span data-stu-id="a2af1-195">To add a provider to a scenario with the Edit-ClsController module</span></span>

1.  <span data-ttu-id="a2af1-196">Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="a2af1-196">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="a2af1-197">Para adicionar um provedor ao cenário AlwaysOn, digite:</span><span class="sxs-lookup"><span data-stu-id="a2af1-197">To add a provider to the AlwaysOn scenario, type:</span></span>
    
        Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to add> -Level <string of type level> -Flags <string of type flags>
    
    <span data-ttu-id="a2af1-198">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="a2af1-198">For Example:</span></span>
    
        Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Level Info -Flags TF_COMPONENT
    
    <span data-ttu-id="a2af1-199">\-LogLevel pode ser do tipo fatal, erro, aviso, info, Verbose, debug ou ALL.</span><span class="sxs-lookup"><span data-stu-id="a2af1-199">\-Loglevel can be of the type Fatal, Error, Warning, Info, Verbose, Debug, or All.</span></span> <span data-ttu-id="a2af1-200">– Os sinalizadores podem ser qualquer um dos sinalizadores aos quais o provedor oferece suporte, como o \_ componente TF, TF \_ diag.</span><span class="sxs-lookup"><span data-stu-id="a2af1-200">–Flags can be any of the flags that the provider supports, such as TF\_COMPONENT, TF\_DIAG.</span></span> <span data-ttu-id="a2af1-201">–Flags também pode ter o valor ALL.</span><span class="sxs-lookup"><span data-stu-id="a2af1-201">–Flags can also be of value ALL</span></span>
    
    <span data-ttu-id="a2af1-p119">O exemplo anterior também pode ser digitado com o uso do recurso posicional do cmdlet. Por exemplo, para adicionar o provedor ChatServer ao cenário AlwaysOn, digite:</span><span class="sxs-lookup"><span data-stu-id="a2af1-p119">The previous example can also be typed using the positional feature of the cmdlet. For example, to add the provider ChatServer to the AlwaysOn scenario, type:</span></span>
    
        Edit-CsClsScenario AlwaysOn ChatServer -Level Info -Flags ALL

</div>

</div>

<span> </span>

</div>

</div>

</div>

