---
title: Gerenciar configurações do Serviço de Log Centralizado no Skype for Business Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 93b9a354-9aea-4b3a-a4fe-68a89f436196
description: 'Resumo: Saiba como recuperar, atualizar e criar definições de configuração para o serviço de registro em log centralizado no Skype para Business Server 2015.'
ms.openlocfilehash: 0c4d03119a61fccd062e650c38815bee069852f5
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="manage-centralized-logging-service-configuration-settings-in-skype-for-business-server-2015"></a><span data-ttu-id="c442e-103">Gerenciar configurações do Serviço de Log Centralizado no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="c442e-103">Manage Centralized Logging Service configuration settings in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="c442e-104">**Resumo:** Saiba como recuperar, atualizar e criar definições de configuração para o serviço de registro em log centralizado no Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="c442e-104">**Summary:** Learn how to retrieve, update, and create configuration settings for the Centralized Logging Service in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="c442e-105">The Centralized Logging Service é controlado e configurado pelas configurações e os parâmetros que são criados e usados pelo Centralized Logging Service controlador (CLSController) para enviar comandos ao (de agente do serviço de registro em log centralizados do computador individual Com o CLSAgent).</span><span class="sxs-lookup"><span data-stu-id="c442e-105">The Centralized Logging Service is controlled and configured by settings and parameters that are created and used by the Centralized Logging Service Controller (CLSController) to send commands to the individual computer's Centralized Logging Service Agent (CLSAgent).</span></span> <span data-ttu-id="c442e-106">O agente processa os comandos enviados a ele e (no caso de um comando Iniciar) usa a configuração dos cenários, provedores, tamanho de log, duração de rastreamento e sinalizadores para começar a coletar logs de rastreamento de acordo com as informações de configuração fornecidas.</span><span class="sxs-lookup"><span data-stu-id="c442e-106">The agent processes the commands that are sent to it and (in the case of a Start command) uses the configuration of the scenarios, providers, trace duration, and flags to begin collecting trace logs according to the configuration information provided.</span></span>
  
> [!IMPORTANT]
>  <span data-ttu-id="c442e-107">Nem todos os cmdlets do Windows PowerShell listados para o serviço de registro em log centralizados servem para uso com Skype para implantações em instalações de negócios Server 2015.</span><span class="sxs-lookup"><span data-stu-id="c442e-107">Not all Windows PowerShell cmdlets listed for the Centralized Logging Service are intended for use with Skype for Business Server 2015 on-premises deployments.</span></span> <span data-ttu-id="c442e-108">Embora eles podem aparecer funcione, os cmdlets a seguir não foram projetados para funcionar com Skype para implantações em instalações de 2015 do servidor de negócios:</span><span class="sxs-lookup"><span data-stu-id="c442e-108">Although they may appear to work, the following cmdlets are not designed to function with Skype for Business Server 2015 on-premises deployments:</span></span>

