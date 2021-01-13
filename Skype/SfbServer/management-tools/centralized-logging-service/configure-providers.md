---
title: Configurar provedores para o Serviço de Log Centralizado no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 6a197ecf-b56b-45e0-8e7c-f532ec5164ff
description: 'Resumo: saiba como configurar provedores de cenário para o Serviço de Log Centralizado no Skype for Business Server 2015.'
ms.openlocfilehash: c96a87ea76930dbd99341667852a9731e56b88b5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49835161"
---
# <a name="configure-providers-for-centralized-logging-service-in-skype-for-business-server-2015"></a><span data-ttu-id="2c132-103">Configurar provedores para o Serviço de Log Centralizado no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="2c132-103">Configure providers for Centralized Logging Service in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="2c132-104">**Resumo:** Saiba como configurar provedores de cenário para o Serviço de Log Centralizado no Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="2c132-104">**Summary:** Learn how to configure scenario providers for the Centralized Logging Service in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="2c132-105">Os conceitos e a configuração de provedores no Serviço de Log Centralizado é um dos mais importantes a entender.</span><span class="sxs-lookup"><span data-stu-id="2c132-105">The concepts and configuration of providers in Centralized Logging Service is one of the most important to grasp.</span></span> <span data-ttu-id="2c132-106">Osprovidadores mapeiam diretamente para os componentes de função de servidor do Skype for Business Server no modelo de rastreamento do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="2c132-106">Theproviders map directly to Skype for Business Server server role components in the Skype for Business Server tracing model.</span></span> <span data-ttu-id="2c132-107">O provedor define os componentes de um Skype for Business Server 2015 que será rastreado, o tipo de mensagens (por exemplo, fatal, erro ou aviso) a serem coletadas e os sinalizadores (por exemplo, TF_Connection ou TF_Diag).</span><span class="sxs-lookup"><span data-stu-id="2c132-107">The provider defines the components of a Skype for Business Server 2015 that will be traced, the type of messages (for example, fatal, error, or warning) to collect, and the flags (for example, TF_Connection or TF_Diag).</span></span> <span data-ttu-id="2c132-108">Provedores são os componentes rastreáveis em cada função de servidor do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="2c132-108">Providers are the traceable components in each Skype for Business Server server role.</span></span> <span data-ttu-id="2c132-109">Usando provedores, você define o nível e o tipo de rastreamento nos componentes (por exemplo, S4, SIPStack, mensagens instantâneas e presença).</span><span class="sxs-lookup"><span data-stu-id="2c132-109">By using providers, you define the level and type of tracing on components (for example, S4, SIPStack, IM and Presence).</span></span> <span data-ttu-id="2c132-110">O provedor definido é usado em um cenário para agrupar todos os provedores de um determinado conjunto lógico que tratam de um problema específico.</span><span class="sxs-lookup"><span data-stu-id="2c132-110">The defined provider is used in a scenario to group all of the providers for a given logical collection that address a specific problem condition.</span></span>
  
<span data-ttu-id="2c132-111">Para executar as funções do Serviço de Log Centralizado usando o Shell de Gerenciamento do Skype for Business Server, você deve ser membro dos grupos de segurança RBAC CsAdministrator ou CsServerAdministrator ou uma função RBAC personalizada que contenha um desses dois grupos.</span><span class="sxs-lookup"><span data-stu-id="2c132-111">To run the Centralized Logging Service functions using the Skype for Business Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="2c132-112">Para retornar uma lista de todas as funções de controle de acesso baseado em função (RBAC) às quais esse cmdlet foi atribuído (incluindo qualquer função RBAC personalizada que você mesmo tenha criado), execute o seguinte comando no Shell de Gerenciamento do Skype for Business Server ou no prompt do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="2c132-112">To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Skype for Business Server Management Shell or the Windows PowerShell prompt:</span></span>
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

<span data-ttu-id="2c132-113">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="2c132-113">For example:</span></span>
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

