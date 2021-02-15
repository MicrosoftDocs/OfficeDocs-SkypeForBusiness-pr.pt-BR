---
title: Gerenciar definições de configuração do Serviço de Log Centralizado no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 8/17/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 93b9a354-9aea-4b3a-a4fe-68a89f436196
description: 'Resumo: Saiba como recuperar, atualizar e criar definições de configuração para o Serviço de Log Centralizado no Skype for Business Server 2015.'
ms.openlocfilehash: dd292465d65116dc1f497a733ca8e010e57b9137
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49835151"
---
# <a name="manage-centralized-logging-service-configuration-settings-in-skype-for-business-server-2015"></a><span data-ttu-id="6f0b3-103">Gerenciar definições de configuração do Serviço de Log Centralizado no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="6f0b3-103">Manage Centralized Logging Service configuration settings in Skype for Business Server 2015</span></span>

<span data-ttu-id="6f0b3-104">**Resumo:** Saiba como recuperar, atualizar e criar definições de configuração para o Serviço de Log Centralizado no Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="6f0b3-104">**Summary:** Learn how to retrieve, update, and create configuration settings for the Centralized Logging Service in Skype for Business Server 2015.</span></span>

<span data-ttu-id="6f0b3-105">O Serviço de Registro em Log Centralizado é controlado e configurado por configurações e parâmetros criados e usados pelo Controlador de Serviço de Log Centralizado (CLSController) para enviar comandos ao Agente de Serviço de Log Centralizado (CLSAgent) do computador individual.</span><span class="sxs-lookup"><span data-stu-id="6f0b3-105">The Centralized Logging Service is controlled and configured by settings and parameters that are created and used by the Centralized Logging Service Controller (CLSController) to send commands to the individual computer's Centralized Logging Service Agent (CLSAgent).</span></span> <span data-ttu-id="6f0b3-106">O agente processa os comandos que são enviados a ele e (no caso de um comando Iniciar) usa a configuração dos cenários, provedores, duração de rastreamento e sinalizadores para começar a coletar logs de rastreamento de acordo com as informações de configuração fornecidas.</span><span class="sxs-lookup"><span data-stu-id="6f0b3-106">The agent processes the commands that are sent to it and (in the case of a Start command) uses the configuration of the scenarios, providers, trace duration, and flags to begin collecting trace logs according to the configuration information provided.</span></span>

> [!IMPORTANT]
>  <span data-ttu-id="6f0b3-107">Nem todos os cmdlets do Windows PowerShell listados para o Serviço de Log Centralizado se destinam ao uso com implantações locais do Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="6f0b3-107">Not all Windows PowerShell cmdlets listed for the Centralized Logging Service are intended for use with Skype for Business Server 2015 on-premises deployments.</span></span> <span data-ttu-id="6f0b3-108">Embora possam parecer funcionar, os seguintes cmdlets não foram projetados para funcionar com implantações locais do Skype for Business Server 2015:</span><span class="sxs-lookup"><span data-stu-id="6f0b3-108">Although they may appear to work, the following cmdlets are not designed to function with Skype for Business Server 2015 on-premises deployments:</span></span>

