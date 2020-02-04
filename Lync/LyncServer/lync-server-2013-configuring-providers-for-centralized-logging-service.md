---
title: 'Lync Server 2013: Configurando provedores para o serviço de log centralizado'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring providers for Centralized Logging Service
ms:assetid: 6a197ecf-b56b-45e0-8e7c-f532ec5164ff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688082(v=OCS.15)
ms:contentKeyID: 49733678
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2428bd11e656d0f1b6295e63ca6106fa7edcbb15
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734835"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-providers-for-centralized-logging-service-in-lync-server-2013"></a><span data-ttu-id="87ce3-102">Configurando provedores para o serviço de log centralizado no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="87ce3-102">Configuring providers for Centralized Logging Service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="87ce3-103">_**Tópico da última modificação:** 2014-03-19_</span><span class="sxs-lookup"><span data-stu-id="87ce3-103">_**Topic Last Modified:** 2014-03-19_</span></span>

<span data-ttu-id="87ce3-104">Os conceitos e a configuração de *provedores* no serviço de log centralizado são um dos mais importantes para entender.</span><span class="sxs-lookup"><span data-stu-id="87ce3-104">The concepts and configuration of *providers* in Centralized Logging Service is one of the most important to grasp.</span></span> <span data-ttu-id="87ce3-105">Os *provedores* mapeiam diretamente para os componentes da função de servidor do Lync Server no modelo de rastreamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="87ce3-105">The *providers* map directly to Lync Server server role components in the Lync Server tracing model.</span></span> <span data-ttu-id="87ce3-106">O provedor define os componentes de um Lync Server 2013 que serão rastreados, o tipo de mensagens (por exemplo, fatal, erro ou aviso) a serem coletadas e os sinalizadores (por exemplo, TF\_conexão ou TF\_diag).</span><span class="sxs-lookup"><span data-stu-id="87ce3-106">The provider defines the components of a Lync Server 2013 that will be traced, the type of messages (for example, fatal, error, or warning) to collect, and the flags (for example, TF\_Connection or TF\_Diag).</span></span> <span data-ttu-id="87ce3-107">Provedores são os componentes rastreáveis em cada função de servidor do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="87ce3-107">Providers are the traceable components in each Lync Server server role.</span></span> <span data-ttu-id="87ce3-108">Usando provedores, você define o nível e o tipo de rastreamento nos componentes (por exemplo, S4, SIPStack, mensagens instantâneas e presença).</span><span class="sxs-lookup"><span data-stu-id="87ce3-108">By using providers, you define the level and type of tracing on components (for example, S4, SIPStack, IM and Presence).</span></span> <span data-ttu-id="87ce3-109">O provedor definido é usado em um cenário para agrupar todos os provedores de um determinado conjunto lógico que tratam de um problema específico.</span><span class="sxs-lookup"><span data-stu-id="87ce3-109">The defined provider is used in a scenario to group all of the providers for a given logical collection that address a specific problem condition.</span></span>

<span data-ttu-id="87ce3-110">Para executar as funções do serviço de log centralizado usando o Shell de gerenciamento do Lync Server, você deve ser membro do grupo de segurança CsAdministrator ou do controle de acesso baseado em função do CsServerAdministrator (RBAC), ou uma função RBAC personalizada que contém um dos esses dois grupos.</span><span class="sxs-lookup"><span data-stu-id="87ce3-110">To run the Centralized Logging Service functions using the Lync Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="87ce3-111">Para retornar uma lista de todas as funções de controle de acesso baseado em função (RBAC) às quais esse cmdlet foi atribuído (incluindo qualquer função RBAC personalizada que você criou), execute o seguinte comando no Shell de gerenciamento do Lync Server ou no prompt do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="87ce3-111">To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Lync Server Management Shell or the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Lync Server 2013 cmdlet"}

<span data-ttu-id="87ce3-112">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="87ce3-112">For example:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