<span data-ttu-id="2c132-114">O restante deste tópico se concentra em como definir provedores, modificar um provedor e o que contém uma definição de provedor para otimizar sua solução de problemas.</span><span class="sxs-lookup"><span data-stu-id="2c132-114">The remainder of this topic focuses on how to define providers, modify a provider and what a provider definition contains to optimize your troubleshooting.</span></span> <span data-ttu-id="2c132-115">Há duas maneiras de emitir comandos do Serviço de Log Centralizado.</span><span class="sxs-lookup"><span data-stu-id="2c132-115">There are two ways to issue Centralized Logging Service commands.</span></span> <span data-ttu-id="2c132-116">Você pode usar o CLSController.exe que está localizado, por padrão, no diretório C:\Program Files\Common Files\Skype for Business Server 2015\CLSAgent.</span><span class="sxs-lookup"><span data-stu-id="2c132-116">You can use the CLSController.exe that is located, by default, in the directory C:\Program Files\Common Files\Skype for Business Server 2015\CLSAgent.</span></span> <span data-ttu-id="2c132-117">Ou você pode usar o Shell de Gerenciamento do Skype for Business Server para emitir comandos do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2c132-117">Or, you can use the Skype for Business Server Management Shell to issue Windows PowerShell commands.</span></span> <span data-ttu-id="2c132-118">Usando o Windows PowerShell, você pode definir novos provedores para uso em suas sessões de registro em log e ter controle total sobre sua criação, o que eles coletam e em que nível coletam dados.</span><span class="sxs-lookup"><span data-stu-id="2c132-118">By using Windows PowerShell, you can define new providers for use in your logging sessions, and have complete control over their creation, what they collect, and at what level they collect data.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="2c132-p104">Como mencionado, os provedores são muito sofisticados. No entanto, os cenários são ainda mais sofisticados, pois incorporam todas as informações necessárias para definir e executar o rastreamento nos componentes que os provedores representam. Como os cenários são um conjunto de provedores, é possível fazer uma comparação livre com a execução de um arquivo de lote que contém centenas de comandos para coletar muitas informações e a emissão de centenas de comandos, um de cada vez, na linha de comando.</span><span class="sxs-lookup"><span data-stu-id="2c132-p104">As mentioned, providers are very powerful. However, scenarios are more powerful because they contain the embodiment of all information needed to set and execute tracing on the components that the providers represent. With scenarios being a collection of providers, this could be loosely compared to running a batch file containing hundreds of commands to collect a lot of information versus issuing hundreds of commands, one at a time, at the command line.</span></span> 
  
<span data-ttu-id="2c132-122">Em vez de exigir que você se acentue nos detalhes dos provedores, o Serviço de Log Centralizado fornece vários cenários que já estão definidos para você.</span><span class="sxs-lookup"><span data-stu-id="2c132-122">Instead of requiring you to dig deeply into the details of providers, the Centralized Logging Service provides a number of scenarios that are already defined for you.</span></span> <span data-ttu-id="2c132-123">Os cenários fornecidos cobrem a maioria dos possíveis problemas que você poderá encontrar.</span><span class="sxs-lookup"><span data-stu-id="2c132-123">The provided scenarios cover the vast majority of possible issues that you will encounter.</span></span> <span data-ttu-id="2c132-124">Raramente, você talvez precise criar e definir provedores e atribuí-los a cenários.</span><span class="sxs-lookup"><span data-stu-id="2c132-124">In rare cases, you may need to create and define providers and assign them to scenarios.</span></span> <span data-ttu-id="2c132-125">Recomendamos que você se familiarize com cada um dos cenários fornecidos antes de investigar a necessidade de criar novos provedores e cenários.</span><span class="sxs-lookup"><span data-stu-id="2c132-125">We strongly recommend that you become familiar with each of the scenarios provided before you investigate the need to create new providers and scenarios.</span></span> <span data-ttu-id="2c132-126">Embora este artigo traga informações sobre a criação de provedores para você se familiarizar com a maneira como os cenários usam os elementos de provedor para coletar informações de rastreamento, por enquanto, não serão fornecidos detalhes sobre os provedores em si.</span><span class="sxs-lookup"><span data-stu-id="2c132-126">While information about creating providers is found here to familiarize you with how the scenarios use the provider elements to collect trace information, details on the providers themselves are not provided at this time.</span></span> 
  
