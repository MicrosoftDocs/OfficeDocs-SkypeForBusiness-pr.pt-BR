---
title: Implantar um único site no Cloud Connector
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 9/25/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: fa8aa499-1188-447e-bc30-89d1f5b198a7
description: Saiba mais sobre como implantar um único site PSTN no Cloud Connector Edition.
ms.openlocfilehash: 32c981b0f7de3d596dc25c3336000871db9fee65
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094829"
---
# <a name="deploy-a-single-site-in-cloud-connector"></a><span data-ttu-id="bd15a-103">Implantar um único site no Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="bd15a-103">Deploy a single site in Cloud Connector</span></span>
 
> [!Important]
> <span data-ttu-id="bd15a-104">O Cloud Connector Edition se aposentará em 31 de julho de 2021 junto com o Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="bd15a-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="bd15a-105">Depois que sua organização tiver atualizado para o Teams, saiba como conectar sua rede de telefonia local ao Teams usando [Roteamento Direto.](/MicrosoftTeams/direct-routing-landing-page)</span><span class="sxs-lookup"><span data-stu-id="bd15a-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="bd15a-106">Saiba mais sobre como implantar um único site PSTN no Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="bd15a-106">Learn about deploying a single PSTN site in Cloud Connector Edition.</span></span>
  
<span data-ttu-id="bd15a-107">Você pode implantar o Skype for Business Cloud Connector Edition com ou sem suporte a ALTA Disponibilidade (HA).</span><span class="sxs-lookup"><span data-stu-id="bd15a-107">You can deploy Skype for Business Cloud Connector Edition with or without High Availability (HA) support.</span></span> <span data-ttu-id="bd15a-108">Se você quiser habilitar a HA, precisará implantar dois ou mais dispositivos em um site.</span><span class="sxs-lookup"><span data-stu-id="bd15a-108">If you want to enable HA, you'll need to deploy two or more appliances within a site.</span></span> <span data-ttu-id="bd15a-109">Você também pode converter um dispositivo existente para dar suporte a HA depois que ele for implantado.</span><span class="sxs-lookup"><span data-stu-id="bd15a-109">You can also convert an existing appliance to support HA after it is deployed.</span></span>
  
## <a name="deploy-the-first-skype-for-business-cloud-connector-edition-appliance"></a><span data-ttu-id="bd15a-110">Implantar o primeiro dispositivo Skype for Business Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="bd15a-110">Deploy the first Skype for Business Cloud Connector Edition appliance</span></span>

<span data-ttu-id="bd15a-111">Para implantar o primeiro dispositivo em um site, abra um console do PowerShell como administrador e execute o seguinte cmdlet para registrar o dispositivo:</span><span class="sxs-lookup"><span data-stu-id="bd15a-111">To deploy the first appliance in a site, open a PowerShell console as administrator and run the following cmdlet to register the appliance:</span></span>
  
```powershell
Register-CcAppliance
```

<span data-ttu-id="bd15a-112">Siga as instruções para fornecer o nome e a senha da conta de administrador do locatário.</span><span class="sxs-lookup"><span data-stu-id="bd15a-112">Follow the instructions to provide the tenant admin account name and password.</span></span> <span data-ttu-id="bd15a-113">Use a conta que você criou para o gerenciamento online do Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="bd15a-113">Use the account you have created for Cloud Connector online management.</span></span> <span data-ttu-id="bd15a-114">Além disso, siga as instruções para fornecer a senha de certificado externo, senha de administrador de modo seguro, senha de administrador de domínio e senha de administrador de VM.</span><span class="sxs-lookup"><span data-stu-id="bd15a-114">Also, follow the instructions to provide the external certificate password, safe mode admin password, domain admin password, and VM admin password.</span></span> 
  
