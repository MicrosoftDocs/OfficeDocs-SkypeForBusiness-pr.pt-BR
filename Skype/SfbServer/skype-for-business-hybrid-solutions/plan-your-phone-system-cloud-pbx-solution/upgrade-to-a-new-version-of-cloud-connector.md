---
title: Atualizar para uma nova versão do Cloud Connector
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: efbe25f2-faf5-41c7-8c95-dbc4a835a4a8
description: Saiba como atualizar sua implantação do Cloud Connector Edition.
ms.openlocfilehash: 5b3ca4b216bc376c9e23424fb978b5cd83e4aa41
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32240659"
---
# <a name="upgrade-to-a-new-version-of-cloud-connector"></a><span data-ttu-id="4b6bb-103">Upgrade to a new version of Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="4b6bb-103">Upgrade to a new version of Cloud Connector</span></span>
 
<span data-ttu-id="4b6bb-104">Saiba como atualizar sua implantação do Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="4b6bb-104">Learn about how to upgrade your Cloud Connector Edition deployment.</span></span>
  
<span data-ttu-id="4b6bb-p101">Se você tiver configurado uma conta de locatário de gerenciamento e habilitado as atualizações automáticas, sua implantação existente do Skype for Business Cloud Connector Edition será atualizada para a versão mais recente automaticamente, conforme sua configuração de frequência de atualização automática. Você também poderá executar uma atualização manual. </span><span class="sxs-lookup"><span data-stu-id="4b6bb-p101">If you have set up an online management tenant account and enabled automatic updates, your existing deployment of Skype for Business Cloud Connector Edition will be upgraded to the newer version automatically—according to your automatic update time window configuration. You can also perform a manual upgrade.</span></span> 
  