<span data-ttu-id="2c132-127">Introduzidos no Serviço de Log Centralizado no [Skype for Business 2015,](centralized-logging-service.md)os principais elementos de definição de um provedor para uso em um cenário são:</span><span class="sxs-lookup"><span data-stu-id="2c132-127">Introduced in [Centralized Logging Service in Skype for Business 2015](centralized-logging-service.md), the key elements of defining a provider for use in a scenario are:</span></span>
  
- <span data-ttu-id="2c132-128">**Provedores** Se você estiver familiarizado com o OCSLogger, os provedores são os componentes que você escolhe para dizer ao OCSLogger do que o mecanismo de rastreamento deve coletar logs.</span><span class="sxs-lookup"><span data-stu-id="2c132-128">**Providers** If you are familiar with OCSLogger, providers are the components that you choose to tell OCSLogger what the tracing engine should collect logs from.</span></span> <span data-ttu-id="2c132-129">Os provedores são os mesmos componentes e, em muitos casos, têm o mesmo nome que os componentes do OCSLogger.</span><span class="sxs-lookup"><span data-stu-id="2c132-129">The providers are the same components, and in many cases have the same name as the components in OCSLogger.</span></span> <span data-ttu-id="2c132-130">Se você não estiver familiarizado com o OCSLogger, os provedores são componentes específicos da função de servidor dos que o Serviço de Log Centralizado pode coletar logs.</span><span class="sxs-lookup"><span data-stu-id="2c132-130">If you are not familiar with OCSLogger, providers are server-role specific components that the Centralized Logging Service can collect logs from.</span></span> <span data-ttu-id="2c132-131">No caso do Serviço de Log Centralizado, o CLSAgent é a parte arquitetônica do Serviço de Log Centralizado que está fazendo o rastreamento dos componentes definidos na configuração de provedores.</span><span class="sxs-lookup"><span data-stu-id="2c132-131">In the case of the Centralized Logging Service, the CLSAgent is the architectural part of the Centralized Logging Service that is doing the tracing of the components that you define in the providers configuration.</span></span>
    
- <span data-ttu-id="2c132-132">**Níveis de log** O OCSLogger forneceu a opção de escolher vários níveis de detalhes para os dados coletados.</span><span class="sxs-lookup"><span data-stu-id="2c132-132">**Logging levels** OCSLogger provided the option to choose a number of levels of detail for the data collected.</span></span> <span data-ttu-id="2c132-133">Esse recurso é uma parte integral do Serviço de Log Centralizado e dos cenários e é definido pelo **parâmetro Type.**</span><span class="sxs-lookup"><span data-stu-id="2c132-133">This feature is an integral part of the Centralized Logging Service and scenarios, and is defined by the **Type** parameter.</span></span> <span data-ttu-id="2c132-134">Você pode escolher entre estas opções:</span><span class="sxs-lookup"><span data-stu-id="2c132-134">You can choose from the following:</span></span>
    
  - <span data-ttu-id="2c132-135">**Todos** Coleta mensagens de rastreamento do tipo fatal, erro, aviso, informações detalhadas e depuração para o log do provedor definido.</span><span class="sxs-lookup"><span data-stu-id="2c132-135">**All** Collects trace messages of type fatal, error, warning, verbose, and debug info to the log for the defined provider.</span></span>
    
  - <span data-ttu-id="2c132-136">**Fatal** Coleta apenas as mensagens de rastreamento definidas como "Fatal".</span><span class="sxs-lookup"><span data-stu-id="2c132-136">**Fatal** Collects only the trace messages defined as "Fatal."</span></span>
    
  - <span data-ttu-id="2c132-137">**Erro** Coleta apenas as mensagens de rastreamento definidas como "Error" ou "Fatal".</span><span class="sxs-lookup"><span data-stu-id="2c132-137">**Error** Collects only the trace messages defined as "Error" or "Fatal."</span></span>
    
  - <span data-ttu-id="2c132-138">**Aviso** Coleta apenas as mensagens de rastreamento do tipo "Aviso", "Erro" e "Fatal".</span><span class="sxs-lookup"><span data-stu-id="2c132-138">**Warning** Collects only the trace messages of type "Warning," "Error" and "Fatal."</span></span>
    
  - <span data-ttu-id="2c132-139">**Informações** Coleta apenas as mensagens de rastreamento que indicam uma mensagem informacional para o provedor definido, além de mensagens fatais, de erro e de aviso.</span><span class="sxs-lookup"><span data-stu-id="2c132-139">**Info** Collects only the trace messages that indicate an informational message for the defined provider, plus fatal, error, and warning messages.</span></span>
    
  - <span data-ttu-id="2c132-140">**Detalhado** Coleta todas as mensagens de rastreamento do tipo fatal, erro, aviso e detalhado para o provedor definido.</span><span class="sxs-lookup"><span data-stu-id="2c132-140">**Verbose** Collects all trace messages of type fatal, error, warning and verbose for the defined provider.</span></span>
    
  - <span data-ttu-id="2c132-141">**Depurar** isso é essencialmente um equivalente a "Todos" – coleta rastreamentos do tipo Fatal, Error, Warning, Info, Verbose e Debug para o provedor definido.</span><span class="sxs-lookup"><span data-stu-id="2c132-141">**Debug** this is essentially an equivalent of 'All' - collects traces of type Fatal, Error, Warning, Info, Verbose and Debug for the defined provider.</span></span>
    
