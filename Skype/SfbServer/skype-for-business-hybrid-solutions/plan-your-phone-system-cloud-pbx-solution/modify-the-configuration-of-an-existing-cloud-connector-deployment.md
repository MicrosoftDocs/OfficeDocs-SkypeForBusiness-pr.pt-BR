---
title: Modificar a configuração de uma implantação do Cloud Connector existente
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 90490c65-0e40-4e85-96e1-751f27897e25
description: Siga as etapas neste tópico para modificar a configuração de uma implantação existente do Skype for Business Cloud Connector Edition 1.4.1 ou posterior.
ms.openlocfilehash: 2d70dfa9e25a0c89a31e25699e67a21f14e4f097
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359107"
---
# <a name="modify-the-configuration-of-an-existing-cloud-connector-deployment"></a><span data-ttu-id="9b6e4-103">Modificar a configuração de uma implantação do Cloud Connector existente</span><span class="sxs-lookup"><span data-stu-id="9b6e4-103">Modify the configuration of an existing Cloud Connector deployment</span></span>

> [!Important]
> <span data-ttu-id="9b6e4-104">O Cloud Connector Edition vai retirar 31 de julho de 2021 junto com o Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="9b6e4-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="9b6e4-105">Depois que sua organização tiver atualizado para o Microsoft Teams, saiba como conectar sua rede de telefonia local ao Microsoft Teams usando o [Roteamento direto](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span><span class="sxs-lookup"><span data-stu-id="9b6e4-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="9b6e4-106">Siga as etapas neste tópico para modificar a configuração de uma implantação existente do Skype for Business Cloud Connector Edition 1.4.1 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="9b6e4-106">Follow the steps in this topic to modify the configuration of an existing Skype for Business Cloud Connector Edition 1.4.1 or later deployment.</span></span> 
  
## <a name="modify-the-configuration-of-a-single-site"></a><span data-ttu-id="9b6e4-107">Modificar a configuração de um único site</span><span class="sxs-lookup"><span data-stu-id="9b6e4-107">Modify the configuration of a single site</span></span>
<span data-ttu-id="9b6e4-108"><a name="BKMK_SIngleSite"> </a></span><span class="sxs-lookup"><span data-stu-id="9b6e4-108"><a name="BKMK_SIngleSite"> </a></span></span>

<span data-ttu-id="9b6e4-109">Se houver apenas um dispositivo no site, quando você quiser alterar as definições de configuração depois que o dispositivo for implantado, você poderá modificar o arquivo de CloudConnector.ini e iniciar a implantação novamente.</span><span class="sxs-lookup"><span data-stu-id="9b6e4-109">If there is only one appliance in the site, when you want to change the configuration settings after the appliance is deployed, you can modify the CloudConnector.ini file and start the deployment again.</span></span>
  
1. <span data-ttu-id="9b6e4-110">Execute o seguinte cmdlet para desinstalar todas as máquinas virtuais existentes no servidor host:</span><span class="sxs-lookup"><span data-stu-id="9b6e4-110">Run the following cmdlet to uninstall all existing virtual machines on the host server:</span></span> 
    
   ```powershell
   Uninstall-CcAppliance
   ```

2. <span data-ttu-id="9b6e4-111">Execute o seguinte cmdlet para cancelar o registro do dispositivo:</span><span class="sxs-lookup"><span data-stu-id="9b6e4-111">Run the following cmdlet to unregister the appliance:</span></span>
    
   ```powershell
   Unregister-CcAppliance
   ```

3. <span data-ttu-id="9b6e4-112">Atualize o arquivo de CloudConnector.ini no diretório de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="9b6e4-112">Update the CloudConnector.ini file in the Appliance Directory.</span></span>
    
4. <span data-ttu-id="9b6e4-113">Execute o seguinte cmdlet para atualizar a configuração: (esta etapa só é aplicável para a versão 2; para versões anteriores, pule para a próxima etapa.)</span><span class="sxs-lookup"><span data-stu-id="9b6e4-113">Run the following cmdlet to update the configuration: (This step is only applicable for version 2; for previous versions, skip to the next step.)</span></span>
    
   ```powershell
   Import-CcConfiguration 
   ```

5. <span data-ttu-id="9b6e4-114">Execute o seguinte cmdlet para registrar o dispositivo novamente:</span><span class="sxs-lookup"><span data-stu-id="9b6e4-114">Run the following cmdlet to register the appliance again:</span></span>
    
   ```powershell
   Register-CcAppliance
   ```

6. <span data-ttu-id="9b6e4-115">Execute o cmdlet a seguir para instalar o Skype for Business Cloud Connector Edition:</span><span class="sxs-lookup"><span data-stu-id="9b6e4-115">Run the following cmdlet to install Skype for Business Cloud Connector Edition:</span></span>
    
   ```powershell
   Install-CcAppliance
   ```

<span data-ttu-id="9b6e4-116">Se houver mais de um dispositivo no site, você precisará seguir estas etapas, modificar o arquivo CloudConnector.ini e reimplantar os dispositivos um por um.</span><span class="sxs-lookup"><span data-stu-id="9b6e4-116">If there is more than one appliance in the site, you'll need to follow these steps, modify the CloudConnector.ini file, and redeploy the appliances one by one.</span></span>
  
1. <span data-ttu-id="9b6e4-117">Execute o seguinte cmdlet para desinstalar todas as máquinas virtuais existentes no dispositivo atual:</span><span class="sxs-lookup"><span data-stu-id="9b6e4-117">Run the following cmdlet to uninstall all existing virtual machines on the current appliance:</span></span> 
    
   ```powershell
   Uninstall-CcAppliance
   ```

