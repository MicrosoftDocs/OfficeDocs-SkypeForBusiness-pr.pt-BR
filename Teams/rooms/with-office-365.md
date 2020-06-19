---
title: Implantar salas do Microsoft Teams com o Microsoft 365 ou o Office 365
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-apr2020
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: Leia este tópico para obter informações sobre como implantar salas do Microsoft Teams com o Microsoft 365 ou o Office 365, em que o Teams ou o Skype for Business e o Exchange estão online.
ms.openlocfilehash: 440bf2f624bfd150f7e00f145770b0fda336deb4
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44756792"
---
# <a name="deploy-microsoft-teams-rooms-with-microsoft-365-or-office-365"></a><span data-ttu-id="522ec-103">Implantar salas do Microsoft Teams com o Microsoft 365 ou o Office 365</span><span class="sxs-lookup"><span data-stu-id="522ec-103">Deploy Microsoft Teams Rooms with Microsoft 365 or Office 365</span></span>

<span data-ttu-id="522ec-104">Leia este tópico para obter informações sobre como implantar salas do Microsoft Teams com o Microsoft 365 ou o Office 365, em que o Microsoft Teams ou o Skype for Business e o Exchange estão online.</span><span class="sxs-lookup"><span data-stu-id="522ec-104">Read this topic for information on how to deploy Microsoft Teams Rooms with Microsoft 365 or Office 365, where Microsoft Teams or Skype for Business and Exchange are both online.</span></span>

<span data-ttu-id="522ec-105">A maneira mais fácil de configurar contas de usuário é configurá-las usando o Windows PowerShell remoto.</span><span class="sxs-lookup"><span data-stu-id="522ec-105">The easiest way to set up user accounts is to configure them using remote Windows PowerShell.</span></span> <span data-ttu-id="522ec-106">A Microsoft fornece [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), um script que ajudará a criar novas contas de usuário ou validar as contas de recursos existentes que você tem para ajudar a transformá-las em contas de usuário de salas do Microsoft Teams compatíveis.</span><span class="sxs-lookup"><span data-stu-id="522ec-106">Microsoft provides [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), a script that will help create new user accounts, or validate existing resource accounts you have in order to help you turn them into compatible Microsoft Teams Rooms user accounts.</span></span> <span data-ttu-id="522ec-107">Se preferir, você pode seguir as etapas abaixo para configurar contas que o dispositivo de salas do Microsoft Teams vai usar.</span><span class="sxs-lookup"><span data-stu-id="522ec-107">If you prefer, you can follow the steps below to configure accounts your Microsoft Teams Rooms device will use.</span></span>

## <a name="requirements"></a><span data-ttu-id="522ec-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="522ec-108">Requirements</span></span>

<span data-ttu-id="522ec-109">Antes de implantar salas do Microsoft Teams com o Microsoft 365 ou o Office 365, certifique-se de que atenda aos requisitos.</span><span class="sxs-lookup"><span data-stu-id="522ec-109">Before you deploy Microsoft Teams Rooms with Microsoft 365 or Office 365, be sure you have met the requirements.</span></span> <span data-ttu-id="522ec-110">Para obter mais informações, consulte [requisitos de salas do Microsoft Teams](requirements.md).</span><span class="sxs-lookup"><span data-stu-id="522ec-110">For more information, see [Microsoft Teams Rooms requirements](requirements.md).</span></span>

<span data-ttu-id="522ec-111">Para habilitar o Skype for Business, você deve ter o seguinte:</span><span class="sxs-lookup"><span data-stu-id="522ec-111">To enable Skype for Business, you must have the following:</span></span>

- <span data-ttu-id="522ec-112">Skype for Business online (plano 2 ou plano baseado em empresas) ou superior em seu plano do Microsoft 365 ou do Office 365.</span><span class="sxs-lookup"><span data-stu-id="522ec-112">Skype for Business Online (Plan 2, or an Enterprise-based plan) or higher in your Microsoft 365 or Office 365 plan.</span></span> <span data-ttu-id="522ec-113">O plano precisa permitir recursos de conferência discada.</span><span class="sxs-lookup"><span data-stu-id="522ec-113">The plan needs to allow dial-in conferencing capabilities.</span></span>