- <span data-ttu-id="2c132-142">**Sinalizadores** O OCSLogger forneceu a opção de escolher sinalizadores para cada provedor que definiam o tipo de informação que você poderia recuperar dos arquivos de rastreamento.</span><span class="sxs-lookup"><span data-stu-id="2c132-142">**Flags** OCSLogger provided the option to choose flags for each provider that defined what type of information you could retrieve from the trace files.</span></span> <span data-ttu-id="2c132-143">Você pode escolher os seguintes sinalizadores, com base no provedor:</span><span class="sxs-lookup"><span data-stu-id="2c132-143">You can chose the following flags, based on the provider:</span></span>
    
  - <span data-ttu-id="2c132-144">**TF_Connection** Fornece entradas de log relacionadas à conexão.</span><span class="sxs-lookup"><span data-stu-id="2c132-144">**TF_Connection** Provides connection-related log entries.</span></span> <span data-ttu-id="2c132-145">Esses logs incluem informações sobre as conexões estabelecidas com e a partir de um componente específico.</span><span class="sxs-lookup"><span data-stu-id="2c132-145">These logs include information about connections established to and from a particular component.</span></span> <span data-ttu-id="2c132-146">Isso também pode incluir informações significativas no nível da rede (ou seja, para componentes sem o conceito de uma conexão).</span><span class="sxs-lookup"><span data-stu-id="2c132-146">This may also include significant network-level information (that is, for components without the concept of a connection).</span></span>
    
  - <span data-ttu-id="2c132-147">**TF_Security** Fornece todos os eventos/entradas de log relacionados à segurança.</span><span class="sxs-lookup"><span data-stu-id="2c132-147">**TF_Security** Provides all events/log entries related to security.</span></span> <span data-ttu-id="2c132-148">Por exemplo, para SipStack, são eventos de segurança como falha na validação do domínio e falhas de autenticação/autorização do cliente.</span><span class="sxs-lookup"><span data-stu-id="2c132-148">For example, for SipStack, these are security events such as domain validation failure, and client authentication/authorization failures.</span></span>
    
  - <span data-ttu-id="2c132-149">**TF_Diag** Fornece eventos de diagnóstico que você pode usar para diagnosticar ou solucionar problemas do componente.</span><span class="sxs-lookup"><span data-stu-id="2c132-149">**TF_Diag** Provides diagnostics events that you can use to diagnose or troubleshoot the component.</span></span> <span data-ttu-id="2c132-150">Por exemplo, para SipStack, são falhas de certificado e avisos/erros de DNS.</span><span class="sxs-lookup"><span data-stu-id="2c132-150">For example, for SipStack, these are certificate failures, or DNS warnings/errors.</span></span>
    
  - <span data-ttu-id="2c132-151">**TF_Protocol** Fornece mensagens de protocolo, como mensagens SIP e Combined Community Codec Pack.</span><span class="sxs-lookup"><span data-stu-id="2c132-151">**TF_Protocol** Provides protocol messages such as SIP and Combined Community Codec Pack messages.</span></span>
    
  - <span data-ttu-id="2c132-152">**TF_Component** Permite o registro em log nos componentes especificados como parte dos provedores.</span><span class="sxs-lookup"><span data-stu-id="2c132-152">**TF_Component** Enables logging on the components specified as part of the providers.</span></span>
    
  - <span data-ttu-id="2c132-153">**Todos** Define todos os sinalizadores disponíveis para o provedor.</span><span class="sxs-lookup"><span data-stu-id="2c132-153">**All** Sets all available flags available for the provider.</span></span>
    