2. <span data-ttu-id="9b6e4-118">Execute o seguinte cmdlet para cancelar o registro do dispositivo:</span><span class="sxs-lookup"><span data-stu-id="9b6e4-118">Run the following cmdlet to unregister the appliance:</span></span>
    
   ```powershell
   Unregister-CcAppliance
   ```

3. <span data-ttu-id="9b6e4-119">Atualize o arquivo de CloudConnector.ini no diretório de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="9b6e4-119">Update the CloudConnector.ini file in the Appliance Directory.</span></span>
    
4. <span data-ttu-id="9b6e4-120">Execute o seguinte cmdlet para atualizar a configuração: (esta etapa só é aplicável para a versão 2; para versões anteriores, pule para a próxima etapa.)</span><span class="sxs-lookup"><span data-stu-id="9b6e4-120">Run the following cmdlet to update the configuration: (This step is only applicable for version 2; for previous versions, skip to the next step.)</span></span>
    
   ```powershell
   Import-CcConfiguration 
   ```

5. <span data-ttu-id="9b6e4-121">Execute o seguinte cmdlet para registrar o dispositivo novamente:</span><span class="sxs-lookup"><span data-stu-id="9b6e4-121">Run the following cmdlet to register the appliance again:</span></span>
    
   ```powershell
   Register-CcAppliance
   ```

6. <span data-ttu-id="9b6e4-122">Execute o cmdlet a seguir em todos os outros dispositivos no site para selecionar a configuração mais recente:</span><span class="sxs-lookup"><span data-stu-id="9b6e4-122">Run the following cmdlet on all other appliances in the site to pick up the latest configuration:</span></span>
    
   ```powershell
   Publish-CcAppliance
   ```

7. <span data-ttu-id="9b6e4-123">Execute o seguinte cmdlet para reimplantar o Cloud Connector no dispositivo atual:</span><span class="sxs-lookup"><span data-stu-id="9b6e4-123">Run the following cmdlet to redeploy Cloud Connector on the current appliance:</span></span>
    
   ```powershell
   Install-CcAppliance
   ```

## <a name="modify-the-configuration-of-multiple-sites"></a><span data-ttu-id="9b6e4-124">Modificar a configuração de vários sites</span><span class="sxs-lookup"><span data-stu-id="9b6e4-124">Modify the configuration of multiple sites</span></span>
<span data-ttu-id="9b6e4-125"><a name="BKMK_MultipleSites"> </a></span><span class="sxs-lookup"><span data-stu-id="9b6e4-125"><a name="BKMK_MultipleSites"> </a></span></span>

<span data-ttu-id="9b6e4-126">Para modificar a configuração de vários sites em uma implantação, siga as etapas de um único site, atualizando um site de cada vez.</span><span class="sxs-lookup"><span data-stu-id="9b6e4-126">To modify the configuration for multiple sites in a deployment, follow the steps for a single site, updating one site at a time.</span></span>
  
## <a name="modify-the-configuration-of-your-microsoft-365-or-office-365-organization-to-enable-automatic-updates"></a><span data-ttu-id="9b6e4-127">Modificar a configuração da sua organização do Microsoft 365 ou do Office 365 para habilitar atualizações automáticas</span><span class="sxs-lookup"><span data-stu-id="9b6e4-127">Modify the configuration of your Microsoft 365 or Office 365 organization to enable automatic updates</span></span>
<span data-ttu-id="9b6e4-128"><a name="BKMK_MultipleSites"> </a></span><span class="sxs-lookup"><span data-stu-id="9b6e4-128"><a name="BKMK_MultipleSites"> </a></span></span>

<span data-ttu-id="9b6e4-129">Para habilitar as atualizações automáticas do sistema operacional e as atualizações automáticas do bits, você deve usar a conta de administrador locatário do Skype for Business para gerenciamento online e usar o PowerShell remoto do locatário, da seguinte maneira.</span><span class="sxs-lookup"><span data-stu-id="9b6e4-129">To enable operating system automatic updates and Bits automatic updates, you must use the Skype for Business tenant admin account for online management and use tenant remote PowerShell as follows.</span></span>
  
<span data-ttu-id="9b6e4-130">Se você desabilitou as atualizações automáticas do sistema operacional ou as atualizações automáticas do bits, o host e a máquina virtual poderão perder atualizações importantes do Windows e o Cloud Connector não será atualizado para a nova versão automaticamente.</span><span class="sxs-lookup"><span data-stu-id="9b6e4-130">If you disabled operating system automatic updates or Bits automatic updates, your host and virtual machine may miss important Windows updates, and Cloud Connector will not upgrade to the new version automatically.</span></span> <span data-ttu-id="9b6e4-131">É altamente recomendável que você habilite as atualizações automáticas.</span><span class="sxs-lookup"><span data-stu-id="9b6e4-131">It is highly recommended that you enable automatic updates.</span></span>
  
1. <span data-ttu-id="9b6e4-132">A propriedade EnableAutoUpdate do site precisa ser definida como true (o valor padrão).</span><span class="sxs-lookup"><span data-stu-id="9b6e4-132">The EnableAutoUpdate property of the site needs to be set to true (the default value).</span></span> <span data-ttu-id="9b6e4-133">Execute o cmdlet a seguir para certificar-se de que EnableAutoUpdate está definido como true:</span><span class="sxs-lookup"><span data-stu-id="9b6e4-133">Run the following cmdlet to make sure EnableAutoUpdate is set to true:</span></span>
    
   ```powershell
   Get-CsHybridPSTNSite -Identity <SiteName>
   ```

