---
title: Redefinir o PIN de Audioconferência no Skype for Business Online
mms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 67866a47-89c1-4593-8766-3a68777e2be6
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Descubra o que você deve saber sobre PINs e como redefini-los no Skype for Business Online. '
ms.openlocfilehash: 57431b51607f963f6dbd6da688e9bf7bd2758b53
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23854291"
---
# <a name="reset-the-audio-conferencing-pin-in-skype-for-business-online"></a><span data-ttu-id="ed3c4-103">Redefinir o PIN de Audioconferência no Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="ed3c4-103">Manage the Audio Conferencing settings for a user in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="ed3c4-104">Para obter informações sobre a redefinição de PINs de Audioconferência no Microsoft Teams, consulte [Redefinir o PIN de Audioconferência no Microsoft Teams](/MicrosoftTeams/reset-the-audio-conferencing-pin-in-teams).</span><span class="sxs-lookup"><span data-stu-id="ed3c4-104">For information about resetting Audio Conferencing PINs in Microsoft Teams, see [Reset the Audio Conferencing PIN in Microsoft Teams](/MicrosoftTeams/reset-the-audio-conferencing-pin-in-teams).</span></span>

<span data-ttu-id="ed3c4-105">Um PIN é um código formado por números que são criados para cada usuário do Skype for Business que esteja habilitado para serviços de audioconferência.</span><span class="sxs-lookup"><span data-stu-id="ed3c4-105">A PIN is a code made up of numbers that is created for each user who is enabled for dial-in conferencing.</span></span> <span data-ttu-id="ed3c4-106">Os PINs de audioconferência são usados pelos organizadores da reunião para identificar que eles são os organizadores e permitir que eles iniciem uma reunião usando o telefone.</span><span class="sxs-lookup"><span data-stu-id="ed3c4-106">Dial-in conferencing PINs are used by meeting organizers to identify that they are the meeting organizer and allow them to start a meeting over the phone.</span></span> <span data-ttu-id="ed3c4-107">Caso usem o aplicativo do Skype for Business para iniciar a reunião, o PIN não será necessário.</span><span class="sxs-lookup"><span data-stu-id="ed3c4-107">If they use the Skype for Business client to start the meeting, a PIN isn't required.</span></span> <span data-ttu-id="ed3c4-108">Se os usuários esquecerem o PIN e não conseguirem encontrá-lo no e-mail que foi enviado quando eles foram habilitados para a audioconferência, um administrador poderá redefinir o PIN dos usuários ou redefinir seu próprio PIN.</span><span class="sxs-lookup"><span data-stu-id="ed3c4-108">If users forget their PIN and they can't find it in the email that was sent to them when they were enabled for dial-in conferencing, an administrator will need to reset their PIN.</span></span>
  
<span data-ttu-id="ed3c4-109">As reuniões podem ser iniciadas quando um usuário autenticado participa usando o aplicativo do Skype for Business ou quando o organizador participa com seu PIN usando o telefone.</span><span class="sxs-lookup"><span data-stu-id="ed3c4-109">Meetings can be started when an authenticated user joins using a Skype for Business client or when the organizer joins with his or her PIN over the phone.</span></span> <span data-ttu-id="ed3c4-110">Se a reunião exigir um PIN para ser iniciada, os usuários que entrarem por telefone serão colocados no lobby e esperarão ouvindo música até que a reunião seja iniciada.</span><span class="sxs-lookup"><span data-stu-id="ed3c4-110">When a meeting requires a PIN to start, users who join over the phone will be placed in the lobby and will listen to music on hold until the meeting starts.</span></span> <span data-ttu-id="ed3c4-111">Se o organizador de uma reunião não exigir um PIN para iniciar a reunião por telefone, os chamadores não precisarão fornecer um PIN para participar.</span><span class="sxs-lookup"><span data-stu-id="ed3c4-111">If the organizer of a meeting doesn't require a PIN to start the meeting over the phone, then callers won't be asked to provide a PIN when they join the meeting.</span></span>
  
## <a name="reset-a-users-pin"></a><span data-ttu-id="ed3c4-112">Redefinir o PIN de um usuário</span><span class="sxs-lookup"><span data-stu-id="ed3c4-112">Reset a user's PIN</span></span>