### <a name="to-review-information-about-existing-centralized-logging-service-scenario-providers"></a><span data-ttu-id="2c132-154">Para revisar informações sobre provedores de cenário de Serviço de Log Centralizado existentes</span><span class="sxs-lookup"><span data-stu-id="2c132-154">To review information about existing Centralized Logging Service scenario providers</span></span>

1. <span data-ttu-id="2c132-155">Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar,** em Todos os **Programas,** no **Skype for Business 2015** e, em seguida, clique no Shell de Gerenciamento do **Skype for Business Server.**</span><span class="sxs-lookup"><span data-stu-id="2c132-155">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="2c132-156">Para exibir a configuração dos provedores existentes, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="2c132-156">To review the configuration of existing providers, type the following:</span></span>
    
   ```PowerShell
   Get-CsClsScenario -Identity <scope and scenario name>
   ```

    <span data-ttu-id="2c132-157">Por exemplo, para exibir informações sobre o participante de conferência global, digite:</span><span class="sxs-lookup"><span data-stu-id="2c132-157">For example, to review information about the global conferencing attendant, type:</span></span>
    
   ```PowerShell
   Get-CsClsScenario -Identity "global/CAA"
   ```

    <span data-ttu-id="2c132-158">O comando exibe uma lista dos provedores com os sinalizadores, as configurações e os componentes associados.</span><span class="sxs-lookup"><span data-stu-id="2c132-158">The command displays a list of providers with the associated flags, settings, and components.</span></span> <span data-ttu-id="2c132-159">Se as informações exibidas não são suficientes ou a lista é muito longa para o formato de lista padrão do Windows PowerShell, você pode exibir informações adicionais definindo um método de saída diferente.</span><span class="sxs-lookup"><span data-stu-id="2c132-159">If the information displayed is not enough or the list is too long for the default Windows PowerShell list format, you can display additional information by defining a different output method.</span></span> <span data-ttu-id="2c132-160">Para isso, digite:</span><span class="sxs-lookup"><span data-stu-id="2c132-160">To do this, type:</span></span>
    
   ```PowerShell
   Get-CsClsScenario -Identity "global/CAA" | Select-Object -ExpandProperty Provider
   ```

    <span data-ttu-id="2c132-161">A saída deste comando exibe cada provedor em um formato de cinco linhas com o nome do provedor, o tipo de log, o nível de log, os sinalizadores, o GUID e a função, cada um em uma linha separada.</span><span class="sxs-lookup"><span data-stu-id="2c132-161">The output of this command displays each provider displayed in a five line format with the provider name, type of logging, logging level, flags, GUID, and role, each one on a separate line.</span></span> 
    
### <a name="to-define-a-new-centralized-logging-service-scenario-provider"></a><span data-ttu-id="2c132-162">Para definir um novo provedor de cenário do Serviço de Log Centralizado</span><span class="sxs-lookup"><span data-stu-id="2c132-162">To define a new Centralized Logging Service scenario provider</span></span>

