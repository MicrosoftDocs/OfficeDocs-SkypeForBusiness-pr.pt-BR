---
title: Implantar um único site no Cloud Connector
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 9/25/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: fa8aa499-1188-447e-bc30-89d1f5b198a7
description: Saiba como implantar um único local de PSTN no Cloud Connector Edition.
ms.openlocfilehash: 389829373d857d587a1fd904932f13a7a321deec
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/04/2018
ms.locfileid: "25375001"
---
# <a name="deploy-a-single-site-in-cloud-connector"></a><span data-ttu-id="4828f-103">Implantar um único site no Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="4828f-103">Deploy a single site in Cloud Connector</span></span>
 
<span data-ttu-id="4828f-104">Saiba como implantar um único local de PSTN no Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="4828f-104">Learn about deploying a single PSTN site in Cloud Connector Edition.</span></span>
  
<span data-ttu-id="4828f-105">Você pode implantar Skype para o conector de nuvem Business Edition com ou sem suporte de alta disponibilidade (HA).</span><span class="sxs-lookup"><span data-stu-id="4828f-105">You can deploy Skype for Business Cloud Connector Edition with or without High Availability (HA) support.</span></span> <span data-ttu-id="4828f-106">Se desejar habilitar alta disponibilidade, você precisará implantar dois ou mais dispositivos em um site.</span><span class="sxs-lookup"><span data-stu-id="4828f-106">If you want to enable HA, you'll need to deploy two or more appliances within a site.</span></span> <span data-ttu-id="4828f-107">Você também pode converter um dispositivo existente para dar suporte à alta disponibilidade após a implantação.</span><span class="sxs-lookup"><span data-stu-id="4828f-107">You can also convert an existing appliance to support HA after it is deployed.</span></span>
  
## <a name="deploy-the-first-skype-for-business-cloud-connector-edition-appliance"></a><span data-ttu-id="4828f-108">Implantar o primeiro dispositivo do Skype for Business Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="4828f-108">Deploy the first Skype for Business Cloud Connector Edition appliance</span></span>

<span data-ttu-id="4828f-109">Para implantar o primeiro dispositivo em um site, abra um console do PowerShell como administrador e execute o seguinte cmdlet para registrar o dispositivo:</span><span class="sxs-lookup"><span data-stu-id="4828f-109">To deploy the first appliance in a site, open a PowerShell console as administrator and run the following cmdlet to register the appliance:</span></span>
  
```
Register-CcAppliance
```

<span data-ttu-id="4828f-p102">Siga as instruções para fornecer o nome e a senha da conta de administrador de locatários. Use a conta que você criou para o gerenciamento online do Cloud Connector. Além disso, siga as instruções para fornecer a senha do certificado externo, a senha do administrador de modo de segurança, a senha do administrador do domínio e a senha do administrador da VM. </span><span class="sxs-lookup"><span data-stu-id="4828f-p102">Follow the instructions to provide the tenant admin account name and password. Use the account you have created for Cloud Connector online management. Also, follow the instructions to provide the external certificate password, safe mode admin password, domain admin password, and VM admin password.</span></span> 
  
<span data-ttu-id="4828f-113">Em versão 1.4.2 e anteriormente, também, siga as instruções para fornecer a senha do certificado externo, senha de admin do modo de segurança, senha de admin do domínio e senha de admin VM.</span><span class="sxs-lookup"><span data-stu-id="4828f-113">In release 1.4.2 and earlier, also follow the instructions to provide the external certificate password, safe mode admin password, domain admin password, and VM admin password.</span></span> 
  
<span data-ttu-id="4828f-114">Na versão 2.0 e posteriores, siga as instruções para fornecer a senha do certificado externo, a senha do CceService e a senha do CABackupFile.</span><span class="sxs-lookup"><span data-stu-id="4828f-114">In release 2.0 and later, also follow the instructions to provide the external certificate password, CceService password and CABackupFile password.</span></span>
  
<span data-ttu-id="4828f-115">Para iniciar a instalação, abra um console do PowerShell como administrador e execute o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="4828f-115">To start the installation, open a PowerShell console as administrator and run the following cmdlet:</span></span>
  
```
Install-CcAppliance
```

## <a name="add-an-appliance-to-an-existing-site"></a><span data-ttu-id="4828f-116">Adicionar um dispositivo a um site existente</span><span class="sxs-lookup"><span data-stu-id="4828f-116">Add an appliance to an existing site</span></span>

<span data-ttu-id="4828f-117">Você pode estender a um site existente do conector de nuvem para oferecer suporte à alta disponibilidade adicionando appliances adicionais para o site.</span><span class="sxs-lookup"><span data-stu-id="4828f-117">You can extend an existing Cloud Connector site to support HA by adding additional appliances to the site.</span></span> 
  
1. <span data-ttu-id="4828f-118">Siga as etapas para preparar seu aparelho de conector de nuvem, conforme descrito em [Prepare seu aparelho de conector de nuvem](prepare-your-cloud-connector-appliance.md).</span><span class="sxs-lookup"><span data-stu-id="4828f-118">Follow the steps to prepare your Cloud Connector appliance as described in [Prepare your Cloud Connector appliance](prepare-your-cloud-connector-appliance.md).</span></span> <span data-ttu-id="4828f-119">Note que algumas etapas são necessárias apenas para o primeiro dispositivo em sua implantação.</span><span class="sxs-lookup"><span data-stu-id="4828f-119">Note that some steps are required only for the first appliance in your deployment.</span></span> <span data-ttu-id="4828f-120">Confirme se o diretório do site existe e se está configurado corretamente para oferecer suporte para alta disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="4828f-120">Confirm that the site directory exists and is correctly configured for HA support.</span></span>
    
