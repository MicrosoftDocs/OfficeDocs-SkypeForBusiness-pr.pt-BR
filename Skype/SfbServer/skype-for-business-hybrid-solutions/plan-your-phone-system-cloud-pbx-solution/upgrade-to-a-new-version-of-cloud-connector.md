---
title: Atualizar para uma nova versão do Cloud Connector
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: efbe25f2-faf5-41c7-8c95-dbc4a835a4a8
description: Saiba como atualizar sua implantação do Cloud Connector Edition.
ms.openlocfilehash: fea78c6b1b6ba3b2e644fef71d78b94aa3a244b7
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51109127"
---
# <a name="upgrade-to-a-new-version-of-cloud-connector"></a><span data-ttu-id="7e97b-103">Atualizar para uma nova versão do Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="7e97b-103">Upgrade to a new version of Cloud Connector</span></span>

> [!Important]
> <span data-ttu-id="7e97b-104">O Cloud Connector Edition se aposentará em 31 de julho de 2021 junto com o Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="7e97b-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="7e97b-105">Depois que sua organização tiver atualizado para o Teams, saiba como conectar sua rede de telefonia local ao Teams usando [Roteamento Direto.](/MicrosoftTeams/direct-routing-landing-page)</span><span class="sxs-lookup"><span data-stu-id="7e97b-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](/MicrosoftTeams/direct-routing-landing-page).</span></span>
 
<span data-ttu-id="7e97b-106">Saiba como atualizar sua implantação do Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="7e97b-106">Learn about how to upgrade your Cloud Connector Edition deployment.</span></span>
  
<span data-ttu-id="7e97b-107">Se você tiver criado uma conta de locatário de gerenciamento online e habilitado atualizações automáticas, a implantação existente do Skype for Business Cloud Connector Edition será atualizada automaticamente para a versão mais recente, de acordo com a configuração da janela de tempo de atualização automática.</span><span class="sxs-lookup"><span data-stu-id="7e97b-107">If you have set up an online management tenant account and enabled automatic updates, your existing deployment of Skype for Business Cloud Connector Edition will be upgraded to the newer version automatically—according to your automatic update time window configuration.</span></span> <span data-ttu-id="7e97b-108">Você também pode executar uma atualização manual.</span><span class="sxs-lookup"><span data-stu-id="7e97b-108">You can also perform a manual upgrade.</span></span> 
  
