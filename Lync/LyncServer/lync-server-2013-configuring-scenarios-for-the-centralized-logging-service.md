---
title: 'Lync Server 2013: Configurando cenários para o serviço de log centralizado'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring scenarios for the Centralized Logging Service
ms:assetid: 6c3bf826-e7fd-4002-95dc-01020641ef01
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688085(v=OCS.15)
ms:contentKeyID: 49733682
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: abc0be2ac6459c34546de41ee7e2c709e0d0c0f8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836183"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-scenarios-for-the-centralized-logging-service-in-lync-server-2013"></a><span data-ttu-id="2c741-102">Configurar cenários para o serviço de log centralizado no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2c741-102">Configuring scenarios for the Centralized Logging Service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2c741-103">_**Tópico da última modificação:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="2c741-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="2c741-104">Cenários definem o escopo (ou seja, global, site, pool ou computador) e quais provedores usar no serviço de log centralizado.</span><span class="sxs-lookup"><span data-stu-id="2c741-104">Scenarios define the scope (that is, global, site, pool, or computer) and what providers to use in the Centralized Logging Service.</span></span> <span data-ttu-id="2c741-105">Ao utilizar cenários, você habilita ou desabilita o rastreamento em provedores (por exemplo, S4, SIPStack, mensagens instantâneas e Presença).</span><span class="sxs-lookup"><span data-stu-id="2c741-105">By using scenarios, you enable or disable tracing on providers (for example, S4, SIPStack, IM, and Presence).</span></span> <span data-ttu-id="2c741-106">Ao configurar um cenário, você pode agrupar todos os provedores de uma determinada coleção lógica que aborda uma condição de problema específica.</span><span class="sxs-lookup"><span data-stu-id="2c741-106">By configuring a scenario, you can group all of the providers for a given logical collection that address a specific problem condition.</span></span> <span data-ttu-id="2c741-107">Se você descobrir que um cenário precisa ser modificado para atender às suas necessidades de solução de problemas e log, as ferramentas de depuração do Lync Server 2013 fornecem um módulo do Windows PowerShell chamado *ClsController. psm1* que contém uma função nomeada \*Edit-CsClsScenario \*.</span><span class="sxs-lookup"><span data-stu-id="2c741-107">If you find that a scenario needs to be modified to meet your troubleshooting and logging needs, the Lync Server 2013 Debug Tools provides you a Windows PowerShell module named *ClsController.psm1* that contains a function named *Edit-CsClsScenario*.</span></span> <span data-ttu-id="2c741-108">O objetivo do módulo é editar as propriedades do cenário nomeado.</span><span class="sxs-lookup"><span data-stu-id="2c741-108">The purpose of the module is to edit the properties of the named scenario.</span></span> <span data-ttu-id="2c741-109">Exemplos do funcionamento desse módulo são fornecidos neste tópico.</span><span class="sxs-lookup"><span data-stu-id="2c741-109">Examples of how this module works are provided in this topic.</span></span> <span data-ttu-id="2c741-110">As ferramentas de depuração do Lync Server 2013 são baixadas do link a seguir:[http://go.microsoft.com/fwlink/?LinkId=285257](http://go.microsoft.com/fwlink/?linkid=285257)</span><span class="sxs-lookup"><span data-stu-id="2c741-110">The Lync Server 2013 Debug Tools are downloaded from the following link: [http://go.microsoft.com/fwlink/?LinkId=285257](http://go.microsoft.com/fwlink/?linkid=285257)</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="2c741-111">Seja qual for o escopo (global, site, pool ou computador), é possível executar no máximo dois cenários por vez.</span><span class="sxs-lookup"><span data-stu-id="2c741-111">For any given scope—site, global, pool or computer—you can run a maximum of two scenarios at any given time.</span></span> <span data-ttu-id="2c741-112">Para determinar quais cenários estão sendo executados no momento, use o Windows PowerShell e <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsClsScenario">Get-CsClsScenario</A>.</span><span class="sxs-lookup"><span data-stu-id="2c741-112">To determine which scenarios are currently running, use Windows PowerShell and <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsClsScenario">Get-CsClsScenario</A>.</span></span> <span data-ttu-id="2c741-113">Usando o Windows PowerShell e o <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsClsScenario">set-CsClsScenario</A>, você pode alterar dinamicamente quais cenários estão em execução.</span><span class="sxs-lookup"><span data-stu-id="2c741-113">By using Windows PowerShell and <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsClsScenario">Set-CsClsScenario</A>, you can dynamically change which scenarios are running.</span></span> <span data-ttu-id="2c741-114">Você pode modificar quais cenários estão em execução durante uma sessão de registro em log para ajustar ou refinar os dados coletados e de quais provedores.</span><span class="sxs-lookup"><span data-stu-id="2c741-114">You can modify which scenarios are running during a logging session to adjust or refine the data you are collecting and from which providers.</span></span>



