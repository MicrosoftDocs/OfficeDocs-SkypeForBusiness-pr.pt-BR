---
title: Criando Microsoft Teams contas de recursos para barras de colaboração para Microsoft Teams usando o PowerShell
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
description: Leia este tópico para obter informações sobre como implantar barras de colaboração para Microsoft Teams.
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 812fb4704661aa11d3388048fa044030cdb1ce00
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51115599"
---
# <a name="create-a-microsoft-365-resource-account-using-the-powershell"></a><span data-ttu-id="43ff3-103">Criar uma Microsoft 365 de recursos usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="43ff3-103">Create a Microsoft 365 resource account using the PowerShell</span></span>

<span data-ttu-id="43ff3-104">Leia este tópico para obter informações sobre como criar contas de recursos para barras de colaboração para Microsoft Teams usando o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="43ff3-104">Read this topic for information on how to create resource accounts for collaboration bars for Microsoft Teams using PowerShell.</span></span>

<span data-ttu-id="43ff3-105">A maneira mais fácil de criar uma conta de recurso é usando o Microsoft 365 de administração.</span><span class="sxs-lookup"><span data-stu-id="43ff3-105">The easiest way to create a resource account is by using the Microsoft 365 admin center.</span></span> <span data-ttu-id="43ff3-106">[Consulte este artigo sobre como fazer isso](resource-account-ui.md).</span><span class="sxs-lookup"><span data-stu-id="43ff3-106">[See this article on how to do this](resource-account-ui.md).</span></span>

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

## <a name="requirements"></a><span data-ttu-id="43ff3-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="43ff3-107">Requirements</span></span>

<span data-ttu-id="43ff3-108">Antes de implantar Salas do Microsoft Teams com Office 365, certifique-se de ter atendido aos requisitos.</span><span class="sxs-lookup"><span data-stu-id="43ff3-108">Before you deploy Microsoft Teams Rooms with Office 365, be sure you have met the requirements.</span></span> <span data-ttu-id="43ff3-109">Para obter mais informações, [consulte Deploy collaboration bars for Microsoft Teams](collab-bar-deploy.md).</span><span class="sxs-lookup"><span data-stu-id="43ff3-109">For more information, see [Deploy collaboration bars for Microsoft Teams](collab-bar-deploy.md).</span></span>

- <span data-ttu-id="43ff3-110">Se você precisar de recursos PSTN para a barra de colaboração, precisará Sistema de Telefonia licença.</span><span class="sxs-lookup"><span data-stu-id="43ff3-110">If you need PSTN capabilities for the collaboration bar, you will need Phone System license.</span></span>

- <span data-ttu-id="43ff3-111">Suas contas de recursos devem ter Exchange caixas de correio.</span><span class="sxs-lookup"><span data-stu-id="43ff3-111">Your resource accounts must have Exchange mailboxes.</span></span> <span data-ttu-id="43ff3-112">Como são contas de recurso, nenhuma Exchange é necessária.</span><span class="sxs-lookup"><span data-stu-id="43ff3-112">As these are resource accounts, no Exchange license is required.</span></span> <span data-ttu-id="43ff3-113">Recomendamos o uso da licença salas de reunião para contas de recursos.</span><span class="sxs-lookup"><span data-stu-id="43ff3-113">We recommend the usage of the Meeting Rooms license for resource accounts.</span></span>


### <a name="add-a-resource-account"></a><span data-ttu-id="43ff3-114">Adicionar uma conta de recurso</span><span class="sxs-lookup"><span data-stu-id="43ff3-114">Add a resource account</span></span>

