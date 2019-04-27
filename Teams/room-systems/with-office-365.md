---
title: Implantar salas de equipes da Microsoft com o Office 365
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
- M365-voice
ms.custom: ''
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: Leia este tópico para obter informações sobre como implantar as salas de equipes da Microsoft com o Office 365.
ms.openlocfilehash: 462f5a6727a3c67e221b0d7ac019849ed3eb6f52
ms.sourcegitcommit: 79ec789a22acf1686c33a5cc8ba3bd50049f94b8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/26/2019
ms.locfileid: "33362580"
---
# <a name="deploy-microsoft-teams-rooms-with-office-365"></a><span data-ttu-id="083d2-103">Implantar salas de equipes da Microsoft com o Office 365</span><span class="sxs-lookup"><span data-stu-id="083d2-103">Deploy Microsoft Teams Rooms with Office 365</span></span>

<span data-ttu-id="083d2-104">Leia este tópico para obter informações sobre como implantar as salas de equipes da Microsoft com o Office 365, onde Teams da Microsoft ou Skype para negócios e do Exchange são ambos online.</span><span class="sxs-lookup"><span data-stu-id="083d2-104">Read this topic for information on how to deploy Microsoft Teams Rooms with Office 365, where Microsoft Teams or Skype for Business and Exchange are both online.</span></span>

<span data-ttu-id="083d2-105">A maneira mais fácil de configurar as contas de usuário é configurá-los usando o Windows PowerShell remoto.</span><span class="sxs-lookup"><span data-stu-id="083d2-105">The easiest way to set up user accounts is to configure them using remote Windows PowerShell.</span></span> <span data-ttu-id="083d2-106">A Microsoft fornece [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), um script que ajudarão a criar novas contas de usuário ou validar contas existentes de recurso, que você ter para ajudá-lo a transformá-los em contas de usuário de salas de equipes da Microsoft compatíveis.</span><span class="sxs-lookup"><span data-stu-id="083d2-106">Microsoft provides [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), a script that will help create new user accounts, or validate existing resource accounts you have in order to help you turn them into compatible Microsoft Teams Rooms user accounts.</span></span> <span data-ttu-id="083d2-107">Se você preferir, você pode seguir as etapas abaixo para configurar contas para que seu dispositivo de salas de equipes da Microsoft usará.</span><span class="sxs-lookup"><span data-stu-id="083d2-107">If you prefer, you can follow the steps below to configure accounts your Microsoft Teams Rooms device will use.</span></span>

## <a name="requirements"></a><span data-ttu-id="083d2-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="083d2-108">Requirements</span></span>

<span data-ttu-id="083d2-109">Antes de implantar salas de equipes da Microsoft com o Office 365, certifique-se de que você cumpre os requisitos.</span><span class="sxs-lookup"><span data-stu-id="083d2-109">Before you deploy Microsoft Teams Rooms with Office 365, be sure you have met the requirements.</span></span> <span data-ttu-id="083d2-110">Para obter mais informações, consulte [requisitos de salas de equipes da Microsoft](requirements.md).</span><span class="sxs-lookup"><span data-stu-id="083d2-110">For more information, see [Microsoft Teams Rooms requirements](requirements.md).</span></span>

<span data-ttu-id="083d2-111">Para habilitar o Skype para a empresa, você deve ter o seguinte:</span><span class="sxs-lookup"><span data-stu-id="083d2-111">To enable Skype for Business, you must have the following:</span></span>

- <span data-ttu-id="083d2-112">Skype para negócios Online (plano 2, ou um plano de empresa) ou superior no seu plano do Office 365.</span><span class="sxs-lookup"><span data-stu-id="083d2-112">Skype for Business Online (Plan 2, or an Enterprise-based plan) or higher in your Office 365 plan.</span></span> <span data-ttu-id="083d2-113">O plano deve permitir que os recursos de conferência discada.</span><span class="sxs-lookup"><span data-stu-id="083d2-113">The plan needs to allow dial-in conferencing capabilities.</span></span>

