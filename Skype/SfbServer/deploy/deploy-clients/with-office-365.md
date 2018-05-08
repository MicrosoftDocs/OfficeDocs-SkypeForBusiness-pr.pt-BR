---
title: Implantar o Skype Room Systems versão 2 com o Office 365
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/8/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: Leia este tópico para obter informações sobre como implantar sistemas de sala Skype v2 com o Office 365.
ms.openlocfilehash: 87ae4f7e846cce1cfeca2c7f64fdee93476ae350
ms.sourcegitcommit: 2c084358844f02fbf7953f2ea49ed6d710cbf06f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/08/2018
---
# <a name="deploy-skype-room-systems-v2-with-office-365"></a><span data-ttu-id="31248-103">Implantar o Skype Room Systems versão 2 com o Office 365 </span><span class="sxs-lookup"><span data-stu-id="31248-103">Deploy Skype Room Systems v2 with Office 365</span></span>
 
<span data-ttu-id="31248-104">Leia este tópico para obter informações sobre como implantar sistemas de sala Skype v2 com o Office 365.</span><span class="sxs-lookup"><span data-stu-id="31248-104">Read this topic for information on how to deploy Skype Room Systems v2 with Office 365.</span></span>
  
<span data-ttu-id="31248-105">Este tópico descreve como adicionar uma conta de dispositivo para sistemas de sala Skype v2 quando você tem uma implantação online do Office 365.</span><span class="sxs-lookup"><span data-stu-id="31248-105">This topic describes how to add a device account for Skype Room Systems v2 when you have an Office 365 online deployment.</span></span>
  
## <a name="deploy-skype-room-systems-v2-with-office-365"></a><span data-ttu-id="31248-106">Implantar o Skype Room Systems versão 2 com o Office 365 </span><span class="sxs-lookup"><span data-stu-id="31248-106">Deploy Skype Room Systems v2 with Office 365</span></span>

<span data-ttu-id="31248-107">Antes de implantar sistemas de sala Skype v2 com o Office 365, certifique-se de que você cumpre os requisitos.</span><span class="sxs-lookup"><span data-stu-id="31248-107">Before you deploy Skype Room Systems v2 with Office 365, be sure you have met the requirements.</span></span> <span data-ttu-id="31248-108">Para obter mais informações, consulte [requisitos de v2 de sistemas de sala Skype](../../plan-your-deployment/clients-and-devices/requirements.md).</span><span class="sxs-lookup"><span data-stu-id="31248-108">For more information, see [Skype Room Systems v2 requirements](../../plan-your-deployment/clients-and-devices/requirements.md).</span></span>
  
<span data-ttu-id="31248-109">Para habilitar o Skype para a empresa, você deve ter o seguinte:</span><span class="sxs-lookup"><span data-stu-id="31248-109">To enable Skype for Business, you must have the following:</span></span>
  
- <span data-ttu-id="31248-110">Skype para negócios Online (plano 2) ou superior no seu plano do Office 365.</span><span class="sxs-lookup"><span data-stu-id="31248-110">Skype for Business Online (Plan 2) or higher in your Office 365 plan.</span></span> <span data-ttu-id="31248-111">O plano precisa dar suporte à funcionalidade de conferência.</span><span class="sxs-lookup"><span data-stu-id="31248-111">The plan needs to support conferencing capability.</span></span>
    
- <span data-ttu-id="31248-112">Se precisar de Enterprise Voice (telefonia PSTN) usando os provedores de serviços de telefonia para sistemas de sala Skype v2 será necessário Skype para Business Online (plano 3).</span><span class="sxs-lookup"><span data-stu-id="31248-112">If you need Enterprise Voice (PSTN telephony) using telephony service providers for Skype Room Systems v2 you need Skype for Business Online (Plan 3).</span></span>
    
- <span data-ttu-id="31248-113">Os usuários de Inquilino devem ter caixas de correio do Exchange.</span><span class="sxs-lookup"><span data-stu-id="31248-113">Your tenant users must have Exchange mailboxes.</span></span>
    