-  <span data-ttu-id="c442e-109">**Cmdlets CsClsRegion:** [Get-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/get-csclsregion?view=skype-ps) ,[Set-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/set-csclsregion?view=skype-ps), [New-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/new-csclsregion?view=skype-ps)e [Remove-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/remove-csclsregion?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="c442e-109">**CsClsRegion cmdlets:** [Get-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/get-csclsregion?view=skype-ps) ,[Set-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/set-csclsregion?view=skype-ps), [New-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/new-csclsregion?view=skype-ps), and [Remove-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/remove-csclsregion?view=skype-ps).</span></span> 
-  <span data-ttu-id="c442e-110">**Cmdlets CsClsSearchTerm:** [Get-CsClsSearchTerm](https://docs.microsoft.com/powershell/module/skype/get-csclssearchterm?view=skype-ps) e [Set-CsClsSearchTerm](https://docs.microsoft.com/powershell/module/skype/set-csclssearchterm?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="c442e-110">**CsClsSearchTerm cmdlets:** [Get-CsClsSearchTerm](https://docs.microsoft.com/powershell/module/skype/get-csclssearchterm?view=skype-ps) and [Set-CsClsSearchTerm](https://docs.microsoft.com/powershell/module/skype/set-csclssearchterm?view=skype-ps).</span></span>  
-  <span data-ttu-id="c442e-111">**Cmdlets CsClsSecurityGroup:** [Get-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/get-csclssecuritygroup?view=skype-ps), [Set-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/set-csclssecuritygroup?view=skype-ps), [New-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/new-csclssecuritygroup?view=skype-ps)e [Remove-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/remove-csclssecuritygroup?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="c442e-111">**CsClsSecurityGroup cmdlets:** [Get-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/get-csclssecuritygroup?view=skype-ps), [Set-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/set-csclssecuritygroup?view=skype-ps),  [New-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/new-csclssecuritygroup?view=skype-ps), and [Remove-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/remove-csclssecuritygroup?view=skype-ps).</span></span> 

<span data-ttu-id="c442e-112">As configurações definidas nesses cmdlets não prejudicar ou causar qualquer comportamento adverso, mas eles foram projetados para uso com o Microsoft Office 365 e não produzirá os resultados esperados em implantações de local.</span><span class="sxs-lookup"><span data-stu-id="c442e-112">The settings defined in these cmdlets will not hinder or cause any adverse behavior, but they are designed for use with Microsoft Office 365 and will not yield the expected results in on-premises deployments.</span></span> <span data-ttu-id="c442e-113">Isso não quer dizer que não há uso para esses cmdlets em implantações locais, mas sua utilização é um tópico mais avançado, que não é abordado nesta documentação.</span><span class="sxs-lookup"><span data-stu-id="c442e-113">This is not to say that there is no use for these cmdlets in on-premises deployments, but their use is a more advanced topic that is not covered in this documentation.</span></span>
  
<span data-ttu-id="c442e-114">The Centralized Logging Service pode ser executado em um escopo que inclui um único computador ou um pool de computadores, em um escopo de site (ou seja, um site definido como o site Redmond que contém uma coleção de computador e os pools na sua implantação) ou em um escopo global (ou seja todos os computadores e pools na sua implantação).</span><span class="sxs-lookup"><span data-stu-id="c442e-114">The Centralized Logging Service can be run at a scope that includes a single computer or a pool of computers, at a site scope (that is, a defined site such as the site Redmond that contains a collection of computer and pools in your deployment), or at a global scope (that is, all computers and pools in your deployment).</span></span>
  
<span data-ttu-id="c442e-115">Para configurar o escopo do serviço de registro em log centralizado em log usando o Skype do Shell de gerenciamento do servidor de negócios, você deve ser um membro do CsAdministrator ou os grupos de segurança CsServerAdministrator acesso baseado em função (RBAC) de controle ou uma função RBAC personalizada que contém um desses dois grupos.</span><span class="sxs-lookup"><span data-stu-id="c442e-115">To configure the Centralized Logging Service scope by using the Skype for Business Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="c442e-116">Para retornar uma lista de todas as funções RBAC que este cmdlet foi atribuído ao (incluindo qualquer funções de RBAC personalizadas que você criou a mesmo), execute o seguinte comando do Skype para Business Server Management Shell ou o prompt do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="c442e-116">To return a list of all the RBAC roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Skype for Business Server Management Shell or the Windows PowerShell prompt:</span></span>
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "<Skype for Business cmdlet>"}
```

<span data-ttu-id="c442e-117">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="c442e-117">For example:</span></span>
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

> [!NOTE]
> <span data-ttu-id="c442e-118">Há algumas diferenças fundamentais entre os comandos de linha de comando que podem ser executados no Windows PowerShell ou CLSController.</span><span class="sxs-lookup"><span data-stu-id="c442e-118">There are fundamental differences between the command-line commands that you can run in Windows PowerShell or CLSController.</span></span> <span data-ttu-id="c442e-119">Windows PowerShell fornece um método avançado para configurar e definir cenários e reutilizar esses cenários de forma significativa para seus cenários de solução de problemas.</span><span class="sxs-lookup"><span data-stu-id="c442e-119">Windows PowerShell provides a rich method to configure and define scenarios, and to reuse those scenarios in a meaningful way for your troubleshooting scenarios.</span></span> <span data-ttu-id="c442e-120">Embora o CLSController forneça uma maneira rápida e eficiente para emitir comandos e obter resultados, o conjunto de comandos do CLSController está limitado aos comandos finitos que você tem disponível na linha de comando.</span><span class="sxs-lookup"><span data-stu-id="c442e-120">While CLSController does provide a fast and efficient way to issue commands and get results, the command set for CLSController is limited by the finite commands that you have available from the command line.</span></span> <span data-ttu-id="c442e-121">Ao contrário de cmdlets do Windows PowerShell, CLSController não é possível definir novos cenários, gerenciar escopo em um site ou nível global e muitos outras limitações de um conjunto de comandos finita que não pode ser configurado dinamicamente.</span><span class="sxs-lookup"><span data-stu-id="c442e-121">Unlike the Windows PowerShell cmdlets, CLSController cannot define new scenarios, manage scope at a site or global level, and many other limitations of a finite command set that cannot be dynamically configured.</span></span> <span data-ttu-id="c442e-122">Enquanto CLSController fornece os meios para execução fast, o Windows PowerShell fornece um meio para estender a funcionalidade de Centralized Logging Service, além do que é possível com CLSController.</span><span class="sxs-lookup"><span data-stu-id="c442e-122">While CLSController provides a means for fast execution, Windows PowerShell provides a means to extend the Centralized Logging Service functionality beyond what is possible with CLSController.</span></span> 
  
<span data-ttu-id="c442e-123">Escopo de um único computador pode ser definido durante a execução de um [Search-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/search-csclslogging?view=skype-ps), [Show-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/show-csclslogging?view=skype-ps), [Start-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/start-csclslogging?view=skype-ps), [Stop-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/stop-csclslogging?view=skype-ps), [Sync-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/sync-csclslogging?view=skype-ps) e [Update-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/update-csclslogging?view=skype-ps) comando usando o parâmetro-Computers.</span><span class="sxs-lookup"><span data-stu-id="c442e-123">A single computer scope can be defined during the execution of a [Search-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/search-csclslogging?view=skype-ps), [Show-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/show-csclslogging?view=skype-ps), [Start-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/start-csclslogging?view=skype-ps), [Stop-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/stop-csclslogging?view=skype-ps), [Sync-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/sync-csclslogging?view=skype-ps) and [Update-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/update-csclslogging?view=skype-ps) command using the -Computers parameter.</span></span> <span data-ttu-id="c442e-124">-Computadores parâmetro aceita uma lista separada por vírgulas de nomes de domínio totalmente qualificados (FQDNs) para o computador de destino.</span><span class="sxs-lookup"><span data-stu-id="c442e-124">The -Computers parameter accepts a comma separated list of fully qualified domain names (FQDNs) for the target computer.</span></span>
  
> [!TIP]
> <span data-ttu-id="c442e-125">Você também pode definir - Pools e uma lista separada por vírgulas de pools que você deseja executar os comandos de log em.</span><span class="sxs-lookup"><span data-stu-id="c442e-125">You can also define -Pools and a comma separated list of pools that you want to run the logging commands on.</span></span> 
  
<span data-ttu-id="c442e-126">Escopos de site e Global forem definidos nos cmdlets **New -**, **Set -**e **Remove -** Centralized Logging Service.</span><span class="sxs-lookup"><span data-stu-id="c442e-126">Site and Global scopes are defined in the **New-**, **Set-**, and **Remove-** Centralized Logging Service cmdlets.</span></span> <span data-ttu-id="c442e-127">Os exemplos a seguir demonstram como definir o escopo global ou de um site.</span><span class="sxs-lookup"><span data-stu-id="c442e-127">The following examples demonstrate how to set a site and a global scope.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="c442e-128">Os comandos mostrados podem conter parâmetros e conceitos que são abordados em outras seções.</span><span class="sxs-lookup"><span data-stu-id="c442e-128">The commands shown may contain parameters and concepts that are covered in other sections.</span></span> <span data-ttu-id="c442e-129">Os comandos de exemplo destinam-se a demonstrar o uso do **-Identity** parâmetro para definir o escopo e os outros parâmetros são incluídos para preservar a integridade e para especificar o escopo.</span><span class="sxs-lookup"><span data-stu-id="c442e-129">The example commands are intended to demonstrate the use of the **-Identity** parameter to define scope, and the other parameters are included for completeness and to specify the scope.</span></span> <span data-ttu-id="c442e-130">Para obter detalhes sobre os cmdlets **Set-CsClsConfiguration** , consulte [Set-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps) na documentação operações.</span><span class="sxs-lookup"><span data-stu-id="c442e-130">For details about the **Set-CsClsConfiguration** cmdlets, see [Set-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps) in the Operations documentation.</span></span>
  
### <a name="to-retrieve-the-current-centralized-logging-service-configuration"></a><span data-ttu-id="c442e-131">Para recuperar a configuração atual do Centralized Logging Service</span><span class="sxs-lookup"><span data-stu-id="c442e-131">To retrieve the current Centralized Logging Service configuration</span></span>

1. <span data-ttu-id="c442e-132">Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="c442e-132">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="c442e-133">Digite o seguinte no prompt de linha de comando:</span><span class="sxs-lookup"><span data-stu-id="c442e-133">Type the following at the command-line prompt:</span></span>
    
  ```
  Get-CsClsConfiguration
  ```

<span data-ttu-id="c442e-134">Use os cmdlets **New-CsClsConfiguration** e **Set-CsClsConfiguration** para criar uma nova configuração ou para atualizar uma configuração existente. Quando você executar **Get-CsClsConfiguration**, ele exibe informações similares a seguinte captura de tela, onde a implantação atualmente tem a configuração Global, mas nenhuma configuração de site definida:</span><span class="sxs-lookup"><span data-stu-id="c442e-134">Use the **New-CsClsConfiguration** and **Set-CsClsConfiguration** cmdlets to create a new configuration or to update an existing configuration.When you run **Get-CsClsConfiguration**, it displays information similar to the following screen shot, where the deployment currently has the default Global configuration, but no site configurations defined:</span></span>
  
![Amostra de saída do Get-CsClsConfiguration.](../../media/Ops_Get-CsClsConfiguration_Basic.jpg)
  
### <a name="to-retrieve-the-current-centralized-logging-service-configuration-from-the-computer-local-store"></a><span data-ttu-id="c442e-136">Para recuperar a configuração atual do serviço de log centralizado em log do repositório local do computador</span><span class="sxs-lookup"><span data-stu-id="c442e-136">To retrieve the current Centralized Logging Service configuration from the computer local store</span></span>

1. <span data-ttu-id="c442e-137">Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="c442e-137">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="c442e-138">Digite o seguinte no prompt de linha de comando:</span><span class="sxs-lookup"><span data-stu-id="c442e-138">Type the following at the command-line prompt:</span></span>
    
  ```
  Get-CsClsConfiguration -LocalStore
  ```

<span data-ttu-id="c442e-139">Quando você usa o primeiro exemplo onde **Get-CsClsConfiguration** não especifica nenhum parâmetro, as referências de comando repositório de gerenciamento Central para os dados.</span><span class="sxs-lookup"><span data-stu-id="c442e-139">When you use the first example where **Get-CsClsConfiguration** does not specify any parameters, the command references the Central Management store for the data.</span></span> <span data-ttu-id="c442e-140">Se você especificar o parâmetro - LocalStore, o comando referencia o computador LocalStore em vez de repositório de gerenciamento Central.</span><span class="sxs-lookup"><span data-stu-id="c442e-140">If you specify the parameter -LocalStore, the command references the computer LocalStore instead of the Central Management store.</span></span>
### <a name="to-retrieve-a-listing-of-scenarios-currently-defined"></a><span data-ttu-id="c442e-141">Para recuperar uma lista de cenários definidos no momento</span><span class="sxs-lookup"><span data-stu-id="c442e-141">To retrieve a listing of scenarios currently defined</span></span>

1. <span data-ttu-id="c442e-142">Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="c442e-142">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="c442e-143">Digite o seguinte no prompt de linha de comando:</span><span class="sxs-lookup"><span data-stu-id="c442e-143">Type the following at the command-line prompt:</span></span>
    
  ```
  Get-CsClsConfiguration -Identity <scope and name> | Select-Object -ExpandProperty Scenarios
  ```

    <span data-ttu-id="c442e-144">Por exemplo, para recuperar os cenários definidos no escopo global:</span><span class="sxs-lookup"><span data-stu-id="c442e-144">For example, to retrieve the scenarios that is defined at the global scope:</span></span>
    
  ```
  Get-CsClsConfiguration -Identity "global" | Select-Object -ExpandProperty Scenarios
  ```

<span data-ttu-id="c442e-145">O cmdlet **Get-CsClsConfiguration** sempre exibe os cenários que fazem parte da configuração de um determinado escopo.</span><span class="sxs-lookup"><span data-stu-id="c442e-145">The cmdlet **Get-CsClsConfiguration** always displays the scenarios that are a part of a given scope's configuration.</span></span> <span data-ttu-id="c442e-146">Na maioria dos casos, nem todos os cenários são exibidos e estão truncados.</span><span class="sxs-lookup"><span data-stu-id="c442e-146">In most cases, all scenarios are not displayed, and are truncated.</span></span> <span data-ttu-id="c442e-147">O comando usado aqui lista todos os cenários e as informações parciais sobre quais provedores, configurações e sinalizadores são usados.</span><span class="sxs-lookup"><span data-stu-id="c442e-147">The command used here lists all of the scenarios and partial information about what providers, settings, and flags are used.</span></span>
### <a name="to-update-a-global-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a><span data-ttu-id="c442e-148">Para atualizar um escopo global para o serviço de registro em log centralizado em log usando o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c442e-148">To update a global scope for the Centralized Logging Service by using Windows PowerShell</span></span>

1. <span data-ttu-id="c442e-149">Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="c442e-149">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="c442e-150">Digite o seguinte no prompt de linha de comando:</span><span class="sxs-lookup"><span data-stu-id="c442e-150">Type the following at the command-line prompt:</span></span>
    
  ```
  Set-CsClsConfiguration -Identity <scope> -EtlFileRolloverSizeMB <size for logging file in megabytes>
  ```

  <span data-ttu-id="c442e-151">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="c442e-151">For example:</span></span>
    
  ```
  Set-CsClsConfiguration -Identity "global" -EtlFileRolloverSizeMB 40
  ```

<span data-ttu-id="c442e-p111">O comando diz ao CLSAgent em cada computador e pool na implantação para definir o tamanho do valor de sobreposição no arquivo de rastreamento para 40 megabytes. Os computadores e pools em todos os sites são afetados pelo comando, e definirão seu valor configurado de sobreposição de log de rastreamento para 40 megabytes.</span><span class="sxs-lookup"><span data-stu-id="c442e-p111">The command tells the CLSAgent on each computer and pool in the deployment to set the size of the rollover value on the tracing file to 40 megabytes. Computers and pools in all sites are affected by the command, and will set their configured trace log rollover value to 40 megabytes.</span></span>
### <a name="to-update-a-site-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a><span data-ttu-id="c442e-154">Para atualizar um escopo de site para o serviço de registro em log centralizado em log usando o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c442e-154">To update a site scope for the Centralized Logging Service by using Windows PowerShell</span></span>

1. <span data-ttu-id="c442e-155">Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="c442e-155">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="c442e-156">Digite o seguinte no prompt de linha de comando:</span><span class="sxs-lookup"><span data-stu-id="c442e-156">Type the following at the command-line prompt:</span></span>
    
  ```
  Set-CsClsConfiguration -Identity <scope/site name> -EtlFileRolloverSizeMB <size for logging file in megabytes>
  ```

  <span data-ttu-id="c442e-157">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="c442e-157">For example:</span></span>
    
  ```
  Set-CsClsConfiguration -Identity "site/Redmond" -EtlFileRolloverSizeMB 40  
  ```

> [!NOTE]
> <span data-ttu-id="c442e-p112">Como observado no exemplo, o local padrão dos arquivos de log é %TEMP%\Tracing. No entanto, como é o CLSAgent que está gravando o arquivo, e o CSLAgent é executado no Serviço de Rede, a variável %TEMP% expande para %WINDIR%\ServiceProfiles\NetworkService\AppData\Local.</span><span class="sxs-lookup"><span data-stu-id="c442e-p112">As noted in the example, the default location of the log files is %TEMP%\Tracing. However, because it is actually CLSAgent that is writing the file and CSLAgent runs as Network Service, the %TEMP% variable expands to %WINDIR%\ServiceProfiles\NetworkService\AppData\Local.</span></span> 
  
<span data-ttu-id="c442e-p113">O comando diz ao CLSAgent em cada computador e pool no site da Redmond para definir o tamanho do valor de sobreposição no arquivo de rastreamento para 40 megabytes. Os computadores e pools em outros sites não serão afetados pelo comando, e continuarão a usar o valor atualmente configurado de sobreposição de log de rastreamento definido pelo padrão (20 megabytes) ou durante o início da sessão de log.</span><span class="sxs-lookup"><span data-stu-id="c442e-p113">The command tells the CLSAgent on each computer and pool in the site Redmond to set the size of the rollover value on the tracing file to 40 megabytes. Computers and pools in other sites will not be affected by the command, and will continue to use the currently configured trace log rollover value defined either by default (20 megabytes) or during the start of the logging session.</span></span>
### <a name="to-create-a-new-centralized-logging-service-configuration"></a><span data-ttu-id="c442e-162">Para criar uma nova configuração de Centralized Logging Service</span><span class="sxs-lookup"><span data-stu-id="c442e-162">To create a new Centralized Logging Service configuration</span></span>

1. <span data-ttu-id="c442e-163">Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="c442e-163">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="c442e-164">Digite o seguinte no prompt de linha de comando:</span><span class="sxs-lookup"><span data-stu-id="c442e-164">Type the following at the command-line prompt:</span></span>
    
  ```
  New-CsClsConfiguration -Identity <scope and name> [CsClsConfiguration options for this site]
  ```

    > [!NOTE]
    > <span data-ttu-id="c442e-165">New-CsClsConfiguration fornece acesso a um grande número de definições de configuração adicionais.</span><span class="sxs-lookup"><span data-stu-id="c442e-165">New-CsClsConfiguration provides access to a large number of optional configuration settings.</span></span> <span data-ttu-id="c442e-166">Para obter detalhes sobre as opções de configuração, consulte [Get-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csclsconfiguration?view=skype-ps) e [Noções básicas sobre Centralized Logging Service definições de configuração](http://technet.microsoft.com/library/3c34e600-0b91-43dc-b4cc-90b6a70ee12e.aspx).</span><span class="sxs-lookup"><span data-stu-id="c442e-166">For details about the configuration options, see [Get-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csclsconfiguration?view=skype-ps) and [Understanding Centralized Logging Service Configuration Settings](http://technet.microsoft.com/library/3c34e600-0b91-43dc-b4cc-90b6a70ee12e.aspx).</span></span> 
  
<span data-ttu-id="c442e-167">Por exemplo, para criar uma nova configuração que defina uma pasta de rede para arquivos de cache, o período de tempo de sobreposição dos arquivos de log e tamanho de sobreposição dos arquivos de log, você deverá digitar:</span><span class="sxs-lookup"><span data-stu-id="c442e-167">For example, to create a new configuration that defines a network folder for cache files, rollover time period for the log files and rollover size for the log files, you would type:</span></span>
    
  ```
  New-CsClsConfiguration -Identity "site:Redmond" -CacheFileNetworkFolder "\\fs01.contoso.net\filestore\logfiles" -EtlFileRolloverMinutes 120 -EtlFileRolloverSizeMB 40
  ```

<span data-ttu-id="c442e-168">Você deverá planejar cuidadosamente a criação de novas configurações e como definir novas propriedades para o serviço de registro em log centralizado.</span><span class="sxs-lookup"><span data-stu-id="c442e-168">You should carefully plan the creation of new configurations and how you define new properties for the Centralized Logging Service.</span></span> <span data-ttu-id="c442e-169">Você deve ter cuidado ao fazer alterações e ter certeza que compreende o impacto da sua capacidade de registrar cenários de problema corretamente.</span><span class="sxs-lookup"><span data-stu-id="c442e-169">You should be cautious about making changes and make sure you understand the impact on your ability to properly log problem scenarios.</span></span> <span data-ttu-id="c442e-170">Você deve fazer alterações na configuração que melhorarão sua capacidade de gerenciar logs para um tamanho e período de sobreposição que permita resolver problemas, quando surgirem.</span><span class="sxs-lookup"><span data-stu-id="c442e-170">You should make changes to the configuration that will enhance your ability to manage logs to a size and a rollover period that will allow problem solving when it arises.</span></span>
### <a name="to-remove-an-existing-centralized-logging-service-configuration"></a><span data-ttu-id="c442e-171">Para remover uma configuração Centralized Logging Service existente</span><span class="sxs-lookup"><span data-stu-id="c442e-171">To remove an existing Centralized Logging Service configuration</span></span>

1. <span data-ttu-id="c442e-172">Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="c442e-172">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="c442e-173">Digite o seguinte no prompt de linha de comando:</span><span class="sxs-lookup"><span data-stu-id="c442e-173">Type the following at the command-line prompt:</span></span>
    
  ```
  Remove-CsClsConfiguration -Identity <scope and name>
  ```

<span data-ttu-id="c442e-174">Por exemplo, para remover uma configuração de Centralized Logging Service que você criou para aumentar o tempo de sobreposição de arquivo de log, aumentar o tamanho de arquivo de log de sobreposição e definir o local de cache do arquivo de log para um compartilhamento de rede da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="c442e-174">For example, to remove a Centralized Logging Service configuration that you created to increase the log file rollover time, increase the rollover log file size, and set the log file cache location to a network share as follows:</span></span>
    
  ```
  Remove-CsClsConfiguration -Identity "site:Redmond"
  ```

> [!NOTE]
> <span data-ttu-id="c442e-175">Esta é a nova configuração que foi criada no procedimento "para criar uma nova configuração de serviço de registro em log centralizado."</span><span class="sxs-lookup"><span data-stu-id="c442e-175">This is the new configuration that was created in the procedure "To create a new Centralized Logging Service configuration."</span></span> 
  
<span data-ttu-id="c442e-176">Se decidir remover a configuração no nível do site, o site usará as configurações globais.</span><span class="sxs-lookup"><span data-stu-id="c442e-176">If you choose to remove a site-level configuration, the site will use the global settings.</span></span>
## <a name="see-also"></a><span data-ttu-id="c442e-177">Consulte também</span><span class="sxs-lookup"><span data-stu-id="c442e-177">See also</span></span>

#### 

[<span data-ttu-id="c442e-178">Configurar provedores para Centralized Logging Service no Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="c442e-178">Configure providers for Centralized Logging Service in Skype for Business Server 2015</span></span>](configure-providers.md)
  
[<span data-ttu-id="c442e-179">Configurar cenários para o serviço de registro em log centralizado no Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="c442e-179">Configure scenarios for the Centralized Logging Service in Skype for Business Server 2015</span></span>](configure-scenarios.md)
#### 

[<span data-ttu-id="c442e-180">Serviço de registro em log centralizado no Skype para negócios 2015</span><span class="sxs-lookup"><span data-stu-id="c442e-180">Centralized Logging Service in Skype for Business 2015</span></span>](centralized-logging-service.md)
#### 

[<span data-ttu-id="c442e-181">Set-CsClsConfiguration</span><span class="sxs-lookup"><span data-stu-id="c442e-181">Set-CsClsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps)
  
[<span data-ttu-id="c442e-182">Get-CsClsConfiguration</span><span class="sxs-lookup"><span data-stu-id="c442e-182">Get-CsClsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csclsconfiguration?view=skype-ps)
  
[<span data-ttu-id="c442e-183">New-CsClsConfiguration</span><span class="sxs-lookup"><span data-stu-id="c442e-183">New-CsClsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csclsconfiguration?view=skype-ps)
  
[<span data-ttu-id="c442e-184">Remove-CsClsConfiguration</span><span class="sxs-lookup"><span data-stu-id="c442e-184">Remove-CsClsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csclsconfiguration?view=skype-ps)

