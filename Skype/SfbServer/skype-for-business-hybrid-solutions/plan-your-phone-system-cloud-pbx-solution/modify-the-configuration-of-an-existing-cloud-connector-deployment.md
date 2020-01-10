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
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 90490c65-0e40-4e85-96e1-751f27897e25
description: Siga as etapas deste tópico para modificar a configuração de uma implantação existente do Skype for Business Cloud Connector Edition 1.4.1 ou posterior.
ms.openlocfilehash: ead952c0ba567a8e5d81c52144de597e50d24014
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41002281"
---
# <a name="modify-the-configuration-of-an-existing-cloud-connector-deployment"></a><span data-ttu-id="4ae4e-103">Modificar a configuração de uma implantação do Cloud Connector existente</span><span class="sxs-lookup"><span data-stu-id="4ae4e-103">Modify the configuration of an existing Cloud Connector deployment</span></span>
 
<span data-ttu-id="4ae4e-104">Siga as etapas deste tópico para modificar a configuração de uma implantação existente do Skype for Business Cloud Connector Edition 1.4.1 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="4ae4e-104">Follow the steps in this topic to modify the configuration of an existing Skype for Business Cloud Connector Edition 1.4.1 or later deployment.</span></span> 
  
## <a name="modify-the-configuration-of-a-single-site"></a><span data-ttu-id="4ae4e-105">Modificar a configuração de um único site</span><span class="sxs-lookup"><span data-stu-id="4ae4e-105">Modify the configuration of a single site</span></span>
<span data-ttu-id="4ae4e-106"><a name="BKMK_SIngleSite"> </a></span><span class="sxs-lookup"><span data-stu-id="4ae4e-106"></span></span>

<span data-ttu-id="4ae4e-107">Se houver apenas um dispositivo no site, quando quiser alterar as definições de configuração depois que o dispositivo for implantado, você poderá modificar o arquivo CloudConnector.ini e iniciar a implantação novamente.</span><span class="sxs-lookup"><span data-stu-id="4ae4e-107">If there is only one appliance in the site, when you want to change the configuration settings after the appliance is deployed, you can modify the CloudConnector.ini file and start the deployment again.</span></span>
  
1. <span data-ttu-id="4ae4e-108">Execute o seguinte cmdlet para desinstalar todas as máquinas virtuais existentes no servidor host: </span><span class="sxs-lookup"><span data-stu-id="4ae4e-108">Run the following cmdlet to uninstall all existing virtual machines on the host server:</span></span> 
    
   ```powershell
   Uninstall-CcAppliance
   ```

2. <span data-ttu-id="4ae4e-109">Execute o seguinte cmdlet para cancelar o registro do dispositivo:</span><span class="sxs-lookup"><span data-stu-id="4ae4e-109">Run the following cmdlet to unregister the appliance:</span></span>
    
   ```powershell
   Unregister-CcAppliance
   ```

3. <span data-ttu-id="4ae4e-110">Atualize o arquivo CloudConnector.ini no Diretório de Dispositivos.</span><span class="sxs-lookup"><span data-stu-id="4ae4e-110">Update the CloudConnector.ini file in the Appliance Directory.</span></span>
    
4. <span data-ttu-id="4ae4e-111">Execute o cmdlet a seguir para atualizar a configuração: (esta etapa só se aplica à versão 2; para versões anteriores, pule para a próxima etapa.)</span><span class="sxs-lookup"><span data-stu-id="4ae4e-111">Run the following cmdlet to update the configuration: (This step is only applicable for version 2; for previous versions, skip to the next step.)</span></span>
    
   ```powershell
   Import-CcConfiguration 
   ```

5. <span data-ttu-id="4ae4e-112">Execute o seguinte cmdlet para registrar o dispositivo novamente:</span><span class="sxs-lookup"><span data-stu-id="4ae4e-112">Run the following cmdlet to register the appliance again:</span></span>
    
   ```powershell
   Register-CcAppliance
   ```

6. <span data-ttu-id="4ae4e-113">Execute o seguinte cmdlet para instalar o Skype for Business Cloud Connector Edition:</span><span class="sxs-lookup"><span data-stu-id="4ae4e-113">Run the following cmdlet to install Skype for Business Cloud Connector Edition:</span></span>
    
   ```powershell
   Install-CcAppliance
   ```

<span data-ttu-id="4ae4e-114">Se houver mais de um dispositivo no site, você deverá seguir estas etapas, modificar o arquivo CloudConnector.ini e reimplantar os dispositivos um a um.</span><span class="sxs-lookup"><span data-stu-id="4ae4e-114">If there is more than one appliance in the site, you'll need to follow these steps, modify the CloudConnector.ini file, and redeploy the appliances one by one.</span></span>
  
1. <span data-ttu-id="4ae4e-115">Execute o seguinte cmdlet para desinstalar todas as máquinas virtuais existentes do dispositivo atual. </span><span class="sxs-lookup"><span data-stu-id="4ae4e-115">Run the following cmdlet to uninstall all existing virtual machines on the current appliance:</span></span> 
    
   ```powershell
   Uninstall-CcAppliance
   ```