2. <span data-ttu-id="9b6e4-134">Crie a janela de tempo de atualização automática para o locatário.</span><span class="sxs-lookup"><span data-stu-id="9b6e4-134">Create auto update time window for the tenant.</span></span>
    
    <span data-ttu-id="9b6e4-135">A janela de tempo pode ser diária, semanal e mensal.</span><span class="sxs-lookup"><span data-stu-id="9b6e4-135">The time window can be daily, weekly and monthly.</span></span> <span data-ttu-id="9b6e4-136">Todas as janelas de tempo precisam de um horário de início e uma duração.</span><span class="sxs-lookup"><span data-stu-id="9b6e4-136">All the time windows need a start time and a duration.</span></span>
    
   - <span data-ttu-id="9b6e4-137">Para uma janela de tempo diária, apenas a hora de início e a duração são necessárias.</span><span class="sxs-lookup"><span data-stu-id="9b6e4-137">For a daily time window, only start time and duration are needed.</span></span> 
    
   - <span data-ttu-id="9b6e4-138">Para uma janela de tempo semanal, os dias da semana são necessários, que podem ser um único dia ou vários dias.</span><span class="sxs-lookup"><span data-stu-id="9b6e4-138">For a weekly time window, days of week are needed, which can be a single day or multiple days.</span></span>
    
   - <span data-ttu-id="9b6e4-139">Para uma janela de tempo mensal, pode haver dois tipos.</span><span class="sxs-lookup"><span data-stu-id="9b6e4-139">For a monthly time window, there can be two types.</span></span> <span data-ttu-id="9b6e4-140">O primeiro tipo é especificar o dia do mês, que pode ser um único dia.</span><span class="sxs-lookup"><span data-stu-id="9b6e4-140">The first type is to specify the day of the month, which can be a single day.</span></span> <span data-ttu-id="9b6e4-141">O segundo tipo é especificar as semanas do mês, junto com os dias da semana, que podem ser um único item ou vários itens.</span><span class="sxs-lookup"><span data-stu-id="9b6e4-141">The second type is to specify the weeks of the month, along with days of the week, which both can be a single item or multiple items.</span></span>
    
   - <span data-ttu-id="9b6e4-142">Cada locatário pode ter 20 janelas de tempo definidas.</span><span class="sxs-lookup"><span data-stu-id="9b6e4-142">Each tenant can have 20 time windows defined.</span></span> <span data-ttu-id="9b6e4-143">A janela de tempo padrão será criada para um novo locatário como a janela de tempo padrão para atualização do sistema operacional e atualização de bits.</span><span class="sxs-lookup"><span data-stu-id="9b6e4-143">The default time window will be created for a new tenant as the default time window for operating system update and Bits update.</span></span> <span data-ttu-id="9b6e4-144">Execute os seguintes cmdlets para definir a janela de tempo diária, semanal ou mensal:</span><span class="sxs-lookup"><span data-stu-id="9b6e4-144">Run the following cmdlet(s) to set the daily, weekly or monthly time window:</span></span>
    
   ```powershell
   New-CsTenantUpdateTimeWindow -Identity Night -Daily -StartTime 22:00 -Duration 6:00
   ```

   ```powershell
   New-CsTenantUpdateTimeWindow -Identity WeekdayNight -Weekly -DaysOfWeek Monday,Tuesday,Wednesday,Thursday,Friday -StartTime 22:00 -Duration 4:00
   ```

   ```powershell
   New-CsTenantUpdateTimeWindow -Identity FirstAndLastWeekend -Monthly -WeeksOfMonth First,Last -DaysOfWeek Sunday,Saturday -StartTime 0:00 -Duration 10:00
   ```

   ```powershell
   New-CsTenantUpdateTimeWindow -Identity MidDayOfMonth -Monthly -DayOfMonth 15 -StartTime 0:00 -Duration 1.00:00
   ```

   - <span data-ttu-id="9b6e4-145">Atribuir janelas de tempo de atualização ao site.</span><span class="sxs-lookup"><span data-stu-id="9b6e4-145">Assign update time windows to the site.</span></span> 
    
     <span data-ttu-id="9b6e4-146">O tempo de atualização do bits e as janelas de tempo de atualização de so são configurados separadamente.</span><span class="sxs-lookup"><span data-stu-id="9b6e4-146">The Bits update time and OS update time windows are configured separately.</span></span> <span data-ttu-id="9b6e4-147">Ambas podem ser atribuídas a uma única ou várias janelas de tempo.</span><span class="sxs-lookup"><span data-stu-id="9b6e4-147">Both of them can be assigned single or multiple time windows.</span></span> <span data-ttu-id="9b6e4-148">Cada janela de tempo pode ser atribuída a diferentes sites e objetivos diferentes (atualização de bits e atualização de so).</span><span class="sxs-lookup"><span data-stu-id="9b6e4-148">Each time window can be assigned to different sites and different purpose (Bits update and OS update).</span></span> <span data-ttu-id="9b6e4-149">Execute o seguinte cmdlet para definir a janela de tempo do site:</span><span class="sxs-lookup"><span data-stu-id="9b6e4-149">Run the following cmdlet to set the time window for the site:</span></span> 
    
   ```powershell
   Set-CsHybridPSTNSite -Identity <SiteName> -BitsUpdateTimeWindow @{add="MidDayOfMonth","WeekdayNight"} -OsUpdateTimeWindow @{replace="Night"}
   ```

## <a name="update-the-dedicated-tenant-admin-credentials"></a><span data-ttu-id="9b6e4-150">Atualizar as credenciais de administrador de locatários dedicados</span><span class="sxs-lookup"><span data-stu-id="9b6e4-150">Update the dedicated tenant admin credentials</span></span>
<span data-ttu-id="9b6e4-151"><a name="BKMK_MultipleSites"> </a></span><span class="sxs-lookup"><span data-stu-id="9b6e4-151"><a name="BKMK_MultipleSites"> </a></span></span>