1. <span data-ttu-id="43ff3-115">Conexão para Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="43ff3-115">Connect to Exchange Online PowerShell.</span></span> <span data-ttu-id="43ff3-116">Para obter instruções, [consulte Conexão Exchange Online PowerShell](/powershell/exchange/exchange-online/exchange-online-powershell-v2/exchange-online-powershell-v2?view=exchange-ps#install-and-maintain-the-exchange-online-powershell-v2-module).</span><span class="sxs-lookup"><span data-stu-id="43ff3-116">For instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/exchange-online/exchange-online-powershell-v2/exchange-online-powershell-v2?view=exchange-ps#install-and-maintain-the-exchange-online-powershell-v2-module).</span></span>

2. <span data-ttu-id="43ff3-117">No Exchange Online PowerShell, crie uma nova caixa de correio de sala ou modifique uma caixa de correio de sala existente.</span><span class="sxs-lookup"><span data-stu-id="43ff3-117">In Exchange Online PowerShell, create a new room mailbox or modify an existing room mailbox.</span></span>

   - <span data-ttu-id="43ff3-118">Para criar uma nova caixa de correio de sala, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="43ff3-118">To create a new room mailbox, use the following syntax:</span></span>

     ``` PowerShell
     New-Mailbox -Name "<Unique Name>" -Alias <Alias> -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID <Account> -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     <span data-ttu-id="43ff3-119">Este exemplo cria uma nova caixa de correio de sala com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="43ff3-119">This example creates a new room mailbox with the following settings:</span></span>

     - <span data-ttu-id="43ff3-120">Nome: Huddle-Room-01</span><span class="sxs-lookup"><span data-stu-id="43ff3-120">Name: Huddle-Room-01</span></span>

     - <span data-ttu-id="43ff3-121">Alias: HuddleRoom01</span><span class="sxs-lookup"><span data-stu-id="43ff3-121">Alias: HuddleRoom01</span></span>

     - <span data-ttu-id="43ff3-122">Conta: huddleroom01@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="43ff3-122">Account: huddleroom01@contoso.onmicrosoft.com</span></span>

     - <span data-ttu-id="43ff3-123">Senha da conta: P@$$W 0rd242</span><span class="sxs-lookup"><span data-stu-id="43ff3-123">Account password: P@$$W0rd242</span></span>

     ``` PowerShell
     New-Mailbox -Name "Huddle-Room-01" -Alias HuddleRoom01 -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID HuddleRoom01@contoso.onmicrosoft.com -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd242' -AsPlainText -Force)
     ```

   - <span data-ttu-id="43ff3-124">Para modificar uma caixa de correio de sala existente, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="43ff3-124">To modify an existing room mailbox, use the following syntax:</span></span>

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     <span data-ttu-id="43ff3-125">Este exemplo habilita a conta para a caixa de correio de sala existente que tem o valor de alias HuddleRoom02 e define a senha como 808P@$$W 0rd.</span><span class="sxs-lookup"><span data-stu-id="43ff3-125">This example enables the account for the existing room mailbox that has the alias value HuddleRoom02, and sets the password to 808P@$$W0rd.</span></span> <span data-ttu-id="43ff3-126">Observe que a conta será HuddleRoom02@contoso.onmicrosoft.com devido ao valor de alias existente.</span><span class="sxs-lookup"><span data-stu-id="43ff3-126">Note that the account will be HuddleRoom02@contoso.onmicrosoft.com because of the existing alias value.</span></span>

     ``` PowerShell
     Set-Mailbox -Identity HuddleRoom02 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '808P@$$W0rd' -AsPlainText -Force)
     ```

   <span data-ttu-id="43ff3-127">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [New-Mailbox](/powershell/module/exchange/mailboxes/new-mailbox) e [Set-Mailbox](/powershell/module/exchange/mailboxes/set-mailbox).</span><span class="sxs-lookup"><span data-stu-id="43ff3-127">For detailed syntax and parameter information, see [New-Mailbox](/powershell/module/exchange/mailboxes/new-mailbox) and [Set-Mailbox](/powershell/module/exchange/mailboxes/set-mailbox).</span></span>


3. <span data-ttu-id="43ff3-128">No Exchange Online PowerShell, configure as seguintes configurações na caixa de correio da sala para melhorar a experiência de reunião:</span><span class="sxs-lookup"><span data-stu-id="43ff3-128">In Exchange Online PowerShell, configure the following settings on the room mailbox to improve the meeting experience:</span></span>

   - <span data-ttu-id="43ff3-129">AutomateProcessing: AutoAccept (Os organizadores da reunião recebem a decisão de reserva de sala diretamente sem intervenção humana: free = accept; busy = decline.)</span><span class="sxs-lookup"><span data-stu-id="43ff3-129">AutomateProcessing: AutoAccept (Meeting organizers receive the room reservation decision directly without human intervention: free = accept; busy = decline.)</span></span>

   - <span data-ttu-id="43ff3-130">AddOrganizerToSubject: $false (O organizador da reunião não é adicionado ao assunto da solicitação de reunião.)</span><span class="sxs-lookup"><span data-stu-id="43ff3-130">AddOrganizerToSubject: $false (The meeting organizer is not added to the subject of the meeting request.)</span></span>

   - <span data-ttu-id="43ff3-131">DeleteComments: $false (Mantenha qualquer texto no corpo da mensagem de solicitações de reunião de entrada.)</span><span class="sxs-lookup"><span data-stu-id="43ff3-131">DeleteComments: $false (Keep any text in the message body of incoming meeting requests.)</span></span>

   - <span data-ttu-id="43ff3-132">DeleteSubject: $false (Mantenha o assunto das solicitações de reunião de entrada.)</span><span class="sxs-lookup"><span data-stu-id="43ff3-132">DeleteSubject: $false (Keep the subject of incoming meeting requests.)</span></span>

   - <span data-ttu-id="43ff3-133">RemovePrivateProperty: $false (Garante que o sinalizador privado enviado pelo organizador da reunião na solicitação de reunião original permaneça conforme especificado.)</span><span class="sxs-lookup"><span data-stu-id="43ff3-133">RemovePrivateProperty: $false (Ensures the private flag that was sent by the meeting organizer in the original meeting request remains as specified.)</span></span>

   - <span data-ttu-id="43ff3-134">AddAdditionalResponse: $true (O texto especificado pelo parâmetro AdditionalResponse é adicionado às solicitações de reunião.)</span><span class="sxs-lookup"><span data-stu-id="43ff3-134">AddAdditionalResponse: $true (The text specified by the AdditionalResponse parameter is added to meeting requests.)</span></span>

   - <span data-ttu-id="43ff3-135">AdditionalResponse: "Esta sala tem uma barra de colaboração para Microsoft Teams!"</span><span class="sxs-lookup"><span data-stu-id="43ff3-135">AdditionalResponse: "This room has a collaboration bar for Microsoft Teams!"</span></span> <span data-ttu-id="43ff3-136">(O texto adicional a ser acrescentado à solicitação de reunião.)</span><span class="sxs-lookup"><span data-stu-id="43ff3-136">(The additional text to add to the meeting request.)</span></span>

   <span data-ttu-id="43ff3-137">Este exemplo configura essas configurações na caixa de correio de sala chamada Huddle-Room-01.</span><span class="sxs-lookup"><span data-stu-id="43ff3-137">This example configures these settings on the room mailbox named Huddle-Room-01.</span></span>

   ``` PowerShell
   Set-CalendarProcessing -Identity "Huddle-Room-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This room has a collaboration bar for Microsoft Teams!"
   ```

   <span data-ttu-id="43ff3-138">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Set-CalendarProcessing](/powershell/module/exchange/mailboxes/set-calendarprocessing).</span><span class="sxs-lookup"><span data-stu-id="43ff3-138">For detailed syntax and parameter information, see [Set-CalendarProcessing](/powershell/module/exchange/mailboxes/set-calendarprocessing).</span></span>

4. <span data-ttu-id="43ff3-139">Conexão ao PowerShell do MS Online para fazer configurações do Active Directory executando o `Connect-MsolService -Credential $cred` cmdlet do powershell.</span><span class="sxs-lookup"><span data-stu-id="43ff3-139">Connect to MS Online PowerShell to make Active Directory settings by running the `Connect-MsolService -Credential $cred` powershell cmdlet.</span></span>   <span data-ttu-id="43ff3-140">Para obter detalhes sobre o Active Directory, consulte [Azure ActiveDirectory (MSOnline) 1.0](/powershell/azure/active-directory/overview?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="43ff3-140">For details about Active Directory, see [Azure ActiveDirectory (MSOnline) 1.0](/powershell/azure/active-directory/overview?view=azureadps-1.0).</span></span> 

   > [!NOTE]
   > <span data-ttu-id="43ff3-141">Azure Active Directory não há suporte para o [PowerShell 2.0.](/powershell/azure/active-directory/overview?view=azureadps-2.0)</span><span class="sxs-lookup"><span data-stu-id="43ff3-141">[Azure Active Directory PowerShell 2.0](/powershell/azure/active-directory/overview?view=azureadps-2.0) is not supported.</span></span> 

5. <span data-ttu-id="43ff3-142">De definir a senha huddleroom01@contoso.onmicrosoft.com não expirar usando a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="43ff3-142">Set the password for huddleroom01@contoso.onmicrosoft.com to not expire using the following syntax:</span></span>

      ``` Powershell
      Set-MsolUser -UserPrincipalName huddleroom01@contoso.onmicrosoft.com -PasswordNeverExpires $true
      ```
    
6. <span data-ttu-id="43ff3-143">A conta de recurso precisa ter uma Office 365 de Office 365, preferencialmente a Sala de Reunião SKU.</span><span class="sxs-lookup"><span data-stu-id="43ff3-143">The resource account needs to have a valid Office 365 license, preferably the Meeting Room SKU.</span></span> <span data-ttu-id="43ff3-144">Você também precisa atribuir um local de uso à sua conta de dispositivo— isso determina quais SKUs de licença estão disponíveis para sua conta.</span><span class="sxs-lookup"><span data-stu-id="43ff3-144">You also need to assign a usage location to your device account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="43ff3-145">Você pode usar `Get-MsolAccountSku` para recuperar uma lista de SKUs disponíveis para seu Office 365 locatário.</span><span class="sxs-lookup"><span data-stu-id="43ff3-145">You can use `Get-MsolAccountSku` to retrieve a list of available SKUs for your Office 365 tenant.</span></span>

      ``` Powershell
      Get-MsolAccountSku
      ```
    
    <span data-ttu-id="43ff3-146">Você pode atribuir a licença usando Set-MsolUserLicense.</span><span class="sxs-lookup"><span data-stu-id="43ff3-146">You can assign the license using Set-MsolUserLicense.</span></span> 

      ``` Powershell
      Set-MsolUser -UserPrincipalName huddleroom01@contoso.onmicrosoft.com -UsageLocation "US"
      Set-MsolUserLicense -UserPrincipalName huddleroom01@contoso.onmicrosoft.com -AddLicenses contoso:meeting_room
      ```
   <span data-ttu-id="43ff3-147">Para obter instruções [detalhadas, consulte Assign licenses to user accounts with Office 365 PowerShell](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="43ff3-147">For detailed instructions, see [Assign licenses to user accounts with Office 365 PowerShell](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>




[<span data-ttu-id="43ff3-148">Configurar contas para barras de colaboração para Microsoft Teams usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="43ff3-148">Configure accounts for collaboration bars for Microsoft Teams using PowerShell</span></span>](resource-account-ps.md)

[<span data-ttu-id="43ff3-149">Implantar barras de colaboração para Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="43ff3-149">Deploy collaboration bars for Microsoft Teams</span></span>](collab-bar-deploy.md)

[<span data-ttu-id="43ff3-150">Barras de colaboração para Microsoft Teams Licenciamento</span><span class="sxs-lookup"><span data-stu-id="43ff3-150">Collaboration bars for Microsoft Teams Licensing</span></span>](../rooms/rooms-licensing.md)