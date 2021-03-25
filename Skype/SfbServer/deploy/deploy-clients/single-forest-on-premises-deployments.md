---
title: Implantações locais de floresta única do Sistema de Sala do Skype
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 80da9d71-3dcd-4ca4-8bd1-6d8196823206
description: Leia este tópico para saber como implantar o Sistema de Sala do Skype em um único ambiente local de floresta.
ms.openlocfilehash: df213b24ef3400aa5551a090d2dd218d05794988
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120320"
---
# <a name="skype-room-system-single-forest-on-premises-deployments"></a><span data-ttu-id="3d139-103">Implantações locais de floresta única do Sistema de Sala do Skype</span><span class="sxs-lookup"><span data-stu-id="3d139-103">Skype Room System single forest on-premises deployments</span></span>
 
<span data-ttu-id="3d139-104">Leia este tópico para saber como implantar o Sistema de Sala do Skype em um único ambiente local de floresta.</span><span class="sxs-lookup"><span data-stu-id="3d139-104">Read this topic to learn how to deploy Skype Room System in a single forest on-premises environment.</span></span>
  
<span data-ttu-id="3d139-105">Esta seção fornece uma visão geral das etapas para provisionar a conta do Sistema de Sala do Skype no Exchange Server e no Skype for Business Server hospedados em uma única implantação local de floresta.</span><span class="sxs-lookup"><span data-stu-id="3d139-105">This section provides an overview of the steps for provisioning the Skype Room System account on Exchange Server and Skype for Business Server hosted in a single forest on-premises deployment.</span></span>
  
## <a name="single-forest-on-premises-deployments"></a><span data-ttu-id="3d139-106">Implantação de uma única floresta no local</span><span class="sxs-lookup"><span data-stu-id="3d139-106">Single forest on-premises deployments</span></span>

<span data-ttu-id="3d139-107">Se você já tiver uma conta de caixa de correio de recurso para a sala de conferência, poderá usá-la.</span><span class="sxs-lookup"><span data-stu-id="3d139-107">If you already have a resource mailbox account for the conferencing room, you can use it.</span></span> <span data-ttu-id="3d139-108">Caso contrário, você precisará criar um novo.</span><span class="sxs-lookup"><span data-stu-id="3d139-108">Otherwise, you will need to create a new one.</span></span> <span data-ttu-id="3d139-109">Você pode usar o Shell de Gerenciamento do Exchange (PowerShell) ou Console de Gerenciamento do Exchange criar uma nova conta de caixa de correio de recurso.</span><span class="sxs-lookup"><span data-stu-id="3d139-109">You can use either Exchange Management Shell (PowerShell) or Exchange Management Console to create a new resource mailbox account.</span></span> <span data-ttu-id="3d139-110">Recomendamos usar uma nova caixa de correio de recurso (excluir caixa de correio antiga e re-criar) para o Sistema de Sala do Skype.</span><span class="sxs-lookup"><span data-stu-id="3d139-110">We recommend using a new (delete old mailbox and re-create) resource mailbox for Skype Room System.</span></span> <span data-ttu-id="3d139-111">Certifique-se de fazer o back up de dados da caixa de correio antes de excluí-los e exportá-los de volta para a caixa de correio re-criada usando o cliente do Outlook (consulte Exportar ou fazer o back-up de mensagens, calendário, tarefas e contatos para obter mais informações).</span><span class="sxs-lookup"><span data-stu-id="3d139-111">Make sure to back up mailbox data before deleting and then export it back to the re-created mailbox using the Outlook client (see Export or back up messages, calendar, tasks, and contacts for more information).</span></span> <span data-ttu-id="3d139-112">Para restaurar as reuniões perdidas excluindo a caixa de correio, consulte [Connect or restore a deleted mailbox](/exchange/connect-or-restore-a-deleted-mailbox-exchange-2013-help).</span><span class="sxs-lookup"><span data-stu-id="3d139-112">To restore the meetings lost by deleting the mailbox, see [Connect or restore a deleted mailbox](/exchange/connect-or-restore-a-deleted-mailbox-exchange-2013-help).</span></span> 
  
<span data-ttu-id="3d139-113">Para usar uma conta de caixa de correio de recurso existente (por exemplo, LRS-01) siga as etapas abaixo:</span><span class="sxs-lookup"><span data-stu-id="3d139-113">To use an existing resource mailbox account (for example, LRS-01) follow the steps below:</span></span>
  