-  <span data-ttu-id="6f0b3-109">**Cmdlets CsClsRegion:** [Get-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/get-csclsregion?view=skype-ps) ,[Set-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/set-csclsregion?view=skype-ps), [New-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/new-csclsregion?view=skype-ps)e [Remove-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/remove-csclsregion?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="6f0b3-109">**CsClsRegion cmdlets:** [Get-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/get-csclsregion?view=skype-ps) ,[Set-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/set-csclsregion?view=skype-ps), [New-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/new-csclsregion?view=skype-ps), and [Remove-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/remove-csclsregion?view=skype-ps).</span></span>
-  <span data-ttu-id="6f0b3-110">**Cmdlets CsClsSearchTerm:** [Get-CsClsSearchTerm](https://docs.microsoft.com/powershell/module/skype/get-csclssearchterm?view=skype-ps) e [Set-CsClsSearchTerm](https://docs.microsoft.com/powershell/module/skype/set-csclssearchterm?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="6f0b3-110">**CsClsSearchTerm cmdlets:** [Get-CsClsSearchTerm](https://docs.microsoft.com/powershell/module/skype/get-csclssearchterm?view=skype-ps) and [Set-CsClsSearchTerm](https://docs.microsoft.com/powershell/module/skype/set-csclssearchterm?view=skype-ps).</span></span>
-  <span data-ttu-id="6f0b3-111">**Cmdlets CsClsSecurityGroup:** [Get-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/get-csclssecuritygroup?view=skype-ps), [Set-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/set-csclssecuritygroup?view=skype-ps),  [New-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/new-csclssecuritygroup?view=skype-ps)e [Remove-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/remove-csclssecuritygroup?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="6f0b3-111">**CsClsSecurityGroup cmdlets:** [Get-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/get-csclssecuritygroup?view=skype-ps), [Set-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/set-csclssecuritygroup?view=skype-ps),  [New-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/new-csclssecuritygroup?view=skype-ps), and [Remove-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/remove-csclssecuritygroup?view=skype-ps).</span></span>

<span data-ttu-id="6f0b3-112">As configurações definidas nesses cmdlets não impedirão ou causarão nenhum comportamento adverso, mas elas foram projetadas para uso com o Microsoft 365 ou o Office 365 e não gerarão os resultados esperados em implantações locais.</span><span class="sxs-lookup"><span data-stu-id="6f0b3-112">The settings defined in these cmdlets will not hinder or cause any adverse behavior, but they are designed for use with Microsoft 365 or Office 365 and will not yield the expected results in on-premises deployments.</span></span> <span data-ttu-id="6f0b3-113">Isso não quer dizer que não há uso para esses cmdlets em implantações locais, mas sua utilização é um tópico mais avançado que não é abordado nesta documentação.</span><span class="sxs-lookup"><span data-stu-id="6f0b3-113">This is not to say that there is no use for these cmdlets in on-premises deployments, but their use is a more advanced topic that is not covered in this documentation.</span></span>

<span data-ttu-id="6f0b3-114">O Serviço de Log Centralizado pode ser executado em um escopo que inclui um único computador ou pool de computadores, em escopo de site (ou seja, um site definido, como o site Redmond que contém uma coleção de computadores e pools em sua implantação) ou em um escopo global (ou seja, todos os computadores e pools em sua implantação).</span><span class="sxs-lookup"><span data-stu-id="6f0b3-114">The Centralized Logging Service can be run at a scope that includes a single computer or a pool of computers, at a site scope (that is, a defined site such as the site Redmond that contains a collection of computer and pools in your deployment), or at a global scope (that is, all computers and pools in your deployment).</span></span>

<span data-ttu-id="6f0b3-115">Para configurar o escopo do Serviço de Log Centralizado usando o Shell de Gerenciamento do Skype for Business Server, você deve ser membro dos grupos de segurança RBAC CsAdministrator ou CsServerAdministrator ou uma função RBAC personalizada que contenha um desses dois grupos.</span><span class="sxs-lookup"><span data-stu-id="6f0b3-115">To configure the Centralized Logging Service scope by using the Skype for Business Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="6f0b3-116">Para retornar uma lista de todas as funções do RBAC às quais este cmdlet foi atribuído (incluindo qualquer função RBAC personalizada que você mesmo tenha criado), execute o seguinte comando no Shell de Gerenciamento do Skype for Business Server ou no prompt do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="6f0b3-116">To return a list of all the RBAC roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Skype for Business Server Management Shell or the Windows PowerShell prompt:</span></span>

```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "<Skype for Business cmdlet>"}
```

<span data-ttu-id="6f0b3-117">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="6f0b3-117">For example:</span></span>

```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

> [!NOTE]
> <span data-ttu-id="6f0b3-118">Há diferenças fundamentais entre os comandos de linha de comando que você pode executar no Windows PowerShell ou CLSController.</span><span class="sxs-lookup"><span data-stu-id="6f0b3-118">There are fundamental differences between the command-line commands that you can run in Windows PowerShell or CLSController.</span></span> <span data-ttu-id="6f0b3-119">O Windows PowerShell fornece um método rico para configurar e definir cenários e reutilizar esses cenários de maneira significativa para seus cenários de solução de problemas.</span><span class="sxs-lookup"><span data-stu-id="6f0b3-119">Windows PowerShell provides a rich method to configure and define scenarios, and to reuse those scenarios in a meaningful way for your troubleshooting scenarios.</span></span> <span data-ttu-id="6f0b3-120">Embora o CLSController does forneça uma maneira rápida e eficiente para emitir comandos e obter resultados, o conjunto de comandos do CLSController está limitado aos comandos finitos que você tem disponível na linha de comando.</span><span class="sxs-lookup"><span data-stu-id="6f0b3-120">While CLSController does provide a fast and efficient way to issue commands and get results, the command set for CLSController is limited by the finite commands that you have available from the command line.</span></span> <span data-ttu-id="6f0b3-121">Ao contrário dos cmdlets do Windows PowerShell, o CLSController não pode definir novos cenários, gerenciar o escopo em um nível de site ou global e muitas outras limitações de um conjunto de comandos finito que não pode ser configurado dinamicamente.</span><span class="sxs-lookup"><span data-stu-id="6f0b3-121">Unlike the Windows PowerShell cmdlets, CLSController cannot define new scenarios, manage scope at a site or global level, and many other limitations of a finite command set that cannot be dynamically configured.</span></span> <span data-ttu-id="6f0b3-122">Embora o CLSController fornece um meio para execução rápida, o Windows PowerShell fornece um meio para estender a funcionalidade do Serviço de Log Centralizado além do que é possível com o CLSController.</span><span class="sxs-lookup"><span data-stu-id="6f0b3-122">While CLSController provides a means for fast execution, Windows PowerShell provides a means to extend the Centralized Logging Service functionality beyond what is possible with CLSController.</span></span>

<span data-ttu-id="6f0b3-123">Um escopo de computador único pode ser definido durante a execução de um [comando Search-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/search-csclslogging?view=skype-ps), [Show-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/show-csclslogging?view=skype-ps), [Start-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/start-csclslogging?view=skype-ps), [Stop-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/stop-csclslogging?view=skype-ps), [Sync-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/sync-csclslogging?view=skype-ps) e [Update-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/update-csclslogging?view=skype-ps) usando o parâmetro -Computers.</span><span class="sxs-lookup"><span data-stu-id="6f0b3-123">A single computer scope can be defined during the execution of a [Search-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/search-csclslogging?view=skype-ps), [Show-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/show-csclslogging?view=skype-ps), [Start-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/start-csclslogging?view=skype-ps), [Stop-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/stop-csclslogging?view=skype-ps), [Sync-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/sync-csclslogging?view=skype-ps) and [Update-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/update-csclslogging?view=skype-ps) command using the -Computers parameter.</span></span> <span data-ttu-id="6f0b3-124">O parâmetro -Computers aceita uma lista separada por vírgulas de FQDNs (nomes de domínio totalmente qualificados) para o computador de destino.</span><span class="sxs-lookup"><span data-stu-id="6f0b3-124">The -Computers parameter accepts a comma separated list of fully qualified domain names (FQDNs) for the target computer.</span></span>

> [!TIP]
> <span data-ttu-id="6f0b3-125">Também é possível definir -Pools e uma lista separada por vírgulas de pools nos quais você deseja executar os comandos de log.</span><span class="sxs-lookup"><span data-stu-id="6f0b3-125">You can also define -Pools and a comma separated list of pools that you want to run the logging commands on.</span></span>

<span data-ttu-id="6f0b3-126">Os escopos de Site e Global são definidos nos cmdlets **New-**, **Set-** e **Remove-** Centralized Logging Service.</span><span class="sxs-lookup"><span data-stu-id="6f0b3-126">Site and Global scopes are defined in the **New-**, **Set-**, and **Remove-** Centralized Logging Service cmdlets.</span></span> <span data-ttu-id="6f0b3-127">Os exemplos a seguir demonstram como definir o escopo de um site ou global.</span><span class="sxs-lookup"><span data-stu-id="6f0b3-127">The following examples demonstrate how to set a site and a global scope.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6f0b3-128">Os comandos mostrados podem conter parâmetros e conceitos que são abordados em outras seções.</span><span class="sxs-lookup"><span data-stu-id="6f0b3-128">The commands shown may contain parameters and concepts that are covered in other sections.</span></span> <span data-ttu-id="6f0b3-129">Os comandos de exemplo destinam-se a demonstrar o uso do parâmetro **-Identity** para definir o escopo, e os outros parâmetros são incluídos para a abrangência completa e para especificar o escopo.</span><span class="sxs-lookup"><span data-stu-id="6f0b3-129">The example commands are intended to demonstrate the use of the **-Identity** parameter to define scope, and the other parameters are included for completeness and to specify the scope.</span></span> <span data-ttu-id="6f0b3-130">Para obter detalhes sobre os cmdlets do **Set-CsClsConfiguration**, consulte [Set-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps) na documentação Operações.</span><span class="sxs-lookup"><span data-stu-id="6f0b3-130">For details about the **Set-CsClsConfiguration** cmdlets, see [Set-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps) in the Operations documentation.</span></span>

### <a name="to-retrieve-the-current-centralized-logging-service-configuration"></a><span data-ttu-id="6f0b3-131">Para recuperar a configuração atual do Serviço de Log Centralizado</span><span class="sxs-lookup"><span data-stu-id="6f0b3-131">To retrieve the current Centralized Logging Service configuration</span></span>

1. <span data-ttu-id="6f0b3-132">Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar,** em Todos os **Programas,** no **Skype for Business 2015** e, em seguida, clique no Shell de Gerenciamento do **Skype for Business Server.**</span><span class="sxs-lookup"><span data-stu-id="6f0b3-132">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="6f0b3-133">Digite o seguinte no prompt de linha de comando:</span><span class="sxs-lookup"><span data-stu-id="6f0b3-133">Type the following at the command-line prompt:</span></span>

   ```PowerShell
   Get-CsClsConfiguration
   ```

<span data-ttu-id="6f0b3-134">Use os cmdlets **New-CsClsConfiguration** e **Set-CsClsConfiguration** para criar uma nova configuração ou atualizar uma configuração existente. Quando você executar **Get-CsClsConfiguration,** ele exibirá informações semelhantes à captura de tela a seguir, em que a implantação tem a configuração global padrão, mas nenhuma configuração de site definida:</span><span class="sxs-lookup"><span data-stu-id="6f0b3-134">Use the **New-CsClsConfiguration** and **Set-CsClsConfiguration** cmdlets to create a new configuration or to update an existing configuration.When you run **Get-CsClsConfiguration**, it displays information similar to the following screen shot, where the deployment currently has the default Global configuration, but no site configurations defined:</span></span>

![Exemplo de saída de Get-CsClsConfiguration.](../../media/Ops_Get-CsClsConfiguration_Basic.jpg)

### <a name="to-retrieve-the-current-centralized-logging-service-configuration-from-the-computer-local-store"></a><span data-ttu-id="6f0b3-136">Para recuperar a configuração atual do Serviço de Log Centralizado do armazenamento local do computador</span><span class="sxs-lookup"><span data-stu-id="6f0b3-136">To retrieve the current Centralized Logging Service configuration from the computer local store</span></span>

1. <span data-ttu-id="6f0b3-137">Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar,** em Todos os **Programas,** no **Skype for Business 2015** e, em seguida, clique no Shell de Gerenciamento do **Skype for Business Server.**</span><span class="sxs-lookup"><span data-stu-id="6f0b3-137">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="6f0b3-138">Digite o seguinte no prompt de linha de comando:</span><span class="sxs-lookup"><span data-stu-id="6f0b3-138">Type the following at the command-line prompt:</span></span>

   ```PowerShell
   Get-CsClsConfiguration -LocalStore
   ```

<span data-ttu-id="6f0b3-139">Quando você usa o primeiro exemplo em que **Get-CsClsConfiguration** não especifica nenhum parâmetro, o comando faz referência ao armazenamento de Gerenciamento Central para os dados.</span><span class="sxs-lookup"><span data-stu-id="6f0b3-139">When you use the first example where **Get-CsClsConfiguration** does not specify any parameters, the command references the Central Management store for the data.</span></span> <span data-ttu-id="6f0b3-140">Se você especificar o parâmetro -LocalStore, o comando referencia o LocalStore do computador em vez do repositório de Gerenciamento Central.</span><span class="sxs-lookup"><span data-stu-id="6f0b3-140">If you specify the parameter -LocalStore, the command references the computer LocalStore instead of the Central Management store.</span></span>
### <a name="to-retrieve-a-listing-of-scenarios-currently-defined"></a><span data-ttu-id="6f0b3-141">Para recuperar uma lista de cenários definidos no momento</span><span class="sxs-lookup"><span data-stu-id="6f0b3-141">To retrieve a listing of scenarios currently defined</span></span>

1. <span data-ttu-id="6f0b3-142">Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar,** em Todos os **Programas,** no **Skype for Business 2015** e, em seguida, clique no Shell de Gerenciamento do **Skype for Business Server.**</span><span class="sxs-lookup"><span data-stu-id="6f0b3-142">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="6f0b3-143">Digite o seguinte no prompt de linha de comando:</span><span class="sxs-lookup"><span data-stu-id="6f0b3-143">Type the following at the command-line prompt:</span></span>

   ```PowerShell
   Get-CsClsConfiguration -Identity <scope and name> | Select-Object -ExpandProperty Scenarios
   ```

    <span data-ttu-id="6f0b3-144">Por exemplo, para recuperar os cenários definidos no escopo global:</span><span class="sxs-lookup"><span data-stu-id="6f0b3-144">For example, to retrieve the scenarios that is defined at the global scope:</span></span>

   ```PowerShell
   Get-CsClsConfiguration -Identity "global" | Select-Object -ExpandProperty Scenarios
   ```

<span data-ttu-id="6f0b3-145">O cmdlet **Get-CsClsConfiguration** sempre exibe os cenários que fazem parte da configuração de um determinado escopo.</span><span class="sxs-lookup"><span data-stu-id="6f0b3-145">The cmdlet **Get-CsClsConfiguration** always displays the scenarios that are a part of a given scope's configuration.</span></span> <span data-ttu-id="6f0b3-146">Na maioria dos casos, nem todos os cenários são exibidos e estão truncados.</span><span class="sxs-lookup"><span data-stu-id="6f0b3-146">In most cases, all scenarios are not displayed, and are truncated.</span></span> <span data-ttu-id="6f0b3-147">O comando usado aqui lista todos os cenários e as informações parciais sobre quais provedores, configurações e sinalizadores são usados.</span><span class="sxs-lookup"><span data-stu-id="6f0b3-147">The command used here lists all of the scenarios and partial information about what providers, settings, and flags are used.</span></span>
### <a name="to-update-a-global-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a><span data-ttu-id="6f0b3-148">Para atualizar um escopo global para o Serviço de Log Centralizado usando o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="6f0b3-148">To update a global scope for the Centralized Logging Service by using Windows PowerShell</span></span>

1. <span data-ttu-id="6f0b3-149">Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar,** em Todos os **Programas,** no **Skype for Business 2015** e, em seguida, clique no Shell de Gerenciamento do **Skype for Business Server.**</span><span class="sxs-lookup"><span data-stu-id="6f0b3-149">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="6f0b3-150">Digite o seguinte no prompt de linha de comando:</span><span class="sxs-lookup"><span data-stu-id="6f0b3-150">Type the following at the command-line prompt:</span></span>

   ```PowerShell
   Set-CsClsConfiguration -Identity <scope> -EtlFileRolloverSizeMB <size for logging file in megabytes>
   ```

   <span data-ttu-id="6f0b3-151">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="6f0b3-151">For example:</span></span>

   ```PowerShell
   Set-CsClsConfiguration -Identity "global" -EtlFileRolloverSizeMB 40
   ```

<span data-ttu-id="6f0b3-p111">O comando diz ao CLSAgent em cada computador e pool na implantação para definir o tamanho do valor de sobreposição no arquivo de rastreamento para 40 megabytes. Os computadores e pools em todos os sites são afetados pelo comando, e definirão seu valor configurado de sobreposição de log de rastreamento para 40 megabytes.</span><span class="sxs-lookup"><span data-stu-id="6f0b3-p111">The command tells the CLSAgent on each computer and pool in the deployment to set the size of the rollover value on the tracing file to 40 megabytes. Computers and pools in all sites are affected by the command, and will set their configured trace log rollover value to 40 megabytes.</span></span>
### <a name="to-update-a-site-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a><span data-ttu-id="6f0b3-154">Para atualizar um escopo de site para o Serviço de Log Centralizado usando o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="6f0b3-154">To update a site scope for the Centralized Logging Service by using Windows PowerShell</span></span>

1. <span data-ttu-id="6f0b3-155">Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar,** em Todos os **Programas,** no **Skype for Business 2015** e, em seguida, clique no Shell de Gerenciamento do **Skype for Business Server.**</span><span class="sxs-lookup"><span data-stu-id="6f0b3-155">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="6f0b3-156">Digite o seguinte no prompt de linha de comando:</span><span class="sxs-lookup"><span data-stu-id="6f0b3-156">Type the following at the command-line prompt:</span></span>

   ```PowerShell
   Set-CsClsConfiguration -Identity <scope/site name> -EtlFileRolloverSizeMB <size for logging file in megabytes>
   ```

   <span data-ttu-id="6f0b3-157">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="6f0b3-157">For example:</span></span>

   ```PowerShell
   Set-CsClsConfiguration -Identity "site/Redmond" -EtlFileRolloverSizeMB 40
   ```

> [!NOTE]
> <span data-ttu-id="6f0b3-p112">Como observado no exemplo, o local padrão dos arquivos de log é %TEMP%\Tracing. No entanto, como é o CLSAgent que está gravando o arquivo, e o CSLAgent é executado no Serviço de Rede, a variável %TEMP% expande para %WINDIR%\ServiceProfiles\NetworkService\AppData\Local.</span><span class="sxs-lookup"><span data-stu-id="6f0b3-p112">As noted in the example, the default location of the log files is %TEMP%\Tracing. However, because it is actually CLSAgent that is writing the file and CSLAgent runs as Network Service, the %TEMP% variable expands to %WINDIR%\ServiceProfiles\NetworkService\AppData\Local.</span></span>

<span data-ttu-id="6f0b3-p113">O comando diz ao CLSAgent em cada computador e pool no site da Redmond para definir o tamanho do valor de sobreposição no arquivo de rastreamento para 40 megabytes. Os computadores e pools em outros sites não serão afetados pelo comando, e continuarão a usar o valor atualmente configurado de sobreposição de log de rastreamento definido pelo padrão (20 megabytes) ou durante o início da sessão de log.</span><span class="sxs-lookup"><span data-stu-id="6f0b3-p113">The command tells the CLSAgent on each computer and pool in the site Redmond to set the size of the rollover value on the tracing file to 40 megabytes. Computers and pools in other sites will not be affected by the command, and will continue to use the currently configured trace log rollover value defined either by default (20 megabytes) or during the start of the logging session.</span></span>
### <a name="to-create-a-new-centralized-logging-service-configuration"></a><span data-ttu-id="6f0b3-162">Para criar uma nova configuração do Serviço de Log Centralizado</span><span class="sxs-lookup"><span data-stu-id="6f0b3-162">To create a new Centralized Logging Service configuration</span></span>

1. <span data-ttu-id="6f0b3-163">Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar,** em Todos os **Programas,** no **Skype for Business 2015** e, em seguida, clique no Shell de Gerenciamento do **Skype for Business Server.**</span><span class="sxs-lookup"><span data-stu-id="6f0b3-163">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="6f0b3-164">Digite o seguinte no prompt de linha de comando:</span><span class="sxs-lookup"><span data-stu-id="6f0b3-164">Type the following at the command-line prompt:</span></span>

   ```PowerShell
   New-CsClsConfiguration -Identity <scope and name> [CsClsConfiguration options for this site]
   ```

    > [!NOTE]
    > <span data-ttu-id="6f0b3-165">New-CsClsConfiguration fornece acesso a um grande número de definições de configuração adicionais.</span><span class="sxs-lookup"><span data-stu-id="6f0b3-165">New-CsClsConfiguration provides access to a large number of optional configuration settings.</span></span> <span data-ttu-id="6f0b3-166">Para obter detalhes sobre as opções de configuração, consulte [Get-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csclsconfiguration?view=skype-ps) and [Understanding Centralized Logging Service Configuration Settings](https://technet.microsoft.com/library/3c34e600-0b91-43dc-b4cc-90b6a70ee12e.aspx).</span><span class="sxs-lookup"><span data-stu-id="6f0b3-166">For details about the configuration options, see [Get-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csclsconfiguration?view=skype-ps) and [Understanding Centralized Logging Service Configuration Settings](https://technet.microsoft.com/library/3c34e600-0b91-43dc-b4cc-90b6a70ee12e.aspx).</span></span>

<span data-ttu-id="6f0b3-167">Por exemplo, para criar uma nova configuração que defina uma pasta de rede para arquivos de cache, o período de tempo de sobreposição dos arquivos de log e tamanho de sobreposição dos arquivos de log, você deverá digitar:</span><span class="sxs-lookup"><span data-stu-id="6f0b3-167">For example, to create a new configuration that defines a network folder for cache files, rollover time period for the log files and rollover size for the log files, you would type:</span></span>

  ```PowerShell
  New-CsClsConfiguration -Identity "site:Redmond" -CacheFileNetworkFolder "\\fs01.contoso.net\filestore\logfiles" -EtlFileRolloverMinutes 120 -EtlFileRolloverSizeMB 40
  ```

<span data-ttu-id="6f0b3-168">Você deve planejar cuidadosamente a criação de novas configurações e como definir novas propriedades para o Serviço de Log Centralizado.</span><span class="sxs-lookup"><span data-stu-id="6f0b3-168">You should carefully plan the creation of new configurations and how you define new properties for the Centralized Logging Service.</span></span> <span data-ttu-id="6f0b3-169">Você deve ter cuidado ao fazer alterações e ter certeza que compreende o impacto da sua capacidade de registrar cenários de problema corretamente.</span><span class="sxs-lookup"><span data-stu-id="6f0b3-169">You should be cautious about making changes and make sure you understand the impact on your ability to properly log problem scenarios.</span></span> <span data-ttu-id="6f0b3-170">Você deve fazer alterações na configuração que melhorarão sua capacidade de gerenciar logs para um tamanho e período de sobreposição que permita resolver problemas, quando surgirem.</span><span class="sxs-lookup"><span data-stu-id="6f0b3-170">You should make changes to the configuration that will enhance your ability to manage logs to a size and a rollover period that will allow problem solving when it arises.</span></span>
### <a name="to-remove-an-existing-centralized-logging-service-configuration"></a><span data-ttu-id="6f0b3-171">Para remover uma configuração existente do Serviço de Log Centralizado</span><span class="sxs-lookup"><span data-stu-id="6f0b3-171">To remove an existing Centralized Logging Service configuration</span></span>

1. <span data-ttu-id="6f0b3-172">Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar,** em Todos os **Programas,** no **Skype for Business 2015** e, em seguida, clique no Shell de Gerenciamento do **Skype for Business Server.**</span><span class="sxs-lookup"><span data-stu-id="6f0b3-172">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="6f0b3-173">Digite o seguinte no prompt de linha de comando:</span><span class="sxs-lookup"><span data-stu-id="6f0b3-173">Type the following at the command-line prompt:</span></span>

   ```PowerShell
   Remove-CsClsConfiguration -Identity <scope and name>
   ```

<span data-ttu-id="6f0b3-174">Por exemplo, para remover uma configuração do Serviço de Log Centralizado que você criou para aumentar o tempo de sobremoção do arquivo de log, aumente o tamanho do arquivo de log de sobremoção e de definir o local do cache do arquivo de log para um compartilhamento de rede da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="6f0b3-174">For example, to remove a Centralized Logging Service configuration that you created to increase the log file rollover time, increase the rollover log file size, and set the log file cache location to a network share as follows:</span></span>

  ```PowerShell
  Remove-CsClsConfiguration -Identity "site:Redmond"
  ```

> [!NOTE]
> <span data-ttu-id="6f0b3-175">Esta é a nova configuração criada no procedimento "Para criar uma nova configuração do Serviço de Log Centralizado".</span><span class="sxs-lookup"><span data-stu-id="6f0b3-175">This is the new configuration that was created in the procedure "To create a new Centralized Logging Service configuration."</span></span>

<span data-ttu-id="6f0b3-176">Se decidir remover a configuração no nível do site, o site usará as configurações globais.</span><span class="sxs-lookup"><span data-stu-id="6f0b3-176">If you choose to remove a site-level configuration, the site will use the global settings.</span></span>
## <a name="see-also"></a><span data-ttu-id="6f0b3-177">Confira também</span><span class="sxs-lookup"><span data-stu-id="6f0b3-177">See also</span></span>

[<span data-ttu-id="6f0b3-178">Configurar provedores para o Serviço de Log Centralizado no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="6f0b3-178">Configure providers for Centralized Logging Service in Skype for Business Server 2015</span></span>](configure-providers.md)

[<span data-ttu-id="6f0b3-179">Configurar cenários para o Serviço de Log Centralizado no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="6f0b3-179">Configure scenarios for the Centralized Logging Service in Skype for Business Server 2015</span></span>](configure-scenarios.md)

[<span data-ttu-id="6f0b3-180">Centralized Logging Service in Skype for Business 2015</span><span class="sxs-lookup"><span data-stu-id="6f0b3-180">Centralized Logging Service in Skype for Business 2015</span></span>](centralized-logging-service.md)

[<span data-ttu-id="6f0b3-181">Set-CsClsConfiguration</span><span class="sxs-lookup"><span data-stu-id="6f0b3-181">Set-CsClsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps)

[<span data-ttu-id="6f0b3-182">Get-CsClsConfiguration</span><span class="sxs-lookup"><span data-stu-id="6f0b3-182">Get-CsClsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csclsconfiguration?view=skype-ps)

[<span data-ttu-id="6f0b3-183">New-CsClsConfiguration</span><span class="sxs-lookup"><span data-stu-id="6f0b3-183">New-CsClsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csclsconfiguration?view=skype-ps)

[<span data-ttu-id="6f0b3-184">Remove-CsClsConfiguration</span><span class="sxs-lookup"><span data-stu-id="6f0b3-184">Remove-CsClsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csclsconfiguration?view=skype-ps)