2. <span data-ttu-id="4ae4e-116">Execute o seguinte cmdlet para cancelar o registro do dispositivo:</span><span class="sxs-lookup"><span data-stu-id="4ae4e-116">Run the following cmdlet to unregister the appliance:</span></span>
    
   ```powershell
   Unregister-CcAppliance
   ```

3. <span data-ttu-id="4ae4e-117">Atualize o arquivo CloudConnector.ini no Diretório de Dispositivos.</span><span class="sxs-lookup"><span data-stu-id="4ae4e-117">Update the CloudConnector.ini file in the Appliance Directory.</span></span>
    
4. <span data-ttu-id="4ae4e-118">Execute o cmdlet a seguir para atualizar a configuração: (esta etapa só se aplica à versão 2; para versões anteriores, pule para a próxima etapa.)</span><span class="sxs-lookup"><span data-stu-id="4ae4e-118">Run the following cmdlet to update the configuration: (This step is only applicable for version 2; for previous versions, skip to the next step.)</span></span>
    
   ```powershell
   Import-CcConfiguration 
   ```

5. <span data-ttu-id="4ae4e-119">Execute o seguinte cmdlet para registrar o dispositivo novamente:</span><span class="sxs-lookup"><span data-stu-id="4ae4e-119">Run the following cmdlet to register the appliance again:</span></span>
    
   ```powershell
   Register-CcAppliance
   ```

6. <span data-ttu-id="4ae4e-120">Execute o seguinte cmdlet em todos os outros dispositivos do site para selecionar a configuração mais recente:</span><span class="sxs-lookup"><span data-stu-id="4ae4e-120">Run the following cmdlet on all other appliances in the site to pick up the latest configuration:</span></span>
    
   ```powershell
   Publish-CcAppliance
   ```

7. <span data-ttu-id="4ae4e-121">Execute o cmdlet a seguir para reimplantar o conector de nuvem no dispositivo atual:</span><span class="sxs-lookup"><span data-stu-id="4ae4e-121">Run the following cmdlet to redeploy Cloud Connector on the current appliance:</span></span>
    
   ```powershell
   Install-CcAppliance
   ```

## <a name="modify-the-configuration-of-multiple-sites"></a><span data-ttu-id="4ae4e-122">Modificar a configuração de vários sites</span><span class="sxs-lookup"><span data-stu-id="4ae4e-122">Modify the configuration of multiple sites</span></span>
<span data-ttu-id="4ae4e-123"><a name="BKMK_MultipleSites"> </a></span><span class="sxs-lookup"><span data-stu-id="4ae4e-123"></span></span>

<span data-ttu-id="4ae4e-124">Para modificar a configuração de vários sites em uma implantação, siga as etapas para um único site, atualizar um site de cada vez.</span><span class="sxs-lookup"><span data-stu-id="4ae4e-124">To modify the configuration for multiple sites in a deployment, follow the steps for a single site, updating one site at a time.</span></span>
  
## <a name="modify-the-configuration-of-your-office-365-tenant-to-enable-automatic-updates"></a><span data-ttu-id="4ae4e-125">Modificar a configuração ou seu locatário do Office 365 para habilitar atualizações automáticas</span><span class="sxs-lookup"><span data-stu-id="4ae4e-125">Modify the configuration of your Office 365 tenant to enable automatic updates</span></span>
<span data-ttu-id="4ae4e-126"><a name="BKMK_MultipleSites"> </a></span><span class="sxs-lookup"><span data-stu-id="4ae4e-126"></span></span>

<span data-ttu-id="4ae4e-127">Para habilitar as atualizações automáticas do sistema operacional e as atualizações automáticas do bits, você deve usar a conta de administrador locatário do Skype for Business para gerenciamento online e usar o PowerShell remoto do locatário da seguinte maneira.</span><span class="sxs-lookup"><span data-stu-id="4ae4e-127">To enable operating system automatic updates and Bits automatic updates, you must use the Skype for Business tenant admin account for online management and use tenant remote PowerShell as follows.</span></span>
  
<span data-ttu-id="4ae4e-128">Se você desabilitou as atualizações automáticas do sistema operacional ou as atualizações automáticas do bits, o host e a máquina virtual podem perder atualizações importantes do Windows e o Cloud Connector não será atualizado para a nova versão automaticamente.</span><span class="sxs-lookup"><span data-stu-id="4ae4e-128">If you disabled operating system automatic updates or Bits automatic updates, your host and virtual machine may miss important Windows updates, and Cloud Connector will not upgrade to the new version automatically.</span></span> <span data-ttu-id="4ae4e-129">É altamente recomendável que você habilite as atualizações automáticas.</span><span class="sxs-lookup"><span data-stu-id="4ae4e-129">It is highly recommended that you enable automatic updates.</span></span>
  
1. <span data-ttu-id="4ae4e-130">A propriedade EnableAutoUpdate do site precisa ser definida como true (o valor padrão).</span><span class="sxs-lookup"><span data-stu-id="4ae4e-130">The EnableAutoUpdate property of the site needs to be set to true (the default value).</span></span> <span data-ttu-id="4ae4e-131">Execute o seguinte cmdlet para garantir que EnableAutoUpdate seja definido como True:</span><span class="sxs-lookup"><span data-stu-id="4ae4e-131">Run the following cmdlet to make sure EnableAutoUpdate is set to true:</span></span>
    
   ```powershell
   Get-CsHybridPSTNSite -Identity <SiteName>
   ```