- <span data-ttu-id="083d2-114">Se você precisar de recursos de dial-in de uma reunião, você precisará uma conferência de áudio e a licença do sistema telefônico.</span><span class="sxs-lookup"><span data-stu-id="083d2-114">If you need dial-in capabilities from a meeting, you will need an audio conferencing and Phone System license.</span></span>  <span data-ttu-id="083d2-115">Se você precisar de recursos de discagem de uma reunião, será necessário um locais ou nacionais e internacionais chamar planejar.</span><span class="sxs-lookup"><span data-stu-id="083d2-115">If you need dial-out capabilities from a meeting, you will need a domestic or domestic and international Calling Plan.</span></span>

- <span data-ttu-id="083d2-116">Os usuários de Inquilino devem ter caixas de correio do Exchange.</span><span class="sxs-lookup"><span data-stu-id="083d2-116">Your tenant users must have Exchange mailboxes.</span></span>

- <span data-ttu-id="083d2-117">Sua conta da Microsoft equipes salas exigir no mínimo um Skype licença Business Online (plano 2), mas ele não requer uma licença do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="083d2-117">Your Microsoft Teams Rooms account does require at a minimum a Skype for Business Online (Plan 2) license, but it does not require an Exchange Online license.</span></span> <span data-ttu-id="083d2-118">Para obter detalhes, consulte [Licenciamento de salas de equipes da Microsoft](/SfbOnline/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2.md) .</span><span class="sxs-lookup"><span data-stu-id="083d2-118">See [Microsoft Teams Rooms Licensing](/SfbOnline/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2.md) for details.</span></span>