<span data-ttu-id="9b6e4-152">Alterações administrativas na organização do Microsoft 365 ou do Office 365 para o Cloud Connector são feitas de uma conta com as permissões necessárias.</span><span class="sxs-lookup"><span data-stu-id="9b6e4-152">Administrative changes in the Microsoft 365 or Office 365 organization for Cloud Connector are made from an account with the needed permissions.</span></span> <span data-ttu-id="9b6e4-153">Nas versões do Cloud Connector anteriores a 2,0, essa conta é uma conta de administrador de locatário global dedicado.</span><span class="sxs-lookup"><span data-stu-id="9b6e4-153">In Cloud Connector versions before 2.0, that account is a dedicated global tenant admin account.</span></span> <span data-ttu-id="9b6e4-154">Nas versões 2,0 e posteriores do Cloud Connector, essa conta pode ser uma conta do Microsoft 365 ou do Office 365 com direitos de administrador do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="9b6e4-154">In Cloud Connector versions 2.0 and later, that account can be a Microsoft 365 or Office 365 account with Skype for Business Administrator rights.</span></span>
  
<span data-ttu-id="9b6e4-155">Se as suas credenciais de conta de administrador forem alteradas no Microsoft 365 ou no Office 365, você também precisará atualizar as credenciais armazenadas em cache localmente no Cloud Connector executando o seguinte comando do PowerShell do administrador em cada dispositivo do Cloud Connector implantado:</span><span class="sxs-lookup"><span data-stu-id="9b6e4-155">If your admin account credentials change in Microsoft 365 or Office 365, you also need to update the locally cached credentials in Cloud Connector by running the following Administrator PowerShell command on each Cloud Connector appliance you have deployed:</span></span>
  
```powershell
Set-CcCredential -AccountType TenantAdmin
```

## <a name="update-the-password-for-the-host-server"></a><span data-ttu-id="9b6e4-156">Atualizar a senha do servidor host</span><span class="sxs-lookup"><span data-stu-id="9b6e4-156">Update the password for the host server</span></span>
<span data-ttu-id="9b6e4-157"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="9b6e4-157"><a name="BKMK_UpdatePassword"> </a></span></span>

> [!NOTE]
> <span data-ttu-id="9b6e4-158">Esta seção é aplicável para o Cloud Connector versão 2,0 e posterior.</span><span class="sxs-lookup"><span data-stu-id="9b6e4-158">This section is applicable to Cloud Connector version 2.0 and later.</span></span> 
  
<span data-ttu-id="9b6e4-159">Todas as credenciais do Cloud Connector são armazenadas no seguinte arquivo: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\> . XML ".</span><span class="sxs-lookup"><span data-stu-id="9b6e4-159">All Cloud Connector credentials are stored in the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span> <span data-ttu-id="9b6e4-160">Quando a senha no servidor host for alterada, será necessário atualizar as credenciais armazenadas localmente.</span><span class="sxs-lookup"><span data-stu-id="9b6e4-160">When the password on the host server changes, you will need to update the locally stored credentials.</span></span>
  
<span data-ttu-id="9b6e4-161">Para atualizar as credenciais armazenadas localmente no dispositivo do Cloud Connector, use os cmdlets [Get-CcCredential](get-cccredential.md) e [set-CcCredential](set-cccredential.md) e siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="9b6e4-161">To update the locally stored credentials on the Cloud Connector appliance, use the [Get-CcCredential](get-cccredential.md) and [Set-CcCredential](set-cccredential.md) cmdlets and follow these steps:</span></span>
  
1. <span data-ttu-id="9b6e4-162">Execute os seguintes comandos para recuperar as senhas que você precisará mais tarde:</span><span class="sxs-lookup"><span data-stu-id="9b6e4-162">Run the following commands to retrieve the passwords you will need later:</span></span> 
    
   - <span data-ttu-id="9b6e4-163">Get-CcCredential-AccountType DomainAdmin-DisplayPassword</span><span class="sxs-lookup"><span data-stu-id="9b6e4-163">Get-CcCredential -AccountType DomainAdmin -DisplayPassword</span></span>
    
   - <span data-ttu-id="9b6e4-164">Get-CcCredential-AccountType VMAdmin-DisplayPassword</span><span class="sxs-lookup"><span data-stu-id="9b6e4-164">Get-CcCredential -AccountType VMAdmin -DisplayPassword</span></span>
    
   - <span data-ttu-id="9b6e4-165">Get-CcCredential-AccountType CceService-DisplayPassword</span><span class="sxs-lookup"><span data-stu-id="9b6e4-165">Get-CcCredential -AccountType CceService -DisplayPassword</span></span>
    
2. <span data-ttu-id="9b6e4-166">Altere a senha da sua conta no servidor host.</span><span class="sxs-lookup"><span data-stu-id="9b6e4-166">Change the password of your account on the host server.</span></span>
    
3. <span data-ttu-id="9b6e4-167">Reinicie o servidor host.</span><span class="sxs-lookup"><span data-stu-id="9b6e4-167">Restart the host server.</span></span>
    
4. <span data-ttu-id="9b6e4-168">Exclua o seguinte arquivo: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\> . XML ".</span><span class="sxs-lookup"><span data-stu-id="9b6e4-168">Delete the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span>
    
5. <span data-ttu-id="9b6e4-169">Inicie um console do PowerShell como administrador e execute "Register-CcAppliance-local" para reinserir as senhas após a descrição.</span><span class="sxs-lookup"><span data-stu-id="9b6e4-169">Launch a PowerShell console as administrator, and then run "Register-CcAppliance -Local" to re-enter the passwords following the description.</span></span> <span data-ttu-id="9b6e4-170">Certifique-se de inserir a mesma senha que você inseriu anteriormente para a implantação do Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="9b6e4-170">Be sure you enter the same password you entered before for the Cloud Connector deployment.</span></span>
    