2. <span data-ttu-id="4ae4e-132">Crie a janela de tempo de atualização automática para o locatário.</span><span class="sxs-lookup"><span data-stu-id="4ae4e-132">Create auto update time window for the tenant.</span></span>
    
    <span data-ttu-id="4ae4e-p103">A janela de tempo pode ser diária, semanal e mensal. Todas as janelas de tempo precisam de uma hora de início e duração.</span><span class="sxs-lookup"><span data-stu-id="4ae4e-p103">The time window can be daily, weekly and monthly. All the time windows need a start time and a duration.</span></span>
    
   - <span data-ttu-id="4ae4e-135">Para a janela de tempo diária, apenas a hora de início e a duração são necessárias. </span><span class="sxs-lookup"><span data-stu-id="4ae4e-135">For a daily time window, only start time and duration are needed.</span></span> 
    
   - <span data-ttu-id="4ae4e-136">Para a janela de tempo semanal, são necessários os dias da semana. Pode ser um único dia ou vários dias.</span><span class="sxs-lookup"><span data-stu-id="4ae4e-136">For a weekly time window, days of week are needed, which can be a single day or multiple days.</span></span>
    
   - <span data-ttu-id="4ae4e-p104">Para a janela de tempo mensal, pode haver 2 tipos. A primeira maneira é especificar o dia do mês, que pode ser um único dia. A segunda maneira é especificar semanas do mês, junto com os dias da semana, que podem ser um item ou vários itens.</span><span class="sxs-lookup"><span data-stu-id="4ae4e-p104">For a monthly time window, there can be two types. The first type is to specify the day of the month, which can be a single day. The second type is to specify the weeks of the month, along with days of the week, which both can be a single item or multiple items.</span></span>
    
   - <span data-ttu-id="4ae4e-p105">Cada locatário pode ter 20 janelas de tempo definidas. A janela de tempo padrão será criada para um novo locatário como janela de tempo padrão para atualização do sistema operacional e do Bits. Execute os seguintes cmdlets para definir a janela de tempo diária, semanal ou mensal:</span><span class="sxs-lookup"><span data-stu-id="4ae4e-p105">Each tenant can have 20 time windows defined. The default time window will be created for a new tenant as the default time window for operating system update and Bits update. Run the following cmdlet(s) to set the daily, weekly or monthly time window:</span></span>
    
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

   - <span data-ttu-id="4ae4e-143">Atribuir janelas de tempo de atualização ao site. </span><span class="sxs-lookup"><span data-stu-id="4ae4e-143">Assign update time windows to the site.</span></span> 
    
     <span data-ttu-id="4ae4e-p106">As janelas de tempo de atualização do Bits e do sistema operacional são configuradas separadamente. É possível atribuir uma ou várias janelas de tempo a ambos. Cada janela de tempo pode ser atribuída a diferentes locais e finalidades (atualização do Bits e atualização do sistema operacional). Execute o seguinte cmdlet para definir a janela de tempo do site: </span><span class="sxs-lookup"><span data-stu-id="4ae4e-p106">The Bits update time and OS update time windows are configured separately. Both of them can be assigned single or multiple time windows. Each time window can be assigned to different sites and different purpose (Bits update and OS update). Run the following cmdlet to set the time window for the site:</span></span> 
    
   ```powershell
   Set-CsHybridPSTNSite -Identity <SiteName> -BitsUpdateTimeWindow @{add="MidDayOfMonth","WeekdayNight"} -OsUpdateTimeWindow @{replace="Night"}
   ```

## <a name="update-the-dedicated-tenant-admin-credentials"></a><span data-ttu-id="4ae4e-148">Atualizar as credenciais exclusivas de administrador do locatário </span><span class="sxs-lookup"><span data-stu-id="4ae4e-148">Update the dedicated tenant admin credentials</span></span>
<span data-ttu-id="4ae4e-149"><a name="BKMK_MultipleSites"> </a></span><span class="sxs-lookup"><span data-stu-id="4ae4e-149"></span></span>

<span data-ttu-id="4ae4e-150">Alterações administrativas no locatário do Office 365 para o Cloud Connector são feitas a partir de uma conta com as permissões necessárias.</span><span class="sxs-lookup"><span data-stu-id="4ae4e-150">Administrative changes in the Office 365 tenant for Cloud Connector are made from an account with the needed permissions.</span></span> <span data-ttu-id="4ae4e-151">Em versões do conector de nuvem anteriores ao 2,0, essa conta é uma conta de administrador de locatário global dedicada.</span><span class="sxs-lookup"><span data-stu-id="4ae4e-151">In Cloud Connector versions before 2.0, that account is a dedicated global tenant admin account.</span></span> <span data-ttu-id="4ae4e-152">Nas versões do conector de nuvem 2,0 e posteriores, essa conta pode ser uma conta do Office 365 com direitos de administrador do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="4ae4e-152">In Cloud Connector versions 2.0 and later, that account can be an Office 365 account with Skype for Business Administrator rights.</span></span>
  
