---
title: Configurar cenários para o Serviço de Log Centralizado no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 6c3bf826-e7fd-4002-95dc-01020641ef01
description: 'Resumo: Saiba como criar, modificar e remover cenários para o Serviço de Log Centralizado no Skype for Business Server 2015.'
ms.openlocfilehash: 8778530826cdbd0c3ecc5128385644f2191a858e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49835181"
---
# <a name="configure-scenarios-for-the-centralized-logging-service-in-skype-for-business-server-2015"></a><span data-ttu-id="8efb2-103">Configurar cenários para o Serviço de Log Centralizado no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="8efb2-103">Configure scenarios for the Centralized Logging Service in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="8efb2-104">**Resumo:** Saiba como criar, modificar e remover cenários para o Serviço de Log Centralizado no Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="8efb2-104">**Summary:** Learn how to create, modify, and remove scenarios for the Centralized Logging Service in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="8efb2-105">Os cenários definem o escopo (ou seja, global, site, pool ou computador) e quais provedores usar no Serviço de Log Centralizado.</span><span class="sxs-lookup"><span data-stu-id="8efb2-105">Scenarios define the scope (that is, global, site, pool, or computer) and what providers to use in the Centralized Logging Service.</span></span> <span data-ttu-id="8efb2-106">Usando cenários, você habilita e desabilita o rastreamento nos provedores (por exemplo, S4, SIPStack, mensagens instantâneas e presença).</span><span class="sxs-lookup"><span data-stu-id="8efb2-106">By using scenarios, you enable or disable tracing on providers (for example, S4, SIPStack, IM, and Presence).</span></span> <span data-ttu-id="8efb2-107">Ao configurar um cenário, você pode agrupar todos os provedores de determinado conjunto lógico que tratam um problema específico.</span><span class="sxs-lookup"><span data-stu-id="8efb2-107">By configuring a scenario, you can group all of the providers for a given logical collection that address a specific problem condition.</span></span> <span data-ttu-id="8efb2-108">Se você achar que um cenário precisa ser modificado para atender às suas necessidades de solução de problemas e registro em log, as Ferramentas de Depuração do Skype for Business Server 2015 fornece um módulo do Windows PowerShell chamado ClsScenarioEdit.psm1 que contém uma função chamadaEdit-CsClsScenario.</span><span class="sxs-lookup"><span data-stu-id="8efb2-108">If you find that a scenario needs to be modified to meet your troubleshooting and logging needs, the Skype for Business Server 2015 Debug Tools provides you a Windows PowerShell module named ClsScenarioEdit.psm1 that contains a function namedEdit-CsClsScenario.</span></span> <span data-ttu-id="8efb2-109">A finalidade desse módulo é editar as propriedades do cenário nomeado.</span><span class="sxs-lookup"><span data-stu-id="8efb2-109">The purpose of the module is to edit the properties of the named scenario.</span></span> <span data-ttu-id="8efb2-110">Neste tópico, serão fornecidos exemplos de como esse módulo funciona.</span><span class="sxs-lookup"><span data-stu-id="8efb2-110">Examples of how this module works are provided in this topic.</span></span> <span data-ttu-id="8efb2-111">Baixe as Ferramentas de [Depuração](https://go.microsoft.com/fwlink/p/?LinkId=285257) do Skype for Business Server 2015 antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="8efb2-111">Download the Skype for Business Server 2015 [Debugging Tools](https://go.microsoft.com/fwlink/p/?LinkId=285257) before going any further.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="8efb2-112">Para qualquer dado escopo (global, site, pool ou computador), é possível executar no máximo dois cenários por vez.</span><span class="sxs-lookup"><span data-stu-id="8efb2-112">For any given scope—site, global, pool or computer—you can run a maximum of two scenarios at any given time.</span></span> <span data-ttu-id="8efb2-113">Para determinar quais cenários estão sendo executados no momento, use o Windows PowerShell e [o Get-CsClsScenario.](https://docs.microsoft.com/powershell/module/skype/get-csclsscenario?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="8efb2-113">To determine which scenarios are currently running, use Windows PowerShell and [Get-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/get-csclsscenario?view=skype-ps).</span></span> <span data-ttu-id="8efb2-114">Usando o Windows PowerShell e [o Set-CsClsScenario,](https://docs.microsoft.com/powershell/module/skype/set-csclsscenario?view=skype-ps)você pode alterar dinamicamente quais cenários estão sendo executados.</span><span class="sxs-lookup"><span data-stu-id="8efb2-114">By using Windows PowerShell and [Set-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/set-csclsscenario?view=skype-ps), you can dynamically change which scenarios are running.</span></span> <span data-ttu-id="8efb2-115">Você pode modificar quais cenários estão em execução durante uma sessão de registro em log para ajustar ou refinar os dados coletados e de quais provedores.</span><span class="sxs-lookup"><span data-stu-id="8efb2-115">You can modify which scenarios are running during a logging session to adjust or refine the data you are collecting and from which providers.</span></span> 
  