<span data-ttu-id="9b6e4-171">Por padrão, VmAdmin e DomainAdmin usam a mesma senha que CceService.</span><span class="sxs-lookup"><span data-stu-id="9b6e4-171">By default, VmAdmin and DomainAdmin use the same password as CceService.</span></span> <span data-ttu-id="9b6e4-172">Se as senhas DomainAdmin, VMAdmin e CceService retornadas na etapa 1 forem diferentes, você deverá executar as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="9b6e4-172">If the DomainAdmin, VMAdmin, and CceService passwords returned in step 1 are different, you must perform the following steps:</span></span>
  
1. <span data-ttu-id="9b6e4-173">Execute Set-CcCredential-AccountType DomainAdmin da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="9b6e4-173">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
1. <span data-ttu-id="9b6e4-174">Quando for solicitada a credencial antiga da conta, insira a credencial que você usou para a senha do CceService.</span><span class="sxs-lookup"><span data-stu-id="9b6e4-174">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
2. <span data-ttu-id="9b6e4-175">Quando for solicitada a nova credencial da conta, insira a senha da senha do DomainAdmin retornada na etapa 1.</span><span class="sxs-lookup"><span data-stu-id="9b6e4-175">When prompted for the new account credential, enter the password for the DomainAdmin password returned in step 1.</span></span>
    
2. <span data-ttu-id="9b6e4-176">Execute Set-CcCredential-AccountType VmAdmin da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="9b6e4-176">Run Set-CcCredential -AccountType VmAdmin as follows:</span></span>
    
1. <span data-ttu-id="9b6e4-177">Quando for solicitada a credencial antiga da conta, insira a credencial que você usou para a senha do CceService.</span><span class="sxs-lookup"><span data-stu-id="9b6e4-177">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
2. <span data-ttu-id="9b6e4-178">Quando for solicitada a nova credencial da conta, insira a senha da senha do VmAdmin retornada na etapa 1.</span><span class="sxs-lookup"><span data-stu-id="9b6e4-178">When prompted for the new account credential, enter the password for the VmAdmin password returned in step 1.</span></span> 
    
## <a name="update-the-password-for-the-cceservice-account"></a><span data-ttu-id="9b6e4-179">Atualizar a senha da conta CceService</span><span class="sxs-lookup"><span data-stu-id="9b6e4-179">Update the password for the CceService account</span></span>
<span data-ttu-id="9b6e4-180"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="9b6e4-180"><a name="BKMK_UpdatePassword"> </a></span></span>

> [!NOTE]
> <span data-ttu-id="9b6e4-181">Esta seção é aplicável ao Cloud Connector versão 2.0.1 e posterior.</span><span class="sxs-lookup"><span data-stu-id="9b6e4-181">This section is applicable to Cloud Connector version 2.0.1 and later.</span></span> 
  
<span data-ttu-id="9b6e4-182">O serviço do Cloud Connector executa o serviço de gerenciamento do Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="9b6e4-182">The Cloud Connector service runs the Cloud Connector Management service.</span></span> <span data-ttu-id="9b6e4-183">A conta CceService é criada durante a implantação do Cloud Connector Edition e armazenada nos seguintes arquivos: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\> . XML "e"% SystemDrive% \Programdata\Cloudconnector\credentials..CceService.xml ".</span><span class="sxs-lookup"><span data-stu-id="9b6e4-183">The CceService account is created during the Cloud Connector Edition deployment and stored in the following files: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml" and "%SystemDrive%\Programdata\Cloudconnector\credentials..CceService.xml".</span></span>
  
<span data-ttu-id="9b6e4-184">Para garantir que todos os dispositivos possam acessar o compartilhamento de diretório de site, a senha da conta CceService deve ser a mesma em todos os dispositivos implantados no site.</span><span class="sxs-lookup"><span data-stu-id="9b6e4-184">To ensure that all appliances can access the site directory share, the password for the CceService account must be the same on all appliances deployed within the site.</span></span> <span data-ttu-id="9b6e4-185">Lembre-se do seguinte:</span><span class="sxs-lookup"><span data-stu-id="9b6e4-185">Keep the following in mind:</span></span>
  
- <span data-ttu-id="9b6e4-186">Por padrão, a conta CceService é configurada como "a senha nunca expira".</span><span class="sxs-lookup"><span data-stu-id="9b6e4-186">By default, the CceService account is configured as "Password never expires".</span></span> <span data-ttu-id="9b6e4-187">Ao atualizar a senha, a Microsoft recomenda manter essa configuração.</span><span class="sxs-lookup"><span data-stu-id="9b6e4-187">When you update the password, Microsoft recommends keeping this configuration.</span></span>
    
- <span data-ttu-id="9b6e4-188">Você deve atualizar a senha durante períodos de uso sem pico e fora das janelas de tempo de atualização automática para bits ou atualizações do Windows.</span><span class="sxs-lookup"><span data-stu-id="9b6e4-188">You should update the password during non-peak usage periods and outside of automatic update time windows for bits or Windows updates.</span></span> <span data-ttu-id="9b6e4-189">Ao atualizar a senha, o dispositivo precisa ser esvaziado e reiniciado, o que leva algum tempo.</span><span class="sxs-lookup"><span data-stu-id="9b6e4-189">When you update the password, the appliance needs to be drained and restarted, which takes some time.</span></span> <span data-ttu-id="9b6e4-190">Reiniciar o dispositivo interromperá as operações de atualização automática.</span><span class="sxs-lookup"><span data-stu-id="9b6e4-190">Restarting the appliance will interrupt automatic update operations.</span></span> 
    