</div>

<span data-ttu-id="2c741-115">Para executar as funções de serviço de log centralizado usando o Shell de gerenciamento do Lync Server, você deve ser membro do grupo de segurança CsAdministrator ou do controle de acesso baseado em função do CsServerAdministrator (RBAC) ou uma função RBAC personalizada que contenha um desses dois grupos.</span><span class="sxs-lookup"><span data-stu-id="2c741-115">To run the Centralized Logging Service functions by using the Lync Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="2c741-116">Para retornar uma lista de todas as funções RBAC às quais esse cmdlet foi atribuído, incluindo qualquer função RBAC personalizada que você tenha criado, execute o seguinte comando no Shell de gerenciamento do Lync Server ou no prompt do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="2c741-116">To return a list of all the RBAC roles this cmdlet has been assigned to, including any custom RBAC roles you have created yourself, run the following command from the Lync Server Management Shell or the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Lync Server 2013 cmdlet"}

<span data-ttu-id="2c741-117">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="2c741-117">For example:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

<span data-ttu-id="2c741-118">O restante deste tópico concentra-se em como definir um cenário, modificar um cenário, determinar quais cenários estão em execução e especificar o que está contido em um cenário para otimizar a solução de problemas.</span><span class="sxs-lookup"><span data-stu-id="2c741-118">The remainder of this topic focuses on how to define a scenario, modify a scenario, retrieve what scenarios are running, remove a scenario, and specify what a scenario contains to optimize your troubleshooting.</span></span> <span data-ttu-id="2c741-119">Há duas maneiras de emitir comandos de serviço de log centralizado.</span><span class="sxs-lookup"><span data-stu-id="2c741-119">There are two ways to issue Centralized Logging Service commands.</span></span> <span data-ttu-id="2c741-120">Você pode usar o CLSController. exe localizado, por padrão, no\\diretório C: Arquivos de programas\\comuns\\Microsoft Lync Server 2013\\CLSAgent.</span><span class="sxs-lookup"><span data-stu-id="2c741-120">You can use the CLSController.exe that is located, by default, in the directory C:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\CLSAgent.</span></span> <span data-ttu-id="2c741-121">Ou você pode usar o Shell de gerenciamento do Lync Server para emitir comandos do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2c741-121">Or, you can use the Lync Server Management Shell to issue Windows PowerShell commands.</span></span> <span data-ttu-id="2c741-122">A diferença importante é que, quando você usa o CLSController. exe na linha de comando, há uma seleção finita de cenários disponíveis.</span><span class="sxs-lookup"><span data-stu-id="2c741-122">The important distinction is that when you use CLSController.exe at the command line there is a finite selection of scenarios available.</span></span> <span data-ttu-id="2c741-123">Ao usar o Windows PowerShell, você pode definir novos cenários para usar em suas sessões de registro em log.</span><span class="sxs-lookup"><span data-stu-id="2c741-123">When you use Windows PowerShell, you can define new scenarios for use in your logging sessions.</span></span>