<span data-ttu-id="4ae4e-153">Se as credenciais da sua conta de administrador forem alteradas no Office 365, você também precisará atualizar as credenciais armazenadas em cache localmente no conector de nuvem executando o seguinte comando do PowerShell do administrador em cada dispositivo de conexão de nuvem que você implantou:</span><span class="sxs-lookup"><span data-stu-id="4ae4e-153">If your admin account credentials change in Office 365, you also need to update the locally cached credentials in Cloud Connector by running the following Administrator PowerShell command on each Cloud Connector appliance you have deployed:</span></span>
  
```powershell
Set-CcCredential -AccountType TenantAdmin
```

## <a name="update-the-password-for-the-host-server"></a><span data-ttu-id="4ae4e-154">Atualizar a senha do servidor host </span><span class="sxs-lookup"><span data-stu-id="4ae4e-154">Update the password for the host server</span></span>
<span data-ttu-id="4ae4e-155"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="4ae4e-155"></span></span>

> [!NOTE]
> <span data-ttu-id="4ae4e-156">Esta seção é aplicável à versão 2.0 e versões posteriores do Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="4ae4e-156">This section is applicable to Cloud Connector version 2.0 and later.</span></span> 
  
<span data-ttu-id="4ae4e-157">Todas as credenciais do conector de nuvem são armazenadas no seguinte arquivo: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>. xml ".</span><span class="sxs-lookup"><span data-stu-id="4ae4e-157">All Cloud Connector credentials are stored in the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span> <span data-ttu-id="4ae4e-158">Quando for alterada a senha do servidor host, você precisará atualizar as credenciais armazenadas localmente.</span><span class="sxs-lookup"><span data-stu-id="4ae4e-158">When the password on the host server changes, you will need to update the locally stored credentials.</span></span>
  
<span data-ttu-id="4ae4e-159">Para atualizar as credenciais armazenadas localmente no dispositivo do conector de nuvem, use os cmdlets [Get-CcCredential](get-cccredential.md) e [set-CcCredential](set-cccredential.md) e siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="4ae4e-159">To update the locally stored credentials on the Cloud Connector appliance, use the [Get-CcCredential](get-cccredential.md) and [Set-CcCredential](set-cccredential.md) cmdlets and follow these steps:</span></span>
  
1. <span data-ttu-id="4ae4e-160">Execute os seguintes comandos para recuperar as senhas das quais você precisará mais tarde: </span><span class="sxs-lookup"><span data-stu-id="4ae4e-160">Run the following commands to retrieve the passwords you will need later:</span></span> 
    
   - <span data-ttu-id="4ae4e-161">Get-CcCredential -AccountType DomainAdmin -DisplayPassword</span><span class="sxs-lookup"><span data-stu-id="4ae4e-161">Get-CcCredential -AccountType DomainAdmin -DisplayPassword</span></span>
    
   - <span data-ttu-id="4ae4e-162">Get-CcCredential -AccountType VMAdmin -DisplayPassword</span><span class="sxs-lookup"><span data-stu-id="4ae4e-162">Get-CcCredential -AccountType VMAdmin -DisplayPassword</span></span>
    
   - <span data-ttu-id="4ae4e-163">Get-CcCredential -AccountType CceService -DisplayPassword</span><span class="sxs-lookup"><span data-stu-id="4ae4e-163">Get-CcCredential -AccountType CceService -DisplayPassword</span></span>
    
2. <span data-ttu-id="4ae4e-164">Altere a senha da sua conta no servidor host.</span><span class="sxs-lookup"><span data-stu-id="4ae4e-164">Change the password of your account on the host server.</span></span>
    
3. <span data-ttu-id="4ae4e-165">Reinicie o servidor host.</span><span class="sxs-lookup"><span data-stu-id="4ae4e-165">Restart the host server.</span></span>
    
4. <span data-ttu-id="4ae4e-166">Exclua o seguinte arquivo: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>. xml ".</span><span class="sxs-lookup"><span data-stu-id="4ae4e-166">Delete the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span>
    
5. <span data-ttu-id="4ae4e-167">Inicie um console do PowerShell como administrador e, em seguida, execute "Register-CcAppliance-local" para inserir novamente as senhas após a descrição.</span><span class="sxs-lookup"><span data-stu-id="4ae4e-167">Launch a PowerShell console as administrator, and then run "Register-CcAppliance -Local" to re-enter the passwords following the description.</span></span> <span data-ttu-id="4ae4e-168">Certifique-se de inserir a mesma senha que você inseriu anteriormente para a implantação do Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="4ae4e-168">Be sure you enter the same password you entered before for the Cloud Connector deployment.</span></span>
    
<span data-ttu-id="4ae4e-p110">Por padrão, VmAdmin e DomainAdmin usam a mesma senha que o CceService. Se as senhas de DomainAdmin, VMAdmin e CceService retornadas na etapa 1 forem diferentes, você deverá executar as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="4ae4e-p110">By default, VmAdmin and DomainAdmin use the same password as CceService. If the DomainAdmin, VMAdmin, and CceService passwords returned in step 1 are different, you must perform the following steps:</span></span>
  
