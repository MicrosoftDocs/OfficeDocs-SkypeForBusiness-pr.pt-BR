---
title: Implantações locais de uma única floresta do Sistema de Salas do Skype
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 80da9d71-3dcd-4ca4-8bd1-6d8196823206
description: Leia este tópico para saber como implantar o Sistema de Salas do Skype em um ambiente local de floresta única.
ms.openlocfilehash: 2d73ee2313088c653f4362139cb431e55d92015b
ms.sourcegitcommit: a2deac5e8308fc58aba34060006bffad2b19abed
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/06/2019
ms.locfileid: "36775258"
---
# <a name="skype-room-system-single-forest-on-premises-deployments"></a><span data-ttu-id="1dd2a-103">Implantações locais de uma única floresta do Sistema de Salas do Skype</span><span class="sxs-lookup"><span data-stu-id="1dd2a-103">Skype Room System single forest on-premises deployments</span></span>
 
<span data-ttu-id="1dd2a-104">Leia este tópico para saber como implantar o Sistema de Salas do Skype em um ambiente local de floresta única.</span><span class="sxs-lookup"><span data-stu-id="1dd2a-104">Read this topic to learn how to deploy Skype Room System in a single forest on-premises environment.</span></span>
  
<span data-ttu-id="1dd2a-105">Esta seção fornece uma visão geral das etapas para provisionar a conta do sistema de sala do Skype no Exchange Server e no Skype for Business Server hospedada em uma única implantação local da floresta.</span><span class="sxs-lookup"><span data-stu-id="1dd2a-105">This section provides an overview of the steps for provisioning the Skype Room System account on Exchange Server and Skype for Business Server hosted in a single forest on-premises deployment.</span></span>
  
## <a name="single-forest-on-premises-deployments"></a><span data-ttu-id="1dd2a-106">Implantações locais de floresta única</span><span class="sxs-lookup"><span data-stu-id="1dd2a-106">Single forest on-premises deployments</span></span>