1. <span data-ttu-id="2c132-163">Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar,** em Todos os **Programas,** no **Skype for Business 2015** e, em seguida, clique no Shell de Gerenciamento do **Skype for Business Server.**</span><span class="sxs-lookup"><span data-stu-id="2c132-163">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="2c132-p113">Um provedor de cenário consiste em um componente a ser rastreado, sinalizadores a serem usados e um nível de detalhamento a ser coletado. Para isso, digite:</span><span class="sxs-lookup"><span data-stu-id="2c132-p113">A scenario provider consists of a component to trace, flags to use, and a level of detail to collect. You do this by typing:</span></span>
    
   ```PowerShell
   $<variableName> = New-CsClsProvider -Name <provider component> -Type <log type> -Level <log level detail type> -Flags <provider trace log flags>
   ```

    <span data-ttu-id="2c132-166">Por exemplo, uma definição de provedor de rastreamento que define o que será coletado e em qual nível de detalhamento do provedor Lyss seria semelhante ao seguinte:</span><span class="sxs-lookup"><span data-stu-id="2c132-166">For example, a trace provider definition that defines what to collect and to what level of detail from the Lyss provider looks like the following:</span></span>
    
   ```PowerShell
   $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Info" -Flags "All"
   ```

<span data-ttu-id="2c132-167">O -Level coleta mensagens fatais, de erro, de aviso e de informações.</span><span class="sxs-lookup"><span data-stu-id="2c132-167">The -Level collects fatal, error, warning, and information messages.</span></span> <span data-ttu-id="2c132-168">Os sinalizadores usados são todos aqueles definidos para o provedor Lyss e incluem TF_Connection, TF_Diag e TF_Protocol.Depois que a variável $LyssProvider for definida, você poderá usá-la com o cmdlet **New-CsClsScenario** para coletar rastreamentos do provedor Lyss.</span><span class="sxs-lookup"><span data-stu-id="2c132-168">The flags used are all of those defined for the Lyss provider, and include TF_Connection, TF_Diag and TF_Protocol.After the variable $LyssProvider is defined, you can use it with the **New-CsClsScenario** cmdlet to collect traces from the Lyss provider.</span></span> <span data-ttu-id="2c132-169">Para concluir a criação e a atribuição do provedor a um novo cenário, digite:</span><span class="sxs-lookup"><span data-stu-id="2c132-169">To complete the creation and assignment of the provider to a new scenario, type:</span></span>

```PowerShell
New-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider
```

<span data-ttu-id="2c132-170">Em que $LyssProvider é a variável que contém o cenário definido criado com **New-CsClsProvider**.</span><span class="sxs-lookup"><span data-stu-id="2c132-170">Where $LyssProvider is the variable containing the defined scenario created with **New-CsClsProvider**.</span></span>
### <a name="to-change-an-existing-centralized-logging-service-scenario-provider"></a><span data-ttu-id="2c132-171">Para alterar um provedor de cenário de Serviço de Log Centralizado existente</span><span class="sxs-lookup"><span data-stu-id="2c132-171">To change an existing Centralized Logging Service scenario provider</span></span>

1. <span data-ttu-id="2c132-172">Inicie o Shell de Gerenciamento do Skype for Business Server: Clique em **Iniciar,** Em Todos os **Programas,** no **Skype for Business 2015** e, em seguida, clique no Shell de Gerenciamento do **Skype for Business Server.**</span><span class="sxs-lookup"><span data-stu-id="2c132-172">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="2c132-173">Para atualizar ou alterar a configuração de um provedor existente, digite:</span><span class="sxs-lookup"><span data-stu-id="2c132-173">To update or change the configuration of an existing provider, type:</span></span>
    
   ```PowerShell
   $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "TF_Connection, TF_Diag"
   ```

    <span data-ttu-id="2c132-174">Em seguida, você atualiza o cenário para atribuir o provedor digitando o seguinte:</span><span class="sxs-lookup"><span data-stu-id="2c132-174">You then update the scenario to assign the provider by typing the following:</span></span>
    
   ```PowerShell
   Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider
   ```