<span data-ttu-id="bd15a-115">Na versão 1.4.2 e anterior, siga também as instruções para fornecer a senha de certificado externo, senha de administrador de modo seguro, senha de administrador de domínio e senha de administrador de VM.</span><span class="sxs-lookup"><span data-stu-id="bd15a-115">In release 1.4.2 and earlier, also follow the instructions to provide the external certificate password, safe mode admin password, domain admin password, and VM admin password.</span></span> 
  
<span data-ttu-id="bd15a-116">Na versão 2.0 e posterior, siga também as instruções para fornecer a senha de certificado externo, a senha do CceService e a senha caBackupFile.</span><span class="sxs-lookup"><span data-stu-id="bd15a-116">In release 2.0 and later, also follow the instructions to provide the external certificate password, CceService password and CABackupFile password.</span></span>
  
<span data-ttu-id="bd15a-117">Para iniciar a instalação, abra um console do PowerShell como administrador e execute o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="bd15a-117">To start the installation, open a PowerShell console as administrator and run the following cmdlet:</span></span>
  
```powershell
Install-CcAppliance
```

## <a name="add-an-appliance-to-an-existing-site"></a><span data-ttu-id="bd15a-118">Adicionar um dispositivo a um site existente</span><span class="sxs-lookup"><span data-stu-id="bd15a-118">Add an appliance to an existing site</span></span>

<span data-ttu-id="bd15a-119">Você pode estender um site do Cloud Connector existente para dar suporte a HA adicionando dispositivos adicionais ao site.</span><span class="sxs-lookup"><span data-stu-id="bd15a-119">You can extend an existing Cloud Connector site to support HA by adding additional appliances to the site.</span></span> 
  
1. <span data-ttu-id="bd15a-120">Siga as etapas para preparar seu dispositivo do Cloud Connector conforme descrito em [Prepare your Cloud Connector appliance](prepare-your-cloud-connector-appliance.md).</span><span class="sxs-lookup"><span data-stu-id="bd15a-120">Follow the steps to prepare your Cloud Connector appliance as described in [Prepare your Cloud Connector appliance](prepare-your-cloud-connector-appliance.md).</span></span> <span data-ttu-id="bd15a-121">Observe que algumas etapas são necessárias apenas para o primeiro dispositivo em sua implantação.</span><span class="sxs-lookup"><span data-stu-id="bd15a-121">Note that some steps are required only for the first appliance in your deployment.</span></span> <span data-ttu-id="bd15a-122">Confirme se o diretório do site existe e está configurado corretamente para suporte a HA.</span><span class="sxs-lookup"><span data-stu-id="bd15a-122">Confirm that the site directory exists and is correctly configured for HA support.</span></span>
    
2. <span data-ttu-id="bd15a-123">Execute o cmdlet a seguir apenas no servidor host recém-adicionado para atualizar informações de topologia na configuração da organização do Microsoft 365 ou office 365.</span><span class="sxs-lookup"><span data-stu-id="bd15a-123">Run the following cmdlet only on the newly added host server to update topology information in your Microsoft 365 or Office 365 organization configuration.</span></span> <span data-ttu-id="bd15a-124">Se você quiser adicionar vários dispositivos ao mesmo tempo, execute o cmdlet em cada servidor host recém-adicionado um por um:</span><span class="sxs-lookup"><span data-stu-id="bd15a-124">If you want to add multiple appliances at the same time, run the cmdlet on each newly added host server one by one:</span></span>
    
   ```powershell
   Register-CcAppliance
   ```

3. <span data-ttu-id="bd15a-125">Atualize a topologia em dispositivos existentes executando o seguinte cmdlet em cada servidor host.</span><span class="sxs-lookup"><span data-stu-id="bd15a-125">Update the topology on existing appliances by running the following cmdlet on each host server.</span></span> <span data-ttu-id="bd15a-126">Execute apenas o cmdlet nos dispositivos existentes.</span><span class="sxs-lookup"><span data-stu-id="bd15a-126">Only run the cmdlet on the existing appliances.</span></span>
    
   ```powershell
   Publish-CcAppliance
   ```

