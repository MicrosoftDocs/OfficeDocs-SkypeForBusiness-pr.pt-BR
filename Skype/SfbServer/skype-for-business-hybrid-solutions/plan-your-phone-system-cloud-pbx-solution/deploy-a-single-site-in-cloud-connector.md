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
description: Saiba como implantar um único site PSTN no Cloud Connector Edition.
ms.openlocfilehash: 327fc4e687377f5f1338bea2f623b526511a2992
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/03/2020
ms.locfileid: "47358927"
---
# <a name="deploy-a-single-site-in-cloud-connector"></a><span data-ttu-id="b513a-103">Implantar um único site no Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="b513a-103">Deploy a single site in Cloud Connector</span></span>
 
> [!Important]
> <span data-ttu-id="b513a-104">O Cloud Connector Edition será destivado em 31 de julho de 2021 junto com o Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="b513a-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="b513a-105">Depois que sua organização tiver atualizado para o Teams, saiba como conectar sua rede de telefonia local ao Teams usando o [Roteamento Direto.](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)</span><span class="sxs-lookup"><span data-stu-id="b513a-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="b513a-106">Saiba como implantar um único site PSTN no Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="b513a-106">Learn about deploying a single PSTN site in Cloud Connector Edition.</span></span>
  
<span data-ttu-id="b513a-107">Você pode implantar o Skype for Business Cloud Connector Edition com ou sem suporte para alta disponibilidade (HA).</span><span class="sxs-lookup"><span data-stu-id="b513a-107">You can deploy Skype for Business Cloud Connector Edition with or without High Availability (HA) support.</span></span> <span data-ttu-id="b513a-108">Se quiser habilitar a habilitar a habilitar, você precisará implantar dois ou mais dispositivos em um site.</span><span class="sxs-lookup"><span data-stu-id="b513a-108">If you want to enable HA, you'll need to deploy two or more appliances within a site.</span></span> <span data-ttu-id="b513a-109">Você também pode converter um dispositivo existente para dar suporte à habilidade após sua implantação.</span><span class="sxs-lookup"><span data-stu-id="b513a-109">You can also convert an existing appliance to support HA after it is deployed.</span></span>
  
## <a name="deploy-the-first-skype-for-business-cloud-connector-edition-appliance"></a><span data-ttu-id="b513a-110">Implantar o primeiro dispositivo do Skype for Business Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="b513a-110">Deploy the first Skype for Business Cloud Connector Edition appliance</span></span>

<span data-ttu-id="b513a-111">Para implantar o primeiro dispositivo em um site, abra um console do PowerShell como administrador e execute o seguinte cmdlet para registrar o dispositivo:</span><span class="sxs-lookup"><span data-stu-id="b513a-111">To deploy the first appliance in a site, open a PowerShell console as administrator and run the following cmdlet to register the appliance:</span></span>
  
```powershell
Register-CcAppliance
```

<span data-ttu-id="b513a-112">Siga as instruções para fornecer o nome e a senha da conta de administrador do locatário.</span><span class="sxs-lookup"><span data-stu-id="b513a-112">Follow the instructions to provide the tenant admin account name and password.</span></span> <span data-ttu-id="b513a-113">Use a conta que você criou para o gerenciamento online do Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="b513a-113">Use the account you have created for Cloud Connector online management.</span></span> <span data-ttu-id="b513a-114">Além disso, siga as instruções para fornecer a senha do certificado externo, a senha do administrador do modo de segurança, a senha do administrador do domínio e a senha do administrador da VM.</span><span class="sxs-lookup"><span data-stu-id="b513a-114">Also, follow the instructions to provide the external certificate password, safe mode admin password, domain admin password, and VM admin password.</span></span> 
  