1. <span data-ttu-id="3d139-114">Execute o seguinte comando do PowerShell de Gerenciamento do Exchange:</span><span class="sxs-lookup"><span data-stu-id="3d139-114">Run the following Exchange Management PowerShell command:</span></span>
    
   ```powershell
   Set-Mailbox -Name 'LRS-01' -Alias 'LRS01' -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

2. <span data-ttu-id="3d139-115">Se você planeja criar uma nova caixa de correio, em seguida, para uma única organização local do Exchange floresta, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="3d139-115">If you plan to create a new mailbox, then, for a single forest on-premises Exchange organization, run the following command:</span></span>
    
   ```powershell
   New-Mailbox -UserPrincipalName LRS01@contoso.com -Alias LRS01 -Name "LRS-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

   <span data-ttu-id="3d139-116">O exemplo acima cria uma conta de usuário habilitada no Active Directory e uma caixa de correio de sala para uma sala de conferência em uma organização local do Exchange.</span><span class="sxs-lookup"><span data-stu-id="3d139-116">The above example creates an enabled user account in Active Directory and a room mailbox for a conference room in an on-premises Exchange organization.</span></span> <span data-ttu-id="3d139-117">O parâmetro RoomMailboxPassword especifica a senha da conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="3d139-117">The RoomMailboxPassword parameter specifies the password for the user account.</span></span>
    
3. <span data-ttu-id="3d139-118">Configure a conta para resolver automaticamente conflitos aceitando/rejeitando reuniões.</span><span class="sxs-lookup"><span data-stu-id="3d139-118">Configure the account to automatically resolve conflicts by accepting/rejecting meetings.</span></span> <span data-ttu-id="3d139-119">As contas de sala de conferência equipadas pelo Sistema do Skype Room no Exchange podem ser gerenciadas por indivíduos, mas observe que até que o indivíduo aceite uma reunião, ela não aparecerá no calendário da tela inicial do Sistema de Sala do Skype.</span><span class="sxs-lookup"><span data-stu-id="3d139-119">Skype Room System-equipped conference room accounts in Exchange can be managed by individuals, but note that until the individual accepts a meeting it will not appear on the Skype Room System home screen calendar.</span></span>
    
   ```powershell
   Set-CalendarProcessing -Identity LRS01 -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteSubject $false -RemovePrivateProperty $false
   ```

   <span data-ttu-id="3d139-120">Para um conjunto completo de comandos disponíveis, consulte Set-CalendarProcessing.</span><span class="sxs-lookup"><span data-stu-id="3d139-120">For a complete set of commands available, see Set-CalendarProcessing.</span></span>
    
   <span data-ttu-id="3d139-121">Para lembrar os organizadores da reunião para tornar a reunião uma reunião online do Skype for Business no Outlook, execute o seguinte comando para configurar uma Dica de Email para a nova conta:</span><span class="sxs-lookup"><span data-stu-id="3d139-121">To remind meeting organizers to make the meeting an online Skype for Business meeting in Outlook, run the following command to set up a MailTip for the new account:</span></span> 
    
   ```powershell
   Set-Mailbox -Identity LRS01@contoso.com -MailTip "This room is equipped with Lync Meeting Room (LRS), please make it a Lync Meeting to take advantage of the enhanced meeting experience from LRS"
   ```
4. <span data-ttu-id="3d139-122">Use os comandos a seguir para configurar cadeias de caracteres localizadas.</span><span class="sxs-lookup"><span data-stu-id="3d139-122">Use the following commands to configure localized strings.</span></span> <span data-ttu-id="3d139-123">Se necessário pela sua organização, você também pode adicionar traduções personalizadas:</span><span class="sxs-lookup"><span data-stu-id="3d139-123">If required by your organization, you can also add custom translations:</span></span> 
   ```powershell
   $Temp = Get-Mailbox  LRS01@ contoso.com 
   $Temp.MailTipTranslations += "ES: Spanish translation of the message"
   Set-Mailbox -Identity LRS01@contoso.com -MailTipTranslations $Temp.MailTipTranslations
   ```

