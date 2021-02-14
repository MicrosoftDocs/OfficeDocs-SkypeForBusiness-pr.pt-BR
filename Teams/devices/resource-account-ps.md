---
title: Criando Contas de Recursos do Microsoft Teams para barras de colaboração do Microsoft Teams usando o PowerShell
ms.author: mitressl
author: flinchbot
manager: ericwe
audience: ITPro
ms.reviewer: payurevi
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom: ''
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: Leia este tópico para obter informações sobre como implantar barras de colaboração para o Microsoft Teams.
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 0cb8043e0530c986b9ddcaa9a1022254939adfd2
ms.sourcegitcommit: f0ccafb7e9c2d382ab4545e085657e8129024f1d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/16/2020
ms.locfileid: "44268009"
---
# <a name="create-a-microsoft-365-resource-account-using-the-powershell"></a><span data-ttu-id="9e0f3-103">Criar uma conta de recurso do Microsoft 365 usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="9e0f3-103">Create a Microsoft 365 resource account using the PowerShell</span></span>

<span data-ttu-id="9e0f3-104">Leia este tópico para obter informações sobre como criar contas de recursos para barras de colaboração do Microsoft Teams usando o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9e0f3-104">Read this topic for information on how to create resource accounts for collaboration bars for Microsoft Teams using PowerShell.</span></span>

<span data-ttu-id="9e0f3-105">A maneira mais fácil de criar uma conta de recurso é usando o Centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9e0f3-105">The easiest way to create a resource account is by using the Microsoft 365 admin center.</span></span> <span data-ttu-id="9e0f3-106">[Confira este artigo sobre como fazer isso.](resource-account-ui.md)</span><span class="sxs-lookup"><span data-stu-id="9e0f3-106">[See this article on how to do this](resource-account-ui.md).</span></span>

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

## <a name="requirements"></a><span data-ttu-id="9e0f3-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9e0f3-107">Requirements</span></span>

<span data-ttu-id="9e0f3-108">Antes de implantar as Salas do Microsoft Teams com o Office 365, certifique-se de que você atendeu aos requisitos.</span><span class="sxs-lookup"><span data-stu-id="9e0f3-108">Before you deploy Microsoft Teams Rooms with Office 365, be sure you have met the requirements.</span></span> <span data-ttu-id="9e0f3-109">Para obter mais informações, consulte [Implantar barras de colaboração para o Microsoft Teams.](collab-bar-deploy.md)</span><span class="sxs-lookup"><span data-stu-id="9e0f3-109">For more information, see [Deploy collaboration bars for Microsoft Teams](collab-bar-deploy.md).</span></span>

- <span data-ttu-id="9e0f3-110">Se precisar de recursos PSTN para a barra de colaboração, você precisará de licença do Sistema de Telefonia.</span><span class="sxs-lookup"><span data-stu-id="9e0f3-110">If you need PSTN capabilities for the collaboration bar, you will need Phone System license.</span></span>

- <span data-ttu-id="9e0f3-111">Suas contas de recursos devem ter caixas de correio do Exchange.</span><span class="sxs-lookup"><span data-stu-id="9e0f3-111">Your resource accounts must have Exchange mailboxes.</span></span> <span data-ttu-id="9e0f3-112">Como são contas de recursos, nenhuma licença do Exchange é necessária.</span><span class="sxs-lookup"><span data-stu-id="9e0f3-112">As these are resource accounts, no Exchange license is required.</span></span> <span data-ttu-id="9e0f3-113">Recomendamos o uso da licença de Salas de Reunião para contas de recursos.</span><span class="sxs-lookup"><span data-stu-id="9e0f3-113">We recommend the usage of the Meeting Rooms license for resource accounts.</span></span>


### <a name="add-a-resource-account"></a><span data-ttu-id="9e0f3-114">Adicionar uma conta de recurso</span><span class="sxs-lookup"><span data-stu-id="9e0f3-114">Add a resource account</span></span>