- <span data-ttu-id="31248-114">Sua conta de v2 de sistemas de sala Skype exigir um Skype para negócios Online (plano 2) ou Skype licença Business Online (plano 3), mas ele não requer uma licença do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="31248-114">Your Skype Room Systems v2 account does require a Skype for Business Online (Plan 2) or Skype for Business Online (Plan 3) license, but it does not require an Exchange Online license.</span></span>
    
### <a name="add-a-device-account"></a><span data-ttu-id="31248-115">Adicionar uma conta de dispositivo</span><span class="sxs-lookup"><span data-stu-id="31248-115">Add a device account</span></span>

1. <span data-ttu-id="31248-116">Inicie uma sessão remota do Windows PowerShell em um PC e se conectar ao Exchange.</span><span class="sxs-lookup"><span data-stu-id="31248-116">Start a remote Windows PowerShell session on a PC and connect to Exchange.</span></span> <span data-ttu-id="31248-117">Verifique se você tem as permissões apropriadas para executar os cmdlets associados.</span><span class="sxs-lookup"><span data-stu-id="31248-117">Be sure you have the right permissions set to run the associated cmdlets.</span></span> <span data-ttu-id="31248-118">Veja a seguir alguns exemplos de cmdlets que podem ser usados e modificados em seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="31248-118">The following are some examples of cmdlets that can be used and modified in your environment.</span></span>
    
   ```
   Set-ExecutionPolicy Unrestricted
   $org='contoso.com'
   $cred=Get-Credential $admin@$org
   $sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential 
   $cred -Authentication Basic -AllowRedirection
   Import-PSSession $sess
   ```

2. <span data-ttu-id="31248-119">Depois de estabelecer uma sessão, você vai criar uma nova caixa de correio e habilitá-lo como um RoomMailboxAccount ou alterar as configurações de uma caixa de correio de sala existente.</span><span class="sxs-lookup"><span data-stu-id="31248-119">After establishing a session, you'll either create a new mailbox and enable it as a RoomMailboxAccount, or change the settings for an existing room mailbox.</span></span> <span data-ttu-id="31248-120">Isso permitirá a conta para se autenticar v2 Skype sistemas de sala.</span><span class="sxs-lookup"><span data-stu-id="31248-120">This will allow the account to authenticate to Skype Room Systems v2.</span></span>
    
  <span data-ttu-id="31248-121">Se você estiver alterando uma caixa de correio do recurso existente:</span><span class="sxs-lookup"><span data-stu-id="31248-121">If you are changing an existing resource mailbox:</span></span>
    
   ```
   Set-Mailbox -Identity 'PROJECTRIGEL01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

  <span data-ttu-id="31248-122">Se você estiver criando uma nova caixa de correio de recursos:</span><span class="sxs-lookup"><span data-stu-id="31248-122">If you're creating a new resource mailbox:</span></span>
    
   ```
   New-Mailbox -MicrosoftOnlineServicesID PROJECTRIGEL01@contoso.com -Alias PROJECTRIGEL01 