<span data-ttu-id="87ce3-113">O restante deste tópico concentra-se em como definir provedores, modificar um provedor e no que contém uma definição de provedor para otimizar a solução de problemas.</span><span class="sxs-lookup"><span data-stu-id="87ce3-113">The remainder of this topic focuses on how to define providers, modify a provider and what a provider definition contains to optimize your troubleshooting.</span></span> <span data-ttu-id="87ce3-114">Há duas maneiras de emitir comandos de serviço de log centralizado.</span><span class="sxs-lookup"><span data-stu-id="87ce3-114">There are two ways to issue Centralized Logging Service commands.</span></span> <span data-ttu-id="87ce3-115">Você pode usar o CLSController. exe localizado, por padrão, no\\diretório C: Arquivos de programas\\comuns\\Microsoft Lync Server 2013\\CLSAgent.</span><span class="sxs-lookup"><span data-stu-id="87ce3-115">You can use the CLSController.exe that is located, by default, in the directory C:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\CLSAgent.</span></span> <span data-ttu-id="87ce3-116">Ou você pode usar o Shell de gerenciamento do Lync Server para emitir comandos do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="87ce3-116">Or, you can use the Lync Server Management Shell to issue Windows PowerShell commands.</span></span> <span data-ttu-id="87ce3-117">A diferença importante é que, quando você usa CLSController. exe na linha de comando, há uma seleção finita de cenários disponíveis em que os provedores já estão definidos e não podem ser alterados, mas você pode definir o nível de log.</span><span class="sxs-lookup"><span data-stu-id="87ce3-117">The important distinction is that when you use CLSController.exe at the command line there is a finite selection of scenarios available in which the providers are already defined and are not changeable, but you can define the log level.</span></span> <span data-ttu-id="87ce3-118">Usando o Windows PowerShell, você pode definir novos provedores para usar em suas sessões de log e ter controle total sobre a criação, o que elas coletam e em que nível elas coletam dados.</span><span class="sxs-lookup"><span data-stu-id="87ce3-118">By using Windows PowerShell, you can define new providers for use in your logging sessions, and have complete control over their creation, what they collect, and at what level they collect data.</span></span>

<div class="">


> [!IMPORTANT]  
> <span data-ttu-id="87ce3-p104">Como mencionado, os provedores são muito sofisticados. No entanto, os cenários são ainda mais sofisticados, pois incorporam todas as informações necessárias para definir e executar o rastreamento nos componentes que os provedores representam. Como os cenários são um conjunto de provedores, é possível fazer uma comparação livre com a execução de um arquivo de lote que contém centenas de comandos para coletar muitas informações e a emissão de centenas de comandos, um de cada vez, na linha de comando.</span><span class="sxs-lookup"><span data-stu-id="87ce3-p104">As mentioned, providers are very powerful. However, scenarios are more powerful because they contain the embodiment of all information needed to set and execute tracing on the components that the providers represent. With scenarios being a collection of providers, this could be loosely compared to running a batch file containing hundreds of commands to collect a lot of information versus issuing hundreds of commands, one at a time, at the command line.</span></span><BR><span data-ttu-id="87ce3-122">Em vez de exigir que você se aprofunde profundamente nos detalhes dos provedores, o serviço de registro em log centralizado oferece vários cenários que já estão definidos para você.</span><span class="sxs-lookup"><span data-stu-id="87ce3-122">Instead of requiring you to dig deeply into the details of providers, the Centralized Logging Service provides a number of scenarios that are already defined for you.</span></span> <span data-ttu-id="87ce3-123">Os cenários fornecidos cobrem a maioria dos possíveis problemas que você poderá encontrar.</span><span class="sxs-lookup"><span data-stu-id="87ce3-123">The provided scenarios cover the vast majority of possible issues that you will encounter.</span></span> <span data-ttu-id="87ce3-124">Raramente, você talvez precise criar e definir provedores e atribuí-los a cenários.</span><span class="sxs-lookup"><span data-stu-id="87ce3-124">In rare cases, you may need to create and define providers and assign them to scenarios.</span></span> <span data-ttu-id="87ce3-125">Recomendamos que você se familiarize com cada um dos cenários fornecidos antes de investigar a necessidade de criar novos provedores e cenários.</span><span class="sxs-lookup"><span data-stu-id="87ce3-125">We strongly recommend that you become familiar with each of the scenarios provided before you investigate the need to create new providers and scenarios.</span></span> <span data-ttu-id="87ce3-126">Embora este artigo traga informações sobre a criação de provedores para você se familiarizar com a maneira como os cenários usam os elementos de provedor para coletar informações de rastreamento, por enquanto, não serão fornecidos detalhes sobre os provedores em si.</span><span class="sxs-lookup"><span data-stu-id="87ce3-126">While information about creating providers is found here to familiarize you with how the scenarios use the provider elements to collect trace information, details on the providers themselves are not provided at this time.</span></span>