1. <span data-ttu-id="9e0f3-115">Conecte-se ao PowerShell do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="9e0f3-115">Connect to Exchange Online PowerShell.</span></span> <span data-ttu-id="9e0f3-116">Para obter instruções, consulte [Conectar-se ao PowerShell do Exchange Online.](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell-v2/exchange-online-powershell-v2?view=exchange-ps#install-and-maintain-the-exchange-online-powershell-v2-module)</span><span class="sxs-lookup"><span data-stu-id="9e0f3-116">For instructions, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell-v2/exchange-online-powershell-v2?view=exchange-ps#install-and-maintain-the-exchange-online-powershell-v2-module).</span></span>

2. <span data-ttu-id="9e0f3-117">No PowerShell do Exchange Online, crie uma nova caixa de correio de sala ou modifique uma caixa de correio de sala existente.</span><span class="sxs-lookup"><span data-stu-id="9e0f3-117">In Exchange Online PowerShell, create a new room mailbox or modify an existing room mailbox.</span></span>

   - <span data-ttu-id="9e0f3-118">Para criar uma nova caixa de correio de sala, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="9e0f3-118">To create a new room mailbox, use the following syntax:</span></span>

     ``` PowerShell
     New-Mailbox -Name "<Unique Name>" -Alias <Alias> -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID <Account> -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     <span data-ttu-id="9e0f3-119">Este exemplo cria uma nova caixa de correio de sala com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="9e0f3-119">This example creates a new room mailbox with the following settings:</span></span>

     - <span data-ttu-id="9e0f3-120">Nome: Desaconsupo-sala-01</span><span class="sxs-lookup"><span data-stu-id="9e0f3-120">Name: Huddle-Room-01</span></span>

     - <span data-ttu-id="9e0f3-121">Alias: Alias: AliasRoom01</span><span class="sxs-lookup"><span data-stu-id="9e0f3-121">Alias: HuddleRoom01</span></span>

     - <span data-ttu-id="9e0f3-122">Conta: huddleroom01@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="9e0f3-122">Account: huddleroom01@contoso.onmicrosoft.com</span></span>

     - <span data-ttu-id="9e0f3-123">Senha da conta: P@$$W 0rd242</span><span class="sxs-lookup"><span data-stu-id="9e0f3-123">Account password: P@$$W0rd242</span></span>

     ``` PowerShell
     New-Mailbox -Name "Huddle-Room-01" -Alias HuddleRoom01 -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID HuddleRoom01@contoso.onmicrosoft.com -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd242' -AsPlainText -Force)
     ```

   - <span data-ttu-id="9e0f3-124">Para modificar uma caixa de correio de sala existente, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="9e0f3-124">To modify an existing room mailbox, use the following syntax:</span></span>

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     <span data-ttu-id="9e0f3-125">Este exemplo habilita a conta para a caixa de correio de sala existente que tem o valor de alias Desarmado02 e define a senha como 808P@$$W 0rd.</span><span class="sxs-lookup"><span data-stu-id="9e0f3-125">This example enables the account for the existing room mailbox that has the alias value HuddleRoom02, and sets the password to 808P@$$W0rd.</span></span> <span data-ttu-id="9e0f3-126">Observe que a conta será HuddleRoom02@contoso.onmicrosoft.com devido ao valor de alias existente.</span><span class="sxs-lookup"><span data-stu-id="9e0f3-126">Note that the account will be HuddleRoom02@contoso.onmicrosoft.com because of the existing alias value.</span></span>

     ``` PowerShell
     Set-Mailbox -Identity HuddleRoom02 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '808P@$$W0rd' -AsPlainText -Force)
     ```

   <span data-ttu-id="9e0f3-127">Para obter informações detalhadas sobre sintaxe e parâmetro, consulte [Caixa de](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-mailbox) Correio Nova e [Set-Mailbox.](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox)</span><span class="sxs-lookup"><span data-stu-id="9e0f3-127">For detailed syntax and parameter information, see [New-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-mailbox) and [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox).</span></span>


3. <span data-ttu-id="9e0f3-128">No PowerShell do Exchange Online, configure as seguintes configurações na caixa de correio da sala para melhorar a experiência da reunião:</span><span class="sxs-lookup"><span data-stu-id="9e0f3-128">In Exchange Online PowerShell, configure the following settings on the room mailbox to improve the meeting experience:</span></span>

   - <span data-ttu-id="9e0f3-129">AutomateProcessing: AutoAccept (organizadores da reunião recebem a decisão de reserva da sala diretamente sem intervenção humana: gratuito = aceitar; ocupado = recusar.)</span><span class="sxs-lookup"><span data-stu-id="9e0f3-129">AutomateProcessing: AutoAccept (Meeting organizers receive the room reservation decision directly without human intervention: free = accept; busy = decline.)</span></span>

   - <span data-ttu-id="9e0f3-130">AddOrganizerToSubject: $false (O organizador da reunião não é adicionado ao assunto da solicitação de reunião.)</span><span class="sxs-lookup"><span data-stu-id="9e0f3-130">AddOrganizerToSubject: $false (The meeting organizer is not added to the subject of the meeting request.)</span></span>

   - <span data-ttu-id="9e0f3-131">DeleteComments: $false (Mantenha qualquer texto no corpo da mensagem das solicitações de reunião recebidas.)</span><span class="sxs-lookup"><span data-stu-id="9e0f3-131">DeleteComments: $false (Keep any text in the message body of incoming meeting requests.)</span></span>

   - <span data-ttu-id="9e0f3-132">DeleteSubject: $false (Mantenha o assunto das solicitações de reunião recebidas.)</span><span class="sxs-lookup"><span data-stu-id="9e0f3-132">DeleteSubject: $false (Keep the subject of incoming meeting requests.)</span></span>

   - <span data-ttu-id="9e0f3-133">RemovePrivateProperty: $false (Garante o sinalizador particular que foi enviado pelo organizador da reunião na solicitação de reunião original permanece como especificado.)</span><span class="sxs-lookup"><span data-stu-id="9e0f3-133">RemovePrivateProperty: $false (Ensures the private flag that was sent by the meeting organizer in the original meeting request remains as specified.)</span></span>

   - <span data-ttu-id="9e0f3-134">AddAdditionalResponse: $true (O texto especificado pelo parâmetro AdditionalResponse é adicionado às solicitações de reunião.)</span><span class="sxs-lookup"><span data-stu-id="9e0f3-134">AddAdditionalResponse: $true (The text specified by the AdditionalResponse parameter is added to meeting requests.)</span></span>

   - <span data-ttu-id="9e0f3-135">AdicionalResponse: "Esta sala tem uma barra de colaboração para o Microsoft Teams!"</span><span class="sxs-lookup"><span data-stu-id="9e0f3-135">AdditionalResponse: "This room has a collaboration bar for Microsoft Teams!"</span></span> <span data-ttu-id="9e0f3-136">(O texto adicional a ser acrescentado à solicitação de reunião.)</span><span class="sxs-lookup"><span data-stu-id="9e0f3-136">(The additional text to add to the meeting request.)</span></span>

   <span data-ttu-id="9e0f3-137">Este exemplo configura essas configurações na caixa de correio da sala chamada Mailbox-Room-01.</span><span class="sxs-lookup"><span data-stu-id="9e0f3-137">This example configures these settings on the room mailbox named Huddle-Room-01.</span></span>

   ``` PowerShell
   Set-CalendarProcessing -Identity "Huddle-Room-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This room has a collaboration bar for Microsoft Teams!"
   ```

   <span data-ttu-id="9e0f3-138">Para obter informações detalhadas sobre sintaxe e parâmetro, consulte [Set-CalendarProcessing.](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing)</span><span class="sxs-lookup"><span data-stu-id="9e0f3-138">For detailed syntax and parameter information, see [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing).</span></span>

4. <span data-ttu-id="9e0f3-139">Conecte-se ao PowerShell do MS Online para criar configurações do Active Directory executando o `Connect-MsolService -Credential $cred` cmdlet do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9e0f3-139">Connect to MS Online PowerShell to make Active Directory settings by running the `Connect-MsolService -Credential $cred` powershell cmdlet.</span></span>   <span data-ttu-id="9e0f3-140">Para obter detalhes sobre o Active Directory, consulte [Azure ActiveDirectory (MSOnline) 1.0.](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0)</span><span class="sxs-lookup"><span data-stu-id="9e0f3-140">For details about Active Directory, see [Azure ActiveDirectory (MSOnline) 1.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0).</span></span> 

   > [!NOTE]
   > <span data-ttu-id="9e0f3-141">[O PowerShell 2.0 do Azure Active Directory](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) não tem suporte.</span><span class="sxs-lookup"><span data-stu-id="9e0f3-141">[Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) is not supported.</span></span> 

5. <span data-ttu-id="9e0f3-142">De definir a senha huddleroom01@contoso.onmicrosoft.com não expirar usando a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="9e0f3-142">Set the password for huddleroom01@contoso.onmicrosoft.com to not expire using the following syntax:</span></span>

      ``` Powershell
      Set-MsolUser -UserPrincipalName huddleroom01@contoso.onmicrosoft.com -PasswordNeverExpires $true
      ```
    
6. <span data-ttu-id="9e0f3-143">A conta de recurso precisa ter uma licença válida do Office 365, de preferência a SKU da Sala de Reunião.</span><span class="sxs-lookup"><span data-stu-id="9e0f3-143">The resource account needs to have a valid Office 365 license, preferably the Meeting Room SKU.</span></span> <span data-ttu-id="9e0f3-144">Você também precisa atribuir um local de uso à sua conta de dispositivo— isso determina quais SKUs de licença estão disponíveis para sua conta.</span><span class="sxs-lookup"><span data-stu-id="9e0f3-144">You also need to assign a usage location to your device account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="9e0f3-145">Você pode usar `Get-MsolAccountSku` para recuperar uma lista de SKUs disponíveis para seu locatário do Office 365.</span><span class="sxs-lookup"><span data-stu-id="9e0f3-145">You can use `Get-MsolAccountSku` to retrieve a list of available SKUs for your Office 365 tenant.</span></span>

      ``` Powershell
      Get-MsolAccountSku
      ```
    
    <span data-ttu-id="9e0f3-146">Você pode atribuir a licença usando Set-MsolUserLicense.</span><span class="sxs-lookup"><span data-stu-id="9e0f3-146">You can assign the license using Set-MsolUserLicense.</span></span> 

      ``` Powershell
      Set-MsolUser -UserPrincipalName huddleroom01@contoso.onmicrosoft.com -UsageLocation "US"
      Set-MsolUserLicense -UserPrincipalName huddleroom01@contoso.onmicrosoft.com -AddLicenses contoso:meeting_room
      ```
   <span data-ttu-id="9e0f3-147">Para obter instruções [detalhadas, consulte Atribuir licenças a contas de usuário com o PowerShell do Office 365.](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="9e0f3-147">For detailed instructions, see [Assign licenses to user accounts with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>




[<span data-ttu-id="9e0f3-148">Configurar contas para barras de colaboração do Microsoft Teams usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="9e0f3-148">Configure accounts for collaboration bars for Microsoft Teams using PowerShell</span></span>](resource-account-ps.md)

[<span data-ttu-id="9e0f3-149">Implantar barras de colaboração para o Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9e0f3-149">Deploy collaboration bars for Microsoft Teams</span></span>](collab-bar-deploy.md)

[<span data-ttu-id="9e0f3-150">Barras de colaboração para licenciamento do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9e0f3-150">Collaboration bars for Microsoft Teams Licensing</span></span>](../rooms/rooms-licensing.md)