<span data-ttu-id="8efb2-116">Para executar as funções do Serviço de Log Centralizado usando o Shell de Gerenciamento do Skype for Business Server, você deve ser membro dos grupos de segurança RBAC CsAdministrator ou CsServerAdministrator ou uma função RBAC personalizada que contenha um desses dois grupos.</span><span class="sxs-lookup"><span data-stu-id="8efb2-116">To run the Centralized Logging Service functions by using the Skype for Business Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="8efb2-117">Para retornar uma lista de todas as funções do RBAC às quais este cmdlet foi atribuído, incluindo qualquer função RBAC personalizada que você mesmo tenha criado, execute o seguinte comando no Shell de Gerenciamento do Skype for Business Server ou no prompt do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="8efb2-117">To return a list of all the RBAC roles this cmdlet has been assigned to, including any custom RBAC roles you have created yourself, run the following command from the Skype for Business Server Management Shell or the Windows PowerShell prompt:</span></span>
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

<span data-ttu-id="8efb2-118">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="8efb2-118">For example:</span></span>
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

<span data-ttu-id="8efb2-119">O restante deste tópico se concentra em como definir um cenário, modificar um cenário, recuperar quais cenários estão sendo executados, remover um cenário e especificar o que contém um cenário para otimizar sua solução de problemas.</span><span class="sxs-lookup"><span data-stu-id="8efb2-119">The remainder of this topic focuses on how to define a scenario, modify a scenario, retrieve what scenarios are running, remove a scenario, and specify what a scenario contains to optimize your troubleshooting.</span></span> <span data-ttu-id="8efb2-120">Você pode usar o Shell de Gerenciamento do Skype for Business Server para emitir comandos do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8efb2-120">You can use the Skype for Business Server Management Shell to issue Windows PowerShell commands.</span></span> <span data-ttu-id="8efb2-121">Ao usar o Windows PowerShell, você pode definir novos cenários para uso em suas sessões de registro em log.</span><span class="sxs-lookup"><span data-stu-id="8efb2-121">When you use Windows PowerShell, you can define new scenarios for use in your logging sessions.</span></span>
  
<span data-ttu-id="8efb2-122">Conforme introduzido no [Serviço de Log Centralizado no Skype for Business 2015,](centralized-logging-service.md)os elementos de um cenário são:</span><span class="sxs-lookup"><span data-stu-id="8efb2-122">As introduced in [Centralized Logging Service in Skype for Business 2015](centralized-logging-service.md), the elements of a scenario are:</span></span>
  
- <span data-ttu-id="8efb2-123">**Provedores** Se você estiver familiarizado com o OCSLogger, os provedores são os componentes que você escolhe para dizer ao OCSLogger do que o mecanismo de rastreamento deve coletar logs.</span><span class="sxs-lookup"><span data-stu-id="8efb2-123">**Providers** If you are familiar with OCSLogger, providers are the components that you choose to tell OCSLogger what the tracing engine should collect logs from.</span></span> <span data-ttu-id="8efb2-124">Os provedores são os mesmos componentes e, em muitos casos, têm o mesmo nome que os componentes do OCSLogger.</span><span class="sxs-lookup"><span data-stu-id="8efb2-124">The providers are the same components, and in many cases have the same name as the components in OCSLogger.</span></span> <span data-ttu-id="8efb2-125">Se você não estiver familiarizado com o OCSLogger, os provedores são componentes específicos da função de servidor dos que o Serviço de Log Centralizado pode coletar logs.</span><span class="sxs-lookup"><span data-stu-id="8efb2-125">If you are not familiar with OCSLogger, providers are server role specific components that the Centralized Logging Service can collect logs from.</span></span> <span data-ttu-id="8efb2-126">Para obter detalhes sobre a configuração de provedores, consulte [Configure providers for Centralized Logging Service in Skype for Business Server 2015.](configure-providers.md)</span><span class="sxs-lookup"><span data-stu-id="8efb2-126">For details about the configuration of providers, see [Configure providers for Centralized Logging Service in Skype for Business Server 2015](configure-providers.md).</span></span>
    