</div>

<span data-ttu-id="87ce3-127">Apresentado em [visão geral do serviço de log centralizado no Lync Server 2013](lync-server-2013-overview-of-the-centralized-logging-service.md), os principais elementos da definição de um provedor para uso em um cenário são:</span><span class="sxs-lookup"><span data-stu-id="87ce3-127">Introduced in [Overview of the Centralized Logging Service in Lync Server 2013](lync-server-2013-overview-of-the-centralized-logging-service.md), the key elements of defining a provider for use in a scenario are:</span></span>

  - <span data-ttu-id="87ce3-128">**Provedores**   se você estiver familiarizado com o OCSLogger, os provedores são os componentes que você escolhe para OCSLogger o que o mecanismo de rastreamento deve coletar logs.</span><span class="sxs-lookup"><span data-stu-id="87ce3-128">**Providers**   If you are familiar with OCSLogger, providers are the components that you choose to tell OCSLogger what the tracing engine should collect logs from.</span></span> <span data-ttu-id="87ce3-129">Os provedores são os mesmos componentes e, em muitos casos, têm o mesmo nome que os componentes do OCSLogger.</span><span class="sxs-lookup"><span data-stu-id="87ce3-129">The providers are the same components, and in many cases have the same name as the components in OCSLogger.</span></span> <span data-ttu-id="87ce3-130">Se você não estiver familiarizado com o OCSLogger, os provedores são componentes específicos de função do servidor que o serviço de log centralizado pode coletar logs.</span><span class="sxs-lookup"><span data-stu-id="87ce3-130">If you are not familiar with OCSLogger, providers are server-role specific components that the Centralized Logging Service can collect logs from.</span></span> <span data-ttu-id="87ce3-131">No caso do serviço de log centralizado, o CLSAgent é a parte da arquitetura do serviço de log centralizado que está fazendo o rastreamento dos componentes definidos na configuração de provedores.</span><span class="sxs-lookup"><span data-stu-id="87ce3-131">In the case of the Centralized Logging Service, the CLSAgent is the architectural part of the Centralized Logging Service that is doing the tracing of the components that you define in the providers configuration.</span></span>

  - <span data-ttu-id="87ce3-132">**Níveis de registro**   de OCSLogger fornece a opção de escolher um número de níveis de detalhes para os dados coletados.</span><span class="sxs-lookup"><span data-stu-id="87ce3-132">**Logging levels**   OCSLogger provided the option to choose a number of levels of detail for the data collected.</span></span> <span data-ttu-id="87ce3-133">Esse recurso é uma parte integral do serviço e cenários de registro centralizado e é definido pelo parâmetro de **tipo** .</span><span class="sxs-lookup"><span data-stu-id="87ce3-133">This feature is an integral part of the Centralized Logging Service and scenarios, and is defined by the **Type** parameter.</span></span> <span data-ttu-id="87ce3-134">As seguintes opções estão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="87ce3-134">You can choose from the following:</span></span>
    
      - <span data-ttu-id="87ce3-135">**All**   coleta mensagens de rastreamento do tipo fatal, erro, aviso e informações para o log do provedor definido.</span><span class="sxs-lookup"><span data-stu-id="87ce3-135">**All**   Collects trace messages of type fatal, error, warning, and info to the log for the defined provider.</span></span>
    
      - <span data-ttu-id="87ce3-136">**Fatal**   coleta apenas as mensagens de rastreamento que indicam uma falha para o provedor definido.</span><span class="sxs-lookup"><span data-stu-id="87ce3-136">**Fatal**   Collects only the trace messages that indicate a failure for the defined provider.</span></span>
    
      - <span data-ttu-id="87ce3-137">**Erro**   coleta apenas as mensagens de rastreamento que indicam um erro para o provedor definido, além de mensagens fatais.</span><span class="sxs-lookup"><span data-stu-id="87ce3-137">**Error**   Collects only the trace messages that indicate an error for the defined provider, plus fatal messages.</span></span>
    
      - <span data-ttu-id="87ce3-138">**Aviso**   coleta apenas as mensagens de rastreamento que indicam um aviso para o provedor definido, além de mensagens fatais e de erro.</span><span class="sxs-lookup"><span data-stu-id="87ce3-138">**Warning**   Collects only the trace messages that indicate a warning for the defined provider, plus fatal and error messages.</span></span>
    
      - <span data-ttu-id="87ce3-139">**Info**   coleta apenas as mensagens de rastreamento que indicam uma mensagem informativa para o provedor definido, além de mensagens de aviso, de erro e fatais.</span><span class="sxs-lookup"><span data-stu-id="87ce3-139">**Info**   Collects only the trace messages that indicate an informational message for the defined provider, plus fatal, error, and warning messages.</span></span>
    
      - <span data-ttu-id="87ce3-140">**Verbose**   coleta todas as mensagens de rastreamento do tipo fatal, erro, aviso e informações para o provedor definido.</span><span class="sxs-lookup"><span data-stu-id="87ce3-140">**Verbose**   Collects all trace messages of type fatal, error, warning and info for the defined provider.</span></span>

  - <span data-ttu-id="87ce3-141">**Flags**   OCSLogger ofereceu a opção de escolher sinalizadores para cada provedor que definia o tipo de informação que você pode recuperar dos arquivos de rastreamento.</span><span class="sxs-lookup"><span data-stu-id="87ce3-141">**Flags**   OCSLogger provided the option to choose flags for each provider that defined what type of information you could retrieve from the trace files.</span></span> <span data-ttu-id="87ce3-142">Você pode escolher os seguintes sinalizadores, com base no provedor:</span><span class="sxs-lookup"><span data-stu-id="87ce3-142">You can chose the following flags, based on the provider:</span></span>
    
      - <span data-ttu-id="87ce3-143">**TF\_conexão**   fornece entradas de log relacionadas a conexão.</span><span class="sxs-lookup"><span data-stu-id="87ce3-143">**TF\_Connection**   Provides connection-related log entries.</span></span> <span data-ttu-id="87ce3-144">Esses logs incluem informações sobre as conexões estabelecidas com e a partir de um componente específico.</span><span class="sxs-lookup"><span data-stu-id="87ce3-144">These logs include information about connections established to and from a particular component.</span></span> <span data-ttu-id="87ce3-145">Isso também pode incluir informações significativas no nível da rede (ou seja, para componentes sem o conceito de uma conexão).</span><span class="sxs-lookup"><span data-stu-id="87ce3-145">This may also include significant network-level information (that is, for components without the concept of a connection).</span></span>
    
      - <span data-ttu-id="87ce3-146">**O\_TF Security**   fornece todos os eventos/entradas de log relacionados à segurança.</span><span class="sxs-lookup"><span data-stu-id="87ce3-146">**TF\_Security**   Provides all events/log entries related to security.</span></span> <span data-ttu-id="87ce3-147">Por exemplo, para SipStack, são eventos de segurança como falha na validação do domínio e falhas de autenticação/autorização do cliente.</span><span class="sxs-lookup"><span data-stu-id="87ce3-147">For example, for SipStack, these are security events such as domain validation failure, and client authentication/authorization failures.</span></span>
    
      - <span data-ttu-id="87ce3-148">**O\_TF diag**   fornece eventos de diagnóstico que você pode usar para diagnosticar ou solucionar problemas do componente.</span><span class="sxs-lookup"><span data-stu-id="87ce3-148">**TF\_Diag**   Provides diagnostics events that you can use to diagnose or troubleshoot the component.</span></span> <span data-ttu-id="87ce3-149">Por exemplo, para SipStack, são falhas de certificado e avisos/erros de DNS.</span><span class="sxs-lookup"><span data-stu-id="87ce3-149">For example, for SipStack, these are certificate failures, or DNS warnings/errors.</span></span>
    
      - <span data-ttu-id="87ce3-150">**O\_protocolo**   TF fornece mensagens de protocolo como SIP e mensagens de pacote de codec de comunidade combinadas.</span><span class="sxs-lookup"><span data-stu-id="87ce3-150">**TF\_Protocol**   Provides protocol messages such as SIP and Combined Community Codec Pack messages.</span></span>
    
      - <span data-ttu-id="87ce3-151">**O\_componente**   TF habilita o registro em log dos componentes especificados como parte dos provedores.</span><span class="sxs-lookup"><span data-stu-id="87ce3-151">**TF\_Component**   Enables logging on the components specified as part of the providers.</span></span>
    
      - <span data-ttu-id="87ce3-152">**Todos**   os conjuntos de todos os sinalizadores disponíveis para o provedor.</span><span class="sxs-lookup"><span data-stu-id="87ce3-152">**All**   Sets all available flags available for the provider.</span></span>

