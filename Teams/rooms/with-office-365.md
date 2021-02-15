---
title: Implantar salas do Microsoft Teams com o Microsoft 365 ou o Office 365
ms.author: v-cichur
author: cichur
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
description: Leia este tópico para obter informações sobre como implantar salas do Microsoft Teams com o Microsoft 365 ou o Office 365, onde o Teams ou o Skype for Business e o Exchange estão online.
ms.openlocfilehash: 4ec54763379e4a13a69eb3e08019924708873faf
ms.sourcegitcommit: bfada4fd06c5cff12b0eefd3384bb3c10d10787f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/12/2021
ms.locfileid: "50196205"
---
# <a name="deploy-microsoft-teams-rooms-with-microsoft-365-or-office-365"></a><span data-ttu-id="47913-103">Implantar salas do Microsoft Teams com o Microsoft 365 ou o Office 365</span><span class="sxs-lookup"><span data-stu-id="47913-103">Deploy Microsoft Teams Rooms with Microsoft 365 or Office 365</span></span>

<span data-ttu-id="47913-104">Leia este tópico para obter informações sobre como implantar salas do Microsoft Teams com o Microsoft 365 ou o Office 365, onde o Microsoft Teams ou o Skype for Business e o Exchange estão online.</span><span class="sxs-lookup"><span data-stu-id="47913-104">Read this topic for information on how to deploy Microsoft Teams Rooms with Microsoft 365 or Office 365, where Microsoft Teams or Skype for Business and Exchange are both online.</span></span>