- <span data-ttu-id="8efb2-127">**Identidade** O parâmetro -Identity define o escopo e o nome do cenário.</span><span class="sxs-lookup"><span data-stu-id="8efb2-127">**Identity** The parameter -Identity sets the scope and name of the scenario.</span></span> <span data-ttu-id="8efb2-128">Por exemplo, você pode definir um escopo "global" e identificar o cenário com "LyssServiceScenario".</span><span class="sxs-lookup"><span data-stu-id="8efb2-128">For example, you could set a scope of "global" and identify the scenario with "LyssServiceScenario".</span></span> <span data-ttu-id="8efb2-129">Ao combinar os dois, você define a Identidade (por exemplo, "global/LyssServiceScenario").</span><span class="sxs-lookup"><span data-stu-id="8efb2-129">When you combine the two, you define the Identity (for example, "global/LyssServiceScenario").</span></span>
    
    <span data-ttu-id="8efb2-130">Opcionalmente, você pode usar os parâmetros -Name e -Parent.</span><span class="sxs-lookup"><span data-stu-id="8efb2-130">Optionally, you can use the -Name and -Parent parameters.</span></span> <span data-ttu-id="8efb2-131">Você define o parâmetro Name para identificar exclusivamente o cenário.</span><span class="sxs-lookup"><span data-stu-id="8efb2-131">You define the Name parameter to uniquely identify the scenario.</span></span> <span data-ttu-id="8efb2-132">Se usá-lo, também deverá usar Parent para adicionar o cenário ao escopo global ou site.</span><span class="sxs-lookup"><span data-stu-id="8efb2-132">If you use Name, you must also use Parent to add the scenario to either global or site.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="8efb2-133">Se você usar os parâmetros Name e Parent, não poderá usar o **parâmetro -Identity.**</span><span class="sxs-lookup"><span data-stu-id="8efb2-133">If you use the Name and Parent parameters, you cannot use the **-Identity** parameter.</span></span>
  
### <a name="to-create-a-new-scenario-with-the-new-csclsscenario-cmdlet"></a><span data-ttu-id="8efb2-134">Para criar um novo cenário com o cmdlet New-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="8efb2-134">To create a new scenario with the New-CsClsScenario cmdlet</span></span>