<div>

## <a name="to-review-information-about-existing-centralized-logging-service-scenario-providers"></a><span data-ttu-id="87ce3-153">Para revisar informações sobre provedores de cenário de serviço de log centralizado existentes</span><span class="sxs-lookup"><span data-stu-id="87ce3-153">To review information about existing Centralized Logging Service scenario providers</span></span>

1.  <span data-ttu-id="87ce3-154">Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="87ce3-154">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="87ce3-155">Para exibir a configuração dos provedores existentes, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="87ce3-155">To review the configuration of existing providers, type the following:</span></span>
    
        Get-CsClsScenario -Identity <scope and scenario name> 
    
    <span data-ttu-id="87ce3-156">Por exemplo, para exibir informações sobre o participante de conferência global, digite:</span><span class="sxs-lookup"><span data-stu-id="87ce3-156">For example, to review information about the global conferencing attendant, type:</span></span>
    
        Get-CsClsScenario -Identity "global/CAA"
    
    <span data-ttu-id="87ce3-157">O comando exibe uma lista dos provedores com os sinalizadores, as configurações e os componentes associados.</span><span class="sxs-lookup"><span data-stu-id="87ce3-157">The command displays a list of providers with the associated flags, settings, and components.</span></span> <span data-ttu-id="87ce3-158">Se as informações exibidas não forem suficientes ou se a lista for muito longa para o formato de lista padrão do Windows PowerShell, você pode exibir informações adicionais definindo um método de saída diferente.</span><span class="sxs-lookup"><span data-stu-id="87ce3-158">If the information displayed is not enough or the list is too long for the default Windows PowerShell list format, you can display additional information by defining a different output method.</span></span> <span data-ttu-id="87ce3-159">Para isso, digite:</span><span class="sxs-lookup"><span data-stu-id="87ce3-159">To do this, type:</span></span>
    
        Get-CsClsScenario -Identity "global/CAA" | Select-Object -ExpandProperty Provider
    
    <span data-ttu-id="87ce3-160">A saída deste comando exibe cada provedor em um formato de cinco linhas com o nome do provedor, o tipo de log, o nível de log, os sinalizadores, o GUID e a função, cada um em uma linha separada.</span><span class="sxs-lookup"><span data-stu-id="87ce3-160">The output of this command displays each provider displayed in a five line format with the provider name, type of logging, logging level, flags, GUID, and role, each one on a separate line.</span></span>