2. <span data-ttu-id="4828f-p104">Execute o cmdlet a seguir apenas no servidor host recém-adicionado para atualizar as informações de topologia na configuração do locatário do O365. Se quiser adicionar vários dispositivos ao mesmo tempo, execute o cmdlet em cada servidor host recém-adicionado um a um:</span><span class="sxs-lookup"><span data-stu-id="4828f-p104">Run the following cmdlet only on the newly added host server to update topology information in your Office 365 tenant configuration. If you want to add multiple appliances at the same time, run the cmdlet on each newly added host server one by one:</span></span>
    
   ```
   Register-CcAppliance
   ```

3. <span data-ttu-id="4828f-p105">Atualize a topologia nos dispositivos existentes executando o cmdlet a seguir em cada servidor host. Execute o cmdlet apenas nos dispositivos existentes.</span><span class="sxs-lookup"><span data-stu-id="4828f-p105">Update the topology on existing appliances by running the following cmdlet on each host server. Only run the cmdlet on the existing appliances.</span></span>
    
   ```
   Publish-CcAppliance
   ```

4. <span data-ttu-id="4828f-125">Execute o cmdlet a seguir apenas em servidores host recém-adicionados.</span><span class="sxs-lookup"><span data-stu-id="4828f-125">Run the following cmdlet only on newly added host servers.</span></span> <span data-ttu-id="4828f-126">Não execute esse cmdlet no dispositivo existente.</span><span class="sxs-lookup"><span data-stu-id="4828f-126">Do not run this cmdlet on the existing appliance.</span></span> <span data-ttu-id="4828f-127">Se quiser adicionar vários dispositivos ao mesmo tempo, execute o cmdlet em cada servidor host recém-adicionado um a um.</span><span class="sxs-lookup"><span data-stu-id="4828f-127">If you want to add multiple appliances at the same time, run the cmdlet on each newly added host server one by one.</span></span>
    
   ```
   Install-CcAppliance
   ```

> [!NOTE]
> <span data-ttu-id="4828f-128">Se o diretório de sites estiver configurado como um caminho de pasta local, você precisará definir um compartilhamento de arquivos para essa pasta e usar um caminho UNC para o diretório de sites no novo dispositivo.</span><span class="sxs-lookup"><span data-stu-id="4828f-128">If the site directory was set to a local folder path, you need to define a file share for this folder and use a UNC path for the site directory on the new appliance.</span></span> <span data-ttu-id="4828f-129">Você pode deixar o diretório de sites do primeiro dispositivo com o caminho local ou modificá-lo para usar o caminho UNC para o compartilhamento na mesma pasta.</span><span class="sxs-lookup"><span data-stu-id="4828f-129">You may leave the first appliance site directory with the local path or modify it to use the UNC path for the share to the same folder.</span></span> <span data-ttu-id="4828f-130">Se o local do diretório de sites compartilhado mudar, todos os dispositivos instalados anteriormente precisarão ser desinstalados e reinstalados.</span><span class="sxs-lookup"><span data-stu-id="4828f-130">If the location for the shared site directory changes, any previously-installed appliances need to be uninstalled and then reinstalled.</span></span> <span data-ttu-id="4828f-131">> Importante: A senha para a conta de CceService e a conta de CABackupFile deve ser o mesmo em todos os aparelhos implantados dentro do site, para que os dispositivos que possam acessar o compartilhamento do diretório de site e o arquivo de backup de autoridade de certificação criptografado no diretório de sites.</span><span class="sxs-lookup"><span data-stu-id="4828f-131">> Important: The password for both the CceService account and the CABackupFile account must be the same on all appliances deployed within the site, so that the appliances can access the site directory share and the encrypted CA backup file in the site directory.</span></span> 
  
## <a name="remove-an-appliance-from-an-existing-site"></a><span data-ttu-id="4828f-132">Remover um dispositivo de um site existente</span><span class="sxs-lookup"><span data-stu-id="4828f-132">Remove an appliance from an existing site</span></span>

<span data-ttu-id="4828f-133">Se você deseja remover um dispositivo de um site existente:</span><span class="sxs-lookup"><span data-stu-id="4828f-133">If you want to remove an appliance from an existing site:</span></span>
  
1. <span data-ttu-id="4828f-134">Execute o cmdlet a seguir apenas nos servidores host que você deseja remover do site para atualizar as informações de topologia na configuração do locatário do O365.</span><span class="sxs-lookup"><span data-stu-id="4828f-134">Run the following cmdlet only on the host servers you want to remove from the site to update the topology information in your Office 365 tenant configuration.</span></span>
    
   ```
   Unregister-CcAppliance
   ```

2. <span data-ttu-id="4828f-135">Execute o cmdlet a seguir apenas nos servidores host dos quais você deseja remover todas as máquinas virtuais do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="4828f-135">Run the following cmdlet only on the host servers from which you want to remove all the virtual machines of the appliance.</span></span>
    
   ```
   Uninstall-CcAppliance
   ```