<span data-ttu-id="2c132-175">O resultado final do comando é que cenário site:Redmond/RedmondLyssInfo terá atualizado os sinalizadores e o nível do provedor atribuído a ele.</span><span class="sxs-lookup"><span data-stu-id="2c132-175">The end result of the command is that the scenario site:Redmond/RedmondLyssInfo will have updated flags and level for the provider assigned to it.</span></span> <span data-ttu-id="2c132-176">Você pode exibir o novo cenário usando Get-CsClsScenario.</span><span class="sxs-lookup"><span data-stu-id="2c132-176">You can view the new scenario by using Get-CsClsScenario.</span></span> <span data-ttu-id="2c132-177">Para obter detalhes, consulte [Get-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/get-csclsscenario?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="2c132-177">For details, see [Get-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/get-csclsscenario?view=skype-ps).</span></span>
> [!CAUTION]
> <span data-ttu-id="2c132-178">**New-ClsCsProvider** não faz uma verificação para determinar se os sinalizadores são válidos.</span><span class="sxs-lookup"><span data-stu-id="2c132-178">**New-ClsCsProvider** does not check to determine whether the flags are valid.</span></span> <span data-ttu-id="2c132-179">Certifique-se de que os sinalizadores (por exemplo, TF_DIAG ou TF_CONNECTION) estejam grafados corretamente.</span><span class="sxs-lookup"><span data-stu-id="2c132-179">Make sure that the spelling of the flags (for example, TF_DIAG or TF_CONNECTION) is spelled correctly.</span></span> <span data-ttu-id="2c132-180">Se os sinalizadores não estiverem grafados corretamente, o provedor não poderá retornar as informações de log esperadas.</span><span class="sxs-lookup"><span data-stu-id="2c132-180">If the flags are not spelled correctly, the provider cannot return the expected log information.</span></span>
  
<span data-ttu-id="2c132-181">Se você desejar adicionar mais provedores a esse cenário, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="2c132-181">If you want to add additional providers to this scenario, type the following:</span></span>

```PowerShell
Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Add=$ABSProvider, $CASProvider, S4Provider}
```

<span data-ttu-id="2c132-182">Em que cada provedor definido com a diretiva Add já foi definido com o uso do processo **New-CsClsProvider**.</span><span class="sxs-lookup"><span data-stu-id="2c132-182">Where each provider defined with the Add directive has already been defined using the **New-CsClsProvider** process.</span></span>
### <a name="to-remove-a-scenario-provider"></a><span data-ttu-id="2c132-183">Para remover um provedor de cenário</span><span class="sxs-lookup"><span data-stu-id="2c132-183">To remove a scenario provider</span></span>

1. <span data-ttu-id="2c132-184">Inicie o Shell de Gerenciamento do Skype for Business Server: Clique em **Iniciar,** Em Todos os **Programas,** no **Skype for Business 2015** e, em seguida, clique no Shell de Gerenciamento do **Skype for Business Server.**</span><span class="sxs-lookup"><span data-stu-id="2c132-184">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="2c132-185">Os cmdlets fornecidos permitem que você atualize os provedores existentes e crie novos provedores.</span><span class="sxs-lookup"><span data-stu-id="2c132-185">The cmdlets provided allow you to update existing providers and create new providers.</span></span> <span data-ttu-id="2c132-186">Para remover um provedor, você precisa usar a diretiva Replace do parâmetro Provider para **Set-CsClsScenario**.</span><span class="sxs-lookup"><span data-stu-id="2c132-186">To remove a provider, you must use the Replace directive for the Provider parameter to **Set-CsClsScenario**.</span></span> <span data-ttu-id="2c132-187">A única maneira de remover completamente um provedor é substituí-lo por um provedor redefinido com o mesmo nome e usar a diretiva Update.</span><span class="sxs-lookup"><span data-stu-id="2c132-187">The only way to completely remove a provider is to replace it with a redefined provider of the same name and use the Update directive.</span></span> <span data-ttu-id="2c132-188">Por exemplo, nosso provedor LyssProvider está definido com o tipo de log WPP, o nível definido para Debug e os sinalizadores definidos como TF_CONNECTION e TF_DIAG.</span><span class="sxs-lookup"><span data-stu-id="2c132-188">For example, our provider LyssProvider is defined with WPP as the log type, level set to Debug, and flags set are TF_CONNECTION and TF_DIAG.</span></span> <span data-ttu-id="2c132-189">Você precisa alterar os sinalizadores para "Tudo".</span><span class="sxs-lookup"><span data-stu-id="2c132-189">You need to change the flags to "All".</span></span> <span data-ttu-id="2c132-190">Para alterar o provedor, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="2c132-190">To change the provider, type the following:</span></span>
    
   ```PowerShell
   $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "All"
   ```

   ```PowerShell
   Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Replace=$LyssProvider}
   ```

3. <span data-ttu-id="2c132-191">Se você desejar remover completamente um cenário e os provedores associados a ele, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="2c132-191">If you want to completely remove a scenario and the providers associated with it, type the following:</span></span>
    
   ```PowerShell
   Remove-CsClsScenario -Identity <scope and name of scenario>
   ```

    <span data-ttu-id="2c132-192">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="2c132-192">For example:</span></span>
    
   ```PowerShell
   Remove-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo"
   ```

    > [!CAUTION]
    > <span data-ttu-id="2c132-193">O cmdlet **Remove-CsClsScenario** não solicita sua confirmação.</span><span class="sxs-lookup"><span data-stu-id="2c132-193">The cmdlet **Remove-CsClsScenario** does not prompt you for confirmation.</span></span> <span data-ttu-id="2c132-194">O cenário será excluído junto com os provedores atribuídos a ele.</span><span class="sxs-lookup"><span data-stu-id="2c132-194">The scenario is deleted, along with the providers that were assigned to it.</span></span> <span data-ttu-id="2c132-195">Você pode recriar o cenário executando novamente os comandos usados para criá-lo inicialmente.</span><span class="sxs-lookup"><span data-stu-id="2c132-195">You can recreate the scenario by re-running the commands used to create it initially.</span></span> <span data-ttu-id="2c132-196">Não há um procedimento para recuperar cenários ou provedores removidos.</span><span class="sxs-lookup"><span data-stu-id="2c132-196">There is no procedure to recover removed scenarios or providers.</span></span>
  
<span data-ttu-id="2c132-197">Quando você remove um cenário usando o cmdlet **Remove-CsClsScenario**, ele é completamente removido do escopo.</span><span class="sxs-lookup"><span data-stu-id="2c132-197">When you remove a scenario by using the **Remove-CsClsScenario** cmdlet, you completely remove the scenario from the scope.</span></span> <span data-ttu-id="2c132-198">Para usar os cenários que você criou e os provedores que faziam parte dele, crie novos provedores e atribua-os a um novo cenário.</span><span class="sxs-lookup"><span data-stu-id="2c132-198">To use the scenarios that you created and the providers that were a part of the scenario, you create new providers and assign them to a new scenario.</span></span>
## <a name="see-also"></a><span data-ttu-id="2c132-199">Confira também</span><span class="sxs-lookup"><span data-stu-id="2c132-199">See also</span></span>

[<span data-ttu-id="2c132-200">Get-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="2c132-200">Get-CsClsScenario</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csclsscenario?view=skype-ps)
  
[<span data-ttu-id="2c132-201">New-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="2c132-201">New-CsClsScenario</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csclsscenario?view=skype-ps)
  
[<span data-ttu-id="2c132-202">Remove-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="2c132-202">Remove-CsClsScenario</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csclsscenario?view=skype-ps)
  
[<span data-ttu-id="2c132-203">Set-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="2c132-203">Set-CsClsScenario</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csclsscenario?view=skype-ps)
  
[<span data-ttu-id="2c132-204">New-CsClsProvider</span><span class="sxs-lookup"><span data-stu-id="2c132-204">New-CsClsProvider</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csclsprovider?view=skype-ps)