</div>

<div>

## <a name="to-define-a-new-centralized-logging-service-scenario-provider"></a><span data-ttu-id="87ce3-161">Para definir um novo provedor de cenário de serviço de log centralizado</span><span class="sxs-lookup"><span data-stu-id="87ce3-161">To define a new Centralized Logging Service scenario provider</span></span>

1.  <span data-ttu-id="87ce3-162">Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="87ce3-162">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="87ce3-p113">Um provedor de cenário consiste em um componente a ser rastreado, sinalizadores a serem usados e um nível de detalhamento a ser coletado. Para isso, digite:</span><span class="sxs-lookup"><span data-stu-id="87ce3-p113">A scenario provider consists of a component to trace, flags to use, and a level of detail to collect. You do this by typing:</span></span>
    
        $<variableName> = New-CsClsProvider -Name <provider component> -Type <log type> -Level <log level detail type> -Flags <provider trace log flags>
    
    <span data-ttu-id="87ce3-165">Por exemplo, uma definição de provedor de rastreamento que define o que será coletado e em qual nível de detalhamento do provedor Lyss seria semelhante ao seguinte:</span><span class="sxs-lookup"><span data-stu-id="87ce3-165">For example, a trace provider definition that defines what to collect and to what level of detail from the Lyss provider looks like the following:</span></span>
    
        $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Info" -Flags "All"

