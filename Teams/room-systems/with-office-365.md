---
title: Implantar Salas do Microsoft Teams com o Office 365
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: davgroom
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
- M365-voice
ms.custom: ''
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: Leia este tópico para obter informações sobre como implantar salas do Microsoft Teams com o Office 365.
ms.openlocfilehash: 9c1e14e9e5e7b32aa6ba4a1b08a2ae6ee8453d93
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36243229"
---
# <a name="deploy-microsoft-teams-rooms-with-office-365"></a><span data-ttu-id="8c059-103">Implantar Salas do Microsoft Teams com o Office 365</span><span class="sxs-lookup"><span data-stu-id="8c059-103">Deploy Microsoft Teams Rooms with Office 365</span></span>

<span data-ttu-id="8c059-104">Leia este tópico para obter informações sobre como implantar salas do Microsoft Teams com o Office 365, em que o Microsoft Teams ou o Skype for Business e o Exchange estão online.</span><span class="sxs-lookup"><span data-stu-id="8c059-104">Read this topic for information on how to deploy Microsoft Teams Rooms with Office 365, where Microsoft Teams or Skype for Business and Exchange are both online.</span></span>

<span data-ttu-id="8c059-105">A maneira mais fácil de configurar contas de usuário é configurá-las usando o Windows PowerShell remoto.</span><span class="sxs-lookup"><span data-stu-id="8c059-105">The easiest way to set up user accounts is to configure them using remote Windows PowerShell.</span></span> <span data-ttu-id="8c059-106">A Microsoft fornece [SkypeRoomProvisioningScript. ps1](https://go.microsoft.com/fwlink/?linkid=870105), um script que ajudará a criar novas contas de usuário ou validar as contas de recursos existentes que você tem para ajudar a transformá-las em contas de usuário compatíveis do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="8c059-106">Microsoft provides [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), a script that will help create new user accounts, or validate existing resource accounts you have in order to help you turn them into compatible Microsoft Teams Rooms user accounts.</span></span> <span data-ttu-id="8c059-107">Se preferir, você pode seguir as etapas abaixo para configurar contas que o dispositivo de salas do Microsoft Teams vai usar.</span><span class="sxs-lookup"><span data-stu-id="8c059-107">If you prefer, you can follow the steps below to configure accounts your Microsoft Teams Rooms device will use.</span></span>

## <a name="requirements"></a><span data-ttu-id="8c059-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8c059-108">Requirements</span></span>

<span data-ttu-id="8c059-109">Antes de implantar salas do Microsoft Teams com o Office 365, certifique-se de que atenda aos requisitos.</span><span class="sxs-lookup"><span data-stu-id="8c059-109">Before you deploy Microsoft Teams Rooms with Office 365, be sure you have met the requirements.</span></span> <span data-ttu-id="8c059-110">Para obter mais informações, consulte [requisitos de salas do Microsoft Teams](requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8c059-110">For more information, see [Microsoft Teams Rooms requirements](requirements.md).</span></span>

<span data-ttu-id="8c059-111">Para habilitar o Skype for Business, você deve ter o seguinte:</span><span class="sxs-lookup"><span data-stu-id="8c059-111">To enable Skype for Business, you must have the following:</span></span>

- <span data-ttu-id="8c059-112">Skype for Business online (plano 2 ou plano baseado em empresas) ou superior em seu plano do Office 365.</span><span class="sxs-lookup"><span data-stu-id="8c059-112">Skype for Business Online (Plan 2, or an Enterprise-based plan) or higher in your Office 365 plan.</span></span> <span data-ttu-id="8c059-113">O plano precisa permitir recursos de conferência discada.</span><span class="sxs-lookup"><span data-stu-id="8c059-113">The plan needs to allow dial-in conferencing capabilities.</span></span>

- <span data-ttu-id="8c059-114">Se precisar de recursos de discagem de uma reunião, você precisará de uma conferência de áudio e uma licença do sistema de telefonia.</span><span class="sxs-lookup"><span data-stu-id="8c059-114">If you need dial-in capabilities from a meeting, you will need an audio conferencing and Phone System license.</span></span>  <span data-ttu-id="8c059-115">Se precisar de recursos de discagem de uma reunião, você precisará de um plano de chamada internacional ou doméstico e internacional.</span><span class="sxs-lookup"><span data-stu-id="8c059-115">If you need dial-out capabilities from a meeting, you will need a domestic or domestic and international Calling Plan.</span></span>

- <span data-ttu-id="8c059-116">Os usuários do locatário devem ter caixas de correio do Exchange.</span><span class="sxs-lookup"><span data-stu-id="8c059-116">Your tenant users must have Exchange mailboxes.</span></span>

- <span data-ttu-id="8c059-117">Sua conta de salas do Microsoft Teams requer pelo menos uma licença do Skype for Business online (plano 2), mas não requer uma licença do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="8c059-117">Your Microsoft Teams Rooms account does require at a minimum a Skype for Business Online (Plan 2) license, but it does not require an Exchange Online license.</span></span> <span data-ttu-id="8c059-118">Consulte [licenças de salas do Microsoft Teams](skype-room-systems-v2.md) para obter detalhes.</span><span class="sxs-lookup"><span data-stu-id="8c059-118">See [Microsoft Teams Rooms licenses](skype-room-systems-v2.md) for details.</span></span>

<span data-ttu-id="8c059-119">Para obter detalhes sobre os planos do Skype for Business Online, consulte a [Descrição do serviço do Skype for Business online](https://technet.microsoft.com/library/jj822172.aspx).</span><span class="sxs-lookup"><span data-stu-id="8c059-119">For details on Skype for Business Online Plans, see the [Skype for Business Online Service Description](https://technet.microsoft.com/library/jj822172.aspx).</span></span>

### <a name="add-a-device-account"></a><span data-ttu-id="8c059-120">Adicionar uma conta de dispositivo</span><span class="sxs-lookup"><span data-stu-id="8c059-120">Add a device account</span></span>

1. <span data-ttu-id="8c059-121">Conecte-se ao PowerShell do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="8c059-121">Connect to Exchange Online PowerShell.</span></span> <span data-ttu-id="8c059-122">Para obter instruções, consulte [conectar ao Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span><span class="sxs-lookup"><span data-stu-id="8c059-122">For instructions, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>

2. <span data-ttu-id="8c059-123">No PowerShell do Exchange Online, crie uma nova caixa de correio de sala ou modifique uma caixa de correio de sala existente.</span><span class="sxs-lookup"><span data-stu-id="8c059-123">In Exchange Online PowerShell, create a new room mailbox or modify an existing room mailbox.</span></span> <span data-ttu-id="8c059-124">Por padrão, as caixas de correio da sala não têm contas associadas, portanto, você precisará adicionar uma conta ao criar ou modificar uma caixa de correio de sala que permita que ela seja autenticada com o Skype Room Systems v2.</span><span class="sxs-lookup"><span data-stu-id="8c059-124">By default, room mailboxes don't have associated accounts, so you'll need to add an account when you create or modify a room mailbox that allows it to authenticate with Skype Room Systems v2.</span></span>

   - <span data-ttu-id="8c059-125">Para criar uma nova caixa de correio de sala, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="8c059-125">To create a new room mailbox, use the following syntax:</span></span>

     ``` PowerShell
     New-Mailbox -Name "<Unique Name>" -Alias <Alias> -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID <Account> -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     <span data-ttu-id="8c059-126">Este exemplo cria uma nova caixa de correio de sala com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="8c059-126">This example creates a new room mailbox with the following settings:</span></span>

     - <span data-ttu-id="8c059-127">Nome: Project-Rigel-01</span><span class="sxs-lookup"><span data-stu-id="8c059-127">Name: Project-Rigel-01</span></span>

     - <span data-ttu-id="8c059-128">Alias: ProjectRigel01</span><span class="sxs-lookup"><span data-stu-id="8c059-128">Alias: ProjectRigel01</span></span>

     - <span data-ttu-id="8c059-129">Conta: ProjectRigel01@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="8c059-129">Account: ProjectRigel01@contoso.onmicrosoft.com</span></span>

     - <span data-ttu-id="8c059-130">Senha da conta: P @ $ $W 0rd5959</span><span class="sxs-lookup"><span data-stu-id="8c059-130">Account password: P@$$W0rd5959</span></span>

     ``` PowerShell
     New-Mailbox -Name "Project-Rigel-01" -Alias ProjectRigel01 -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID ProjectRigel01@contoso.onmicrosoft.com -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
     ```

   - <span data-ttu-id="8c059-131">Para modificar uma caixa de correio de sala existente, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="8c059-131">To modify an existing room mailbox, use the following syntax:</span></span>

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     <span data-ttu-id="8c059-132">Este exemplo habilita a conta da caixa de correio de sala existente que tem o valor do alias ProjectRigel02, e define a senha como 9898P @ $ $W 0rd.</span><span class="sxs-lookup"><span data-stu-id="8c059-132">This example enables the account for the existing room mailbox that has the alias value ProjectRigel02, and sets the password to 9898P@$$W0rd.</span></span> <span data-ttu-id="8c059-133">Observe que a conta será ProjectRigel02@contoso.onmicrosoft.comda por causa do valor de alias existente.</span><span class="sxs-lookup"><span data-stu-id="8c059-133">Note that the account will be ProjectRigel02@contoso.onmicrosoft.com because of the existing alias value.</span></span>

     ``` PowerShell
     Set-Mailbox -Identity ProjectRigel02 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '9898P@$$W0rd' -AsPlainText -Force)
     ```

   <span data-ttu-id="8c059-134">Para obter informações detalhadas sobre a sintaxe e o parâmetro, consulte [novo-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-mailbox) e [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox).</span><span class="sxs-lookup"><span data-stu-id="8c059-134">For detailed syntax and parameter information, see [New-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-mailbox) and [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox).</span></span>


3. <span data-ttu-id="8c059-135">No PowerShell do Exchange Online, defina as seguintes configurações na caixa de correio da sala para melhorar a experiência da reunião:</span><span class="sxs-lookup"><span data-stu-id="8c059-135">In Exchange Online PowerShell, configure the following settings on the room mailbox to improve the meeting experience:</span></span>

   - <span data-ttu-id="8c059-136">AutomateProcessing: a aceitação autoaceitar (os organizadores de reunião recebem a decisão de reserva de sala diretamente sem intervenção humana: grátis = aceitar; Busy = recusar.)</span><span class="sxs-lookup"><span data-stu-id="8c059-136">AutomateProcessing: AutoAccept (Meeting organizers receive the room reservation decision directly without human intervention: free = accept; busy = decline.)</span></span>

   - <span data-ttu-id="8c059-137">AddOrganizerToSubject: $false (o organizador da reunião não é adicionado ao assunto da solicitação de reunião.)</span><span class="sxs-lookup"><span data-stu-id="8c059-137">AddOrganizerToSubject: $false (The meeting organizer is not added to the subject of the meeting request.)</span></span>

   - <span data-ttu-id="8c059-138">DeleteComments: $false (Mantenha qualquer texto no corpo da mensagem de solicitações de reunião recebidas.)</span><span class="sxs-lookup"><span data-stu-id="8c059-138">DeleteComments: $false (Keep any text in the message body of incoming meeting requests.)</span></span>

   - <span data-ttu-id="8c059-139">DeleteSubject: $false (Mantenha o assunto das solicitações de reunião recebidas.)</span><span class="sxs-lookup"><span data-stu-id="8c059-139">DeleteSubject: $false (Keep the subject of incoming meeting requests.)</span></span>

   - <span data-ttu-id="8c059-140">RemovePrivateProperty: $false (garante que o sinalizador particular enviado pelo organizador da reunião na solicitação de reunião original permaneça conforme especificado.)</span><span class="sxs-lookup"><span data-stu-id="8c059-140">RemovePrivateProperty: $false (Ensures the private flag that was sent by the meeting organizer in the original meeting request remains as specified.)</span></span>

   - <span data-ttu-id="8c059-141">AddAdditionalResponse: $true (o texto especificado pelo parâmetro AdditionalResponse é adicionado a solicitações de reunião.)</span><span class="sxs-lookup"><span data-stu-id="8c059-141">AddAdditionalResponse: $true (The text specified by the AdditionalResponse parameter is added to meeting requests.)</span></span>

   - <span data-ttu-id="8c059-142">AdditionalResponse: "esta é uma sala de reunião do Skype!"</span><span class="sxs-lookup"><span data-stu-id="8c059-142">AdditionalResponse: "This is a Skype Meeting room!"</span></span> <span data-ttu-id="8c059-143">(O texto adicional a ser adicionado à solicitação de reunião.)</span><span class="sxs-lookup"><span data-stu-id="8c059-143">(The additional text to add to the meeting request.)</span></span>

   <span data-ttu-id="8c059-144">Este exemplo configura essas configurações na caixa de correio da sala chamada Project-Rigel-01.</span><span class="sxs-lookup"><span data-stu-id="8c059-144">This example configures these settings on the room mailbox named Project-Rigel-01.</span></span>

   ``` PowerShell
   Set-CalendarProcessing -Identity "Project-Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   <span data-ttu-id="8c059-145">Para obter informações detalhadas de sintaxe e parâmetro, consulte [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing).</span><span class="sxs-lookup"><span data-stu-id="8c059-145">For detailed syntax and parameter information, see [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing).</span></span>

4. <span data-ttu-id="8c059-146">Conecte-se ao MS online PowerShell para fazer as configurações do Active `Connect-MsolService -Credential $cred` Directory executando o cmdlet do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8c059-146">Connect to MS Online PowerShell to make Active Directory settings by running the `Connect-MsolService -Credential $cred` powershell cmdlet.</span></span>   <span data-ttu-id="8c059-147">Para obter detalhes sobre o Active Directory, consulte [Azure ActiveDirectory (MSOnline) 1,0](https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="8c059-147">For details about Active Directory, see [Azure ActiveDirectory (MSOnline) 1.0](https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-1.0).</span></span> 

   > [!NOTE]
   > <span data-ttu-id="8c059-148">Não há suporte para o [Azure Active Directory PowerShell 2,0](https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-2.0) .</span><span class="sxs-lookup"><span data-stu-id="8c059-148">[Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-2.0) is not supported.</span></span> 

5. <span data-ttu-id="8c059-149">Se você não quiser que a senha expire, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="8c059-149">If you do not want the password to expire, use the following syntax:</span></span>

    ``` PowerShell
    Set-MsolUser -UserPrincipalName $acctUpn -PasswordNeverExpires $true
    ```
<!--
   ``` PowerShell
   Set-AzureADUserPassword -UserPrincipalName <Account> -EnforceChangePasswordPolicy $false
   ```  -->

   <span data-ttu-id="8c059-150">Este exemplo define a senha da conta ProjectRigel01@contoso.onmicrosoft.com para nunca expirar.</span><span class="sxs-lookup"><span data-stu-id="8c059-150">This example sets the password for the account ProjectRigel01@contoso.onmicrosoft.com to never expire.</span></span>

  ``` PowerShell
    Set-MsolUser -UserPrincipalName $acctUpn -PasswordNeverExpires $true
  ```
<!-- 
   ``` PowerShell
   Set-AzureADUserPassword -UserPrincipalName ProjectRigel01@contoso.onmicrosoft.com -EnforceChangePasswordPolicy $false
   ``` -->

   <span data-ttu-id="8c059-151">Você também pode definir um número de telefone para a conta executando o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="8c059-151">You can also set a phone number for the account by running the following command:</span></span>

  ``` PowerShell
    Set-MsolUser -UserPrincipalName <upn> -PhoneNumber <phone number>
  ```
<!-- 
   ``` PowerShell
   Set-AzureADUser -UserPrincipalName <Account> -PhoneNumber "<PhoneNumber>"
   ```  -->

6. <span data-ttu-id="8c059-152">A conta do dispositivo precisa ter uma licença válida do Office 365 ou o Exchange e o Microsoft Teams ou o Skype for Business não funcionarão.</span><span class="sxs-lookup"><span data-stu-id="8c059-152">The device account needs to have a valid Office 365 license, or Exchange and Microsoft Teams or Skype for Business will not work.</span></span> <span data-ttu-id="8c059-153">Se você tem a licença, deve atribuir um local de uso à conta de dispositivo (isso determina quais SKUs de licença estão disponíveis para sua conta).</span><span class="sxs-lookup"><span data-stu-id="8c059-153">If you have the license, you need to assign a usage location to your device account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="8c059-154">Você pode usar`Get-MsolAccountSku`</span><span class="sxs-lookup"><span data-stu-id="8c059-154">You can use `Get-MsolAccountSku`</span></span> <!-- Get-AzureADSubscribedSku --> <span data-ttu-id="8c059-155">para recuperar uma lista de SKUs disponíveis para o seu locatário do Office 365 da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="8c059-155">to retrieve a list of available SKUs for your Office 365 tenant as follows:</span></span>

  ``` Powershell
  Get-MsolAccountSku
  ```
<!--
   ``` Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ```  -->

   <span data-ttu-id="8c059-156">Em seguida, você pode adicionar uma licença usando o`Set-MsolUserLicense`</span><span class="sxs-lookup"><span data-stu-id="8c059-156">Next, you can add a license using the `Set-MsolUserLicense`</span></span> <!--Set-AzureADUserLicense --> <span data-ttu-id="8c059-157">cmdlet.</span><span class="sxs-lookup"><span data-stu-id="8c059-157">cmdlet.</span></span> <span data-ttu-id="8c059-158">Nesse caso, $strLicense é o código de SKU que você vê (por exemplo, contoso:STANDARDPACK).</span><span class="sxs-lookup"><span data-stu-id="8c059-158">In this case, $strLicense is the SKU code that you see (for example, contoso:STANDARDPACK).</span></span>

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

   <span data-ttu-id="8c059-159">Para obter instruções detalhadas, consulte [atribuir licenças a contas de usuário com o Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="8c059-159">For detailed instructions, see [Assign licenses to user accounts with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

7. <span data-ttu-id="8c059-160">Em seguida, você precisa habilitar a conta do dispositivo com o Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="8c059-160">Next, you need to enable the device account with Skype for Business.</span></span> <span data-ttu-id="8c059-161">Certifique-se de que seu ambiente atenda aos requisitos definidos nos [requisitos de salas do Microsoft Teams](requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8c059-161">Be sure your environment meets the requirements defined in [Microsoft Teams Rooms requirements](requirements.md).</span></span>

   <span data-ttu-id="8c059-162">Inicie uma sessão remota do [Windows PowerShell](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) da seguinte maneira (certifique [-se de instalar os componentes do PowerShell do Skype for Business online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)):</span><span class="sxs-lookup"><span data-stu-id="8c059-162">Start a remote [Windows PowerShell session](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) as follows (be sure to [install Skype for Business Online PowerShell components](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)):</span></span>

   ``` Powershell
   Import-Module SkypeOnlineConnector  
   $cssess=New-CsOnlineSession -Credential $cred  
   Import-PSSession $cssess -AllowClobber
   ```

   <span data-ttu-id="8c059-163">Em seguida, habilite a sua conta de salas do Microsoft Teams para o Skype for Business Server executando o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="8c059-163">Next, enable your Microsoft Teams Rooms account for Skype for Business Server by running the following cmdlet:</span></span>

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

   <span data-ttu-id="8c059-164">Obtenha as informações de RegistrarPool da nova conta de usuário que está sendo configurada, conforme mostrado neste exemplo:</span><span class="sxs-lookup"><span data-stu-id="8c059-164">Obtain the RegistrarPool information from the new user account being setup, as shown in this example:</span></span>

    ``` Powershell
    Get-CsOnlineUser -Identity $rm | Select -Expand RegistrarPool
    ```

    > [!NOTE]
    > <span data-ttu-id="8c059-165">Não é possível criar novas contas de usuário no mesmo pool de registradores como contas de usuário existentes no locatário.</span><span class="sxs-lookup"><span data-stu-id="8c059-165">New user accounts might not be created on the same registrar pool as existing user accounts in the tenant.</span></span> <span data-ttu-id="8c059-166">O comando acima impedirá erros na configuração da conta devido a essa situação.</span><span class="sxs-lookup"><span data-stu-id="8c059-166">The command above will prevent errors in account setup due to this situation.</span></span>

<span data-ttu-id="8c059-167">Depois de concluir as etapas anteriores para habilitar sua conta de salas do Microsoft Teams no Microsoft Teams ou o Skype for Business Online, você precisa atribuir uma licença ao dispositivo de salas do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="8c059-167">After you've completed the preceding steps to enable your Microsoft Teams Rooms account in Microsoft Teams or Skype for Business Online, you need to assign a license to Microsoft Teams Rooms device.</span></span> <span data-ttu-id="8c059-168">Usando o portal administrativo do Office 365, atribua uma licença do Skype for Business online (plano 2) ou do Skype for Business online (plano 3) ao dispositivo.</span><span class="sxs-lookup"><span data-stu-id="8c059-168">Using the Office 365 administrative portal, assign either a Skype for Business Online (Plan 2) or a Skype for Business Online (Plan 3) license to the device.</span></span>

### <a name="assign-a-license-to-your-account"></a><span data-ttu-id="8c059-169">Atribuir uma licença à conta</span><span class="sxs-lookup"><span data-stu-id="8c059-169">Assign a license to your account</span></span>

1. <span data-ttu-id="8c059-170">Faça logon como administrador de locatários, abra o portal administrativo do Office 365 e clique no aplicativo de administração.</span><span class="sxs-lookup"><span data-stu-id="8c059-170">Login as a tenant administrator, open the Office 365 Administrative Portal, and click on the Admin app.</span></span>

2. <span data-ttu-id="8c059-171">Clique em **Usuários e Grupos** e clique em **Adicionar usuários, redefinir senhas e muito mais**.</span><span class="sxs-lookup"><span data-stu-id="8c059-171">Click **Users and Groups** and then click **Add users, reset passwords, and more**.</span></span>

3. <span data-ttu-id="8c059-172">Selecione a conta de salas do Microsoft Teams e, em seguida, clique ou toque no ícone de caneta, o que significa editar.</span><span class="sxs-lookup"><span data-stu-id="8c059-172">Select the Microsoft Teams Rooms account, and then click or tap the pen icon, which means edit.</span></span>

4. <span data-ttu-id="8c059-173">Clique na opção **Licenças**.</span><span class="sxs-lookup"><span data-stu-id="8c059-173">Click on the **Licenses** option.</span></span>

5. <span data-ttu-id="8c059-174">Na seção **atribuir licenças** , você precisa selecionar o Skype for Business online (plano 2) ou o Skype for Business online (plano 3), dependendo do seu licenciamento e do que você decidiu em termos de necessidade do Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="8c059-174">In the **Assign licenses** section, you need to select Skype for Business Online (Plan 2) or Skype for Business Online (Plan 3), depending on your licensing and what you've decided in terms of needing Enterprise Voice.</span></span> <span data-ttu-id="8c059-175">Você terá que usar uma licença do plano 3 se quiser usar o Cloud PBX em salas do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="8c059-175">You'll have to use a Plan 3 license if you want to use Cloud PBX on Microsoft Teams Rooms.</span></span> <span data-ttu-id="8c059-176">O CloudPBX será necessário como requisito mínimo para habilitar a conectividade de voz.</span><span class="sxs-lookup"><span data-stu-id="8c059-176">Minimally you will need CloudPBX for voice connectivity.</span></span> <span data-ttu-id="8c059-177">Em seguida, configure as chamadas PSTN ou de voz híbridas com base no método de conectividade PSTN.</span><span class="sxs-lookup"><span data-stu-id="8c059-177">Then configure hybrid voice or PSTN calling based on the PSTN connectivity method.</span></span> <span data-ttu-id="8c059-178">Consulte [licenças de salas do Microsoft Teams](https://docs.microsoft.com/en-us/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2) para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="8c059-178">See [Microsoft Teams Rooms licenses](https://docs.microsoft.com/en-us/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2) for more details.</span></span>

6. <span data-ttu-id="8c059-179">Clique em **Salvar** para concluir a tarefa.</span><span class="sxs-lookup"><span data-stu-id="8c059-179">Click **Save** to complete the task.</span></span>

## <a name="sample-room-account-setup-in-exchange-online-and-skype-for-business-online"></a><span data-ttu-id="8c059-180">Exemplo: configuração da conta de sala no Exchange Online e no Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="8c059-180">Sample: Room account setup in Exchange Online and Skype for Business Online</span></span>

<span data-ttu-id="8c059-181">Comandos do PowerShell do Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="8c059-181">Exchange Online PowerShell commands:</span></span>

``` Powershell
New-Mailbox -MicrosoftOnlineServicesID Rigel1@contoso.com -Alias rigel1 -Name "Rigel 1" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)

Set-CalendarProcessing -Identity rigel1 -AutomateProcessing AutoAccept-AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true
-AdditionalResponse "This is a Rigel room!"
```

<span data-ttu-id="8c059-182">Comandos do PowerShell do Azure Active Directory:</span><span class="sxs-lookup"><span data-stu-id="8c059-182">Azure Active Directory PowerShell commands:</span></span>

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

<span data-ttu-id="8c059-183">Comando do PowerShell do Skype for Business:</span><span class="sxs-lookup"><span data-stu-id="8c059-183">Skype for Business PowerShell command:</span></span>

``` PowerShell
Enable-CsMeetingRoom -Identity rigel1@contoso.onmicrosoft.com -RegistrarPool sippooldm21a05.infra.lync.com
-SipAddressType EmailAddress
```

> [!NOTE]
> <span data-ttu-id="8c059-184">Assim, você adiciona CloudPBX e PSTNCallingDomesticAndInternational.</span><span class="sxs-lookup"><span data-stu-id="8c059-184">This adds CloudPBX and PSTNCallingDomesticAndInternational.</span></span> <span data-ttu-id="8c059-185">Além disso, será necessário usar a interface do administrador para atribuir um número de telefone.</span><span class="sxs-lookup"><span data-stu-id="8c059-185">Additionally, you will need to use the Admin interface to assign a phone number.</span></span>

## <a name="validate"></a><span data-ttu-id="8c059-186">Válida</span><span class="sxs-lookup"><span data-stu-id="8c059-186">Validate</span></span>

<span data-ttu-id="8c059-187">Para a validação, você deve ser capaz de usar qualquer cliente Skype for Business para entrar na conta que você criou.</span><span class="sxs-lookup"><span data-stu-id="8c059-187">For validation, you should be able to use any Skype for Business client to sign in to the account you created.</span></span>

## <a name="see-also"></a><span data-ttu-id="8c059-188">Confira também</span><span class="sxs-lookup"><span data-stu-id="8c059-188">See also</span></span>

[<span data-ttu-id="8c059-189">Configurar contas para salas do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8c059-189">Configure accounts for Microsoft Teams Rooms</span></span>](room-systems-v2-configure-accounts.md)

[<span data-ttu-id="8c059-190">Plano para salas do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8c059-190">Plan for Microsoft Teams Rooms</span></span>](skype-room-systems-v2-0.md)

[<span data-ttu-id="8c059-191">Implantar salas do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8c059-191">Deploy Microsoft Teams Rooms</span></span>](room-systems-v2.md)

[<span data-ttu-id="8c059-192">Configurar um console de salas do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8c059-192">Configure a Microsoft Teams Rooms console</span></span>](console.md)

[<span data-ttu-id="8c059-193">Gerenciar Salas do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8c059-193">Manage Microsoft Teams Rooms</span></span>](skype-room-systems-v2.md)

[<span data-ttu-id="8c059-194">Licenciamento de salas do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8c059-194">Microsoft Teams Rooms Licensing</span></span>](/SfbOnline/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2.md)