<span data-ttu-id="083d2-119">Para obter detalhes sobre Skype para negócios Online planos, consulte o [Skype para negócios Online Service Description](https://technet.microsoft.com/library/jj822172.aspx).</span><span class="sxs-lookup"><span data-stu-id="083d2-119">For details on Skype for Business Online Plans, see the [Skype for Business Online Service Description](https://technet.microsoft.com/library/jj822172.aspx).</span></span>

### <a name="add-a-device-account"></a><span data-ttu-id="083d2-120">Adicionar uma conta de dispositivo</span><span class="sxs-lookup"><span data-stu-id="083d2-120">Add a device account</span></span>

1. <span data-ttu-id="083d2-121">Conecte-se para o Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="083d2-121">Connect to Exchange Online PowerShell.</span></span> <span data-ttu-id="083d2-122">Para obter instruções, consulte [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span><span class="sxs-lookup"><span data-stu-id="083d2-122">For instructions, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>

2. <span data-ttu-id="083d2-123">No PowerShell do Exchange Online, crie uma nova caixa de correio de sala ou modificar uma caixa de correio de sala existente.</span><span class="sxs-lookup"><span data-stu-id="083d2-123">In Exchange Online PowerShell, create a new room mailbox or modify an existing room mailbox.</span></span> <span data-ttu-id="083d2-124">Por padrão, caixas de correio de sala não têm contas associadas, portanto, você precisará adicionar uma conta ao criar ou modificar uma caixa de correio de sala que permite que ele autenticar com sistemas de sala Skype v2.</span><span class="sxs-lookup"><span data-stu-id="083d2-124">By default, room mailboxes don't have associated accounts, so you'll need to add an account when you create or modify a room mailbox that allows it to authenticate with Skype Room Systems v2.</span></span>

   - <span data-ttu-id="083d2-125">Para criar uma nova caixa de correio de sala, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="083d2-125">To create a new room mailbox, use the following syntax:</span></span>

     ``` PowerShell
     New-Mailbox -Name "<Unique Name>" -Alias <Alias> -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID <Account> -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     <span data-ttu-id="083d2-126">Este exemplo cria uma nova caixa de correio de sala com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="083d2-126">This example creates a new room mailbox with the following settings:</span></span>

     - <span data-ttu-id="083d2-127">Nome: Project-Rigel-01</span><span class="sxs-lookup"><span data-stu-id="083d2-127">Name: Project-Rigel-01</span></span>

     - <span data-ttu-id="083d2-128">Alias: ProjectRigel01</span><span class="sxs-lookup"><span data-stu-id="083d2-128">Alias: ProjectRigel01</span></span>

     - <span data-ttu-id="083d2-129">Conta: ProjectRigel01@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="083d2-129">Account: ProjectRigel01@contoso.onmicrosoft.com</span></span>

     - <span data-ttu-id="083d2-130">Senha da conta: P@$$W0rd5959</span><span class="sxs-lookup"><span data-stu-id="083d2-130">Account password: P@$$W0rd5959</span></span>

     ``` PowerShell
     New-Mailbox -Name "Project-Rigel-01" -Alias ProjectRigel01 -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID ProjectRigel01@contoso.onmicrosoft.com -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
     ```

   - <span data-ttu-id="083d2-131">Para modificar uma caixa de correio de sala existente, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="083d2-131">To modify an existing room mailbox, use the following syntax:</span></span>

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     <span data-ttu-id="083d2-132">Este exemplo habilita a conta para a caixa de correio de sala existente que tem o valor de alias ProjectRigel02 e define a senha como 9898P@$$W0rd.</span><span class="sxs-lookup"><span data-stu-id="083d2-132">This example enables the account for the existing room mailbox that has the alias value ProjectRigel02, and sets the password to 9898P@$$W0rd.</span></span> <span data-ttu-id="083d2-133">Observe que a conta seja ProjectRigel02@contoso.onmicrosoft.com devido ao valor existente do alias.</span><span class="sxs-lookup"><span data-stu-id="083d2-133">Note that the account will be ProjectRigel02@contoso.onmicrosoft.com because of the existing alias value.</span></span>

     ``` PowerShell
     Set-Mailbox -Identity ProjectRigel02 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '9898P@$$W0rd' -AsPlainText -Force)
     ```

   <span data-ttu-id="083d2-134">Para detalhadas sobre sintaxe e informações de parâmetro, consulte [New-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-mailbox) e [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox).</span><span class="sxs-lookup"><span data-stu-id="083d2-134">For detailed syntax and parameter information, see [New-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-mailbox) and [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox).</span></span>


3. <span data-ttu-id="083d2-135">No PowerShell do Exchange Online, defina as seguintes configurações na caixa de correio de sala para melhorar a experiência de reunião:</span><span class="sxs-lookup"><span data-stu-id="083d2-135">In Exchange Online PowerShell, configure the following settings on the room mailbox to improve the meeting experience:</span></span>

   - <span data-ttu-id="083d2-136">AutomateProcessing: AutoAccept (organizadores de reunião recebem a decisão de reserva de sala diretamente, sem intervenção humana: livre = aceitar; ocupado = recusar.)</span><span class="sxs-lookup"><span data-stu-id="083d2-136">AutomateProcessing: AutoAccept (Meeting organizers receive the room reservation decision directly without human intervention: free = accept; busy = decline.)</span></span>

   - <span data-ttu-id="083d2-137">AddOrganizerToSubject: $false (o organizador da reunião não é adicionado ao assunto da solicitação de reunião.)</span><span class="sxs-lookup"><span data-stu-id="083d2-137">AddOrganizerToSubject: $false (The meeting organizer is not added to the subject of the meeting request.)</span></span>

   - <span data-ttu-id="083d2-138">DeleteComments: $false (mantenha qualquer texto no corpo da mensagem de entrada solicitações de reunião).</span><span class="sxs-lookup"><span data-stu-id="083d2-138">DeleteComments: $false (Keep any text in the message body of incoming meeting requests.)</span></span>

   - <span data-ttu-id="083d2-139">DeleteSubject: $false (manter o assunto de solicitações de reunião recebidas).</span><span class="sxs-lookup"><span data-stu-id="083d2-139">DeleteSubject: $false (Keep the subject of incoming meeting requests.)</span></span>

   - <span data-ttu-id="083d2-140">RemovePrivateProperty: $false (assegura o sinalizador particular que foi enviado pelo organizador da reunião na reunião original permanece conforme especificado de solicitação).</span><span class="sxs-lookup"><span data-stu-id="083d2-140">RemovePrivateProperty: $false (Ensures the private flag that was sent by the meeting organizer in the original meeting request remains as specified.)</span></span>

   - <span data-ttu-id="083d2-141">AddAdditionalResponse: $true (o texto especificado pelo parâmetro AdditionalResponse é adicionado às solicitações de reunião).</span><span class="sxs-lookup"><span data-stu-id="083d2-141">AddAdditionalResponse: $true (The text specified by the AdditionalResponse parameter is added to meeting requests.)</span></span>

   - <span data-ttu-id="083d2-142">AdditionalResponse: "Esta é uma sala de reunião Skype!"</span><span class="sxs-lookup"><span data-stu-id="083d2-142">AdditionalResponse: "This is a Skype Meeting room!"</span></span> <span data-ttu-id="083d2-143">(O texto adicional para adicionar à solicitação de reunião).</span><span class="sxs-lookup"><span data-stu-id="083d2-143">(The additional text to add to the meeting request.)</span></span>

   <span data-ttu-id="083d2-144">Este exemplo configura essas configurações na caixa de correio de sala chamada Project-Rigel-01.</span><span class="sxs-lookup"><span data-stu-id="083d2-144">This example configures these settings on the room mailbox named Project-Rigel-01.</span></span>

   ``` PowerShell
   Set-CalendarProcessing -Identity "Project-Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   <span data-ttu-id="083d2-145">Para detalhadas sobre sintaxe e informações de parâmetro, consulte [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing).</span><span class="sxs-lookup"><span data-stu-id="083d2-145">For detailed syntax and parameter information, see [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing).</span></span>

4. <span data-ttu-id="083d2-146">Conectar-se ao MS Online PowerShell para fazer configurações do Active Directory, executando o `Connect-MsolService -Credential $cred` cmdlet do powershell.</span><span class="sxs-lookup"><span data-stu-id="083d2-146">Connect to MS Online PowerShell to make Active Directory settings by running the `Connect-MsolService -Credential $cred` powershell cmdlet.</span></span>   <span data-ttu-id="083d2-147">Para obter detalhes sobre o Active Directory, consulte o [Azure ActiveDirectory (MSOnline) 1.0](https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="083d2-147">For details about Active Directory, see [Azure ActiveDirectory (MSOnline) 1.0](https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-1.0).</span></span> <!-- or [Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-2.0) for the new module -->  
    1. <span data-ttu-id="083d2-148">Se você não quiser que a senha para expirar, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="083d2-148">If you do not want the password to expire, use the following syntax:</span></span>

    ``` PowerShell
    Set-MsolUser -UserPrincipalName $acctUpn -PasswordNeverExpires $true
    ```
<!--
   ``` PowerShell
   Set-AzureADUserPassword -UserPrincipalName <Account> -EnforceChangePasswordPolicy $false
   ```  -->

   <span data-ttu-id="083d2-149">Este exemplo define a senha para a conta ProjectRigel01@contoso.onmicrosoft.com para nunca expirar.</span><span class="sxs-lookup"><span data-stu-id="083d2-149">This example sets the password for the account ProjectRigel01@contoso.onmicrosoft.com to never expire.</span></span>

  ``` PowerShell
    Set-MsolUser -UserPrincipalName $acctUpn -PasswordNeverExpires $true
  ```
<!-- 
   ``` PowerShell
   Set-AzureADUserPassword -UserPrincipalName ProjectRigel01@contoso.onmicrosoft.com -EnforceChangePasswordPolicy $false
   ``` -->

   <span data-ttu-id="083d2-150">Você também pode definir um número de telefone para a conta executando o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="083d2-150">You can also set a phone number for the account by running the following command:</span></span>

  ``` PowerShell
    Set-MsolUser -UserPrincipalName <upn> -PhoneNumber <phone number>
  ```
<!-- 
   ``` PowerShell
   Set-AzureADUser -UserPrincipalName <Account> -PhoneNumber "<PhoneNumber>"
   ```  -->

6. <span data-ttu-id="083d2-151">A conta do dispositivo precisa ter uma licença válida do Office 365 ou Exchange e Microsoft Teams ou Skype para negócios não funcionará.</span><span class="sxs-lookup"><span data-stu-id="083d2-151">The device account needs to have a valid Office 365 license, or Exchange and Microsoft Teams or Skype for Business will not work.</span></span> <span data-ttu-id="083d2-152">Se você tem a licença, deve atribuir um local de uso à conta de dispositivo (isso determina quais SKUs de licença estão disponíveis para sua conta).</span><span class="sxs-lookup"><span data-stu-id="083d2-152">If you have the license, you need to assign a usage location to your device account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="083d2-153">Você pode usar`Get-MsolAccountSku`</span><span class="sxs-lookup"><span data-stu-id="083d2-153">You can use `Get-MsolAccountSku`</span></span> <!-- Get-AzureADSubscribedSku --> <span data-ttu-id="083d2-154">para recuperar uma lista de SKUs disponíveis para seu locatário do Office 365, da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="083d2-154">to retrieve a list of available SKUs for your Office 365 tenant as follows:</span></span>

  ``` Powershell
  Get-MsolAccountSku
  ```
<!--
   ``` Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ```  -->

   <span data-ttu-id="083d2-155">Em seguida, você pode adicionar uma licença usando o`Set-MsolUserLicense`</span><span class="sxs-lookup"><span data-stu-id="083d2-155">Next, you can add a license using the `Set-MsolUserLicense`</span></span> <!--Set-AzureADUserLicense --> <span data-ttu-id="083d2-156">cmdlet.</span><span class="sxs-lookup"><span data-stu-id="083d2-156">cmdlet.</span></span> <span data-ttu-id="083d2-157">Nesse caso, $strLicense é o código de SKU que você vê (por exemplo, contoso:STANDARDPACK).</span><span class="sxs-lookup"><span data-stu-id="083d2-157">In this case, $strLicense is the SKU code that you see (for example, contoso:STANDARDPACK).</span></span>

  ``` PowerShell
   Set-MsolUser -UserPrincipalName $acctUpn -UsageLocation "US"
   Get-MsolAccountSku
   Set-MsolUserLicense -UserPrincipalName $acctUpn -AddLicenses $strLicense
  ``` 
<!-- 
   ``` Powershell
   Set-AzureADUserLicense -UserPrincipalName $acctUpn -UsageLocation "US"
   Get-AzureADSubscribedSku
   Set-AzureADUserLicense -UserPrincipalName $acctUpn -AddLicenses $strLicense
   ```   -->

   <span data-ttu-id="083d2-158">Para obter instruções detalhadas, consulte [Atribuir licenças às contas de usuário com o Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="083d2-158">For detailed instructions, see [Assign licenses to user accounts with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

7. <span data-ttu-id="083d2-159">Em seguida, você precisará habilitar a conta de dispositivo com Skype para negócios.</span><span class="sxs-lookup"><span data-stu-id="083d2-159">Next, you need to enable the device account with Skype for Business.</span></span> <span data-ttu-id="083d2-160">Certifique-se de que seu ambiente atende aos requisitos definidos nas [salas de equipes da Microsoft requisitos](requirements.md).</span><span class="sxs-lookup"><span data-stu-id="083d2-160">Be sure your environment meets the requirements defined in [Microsoft Teams Rooms requirements](requirements.md).</span></span>

   <span data-ttu-id="083d2-161">Inicie uma [sessão do Windows PowerShell](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) de remota da seguinte maneira (certifique-se de [instalar o Skype para componentes de negócios Online PowerShell](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)):</span><span class="sxs-lookup"><span data-stu-id="083d2-161">Start a remote [Windows PowerShell session](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) as follows (be sure to [install Skype for Business Online PowerShell components](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)):</span></span>

   ``` Powershell
   Import-Module SkypeOnlineConnector  
   $cssess=New-CsOnlineSession -Credential $cred  
   Import-PSSession $cssess -AllowClobber
   ```

   <span data-ttu-id="083d2-162">Em seguida, habilite sua conta de salas de equipes da Microsoft para Skype para Business Server executando o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="083d2-162">Next, enable your Microsoft Teams Rooms account for Skype for Business Server by running the following cmdlet:</span></span>

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

   <span data-ttu-id="083d2-163">Obtenha as informações de RegistrarPool da nova conta de usuário sendo instalação, como mostrado neste exemplo:</span><span class="sxs-lookup"><span data-stu-id="083d2-163">Obtain the RegistrarPool information from the new user account being setup, as shown in this example:</span></span>

    ``` Powershell
    Get-CsOnlineUser -Identity $rm | Select -Expand RegistrarPool
    ```

    > [!NOTE]
    > <span data-ttu-id="083d2-164">Novas contas de usuário não podem ser criadas no mesmo pool do registrador contas de usuário existentes no inquilino.</span><span class="sxs-lookup"><span data-stu-id="083d2-164">New user accounts might not be created on the same registrar pool as existing user accounts in the tenant.</span></span> <span data-ttu-id="083d2-165">O comando acima evitará erros na configuração de conta devido a essa situação.</span><span class="sxs-lookup"><span data-stu-id="083d2-165">The command above will prevent errors in account setup due to this situation.</span></span>

<span data-ttu-id="083d2-166">Depois de concluir as etapas anteriores para habilitar a sua conta de salas de equipes da Microsoft em Microsoft Teams ou Skype para Business Online, você precisa atribuir uma licença a dispositivo de salas de equipes da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="083d2-166">After you've completed the preceding steps to enable your Microsoft Teams Rooms account in Microsoft Teams or Skype for Business Online, you need to assign a license to Microsoft Teams Rooms device.</span></span> <span data-ttu-id="083d2-167">Usando o portal administrativo do Office 365, atribua a qualquer um Skype para Business Online (plano 2) ou uma Skype licença Business Online (plano 3) para o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="083d2-167">Using the Office 365 administrative portal, assign either a Skype for Business Online (Plan 2) or a Skype for Business Online (Plan 3) license to the device.</span></span>

### <a name="assign-a-license-to-your-account"></a><span data-ttu-id="083d2-168">Atribuir uma licença à conta</span><span class="sxs-lookup"><span data-stu-id="083d2-168">Assign a license to your account</span></span>

1. <span data-ttu-id="083d2-169">Logon como um administrador de locatário, abra o Portal do Office 365 administrativas e clique no aplicativo Administração.</span><span class="sxs-lookup"><span data-stu-id="083d2-169">Login as a tenant administrator, open the Office 365 Administrative Portal, and click on the Admin app.</span></span>

2. <span data-ttu-id="083d2-170">Clique em **Usuários e Grupos** e clique em **Adicionar usuários, redefinir senhas e muito mais**.</span><span class="sxs-lookup"><span data-stu-id="083d2-170">Click **Users and Groups** and then click **Add users, reset passwords, and more**.</span></span>

3. <span data-ttu-id="083d2-171">Selecione a conta de salas de equipes da Microsoft e, em seguida, clique ou toque no ícone de caneta, o que significa editar.</span><span class="sxs-lookup"><span data-stu-id="083d2-171">Select the Microsoft Teams Rooms account, and then click or tap the pen icon, which means edit.</span></span>

4. <span data-ttu-id="083d2-172">Clique na opção **Licenças**.</span><span class="sxs-lookup"><span data-stu-id="083d2-172">Click on the **Licenses** option.</span></span>

5. <span data-ttu-id="083d2-173">Na seção **Atribuir licenças** , você precisa selecionar o Skype para Business Online (plano 2) ou Skype para Business Online (plano 3), dependendo do seu licenciamento e o que você decidiu em termos de necessidade de Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="083d2-173">In the **Assign licenses** section, you need to select Skype for Business Online (Plan 2) or Skype for Business Online (Plan 3), depending on your licensing and what you've decided in terms of needing Enterprise Voice.</span></span> <span data-ttu-id="083d2-174">Você terá que usar uma licença de plano 3 se você quiser usar o PBX de nuvem em salas de equipes da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="083d2-174">You'll have to use a Plan 3 license if you want to use Cloud PBX on Microsoft Teams Rooms.</span></span> <span data-ttu-id="083d2-175">O CloudPBX será necessário como requisito mínimo para habilitar a conectividade de voz.</span><span class="sxs-lookup"><span data-stu-id="083d2-175">Minimally you will need CloudPBX for voice connectivity.</span></span> <span data-ttu-id="083d2-176">Em seguida, configure as chamadas PSTN ou de voz híbridas com base no método de conectividade PSTN.</span><span class="sxs-lookup"><span data-stu-id="083d2-176">Then configure hybrid voice or PSTN calling based on the PSTN connectivity method.</span></span> <span data-ttu-id="083d2-177">Consulte [licenças de salas de equipes da Microsoft](https://docs.microsoft.com/en-us/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2) para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="083d2-177">See [Microsoft Teams Rooms licenses](https://docs.microsoft.com/en-us/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2) for more details.</span></span>

6. <span data-ttu-id="083d2-178">Clique em **Salvar** para concluir a tarefa.</span><span class="sxs-lookup"><span data-stu-id="083d2-178">Click **Save** to complete the task.</span></span>

## <a name="sample-room-account-setup-in-exchange-online-and-skype-for-business-online"></a><span data-ttu-id="083d2-179">Exemplo: Conta de sala de instalação no Exchange Online e Skype para negócios Online</span><span class="sxs-lookup"><span data-stu-id="083d2-179">Sample: Room account setup in Exchange Online and Skype for Business Online</span></span>

<span data-ttu-id="083d2-180">Comandos do PowerShell do Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="083d2-180">Exchange Online PowerShell commands:</span></span>

``` Powershell
New-Mailbox -MicrosoftOnlineServicesID Rigel1@contoso.com -Alias rigel1 -Name "Rigel 1" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)

Set-CalendarProcessing -Identity rigel1 -AutomateProcessing AutoAccept-AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true
-AdditionalResponse "This is a Rigel room!"
```

<span data-ttu-id="083d2-181">Comandos do Azure Active Directory PowerShell:</span><span class="sxs-lookup"><span data-stu-id="083d2-181">Azure Active Directory PowerShell commands:</span></span>

``` PowerShell
Set-MsolUser -UserPrincipalName rigel1@contoso.com -PasswordNeverExpires $true -UsageLocation "US"
Set-MsolUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:O365_BUSINESS_PREMIUM"
Set-MsolUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:MCOEV"
Set-MsolUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:MCOPSTN2"
```

<!-- 
``` PowerShell
Set-AzureADUserLicense -UserPrincipalName rigel1@contoso.com -PasswordNeverExpires $true -UsageLocation "US"
Set-AzureADUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:O365_BUSINESS_PREMIUM"
Set-AzureADUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:MCOEV"
Set-AzureADUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:MCOPSTN2"
```  -->

<span data-ttu-id="083d2-182">Skype para o comando do PowerShell de negócios:</span><span class="sxs-lookup"><span data-stu-id="083d2-182">Skype for Business PowerShell command:</span></span>

``` PowerShell
Enable-CsMeetingRoom -Identity rigel1@contoso.onmicrosoft.com -RegistrarPool sippooldm21a05.infra.lync.com
-SipAddressType EmailAddress
```

> [!NOTE]
> <span data-ttu-id="083d2-183">Assim, você adiciona CloudPBX e PSTNCallingDomesticAndInternational.</span><span class="sxs-lookup"><span data-stu-id="083d2-183">This adds CloudPBX and PSTNCallingDomesticAndInternational.</span></span> <span data-ttu-id="083d2-184">Além disso, você precisará usar a interface de administração para atribuir um número de telefone.</span><span class="sxs-lookup"><span data-stu-id="083d2-184">Additionally, you will need to use the Admin interface to assign a phone number.</span></span>

## <a name="validate"></a><span data-ttu-id="083d2-185">Validar</span><span class="sxs-lookup"><span data-stu-id="083d2-185">Validate</span></span>

<span data-ttu-id="083d2-186">Para validação, você deve ser capaz de usar qualquer Skype para o cliente de negócios para entrar com a conta que você criou.</span><span class="sxs-lookup"><span data-stu-id="083d2-186">For validation, you should be able to use any Skype for Business client to sign in to the account you created.</span></span>

## <a name="see-also"></a><span data-ttu-id="083d2-187">Confira também</span><span class="sxs-lookup"><span data-stu-id="083d2-187">See also</span></span>

[<span data-ttu-id="083d2-188">Configurar contas para salas de equipes da Microsoft</span><span class="sxs-lookup"><span data-stu-id="083d2-188">Configure accounts for Microsoft Teams Rooms</span></span>](room-systems-v2-configure-accounts.md)

[<span data-ttu-id="083d2-189">Planejar para salas de equipes da Microsoft</span><span class="sxs-lookup"><span data-stu-id="083d2-189">Plan for Microsoft Teams Rooms</span></span>](skype-room-systems-v2-0.md)

[<span data-ttu-id="083d2-190">Implantar salas de equipes da Microsoft</span><span class="sxs-lookup"><span data-stu-id="083d2-190">Deploy Microsoft Teams Rooms</span></span>](room-systems-v2.md)

[<span data-ttu-id="083d2-191">Configurar um console de salas de equipes da Microsoft</span><span class="sxs-lookup"><span data-stu-id="083d2-191">Configure a Microsoft Teams Rooms console</span></span>](console.md)

[<span data-ttu-id="083d2-192">Gerenciar Salas do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="083d2-192">Manage Microsoft Teams Rooms</span></span>](skype-room-systems-v2.md)

[<span data-ttu-id="083d2-193">Licenciamento de salas de equipes da Microsoft</span><span class="sxs-lookup"><span data-stu-id="083d2-193">Microsoft Teams Rooms Licensing</span></span>](/SfbOnline/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2.md)