<span data-ttu-id="2c741-124">Como apresentado na [visão geral do serviço de log centralizado no Lync Server 2013](lync-server-2013-overview-of-the-centralized-logging-service.md), os elementos de um cenário são:</span><span class="sxs-lookup"><span data-stu-id="2c741-124">As introduced in [Overview of the Centralized Logging Service in Lync Server 2013](lync-server-2013-overview-of-the-centralized-logging-service.md), the elements of a scenario are:</span></span>

  - <span data-ttu-id="2c741-125">**Provedores**   se você estiver familiarizado com o OCSLogger, os provedores são os componentes que você escolhe para OCSLogger o que o mecanismo de rastreamento deve coletar logs.</span><span class="sxs-lookup"><span data-stu-id="2c741-125">**Providers**   If you are familiar with OCSLogger, providers are the components that you choose to tell OCSLogger what the tracing engine should collect logs from.</span></span> <span data-ttu-id="2c741-126">Os provedores são os mesmos componentes e, em muitos casos, têm o mesmo nome que os componentes do OCSLogger.</span><span class="sxs-lookup"><span data-stu-id="2c741-126">The providers are the same components, and in many cases have the same name as the components in OCSLogger.</span></span> <span data-ttu-id="2c741-127">Se você não estiver familiarizado com o OCSLogger, os provedores são componentes específicos de função de servidor que o serviço de log centralizado pode coletar logs.</span><span class="sxs-lookup"><span data-stu-id="2c741-127">If you are not familiar with OCSLogger, providers are server role specific components that the Centralized Logging Service can collect logs from.</span></span> <span data-ttu-id="2c741-128">Para obter detalhes sobre a configuração de provedores, consulte Configurando [provedores para o serviço de log centralizado no Lync Server 2013](lync-server-2013-configuring-providers-for-centralized-logging-service.md).</span><span class="sxs-lookup"><span data-stu-id="2c741-128">For details about the configuration of providers, see [Configuring providers for Centralized Logging Service in Lync Server 2013](lync-server-2013-configuring-providers-for-centralized-logging-service.md).</span></span>

  - <span data-ttu-id="2c741-129">**Identity**   o parâmetro – Identity define o escopo e o nome do cenário.</span><span class="sxs-lookup"><span data-stu-id="2c741-129">**Identity**   The parameter –Identity sets the scope and name of the scenario.</span></span> <span data-ttu-id="2c741-130">Por exemplo, você pode definir um escopo "global" e identificar o cenário como “LyssServiceScenario”.</span><span class="sxs-lookup"><span data-stu-id="2c741-130">For example, you could set a scope of “global” and identify the scenario with “LyssServiceScenario”.</span></span> <span data-ttu-id="2c741-131">Ao combinar os dois, você define a identidade (por exemplo, “global/LyssServiceScenario”).</span><span class="sxs-lookup"><span data-stu-id="2c741-131">When you combine the two, you define the Identity (for example, “global/LyssServiceScenario”).</span></span>
    
    <span data-ttu-id="2c741-p107">Opcionalmente, você pode usar os parâmetros –Name e –Parent. Você define o parâmetro Name para identificar exclusivamente o cenário. Se usá-lo, também deverá usar Parent para adicionar o cenário ao escopo global ou site.</span><span class="sxs-lookup"><span data-stu-id="2c741-p107">Optionally, you can use the –Name and –Parent parameters. You define the Name parameter to uniquely identify the scenario. If you use Name, you must also use Parent to add the scenario to either global or site.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="2c741-135">Se você usar os parâmetros Name e Parent, não poderá usar o parâmetro <STRONG>–Identity</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="2c741-135">If you use the Name and Parent parameters, you cannot use the <STRONG>–Identity</STRONG> parameter.</span></span>

    
    </div>

<div>

## <a name="to-create-a-new-scenario-with-the-new-csclsscenario-cmdlet"></a><span data-ttu-id="2c741-136">Para criar um novo cenário com o cmdlet New-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="2c741-136">To create a new scenario with the New-CsClsScenario cmdlet</span></span>