1. <span data-ttu-id="4ae4e-171">Execute Set-CcCredential -AccountType DomainAdmin da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="4ae4e-171">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
1. <span data-ttu-id="4ae4e-172">Quando solicitada a antiga credencial da conta, insira a credencial que você usou para a senha do CceService.</span><span class="sxs-lookup"><span data-stu-id="4ae4e-172">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
2. <span data-ttu-id="4ae4e-173">Quando solicitada a nova credencial da conta, insira a senha do DomainAdmin retornada na etapa 1.</span><span class="sxs-lookup"><span data-stu-id="4ae4e-173">When prompted for the new account credential, enter the password for the DomainAdmin password returned in step 1.</span></span>
    
2. <span data-ttu-id="4ae4e-174">Execute Set-CcCredential -AccountType VmAdmin da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="4ae4e-174">Run Set-CcCredential -AccountType VmAdmin as follows:</span></span>
    
1. <span data-ttu-id="4ae4e-175">Quando solicitada a antiga credencial da conta, insira a credencial que você usou para a senha do CceService.</span><span class="sxs-lookup"><span data-stu-id="4ae4e-175">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
2. <span data-ttu-id="4ae4e-176">Quando solicitada a nova credencial da conta, insira a senha do VmAdmin retornada na etapa 1. </span><span class="sxs-lookup"><span data-stu-id="4ae4e-176">When prompted for the new account credential, enter the password for the VmAdmin password returned in step 1.</span></span> 
    
## <a name="update-the-password-for-the-cceservice-account"></a><span data-ttu-id="4ae4e-177">Atualizar a senha da conta do CceService</span><span class="sxs-lookup"><span data-stu-id="4ae4e-177">Update the password for the CceService account</span></span>
<span data-ttu-id="4ae4e-178"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="4ae4e-178"></span></span>

> [!NOTE]
> <span data-ttu-id="4ae4e-179">Esta seção é aplicável para o Cloud Connector versão 2.0.1 e posterior.</span><span class="sxs-lookup"><span data-stu-id="4ae4e-179">This section is applicable to Cloud Connector version 2.0.1 and later.</span></span> 
  
<span data-ttu-id="4ae4e-180">O serviço do conector de nuvem executa o serviço de gerenciamento do Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="4ae4e-180">The Cloud Connector service runs the Cloud Connector Management service.</span></span> <span data-ttu-id="4ae4e-181">A conta CceService é criada durante a implantação da edição do Cloud Connector e armazenada nos seguintes arquivos: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>. xml "e"%systemdrive%\Programdata\Cloudconnector\credentials.. CceService. xml ".</span><span class="sxs-lookup"><span data-stu-id="4ae4e-181">The CceService account is created during the Cloud Connector Edition deployment and stored in the following files: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml" and "%SystemDrive%\Programdata\Cloudconnector\credentials..CceService.xml".</span></span>
  
<span data-ttu-id="4ae4e-182">Para garantir que todos os aparelhos possam acessar o compartilhamento de diretório de sites, a senha da conta CceService deve ser a mesma em todos os aparelhos implantados no site.</span><span class="sxs-lookup"><span data-stu-id="4ae4e-182">To ensure that all appliances can access the site directory share, the password for the CceService account must be the same on all appliances deployed within the site.</span></span> <span data-ttu-id="4ae4e-183">Considere o seguinte:</span><span class="sxs-lookup"><span data-stu-id="4ae4e-183">Keep the following in mind:</span></span>
  
- <span data-ttu-id="4ae4e-184">Por padrão, a conta CceService está configurada como "a senha nunca expira".</span><span class="sxs-lookup"><span data-stu-id="4ae4e-184">By default, the CceService account is configured as "Password never expires".</span></span> <span data-ttu-id="4ae4e-185">Quando você atualiza a senha, a Microsoft recomenda manter essa configuração.</span><span class="sxs-lookup"><span data-stu-id="4ae4e-185">When you update the password, Microsoft recommends keeping this configuration.</span></span>
    
- <span data-ttu-id="4ae4e-186">Você deve atualizar a senha durante períodos de uso sem pico e fora das janelas de tempo de atualização automática para bits ou atualizações do Windows.</span><span class="sxs-lookup"><span data-stu-id="4ae4e-186">You should update the password during non-peak usage periods and outside of automatic update time windows for bits or Windows updates.</span></span> <span data-ttu-id="4ae4e-187">Quando você atualiza a senha, o aparelho precisa ser descarregada e reiniciada, o que leva algum tempo.</span><span class="sxs-lookup"><span data-stu-id="4ae4e-187">When you update the password, the appliance needs to be drained and restarted, which takes some time.</span></span> <span data-ttu-id="4ae4e-188">Reiniciar o aparelho irá interromper as operações de atualização automática.</span><span class="sxs-lookup"><span data-stu-id="4ae4e-188">Restarting the appliance will interrupt automatic update operations.</span></span> 
    
- <span data-ttu-id="4ae4e-189">Quando você alterar a senha da conta do CceService, será necessário especificar todas as credenciais e atualizá-las no arquivo armazenado localmente.</span><span class="sxs-lookup"><span data-stu-id="4ae4e-189">When you change the CceService account password, you will need to specify all the credentials and update them in the locally stored file.</span></span> 
    