<span data-ttu-id="1dd2a-107">Se você já tem uma conta de caixa de correio de recursos para a sala de conferências, pode utilizá-la.</span><span class="sxs-lookup"><span data-stu-id="1dd2a-107">If you already have a resource mailbox account for the conferencing room, you can use it.</span></span> <span data-ttu-id="1dd2a-108">Caso contrário, será necessário criar uma nova.</span><span class="sxs-lookup"><span data-stu-id="1dd2a-108">Otherwise, you will need to create a new one.</span></span> <span data-ttu-id="1dd2a-109">Você pode usar o Shell de Gerenciamento do Exchange (PowerShell) ou o Console de Gerenciamento do Exchange para criar uma nova conta de caixa de correio de recursos.</span><span class="sxs-lookup"><span data-stu-id="1dd2a-109">You can use either Exchange Management Shell (PowerShell) or Exchange Management Console to create a new resource mailbox account.</span></span> <span data-ttu-id="1dd2a-110">Recomendamos usar uma nova caixa de correio de recurso (excluir caixa de correio antiga e recriar) para o sistema de sala do Skype.</span><span class="sxs-lookup"><span data-stu-id="1dd2a-110">We recommend using a new (delete old mailbox and re-create) resource mailbox for Skype Room System.</span></span> <span data-ttu-id="1dd2a-111">Faça o backup dos dados da caixa de correio antes de excluí-los e, em seguida, exporte-os novamente para a caixa de correio recriada usando o cliente Outlook (consulte Exportar ou fazer backup de mensagens, calendário, tarefas e contatos para obter mais informações).</span><span class="sxs-lookup"><span data-stu-id="1dd2a-111">Make sure to back up mailbox data before deleting and then export it back to the re-created mailbox using the Outlook client (see Export or back up messages, calendar, tasks, and contacts for more information).</span></span> <span data-ttu-id="1dd2a-112">Para restaurar as reuniões perdidas excluindo a caixa de correio, consulte [conectar ou restaurar uma caixa de correio excluída](https://technet.microsoft.com/library/jj863438%28v=exchg.150%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="1dd2a-112">To restore the meetings lost by deleting the mailbox, see [Connect or restore a deleted mailbox](https://technet.microsoft.com/library/jj863438%28v=exchg.150%29.aspx).</span></span> 
  
<span data-ttu-id="1dd2a-113">Para usar uma conta de caixa de correio de recursos existente (por exemplo, LRS-01), siga as etapas abaixo:</span><span class="sxs-lookup"><span data-stu-id="1dd2a-113">To use an existing resource mailbox account (for example, LRS-01) follow the steps below:</span></span>
  
1. <span data-ttu-id="1dd2a-114">Execute o seguinte comando do PowerShell de Gerenciamento do Exchange:</span><span class="sxs-lookup"><span data-stu-id="1dd2a-114">Run the following Exchange Management PowerShell command:</span></span>
    
   ```
   Set-Mailbox -Name 'LRS-01' -Alias 'LRS01' -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

2. <span data-ttu-id="1dd2a-115">Se você planeja criar uma nova caixa de correio, para uma empresa do Exchange local de floresta única, execute o comando a seguir:</span><span class="sxs-lookup"><span data-stu-id="1dd2a-115">If you plan to create a new mailbox, then, for a single forest on-premises Exchange organization, run the following command:</span></span>
    
   ```
   New-Mailbox -UserPrincipalName LRS01@contoso.com -Alias LRS01 -Name "LRS-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

   <span data-ttu-id="1dd2a-p102">O exemplo acima cria uma conta de usuário habilitada no Active Directory e uma caixa de correio para sala de conferência em uma empresa local do Exchange. O parâmetro RoomMailboxPassword especifica a senha para a conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="1dd2a-p102">The above example creates an enabled user account in Active Directory and a room mailbox for a conference room in an on-premises Exchange organization. The RoomMailboxPassword parameter specifies the password for the user account.</span></span>
    
3. <span data-ttu-id="1dd2a-118">Configure a conta para solucionar conflitos automaticamente ao aceitar/rejeitar reuniões.</span><span class="sxs-lookup"><span data-stu-id="1dd2a-118">Configure the account to automatically resolve conflicts by accepting/rejecting meetings.</span></span> <span data-ttu-id="1dd2a-119">Sala de reuniões do Skype-as contas da sala de conferências equipadas no Exchange podem ser gerenciadas por indivíduos, mas observe que, até que a pessoa aceite uma reunião, ela não aparecerá no calendário da tela inicial do Skype Room System.</span><span class="sxs-lookup"><span data-stu-id="1dd2a-119">Skype Room System-equipped conference room accounts in Exchange can be managed by individuals, but note that until the individual accepts a meeting it will not appear on the Skype Room System home screen calendar.</span></span>
    
   ```
   Set-CalendarProcessing -Identity LRS01 -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteSubject $false -RemovePrivateProperty $false
   ```

   <span data-ttu-id="1dd2a-120">Para ver um conjunto completo de comandos disponíveis, consulte Set-CalendarProcessing.</span><span class="sxs-lookup"><span data-stu-id="1dd2a-120">For a complete set of commands available, see Set-CalendarProcessing.</span></span>
    
   <span data-ttu-id="1dd2a-121">Para lembrar os organizadores da reunião para que a reunião seja uma reunião online do Skype for Business no Outlook, execute o seguinte comando para configurar uma dica de tela para a nova conta:</span><span class="sxs-lookup"><span data-stu-id="1dd2a-121">To remind meeting organizers to make the meeting an online Skype for Business meeting in Outlook, run the following command to set up a MailTip for the new account:</span></span> 
    
   ```
   Set-Mailbox -Identity LRS01@contoso.com -MailTip "This room is equipped with Lync Meeting Room (LRS), please make it a Lync Meeting to take advantage of the enhanced meeting experience from LRS"
   ```
4. <span data-ttu-id="1dd2a-122">Use os seguintes comandos para configurar sequências de caracteres localizadas.</span><span class="sxs-lookup"><span data-stu-id="1dd2a-122">Use the following commands to configure localized strings.</span></span> <span data-ttu-id="1dd2a-123">Se for exigido por sua empresa, você pode também adicionar traduções personalizadas:</span><span class="sxs-lookup"><span data-stu-id="1dd2a-123">If required by your organization, you can also add custom translations:</span></span> 
   ```
   $Temp = Get-Mailbox  LRS01@ contoso.com 
   $Temp.MailTipTranslations += "ES: Spanish translation of the message"
   Set-Mailbox -Identity LRS01@contoso.com -MailTipTranslations $Temp.MailTipTranslations
   ```

5. <span data-ttu-id="1dd2a-124">Opcional: configurar o texto de aceitação da reunião que fornece aos usuários informações sobre a sala de reunião do Skype for Business e o que esperar quando agendar e ingressar em reuniões.</span><span class="sxs-lookup"><span data-stu-id="1dd2a-124">Optional: Configure meeting acceptance text that provides users with information about Skype for Business Meeting Room, and what to expect when they schedule and join meetings.</span></span> 
    
   ```
   Set-CalendarProcessing -Identity LRS01 -AddAdditionalResponse $TRUE -AdditionalResponse "This is the Additional Response Text"
   ```

## <a name="check-resource-mailbox-account-in-active-directory"></a><span data-ttu-id="1dd2a-125">Verifique a Conta da Caixa de Correio de Recursos no Active Directory</span><span class="sxs-lookup"><span data-stu-id="1dd2a-125">Check Resource Mailbox Account in Active Directory</span></span>

<span data-ttu-id="1dd2a-126">A conta da caixa de correio da sala de conferência criada pelo Exchange na etapa 1 acima pode ser um objeto de usuário desativado no Active Directory.</span><span class="sxs-lookup"><span data-stu-id="1dd2a-126">The conference room mailbox account created by Exchange in step 1 above might be a disabled user object in Active Directory.</span></span> <span data-ttu-id="1dd2a-127">O sistema de sala da Skype não pode entrar ou autenticar usando a autenticação Kerberos/NTLM se a conta estiver desabilitada no Active Directory.</span><span class="sxs-lookup"><span data-stu-id="1dd2a-127">Skype Room System cannot sign in or authenticate by using Kerberos/NTLM authentication if the account is disabled in Active Directory.</span></span> <span data-ttu-id="1dd2a-128">O cliente do sistema de sala do Skype deve ser capaz de se autenticar nos serviços Web do Exchange para recuperar as configurações do calendário e também deve ser capaz de enviar emails com conteúdo do whiteboard.</span><span class="sxs-lookup"><span data-stu-id="1dd2a-128">The Skype Room System client must be able to authenticate against Exchange Web Services to retrieve calendar settings, and must also be able to send email with whiteboard contents.</span></span> 
  
<span data-ttu-id="1dd2a-129">Portanto, se a conta estiver desativada, você deverá habilitá-la no Active Directory fazendo o seguinte:</span><span class="sxs-lookup"><span data-stu-id="1dd2a-129">Therefore, if the account is disabled, you must enable this account in Active Directory by doing the following:</span></span> 
  
1. <span data-ttu-id="1dd2a-130">No Active Directory, execute o seguinte comando para habilitar o login da conta:</span><span class="sxs-lookup"><span data-stu-id="1dd2a-130">In Active Directory, run the following command to enable account log on:</span></span> 
    
   ```
   Set-ADAccountPassword -Identity LRS01
   ```

   <span data-ttu-id="1dd2a-131">A execução desse comando solicitará que você insira a senha atual e, em seguida, insira novamente a senha duas vezes para confirmar.</span><span class="sxs-lookup"><span data-stu-id="1dd2a-131">Running this command will prompt you to enter the current password, and then to re-enter the password twice for confirmation.</span></span>
    
2. <span data-ttu-id="1dd2a-132">Após definir a senha, execute o seguinte comando para habilitar a conta:</span><span class="sxs-lookup"><span data-stu-id="1dd2a-132">Once the password is set, run the following command to enable the account:</span></span> 
    
   ```
   Enable-ADAccount -Identity LRS01
   ```

## <a name="enabling-skype-room-system-accounts-for-skype-for-business"></a><span data-ttu-id="1dd2a-133">Como habilitar contas do sistema de sala do Skype para o Skype for Business</span><span class="sxs-lookup"><span data-stu-id="1dd2a-133">Enabling Skype Room System Accounts for Skype for Business</span></span>

<span data-ttu-id="1dd2a-134">Esta seção fornece uma visão geral das etapas necessárias para habilitar o Skype for Business para a sua conta de sala de conferência, que será configurada no sistema de salas da Skype.</span><span class="sxs-lookup"><span data-stu-id="1dd2a-134">This section provides an overview of the steps required to enable Skype for Business for your conference room account, which will be configured on Skype Room System.</span></span> 
  
<span data-ttu-id="1dd2a-135">Depois de criar uma conta de caixa de correio de recursos para as salas de conferência, use o Shell de gerenciamento do Skype for Business Server para habilitar as contas do sistema de sala do Skype para serviços do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="1dd2a-135">After you create a resource mailbox account for the conferencing rooms, use Skype for Business Server Management Shell to enable Skype Room System accounts for Skype for Business services.</span></span>
  
> [!NOTE]
> <span data-ttu-id="1dd2a-136">O procedimento a seguir pressupõe que você habilitou a conta do sistema de sala do Skype no Active Directory.</span><span class="sxs-lookup"><span data-stu-id="1dd2a-136">The following procedure assumes that you have enabled the Skype Room System account in Active Directory.</span></span> 
  
1. <span data-ttu-id="1dd2a-137">Execute o seguinte comando para habilitar a conta do sistema de sala do Skype em um pool do servidor do Skype for Business:</span><span class="sxs-lookup"><span data-stu-id="1dd2a-137">Run the following command to enable the Skype Room System account on a Skype for Business Server pool:</span></span>
    
   ```
   Enable-CsMeetingRoom -SipAddress "sip:LRS01@contoso.com" -domaincontroller DC-ND-001.contoso.com -RegistrarPool LYNCPool15.contoso.com -Identity LRS01
   ```

2. <span data-ttu-id="1dd2a-138">Opcional: permita que essa conta faça e receba chamadas telefônicas PSTN, habilitando a conta para o Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="1dd2a-138">Optional: Allow this account to make and receive PSTN phone calls by enabling the account for Enterprise Voice.</span></span> <span data-ttu-id="1dd2a-139">O Enterprise Voice não é necessário para o sistema de sala da Skype, mas se você não habilitá-lo para o Enterprise Voice, o cliente do sistema de sala do Skype não poderá fornecer funcionalidade de discagem PSTN:</span><span class="sxs-lookup"><span data-stu-id="1dd2a-139">Enterprise Voice is not required for Skype Room System, but if you do not enable it for Enterprise Voice, the Skype Room System client won't be able to provide PSTN dialing functionality:</span></span>
    
   ```
   Set-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com -LineURItel: +14255550555;ext=50555"
   Set-CsMeetingRoom -domaincontroller DC-ND-001.contoso.com -Identity LRS01 -EnterpriseVoiceEnabled $true
   ```

> [!NOTE]
> <span data-ttu-id="1dd2a-140">Se você habilitar o Enterprise Voice para a conta da sala de conferências do Skype Room System, certifique-se de configurar uma política de voz restrita adequada para a sua organização.</span><span class="sxs-lookup"><span data-stu-id="1dd2a-140">If you enable Enterprise Voice for the Skype Room System conference room account, make sure to configure a restricted Voice Policy suitable for your organization.</span></span> <span data-ttu-id="1dd2a-141">Se a sala de reunião do Skype for Business for um recurso disponível publicamente, qualquer pessoa poderá usá-lo para ingressar em uma reunião, seja agendada ou ad hoc.</span><span class="sxs-lookup"><span data-stu-id="1dd2a-141">If the Skype for Business Meeting Room is a publicly available resource, anyone could use it to join a meeting, either scheduled or ad hoc.</span></span> <span data-ttu-id="1dd2a-142">Depois de ingressar em uma reunião, a pessoa pode discar para qualquer número.</span><span class="sxs-lookup"><span data-stu-id="1dd2a-142">After joining a meeting, the person could dial out to any number.</span></span> <span data-ttu-id="1dd2a-143">No Skype for Business Server, o recurso discagem de conferências usa a política de voz do usuário, nesse caso, a conta do sistema de sala do Skype usada para ingressar na reunião.</span><span class="sxs-lookup"><span data-stu-id="1dd2a-143">In Skype for Business Server, the dial-out from conferences feature uses the voice policy of the user, in this case the Skype Room System account used to join the meeting.</span></span> <span data-ttu-id="1dd2a-144">Nas versões anteriores do Lync Server, a política de voz do organizador era utilizada.</span><span class="sxs-lookup"><span data-stu-id="1dd2a-144">In earlier versions of Lync Server, the voice policy of the organizer is used.</span></span> <span data-ttu-id="1dd2a-145">Portanto, se um usuário de uma versão anterior do Lync Server agendar uma sala de reunião e convidar a conta da sala do sistema de sala da Skype, qualquer pessoa poderá usar a sala de reunião do Skype for Business para participar da reunião e poderá discar para qualquer telefone nacional/regional ou internacional número, desde que o organizador tenha permissão para discar esses números.</span><span class="sxs-lookup"><span data-stu-id="1dd2a-145">Therefore, if a user of an earlier version of Lync Server schedules a meeting room and invites the Skype Room System room account, anyone could use the Skype for Business Meeting Room to join the meeting and could dial any national/regional or international phone number, as long as the organizer is allowed to dial those numbers.</span></span> 
  