1.  <span data-ttu-id="2c741-137">Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="2c741-137">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="2c741-p108">Para criar um novo cenário para uma sessão de registro em log, use [New-CsClsProvider](https://docs.microsoft.com/powershell/module/skype/New-CsClsProvider) e defina o nome do cenário (ou seja, como ele será identificado exclusivamente). Escolha um tipo de formato de registro em log entre WPP (ou seja, o pré-processador de rastreamento de software do Windows, que é o padrão), EventLog (ou seja, o formato de log de eventos do Windows) ou IISLog (ou seja, o arquivo de formato ASCII baseado no formato de arquivo de log do IIS). Em seguida, defina o nível (conforme definido em Níveis de registro em log, neste tópico) e os sinalizadores (conforme definido em Sinalizadores, neste tópico).</span><span class="sxs-lookup"><span data-stu-id="2c741-p108">To create a new scenario for a logging session, use [New-CsClsProvider](https://docs.microsoft.com/powershell/module/skype/New-CsClsProvider) and define the name of the scenario (that is, how it will be uniquely identified). Choose a type of logging format from WPP (that is, Windows software tracing preprocessor and is the default), EventLog (that is, Windows event log format), or IISLog (that is, ASCII format file based on the IIS log file format). Next, define Level (as the defined under Logging Levels in this topic), and Flags (as defined under Flags in this topic).</span></span>
    
    <span data-ttu-id="2c741-141">Para este cenário de exemplo, usaremos LyssProvider como a variável de provedor de exemplo.</span><span class="sxs-lookup"><span data-stu-id="2c741-141">For this example scenario, we use LyssProvider as the example provider variable.</span></span>
    
    <span data-ttu-id="2c741-142">Para criar um cenário usando as opções definidas, digite:</span><span class="sxs-lookup"><span data-stu-id="2c741-142">To create a scenario using the options defined, type:</span></span>
    
        New-CsClsScenario -Identity <scope>/<unique scenario name> -Provider <provider variable>
    
    <span data-ttu-id="2c741-143">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="2c741-143">For example:</span></span>
    
        New-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider $LyssProvider
    
    <span data-ttu-id="2c741-144">Formato alternativo usando –Name e –Parent:</span><span class="sxs-lookup"><span data-stu-id="2c741-144">The alternate format using –Name and –Parent:</span></span>
    
        New-CsClsScenario -Name "LyssServiceScenario" -Parent "site:Redmond" -Provider $LyssProvider

</div>

<div>

## <a name="to-create-a-new-scenario-with-multiple-providers-with-the-new-csclsscenario-cmdlet"></a><span data-ttu-id="2c741-145">Para criar um novo cenário com vários provedores usando o cmdlet New-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="2c741-145">To create a new scenario with multiple providers with the New-CsClsScenario cmdlet</span></span>

1.  <span data-ttu-id="2c741-146">Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="2c741-146">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="2c741-147">Há um limite de dois cenários por escopo.</span><span class="sxs-lookup"><span data-stu-id="2c741-147">You are limited to two scenarios per scope.</span></span> <span data-ttu-id="2c741-148">No entanto, não há um limite quanto ao número de provedores.</span><span class="sxs-lookup"><span data-stu-id="2c741-148">However, you are not limited to a set number of providers.</span></span> <span data-ttu-id="2c741-149">Neste exemplo, vamos supor que criamos três provedores e você deseja atribuir todos eles ao cenário que está definindo.</span><span class="sxs-lookup"><span data-stu-id="2c741-149">In this example, assume that we have created three providers, and you want to assign all three to the scenario you are defining.</span></span> <span data-ttu-id="2c741-150">Os nomes das variáveis dos provedores são LyssProvider, ABServerProvider e SIPStackProvider.</span><span class="sxs-lookup"><span data-stu-id="2c741-150">The provider variable names are LyssProvider, ABServerProvider, and SIPStackProvider.</span></span> <span data-ttu-id="2c741-151">Para definir e atribuir vários provedores a um cenário, digite o seguinte em um shell de gerenciamento do Lync Server ou prompt de comando do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="2c741-151">To define and assign multiple providers to a scenario, type the following at a Lync Server Management Shell or Windows PowerShell command prompt:</span></span>
    
        New-CsClsScenario -Identity "site:Redmond/CollectDataScenario" -Provider @{Add=$LyssProvider, $ABServerProvider,  $SIPStackProvider}
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2c741-152">Como é conhecido no Windows PowerShell, a Convenção para criar uma tabela de hash de valores usando <CODE>@{&lt;variable&gt;=&lt;value1&gt;, &lt;value2&gt;, &lt;value&gt;...}</CODE> é conhecida como <EM>splatting</EM>.</span><span class="sxs-lookup"><span data-stu-id="2c741-152">As it is known in Windows PowerShell, the convention for creating a hash table of values using <CODE>@{&lt;variable&gt;=&lt;value1&gt;, &lt;value2&gt;, &lt;value&gt;...}</CODE> is known as <EM>splatting</EM>.</span></span> <span data-ttu-id="2c741-153">Para obter detalhes sobre o splatting no Windows PowerShell <A href="http://go.microsoft.com/fwlink/p/?linkid=267760">http://go.microsoft.com/fwlink/p/?LinkId=267760</A>, consulte.</span><span class="sxs-lookup"><span data-stu-id="2c741-153">For details about splatting in Windows PowerShell, see <A href="http://go.microsoft.com/fwlink/p/?linkid=267760">http://go.microsoft.com/fwlink/p/?LinkId=267760</A>.</span></span>

    
    </div>

</div>

<div>

## <a name="to-modify-an-existing-scenario-with-the-set-csclsscenario-cmdlet"></a><span data-ttu-id="2c741-154">Para modificar um cenário existente com o cmdlet Set-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="2c741-154">To modify an existing scenario with the Set-CsClsScenario cmdlet</span></span>

1.  <span data-ttu-id="2c741-155">Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="2c741-155">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="2c741-p111">Há um limite de dois cenários por escopo. Você pode alterar quais cenários estão em execução a qualquer momento, mesmo quando uma sessão de coleta de log está em andamento. Se você redefinir os cenários em execução, a sessão de registro em log atual parará de usar o cenário que foi removido e começará a usar o novo cenário. No entanto, as informações de log que já foram coletadas com o cenário removido permanecerão nos logs coletados. Para definir um novo cenário, faça o seguinte (pressupondo a adição de um provedor já definido chamado “S4Provider”):</span><span class="sxs-lookup"><span data-stu-id="2c741-p111">You are limited to two scenarios per scope. You can change which scenarios are running at any time, even when a logging capture session is in process. If you redefine the running scenarios, the current logging session will stop using the scenario that was removed and then begin using the new scenario. However, the logging information that was captured with the removed scenario remains in the captured logs. To define a new scenario, do the following (that is, assuming the addition of an already defined provider named “S4Provider”):</span></span>
    
        Set-CsClsScenario -Identity <name of scope and scenario defined by New-CsClsScenario> -Provider @{Add=<new provider to add>}
    
    <span data-ttu-id="2c741-161">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="2c741-161">For example:</span></span>
    
        Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Add=$S4Provider}
    
    <span data-ttu-id="2c741-p112">Se você desejar substituir provedores, defina um único provedor ou uma lista separada por vírgulas de provedores para substituir o conjunto atual. Se você desejar substituir apenas um de vários provedores, adicione os provedores atuais junto com os novos provedores para criar um novo conjunto de provedores que contenha os provedores novos e existentes. Para substituir todos os provedores por um novo conjunto, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="2c741-p112">If you want to replace providers, define a single provider or a comma separated list of providers to replace the current set. If you only want to replace one of many providers, add the current providers with the new providers to create a new set of providers that contains both new providers and existing providers. To replace all providers with a new set, type the following:</span></span>
    
        Set-CsClsScenario -Identity <name of scope and scenario defined by New-CsClsScenario> -Provider @{Replace=<providers to replace existing provider set>}
    
    <span data-ttu-id="2c741-165">Por exemplo, para substituir o conjunto atual de $LyssProvider, $ABServerProvider e $SIPStackProvider por $LyssServiceProvider:</span><span class="sxs-lookup"><span data-stu-id="2c741-165">For example, to replace the current set of $LyssProvider, $ABServerProvider, and $SIPStackProvider with $LyssServiceProvider:</span></span>
    
        Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Replace=$LyssServiceProvider}
    
    <span data-ttu-id="2c741-166">Para substituir apenas o provedor $LyssProvider do conjunto atual de $LyssProvider, $ABServerProvider e $SIPStackProvider por $LyssServiceProvider, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="2c741-166">To replace just the $LyssProvider provider from the current set of $LyssProvider, $ABServerProvider, and $SIPStackProvider with $LyssServiceProvider, type the following:</span></span>
    
        Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Replace=$LyssServiceProvider, $ABServerProvider, $SIPStackProvider}