1. <span data-ttu-id="ed3c4-113">Entre no Office 365 com sua conta corporativa ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="ed3c4-113">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="ed3c4-114">Vá até o **Centro de administração do Office 365** > **Skype for Business** e no painel de navegação à esquerda, clique em **Audioconferência**.</span><span class="sxs-lookup"><span data-stu-id="ed3c4-114">Go to the **Office 365 admin center** > **Skype for Business** and in the left navigation click **Dial-in conferencing**</span></span>
    
3. <span data-ttu-id="ed3c4-115">Clique em **Usuários** e selecione o usuário cujo PIN você deseja redefinir.</span><span class="sxs-lookup"><span data-stu-id="ed3c4-115">Click on **Dial-in users**, select the user that you want to reset the PIN for.</span></span>
    
4. <span data-ttu-id="ed3c4-116">No painel de Ação, em **PIN**, clique em **Redefinir**.</span><span class="sxs-lookup"><span data-stu-id="ed3c4-116">In the Action pane, click **Reset PIN**.</span></span>
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
   
## <a name="have-a-user-reset-his-or-her-own-pin"></a><span data-ttu-id="ed3c4-117">Faça com que um usuário redefina seu próprio PIN</span><span class="sxs-lookup"><span data-stu-id="ed3c4-117">Have a user reset his or her own PIN</span></span>

<span data-ttu-id="ed3c4-118">Um usuário pode redefinir um PIN usando a opção **Redefinir PIN** na página **Conferência discada** .</span><span class="sxs-lookup"><span data-stu-id="ed3c4-118">A user can reset a PIN by using the **Reset PIN** option on the **Dial-in Conferencing** page.</span></span> <span data-ttu-id="ed3c4-119">Essa página pode ser acessada de três formas:</span><span class="sxs-lookup"><span data-stu-id="ed3c4-119">This page can be accessed in one of three ways:</span></span>