<span data-ttu-id="87ce3-166">–Level coleta mensagens fatais, de erro, aviso e informações.</span><span class="sxs-lookup"><span data-stu-id="87ce3-166">The –Level collects fatal, error, warning, and information messages.</span></span> <span data-ttu-id="87ce3-167">Os sinalizadores usados são todos aqueles definidos para o provedor Lyss e incluem a conexão de\_TF, TF\_diag and TF\_Protocol.</span><span class="sxs-lookup"><span data-stu-id="87ce3-167">The flags used are all of those defined for the Lyss provider, and include TF\_Connection, TF\_Diag and TF\_Protocol.</span></span>

<span data-ttu-id="87ce3-168">Depois que a variável $LyssProvider for definida, você poderá usá-la com o cmdlet **New-CsClsScenario** para coletar rastreamentos do provedor Lyss.</span><span class="sxs-lookup"><span data-stu-id="87ce3-168">After the variable $LyssProvider is defined, you can use it with the **New-CsClsScenario** cmdlet to collect traces from the Lyss provider.</span></span> <span data-ttu-id="87ce3-169">Para concluir a criação e a atribuição do provedor a um novo cenário, digite:</span><span class="sxs-lookup"><span data-stu-id="87ce3-169">To complete the creation and assignment of the provider to a new scenario, type:</span></span>

    New-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider

<span data-ttu-id="87ce3-170">Em que $LyssProvider é a variável que contém o cenário definido criado com **New-CsClsProvider**.</span><span class="sxs-lookup"><span data-stu-id="87ce3-170">Where $LyssProvider is the variable containing the defined scenario created with **New-CsClsProvider**.</span></span>

</div>

<div>

## <a name="to-change-an-existing-centralized-logging-service-scenario-provider"></a><span data-ttu-id="87ce3-171">Para alterar um provedor de cenário de serviço de log centralizado existente</span><span class="sxs-lookup"><span data-stu-id="87ce3-171">To change an existing Centralized Logging Service scenario provider</span></span>

1.  <span data-ttu-id="87ce3-172">Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="87ce3-172">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="87ce3-173">Para atualizar ou alterar a configuração de um provedor existente, digite:</span><span class="sxs-lookup"><span data-stu-id="87ce3-173">To update or change the configuration of an existing provider, type:</span></span>
    
        $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "TF_Connection, TF_Diag"
    
    <span data-ttu-id="87ce3-174">Em seguida, você atualiza o cenário para atribuir o provedor digitando o seguinte:</span><span class="sxs-lookup"><span data-stu-id="87ce3-174">You then update the scenario to assign the provider by typing the following:</span></span>
    
        Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider

<span data-ttu-id="87ce3-p116">O resultado final do comando é que cenário site:Redmond/RedmondLyssInfo terá atualizado os sinalizadores e o nível do provedor atribuído a ele. Você pode exibir o novo cenário usando Get-CsClsScenario. Para obter detalhes, consulte [Get-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/Get-CsClsScenario).</span><span class="sxs-lookup"><span data-stu-id="87ce3-p116">The end result of the command is that the scenario site:Redmond/RedmondLyssInfo will have updated flags and level for the provider assigned to it. You can view the new scenario by using Get-CsClsScenario. For details, see [Get-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/Get-CsClsScenario).</span></span>

<div class="">


> [!WARNING]  
> <span data-ttu-id="87ce3-178"><STRONG>New-ClsCsProvider</STRONG> não faz uma verificação para determinar se os sinalizadores são válidos.</span><span class="sxs-lookup"><span data-stu-id="87ce3-178"><STRONG>New-ClsCsProvider</STRONG> does not check to determine whether the flags are valid.</span></span> <span data-ttu-id="87ce3-179">Certifique-se de que os sinalizadores (por exemplo, TF_DIAG ou TF_CONNECTION) estejam grafados corretamente.</span><span class="sxs-lookup"><span data-stu-id="87ce3-179">Make sure that the spelling of the flags (for example, TF_DIAG or TF_CONNECTION) is spelled correctly.</span></span> <span data-ttu-id="87ce3-180">Se os sinalizadores não estiverem grafados corretamente, o provedor não poderá retornar as informações de log esperadas.</span><span class="sxs-lookup"><span data-stu-id="87ce3-180">If the flags are not spelled correctly, the provider cannot return the expected log information.</span></span>



</div>

<span data-ttu-id="87ce3-181">Se você quiser adicionar mais provedores a esse cenário, digite:</span><span class="sxs-lookup"><span data-stu-id="87ce3-181">If you want to add additional providers to this scenario, type the following:</span></span>

    Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Add=$ABSProvider, $CASProvider, S4Provider}

<span data-ttu-id="87ce3-182">Onde cada provedor definido com a diretiva Add já foi definido com o uso do processo **New-CsClsProvider**.</span><span class="sxs-lookup"><span data-stu-id="87ce3-182">Where each provider defined with the Add directive has already been defined using the **New-CsClsProvider** process.</span></span>

</div>

<div>

## <a name="to-remove-a-scenario-provider"></a><span data-ttu-id="87ce3-183">Para remover um provedor de cenário</span><span class="sxs-lookup"><span data-stu-id="87ce3-183">To remove a scenario provider</span></span>

1.  <span data-ttu-id="87ce3-184">Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="87ce3-184">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="87ce3-185">Os cmdlets fornecidos permitem que você atualize os provedores existentes e crie novos provedores.</span><span class="sxs-lookup"><span data-stu-id="87ce3-185">The cmdlets provided allow you to update existing providers and create new providers.</span></span> <span data-ttu-id="87ce3-186">Para remover um provedor, você precisa usar a diretiva Replace do parâmetro Provider para **Set-CsClsScenario**.</span><span class="sxs-lookup"><span data-stu-id="87ce3-186">To remove a provider, you must use the Replace directive for the Provider parameter to **Set-CsClsScenario**.</span></span> <span data-ttu-id="87ce3-187">A única maneira de remover completamente um provedor é substituí-lo por um provedor redefinido com o mesmo nome e usar a diretiva Update.</span><span class="sxs-lookup"><span data-stu-id="87ce3-187">The only way to completely remove a provider is to replace it with a redefined provider of the same name and use the Update directive.</span></span> <span data-ttu-id="87ce3-188">Por exemplo, nosso provedor LyssProvider é definido com WPP como o tipo de log, o nível definido para depurar e os sinalizadores definidos\_são TF conexão\_e TF diag.</span><span class="sxs-lookup"><span data-stu-id="87ce3-188">For example, our provider LyssProvider is defined with WPP as the log type, level set to Debug, and flags set are TF\_CONNECTION and TF\_DIAG.</span></span> <span data-ttu-id="87ce3-189">Você precisa alterar os sinalizadores para "All".</span><span class="sxs-lookup"><span data-stu-id="87ce3-189">You need to change the flags to “All”.</span></span> <span data-ttu-id="87ce3-190">Para alterar o provedor, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="87ce3-190">To change the provider, type the following:</span></span>
    
        $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "All"

     &nbsp;
    
        Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Replace=$LyssProvider}