</div>

<div>

## <a name="to-remove-an-existing-scenario-with-the-remove-csclsscenario-cmdlet"></a><span data-ttu-id="2c741-167">Para remover um cenário existente com o cmdlet Remove-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="2c741-167">To remove an existing scenario with the Remove-CsClsScenario cmdlet</span></span>

1.  <span data-ttu-id="2c741-168">Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="2c741-168">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="2c741-169">Se você desejar remover um cenário que foi definido anteriormente, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="2c741-169">If you want to remove a scenario that has been previously defined, type the following:</span></span>
    
        Remove-CsClsScenario -Identity <name of scope and scenario>
    
    <span data-ttu-id="2c741-170">Por exemplo, para remover o cenário definido site:Redmond/LyssServiceScenario:</span><span class="sxs-lookup"><span data-stu-id="2c741-170">For example, to remove the defined scenario site:Redmond/LyssServiceScenario:</span></span>
    
        Remove-CsClsScenario -Identity "site:Redmond/LyssServiceScenario"

<span data-ttu-id="2c741-171">O cmdlet **Remove-CsClsScenario** remove o cenário especificado, mas os rastreamentos que foram coletados ainda estarão disponíveis nos logs para pesquisa.</span><span class="sxs-lookup"><span data-stu-id="2c741-171">The **Remove-CsClsScenario** cmdlet removes the specified scenario, but the traces that have been captured are still available in the logs for you to search on.</span></span>