<span data-ttu-id="7e97b-109">As versões 1.4.1 e posteriores do Cloud Connector Edition executam atualizações automáticas por padrão.</span><span class="sxs-lookup"><span data-stu-id="7e97b-109">Cloud Connector Edition versions 1.4.1 and later perform automatic updates by default.</span></span> <span data-ttu-id="7e97b-110">Se você deseja atualizar para a versão mais recente (2.1) manualmente, consulte [Upgrade a single site to a new version](upgrade-to-a-new-version-of-cloud-connector.md#BKMK_Upgrade) later in this topic.</span><span class="sxs-lookup"><span data-stu-id="7e97b-110">If you want to upgrade to the latest version (2.1) manually, see [Upgrade a single site to a new version](upgrade-to-a-new-version-of-cloud-connector.md#BKMK_Upgrade) later in this topic.</span></span>
  
<span data-ttu-id="7e97b-111">A atualização automática exige que o serviço do Cloud Connector está em execução.</span><span class="sxs-lookup"><span data-stu-id="7e97b-111">Automatic update requires that the Cloud Connector service is running.</span></span> <span data-ttu-id="7e97b-112">As etapas a seguir descrevem o processo de atualizações automáticas:</span><span class="sxs-lookup"><span data-stu-id="7e97b-112">The following steps describe the process for automatic updates:</span></span>
  
- <span data-ttu-id="7e97b-113">O processo de atualização automática será executado de acordo com o cronograma que você configurou para atualizações automáticas.</span><span class="sxs-lookup"><span data-stu-id="7e97b-113">The automatic update process will run according to the schedule you have configured for automatic updates.</span></span>
    
- <span data-ttu-id="7e97b-114">Tarefas de atualização do sistema operacional</span><span class="sxs-lookup"><span data-stu-id="7e97b-114">Operating system update tasks</span></span>
    
  - <span data-ttu-id="7e97b-115">Verifique e baixe as atualizações do sistema operacional para todas as VMs do Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="7e97b-115">Check and download operating system updates to all Cloud Connector VMs.</span></span> 
    
  - <span data-ttu-id="7e97b-116">Instale e atualize todas as VMs do Cloud Connector uma por uma e reinicie.</span><span class="sxs-lookup"><span data-stu-id="7e97b-116">Install and update all Cloud Connector VMs one by one and restart.</span></span>
    
  - <span data-ttu-id="7e97b-117">Após a reinicialização das VMs do Cloud Connector, verifique se outra reinicialização é necessária.</span><span class="sxs-lookup"><span data-stu-id="7e97b-117">After the Cloud Connector VMs restart, check to see if another restart is needed.</span></span>
    
  - <span data-ttu-id="7e97b-118">Depois que as VMs do Cloud Connector foram corrigidas com êxito, repita o processo para o computador host do Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="7e97b-118">After the Cloud Connector VMs have been successfully patched, repeat the process for the Cloud Connector host machine.</span></span>
    
  - <span data-ttu-id="7e97b-119">Depois que a máquina host do Cloud Connector for inicializada com êxito, todas as tarefas pendentes de atualização do sistema operacional serão concluídas.</span><span class="sxs-lookup"><span data-stu-id="7e97b-119">After the Cloud Connector host machine successfully boots up, any outstanding operating system update tasks are completed.</span></span>
    
- <span data-ttu-id="7e97b-120">Tarefas de atualização do Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="7e97b-120">Cloud Connector update tasks</span></span>
    
  - <span data-ttu-id="7e97b-121">Baixe e verifique o arquivo de versão do site de download.</span><span class="sxs-lookup"><span data-stu-id="7e97b-121">Download and check the version file from the download site.</span></span>
    
  - <span data-ttu-id="7e97b-122">Baixe o novo arquivo .msi versão.</span><span class="sxs-lookup"><span data-stu-id="7e97b-122">Download the new version .msi file.</span></span> 
    
  - <span data-ttu-id="7e97b-123">Desinstalar o arquivo msi antigo; instale o novo arquivo msi.</span><span class="sxs-lookup"><span data-stu-id="7e97b-123">Uninstall the old msi file; install the new msi file.</span></span>
    
  - <span data-ttu-id="7e97b-124">Baixe a nova versão dos bits do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="7e97b-124">Download the new version of Skype for Business bits.</span></span>
    
  - <span data-ttu-id="7e97b-125">Registre o dispositivo chamando Register-CcAppliance.</span><span class="sxs-lookup"><span data-stu-id="7e97b-125">Register the appliance by calling Register-CcAppliance.</span></span>
    
  - <span data-ttu-id="7e97b-126">Instale a nova versão do Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="7e97b-126">Install the new Cloud Connector version.</span></span>
    
  - <span data-ttu-id="7e97b-127">Drenar o dispositivo antigo e alternar a conexão de rede para o novo dispositivo.</span><span class="sxs-lookup"><span data-stu-id="7e97b-127">Drain the old appliance and switch the network connection to the new appliance.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="7e97b-128">Quando o Cloud Connector é atualizado para uma nova com build, os cmdlets do Cloud Connector podem não ser atualizados.</span><span class="sxs-lookup"><span data-stu-id="7e97b-128">When Cloud Connector updates to a new build, Cloud Connector cmdlets might not be updated.</span></span> <span data-ttu-id="7e97b-129">Isso pode acontecer, por exemplo, se uma janela do PowerShell for deixada aberta enquanto a atualização automática ocorrer.</span><span class="sxs-lookup"><span data-stu-id="7e97b-129">This can happen, for example, if a PowerShell window is left open while automatic update occurs.</span></span> <span data-ttu-id="7e97b-130">Para carregar os cmdlets atualizados, você pode executar uma das seguintes etapas:> Fechar o PowerShell no dispositivo do Cloud Connector e reabrir o PowerShell.> Ou, você pode executar Import-Module CloudConnector -Force.</span><span class="sxs-lookup"><span data-stu-id="7e97b-130">To load the updated cmdlets, you can do either of the following steps:>  Close PowerShell on the Cloud Connector appliance, and then reopen PowerShell.>  Or, you can run Import-Module CloudConnector -Force.</span></span>
  
## <a name="upgrade-a-single-site-to-a-new-version"></a><span data-ttu-id="7e97b-131">Atualizar um único site para uma nova versão</span><span class="sxs-lookup"><span data-stu-id="7e97b-131">Upgrade a single site to a new version</span></span>
<span data-ttu-id="7e97b-132"><a name="BKMK_Upgrade"> </a></span><span class="sxs-lookup"><span data-stu-id="7e97b-132"><a name="BKMK_Upgrade"> </a></span></span>

<span data-ttu-id="7e97b-133">Se houver apenas um dispositivo no site que você deseja atualizar, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="7e97b-133">If there is only one appliance in the site you want to upgrade, do the following:</span></span>
  
1. <span data-ttu-id="7e97b-134">Desinstale a versão existente do Cloud Connector em Programas e Recursos do Painel de **\> \> Controle.**</span><span class="sxs-lookup"><span data-stu-id="7e97b-134">Uninstall the existing Cloud Connector version in **Control Panel \> Programs \> Programs and Features**.</span></span>
    
2. <span data-ttu-id="7e97b-135">Instale a nova versão do CloudConnector.msi de [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller) .</span><span class="sxs-lookup"><span data-stu-id="7e97b-135">Install the new version of CloudConnector.msi from [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller).</span></span>
    
3. <span data-ttu-id="7e97b-136">Confirme se você tem o arquivo CloudConnector.ini da versão que está instalando e se atualizou todos os valores necessários para seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="7e97b-136">Confirm that you have the CloudConnector.ini file for the version you are installing, and that you have updated all of the required values for your environment.</span></span> <span data-ttu-id="7e97b-137">Não é possível usar o arquivo .ini de uma versão anterior.</span><span class="sxs-lookup"><span data-stu-id="7e97b-137">You cannot use the .ini file from a previous release.</span></span> <span data-ttu-id="7e97b-138">Se você estiver atualizando o Cloud Connector, consulte o tópico Prepare your [Cloud Connector appliance](prepare-your-cloud-connector-appliance.md) and make sure SiteName and EnableReferSupport are set to the correct value in the CloudConnector.ini file.</span><span class="sxs-lookup"><span data-stu-id="7e97b-138">If you are upgrading Cloud Connector, please refer to the topic [Prepare your Cloud Connector appliance](prepare-your-cloud-connector-appliance.md) and make sure SiteName and EnableReferSupport are set to the correct value in the CloudConnector.ini file.</span></span>
    
4. <span data-ttu-id="7e97b-139">Inicie um console do PowerShell como administrador e execute o seguinte cmdlet para registrar o dispositivo atual:</span><span class="sxs-lookup"><span data-stu-id="7e97b-139">Start a PowerShell console as administrator and run the following cmdlet to register the current appliance:</span></span>
    
   ```powershell
   Register-CcAppliance
   ```

5. <span data-ttu-id="7e97b-140">Execute o seguinte cmdlet para baixar a versão mais recente:</span><span class="sxs-lookup"><span data-stu-id="7e97b-140">Run the following cmdlet to download the latest version:</span></span>
    
   ```powershell
   Start-CcDownload
   ```

6. <span data-ttu-id="7e97b-141">Execute o seguinte cmdlet para iniciar a instalação:</span><span class="sxs-lookup"><span data-stu-id="7e97b-141">Run the following cmdlet to start the installation:</span></span> 
    
   ```powershell
   Install-CcAppliance -Upgrade
   ```

7. <span data-ttu-id="7e97b-142">Execute o seguinte cmdlet para ativar a nova implantação e desativar a versão anterior:</span><span class="sxs-lookup"><span data-stu-id="7e97b-142">Run the following cmdlet to activate the new deployment and turn off the previous version:</span></span>
    
   ```powershell
   Switch-CcVersion
   ```

<span data-ttu-id="7e97b-143">Se houver mais de um dispositivo no site, siga as etapas anteriores para atualizar cada dispositivo um por um.</span><span class="sxs-lookup"><span data-stu-id="7e97b-143">If there is more than one appliance in the site, please follow the preceding steps to upgrade each appliance one by one.</span></span>
  
<span data-ttu-id="7e97b-144">Se você quiser atualizar o administrador de domínio, administrador de máquina virtual, administrador de modo seguro e credenciais de administrador de locatários, você pode executar o cmdlet com o parâmetro  _UpdateAllCredentials_ para redefinir todas as credenciais:</span><span class="sxs-lookup"><span data-stu-id="7e97b-144">If you want to update Domain administrator, Virtual machine administrator, Safe Mode administrator and Tenant administrator credentials, you can run the cmdlet with the  _UpdateAllCredentials_ parameter to reset all credentials:</span></span>
  
```powershell
Install-CcAppliance -UpdateAllCredentials
```

<span data-ttu-id="7e97b-145">Em seguida, quando você começar a atualizar para uma nova versão, será promovido a inserir as novas credenciais.</span><span class="sxs-lookup"><span data-stu-id="7e97b-145">Then, when you start to upgrade to a new version, you will be promoted to input the new credentials.</span></span> 
  
<span data-ttu-id="7e97b-146">Se você deseja apenas redefinir suas credenciais de administrador de locatários, execute o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="7e97b-146">If you only want to reset your Tenant administrator credentials, run the following cmdlet:</span></span>
  
```powershell
Set-CcCredential -AccountType TenantAdmin
```

## <a name="upgrade-multiple-sites-to-a-new-version"></a><span data-ttu-id="7e97b-147">Atualizar vários sites para uma nova versão</span><span class="sxs-lookup"><span data-stu-id="7e97b-147">Upgrade multiple sites to a new version</span></span>
<span data-ttu-id="7e97b-148"><a name="BKMK_Upgrade"> </a></span><span class="sxs-lookup"><span data-stu-id="7e97b-148"><a name="BKMK_Upgrade"> </a></span></span>

<span data-ttu-id="7e97b-149">Siga as etapas para atualizar um único site, atualizando um site por vez para cada site em sua implantação.</span><span class="sxs-lookup"><span data-stu-id="7e97b-149">Follow the steps for upgrading a single site, upgrading one site at a time for each site in your deployment.</span></span> <span data-ttu-id="7e97b-150">Certifique-se de [validar a implantação do Cloud Connector](validate-your-cloud-connector-deployment.md) após atualizar cada site.</span><span class="sxs-lookup"><span data-stu-id="7e97b-150">Make sure and [Validate your Cloud Connector deployment](validate-your-cloud-connector-deployment.md) after upgrading each site.</span></span>