3.  <span data-ttu-id="87ce3-191">Se você desejar remover completamente um cenário e os provedores associados a ele, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="87ce3-191">If you want to completely remove a scenario and the providers associated with it, type the following:</span></span>
    
        Remove-CsClsScenario -Identity <scope and name of scenario>
    
    <span data-ttu-id="87ce3-192">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="87ce3-192">For example:</span></span>
    
        Remove-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo"
    
    <div class="">
    

    > [!WARNING]  
    > <span data-ttu-id="87ce3-193">O cmdlet <STRONG>Remove-CsClsScenario</STRONG> não solicita sua confirmação.</span><span class="sxs-lookup"><span data-stu-id="87ce3-193">The cmdlet <STRONG>Remove-CsClsScenario</STRONG> does not prompt you for confirmation.</span></span> <span data-ttu-id="87ce3-194">O cenário será excluído junto com os provedores atribuídos a ele.</span><span class="sxs-lookup"><span data-stu-id="87ce3-194">The scenario is deleted, along with the providers that were assigned to it.</span></span> <span data-ttu-id="87ce3-195">Você pode recriar o cenário executando novamente os comandos usados para criá-lo inicialmente.</span><span class="sxs-lookup"><span data-stu-id="87ce3-195">You can recreate the scenario by re-running the commands used to create it initially.</span></span> <span data-ttu-id="87ce3-196">Não há um procedimento para recuperar cenários ou provedores removidos.</span><span class="sxs-lookup"><span data-stu-id="87ce3-196">There is no procedure to recover removed scenarios or providers.</span></span>

    
    </div>

<span data-ttu-id="87ce3-197">Quando você remove um cenário usando o cmdlet **Remove-CsClsScenario**, ele é completamente removido do escopo.</span><span class="sxs-lookup"><span data-stu-id="87ce3-197">When you remove a scenario by using the **Remove-CsClsScenario** cmdlet, you completely remove the scenario from the scope.</span></span> <span data-ttu-id="87ce3-198">Para usar os cenários que você criou e os provedores que faziam parte dele, crie novos provedores e atribua-os a um novo cenário.</span><span class="sxs-lookup"><span data-stu-id="87ce3-198">To use the scenarios that you created and the providers that were a part of the scenario, you create new providers and assign them to a new scenario.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="87ce3-199">Confira também</span><span class="sxs-lookup"><span data-stu-id="87ce3-199">See Also</span></span>


[<span data-ttu-id="87ce3-200">Get-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="87ce3-200">Get-CsClsScenario</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsClsScenario)  
[<span data-ttu-id="87ce3-201">New-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="87ce3-201">New-CsClsScenario</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsClsScenario)  
[<span data-ttu-id="87ce3-202">Remove-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="87ce3-202">Remove-CsClsScenario</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsClsScenario)  
[<span data-ttu-id="87ce3-203">Set-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="87ce3-203">Set-CsClsScenario</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsClsScenario)  
[<span data-ttu-id="87ce3-204">New-CsClsProvider</span><span class="sxs-lookup"><span data-stu-id="87ce3-204">New-CsClsProvider</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsClsProvider)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