<span data-ttu-id="b513a-115">Na versão 1.4.2 e anteriores, siga também as instruções para fornecer a senha do certificado externo, a senha do administrador do modo de segurança, a senha do administrador do domínio e a senha do administrador da VM.</span><span class="sxs-lookup"><span data-stu-id="b513a-115">In release 1.4.2 and earlier, also follow the instructions to provide the external certificate password, safe mode admin password, domain admin password, and VM admin password.</span></span> 
  
<span data-ttu-id="b513a-116">Na versão 2.0 e posterior, siga também as instruções para fornecer a senha do certificado externo, a senha do CceService e a senha do CABackupFile.</span><span class="sxs-lookup"><span data-stu-id="b513a-116">In release 2.0 and later, also follow the instructions to provide the external certificate password, CceService password and CABackupFile password.</span></span>
  
<span data-ttu-id="b513a-117">Para iniciar a instalação, abra um console do PowerShell como administrador e execute o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="b513a-117">To start the installation, open a PowerShell console as administrator and run the following cmdlet:</span></span>
  
```powershell
Install-CcAppliance
```

## <a name="add-an-appliance-to-an-existing-site"></a><span data-ttu-id="b513a-118">Adicionar um dispositivo a um site existente</span><span class="sxs-lookup"><span data-stu-id="b513a-118">Add an appliance to an existing site</span></span>

<span data-ttu-id="b513a-119">Você pode estender um site existente do Cloud Connector para dar suporte à habeha adicionando outros dispositivos ao site.</span><span class="sxs-lookup"><span data-stu-id="b513a-119">You can extend an existing Cloud Connector site to support HA by adding additional appliances to the site.</span></span> 
  
1. <span data-ttu-id="b513a-120">Siga as etapas para preparar o dispositivo do Cloud Connector conforme descrito em [Preparar o dispositivo do Cloud Connector.](prepare-your-cloud-connector-appliance.md)</span><span class="sxs-lookup"><span data-stu-id="b513a-120">Follow the steps to prepare your Cloud Connector appliance as described in [Prepare your Cloud Connector appliance](prepare-your-cloud-connector-appliance.md).</span></span> <span data-ttu-id="b513a-121">Observe que algumas etapas são necessárias apenas para o primeiro dispositivo em sua implantação.</span><span class="sxs-lookup"><span data-stu-id="b513a-121">Note that some steps are required only for the first appliance in your deployment.</span></span> <span data-ttu-id="b513a-122">Confirme se o diretório de sites existe e se está configurado corretamente para suporte de ha.ha.</span><span class="sxs-lookup"><span data-stu-id="b513a-122">Confirm that the site directory exists and is correctly configured for HA support.</span></span>
    
2. <span data-ttu-id="b513a-123">Execute o seguinte cmdlet somente no servidor host recém-adicionado para atualizar as informações de topologia na configuração da sua organização do Microsoft 365 ou Office 365.</span><span class="sxs-lookup"><span data-stu-id="b513a-123">Run the following cmdlet only on the newly added host server to update topology information in your Microsoft 365 or Office 365 organization configuration.</span></span> <span data-ttu-id="b513a-124">Se você quiser adicionar vários dispositivos ao mesmo tempo, execute o cmdlet em cada servidor host recém-adicionado um a um:</span><span class="sxs-lookup"><span data-stu-id="b513a-124">If you want to add multiple appliances at the same time, run the cmdlet on each newly added host server one by one:</span></span>
    
   ```powershell
   Register-CcAppliance
   ```

3. <span data-ttu-id="b513a-125">Atualize a topologia em dispositivos existentes executando o seguinte cmdlet em cada servidor host.</span><span class="sxs-lookup"><span data-stu-id="b513a-125">Update the topology on existing appliances by running the following cmdlet on each host server.</span></span> <span data-ttu-id="b513a-126">Execute apenas o cmdlet nos dispositivos existentes.</span><span class="sxs-lookup"><span data-stu-id="b513a-126">Only run the cmdlet on the existing appliances.</span></span>
    
   ```powershell
   Publish-CcAppliance
   ```