<span data-ttu-id="4ae4e-190">Para cada dispositivo que pertence ao mesmo site PSTN, será preciso especificar o seguinte:</span><span class="sxs-lookup"><span data-stu-id="4ae4e-190">For each appliance that belongs to the same PSTN site, you will need to specify the following:</span></span> 
  
1. <span data-ttu-id="4ae4e-191">Execute os seguintes comandos para recuperar os nomes de conta e as senhas que você usará mais tarde:</span><span class="sxs-lookup"><span data-stu-id="4ae4e-191">Run the following commands to retrieve the account names and passwords that you will use later:</span></span>
    
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

2. <span data-ttu-id="4ae4e-192">Execute o cmdlet Enter-CcUpdate para dissipar o aparelho e mova-o para o modo de manutenção manual.</span><span class="sxs-lookup"><span data-stu-id="4ae4e-192">Run the Enter-CcUpdate cmdlet to drain the appliance and move it into manual maintenance mode.</span></span>
    
3. <span data-ttu-id="4ae4e-193">Atualize a senha da conta do CceService no servidor host.</span><span class="sxs-lookup"><span data-stu-id="4ae4e-193">Update the password of the CceService account on the host server.</span></span>
    
4. <span data-ttu-id="4ae4e-194">Reinicie o servidor host.</span><span class="sxs-lookup"><span data-stu-id="4ae4e-194">Restart the host server.</span></span>
    
5. <span data-ttu-id="4ae4e-195">Execute o cmdlet Restore-CcCredentials para inserir novamente as senhas após a descrição.</span><span class="sxs-lookup"><span data-stu-id="4ae4e-195">Run the Restore-CcCredentials cmdlet to re-enter the passwords following the description.</span></span> 
    
    <span data-ttu-id="4ae4e-196">Certifique-se de digitar a mesma senha que você inseriu antes para a implantação do conector de nuvem, exceto para a conta do CceService.</span><span class="sxs-lookup"><span data-stu-id="4ae4e-196">Be sure you enter the same password you entered before for the Cloud Connector deployment except for the CceService account.</span></span> <span data-ttu-id="4ae4e-197">Para a conta CceService, insira sua nova senha.</span><span class="sxs-lookup"><span data-stu-id="4ae4e-197">For the CceService account, enter your new password.</span></span> <span data-ttu-id="4ae4e-198">Certifique-se de que a nova senha da conta CceService é a mesma para todos os aparelhos no site PSTN.</span><span class="sxs-lookup"><span data-stu-id="4ae4e-198">Be sure the new password for the CceService account is the same for all appliances in the PSTN site.</span></span>
    
6. <span data-ttu-id="4ae4e-p116">Por padrão, VmAdmin e DomainAdmin usam a mesma senha que o CceService. Se as senhas de DomainAdmin, VMAdmin e CceService retornadas na etapa 1 forem diferentes, você deverá executar as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="4ae4e-p116">By default, VmAdmin and DomainAdmin use the same password as CceService. If the DomainAdmin, VMAdmin, and CceService passwords returned in step 1 are different, you must perform the following steps:</span></span>
    
7. <span data-ttu-id="4ae4e-201">Execute Set-CcCredential -AccountType DomainAdmin da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="4ae4e-201">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
   - <span data-ttu-id="4ae4e-202">Quando solicitada a antiga credencial da conta, insira a credencial que você usou para a senha do CceService.</span><span class="sxs-lookup"><span data-stu-id="4ae4e-202">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
   - <span data-ttu-id="4ae4e-203">Quando solicitada a nova credencial da conta, insira a senha do DomainAdmin retornada na etapa 1.</span><span class="sxs-lookup"><span data-stu-id="4ae4e-203">When prompted for the new account credential, enter the password for the DomainAdmin password returned in step 1.</span></span>
    
8. <span data-ttu-id="4ae4e-204">Execute Set-CcCredential -AccountType VmAdmin da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="4ae4e-204">Run Set-CcCredential -AccountType VmAdmin as follows:</span></span>
    
   - <span data-ttu-id="4ae4e-205">Quando solicitada a antiga credencial da conta, insira a credencial que você usou para a senha do CceService.</span><span class="sxs-lookup"><span data-stu-id="4ae4e-205">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
   - <span data-ttu-id="4ae4e-206">Quando solicitada a nova credencial da conta, insira a senha do VmAdmin retornada na etapa 1. </span><span class="sxs-lookup"><span data-stu-id="4ae4e-206">When prompted for the new account credential, enter the password for the VmAdmin password returned in step 1.</span></span> 
    
9. <span data-ttu-id="4ae4e-207">Execute o cmdlet Exit-CcUpdate para mover o aplicativo para fora do modo de manutenção manual.</span><span class="sxs-lookup"><span data-stu-id="4ae4e-207">Run the Exit-CcUpdate cmdlet to move the appliance out of manual maintenance mode.</span></span>
    