</div>

<div>

## <a name="to-load-and-unload-the-edit-csclsscenario-cmdlet-using-the-clscontrollerpsm1-module"></a><span data-ttu-id="2c741-172">Para carregar e descarregar o cmdlet Edit-CsClsScenario usando o módulo ClsController. psm1</span><span class="sxs-lookup"><span data-stu-id="2c741-172">To load and unload the Edit-CsClsScenario cmdlet using the ClsController.psm1 module</span></span>

1.  <span data-ttu-id="2c741-173">Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="2c741-173">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="2c741-174">O módulo ClsController. psm1 é fornecido como um download da Web separado.</span><span class="sxs-lookup"><span data-stu-id="2c741-174">The ClsController.psm1 module is provided as a separate Web download.</span></span> <span data-ttu-id="2c741-175">O módulo faz parte das ferramentas de depuração do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2c741-175">The module is part of the Lync Server 2013 Debugging tools.</span></span> <span data-ttu-id="2c741-176">Por padrão, as ferramentas de depuração são instaladas no diretório C:\Arquivos de Files\Lync Server 2013 \ ferramentas de depuração.</span><span class="sxs-lookup"><span data-stu-id="2c741-176">By default, the debugging tools are installed in the directory C:\Program Files\Lync Server 2013\Debugging Tools.</span></span>

    
    </div>

2.  <span data-ttu-id="2c741-177">No Windows PowerShell, digite:</span><span class="sxs-lookup"><span data-stu-id="2c741-177">From the Windows PowerShell, type:</span></span>
    
        Import-Module "C:\Program Files\Lync Server 2013\Debugging Tools\ClsController.psm1"
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="2c741-178">O carregamento bem-sucedido do módulo o devolve para o prompt de comando do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2c741-178">Successful loading of the module returns you to the Windows PowerShell command prompt.</span></span> <span data-ttu-id="2c741-179">Para confirmar se o módulo está carregado e se o Edit-CsClsScenario está disponível, <CODE>Get-Help Edit-CsClsScenario</CODE>digite.</span><span class="sxs-lookup"><span data-stu-id="2c741-179">To confirm that the module is loaded and that Edit-CsClsScenario is available, type <CODE>Get-Help Edit-CsClsScenario</CODE>.</span></span> <span data-ttu-id="2c741-180">Você deverá ver a sinopse básica da sintaxe de EditCsClsScenario.</span><span class="sxs-lookup"><span data-stu-id="2c741-180">You should see the basic synopsis of the syntax for EditCsClsScenario.</span></span>

    
    </div>

3.  <span data-ttu-id="2c741-181">Para descarregar os módulos, digite:</span><span class="sxs-lookup"><span data-stu-id="2c741-181">To unload the modules, type:</span></span>
    
        Remove-Module ClsController
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="2c741-182">O descarregamento bem-sucedido do módulo retorna para o prompt de comando do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2c741-182">Successful unloading of the module returns you to the Windows PowerShell command prompt.</span></span> <span data-ttu-id="2c741-183">Para confirmar se o módulo é descarregado, <CODE>Get-Help Edit-CsClsScenario</CODE>digite.</span><span class="sxs-lookup"><span data-stu-id="2c741-183">To confirm that the module is unloaded, type <CODE>Get-Help Edit-CsClsScenario</CODE>.</span></span> <span data-ttu-id="2c741-184">O Windows PowerShell tentará localizar a ajuda para o cmdlet e falhar.</span><span class="sxs-lookup"><span data-stu-id="2c741-184">Windows PowerShell will attempt to locate the help for the cmdlet and fail.</span></span>

    
    </div>

</div>

<div>