-Name "Project-Rigel-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword
 (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. <span data-ttu-id="31248-p105">Várias propriedades do Exchange deverão ser definidas na conta de dispositivo para aprimorar a experiência de reunião. Para saber quais propriedades precisam ser definidas, confira a seção Propriedades do Exchange.</span><span class="sxs-lookup"><span data-stu-id="31248-p105">Various Exchange properties must be set on the device account to improve the meeting experience. You can see which properties need to be set in the Exchange properties section.</span></span>
    
   ```
   Set-CalendarProcessing -Identity $acctUpn -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false
   -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity $acctUpn -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"

   ```

4. <span data-ttu-id="31248-125">Você deverá conectar-se ao Azure Active Directory para aplicar algumas configurações à conta.</span><span class="sxs-lookup"><span data-stu-id="31248-125">You will need to connect to Azure Active Directory to apply some account settings.</span></span> <span data-ttu-id="31248-126">Para se conectar ao Azure AD, execute o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="31248-126">To connect to Azure AD, run the following cmdlet:</span></span>
    
   ```
   Connect-MsolService -Credential $cred
   ```

5. <span data-ttu-id="31248-127">	Para a senha não expirar, execute o cmdlet Set-MsolUser com a opção PasswordNeverExpires, como a seguir:  </span><span class="sxs-lookup"><span data-stu-id="31248-127">If you do not want the password to expire, run the Set-MsolUser cmdlet with the PasswordNeverExpires option as follows:</span></span> 
    
   ```
   Set-MsolUser -UserPrincipalName $acctUpn -PasswordNeverExpires $true
   ```

   <span data-ttu-id="31248-128">Você também pode definir um número de telefone para a sala da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="31248-128">You can also set a phone number for the room as follows:</span></span>
    
   ```
   Set-MsolUser -UniversalPrincipalName <upn> -PhoneNumber <phone number>
   ```

6. <span data-ttu-id="31248-129">A conta do dispositivo precisa ter uma licença válida do Office 365 ou Exchange e Skype para negócios não funcionará.</span><span class="sxs-lookup"><span data-stu-id="31248-129">The device account needs to have a valid Office 365 license, or Exchange and Skype for Business will not work.</span></span> <span data-ttu-id="31248-130">Se você tem a licença, deve atribuir um local de uso à conta de dispositivo (isso determina quais SKUs de licença estão disponíveis para sua conta).</span><span class="sxs-lookup"><span data-stu-id="31248-130">If you have the license, you need to assign a usage location to your device account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="31248-131">Você pode usar o Get-MsolAccountSku para recuperar uma lista de SKUs disponíveis para seu locatário do Office 365, da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="31248-131">You can use Get-MsolAccountSku to retrieve a list of available SKUs for your Office 365 tenant as follows:</span></span>
    
   ```
   Get-MsolAccountSku
   ```

   <span data-ttu-id="31248-p108">Em seguida, você pode adicionar uma licença usando o cmdlet Set-MsolUserLicense. Nesse caso, $strLicense é o código de SKU que você vê (por exemplo, contoso:STANDARDPACK).</span><span class="sxs-lookup"><span data-stu-id="31248-p108">Next, you can add a license using the Set-MsolUserLicense cmdlet. In this case, $strLicense is the SKU code that you see (for example, contoso:STANDARDPACK).</span></span>
    
   ```
   Set-MsolUser -UserPrincipalName $acctUpn -UsageLocation "US"
   Get-MsolAccountSku
   Set-MsolUserLicense -UserPrincipalName $acctUpn -AddLicenses $strLicense
   ```

7. <span data-ttu-id="31248-134">Em seguida, você precisará habilitar a conta de dispositivo com Skype para negócios.</span><span class="sxs-lookup"><span data-stu-id="31248-134">Next, you need to enable the device account with Skype for Business.</span></span> <span data-ttu-id="31248-135">Certifique-se de que seu ambiente atende aos requisitos definidos em [sistemas de sala Skype v2 requirements](../../plan-your-deployment/clients-and-devices/requirements.md).</span><span class="sxs-lookup"><span data-stu-id="31248-135">Be sure your environment meets the requirements defined in [Skype Room Systems v2 requirements](../../plan-your-deployment/clients-and-devices/requirements.md).</span></span>
    
   <span data-ttu-id="31248-136">Iniciar uma sessão do Windows PowerShell remota da seguinte maneira (certifique-se de instalar o Skype para componentes de negócios Online PowerShell):</span><span class="sxs-lookup"><span data-stu-id="31248-136">Start a remote Windows PowerShell session as follows (be sure to install Skype for Business Online PowerShell components):</span></span>
    
   ```
   Import-Module LyncOnlineConnector  
   $cssess=New-CsOnlineSession -Credential $cred  
   Import-PSSession $cssess -AllowClobber
   ```

   <span data-ttu-id="31248-137">Em seguida, habilite sua conta do Skype sala sistemas v2 para Skype para Business Server executando o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="31248-137">Next, enable your Skype Room Systems v2 account for Skype for Business Server by running the following cmdlet:</span></span>
    
   ```
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

   <span data-ttu-id="31248-138">Obtenha as informações de RegistrarPool da nova conta de usuário sendo instalação, como mostrado neste exemplo:</span><span class="sxs-lookup"><span data-stu-id="31248-138">Obtain the RegistrarPool information from the new user account being setup, as shown in this example:</span></span>
    
    ```
    Get-CsOnlineUser -Identity $rm | Select -Expand RegistrarPool
    ```

    > [!NOTE]
    > <span data-ttu-id="31248-139">Novas contas de usuário não podem ser criadas no mesmo pool do registrador contas de usuário existentes no inquilino.</span><span class="sxs-lookup"><span data-stu-id="31248-139">New user accounts might not be created on the same registrar pool as existing user accounts in the tenant.</span></span> <span data-ttu-id="31248-140">O comando acima evitará erros na configuração de conta devido a essa situação.</span><span class="sxs-lookup"><span data-stu-id="31248-140">The command above will prevent errors in account setup due to this situation.</span></span> 
  
<span data-ttu-id="31248-141">Depois de concluir as etapas anteriores para habilitar sua conta v2 de sistemas de sala Skype no Skype para Business Online, você precisa atribuir uma licença a dispositivo de v2 Skype sistemas de sala.</span><span class="sxs-lookup"><span data-stu-id="31248-141">After you've completed the preceding steps to enable your Skype Room Systems v2 account in Skype for Business Online, you need to assign a license to Skype Room Systems v2 device.</span></span> <span data-ttu-id="31248-142">Usando o portal administrativo do Office 365, atribua a qualquer um Skype para Business Online (plano 2) ou uma Skype licença Business Online (plano 3) para o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="31248-142">Using the Office 365 administrative portal, assign either a Skype for Business Online (Plan 2) or a Skype for Business Online (Plan 3) license to the device.</span></span>
  
### <a name="assign-a-license-to-your-account"></a><span data-ttu-id="31248-143">Atribuir uma licença à conta</span><span class="sxs-lookup"><span data-stu-id="31248-143">Assign a license to your account</span></span>

1. <span data-ttu-id="31248-144">Logon como um administrador de locatário, abra o Portal do Office 365 administrativas e clique no aplicativo Administração.</span><span class="sxs-lookup"><span data-stu-id="31248-144">Login as a tenant administrator, open the Office 365 Administrative Portal, and click on the Admin app.</span></span>
    
2. <span data-ttu-id="31248-145">Clique em **Usuários e Grupos** e clique em **Adicionar usuários, redefinir senhas e muito mais**.</span><span class="sxs-lookup"><span data-stu-id="31248-145">Click **Users and Groups** and then click **Add users, reset passwords, and more**.</span></span>
    
3. <span data-ttu-id="31248-146">Selecione a conta do Skype sala sistemas v2 e, em seguida, clique ou toque no ícone de caneta, o que significa editar.</span><span class="sxs-lookup"><span data-stu-id="31248-146">Select the Skype Room Systems v2 account, and then click or tap the pen icon, which means edit.</span></span>
    
4. <span data-ttu-id="31248-147">Clique na opção **Licenças**.</span><span class="sxs-lookup"><span data-stu-id="31248-147">Click on the **Licenses** option.</span></span>
    
5. <span data-ttu-id="31248-148">Na seção **Atribuir licenças** , você precisa selecionar o Skype para Business Online (plano 2) ou Skype para Business Online (plano 3), dependendo do seu licenciamento e o que você decidiu em termos de necessidade de Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="31248-148">In the **Assign licenses** section, you need to select Skype for Business Online (Plan 2) or Skype for Business Online (Plan 3), depending on your licensing and what you've decided in terms of needing Enterprise Voice.</span></span> <span data-ttu-id="31248-149">Você terá que usar uma licença de plano 3 se você quiser usar o PBX de nuvem em sistemas de sala Skype v2.</span><span class="sxs-lookup"><span data-stu-id="31248-149">You'll have to use a Plan 3 license if you want to use Cloud PBX on Skype Room Systems v2.</span></span> <span data-ttu-id="31248-150">O CloudPBX será necessário como requisito mínimo para habilitar a conectividade de voz.</span><span class="sxs-lookup"><span data-stu-id="31248-150">Minimally you will need CloudPBX for voice connectivity.</span></span> <span data-ttu-id="31248-151">Em seguida, configure as chamadas PSTN ou de voz híbridas com base no método de conectividade PSTN.</span><span class="sxs-lookup"><span data-stu-id="31248-151">Then configure hybrid voice or PSTN calling based on the PSTN connectivity method.</span></span>
    
6. <span data-ttu-id="31248-152">Clique em **Salvar** para concluir a tarefa.</span><span class="sxs-lookup"><span data-stu-id="31248-152">Click **Save** to complete the task.</span></span>
    
## <a name="sample-room-account-setup-in-exchange-online-and-skype-for-business-online"></a><span data-ttu-id="31248-153">Exemplo: Conta de sala de instalação no Exchange Online e Skype para negócios Online</span><span class="sxs-lookup"><span data-stu-id="31248-153">Sample: Room account setup in Exchange Online and Skype for Business Online</span></span>

```
New-Mailbox -MicrosoftOnlineServicesID Rigel1@contoso.com
 -Alias rigel1 -Name "Rigel 1" -Room -EnableRoomMailboxAccount $true
 -RoomMailboxPassword (ConvertTo-SecureString -String "" -AsPlainText -Force)
 
Set-CalendarProcessing -Identity rigel1 -AutomateProcessing AutoAccept 
-AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments 
$false -DeleteSubject $false -RemovePrivateProperty $false
 
Set-CalendarProcessing -Identity rigel1 -AddAdditionalResponse $true 
-AdditionalResponse "This is a Rigel room!"
 
Set-MsolUser -UserPrincipalName rigel1@contoso.com -PasswordNeverExpires $true -UsageLocation "US"
 
Set-MsolUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:O365_BUSINESS_PREMIUM"
Set-MsolUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:MCOEV"
Set-MsolUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:MCOPSTN2"
 
Enable-CsMeetingRoom -Identity rigel1@contoso.onmicrosoft.com -RegistrarPool sippooldm21a05.infra.lync.com
-SipAddressType EmailAddress

```

> [!NOTE]
> <span data-ttu-id="31248-p113">Assim, você adiciona CloudPBX e PSTNCallingDomesticAndInternational. Além disso, será necessário usar a Interface do administrador para atribuir um número de telefone.</span><span class="sxs-lookup"><span data-stu-id="31248-p113">This adds CloudPBX and PSTNCallingDomesticAndInternational. Addtionally, you will need to use the Admin interface to assign a phone number.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="31248-156">Consulte também</span><span class="sxs-lookup"><span data-stu-id="31248-156">See also</span></span>

#### 

[<span data-ttu-id="31248-157">Planejar a sala Skype v2 de sistemas</span><span class="sxs-lookup"><span data-stu-id="31248-157">Plan for Skype Room Systems v2</span></span>](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[<span data-ttu-id="31248-158">Implantar Skype sala v2 de sistemas</span><span class="sxs-lookup"><span data-stu-id="31248-158">Deploy Skype Room Systems v2</span></span>](room-systems-v2.md)
  
[<span data-ttu-id="31248-159">Configurar um console v2 de sistemas de sala do Skype</span><span class="sxs-lookup"><span data-stu-id="31248-159">Configure a Skype Room Systems v2 console</span></span>](console.md)
  
[<span data-ttu-id="31248-160">Gerenciar Skype sala v2 de sistemas</span><span class="sxs-lookup"><span data-stu-id="31248-160">Manage Skype Room Systems v2</span></span>](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)