1. <span data-ttu-id="8efb2-135">Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar,** em Todos os **Programas,** no **Skype for Business 2015** e, em seguida, clique no Shell de Gerenciamento do **Skype for Business Server.**</span><span class="sxs-lookup"><span data-stu-id="8efb2-135">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="8efb2-136">Para criar um novo cenário para uma sessão de registro em log, use [New-CsClsProvider](https://docs.microsoft.com/powershell/module/skype/new-csclsprovider?view=skype-ps) e defina o nome do cenário (ou seja, como ele será identificado exclusivamente).</span><span class="sxs-lookup"><span data-stu-id="8efb2-136">To create a new scenario for a logging session, use [New-CsClsProvider](https://docs.microsoft.com/powershell/module/skype/new-csclsprovider?view=skype-ps) and define the name of the scenario (that is, how it will be uniquely identified).</span></span> <span data-ttu-id="8efb2-137">Escolha um tipo de formato de registro em log entre WPP (ou seja, o pré-processador de rastreamento de software do Windows, que é o padrão), EventLog (ou seja, o formato de log de eventos do Windows) ou IISLog (ou seja, o arquivo de formato ASCII baseado no formato de arquivo de log do IIS).</span><span class="sxs-lookup"><span data-stu-id="8efb2-137">Choose a type of logging format from WPP (that is, Windows software tracing preprocessor and is the default), EventLog (that is, Windows event log format), or IISLog (that is, ASCII format file based on the IIS log file format).</span></span> <span data-ttu-id="8efb2-138">Em seguida, defina o nível (conforme definido em Níveis de registro em log neste tópico) e os sinalizadores (conforme definido em Sinalizadores neste tópico).</span><span class="sxs-lookup"><span data-stu-id="8efb2-138">Next, define Level (as the defined under Logging Levels in this topic), and Flags (as defined under Flags in this topic).</span></span>
    
    <span data-ttu-id="8efb2-139">Para este cenário de exemplo, usaremos LyssProvider como a variável de provedor de exemplo.</span><span class="sxs-lookup"><span data-stu-id="8efb2-139">For this example scenario, we use LyssProvider as the example provider variable.</span></span>
    
    <span data-ttu-id="8efb2-140">Para criar um cenário usando as opções definidas, digite:</span><span class="sxs-lookup"><span data-stu-id="8efb2-140">To create a scenario using the options defined, type:</span></span>
    
   ```PowerShell
   New-CsClsScenario -Identity <scope>/<unique scenario name> -Provider <provider variable>
   ```

    <span data-ttu-id="8efb2-141">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="8efb2-141">For example:</span></span>
    
   ```PowerShell
   New-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider $LyssProvider
   ```

    <span data-ttu-id="8efb2-142">O formato alternativo usando -Name e -Parent:</span><span class="sxs-lookup"><span data-stu-id="8efb2-142">The alternate format using -Name and -Parent:</span></span>
    
   ```PowerShell
   New-CsClsScenario -Name "LyssServiceScenario" -Parent "site:Redmond" -Provider $LyssProvider
   ```

### <a name="to-create-a-new-scenario-with-multiple-providers-with-the-new-csclsscenario-cmdlet"></a><span data-ttu-id="8efb2-143">Para criar um novo cenário com vários provedores usando o cmdlet New-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="8efb2-143">To create a new scenario with multiple providers with the New-CsClsScenario cmdlet</span></span>

1. <span data-ttu-id="8efb2-144">Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar,** em Todos os **Programas,** no **Skype for Business 2015** e, em seguida, clique no Shell de Gerenciamento do **Skype for Business Server.**</span><span class="sxs-lookup"><span data-stu-id="8efb2-144">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="8efb2-145">Há um limite de dois cenários por escopo.</span><span class="sxs-lookup"><span data-stu-id="8efb2-145">You are limited to two scenarios per scope.</span></span> <span data-ttu-id="8efb2-146">No entanto, não há um limite quanto ao número de provedores.</span><span class="sxs-lookup"><span data-stu-id="8efb2-146">However, you are not limited to a set number of providers.</span></span> <span data-ttu-id="8efb2-147">Neste exemplo, suponha que criamos três provedores e você deseja atribuir todos eles ao cenário que está definindo.</span><span class="sxs-lookup"><span data-stu-id="8efb2-147">In this example, assume that we have created three providers, and you want to assign all three to the scenario you are defining.</span></span> <span data-ttu-id="8efb2-148">Os nomes das variáveis dos provedores são LyssProvider, ABServerProvider e SIPStackProvider.</span><span class="sxs-lookup"><span data-stu-id="8efb2-148">The provider variable names are LyssProvider, ABServerProvider, and SIPStackProvider.</span></span> <span data-ttu-id="8efb2-149">Para definir e atribuir vários provedores a um cenário, digite o seguinte em um prompt de comando do Shell de Gerenciamento do Skype for Business Server ou do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="8efb2-149">To define and assign multiple providers to a scenario, type the following at a Skype for Business Server Management Shell or Windows PowerShell command prompt:</span></span>
    
   ```PowerShell
   New-CsClsScenario -Identity "site:Redmond/CollectDataScenario" -Provider @{Add=$LyssProvider, $ABServerProvider,  $SIPStackProvider}
   ```

    > [!NOTE]
    > <span data-ttu-id="8efb2-150">Como é conhecido no Windows PowerShell, a convenção para criar uma tabela de hash de valores usando é conhecida  `@{<variable>=<value1>, <value2>, <value>…}` como plataforma.</span><span class="sxs-lookup"><span data-stu-id="8efb2-150">As it is known in Windows PowerShell, the convention for creating a hash table of values using  `@{<variable>=<value1>, <value2>, <value>…}` is known assplatting.</span></span> <span data-ttu-id="8efb2-151">Para obter detalhes sobre o splatting no Windows PowerShell, consulte [https://go.microsoft.com/fwlink/p/?LinkId=267760](https://go.microsoft.com/fwlink/p/?LinkId=267760) .</span><span class="sxs-lookup"><span data-stu-id="8efb2-151">For details about splatting in Windows PowerShell, see [https://go.microsoft.com/fwlink/p/?LinkId=267760](https://go.microsoft.com/fwlink/p/?LinkId=267760).</span></span> 
  
### <a name="to-modify-an-existing-scenario-with-the-set-csclsscenario-cmdlet"></a><span data-ttu-id="8efb2-152">Para modificar um cenário existente com o cmdlet Set-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="8efb2-152">To modify an existing scenario with the Set-CsClsScenario cmdlet</span></span>

1. <span data-ttu-id="8efb2-153">Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar,** em Todos os **Programas,** no **Skype for Business 2015** e, em seguida, clique no Shell de Gerenciamento do **Skype for Business Server.**</span><span class="sxs-lookup"><span data-stu-id="8efb2-153">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="8efb2-154">Há um limite de dois cenários por escopo.</span><span class="sxs-lookup"><span data-stu-id="8efb2-154">You are limited to two scenarios per scope.</span></span> <span data-ttu-id="8efb2-155">Você pode alterar quais cenários estão em execução a qualquer momento, mesmo quando uma sessão de coleta de log está em andamento.</span><span class="sxs-lookup"><span data-stu-id="8efb2-155">You can change which scenarios are running at any time, even when a logging capture session is in process.</span></span> <span data-ttu-id="8efb2-156">Se você redefinir os cenários em execução, a sessão de registro em log atual parará de usar o cenário que foi removido e começará a usar o novo cenário.</span><span class="sxs-lookup"><span data-stu-id="8efb2-156">If you redefine the running scenarios, the current logging session will stop using the scenario that was removed and then begin using the new scenario.</span></span> <span data-ttu-id="8efb2-157">No entanto, as informações de log que já foram coletadas com o cenário removido permanecerão nos logs coletados.</span><span class="sxs-lookup"><span data-stu-id="8efb2-157">However, the logging information that was captured with the removed scenario remains in the captured logs.</span></span> <span data-ttu-id="8efb2-158">Para definir um novo cenário, faça o seguinte (ou seja, supondo a adição de um provedor já definido chamado "S4Provider"):</span><span class="sxs-lookup"><span data-stu-id="8efb2-158">To define a new scenario, do the following (that is, assuming the addition of an already defined provider named "S4Provider"):</span></span>
    
   ```PowerShell
   Set-CsClsScenario -Identity <name of scope and scenario defined by New-CsClsScenario> -Provider @{Add=<new provider to add>}
   ```

    <span data-ttu-id="8efb2-159">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="8efb2-159">For example:</span></span>
    
   ```PowerShell
   Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Add=$S4Provider}
   ```

    <span data-ttu-id="8efb2-p112">Se você desejar substituir provedores, defina um único provedor ou uma lista separada por vírgulas de provedores para substituir o conjunto atual. Se você desejar substituir apenas um de vários provedores, adicione os provedores atuais junto com os novos provedores para criar um novo conjunto de provedores que contenha os provedores novos e existentes. Para substituir todos os provedores por um novo conjunto, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="8efb2-p112">If you want to replace providers, define a single provider or a comma separated list of providers to replace the current set. If you only want to replace one of many providers, add the current providers with the new providers to create a new set of providers that contains both new providers and existing providers. To replace all providers with a new set, type the following:</span></span>
    
   ```PowerShell
   Set-CsClsScenario -Identity <name of scope and scenario defined by New-CsClsScenario> -Provider @{Replace=<providers to replace existing provider set>}
   ```

    <span data-ttu-id="8efb2-163">Por exemplo, para substituir o conjunto atual de $LyssProvider, $ABServerProvider e $SIPStackProvider por $LyssServiceProvider:</span><span class="sxs-lookup"><span data-stu-id="8efb2-163">For example, to replace the current set of $LyssProvider, $ABServerProvider, and $SIPStackProvider with $LyssServiceProvider:</span></span>
    
   ```PowerShell
   Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Replace=$LyssServiceProvider}
   ```

    <span data-ttu-id="8efb2-164">Para substituir apenas o provedor $LyssProvider do conjunto atual de $LyssProvider, $ABServerProvider e $SIPStackProvider por $LyssServiceProvider, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="8efb2-164">To replace just the $LyssProvider provider from the current set of $LyssProvider, $ABServerProvider, and $SIPStackProvider with $LyssServiceProvider, type the following:</span></span>
    
   ```PowerShell
   Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Replace=$LyssServiceProvider, $ABServerProvider, $SIPStackProvider}
   ```

### <a name="to-remove-an-existing-scenario-with-the-remove-csclsscenario-cmdlet"></a><span data-ttu-id="8efb2-165">Para remover um cenário existente com o cmdlet Remove-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="8efb2-165">To remove an existing scenario with the Remove-CsClsScenario cmdlet</span></span>

1. <span data-ttu-id="8efb2-166">Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar,** em Todos os **Programas,** no **Skype for Business 2015** e, em seguida, clique no Shell de Gerenciamento do **Skype for Business Server.**</span><span class="sxs-lookup"><span data-stu-id="8efb2-166">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="8efb2-167">Se você desejar remover um cenário que foi definido anteriormente, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="8efb2-167">If you want to remove a scenario that has been previously defined, type the following:</span></span>
    
   ```PowerShell
   Remove-CsClsScenario -Identity <name of scope and scenario>
   ```

    <span data-ttu-id="8efb2-168">Por exemplo, para remover o cenário definido site:Redmond/LyssServiceScenario:</span><span class="sxs-lookup"><span data-stu-id="8efb2-168">For example, to remove the defined scenario site:Redmond/LyssServiceScenario:</span></span>
    
   ```PowerShell
   Remove-CsClsScenario -Identity "site:Redmond/LyssServiceScenario"
   ```

<span data-ttu-id="8efb2-169">O cmdlet **Remove-CsClsScenario** remove o cenário especificado, mas os rastreamentos que foram coletados ainda estarão disponíveis nos logs para pesquisa.</span><span class="sxs-lookup"><span data-stu-id="8efb2-169">The **Remove-CsClsScenario** cmdlet removes the specified scenario, but the traces that have been captured are still available in the logs for you to search on.</span></span>
### <a name="to-load-and-unload-the-edit-csclsscenario-cmdlet-using-the-clsscenarioeditpsm1-module"></a><span data-ttu-id="8efb2-170">Para carregar e descarregar o Edit-CsClsScenario cmdlet usando o módulo ClsScenarioEdit.psm1</span><span class="sxs-lookup"><span data-stu-id="8efb2-170">To load and unload the Edit-CsClsScenario cmdlet using the ClsScenarioEdit.psm1 module</span></span>

1. <span data-ttu-id="8efb2-171">Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar,** em Todos os **Programas,** no **Skype for Business 2015** e, em seguida, clique no Shell de Gerenciamento do **Skype for Business Server.**</span><span class="sxs-lookup"><span data-stu-id="8efb2-171">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="8efb2-172">O módulo ClsScenarioEdit.psm1 é fornecido como um download da Web separado.</span><span class="sxs-lookup"><span data-stu-id="8efb2-172">The ClsScenarioEdit.psm1 module is provided as a separate Web download.</span></span> <span data-ttu-id="8efb2-173">O módulo faz parte das ferramentas de depuração do Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="8efb2-173">The module is part of the Skype for Business Server 2015 Debugging tools.</span></span> <span data-ttu-id="8efb2-174">Por padrão, as ferramentas de depuração são instaladas no diretório C:\Arquivos de Programas\Skype for Business Server 2015\Ferramentas de Depuração.</span><span class="sxs-lookup"><span data-stu-id="8efb2-174">By default, the debugging tools are installed in the directory C:\Program Files\Skype for Business Server 2015\Debugging Tools.</span></span> 
  
2. <span data-ttu-id="8efb2-175">No Windows PowerShell, digite:</span><span class="sxs-lookup"><span data-stu-id="8efb2-175">From the Windows PowerShell, type:</span></span>
    
   ```PowerShell
   Import-Module "CDBurn\OCO\amd64\Support"
   ```

    > [!TIP]
    > <span data-ttu-id="8efb2-176">O carregamento bem-sucedido do módulo o retornará ao prompt de comando do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8efb2-176">Successful loading of the module returns you to the Windows PowerShell command prompt.</span></span> <span data-ttu-id="8efb2-177">Para confirmar se o módulo está carregado e se Edit-CsClsScenario está disponível, digite  `Get-Help Edit-CsClsScenario` .</span><span class="sxs-lookup"><span data-stu-id="8efb2-177">To confirm that the module is loaded and that Edit-CsClsScenario is available, type  `Get-Help Edit-CsClsScenario`.</span></span> <span data-ttu-id="8efb2-178">Você deverá ver a sinopse básica da sintaxe de EditCsClsScenario.</span><span class="sxs-lookup"><span data-stu-id="8efb2-178">You should see the basic synopsis of the syntax for EditCsClsScenario.</span></span> 
  
3. <span data-ttu-id="8efb2-179">Para descarregar os módulos, digite:</span><span class="sxs-lookup"><span data-stu-id="8efb2-179">To unload the modules, type:</span></span>
    
   ```PowerShell
   Remove-Module ClsController
   ```

    > [!TIP]
    > <span data-ttu-id="8efb2-180">O descarregamento bem-sucedido do módulo retorna você para o prompt de comando do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8efb2-180">Successful unloading of the module returns you to the Windows PowerShell command prompt.</span></span> <span data-ttu-id="8efb2-181">Para confirmar que o módulo foi descarregado, digite  `Get-Help Edit-CsClsScenario` .</span><span class="sxs-lookup"><span data-stu-id="8efb2-181">To confirm that the module is unloaded, type  `Get-Help Edit-CsClsScenario`.</span></span> <span data-ttu-id="8efb2-182">O Windows PowerShell tentará localizar a ajuda do cmdlet e falhará.</span><span class="sxs-lookup"><span data-stu-id="8efb2-182">Windows PowerShell will attempt to locate the help for the cmdlet and fail.</span></span> 
  
### <a name="to-remove-an-existing-provider-from-a-scenario-with-the-edit-clscontroller-module"></a><span data-ttu-id="8efb2-183">Para remover um provedor existente de um cenário com o módulo Edit-ClsController</span><span class="sxs-lookup"><span data-stu-id="8efb2-183">To remove an existing provider from a scenario with the Edit-ClsController module</span></span>

1. <span data-ttu-id="8efb2-184">Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar,** em Todos os **Programas,** no **Skype for Business 2015** e, em seguida, clique no Shell de Gerenciamento do **Skype for Business Server.**</span><span class="sxs-lookup"><span data-stu-id="8efb2-184">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="8efb2-185">No Windows PowerShell, digite:</span><span class="sxs-lookup"><span data-stu-id="8efb2-185">From the Windows PowerShell, type:</span></span>
    
   ```PowerShell
   Import-Module "CDBurn\OCO\amd64\Support"
   ```

    > [!TIP]
    > <span data-ttu-id="8efb2-186">O carregamento bem-sucedido do módulo o retornará ao prompt de comando do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8efb2-186">Successful loading of the module returns you to the Windows PowerShell command prompt.</span></span> <span data-ttu-id="8efb2-187">Para confirmar se o módulo está carregado e se Edit-CsClsScenario está disponível, digite  `Get-Help Edit-CsClsScenario` .</span><span class="sxs-lookup"><span data-stu-id="8efb2-187">To confirm that the module is loaded and that Edit-CsClsScenario is available, type  `Get-Help Edit-CsClsScenario`.</span></span> <span data-ttu-id="8efb2-188">Você deverá ver a sinopse básica da sintaxe de EditCsClsScenario.</span><span class="sxs-lookup"><span data-stu-id="8efb2-188">You should see the basic synopsis of the syntax for EditCsClsScenario.</span></span> 
  
3. <span data-ttu-id="8efb2-189">Para remover um provedor do cenário AlwaysOn, digite:</span><span class="sxs-lookup"><span data-stu-id="8efb2-189">To remove a provider from the AlwaysOn scenario, type:</span></span>
    
   ```PowerShell
   Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to remove> -Remove
   ```

   <span data-ttu-id="8efb2-190">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="8efb2-190">For Example:</span></span>
    
   ```PowerShell
   Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Remove
   ```

   <span data-ttu-id="8efb2-p117">Os parâmetros ScenarioName e ProviderName são posicionais (ou seja, devem ser definidos na posição esperada na linha de comando). O nome do parâmetro não precisa ser explicitamente definido se o nome do cenário estiver na segunda ou na terceira posição em relação ao nome do cmdlet na primeira posição. Usando essas informações, o comando anterior seria digitado como:</span><span class="sxs-lookup"><span data-stu-id="8efb2-p117">The parameters ScenarioName and ProviderName are positional (that is, they must be defined in the expected position in the command line) parameters. The parameter name does not have to be explicitly defined if the scenario name is in position two and the provider is in position three, relative to the name of the cmdlet as position one. Using this information, the previous command would be typed as:</span></span>
    
   ```PowerShell
   Edit-CsClsScenario AlwaysOn ChatServer -Remove
   ```

   <span data-ttu-id="8efb2-194">A colocação posicional dos valores de parâmetro se aplica somente a -Scenario e -Provider.</span><span class="sxs-lookup"><span data-stu-id="8efb2-194">The positional placing of the parameter values applies only to -Scenario and -Provider.</span></span> <span data-ttu-id="8efb2-195">Todos os outros parâmetros devem ser definidos explicitamente.</span><span class="sxs-lookup"><span data-stu-id="8efb2-195">All other parameters must be explicitly defined.</span></span>
    
### <a name="to-add-a-provider-to-a-scenario-with-the-edit-clscontroller-module"></a><span data-ttu-id="8efb2-196">Para adicionar um provedor a um cenário com o cmdlet Edit-ClsController</span><span class="sxs-lookup"><span data-stu-id="8efb2-196">To add a provider to a scenario with the Edit-ClsController module</span></span>

1. <span data-ttu-id="8efb2-197">Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar,** em Todos os **Programas,** no **Skype for Business 2015** e, em seguida, clique no Shell de Gerenciamento do **Skype for Business Server.**</span><span class="sxs-lookup"><span data-stu-id="8efb2-197">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="8efb2-198">Para adicionar um provedor ao cenário AlwaysOn, digite:</span><span class="sxs-lookup"><span data-stu-id="8efb2-198">To add a provider to the AlwaysOn scenario, type:</span></span>
    
   ```PowerShell
   Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to add> -Level <string of type level> -Flags <string of type flags>
   ```

    <span data-ttu-id="8efb2-199">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="8efb2-199">For Example:</span></span>
    
   ```PowerShell
   Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Level Info -Flags TF_COMPONENT
   ```

    <span data-ttu-id="8efb2-200">-Loglevel pode ser do tipo Fatal, Error, Warning, Info, Verbose, Debug ou All.</span><span class="sxs-lookup"><span data-stu-id="8efb2-200">-Loglevel can be of the type Fatal, Error, Warning, Info, Verbose, Debug, or All.</span></span> <span data-ttu-id="8efb2-201">-Flags pode ser qualquer um dos sinalizadores que o provedor suporta, como TF_COMPONENT, TF_DIAG.</span><span class="sxs-lookup"><span data-stu-id="8efb2-201">-Flags can be any of the flags that the provider supports, such as TF_COMPONENT, TF_DIAG.</span></span> <span data-ttu-id="8efb2-202">-Flags também pode ser do valor ALL</span><span class="sxs-lookup"><span data-stu-id="8efb2-202">-Flags can also be of value ALL</span></span>
    
   <span data-ttu-id="8efb2-p120">O exemplo anterior também pode ser digitado com o uso do recurso posicional do cmdlet. Por exemplo, para adicionar o provedor ChatServer ao cenário AlwaysOn, digite:</span><span class="sxs-lookup"><span data-stu-id="8efb2-p120">The previous example can also be typed using the positional feature of the cmdlet. For example, to add the provider ChatServer to the AlwaysOn scenario, type:</span></span>
    
   ```PowerShell
   Edit-CsClsScenario AlwaysOn ChatServer -Level Info -Flags ALL
   ```