<span data-ttu-id="4b6bb-107">Versões de conector Edition 1.4.1 em nuvem e posteriormente executar atualizações automáticas por padrão.</span><span class="sxs-lookup"><span data-stu-id="4b6bb-107">Cloud Connector Edition versions 1.4.1 and later perform automatic updates by default.</span></span> <span data-ttu-id="4b6bb-108">Se você deseja atualizar para a versão mais recente (2.1) manualmente, consulte [atualizar um único site para uma nova versão](upgrade-to-a-new-version-of-cloud-connector.md#BKMK_Upgrade) , mais adiante neste tópico.</span><span class="sxs-lookup"><span data-stu-id="4b6bb-108">If you want to upgrade to the latest version (2.1) manually, see [Upgrade a single site to a new version](upgrade-to-a-new-version-of-cloud-connector.md#BKMK_Upgrade) later in this topic.</span></span>
  
<span data-ttu-id="4b6bb-109">Atualização automática requer que o serviço de nuvem conector está funcionando.</span><span class="sxs-lookup"><span data-stu-id="4b6bb-109">Automatic update requires that the Cloud Connector service is running.</span></span> <span data-ttu-id="4b6bb-110">As seguintes etapas escrevem o processo para as atualizações automáticas:</span><span class="sxs-lookup"><span data-stu-id="4b6bb-110">The following steps describe the process for automatic updates:</span></span>
  
- <span data-ttu-id="4b6bb-111">O processo de atualização automática será executado de acordo com a programação que você configurou para as atualizações automáticas.</span><span class="sxs-lookup"><span data-stu-id="4b6bb-111">The automatic update process will run according to the schedule you have configured for automatic updates.</span></span>
    
- <span data-ttu-id="4b6bb-112">Tarefas de atualização do sistema operacional</span><span class="sxs-lookup"><span data-stu-id="4b6bb-112">Operating system update tasks</span></span>
    
  - <span data-ttu-id="4b6bb-113">Verifique e baixar atualizações de sistema operacional para todas as máquinas virtuais de conector de nuvem.</span><span class="sxs-lookup"><span data-stu-id="4b6bb-113">Check and download operating system updates to all Cloud Connector VMs.</span></span> 
    
  - <span data-ttu-id="4b6bb-114">Instalar e atualizar todas as VMs de conector de nuvem uma e reiniciar.</span><span class="sxs-lookup"><span data-stu-id="4b6bb-114">Install and update all Cloud Connector VMs one by one and restart.</span></span>
    
  - <span data-ttu-id="4b6bb-115">Após reiniciar a nuvem conector VMs, verifique se outra reinicialização é necessária.</span><span class="sxs-lookup"><span data-stu-id="4b6bb-115">After the Cloud Connector VMs restart, check to see if another restart is needed.</span></span>
    
  - <span data-ttu-id="4b6bb-116">Após a nuvem conector VMs receberam com êxito o patch, repita o processo para a máquina host de conector de nuvem.</span><span class="sxs-lookup"><span data-stu-id="4b6bb-116">After the Cloud Connector VMs have been successfully patched, repeat the process for the Cloud Connector host machine.</span></span>
    
  - <span data-ttu-id="4b6bb-117">Depois que a máquina host de conector de nuvem inicializa com êxito, qualquer excelente do sistema operacional atualizar tarefas podem ser concluídas.</span><span class="sxs-lookup"><span data-stu-id="4b6bb-117">After the Cloud Connector host machine successfully boots up, any outstanding operating system update tasks are completed.</span></span>
    
- <span data-ttu-id="4b6bb-118">Tarefas de atualização do conector na nuvem</span><span class="sxs-lookup"><span data-stu-id="4b6bb-118">Cloud Connector update tasks</span></span>
    
  - <span data-ttu-id="4b6bb-119">Baixe e verifique o arquivo de versão do site de download.</span><span class="sxs-lookup"><span data-stu-id="4b6bb-119">Download and check the version file from the download site.</span></span>
    
  - <span data-ttu-id="4b6bb-120">Baixe a nova versão do arquivo .msi. </span><span class="sxs-lookup"><span data-stu-id="4b6bb-120">Download the new version .msi file.</span></span> 
    
  - <span data-ttu-id="4b6bb-121">Desinstalar o arquivo msi antigo; Instale o novo arquivo msi.</span><span class="sxs-lookup"><span data-stu-id="4b6bb-121">Uninstall the old msi file; install the new msi file.</span></span>
    
  - <span data-ttu-id="4b6bb-122">Baixe a nova versão do Skype para bits de negócios.</span><span class="sxs-lookup"><span data-stu-id="4b6bb-122">Download the new version of Skype for Business bits.</span></span>
    
  - <span data-ttu-id="4b6bb-123">Registre o dispositivo chamando o Register-CcAppliance.</span><span class="sxs-lookup"><span data-stu-id="4b6bb-123">Register the appliance by calling Register-CcAppliance.</span></span>
    
  - <span data-ttu-id="4b6bb-124">Instale a nova versão do conector de nuvem.</span><span class="sxs-lookup"><span data-stu-id="4b6bb-124">Install the new Cloud Connector version.</span></span>
    
  - <span data-ttu-id="4b6bb-125">Esvazie o dispositivo antigo e alterne a conexão da rede para o novo dispositivo.</span><span class="sxs-lookup"><span data-stu-id="4b6bb-125">Drain the old appliance and switch the network connection to the new appliance.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="4b6bb-126">Quando o conector de nuvem atualiza para uma nova compilação, cmdlets de conector de nuvem não pode ser atualizados.</span><span class="sxs-lookup"><span data-stu-id="4b6bb-126">When Cloud Connector updates to a new build, Cloud Connector cmdlets might not be updated.</span></span> <span data-ttu-id="4b6bb-127">Isso pode acontecer, por exemplo, se uma janela do PowerShell permanecerá aberta durante a atualização automática.</span><span class="sxs-lookup"><span data-stu-id="4b6bb-127">This can happen, for example, if a PowerShell window is left open while automatic update occurs.</span></span> <span data-ttu-id="4b6bb-128">Para carregar os cmdlets atualizados, você pode fazer um das seguintes etapas: gt _ PowerShell Close no dispositivo do conector de nuvem e reabra PowerShell.> ou, você pode executar Import-Module CloudConnector-Force.</span><span class="sxs-lookup"><span data-stu-id="4b6bb-128">To load the updated cmdlets, you can do either of the following steps:>  Close PowerShell on the Cloud Connector appliance, and then reopen PowerShell.>  Or, you can run Import-Module CloudConnector -Force.</span></span>
  
## <a name="upgrade-a-single-site-to-a-new-version"></a><span data-ttu-id="4b6bb-129">Atualizar um único site para uma nova versão</span><span class="sxs-lookup"><span data-stu-id="4b6bb-129">Upgrade a single site to a new version</span></span>
<span data-ttu-id="4b6bb-130"><a name="BKMK_Upgrade"> </a></span><span class="sxs-lookup"><span data-stu-id="4b6bb-130"></span></span>

<span data-ttu-id="4b6bb-131">Se existir somente um dispositivo no site que você deseja atualizar, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="4b6bb-131">If there is only one appliance in the site you want to upgrade, do the following:</span></span>
  
1. <span data-ttu-id="4b6bb-132">Desinstalar a versão existente do conector de nuvem em **Painel de controle \> programas \> programas e recursos**.</span><span class="sxs-lookup"><span data-stu-id="4b6bb-132">Uninstall the existing Cloud Connector version in **Control Panel \> Programs \> Programs and Features**.</span></span>
    
2. <span data-ttu-id="4b6bb-133">Instalar a nova versão do CloudConnector.msi do [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller).</span><span class="sxs-lookup"><span data-stu-id="4b6bb-133">Install the new version of CloudConnector.msi from [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller).</span></span>
    
3. <span data-ttu-id="4b6bb-134">Confirme se você tem o arquivo CloudConnector.ini para a versão que está instalando e se atualizou todos os valores necessários para seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="4b6bb-134">Confirm that you have the CloudConnector.ini file for the version you are installing, and that you have updated all of the required values for your environment.</span></span> <span data-ttu-id="4b6bb-135">Você não pode usar o arquivo .ini de uma versão anterior.</span><span class="sxs-lookup"><span data-stu-id="4b6bb-135">You cannot use the .ini file from a previous release.</span></span> <span data-ttu-id="4b6bb-136">Se você estiver atualizando o conector de nuvem, consulte o tópico [Prepare seu aparelho de conector de nuvem](prepare-your-cloud-connector-appliance.md) e certificar-se de que SiteName e EnableReferSupport estão definidos para o valor correto no arquivo CloudConnector.ini.</span><span class="sxs-lookup"><span data-stu-id="4b6bb-136">If you are upgrading Cloud Connector, please refer to the topic [Prepare your Cloud Connector appliance](prepare-your-cloud-connector-appliance.md) and make sure SiteName and EnableReferSupport are set to the correct value in the CloudConnector.ini file.</span></span>
    
4. <span data-ttu-id="4b6bb-137">Inicie um console do PowerShell como administrador e execute o seguinte cmdlet para registrar o dispositivo atual:</span><span class="sxs-lookup"><span data-stu-id="4b6bb-137">Start a PowerShell console as administrator and run the following cmdlet to register the current appliance:</span></span>
    
   ```
   Register-CcAppliance
   ```

5. <span data-ttu-id="4b6bb-138">Execute o seguinte cmdlet para baixar a versão mais recente:</span><span class="sxs-lookup"><span data-stu-id="4b6bb-138">Run the following cmdlet to download the latest version:</span></span>
    
   ```
   Start-CcDownload
   ```

6. <span data-ttu-id="4b6bb-139">Execute o seguinte cmdlet para iniciar a instalação:</span><span class="sxs-lookup"><span data-stu-id="4b6bb-139">Run the following cmdlet to start the installation:</span></span> 
    
   ```
   Install-CcAppliance -Upgrade
   ```

7. <span data-ttu-id="4b6bb-140">Execute o seguinte cmdlet para ativar a nova implantação e desativar a versão anterior.</span><span class="sxs-lookup"><span data-stu-id="4b6bb-140">Run the following cmdlet to activate the new deployment and turn off the previous version:</span></span>
    
   ```
   Switch-CcVersion
   ```

<span data-ttu-id="4b6bb-141">Se existir mais de um dispositivo no site, siga as etapas anteriores para atualizar cada dispositivo individualmente.</span><span class="sxs-lookup"><span data-stu-id="4b6bb-141">If there is more than one appliance in the site, please follow the preceding steps to upgrade each appliance one by one.</span></span>
  
<span data-ttu-id="4b6bb-142">Se você deseja atualizar o administrador de domínio, o administrador da máquina Virtual, o administrador do modo de segurança e credenciais de administrador de locatário, você pode executar o cmdlet com o parâmetro _UpdateAllCredentials_ para redefinir todas as credenciais:</span><span class="sxs-lookup"><span data-stu-id="4b6bb-142">If you want to update Domain administrator, Virtual machine administrator, Safe Mode administrator and Tenant administrator credentials, you can run the cmdlet with the  _UpdateAllCredentials_ parameter to reset all credentials:</span></span>
  
```
Install-CcAppliance -UpdateAllCredentials
```

<span data-ttu-id="4b6bb-143">Posteriormente, quando você iniciar a atualização para uma nova versão, o programa solicitará a entrada das novas credenciais. </span><span class="sxs-lookup"><span data-stu-id="4b6bb-143">Then, when you start to upgrade to a new version, you will be promoted to input the new credentials.</span></span> 
  
<span data-ttu-id="4b6bb-144">Para apenas redefinir as credenciais do administrador de locatários, execute o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="4b6bb-144">If you only want to reset your Tenant administrator credentials, run the following cmdlet:</span></span>
  
```
Set-CcCredential -AccountType TenantAdmin
```

## <a name="upgrade-multiple-sites-to-a-new-version"></a><span data-ttu-id="4b6bb-145">Atualizar vários sites para uma nova versão</span><span class="sxs-lookup"><span data-stu-id="4b6bb-145">Upgrade multiple sites to a new version</span></span>
<span data-ttu-id="4b6bb-146"><a name="BKMK_Upgrade"> </a></span><span class="sxs-lookup"><span data-stu-id="4b6bb-146"></span></span>

<span data-ttu-id="4b6bb-p106">Siga as etapas para a atualização de um único site, atualizando um site de cada vez de sua implantação. Certifique-se de [Validate your Cloud Connector deployment](validate-your-cloud-connector-deployment.md) após atualizar cada site.</span><span class="sxs-lookup"><span data-stu-id="4b6bb-p106">Follow the steps for upgrading a single site, upgrading one site at a time for each site in your deployment. Make sure and [Validate your Cloud Connector deployment](validate-your-cloud-connector-deployment.md) after upgrading each site.</span></span>
  