10. <span data-ttu-id="4ae4e-208">Depois de concluir essas etapas em todos os aparelhos no mesmo site PSTN, exclua os seguintes arquivos no diretório raiz do site:</span><span class="sxs-lookup"><span data-stu-id="4ae4e-208">After you complete these steps on all appliances in the same PSTN site, delete the following files in the site root directory:</span></span>
    
    - <span data-ttu-id="4ae4e-209">CcLockFile</span><span class="sxs-lookup"><span data-stu-id="4ae4e-209">CcLockFile</span></span>
    
    - <span data-ttu-id="4ae4e-210">Site_\<o FQDN do pool de conector SIP externo\></span><span class="sxs-lookup"><span data-stu-id="4ae4e-210">Site_\<Edge External Sip Pool fqdn\></span></span>
    
    - <span data-ttu-id="4ae4e-211">Tenant_\<o FQDN do pool de conector SIP externo\></span><span class="sxs-lookup"><span data-stu-id="4ae4e-211">Tenant_\<Edge External Sip Pool fqdn\></span></span>
    
    - <span data-ttu-id="4ae4e-212">TenantConfigLock_\<o FQDN do pool de conector SIP externo\></span><span class="sxs-lookup"><span data-stu-id="4ae4e-212">TenantConfigLock_\<Edge External Sip Pool fqdn\></span></span>
    
## <a name="add-a-new-sip-domain"></a><span data-ttu-id="4ae4e-213">Adicionar um novo domínio SIP </span><span class="sxs-lookup"><span data-stu-id="4ae4e-213">Add a new SIP domain</span></span>
<span data-ttu-id="4ae4e-214"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="4ae4e-214"></span></span>

<span data-ttu-id="4ae4e-215">Para adicionar um novo domínio SIP (ou vários domínios SIP) à sua implantação do conector de nuvem existente, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="4ae4e-215">To add a new SIP domain (or multiple SIP domains) to your existing Cloud Connector deployment, do the following:</span></span>
  
1. <span data-ttu-id="4ae4e-216">Verifique se você concluiu as etapas para atualizar seu domínio no Office 365 e se consegue adicionar registros DNS.</span><span class="sxs-lookup"><span data-stu-id="4ae4e-216">Make sure you've completed the steps to update your domain in Office 365 and have the ability to add DNS records.</span></span> <span data-ttu-id="4ae4e-217">Para obter mais informações sobre como configurar seu domínio no Office 365, consulte [Adicionar um domínio ao office 365](https://support.office.com/en-us/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span><span class="sxs-lookup"><span data-stu-id="4ae4e-217">For more information about how to set up your domain in Office 365, see [Add a domain to Office 365](https://support.office.com/en-us/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span></span>
    
2. <span data-ttu-id="4ae4e-218">Atualize o arquivo de configuração do conector de nuvem com o novo domínio SIP ou domínios.</span><span class="sxs-lookup"><span data-stu-id="4ae4e-218">Update the Cloud Connector configuration file with the new SIP domain or domains.</span></span>
    
3. <span data-ttu-id="4ae4e-219">Solicite um novo certificado externo de borda com nomes de SAN adicionais para SIP. domain para cada domínio SIP definido na configuração do seu conector de nuvem.</span><span class="sxs-lookup"><span data-stu-id="4ae4e-219">Request a new Edge external certificate with additional SAN names for sip.domain for each SIP domain defined in your Cloud Connector configuration.</span></span> 
    
4. <span data-ttu-id="4ae4e-220">Defina o caminho do certificado externo de Borda da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="4ae4e-220">Set the path for the new Edge external certificate as follows:</span></span>
    
   ```powershell
   Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
   ```

5. 
    
    <span data-ttu-id="4ae4e-221">Siga as instruções para [Modificar a configuração de um único site](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_SIngleSite) ou [Modificar a configuração de vários sites](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_MultipleSites).</span><span class="sxs-lookup"><span data-stu-id="4ae4e-221">Follow the instructions to [Modify the configuration of a single site](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_SIngleSite) or [Modify the configuration of multiple sites](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_MultipleSites).</span></span>
    
## <a name="modify-the-primary-sip-domain"></a><span data-ttu-id="4ae4e-222">Modificar o domínio SIP primário</span><span class="sxs-lookup"><span data-stu-id="4ae4e-222">Modify the primary SIP domain</span></span>
<span data-ttu-id="4ae4e-223"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="4ae4e-223"></span></span>

<span data-ttu-id="4ae4e-224">Se você precisar alterar o domínio SIP primário em sua implantação do conector de nuvem, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="4ae4e-224">If you need to change the primary SIP domain in your Cloud Connector deployment, do the following:</span></span>
  
1. <span data-ttu-id="4ae4e-225">Verifique se você concluiu as etapas para atualizar seu domínio no Office 365 e se consegue adicionar registros DNS.</span><span class="sxs-lookup"><span data-stu-id="4ae4e-225">Make sure you've completed the steps to update your domain in Office 365 and have the ability to add DNS records.</span></span> <span data-ttu-id="4ae4e-226">Para obter mais informações sobre como configurar seu domínio no Office 365, consulte [Adicionar um domínio ao office 365](https://support.office.com/en-us/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span><span class="sxs-lookup"><span data-stu-id="4ae4e-226">For more information about how to set up your domain in Office 365, see [Add a domain to Office 365](https://support.office.com/en-us/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span></span>
    
2. <span data-ttu-id="4ae4e-227">Atualize o arquivo de configuração do conector de nuvem com o novo domínio SIP.</span><span class="sxs-lookup"><span data-stu-id="4ae4e-227">Update the Cloud Connector configuration file with the new SIP domain.</span></span>
    