* <span data-ttu-id="ed3c4-120">Em um navegador, vá até [https://mysettings.lync.com/pstncalling](https://mysettings.lync.com/pstncalling).</span><span class="sxs-lookup"><span data-stu-id="ed3c4-120">In a browser, go to [https://mysettings.lync.com/pstncalling](https://mysettings.lync.com/pstncalling).</span></span>
* <span data-ttu-id="ed3c4-121">No Skype for Business, clique na seta **Mostrar Menu** ao lado de **Opções** e, em seguida, clique em **Ferramentas** > **Configurações de conferência discada**.</span><span class="sxs-lookup"><span data-stu-id="ed3c4-121">In Skype for Business, click the **Show Menu** arrow next to **Options**, and then click **Tools** > **Dial-in Conference Settings**.</span></span>
* <span data-ttu-id="ed3c4-122">No Skype for Business, clique em **Opções**, depois em **Encaminhamento de chamadas** no menu à esquerda e na seção **Mais configurações de chamadas** , clique em **Editar configurações online**.</span><span class="sxs-lookup"><span data-stu-id="ed3c4-122">In Skype for Business, click **Options**, click **Call Forwarding** in the left menu, and then in the **More Call Settings** section, click **Edit settings online**.</span></span> 

## <a name="what-else-should-you-know-about-pins"></a><span data-ttu-id="ed3c4-123">O que mais você deve saber sobre PINs?</span><span class="sxs-lookup"><span data-stu-id="ed3c4-123">What else should you know about PINs?</span></span>

- <span data-ttu-id="ed3c4-124">Por motivos de segurança, o PIN só é mostrado para o administrador em uma ocasião: quando o PIN é redefinido.</span><span class="sxs-lookup"><span data-stu-id="ed3c4-124">For security purposes, the PIN is only shown to an administrator on one time, when the PIN is reset.</span></span> <span data-ttu-id="ed3c4-125">Depois que o PIN for redefinido por um administrador, ele será listado como \*\*\*\*\*\*\*\*\*\*\* no **centro de administração do Skype for Business**  e nos resultados quando usarem o comando Get-CsCsOnlineDialInConfencingUser no Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ed3c4-125">After the PIN is reset by an administrator, the PIN will be listed as \*\*\*\*\*\*\*\*\*\*\* in the Skype for Business admin center and in the results when they use **Get-CsCsOnlineDialInConfencingUser** in the Windows PowerShell.</span></span>
    
- <span data-ttu-id="ed3c4-126">O envio automático de e-mails para usuários é ativado por padrão e os usuários receberão um e-mail com o PIN quando estiverem habilitados para audioconferência ou quando o PIN for redefinido.</span><span class="sxs-lookup"><span data-stu-id="ed3c4-126">Automatically sending emails to users is enabled by default and users will receive an email with their PIN when they're enabled for dial-in conferencing or when the PIN is reset.</span></span> <span data-ttu-id="ed3c4-127">Entretanto, se você tiver desabilitado o envio automático de emails, o email de redefinição de PIN não será enviado para o usuário e você precisará enviar manualmente as informações de PIN para o usuário.</span><span class="sxs-lookup"><span data-stu-id="ed3c4-127">But if you have disabled automatically sending emails, then a PIN reset email won't be sent to a user and you will have to manually send the PIN information to the user.</span></span>
    
- <span data-ttu-id="ed3c4-p106">Quando uma reunião for iniciada, todos os usuários do lobby serão conectados automaticamente. Por exemplo, se dois participantes tentarem participar de uma reunião antes que ela seja iniciada, eles serão colocados no lobby e esperarão ouvindo música. Quando o organizador da reunião participar usando o PIN por telefone, a reunião será iniciada e os participantes do lobby entrarão na reunião.</span><span class="sxs-lookup"><span data-stu-id="ed3c4-p106">When a meeting starts, all of the users in the lobby will automatically join it. For example, if two participants try to join a meeting before it has been started, they will be put in the lobby and will listen to music on hold, and when the meeting organizer joins using his PIN via phone, the meeting will start and the participants in the lobby will join the meeting.</span></span>
    
- <span data-ttu-id="ed3c4-130">A configuração padrão é não permitir que uma reunião seja iniciada por autores de chamadas anônimos.</span><span class="sxs-lookup"><span data-stu-id="ed3c4-130">The default setting isn't to allow a meeting to be started by an anonymous callers.</span></span>
    
- <span data-ttu-id="ed3c4-131">Quando você habilita um usuário para audioconferências, por padrão, ele recebe emails que incluem informações da conferência e seu PIN.</span><span class="sxs-lookup"><span data-stu-id="ed3c4-131">When you enable a user for dial-in conferencing, by default they are sent emails that includes conferencing information and their PIN.</span></span> <span data-ttu-id="ed3c4-132">O usuário deve ter uma caixa de correio do Office 365 porque, quando um PIN é redefinido, um novo PIN será enviado ao usuário por email para o endereço SMTP principal (alias) definido para o usuário.</span><span class="sxs-lookup"><span data-stu-id="ed3c4-132">The user must have an Office 365 mailbox because when a PIN is reset, a new PIN will be sent to the user in email to their primary SMTP address (alias) that is set for the user.</span></span>
    
- <span data-ttu-id="ed3c4-133">Quando você configura serviços de audioconferência, você pode definir os dígitos que são necessários para os PINs em sua organização.</span><span class="sxs-lookup"><span data-stu-id="ed3c4-133">When you set up audio conferencing, you set the digits that are required for the PINs in your organization.</span></span> <span data-ttu-id="ed3c4-134">PINs podem ter de 4 a 12 dígitos - o padrão são 5 dígitos.</span><span class="sxs-lookup"><span data-stu-id="ed3c4-134">PINs can be from 4 to 12 digits - the default is 5.</span></span> <span data-ttu-id="ed3c4-135">Se você alterar a configuração do tamanho do PIN, a configuração será aplicada somente aos PINs recém-gerados e não será aplicada à configuração do PIN para usuários existentes que estejam habilitados para audioconferência.</span><span class="sxs-lookup"><span data-stu-id="ed3c4-135">If you change the PIN length setting, the setting is only applied on newly generated PINs and isn't applied to the PIN setting for existing users that are enabled for audio conferencing.</span></span> <span data-ttu-id="ed3c4-136">Consulte [Definir o tamanho do PIN para reuniões de Audioconferência](Set-the-PIN-length-for-Audio-Conferencing-meetings.md).</span><span class="sxs-lookup"><span data-stu-id="ed3c4-136">[](Set-the-PIN-length-for-Audio-Conferencing-meetings.md)Set the length of the PIN for Audio Conferencing meetings</span></span>
    
- <span data-ttu-id="ed3c4-137">Por padrão, o email será definido como o endereço SMTP principal do Office 365 do usuário.</span><span class="sxs-lookup"><span data-stu-id="ed3c4-137">The email by default will be set to the Office 365 primary SMTP address of the user.</span></span> <span data-ttu-id="ed3c4-138">Você pode enviar um email para um endereço que não seja do Office 365, como um endereço de email do Hotmail ou do MSN.</span><span class="sxs-lookup"><span data-stu-id="ed3c4-138">You can send an email to a non-Office 365 address such as a Hotmail or MSN email address.</span></span> <span data-ttu-id="ed3c4-139">Você pode substituir o endereço de email padrão usando o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ed3c4-139">You can override the default email address by using Windows PowerShell.</span></span> <span data-ttu-id="ed3c4-140">Isso é útil se os usuários não tiverem uma caixa de correio do Exchange no Office 365.</span><span class="sxs-lookup"><span data-stu-id="ed3c4-140">This is useful if the users don't have an Exchange mailbox in Office 365.</span></span>
    
- <span data-ttu-id="ed3c4-141">Para substituir o endereço de usuário padrão para o qual o email é enviado, o administrador do locatário pode usar o seguinte cmdlet: Set-CsOnlineDialInConferencingUser -amos.marble -ResetLeaderPIN -SendEmail -SendEmailToAddress "u@hotmail.com".</span><span class="sxs-lookup"><span data-stu-id="ed3c4-141">To override the default user address where the email is sent to, the tenant admin can use the following cmdlet:  .</span></span> <span data-ttu-id="ed3c4-142">O parâmetro SendEmail é obrigatório para substituir o endereço de email do usuário.</span><span class="sxs-lookup"><span data-stu-id="ed3c4-142">The  SendEmail parameter is required to override the email address of the user.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="ed3c4-143">Quer saber como gerenciar com o Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="ed3c4-143">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="ed3c4-144">Para economizar tempo ou automatizar o processo, você pode usar o cmdlet [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ).</span><span class="sxs-lookup"><span data-stu-id="ed3c4-144">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) cmdlet.</span></span>
    