- <span data-ttu-id="9b6e4-191">Ao alterar a senha da conta CceService, será necessário especificar todas as credenciais e atualizá-las no arquivo armazenado localmente.</span><span class="sxs-lookup"><span data-stu-id="9b6e4-191">When you change the CceService account password, you will need to specify all the credentials and update them in the locally stored file.</span></span> 
    
<span data-ttu-id="9b6e4-192">Para cada dispositivo que pertença ao mesmo site PSTN, será necessário especificar o seguinte:</span><span class="sxs-lookup"><span data-stu-id="9b6e4-192">For each appliance that belongs to the same PSTN site, you will need to specify the following:</span></span> 
  
1. <span data-ttu-id="9b6e4-193">Execute os seguintes comandos para recuperar os nomes de conta e senhas que você usará posteriormente:</span><span class="sxs-lookup"><span data-stu-id="9b6e4-193">Run the following commands to retrieve the account names and passwords that you will use later:</span></span>
    
   ```powershell
   Get-CcCredential -AccountType TenantAdmin -DisplayPassword
   Get-CcCredential -AccountType TenantAdmin
   Get-CcCredential -AccountType OMSWorkspace -DisplayPassword
   Get-CcCredential -AccountType OMSWorkspace 
   Get-CcCredential -AccountType ExternalCert -DisplayPassword
   Get-CcCredential -AccountType CABackupFile -DisplayPassword
   Get-CcCredential -AccountType CceService -DisplayPassword
   Get-CcCredential -AccountType VMAdmin -DisplayPassword
   Get-CcCredential -AccountType DomainAdmin -DisplayPassword
   ```

2. <span data-ttu-id="9b6e4-194">Execute o cmdlet Enter-CcUpdate para drenar o dispositivo e movê-lo para o modo de manutenção manual.</span><span class="sxs-lookup"><span data-stu-id="9b6e4-194">Run the Enter-CcUpdate cmdlet to drain the appliance and move it into manual maintenance mode.</span></span>
    
3. <span data-ttu-id="9b6e4-195">Atualize a senha da conta CceService no servidor host.</span><span class="sxs-lookup"><span data-stu-id="9b6e4-195">Update the password of the CceService account on the host server.</span></span>
    
4. <span data-ttu-id="9b6e4-196">Reinicie o servidor host.</span><span class="sxs-lookup"><span data-stu-id="9b6e4-196">Restart the host server.</span></span>
    
5. <span data-ttu-id="9b6e4-197">Execute o cmdlet Restore-CcCredentials para inserir novamente as senhas após a descrição.</span><span class="sxs-lookup"><span data-stu-id="9b6e4-197">Run the Restore-CcCredentials cmdlet to re-enter the passwords following the description.</span></span> 
    
    <span data-ttu-id="9b6e4-198">Certifique-se de inserir a mesma senha que você inseriu anteriormente para a implantação do Cloud Connector, exceto para a conta CceService.</span><span class="sxs-lookup"><span data-stu-id="9b6e4-198">Be sure you enter the same password you entered before for the Cloud Connector deployment except for the CceService account.</span></span> <span data-ttu-id="9b6e4-199">Para a conta CceService, insira sua nova senha.</span><span class="sxs-lookup"><span data-stu-id="9b6e4-199">For the CceService account, enter your new password.</span></span> <span data-ttu-id="9b6e4-200">Certifique-se de que a nova senha da conta CceService seja a mesma para todos os dispositivos no site PSTN.</span><span class="sxs-lookup"><span data-stu-id="9b6e4-200">Be sure the new password for the CceService account is the same for all appliances in the PSTN site.</span></span>
    
6. <span data-ttu-id="9b6e4-201">Por padrão, VmAdmin e DomainAdmin usam a mesma senha que CceService.</span><span class="sxs-lookup"><span data-stu-id="9b6e4-201">By default, VmAdmin and DomainAdmin use the same password as CceService.</span></span> <span data-ttu-id="9b6e4-202">Se as senhas DomainAdmin, VMAdmin e CceService retornadas na etapa 1 forem diferentes, você deverá executar as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="9b6e4-202">If the DomainAdmin, VMAdmin, and CceService passwords returned in step 1 are different, you must perform the following steps:</span></span>
    
7. <span data-ttu-id="9b6e4-203">Execute Set-CcCredential-AccountType DomainAdmin da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="9b6e4-203">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
   - <span data-ttu-id="9b6e4-204">Quando for solicitada a credencial antiga da conta, insira a credencial que você usou para a senha do CceService.</span><span class="sxs-lookup"><span data-stu-id="9b6e4-204">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
   - <span data-ttu-id="9b6e4-205">Quando for solicitada a nova credencial da conta, insira a senha da senha do DomainAdmin retornada na etapa 1.</span><span class="sxs-lookup"><span data-stu-id="9b6e4-205">When prompted for the new account credential, enter the password for the DomainAdmin password returned in step 1.</span></span>
    
8. <span data-ttu-id="9b6e4-206">Execute Set-CcCredential-AccountType VmAdmin da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="9b6e4-206">Run Set-CcCredential -AccountType VmAdmin as follows:</span></span>
    
   - <span data-ttu-id="9b6e4-207">Quando for solicitada a credencial antiga da conta, insira a credencial que você usou para a senha do CceService.</span><span class="sxs-lookup"><span data-stu-id="9b6e4-207">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
   - <span data-ttu-id="9b6e4-208">Quando for solicitada a nova credencial da conta, insira a senha da senha do VmAdmin retornada na etapa 1.</span><span class="sxs-lookup"><span data-stu-id="9b6e4-208">When prompted for the new account credential, enter the password for the VmAdmin password returned in step 1.</span></span> 
    