<span data-ttu-id="47913-105">A maneira mais fácil de configurar contas de usuário é configurá-las usando o Windows PowerShell remoto.</span><span class="sxs-lookup"><span data-stu-id="47913-105">The easiest way to set up user accounts is to configure them using remote Windows PowerShell.</span></span> <span data-ttu-id="47913-106">A Microsoft [ forneceSkypeRoomProvisioningScript.ps1, ](https://go.microsoft.com/fwlink/?linkid=870105)um script que ajudará a criar novas contas de usuário ou validar contas de recursos existentes que você tem para ajudá-lo a transformá-las em contas de usuário compatíveis com Salas do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="47913-106">Microsoft provides [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), a script that will help create new user accounts, or validate existing resource accounts you have in order to help you turn them into compatible Microsoft Teams Rooms user accounts.</span></span> <span data-ttu-id="47913-107">Se preferir, siga as etapas abaixo para configurar as contas que seu dispositivo Salas do Microsoft Teams usará.</span><span class="sxs-lookup"><span data-stu-id="47913-107">If you prefer, you can follow the steps below to configure accounts your Microsoft Teams Rooms device will use.</span></span>

## <a name="requirements"></a><span data-ttu-id="47913-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="47913-108">Requirements</span></span>

<span data-ttu-id="47913-109">Antes de implantar as Salas do Microsoft Teams com o Microsoft 365 ou o Office 365, certifique-se de que você atendeu aos requisitos.</span><span class="sxs-lookup"><span data-stu-id="47913-109">Before you deploy Microsoft Teams Rooms with Microsoft 365 or Office 365, be sure you have met the requirements.</span></span> <span data-ttu-id="47913-110">Para obter mais informações, consulte [os requisitos de Salas do Microsoft Teams.](requirements.md)</span><span class="sxs-lookup"><span data-stu-id="47913-110">For more information, see [Microsoft Teams Rooms requirements](requirements.md).</span></span>

<span data-ttu-id="47913-111">Para habilitar o Skype for Business, você deve ter o seguinte:</span><span class="sxs-lookup"><span data-stu-id="47913-111">To enable Skype for Business, you must have the following:</span></span>

- <span data-ttu-id="47913-112">Skype for Business Online (Plano 2 ou um plano baseado em empresas) ou superior em seu plano Microsoft 365 ou Office 365.</span><span class="sxs-lookup"><span data-stu-id="47913-112">Skype for Business Online (Plan 2, or an Enterprise-based plan) or higher in your Microsoft 365 or Office 365 plan.</span></span> <span data-ttu-id="47913-113">O plano precisa permitir recursos de conferência discado.</span><span class="sxs-lookup"><span data-stu-id="47913-113">The plan needs to allow dial-in conferencing capabilities.</span></span>

- <span data-ttu-id="47913-114">Se precisar de recursos de discagem de uma reunião, você precisará de uma licença de Audioconferência e sistema de telefonia.</span><span class="sxs-lookup"><span data-stu-id="47913-114">If you need dial-in capabilities from a meeting, you will need an Audio Conferencing and Phone System license.</span></span>  <span data-ttu-id="47913-115">Se precisar de recursos de discagem de uma reunião, você precisará de uma licença de Audioconferência.</span><span class="sxs-lookup"><span data-stu-id="47913-115">If you need dial-out capabilities from a meeting, you will need an Audio Conferencing license.</span></span>

- <span data-ttu-id="47913-116">Os usuários do locatário devem ter caixas de correio do Exchange.</span><span class="sxs-lookup"><span data-stu-id="47913-116">Your tenant users must have Exchange mailboxes.</span></span>

- <span data-ttu-id="47913-117">Sua conta do Microsoft Teams Rooms requer no mínimo uma licença do Skype for Business Online (Plano 2), mas não requer uma licença do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="47913-117">Your Microsoft Teams Rooms account does require at a minimum a Skype for Business Online (Plan 2) license, but it does not require an Exchange Online license.</span></span> <span data-ttu-id="47913-118">Confira [as licenças de Salas do Microsoft Teams](rooms-licensing.md) para obter detalhes.</span><span class="sxs-lookup"><span data-stu-id="47913-118">See [Microsoft Teams Rooms licenses](rooms-licensing.md) for details.</span></span>

<span data-ttu-id="47913-119">Para obter detalhes sobre os planos do Skype for Business Online, consulte a Descrição [do serviço Skype for Business Online.](https://technet.microsoft.com/library/jj822172.aspx)</span><span class="sxs-lookup"><span data-stu-id="47913-119">For details on Skype for Business Online Plans, see the [Skype for Business Online Service Description](https://technet.microsoft.com/library/jj822172.aspx).</span></span>

### <a name="add-a-device-account"></a><span data-ttu-id="47913-120">Adicionar uma conta de dispositivo</span><span class="sxs-lookup"><span data-stu-id="47913-120">Add a device account</span></span>

1. <span data-ttu-id="47913-121">Conecte-se ao PowerShell do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="47913-121">Connect to Exchange Online PowerShell.</span></span> <span data-ttu-id="47913-122">Para obter instruções, [consulte Conectar-se ao PowerShell do Exchange Online.](https://go.microsoft.com/fwlink/p/?linkid=396554)</span><span class="sxs-lookup"><span data-stu-id="47913-122">For instructions, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>

2. <span data-ttu-id="47913-123">No PowerShell do Exchange Online, crie uma nova caixa de correio de sala ou modifique uma caixa de correio de sala existente.</span><span class="sxs-lookup"><span data-stu-id="47913-123">In Exchange Online PowerShell, create a new room mailbox or modify an existing room mailbox.</span></span> <span data-ttu-id="47913-124">Por padrão, as caixas de correio de sala não têm contas associadas, portanto, você precisará adicionar uma conta ao criar ou modificar uma caixa de correio de sala que permita autenticar com o Skype Room Systems v2.</span><span class="sxs-lookup"><span data-stu-id="47913-124">By default, room mailboxes don't have associated accounts, so you'll need to add an account when you create or modify a room mailbox that allows it to authenticate with Skype Room Systems v2.</span></span>

   - <span data-ttu-id="47913-125">Para criar uma nova caixa de correio de sala, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="47913-125">To create a new room mailbox, use the following syntax:</span></span>

     ``` PowerShell
     New-Mailbox -Name "<Unique Name>" -Alias <Alias> -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID <Account> -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     <span data-ttu-id="47913-126">Este exemplo cria uma nova caixa de correio de sala com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="47913-126">This example creates a new room mailbox with the following settings:</span></span>

     - <span data-ttu-id="47913-127">Nome: Rigel-01</span><span class="sxs-lookup"><span data-stu-id="47913-127">Name: Rigel-01</span></span>

     - <span data-ttu-id="47913-128">Alias: Rigel1</span><span class="sxs-lookup"><span data-stu-id="47913-128">Alias: Rigel1</span></span>

     - <span data-ttu-id="47913-129">Conta: Rigel1@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="47913-129">Account: Rigel1@contoso.onmicrosoft.com</span></span>

     - <span data-ttu-id="47913-130">Senha da conta: P@$$W 0rd5959</span><span class="sxs-lookup"><span data-stu-id="47913-130">Account password: P@$$W0rd5959</span></span>

     ``` PowerShell
     New-Mailbox -Name "Rigel-01" -Alias Rigel1 -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID Rigel1@contoso.onmicrosoft.com -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
     ```

   - <span data-ttu-id="47913-131">Para modificar uma caixa de correio de sala existente, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="47913-131">To modify an existing room mailbox, use the following syntax:</span></span>

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     <span data-ttu-id="47913-132">Este exemplo habilita a conta para a caixa de correio de sala existente que tem o valor de alias Rigel2 e define a senha como 9898P@$$W 0rd.</span><span class="sxs-lookup"><span data-stu-id="47913-132">This example enables the account for the existing room mailbox that has the alias value Rigel2, and sets the password to 9898P@$$W0rd.</span></span> <span data-ttu-id="47913-133">Observe que a conta será Rigel2@contoso.onmicrosoft.com devido ao valor de alias existente.</span><span class="sxs-lookup"><span data-stu-id="47913-133">Note that the account will be Rigel2@contoso.onmicrosoft.com because of the existing alias value.</span></span>

     ``` PowerShell
     Set-Mailbox -Identity Rigel2 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '9898P@$$W0rd' -AsPlainText -Force)
     ```

   <span data-ttu-id="47913-134">Para obter informações detalhadas sobre sintaxe e parâmetro, consulte [Caixa de Correio Nova](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-mailbox) e [Set-Mailbox.](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox)</span><span class="sxs-lookup"><span data-stu-id="47913-134">For detailed syntax and parameter information, see [New-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-mailbox) and [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox).</span></span>

3. <span data-ttu-id="47913-135">No PowerShell do Exchange Online, configure as seguintes configurações na caixa de correio da sala para melhorar a experiência da reunião:</span><span class="sxs-lookup"><span data-stu-id="47913-135">In Exchange Online PowerShell, configure the following settings on the room mailbox to improve the meeting experience:</span></span>

   - <span data-ttu-id="47913-136">AutomateProcessing: AutoAccept (organizadores da reunião recebem a decisão de reserva da sala diretamente sem intervenção humana: gratuito = aceitar; ocupado = recusar.)</span><span class="sxs-lookup"><span data-stu-id="47913-136">AutomateProcessing: AutoAccept (Meeting organizers receive the room reservation decision directly without human intervention: free = accept; busy = decline.)</span></span>

   - <span data-ttu-id="47913-137">AddOrganizerToSubject: $false (O organizador da reunião não é adicionado ao assunto da solicitação de reunião.)</span><span class="sxs-lookup"><span data-stu-id="47913-137">AddOrganizerToSubject: $false (The meeting organizer is not added to the subject of the meeting request.)</span></span>

   - <span data-ttu-id="47913-138">DeleteComments: $false (Mantenha qualquer texto no corpo da mensagem de solicitações de reunião recebidas.)</span><span class="sxs-lookup"><span data-stu-id="47913-138">DeleteComments: $false (Keep any text in the message body of incoming meeting requests.)</span></span>

   - <span data-ttu-id="47913-139">DeleteSubject: $false (Mantenha o assunto das solicitações de reunião recebidas.)</span><span class="sxs-lookup"><span data-stu-id="47913-139">DeleteSubject: $false (Keep the subject of incoming meeting requests.)</span></span>

   - <span data-ttu-id="47913-140">RemovePrivateProperty: $false (Garante o sinalizador particular que foi enviado pelo organizador da reunião na solicitação de reunião original permanece como especificado.)</span><span class="sxs-lookup"><span data-stu-id="47913-140">RemovePrivateProperty: $false (Ensures the private flag that was sent by the meeting organizer in the original meeting request remains as specified.)</span></span>

   - <span data-ttu-id="47913-141">AddAdditionalResponse: $true (O texto especificado pelo parâmetro AdditionalResponse é adicionado às solicitações de reunião.)</span><span class="sxs-lookup"><span data-stu-id="47913-141">AddAdditionalResponse: $true (The text specified by the AdditionalResponse parameter is added to meeting requests.)</span></span>

   - <span data-ttu-id="47913-142">AdicionalResponse: "Esta é uma sala de reunião do Skype!"</span><span class="sxs-lookup"><span data-stu-id="47913-142">AdditionalResponse: "This is a Skype Meeting room!"</span></span> <span data-ttu-id="47913-143">(O texto adicional a ser acrescentado à solicitação de reunião.)</span><span class="sxs-lookup"><span data-stu-id="47913-143">(The additional text to add to the meeting request.)</span></span>

   <span data-ttu-id="47913-144">Este exemplo configura essas configurações na caixa de correio da sala chamada Rigel-01.</span><span class="sxs-lookup"><span data-stu-id="47913-144">This example configures these settings on the room mailbox named Rigel-01.</span></span>

   ``` PowerShell
   Set-CalendarProcessing -Identity "Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   <span data-ttu-id="47913-145">Para obter informações detalhadas sobre sintaxe e parâmetro, consulte [Set-CalendarProcessing.](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing)</span><span class="sxs-lookup"><span data-stu-id="47913-145">For detailed syntax and parameter information, see [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing).</span></span>

4. <span data-ttu-id="47913-146">Conecte-se ao PowerShell do MS Online para fazer configurações do Active Directory executando o `Connect-MsolService -Credential $cred` cmdlet do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="47913-146">Connect to MS Online PowerShell to make Active Directory settings by running the `Connect-MsolService -Credential $cred` PowerShell cmdlet.</span></span> <span data-ttu-id="47913-147">Para obter detalhes sobre o Active Directory, consulte [Azure ActiveDirectory (MSOnline) 1.0.](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0)</span><span class="sxs-lookup"><span data-stu-id="47913-147">For details about Active Directory, see [Azure ActiveDirectory (MSOnline) 1.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0).</span></span>

   > [!NOTE]
   > <span data-ttu-id="47913-148">[Não há suporte para o PowerShell 2.0 do Azure Active Directory.](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0)</span><span class="sxs-lookup"><span data-stu-id="47913-148">[Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) is not supported.</span></span>

5. <span data-ttu-id="47913-149">Se você não quiser que a senha expire, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="47913-149">If you do not want the password to expire, use the following syntax:</span></span>

   ```PowerShell
   Set-MsolUser -UserPrincipalName <upn> -PasswordNeverExpires $true
   ```

   <!--
   ```PowerShell
   Set-AzureADUserPassword -UserPrincipalName <Account> -EnforceChangePasswordPolicy $false
   ```  -->

   <span data-ttu-id="47913-150">Este exemplo define a senha para a conta Rigel1@contoso.onmicrosoft.com nunca expirar.</span><span class="sxs-lookup"><span data-stu-id="47913-150">This example sets the password for the account Rigel1@contoso.onmicrosoft.com to never expire.</span></span>

   ```PowerShell
   Set-MsolUser -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -PasswordNeverExpires $true
   ```

   <!-- 
   ```PowerShell
   Set-AzureADUserPassword -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -EnforceChangePasswordPolicy $false
   ``` -->

   <span data-ttu-id="47913-151">Você também pode definir um número de telefone para a conta executando o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="47913-151">You can also set a phone number for the account by running the following command:</span></span>

   ```PowerShell
   Set-MsolUser -UserPrincipalName <upn> -PhoneNumber <phone number>
   ```

   <!-- 
   ```PowerShell
   Set-AzureADUser -UserPrincipalName <Account> -PhoneNumber "<PhoneNumber>"
   ```  -->

> [!NOTE]
> <span data-ttu-id="47913-152">Se a senha não estiver definida como Nunca Expirar, a conta não entrará mais no dispositivo quando a conta atingir o período de vencimento.</span><span class="sxs-lookup"><span data-stu-id="47913-152">If the password is not set to Never Expire, the account will no longer sign in on the device when the account reaches the expiry period.</span></span> <span data-ttu-id="47913-153">Em seguida, a senha precisará ser alterada para a conta e também atualizada localmente no dispositivo MTR.</span><span class="sxs-lookup"><span data-stu-id="47913-153">The password will then need to be changed for the account and also updated locally on the MTR device.</span></span>

6. <span data-ttu-id="47913-154">A conta do dispositivo precisa ter uma licença válida do Microsoft 365 ou do Office 365, ou o Exchange e o Microsoft Teams ou o Skype for Business não funcionarão.</span><span class="sxs-lookup"><span data-stu-id="47913-154">The device account needs to have a valid Microsoft 365 or Office 365 license, or Exchange and Microsoft Teams or Skype for Business will not work.</span></span> <span data-ttu-id="47913-155">Se você tem a licença, deve atribuir um local de uso à conta de dispositivo (isso determina quais SKUs de licença estão disponíveis para sua conta).</span><span class="sxs-lookup"><span data-stu-id="47913-155">If you have the license, you need to assign a usage location to your device account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="47913-156">Você pode usar `Get-MsolAccountSku`</span><span class="sxs-lookup"><span data-stu-id="47913-156">You can use `Get-MsolAccountSku`</span></span> <!-- Get-AzureADSubscribedSku --> <span data-ttu-id="47913-157">para recuperar uma lista de SKUs disponíveis para sua organização do Microsoft 365 ou do Office 365 da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="47913-157">to retrieve a list of available SKUs for your Microsoft 365 or Office 365 organization as follows:</span></span>

   ```Powershell
   Get-MsolAccountSku
   ```

   <!--
   ```Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ```  -->

   <span data-ttu-id="47913-158">Em seguida, você pode adicionar uma licença usando o `Set-MsolUserLicense`</span><span class="sxs-lookup"><span data-stu-id="47913-158">Next, you can add a license using the `Set-MsolUserLicense`</span></span> <!--Set-AzureADUserLicense --> <span data-ttu-id="47913-159">Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="47913-159">cmdlet.</span></span> <span data-ttu-id="47913-160">Este exemplo adiciona a licença da Sala de Reunião à conta:</span><span class="sxs-lookup"><span data-stu-id="47913-160">This example adds the Meeting Room license to the account:</span></span>

   ```PowerShell
   Set-MsolUser -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -UsageLocation "US"
   Set-MsolUserLicense -UserPrincipalName $acctUpn -AddLicenses "Contoso:MEETING_ROOM"
   ```

   <!-- 
   ```Powershell
   Set-AzureADUser -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -UsageLocation "US"
   Set-AzureADUserLicense -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -AddLicenses "Contoso:MEETING_ROOM"
   ```   -->

   <span data-ttu-id="47913-161">Para obter instruções [detalhadas, consulte Atribuir licenças a contas de usuário com o PowerShell do Office 365.](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="47913-161">For detailed instructions, see [Assign licenses to user accounts with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

   <span data-ttu-id="47913-162">Você também pode adicionar recursos do Sistema de Telefonia a essa conta, mas precisa configurá-lo primeiro.</span><span class="sxs-lookup"><span data-stu-id="47913-162">You can also add Phone System capabilities to this account, but you have to configure it first.</span></span> <span data-ttu-id="47913-163">Veja [o que é o Sistema de Telefonia?](../what-is-phone-system-in-office-365.md) Para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="47913-163">See [What is Phone System?](../what-is-phone-system-in-office-365.md) for more details.</span></span> <span data-ttu-id="47913-164">Este exemplo adiciona o Plano de Chamada PSTN Doméstico e Internacional:</span><span class="sxs-lookup"><span data-stu-id="47913-164">This example adds the PSTN Domestic and International Calling Plan:</span></span>

   ```PowerShell
   Set-MsolUserLicense -UserPrincipalName rigel1@contoso.onmicrosoft.com -AddLicenses "Contoso:MCOPSTN2"
   ```

7. <span data-ttu-id="47913-165">Em seguida, você precisa habilitar a conta do dispositivo com o Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="47913-165">Next, you need to enable the device account with Skype for Business.</span></span> <span data-ttu-id="47913-166">Certifique-se de que seu ambiente atenda aos requisitos definidos nos [requisitos de Salas do Microsoft Teams.](requirements.md)</span><span class="sxs-lookup"><span data-stu-id="47913-166">Be sure your environment meets the requirements defined in [Microsoft Teams Rooms requirements](requirements.md).</span></span>

   <span data-ttu-id="47913-167">Inicie uma sessão remota [do Windows PowerShell](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) da seguinte forma (instale os componentes do PowerShell do [Skype for Business Online):](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)</span><span class="sxs-lookup"><span data-stu-id="47913-167">Start a remote [Windows PowerShell session](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) as follows (be sure to [install Skype for Business Online PowerShell components](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)):</span></span>

> [!NOTE]
> <span data-ttu-id="47913-168">No momento, o Skype for Business Online Connector faz parte do módulo mais recente do PowerShell do Teams.</span><span class="sxs-lookup"><span data-stu-id="47913-168">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
>
> <span data-ttu-id="47913-169">Se você estiver usando a versão pública mais recente do [Teams PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams/)não será necessário instalar o Skype for Business Online Connector.</span><span class="sxs-lookup"><span data-stu-id="47913-169">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

   ``` Powershell
   Import-Module -Name MicrosoftTeams  
   $cssess = New-CsOnlineSession -Credential $cred  
   Import-PSSession $cssess -AllowClobber
   ```

   <span data-ttu-id="47913-170">Obtenha as informações do RegistradorPool da nova conta de usuário que está sendo configurada, conforme mostrado neste exemplo:</span><span class="sxs-lookup"><span data-stu-id="47913-170">Obtain the RegistrarPool information from the new user account being setup, as shown in this example:</span></span>

   ``` Powershell
    Get-CsOnlineUser -Identity "Rigel1@contoso.onmicrosoft.com" | Select -Expand RegistrarPool
   ```

   <span data-ttu-id="47913-171">Em seguida, habilita sua conta do Microsoft Teams Rooms para o Skype for Business Server executando o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="47913-171">Next, enable your Microsoft Teams Rooms account for Skype for Business Server by running the following cmdlet:</span></span>

   ``` Powershell
   Enable-CsMeetingRoom -Identity "Rigel1@contoso.onmicrosoft.com" -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

   > [!NOTE]
   > <span data-ttu-id="47913-172">Novas contas de usuário podem não ser criadas no mesmo pool de registradores que as contas de usuário existentes no locatário.</span><span class="sxs-lookup"><span data-stu-id="47913-172">New user accounts might not be created on the same registrar pool as existing user accounts in the tenant.</span></span> <span data-ttu-id="47913-173">O comando acima evitará erros na configuração da conta devido a essa situação.</span><span class="sxs-lookup"><span data-stu-id="47913-173">The command above will prevent errors in account setup due to this situation.</span></span>

## <a name="validate"></a><span data-ttu-id="47913-174">Validar</span><span class="sxs-lookup"><span data-stu-id="47913-174">Validate</span></span>

<span data-ttu-id="47913-175">Para validação, você deve ser capaz de usar qualquer cliente do Skype for Business para entrar na conta criada.</span><span class="sxs-lookup"><span data-stu-id="47913-175">For validation, you should be able to use any Skype for Business client to sign in to the account you created.</span></span>

## <a name="see-also"></a><span data-ttu-id="47913-176">Confira também</span><span class="sxs-lookup"><span data-stu-id="47913-176">See also</span></span>

[<span data-ttu-id="47913-177">Configurar contas para salas do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="47913-177">Configure accounts for Microsoft Teams Rooms</span></span>](rooms-configure-accounts.md)

[<span data-ttu-id="47913-178">Planejar as Salas do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="47913-178">Plan for Microsoft Teams Rooms</span></span>](rooms-plan.md)

[<span data-ttu-id="47913-179">Implantar Salas do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="47913-179">Deploy Microsoft Teams Rooms</span></span>](rooms-deploy.md)

[<span data-ttu-id="47913-180">Configurar um console de Salas do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="47913-180">Configure a Microsoft Teams Rooms console</span></span>](console.md)

[<span data-ttu-id="47913-181">Gerenciar Salas do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="47913-181">Manage Microsoft Teams Rooms</span></span>](rooms-manage.md)

[<span data-ttu-id="47913-182">Licenciamento de Salas do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="47913-182">Microsoft Teams Rooms Licensing</span></span>](rooms-licensing.md)