3. <span data-ttu-id="4ae4e-228">Solicite um novo certificado externo de borda com nomes de SAN adicionais para SIP. domain para cada domínio SIP definido na configuração do seu conector de nuvem.</span><span class="sxs-lookup"><span data-stu-id="4ae4e-228">Request a new Edge external certificate with additional SAN names for sip.domain for each SIP domain defined in your Cloud Connector configuration.</span></span> 
    
4. <span data-ttu-id="4ae4e-229">Defina o caminho do certificado externo de Borda da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="4ae4e-229">Set the path for the new Edge external certificate as follows:</span></span>
    
   ```powershell
   Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
   ```

5. 
    
    <span data-ttu-id="4ae4e-230">Remova o registro do locatário para cada aplicativo em um site executando o seguinte cmdlet no PowerShell do administrador no conector de nuvem:</span><span class="sxs-lookup"><span data-stu-id="4ae4e-230">Remove the tenant registration for each appliance in a site by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
   ```powershell
   Unregister-CcAppliance
   ```

6. 
    
    <span data-ttu-id="4ae4e-231">Remova o registro do site de cada um dos sites executando o seguinte cmdlet no PowerShell do Skype for Business Online:</span><span class="sxs-lookup"><span data-stu-id="4ae4e-231">Remove the site registration for each site by running the following cmdlet in Skype for Business Online PowerShell:</span></span>
    
   ```powershell
   Remove-CsHybridPSTNSite
   ```

7. 
    
    <span data-ttu-id="4ae4e-232">Desinstale cada dispositivo executando o seguinte cmdlet no PowerShell do administrador no conector de nuvem:</span><span class="sxs-lookup"><span data-stu-id="4ae4e-232">Uninstall each appliance by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
   ```powershell
   Uninstall-CcAppliance
   ```

8. 
    
     <span data-ttu-id="4ae4e-233">Registre cada dispositivo executando o seguinte cmdlet no PowerShell do administrador no conector de nuvem:</span><span class="sxs-lookup"><span data-stu-id="4ae4e-233">Register each appliance by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
   ```powershell
   Register-ccAppliance
   ```

9. 
    
     <span data-ttu-id="4ae4e-234">Instale cada utilitário, um por um, executando o seguinte cmdlet no PowerShell do administrador no conector de nuvem:</span><span class="sxs-lookup"><span data-stu-id="4ae4e-234">Install each appliance, one by one, by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
   ```powershell
   Install-CcAppliance
   ```

## <a name="replace-the-external-edge-certificate-with-a-new-certificate"></a><span data-ttu-id="4ae4e-235">Substituir o certificado de borda externa por um novo certificado</span><span class="sxs-lookup"><span data-stu-id="4ae4e-235">Replace the external Edge certificate with a new certificate</span></span>
<span data-ttu-id="4ae4e-236"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="4ae4e-236"></span></span>

<span data-ttu-id="4ae4e-237">Quando você precisar substituir o certificado de borda externa em seus aparelhos de conector de nuvem, será necessário obter um novo certificado de borda, preparar o arquivo PFX contendo a chave privada e a cadeia de certificados completo e, em seguida, fazer o seguinte em cada dispositivo:</span><span class="sxs-lookup"><span data-stu-id="4ae4e-237">When you need to replace the external Edge certificate on your Cloud Connector appliances, you will need to obtain a new Edge certificate, prepare the PFX file containing the Private Key and full certificate chain, and then do the following on each appliance:</span></span>
  
1. <span data-ttu-id="4ae4e-238">Coloque o aparelho no modo de manutenção usando o cmdlet Enter-CcUpdate.</span><span class="sxs-lookup"><span data-stu-id="4ae4e-238">Put the appliance in maintenance mode by using the Enter-CcUpdate cmdlet.</span></span>
    
2. <span data-ttu-id="4ae4e-239">Execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="4ae4e-239">Run the following command:</span></span> 
    
   ```powershell
   Set-CcExternalCertificateFilePath -Target EdgeServer -Path <Full file path of new certificate including filename> -Import
   ```

3. 
    
    <span data-ttu-id="4ae4e-240">Se a senha do novo certificado for igual à antiga, a importação será bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="4ae4e-240">If the password of the new certificate is the same as the old, the import will be successful.</span></span> <span data-ttu-id="4ae4e-241">Se a senha for diferente, você receberá um erro informando que a senha está errada e será necessário redefinir a senha executando o cmdlet Register-CcAppliance com o parâmetro-local e, em seguida, repetindo a etapa 2.</span><span class="sxs-lookup"><span data-stu-id="4ae4e-241">If the password is different, you will receive an error that the password is wrong, and you will need to reset the password by running the Register-CcAppliance cmdlet with the -Local parameter, and then repeating step 2.</span></span> 
    
4. <span data-ttu-id="4ae4e-242">Retire o aparelho do modo de manutenção usando o cmdlet Exit-CcUpdate.</span><span class="sxs-lookup"><span data-stu-id="4ae4e-242">Take the appliance out of maintenance mode by using the Exit -CcUpdate cmdlet.</span></span>
    