5. <span data-ttu-id="3d139-124">Opcional: configure o texto de aceitação da reunião que fornece aos usuários informações sobre a Sala de Reunião do Skype for Business e o que esperar ao agendar e participar de reuniões.</span><span class="sxs-lookup"><span data-stu-id="3d139-124">Optional: Configure meeting acceptance text that provides users with information about Skype for Business Meeting Room, and what to expect when they schedule and join meetings.</span></span> 
    
   ```powershell
   Set-CalendarProcessing -Identity LRS01 -AddAdditionalResponse $TRUE -AdditionalResponse "This is the Additional Response Text"
   ```

## <a name="check-resource-mailbox-account-in-active-directory"></a><span data-ttu-id="3d139-125">Verificar Conta de Caixa de Correio de Recurso no Active Directory</span><span class="sxs-lookup"><span data-stu-id="3d139-125">Check Resource Mailbox Account in Active Directory</span></span>

<span data-ttu-id="3d139-126">A conta de caixa de correio da sala de conferência criada pelo Exchange na etapa 1 acima pode ser um objeto de usuário desabilitado no Active Directory.</span><span class="sxs-lookup"><span data-stu-id="3d139-126">The conference room mailbox account created by Exchange in step 1 above might be a disabled user object in Active Directory.</span></span> <span data-ttu-id="3d139-127">O Sistema de Sala do Skype não pode entrar ou autenticar usando a autenticação Kerberos/NTLM se a conta estiver desabilitada no Active Directory.</span><span class="sxs-lookup"><span data-stu-id="3d139-127">Skype Room System cannot sign in or authenticate by using Kerberos/NTLM authentication if the account is disabled in Active Directory.</span></span> <span data-ttu-id="3d139-128">O cliente do Sistema de Sala do Skype deve ser capaz de se autenticar nos Serviços Web do Exchange para recuperar configurações de calendário e também pode enviar emails com conteúdo de quadro de trabalho.</span><span class="sxs-lookup"><span data-stu-id="3d139-128">The Skype Room System client must be able to authenticate against Exchange Web Services to retrieve calendar settings, and must also be able to send email with whiteboard contents.</span></span> 
  
<span data-ttu-id="3d139-129">Portanto, se a conta estiver desabilitada, você deverá habilitar essa conta no Active Directory fazendo o seguinte:</span><span class="sxs-lookup"><span data-stu-id="3d139-129">Therefore, if the account is disabled, you must enable this account in Active Directory by doing the following:</span></span> 
  
1. <span data-ttu-id="3d139-130">No Active Directory, execute o seguinte comando para habilitar o log de conta em:</span><span class="sxs-lookup"><span data-stu-id="3d139-130">In Active Directory, run the following command to enable account log on:</span></span> 
    
   ```powershell
   Set-ADAccountPassword -Identity LRS01
   ```

   <span data-ttu-id="3d139-131">Executar esse comando solicitará que você insira a senha atual e insira a senha duas vezes para confirmação.</span><span class="sxs-lookup"><span data-stu-id="3d139-131">Running this command will prompt you to enter the current password, and then to re-enter the password twice for confirmation.</span></span>
    
2. <span data-ttu-id="3d139-132">Depois que a senha for definida, execute o seguinte comando para habilitar a conta:</span><span class="sxs-lookup"><span data-stu-id="3d139-132">Once the password is set, run the following command to enable the account:</span></span> 
    
   ```powershell
   Enable-ADAccount -Identity LRS01
   ```

## <a name="enabling-skype-room-system-accounts-for-skype-for-business"></a><span data-ttu-id="3d139-133">Habilitando contas do sistema de sala do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="3d139-133">Enabling Skype Room System Accounts for Skype for Business</span></span>

<span data-ttu-id="3d139-134">Esta seção fornece uma visão geral das etapas necessárias para habilitar o Skype for Business para sua conta de sala de conferência, que será configurada no Skype Room System.</span><span class="sxs-lookup"><span data-stu-id="3d139-134">This section provides an overview of the steps required to enable Skype for Business for your conference room account, which will be configured on Skype Room System.</span></span> 
  
<span data-ttu-id="3d139-135">Depois de criar uma conta de caixa de correio de recurso para as salas de conferência, use o Shell de Gerenciamento do Skype for Business Server para habilitar contas do Sistema de Salas do Skype para serviços do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="3d139-135">After you create a resource mailbox account for the conferencing rooms, use Skype for Business Server Management Shell to enable Skype Room System accounts for Skype for Business services.</span></span>
  