- <span data-ttu-id="522ec-114">Se precisar de recursos de discagem de uma reunião, você precisará de uma conferência de áudio e uma licença do sistema de telefonia.</span><span class="sxs-lookup"><span data-stu-id="522ec-114">If you need dial-in capabilities from a meeting, you will need an Audio Conferencing and Phone System license.</span></span>  <span data-ttu-id="522ec-115">Se precisar de recursos de discagem de uma reunião, será necessária uma licença de audioconferência.</span><span class="sxs-lookup"><span data-stu-id="522ec-115">If you need dial-out capabilities from a meeting, you will need an Audio Conferencing license.</span></span>

- <span data-ttu-id="522ec-116">Os usuários do locatário devem ter caixas de correio do Exchange.</span><span class="sxs-lookup"><span data-stu-id="522ec-116">Your tenant users must have Exchange mailboxes.</span></span>

- <span data-ttu-id="522ec-117">Sua conta de salas do Microsoft Teams requer pelo menos uma licença do Skype for Business online (plano 2), mas não requer uma licença do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="522ec-117">Your Microsoft Teams Rooms account does require at a minimum a Skype for Business Online (Plan 2) license, but it does not require an Exchange Online license.</span></span> <span data-ttu-id="522ec-118">Consulte [licenças de salas do Microsoft Teams](rooms-licensing.md) para obter detalhes.</span><span class="sxs-lookup"><span data-stu-id="522ec-118">See [Microsoft Teams Rooms licenses](rooms-licensing.md) for details.</span></span>