9. <span data-ttu-id="9b6e4-209">Execute o cmdlet Exit-CcUpdate para mover o dispositivo para fora do modo de manutenção manual.</span><span class="sxs-lookup"><span data-stu-id="9b6e4-209">Run the Exit-CcUpdate cmdlet to move the appliance out of manual maintenance mode.</span></span>
    
10. <span data-ttu-id="9b6e4-210">Após concluir essas etapas em todos os dispositivos no mesmo site PSTN, exclua os seguintes arquivos no diretório raiz do site:</span><span class="sxs-lookup"><span data-stu-id="9b6e4-210">After you complete these steps on all appliances in the same PSTN site, delete the following files in the site root directory:</span></span>
    
    - <span data-ttu-id="9b6e4-211">CcLockFile</span><span class="sxs-lookup"><span data-stu-id="9b6e4-211">CcLockFile</span></span>
    
    - <span data-ttu-id="9b6e4-212">Site_\<Edge External Sip Pool fqdn\></span><span class="sxs-lookup"><span data-stu-id="9b6e4-212">Site_\<Edge External Sip Pool fqdn\></span></span>
    
    - <span data-ttu-id="9b6e4-213">Tenant_\<Edge External Sip Pool fqdn\></span><span class="sxs-lookup"><span data-stu-id="9b6e4-213">Tenant_\<Edge External Sip Pool fqdn\></span></span>
    
    - <span data-ttu-id="9b6e4-214">TenantConfigLock_\<Edge External Sip Pool fqdn\></span><span class="sxs-lookup"><span data-stu-id="9b6e4-214">TenantConfigLock_\<Edge External Sip Pool fqdn\></span></span>
    
## <a name="add-a-new-sip-domain"></a><span data-ttu-id="9b6e4-215">Adicionar um novo domínio SIP</span><span class="sxs-lookup"><span data-stu-id="9b6e4-215">Add a new SIP domain</span></span>
<span data-ttu-id="9b6e4-216"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="9b6e4-216"><a name="BKMK_UpdatePassword"> </a></span></span>

<span data-ttu-id="9b6e4-217">Para adicionar um novo domínio SIP (ou vários domínios SIP) à sua implantação existente do Cloud Connector, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="9b6e4-217">To add a new SIP domain (or multiple SIP domains) to your existing Cloud Connector deployment, do the following:</span></span>
  
1. <span data-ttu-id="9b6e4-218">Verifique se você concluiu as etapas para atualizar seu domínio no Microsoft 365 ou no Office 365 e tem a capacidade de adicionar registros DNS.</span><span class="sxs-lookup"><span data-stu-id="9b6e4-218">Make sure you've completed the steps to update your domain in Microsoft 365 or Office 365 and have the ability to add DNS records.</span></span> <span data-ttu-id="9b6e4-219">Para obter mais informações sobre como configurar seu domínio no Microsoft 365 ou no Office 365, consulte [Adicionar um domínio ao microsoft 365 ou office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span><span class="sxs-lookup"><span data-stu-id="9b6e4-219">For more information about how to set up your domain in Microsoft 365 or Office 365, see [Add a domain to Microsoft 365 or Office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span></span>
    
2. <span data-ttu-id="9b6e4-220">Atualize o arquivo de configuração do Cloud Connector com o novo domínio ou domínios SIP.</span><span class="sxs-lookup"><span data-stu-id="9b6e4-220">Update the Cloud Connector configuration file with the new SIP domain or domains.</span></span>
    
3. <span data-ttu-id="9b6e4-221">Solicite um novo certificado externo de borda com nomes de SAN adicionais para SIP. domain para cada domínio SIP definido na configuração do Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="9b6e4-221">Request a new Edge external certificate with additional SAN names for sip.domain for each SIP domain defined in your Cloud Connector configuration.</span></span> 
    
4. <span data-ttu-id="9b6e4-222">Defina o caminho para o novo certificado externo de borda da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="9b6e4-222">Set the path for the new Edge external certificate as follows:</span></span>
    
   ```powershell
   Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
   ```

5. 
    
    <span data-ttu-id="9b6e4-223">Siga as instruções para [Modificar a configuração de um único site](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_SIngleSite) ou [Modificar a configuração de vários sites](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_MultipleSites).</span><span class="sxs-lookup"><span data-stu-id="9b6e4-223">Follow the instructions to [Modify the configuration of a single site](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_SIngleSite) or [Modify the configuration of multiple sites](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_MultipleSites).</span></span>
    
## <a name="modify-the-primary-sip-domain"></a><span data-ttu-id="9b6e4-224">Modificar o domínio SIP primário</span><span class="sxs-lookup"><span data-stu-id="9b6e4-224">Modify the primary SIP domain</span></span>
<span data-ttu-id="9b6e4-225"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="9b6e4-225"><a name="BKMK_UpdatePassword"> </a></span></span>

<span data-ttu-id="9b6e4-226">Se você precisar alterar o domínio SIP primário em sua implantação do Cloud Connector, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="9b6e4-226">If you need to change the primary SIP domain in your Cloud Connector deployment, do the following:</span></span>
  
1. <span data-ttu-id="9b6e4-227">Verifique se você concluiu as etapas para atualizar seu domínio no Microsoft 365 ou no Office 365 e tem a capacidade de adicionar registros DNS.</span><span class="sxs-lookup"><span data-stu-id="9b6e4-227">Make sure you've completed the steps to update your domain in Microsoft 365 or Office 365 and have the ability to add DNS records.</span></span> <span data-ttu-id="9b6e4-228">Para obter mais informações sobre como configurar seu domínio no Microsoft 365 ou no Office 365, consulte [Adicionar um domínio ao microsoft 365 ou office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span><span class="sxs-lookup"><span data-stu-id="9b6e4-228">For more information about how to set up your domain in Microsoft 365 or Office 365, see [Add a domain to Microsoft 365 or Office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span></span>
    