4. <span data-ttu-id="b513a-127">Execute o cmdlet a seguir apenas em servidores host recém-adicionados.</span><span class="sxs-lookup"><span data-stu-id="b513a-127">Run the following cmdlet only on newly added host servers.</span></span> <span data-ttu-id="b513a-128">Não execute este cmdlet no dispositivo existente.</span><span class="sxs-lookup"><span data-stu-id="b513a-128">Do not run this cmdlet on the existing appliance.</span></span> <span data-ttu-id="b513a-129">Se você quiser adicionar vários dispositivos ao mesmo tempo, execute o cmdlet em cada servidor host recém-adicionado um a um.</span><span class="sxs-lookup"><span data-stu-id="b513a-129">If you want to add multiple appliances at the same time, run the cmdlet on each newly added host server one by one.</span></span>
    
   ```powershell
   Install-CcAppliance
   ```

> [!NOTE]
> <span data-ttu-id="b513a-130">Se o diretório de sites tiver sido definido como um caminho de pasta local, você precisará definir um compartilhamento de arquivos para essa pasta e usar um caminho UNC para o diretório de sites no novo dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b513a-130">If the site directory was set to a local folder path, you need to define a file share for this folder and use a UNC path for the site directory on the new appliance.</span></span> <span data-ttu-id="b513a-131">Você pode deixar o primeiro diretório de sites de dispositivos com o caminho local ou modificá-lo para usar o caminho UNC para o compartilhamento na mesma pasta.</span><span class="sxs-lookup"><span data-stu-id="b513a-131">You may leave the first appliance site directory with the local path or modify it to use the UNC path for the share to the same folder.</span></span> <span data-ttu-id="b513a-132">Se o local do diretório de sites compartilhado mudar, todos os dispositivos instalados anteriormente precisarão ser desinstalados e reinstalados.</span><span class="sxs-lookup"><span data-stu-id="b513a-132">If the location for the shared site directory changes, any previously-installed appliances need to be uninstalled and then reinstalled.</span></span> <span data-ttu-id="b513a-133">> Importante: a senha da conta CceService e da conta CABackupFile deve ser a mesma em todos os dispositivos implantados no site, para que os dispositivos possam acessar o compartilhamento de diretório do site e o arquivo de backup de CA criptografado no diretório de sites.</span><span class="sxs-lookup"><span data-stu-id="b513a-133">> Important: The password for both the CceService account and the CABackupFile account must be the same on all appliances deployed within the site, so that the appliances can access the site directory share and the encrypted CA backup file in the site directory.</span></span> 
  
## <a name="remove-an-appliance-from-an-existing-site"></a><span data-ttu-id="b513a-134">Remover um dispositivo de um site existente</span><span class="sxs-lookup"><span data-stu-id="b513a-134">Remove an appliance from an existing site</span></span>

<span data-ttu-id="b513a-135">Se você quiser remover um dispositivo de um site existente:</span><span class="sxs-lookup"><span data-stu-id="b513a-135">If you want to remove an appliance from an existing site:</span></span>
  
1. <span data-ttu-id="b513a-136">Execute o cmdlet a seguir apenas nos servidores host que você deseja remover do site para atualizar as informações de topologia na configuração da organização do Microsoft 365 ou Office 365.</span><span class="sxs-lookup"><span data-stu-id="b513a-136">Run the following cmdlet only on the host servers you want to remove from the site to update the topology information in your Microsoft 365 or Office 365 organization configuration.</span></span>
    
   ```powershell
   Unregister-CcAppliance
   ```

2. <span data-ttu-id="b513a-137">Execute o cmdlet a seguir apenas nos servidores host dos quais você deseja remover todas as máquinas virtuais do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b513a-137">Run the following cmdlet only on the host servers from which you want to remove all the virtual machines of the appliance.</span></span>
    
   ```powershell
   Uninstall-CcAppliance
   ```