4. <span data-ttu-id="bd15a-127">Execute o cmdlet a seguir somente em servidores host recém-adicionados.</span><span class="sxs-lookup"><span data-stu-id="bd15a-127">Run the following cmdlet only on newly added host servers.</span></span> <span data-ttu-id="bd15a-128">Não execute este cmdlet no dispositivo existente.</span><span class="sxs-lookup"><span data-stu-id="bd15a-128">Do not run this cmdlet on the existing appliance.</span></span> <span data-ttu-id="bd15a-129">Se você quiser adicionar vários dispositivos ao mesmo tempo, execute o cmdlet em cada servidor host recém-adicionado um por um.</span><span class="sxs-lookup"><span data-stu-id="bd15a-129">If you want to add multiple appliances at the same time, run the cmdlet on each newly added host server one by one.</span></span>
    
   ```powershell
   Install-CcAppliance
   ```

> [!NOTE]
> <span data-ttu-id="bd15a-130">Se o diretório do site foi definido como um caminho de pasta local, você precisará definir um compartilhamento de arquivos para essa pasta e usar um caminho UNC para o diretório do site no novo dispositivo.</span><span class="sxs-lookup"><span data-stu-id="bd15a-130">If the site directory was set to a local folder path, you need to define a file share for this folder and use a UNC path for the site directory on the new appliance.</span></span> <span data-ttu-id="bd15a-131">Você pode deixar o primeiro diretório de site do dispositivo com o caminho local ou modificá-lo para usar o caminho UNC para o compartilhamento na mesma pasta.</span><span class="sxs-lookup"><span data-stu-id="bd15a-131">You may leave the first appliance site directory with the local path or modify it to use the UNC path for the share to the same folder.</span></span> <span data-ttu-id="bd15a-132">Se o local do diretório de site compartilhado mudar, todos os dispositivos instalados anteriormente precisarão ser desinstalados e reinstalados.</span><span class="sxs-lookup"><span data-stu-id="bd15a-132">If the location for the shared site directory changes, any previously-installed appliances need to be uninstalled and then reinstalled.</span></span> <span data-ttu-id="bd15a-133">> Importante: a senha da conta CceService e da conta CABackupFile deve ser a mesma em todos os dispositivos implantados no site, para que os dispositivos possam acessar o compartilhamento de diretório do site e o arquivo de backup de CA criptografado no diretório do site.</span><span class="sxs-lookup"><span data-stu-id="bd15a-133">> Important: The password for both the CceService account and the CABackupFile account must be the same on all appliances deployed within the site, so that the appliances can access the site directory share and the encrypted CA backup file in the site directory.</span></span> 
  
## <a name="remove-an-appliance-from-an-existing-site"></a><span data-ttu-id="bd15a-134">Remover um dispositivo de um site existente</span><span class="sxs-lookup"><span data-stu-id="bd15a-134">Remove an appliance from an existing site</span></span>

<span data-ttu-id="bd15a-135">Se você quiser remover um dispositivo de um site existente:</span><span class="sxs-lookup"><span data-stu-id="bd15a-135">If you want to remove an appliance from an existing site:</span></span>
  
1. <span data-ttu-id="bd15a-136">Execute o cmdlet a seguir somente nos servidores host que você deseja remover do site para atualizar as informações de topologia em sua configuração da organização do Microsoft 365 ou Office 365.</span><span class="sxs-lookup"><span data-stu-id="bd15a-136">Run the following cmdlet only on the host servers you want to remove from the site to update the topology information in your Microsoft 365 or Office 365 organization configuration.</span></span>
    
   ```powershell
   Unregister-CcAppliance
   ```

2. <span data-ttu-id="bd15a-137">Execute o cmdlet a seguir somente nos servidores host dos quais você deseja remover todas as máquinas virtuais do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="bd15a-137">Run the following cmdlet only on the host servers from which you want to remove all the virtual machines of the appliance.</span></span>
    
   ```powershell
   Uninstall-CcAppliance
   ```