> [!NOTE]
> <span data-ttu-id="3d139-136">O procedimento a seguir supõe que você tenha habilitado a conta do Sistema de Sala do Skype no Active Directory.</span><span class="sxs-lookup"><span data-stu-id="3d139-136">The following procedure assumes that you have enabled the Skype Room System account in Active Directory.</span></span> 
  
1. <span data-ttu-id="3d139-137">Execute o seguinte comando para habilitar a conta do Sistema de Sala do Skype em um pool do Skype for Business Server:</span><span class="sxs-lookup"><span data-stu-id="3d139-137">Run the following command to enable the Skype Room System account on a Skype for Business Server pool:</span></span>
    
   ```powershell
   Enable-CsMeetingRoom -SipAddress "sip:LRS01@contoso.com" -domaincontroller DC-ND-001.contoso.com -RegistrarPool LYNCPool15.contoso.com -Identity LRS01
   ```

2. <span data-ttu-id="3d139-138">Opcional: permita que essa conta faça e receba chamadas telefônicas PSTN habilitando a conta para Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="3d139-138">Optional: Allow this account to make and receive PSTN phone calls by enabling the account for Enterprise Voice.</span></span> <span data-ttu-id="3d139-139">Enterprise Voice não é necessário para o Skype Room System, mas se você não habilita-lo para Enterprise Voice, o cliente do Sistema de Sala do Skype não poderá fornecer a funcionalidade de discagem PSTN:</span><span class="sxs-lookup"><span data-stu-id="3d139-139">Enterprise Voice is not required for Skype Room System, but if you do not enable it for Enterprise Voice, the Skype Room System client won't be able to provide PSTN dialing functionality:</span></span>
    
   ```powershell
   Set-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com -LineURItel: +14255550555;ext=50555"
   Set-CsMeetingRoom -domaincontroller DC-ND-001.contoso.com -Identity LRS01 -EnterpriseVoiceEnabled $true
   ```

> [!NOTE]
> <span data-ttu-id="3d139-140">Se você habilitar Enterprise Voice para a conta da sala de conferência do Sistema de Sala do Skype, configure uma Política de Voz restrita adequada para sua organização.</span><span class="sxs-lookup"><span data-stu-id="3d139-140">If you enable Enterprise Voice for the Skype Room System conference room account, make sure to configure a restricted Voice Policy suitable for your organization.</span></span> <span data-ttu-id="3d139-141">Se a Sala de Reunião do Skype for Business for um recurso disponível publicamente, qualquer pessoa poderá usá-la para ingressar em uma reunião, agendada ou ad hoc.</span><span class="sxs-lookup"><span data-stu-id="3d139-141">If the Skype for Business Meeting Room is a publicly available resource, anyone could use it to join a meeting, either scheduled or ad hoc.</span></span> <span data-ttu-id="3d139-142">Depois de ingressar em uma reunião, a pessoa pode discar para qualquer número.</span><span class="sxs-lookup"><span data-stu-id="3d139-142">After joining a meeting, the person could dial out to any number.</span></span> <span data-ttu-id="3d139-143">No Skype for Business Server, o recurso discagem de conferências usa a política de voz do usuário, nesse caso, a conta do Sistema de Sala do Skype usada para ingressar na reunião.</span><span class="sxs-lookup"><span data-stu-id="3d139-143">In Skype for Business Server, the dial-out from conferences feature uses the voice policy of the user, in this case the Skype Room System account used to join the meeting.</span></span> <span data-ttu-id="3d139-144">Em versões anteriores do Lync Server, a política de voz do organizador é usada.</span><span class="sxs-lookup"><span data-stu-id="3d139-144">In earlier versions of Lync Server, the voice policy of the organizer is used.</span></span> <span data-ttu-id="3d139-145">Portanto, se um usuário de uma versão anterior do Lync Server agendar uma sala de reunião e convidar a conta da sala do Sistema de Sala do Skype, qualquer pessoa poderá usar a Sala de Reunião do Skype for Business para ingressar na reunião e poder discar qualquer número de telefone nacional/regional ou internacional, desde que o organizador tenha permissão para discar esses números.</span><span class="sxs-lookup"><span data-stu-id="3d139-145">Therefore, if a user of an earlier version of Lync Server schedules a meeting room and invites the Skype Room System room account, anyone could use the Skype for Business Meeting Room to join the meeting and could dial any national/regional or international phone number, as long as the organizer is allowed to dial those numbers.</span></span> 