<span data-ttu-id="522ec-119">Para obter detalhes sobre os planos do Skype for Business Online, consulte a [Descrição do serviço do Skype for Business online](https://technet.microsoft.com/library/jj822172.aspx).</span><span class="sxs-lookup"><span data-stu-id="522ec-119">For details on Skype for Business Online Plans, see the [Skype for Business Online Service Description](https://technet.microsoft.com/library/jj822172.aspx).</span></span>

### <a name="add-a-device-account"></a><span data-ttu-id="522ec-120">Adicionar uma conta de dispositivo</span><span class="sxs-lookup"><span data-stu-id="522ec-120">Add a device account</span></span>

1. <span data-ttu-id="522ec-121">Conecte-se ao PowerShell do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="522ec-121">Connect to Exchange Online PowerShell.</span></span> <span data-ttu-id="522ec-122">Para obter instruções, consulte [conectar ao Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span><span class="sxs-lookup"><span data-stu-id="522ec-122">For instructions, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>

2. <span data-ttu-id="522ec-123">No PowerShell do Exchange Online, crie uma nova caixa de correio de sala ou modifique uma caixa de correio de sala existente.</span><span class="sxs-lookup"><span data-stu-id="522ec-123">In Exchange Online PowerShell, create a new room mailbox or modify an existing room mailbox.</span></span> <span data-ttu-id="522ec-124">Por padrão, as caixas de correio da sala não têm contas associadas, portanto, você precisará adicionar uma conta ao criar ou modificar uma caixa de correio de sala que permita que ela seja autenticada com o Skype Room Systems v2.</span><span class="sxs-lookup"><span data-stu-id="522ec-124">By default, room mailboxes don't have associated accounts, so you'll need to add an account when you create or modify a room mailbox that allows it to authenticate with Skype Room Systems v2.</span></span>

   - <span data-ttu-id="522ec-125">Para criar uma nova caixa de correio de sala, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="522ec-125">To create a new room mailbox, use the following syntax:</span></span>

     ``` PowerShell
     New-Mailbox -Name "<Unique Name>" -Alias <Alias> -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID <Account> -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     <span data-ttu-id="522ec-126">Este exemplo cria uma nova caixa de correio de sala com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="522ec-126">This example creates a new room mailbox with the following settings:</span></span>

     - <span data-ttu-id="522ec-127">Nome: Rigel-01</span><span class="sxs-lookup"><span data-stu-id="522ec-127">Name: Rigel-01</span></span>

     - <span data-ttu-id="522ec-128">Alias: Rigel1</span><span class="sxs-lookup"><span data-stu-id="522ec-128">Alias: Rigel1</span></span>

     - <span data-ttu-id="522ec-129">Conta: Rigel1@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="522ec-129">Account: Rigel1@contoso.onmicrosoft.com</span></span>

     - <span data-ttu-id="522ec-130">Senha da conta: P@ $ $W 0rd5959</span><span class="sxs-lookup"><span data-stu-id="522ec-130">Account password: P@$$W0rd5959</span></span>

     ``` PowerShell
     New-Mailbox -Name "Rigel-01" -Alias Rigel1 -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID Rigel1@contoso.onmicrosoft.com -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
     ```

   - <span data-ttu-id="522ec-131">Para modificar uma caixa de correio de sala existente, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="522ec-131">To modify an existing room mailbox, use the following syntax:</span></span>

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     <span data-ttu-id="522ec-132">Este exemplo habilita a conta da caixa de correio de sala existente que tem o valor do alias Rigel2 e define a senha como 9898P@ $ $W 0rd.</span><span class="sxs-lookup"><span data-stu-id="522ec-132">This example enables the account for the existing room mailbox that has the alias value Rigel2, and sets the password to 9898P@$$W0rd.</span></span> <span data-ttu-id="522ec-133">Observe que a conta será Rigel2@contoso.onmicrosoft.comda por causa do valor de alias existente.</span><span class="sxs-lookup"><span data-stu-id="522ec-133">Note that the account will be Rigel2@contoso.onmicrosoft.com because of the existing alias value.</span></span>

     ``` PowerShell
     Set-Mailbox -Identity Rigel2 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '9898P@$$W0rd' -AsPlainText -Force)
     ```

   <span data-ttu-id="522ec-134">Para obter informações detalhadas sobre a sintaxe e o parâmetro, consulte [novo-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-mailbox) e [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox).</span><span class="sxs-lookup"><span data-stu-id="522ec-134">For detailed syntax and parameter information, see [New-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-mailbox) and [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox).</span></span>


3. <span data-ttu-id="522ec-135">No PowerShell do Exchange Online, defina as seguintes configurações na caixa de correio da sala para melhorar a experiência da reunião:</span><span class="sxs-lookup"><span data-stu-id="522ec-135">In Exchange Online PowerShell, configure the following settings on the room mailbox to improve the meeting experience:</span></span>

   - <span data-ttu-id="522ec-136">AutomateProcessing: a aceitação autoaceitar (os organizadores de reunião recebem a decisão de reserva de sala diretamente sem intervenção humana: grátis = aceitar; Busy = recusar.)</span><span class="sxs-lookup"><span data-stu-id="522ec-136">AutomateProcessing: AutoAccept (Meeting organizers receive the room reservation decision directly without human intervention: free = accept; busy = decline.)</span></span>

   - <span data-ttu-id="522ec-137">AddOrganizerToSubject: $false (o organizador da reunião não é adicionado ao assunto da solicitação de reunião.)</span><span class="sxs-lookup"><span data-stu-id="522ec-137">AddOrganizerToSubject: $false (The meeting organizer is not added to the subject of the meeting request.)</span></span>

   - <span data-ttu-id="522ec-138">DeleteComments: $false (Mantenha qualquer texto no corpo da mensagem de solicitações de reunião recebidas.)</span><span class="sxs-lookup"><span data-stu-id="522ec-138">DeleteComments: $false (Keep any text in the message body of incoming meeting requests.)</span></span>

   - <span data-ttu-id="522ec-139">DeleteSubject: $false (Mantenha o assunto das solicitações de reunião recebidas.)</span><span class="sxs-lookup"><span data-stu-id="522ec-139">DeleteSubject: $false (Keep the subject of incoming meeting requests.)</span></span>

   - <span data-ttu-id="522ec-140">RemovePrivateProperty: $false (garante que o sinalizador particular enviado pelo organizador da reunião na solicitação de reunião original permaneça conforme especificado.)</span><span class="sxs-lookup"><span data-stu-id="522ec-140">RemovePrivateProperty: $false (Ensures the private flag that was sent by the meeting organizer in the original meeting request remains as specified.)</span></span>

   - <span data-ttu-id="522ec-141">AddAdditionalResponse: $true (o texto especificado pelo parâmetro AdditionalResponse é adicionado a solicitações de reunião.)</span><span class="sxs-lookup"><span data-stu-id="522ec-141">AddAdditionalResponse: $true (The text specified by the AdditionalResponse parameter is added to meeting requests.)</span></span>

   - <span data-ttu-id="522ec-142">AdditionalResponse: "esta é uma sala de reunião do Skype!"</span><span class="sxs-lookup"><span data-stu-id="522ec-142">AdditionalResponse: "This is a Skype Meeting room!"</span></span> <span data-ttu-id="522ec-143">(O texto adicional a ser adicionado à solicitação de reunião.)</span><span class="sxs-lookup"><span data-stu-id="522ec-143">(The additional text to add to the meeting request.)</span></span>

   <span data-ttu-id="522ec-144">Este exemplo configura essas configurações na caixa de correio da sala chamada Rigel-01.</span><span class="sxs-lookup"><span data-stu-id="522ec-144">This example configures these settings on the room mailbox named Rigel-01.</span></span>

   ``` PowerShell
   Set-CalendarProcessing -Identity "Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   <span data-ttu-id="522ec-145">Para obter informações detalhadas de sintaxe e parâmetro, consulte [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing).</span><span class="sxs-lookup"><span data-stu-id="522ec-145">For detailed syntax and parameter information, see [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing).</span></span>

4. <span data-ttu-id="522ec-146">Conecte-se ao MS online PowerShell para fazer as configurações do Active Directory executando o `Connect-MsolService -Credential $cred` cmdlet do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="522ec-146">Connect to MS Online PowerShell to make Active Directory settings by running the `Connect-MsolService -Credential $cred` powershell cmdlet.</span></span>   <span data-ttu-id="522ec-147">Para obter detalhes sobre o Active Directory, consulte [Azure ActiveDirectory (MSOnline) 1,0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="522ec-147">For details about Active Directory, see [Azure ActiveDirectory (MSOnline) 1.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0).</span></span> 

   > [!NOTE]
   > <span data-ttu-id="522ec-148">Não há suporte para o [Azure Active Directory PowerShell 2,0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) .</span><span class="sxs-lookup"><span data-stu-id="522ec-148">[Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) is not supported.</span></span> 

5. <span data-ttu-id="522ec-149">Se você não quiser que a senha expire, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="522ec-149">If you do not want the password to expire, use the following syntax:</span></span>

   ```PowerShell
   Set-MsolUser -UserPrincipalName <upn> -PasswordNeverExpires $true
   ```
   <!--
   ```PowerShell
   Set-AzureADUserPassword -UserPrincipalName <Account> -EnforceChangePasswordPolicy $false
   ```  -->

   <span data-ttu-id="522ec-150">Este exemplo define a senha da conta Rigel1@contoso.onmicrosoft.com para nunca expirar.</span><span class="sxs-lookup"><span data-stu-id="522ec-150">This example sets the password for the account Rigel1@contoso.onmicrosoft.com to never expire.</span></span>

   ```PowerShell
   $acctUpn="Rigel1@contoso.onmicrosoft.com"
   Set-MsolUser -UserPrincipalName $acctUpn -PasswordNeverExpires $true
   ```
   <!-- 
   ```PowerShell
   Set-AzureADUserPassword -UserPrincipalName Rigel1@contoso.onmicrosoft.com -EnforceChangePasswordPolicy $false
   ``` -->

   <span data-ttu-id="522ec-151">Você também pode definir um número de telefone para a conta executando o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="522ec-151">You can also set a phone number for the account by running the following command:</span></span>

   ```PowerShell
   Set-MsolUser -UserPrincipalName <upn> -PhoneNumber <phone number>
   ```
   <!-- 
   ```PowerShell
   Set-AzureADUser -UserPrincipalName <Account> -PhoneNumber "<PhoneNumber>"
   ```  -->

6. <span data-ttu-id="522ec-152">A conta do dispositivo precisa ter uma licença válida do Microsoft 365 ou do Office 365 ou o Exchange e o Microsoft Teams ou o Skype for Business não funcionarão.</span><span class="sxs-lookup"><span data-stu-id="522ec-152">The device account needs to have a valid Microsoft 365 or Office 365 license, or Exchange and Microsoft Teams or Skype for Business will not work.</span></span> <span data-ttu-id="522ec-153">Se você tem a licença, deve atribuir um local de uso à conta de dispositivo (isso determina quais SKUs de licença estão disponíveis para sua conta).</span><span class="sxs-lookup"><span data-stu-id="522ec-153">If you have the license, you need to assign a usage location to your device account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="522ec-154">Você pode usar`Get-MsolAccountSku`</span><span class="sxs-lookup"><span data-stu-id="522ec-154">You can use `Get-MsolAccountSku`</span></span> <!-- Get-AzureADSubscribedSku --> <span data-ttu-id="522ec-155">para recuperar uma lista de SKUs disponíveis para a sua organização do Microsoft 365 ou do Office 365 da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="522ec-155">to retrieve a list of available SKUs for your Microsoft 365 or Office 365 organization as follows:</span></span>

   ```Powershell
   Get-MsolAccountSku
   ```
   <!--
   ```Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ```  -->

   <span data-ttu-id="522ec-156">Em seguida, você pode adicionar uma licença usando o`Set-MsolUserLicense`</span><span class="sxs-lookup"><span data-stu-id="522ec-156">Next, you can add a license using the `Set-MsolUserLicense`</span></span> <!--Set-AzureADUserLicense --> <span data-ttu-id="522ec-157">cmdlet.</span><span class="sxs-lookup"><span data-stu-id="522ec-157">cmdlet.</span></span> <span data-ttu-id="522ec-158">Nesse caso, $strLicense é o código de SKU que você vê (por exemplo, contoso:STANDARDPACK).</span><span class="sxs-lookup"><span data-stu-id="522ec-158">In this case, $strLicense is the SKU code that you see (for example, contoso:STANDARDPACK).</span></span>

   ```PowerShell
   $acctUpn="Rigel1@contoso.onmicrosoft.com"
   Set-MsolUser -UserPrincipalName $acctUpn -UsageLocation "US"
   Get-MsolAccountSku
   Set-MsolUserLicense -UserPrincipalName $acctUpn -AddLicenses $strLicense
   ``` 
   <!-- 
   ```Powershell
   Set-AzureADUserLicense -UserPrincipalName $acctUpn -UsageLocation "US"
   Get-AzureADSubscribedSku
   Set-AzureADUserLicense -UserPrincipalName $acctUpn -AddLicenses $strLicense
   ```   -->

   <span data-ttu-id="522ec-159">Para obter instruções detalhadas, consulte [atribuir licenças a contas de usuário com o Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="522ec-159">For detailed instructions, see [Assign licenses to user accounts with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

7. <span data-ttu-id="522ec-160">Em seguida, você precisa habilitar a conta do dispositivo com o Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="522ec-160">Next, you need to enable the device account with Skype for Business.</span></span> <span data-ttu-id="522ec-161">Certifique-se de que seu ambiente atenda aos requisitos definidos nos [requisitos de salas do Microsoft Teams](requirements.md).</span><span class="sxs-lookup"><span data-stu-id="522ec-161">Be sure your environment meets the requirements defined in [Microsoft Teams Rooms requirements](requirements.md).</span></span>

   <span data-ttu-id="522ec-162">Inicie uma sessão remota do [Windows PowerShell](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) da seguinte maneira (certifique [-se de instalar os componentes do PowerShell do Skype for Business online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)):</span><span class="sxs-lookup"><span data-stu-id="522ec-162">Start a remote [Windows PowerShell session](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) as follows (be sure to [install Skype for Business Online PowerShell components](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)):</span></span>

   ``` Powershell
   Import-Module SkypeOnlineConnector  
   $cssess=New-CsOnlineSession -Credential $cred  
   Import-PSSession $cssess -AllowClobber
   ```

   <span data-ttu-id="522ec-163">Em seguida, habilite a sua conta de salas do Microsoft Teams para o Skype for Business Server executando o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="522ec-163">Next, enable your Microsoft Teams Rooms account for Skype for Business Server by running the following cmdlet:</span></span>

   ``` Powershell
   $rm="Rigel1@contoso.onmicrosoft.com"
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

   <span data-ttu-id="522ec-164">Obtenha as informações de RegistrarPool da nova conta de usuário que está sendo configurada, conforme mostrado neste exemplo:</span><span class="sxs-lookup"><span data-stu-id="522ec-164">Obtain the RegistrarPool information from the new user account being setup, as shown in this example:</span></span>

    ``` Powershell
    $rm="Rigel1@contoso.onmicrosoft.com"
    Get-CsOnlineUser -Identity $rm | Select -Expand RegistrarPool
    ```

    > [!NOTE]
    > <span data-ttu-id="522ec-165">Não é possível criar novas contas de usuário no mesmo pool de registradores como contas de usuário existentes no locatário.</span><span class="sxs-lookup"><span data-stu-id="522ec-165">New user accounts might not be created on the same registrar pool as existing user accounts in the tenant.</span></span> <span data-ttu-id="522ec-166">O comando acima impedirá erros na configuração da conta devido a essa situação.</span><span class="sxs-lookup"><span data-stu-id="522ec-166">The command above will prevent errors in account setup due to this situation.</span></span>

### <a name="assign-a-license-to-your-account"></a><span data-ttu-id="522ec-167">Atribuir uma licença à conta</span><span class="sxs-lookup"><span data-stu-id="522ec-167">Assign a license to your account</span></span>

1. <span data-ttu-id="522ec-168">Faça logon como administrador de locatários, abra o centro de administração do Microsoft 365 e clique no aplicativo de administração.</span><span class="sxs-lookup"><span data-stu-id="522ec-168">Login as a tenant administrator, open the Microsoft 365 admin center, and click on the Admin app.</span></span>

2. <span data-ttu-id="522ec-169">Clique em **Usuários e Grupos** e clique em **Adicionar usuários, redefinir senhas e muito mais**.</span><span class="sxs-lookup"><span data-stu-id="522ec-169">Click **Users and Groups** and then click **Add users, reset passwords, and more**.</span></span>

3. <span data-ttu-id="522ec-170">Selecione a conta de salas do Microsoft Teams e, em seguida, clique ou toque no ícone de caneta, o que significa editar.</span><span class="sxs-lookup"><span data-stu-id="522ec-170">Select the Microsoft Teams Rooms account, and then click or tap the pen icon, which means edit.</span></span>

4. <span data-ttu-id="522ec-171">Clique na opção **Licenças**.</span><span class="sxs-lookup"><span data-stu-id="522ec-171">Click on the **Licenses** option.</span></span>

5. <span data-ttu-id="522ec-172">Na seção **atribuir licenças** , você precisa selecionar o Skype for Business online (plano 2) ou o Skype for Business online (plano 3), dependendo do seu licenciamento e do que você decidiu em termos de necessidade do Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="522ec-172">In the **Assign licenses** section, you need to select Skype for Business Online (Plan 2) or Skype for Business Online (Plan 3), depending on your licensing and what you've decided in terms of needing Enterprise Voice.</span></span> <span data-ttu-id="522ec-173">Você terá que usar uma licença do plano 3 se quiser usar o Cloud PBX em salas do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="522ec-173">You'll have to use a Plan 3 license if you want to use Cloud PBX on Microsoft Teams Rooms.</span></span> <span data-ttu-id="522ec-174">O CloudPBX será necessário como requisito mínimo para habilitar a conectividade de voz.</span><span class="sxs-lookup"><span data-stu-id="522ec-174">Minimally you will need CloudPBX for voice connectivity.</span></span> <span data-ttu-id="522ec-175">Em seguida, configure as chamadas PSTN ou de voz híbridas com base no método de conectividade PSTN.</span><span class="sxs-lookup"><span data-stu-id="522ec-175">Then configure hybrid voice or PSTN calling based on the PSTN connectivity method.</span></span> <span data-ttu-id="522ec-176">Consulte [licenças de salas do Microsoft Teams](rooms-licensing.md) para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="522ec-176">See [Microsoft Teams Rooms licenses](rooms-licensing.md) for more details.</span></span>

6. <span data-ttu-id="522ec-177">Clique em **Salvar** para concluir a tarefa.</span><span class="sxs-lookup"><span data-stu-id="522ec-177">Click **Save** to complete the task.</span></span>

## <a name="sample-room-account-setup-in-exchange-online-and-skype-for-business-online"></a><span data-ttu-id="522ec-178">Exemplo: configuração da conta de sala no Exchange Online e no Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="522ec-178">Sample: Room account setup in Exchange Online and Skype for Business Online</span></span>

<span data-ttu-id="522ec-179">Comandos do PowerShell do Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="522ec-179">Exchange Online PowerShell commands:</span></span>

``` Powershell
New-Mailbox -MicrosoftOnlineServicesID Rigel1@contoso.onmicrosoft.com -Alias rigel1 -Name "Rigel 1" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)

Set-CalendarProcessing -Identity rigel1 -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true
-AdditionalResponse "This is a Rigel room!"
```

<span data-ttu-id="522ec-180">Comandos do PowerShell do Azure Active Directory:</span><span class="sxs-lookup"><span data-stu-id="522ec-180">Azure Active Directory PowerShell commands:</span></span>

``` PowerShell
Set-MsolUser -UserPrincipalName rigel1@contoso.onmicrosoft.com -PasswordNeverExpires $true -UsageLocation "US"
Set-MsolUserLicense -UserPrincipalName rigel1@contoso.onmicrosoft.com -AddLicenses "sfblab:O365_BUSINESS_PREMIUM"
Set-MsolUserLicense -UserPrincipalName rigel1@contoso.onmicrosoft.com -AddLicenses "sfblab:MCOEV"
Set-MsolUserLicense -UserPrincipalName rigel1@contoso.onmicrosoft.com -AddLicenses "sfblab:MCOPSTN2"
```

<!-- 
``` PowerShell
Set-AzureADUserLicense -UserPrincipalName rigel1@contoso.onmicrosoft.com -PasswordNeverExpires $true -UsageLocation "US"
Set-AzureADUserLicense -UserPrincipalName rigel1@contoso.onmicrosoft.com -AddLicenses "sfblab:O365_BUSINESS_PREMIUM"
Set-AzureADUserLicense -UserPrincipalName rigel1@contoso.onmicrosoft.com -AddLicenses "sfblab:MCOEV"
Set-AzureADUserLicense -UserPrincipalName rigel1@contoso.onmicrosoft.com -AddLicenses "sfblab:MCOPSTN2"
```  -->

<span data-ttu-id="522ec-181">Comando do PowerShell do Skype for Business:</span><span class="sxs-lookup"><span data-stu-id="522ec-181">Skype for Business PowerShell command:</span></span>

``` PowerShell
Enable-CsMeetingRoom -Identity rigel1@contoso.onmicrosoft.com -RegistrarPool sippooldm21a05.infra.lync.com
-SipAddressType EmailAddress
```

> [!NOTE]
> <span data-ttu-id="522ec-182">Assim, você adiciona CloudPBX e PSTNCallingDomesticAndInternational.</span><span class="sxs-lookup"><span data-stu-id="522ec-182">This adds CloudPBX and PSTNCallingDomesticAndInternational.</span></span> <span data-ttu-id="522ec-183">Além disso, será necessário usar a interface do administrador para atribuir um número de telefone.</span><span class="sxs-lookup"><span data-stu-id="522ec-183">Additionally, you will need to use the Admin interface to assign a phone number.</span></span>

## <a name="validate"></a><span data-ttu-id="522ec-184">Válida</span><span class="sxs-lookup"><span data-stu-id="522ec-184">Validate</span></span>

<span data-ttu-id="522ec-185">Para a validação, você deve ser capaz de usar qualquer cliente Skype for Business para entrar na conta que você criou.</span><span class="sxs-lookup"><span data-stu-id="522ec-185">For validation, you should be able to use any Skype for Business client to sign in to the account you created.</span></span>

## <a name="see-also"></a><span data-ttu-id="522ec-186">Confira também</span><span class="sxs-lookup"><span data-stu-id="522ec-186">See also</span></span>

[<span data-ttu-id="522ec-187">Configurar contas para salas do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="522ec-187">Configure accounts for Microsoft Teams Rooms</span></span>](rooms-configure-accounts.md)

[<span data-ttu-id="522ec-188">Planejar as Salas do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="522ec-188">Plan for Microsoft Teams Rooms</span></span>](rooms-plan.md)

[<span data-ttu-id="522ec-189">Implantar Salas do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="522ec-189">Deploy Microsoft Teams Rooms</span></span>](rooms-deploy.md)

[<span data-ttu-id="522ec-190">Configurar um console de Salas do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="522ec-190">Configure a Microsoft Teams Rooms console</span></span>](console.md)

[<span data-ttu-id="522ec-191">Gerenciar Salas do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="522ec-191">Manage Microsoft Teams Rooms</span></span>](rooms-manage.md)

[<span data-ttu-id="522ec-192">Licenciamento de salas do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="522ec-192">Microsoft Teams Rooms Licensing</span></span>](rooms-licensing.md)