2. <span data-ttu-id="9b6e4-229">Atualize o arquivo de configuração do Cloud Connector com o novo domínio SIP.</span><span class="sxs-lookup"><span data-stu-id="9b6e4-229">Update the Cloud Connector configuration file with the new SIP domain.</span></span>
    
3. <span data-ttu-id="9b6e4-230">Solicite um novo certificado externo de borda com nomes de SAN adicionais para SIP. domain para cada domínio SIP definido na configuração do Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="9b6e4-230">Request a new Edge external certificate with additional SAN names for sip.domain for each SIP domain defined in your Cloud Connector configuration.</span></span> 
    
4. <span data-ttu-id="9b6e4-231">Defina o caminho para o novo certificado externo de borda da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="9b6e4-231">Set the path for the new Edge external certificate as follows:</span></span>
    
   ```powershell
   Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
   ```

5. 
    
    <span data-ttu-id="9b6e4-232">Remova o registro do locatário para cada dispositivo em um site executando o seguinte cmdlet no PowerShell do administrador no Cloud Connector:</span><span class="sxs-lookup"><span data-stu-id="9b6e4-232">Remove the tenant registration for each appliance in a site by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
   ```powershell
   Unregister-CcAppliance
   ```

6. 
    
    <span data-ttu-id="9b6e4-233">Remova o registro do site de cada site executando o seguinte cmdlet no PowerShell do Skype for Business Online:</span><span class="sxs-lookup"><span data-stu-id="9b6e4-233">Remove the site registration for each site by running the following cmdlet in Skype for Business Online PowerShell:</span></span>
    
   ```powershell
   Remove-CsHybridPSTNSite
   ```

7. 
    
    <span data-ttu-id="9b6e4-234">Desinstale cada dispositivo executando o seguinte cmdlet no PowerShell do administrador no Cloud Connector:</span><span class="sxs-lookup"><span data-stu-id="9b6e4-234">Uninstall each appliance by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
   ```powershell
   Uninstall-CcAppliance
   ```

8. 
    
     <span data-ttu-id="9b6e4-235">Registre cada dispositivo executando o seguinte cmdlet no PowerShell do administrador no Cloud Connector:</span><span class="sxs-lookup"><span data-stu-id="9b6e4-235">Register each appliance by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
   ```powershell
   Register-ccAppliance
   ```

9. 
    
     <span data-ttu-id="9b6e4-236">Instale cada um dos dispositivos, um a um, executando o seguinte cmdlet no PowerShell do administrador no Cloud Connector:</span><span class="sxs-lookup"><span data-stu-id="9b6e4-236">Install each appliance, one by one, by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
   ```powershell
   Install-CcAppliance
   ```

## <a name="replace-the-external-edge-certificate-with-a-new-certificate"></a><span data-ttu-id="9b6e4-237">Substitua o certificado de borda externa por um novo certificado</span><span class="sxs-lookup"><span data-stu-id="9b6e4-237">Replace the external Edge certificate with a new certificate</span></span>
<span data-ttu-id="9b6e4-238"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="9b6e4-238"><a name="BKMK_UpdatePassword"> </a></span></span>

<span data-ttu-id="9b6e4-239">Quando precisar substituir o certificado de borda externa em seus dispositivos do Cloud Connector, você precisará obter um novo certificado de borda, preparar o arquivo PFX contendo a chave privada e a cadeia de certificados completo e, em seguida, faça o seguinte em cada dispositivo:</span><span class="sxs-lookup"><span data-stu-id="9b6e4-239">When you need to replace the external Edge certificate on your Cloud Connector appliances, you will need to obtain a new Edge certificate, prepare the PFX file containing the Private Key and full certificate chain, and then do the following on each appliance:</span></span>
  
1. <span data-ttu-id="9b6e4-240">Coloque o dispositivo no modo de manutenção usando o cmdlet Enter-CcUpdate.</span><span class="sxs-lookup"><span data-stu-id="9b6e4-240">Put the appliance in maintenance mode by using the Enter-CcUpdate cmdlet.</span></span>
    
2. <span data-ttu-id="9b6e4-241">Execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="9b6e4-241">Run the following command:</span></span> 
    
   ```powershell
   Set-CcExternalCertificateFilePath -Target EdgeServer -Path <Full file path of new certificate including filename> -Import
   ```

3. 
    
    <span data-ttu-id="9b6e4-242">Se a senha do novo certificado for igual à antiga, a importação será bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="9b6e4-242">If the password of the new certificate is the same as the old, the import will be successful.</span></span> <span data-ttu-id="9b6e4-243">Se a senha for diferente, você receberá um erro de que a senha está errada e será necessário redefinir a senha executando o cmdlet Register-CcAppliance com o parâmetro-local e, em seguida, repetindo a etapa 2.</span><span class="sxs-lookup"><span data-stu-id="9b6e4-243">If the password is different, you will receive an error that the password is wrong, and you will need to reset the password by running the Register-CcAppliance cmdlet with the -Local parameter, and then repeating step 2.</span></span> 
    
4. <span data-ttu-id="9b6e4-244">Retire o dispositivo do modo de manutenção, usando o cmdlet Exit-CcUpdate.</span><span class="sxs-lookup"><span data-stu-id="9b6e4-244">Take the appliance out of maintenance mode by using the Exit -CcUpdate cmdlet.</span></span>
    