- <span data-ttu-id="ed3c4-145">Você pode definir o PIN do Amos Marble executando:</span><span class="sxs-lookup"><span data-stu-id="ed3c4-145">You can set the PIN for Amos Marble by running:</span></span>
    
  ```
  Set-CsOnlineDialInConferencingUser -id amos.marble@contoso.com -ResetLeaderPIN
  ```

- <span data-ttu-id="ed3c4-p111">O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com o Windows PowerShell, você pode gerenciar o Office 365 usando um ponto único de administração para simplificar seu trabalho diário quando houver várias tarefas a serem feitas. Para começar a usar o Windows PowerShell, consulte estes tópicos:</span><span class="sxs-lookup"><span data-stu-id="ed3c4-p111">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="ed3c4-149">Por que você precisa usar o PowerShell do Office 365</span><span class="sxs-lookup"><span data-stu-id="ed3c4-149">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="ed3c4-150">Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ed3c4-150">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="ed3c4-151">O Windows PowerShell tem muitas vantagens de velocidade, simplicidade e produtividade em comparação ao uso exclusivo do centro de administração do Office 365, como quando você está fazendo alterações de configurações para muitos usuários ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="ed3c4-151">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="ed3c4-152">Saiba mais sobre essas vantagens nos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="ed3c4-152">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="ed3c4-153">Uma introdução ao Windows PowerShell e ao Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="ed3c4-153">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [<span data-ttu-id="ed3c4-154">Usar o Windows PowerShell para gerenciar o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="ed3c4-154">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="ed3c4-155">Uso do Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="ed3c4-155">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="ed3c4-p113">[!OBSERVAçãO] O módulo Windows PowerShell para Skype for Business Online permite que você crie uma sessão remota do Windows PowerShell que se conecta ao Skype for Business Online. Esse módulo, que tem suporte apenas em computadores de 64 bits, pode ser baixado do Centro de Download da Microsoft em [Módulo Windows PowerShell para Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span><span class="sxs-lookup"><span data-stu-id="ed3c4-p113">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="ed3c4-158">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="ed3c4-158">Related topics</span></span>

[<span data-ttu-id="ed3c4-159">Redefinir a ID de conferência de um usuário</span><span class="sxs-lookup"><span data-stu-id="ed3c4-159">Reset a conference ID for a user</span></span>](reset-a-conference-id-for-a-user.md)