## <a name="to-remove-an-existing-provider-from-a-scenario-with-the-edit-clscontroller-module"></a><span data-ttu-id="2c741-185">Para remover um provedor existente de um cenário com o módulo Edit-ClsController</span><span class="sxs-lookup"><span data-stu-id="2c741-185">To remove an existing provider from a scenario with the Edit-ClsController module</span></span>

1.  <span data-ttu-id="2c741-186">Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="2c741-186">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="2c741-187">Para remover um provedor do cenário AlwaysOn, digite:</span><span class="sxs-lookup"><span data-stu-id="2c741-187">To remove a provider from the AlwaysOn scenario, type:</span></span>
    
        Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to remove> -Remove
    
    <span data-ttu-id="2c741-188">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="2c741-188">For Example:</span></span>
    
        Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Remove
    
    <span data-ttu-id="2c741-p116">Os parâmetros ScenarioName e ProviderName são posicionais (ou seja, devem ser definidos na posição esperada na linha de comando). O nome do parâmetro não precisa ser explicitamente definido se o nome do cenário estiver na segunda ou na terceira posição em relação ao nome do cmdlet na primeira posição. Usando essas informações, o comando anterior seria digitado como:</span><span class="sxs-lookup"><span data-stu-id="2c741-p116">The parameters ScenarioName and ProviderName are positional (that is, they must be defined in the expected position in the command line) parameters. The parameter name does not have to be explicitly defined if the scenario name is in position two and the provider is in position three, relative to the name of the cmdlet as position one. Using this information, the previous command would be typed as:</span></span>
    
        Edit-CsClsScenario AlwaysOn ChatServer -Remove
    
    <span data-ttu-id="2c741-p117">A colocação posicional dos valores de parâmetro aplica-se somente a –Scenario e –Provider. Todos os outros parâmetros devem ser definidos explicitamente.</span><span class="sxs-lookup"><span data-stu-id="2c741-p117">The positional placing of the parameter values applies only to –Scenario and –Provider. All other parameters must be explicitly defined.</span></span>

</div>

<div>

## <a name="to-add-a-provider-to-a-scenario-with-the-edit-clscontroller-module"></a><span data-ttu-id="2c741-194">Para adicionar um provedor a um cenário com o cmdlet Edit-ClsController</span><span class="sxs-lookup"><span data-stu-id="2c741-194">To add a provider to a scenario with the Edit-ClsController module</span></span>

1.  <span data-ttu-id="2c741-195">Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="2c741-195">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="2c741-196">Para adicionar um provedor ao cenário AlwaysOn, digite:</span><span class="sxs-lookup"><span data-stu-id="2c741-196">To add a provider to the AlwaysOn scenario, type:</span></span>
    
        Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to add> -Level <string of type level> -Flags <string of type flags>
    
    <span data-ttu-id="2c741-197">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="2c741-197">For Example:</span></span>
    
        Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Level Info -Flags TF_COMPONENT
    
    <span data-ttu-id="2c741-198">\-LogLevel pode ser do tipo fatal, Error, Warning, info, Verbose, debug ou ALL.</span><span class="sxs-lookup"><span data-stu-id="2c741-198">\-Loglevel can be of the type Fatal, Error, Warning, Info, Verbose, Debug, or All.</span></span> <span data-ttu-id="2c741-199">– Os sinalizadores podem ser qualquer um dos sinalizadores compatíveis com o provedor, como o\_componente TF,\_TF diag.</span><span class="sxs-lookup"><span data-stu-id="2c741-199">–Flags can be any of the flags that the provider supports, such as TF\_COMPONENT, TF\_DIAG.</span></span> <span data-ttu-id="2c741-200">–Flags também pode ter o valor ALL</span><span class="sxs-lookup"><span data-stu-id="2c741-200">–Flags can also be of value ALL</span></span>
    
    <span data-ttu-id="2c741-p119">O exemplo anterior também pode ser digitado com o uso do recurso posicional do cmdlet. Por exemplo, para adicionar o provedor ChatServer ao cenário AlwaysOn, digite:</span><span class="sxs-lookup"><span data-stu-id="2c741-p119">The previous example can also be typed using the positional feature of the cmdlet. For example, to add the provider ChatServer to the AlwaysOn scenario, type:</span></span>
    
        Edit-CsClsScenario AlwaysOn ChatServer -Level Info -Flags ALL

</div>

</div>

<span> </span>

</div>

</div>

</div>

