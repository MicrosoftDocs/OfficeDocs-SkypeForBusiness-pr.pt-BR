---
title: Redefinir o PIN de audioconferência no Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 67866a47-89c1-4593-8766-3a68777e2be6
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-apr2020
description: Saiba como redefinir o PIN de Audioconferência de um usuário no Microsoft Teams e saiba fatos importantes sobre PINs.
ms.openlocfilehash: 7ea380fbeb722337eaec598823b12dbe18f49918
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117629"
---
# <a name="reset-the-audio-conferencing-pin-in-microsoft-teams"></a><span data-ttu-id="876d5-103">Redefinir o PIN de audioconferência no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="876d5-103">Reset the Audio Conferencing PIN in Microsoft Teams</span></span>

<span data-ttu-id="876d5-104">Um PIN é um código que é criado para cada usuário do Microsoft Teams habilitado para audioconferência.</span><span class="sxs-lookup"><span data-stu-id="876d5-104">A PIN is a code made up of numbers that is created for each Microsoft Teams user who is enabled for audio conferencing.</span></span> <span data-ttu-id="876d5-105">Os PINs de audioconferência são usados pelos organizadores da reunião para identificar que eles são o organizador da reunião e permitir que eles iniciem uma reunião por telefone.</span><span class="sxs-lookup"><span data-stu-id="876d5-105">Audio conferencing PINs are used by meeting organizers to identify that they are the meeting organizer and allow them to start a meeting over the phone.</span></span> <span data-ttu-id="876d5-106">Se eles usarem o aplicativo do Microsoft Teams para iniciar a reunião, um PIN não será necessário.</span><span class="sxs-lookup"><span data-stu-id="876d5-106">If they use the Microsoft Teams app to start the meeting, a PIN isn't required.</span></span> <span data-ttu-id="876d5-107">Se os usuários esquecerem o PIN e não puderem encontrá-lo no email que foi enviado para eles quando eles foram habilitados para audioconferência, um administrador pode redefinir seu PIN ou pode redefinir seu próprio PIN.</span><span class="sxs-lookup"><span data-stu-id="876d5-107">If users forget their PIN and they can't find it in the email that was sent to them when they were enabled for audio conferencing, an administrator can reset their PIN, or they can reset their own PIN.</span></span>
  
<span data-ttu-id="876d5-108">As reuniões podem ser iniciadas quando um usuário autenticado entra usando o aplicativo do Microsoft Teams ou quando o organizador ins junta seu PIN pelo telefone.</span><span class="sxs-lookup"><span data-stu-id="876d5-108">Meetings can be started when an authenticated user joins using the Microsoft Teams app or when the organizer joins with their PIN over the phone.</span></span> <span data-ttu-id="876d5-109">Se a reunião exigir um PIN para ser iniciada, os usuários que entrarem por telefone serão colocados no lobby e esperarão ouvindo música até que a reunião seja iniciada.</span><span class="sxs-lookup"><span data-stu-id="876d5-109">When a meeting requires a PIN to start, users who join over the phone will be placed in the lobby and will listen to music on hold until the meeting starts.</span></span> <span data-ttu-id="876d5-110">Se o organizador de uma reunião não exigir um PIN para iniciar a reunião por telefone, os chamadores não precisarão fornecer um PIN para participar.</span><span class="sxs-lookup"><span data-stu-id="876d5-110">If the organizer of a meeting doesn't require a PIN to start the meeting over the phone, then callers won't be asked to provide a PIN when they join the meeting.</span></span>

## <a name="reset-a-users-pin"></a><span data-ttu-id="876d5-111">Redefinir o PIN de um usuário</span><span class="sxs-lookup"><span data-stu-id="876d5-111">Reset a user's PIN</span></span>

<span data-ttu-id="876d5-112">![Um ícone que mostra o logotipo do Microsoft Teams](media/teams-logo-30x30.png) **Usando o centro de administração do Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="876d5-112">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="876d5-113">Na navegação à esquerda, clique em **Usuários** e selecione o usuário na lista de usuários disponíveis.</span><span class="sxs-lookup"><span data-stu-id="876d5-113">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="876d5-114">Clique **em Editar**.</span><span class="sxs-lookup"><span data-stu-id="876d5-114">Click **Edit**.</span></span>

3. <span data-ttu-id="876d5-115">Em **Audioconferência,** clique em **Redefinir PIN**.</span><span class="sxs-lookup"><span data-stu-id="876d5-115">Under **Audio Conferencing**, click **Reset PIN**.</span></span>

4. <span data-ttu-id="876d5-116">Clique **em Redefinir**.</span><span class="sxs-lookup"><span data-stu-id="876d5-116">Click **Reset**.</span></span>
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
   
## <a name="have-a-user-reset-their-own-pin"></a><span data-ttu-id="876d5-117">Fazer com que um usuário redefinir seu próprio PIN</span><span class="sxs-lookup"><span data-stu-id="876d5-117">Have a user reset their own PIN</span></span>

1. <span data-ttu-id="876d5-118">Fazer o usuário ir para [https://admin0m.online.lync.com/lscp/usp/pstnconferencing](https://admin0m.online.lync.com/lscp/usp/pstnconferencing) .</span><span class="sxs-lookup"><span data-stu-id="876d5-118">Have the user go to [https://admin0m.online.lync.com/lscp/usp/pstnconferencing](https://admin0m.online.lync.com/lscp/usp/pstnconferencing).</span></span>
2. <span data-ttu-id="876d5-119">Clique **em Redefinir PIN**.</span><span class="sxs-lookup"><span data-stu-id="876d5-119">Click **Reset PIN**.</span></span> 

> [!NOTE]
> <span data-ttu-id="876d5-120">Para GCCH, vá para: https://webdir2g.online.gov.skypeforbusiness.us/lscp/usp/pstnconferencing .</span><span class="sxs-lookup"><span data-stu-id="876d5-120">For GCCH go to: https://webdir2g.online.gov.skypeforbusiness.us/lscp/usp/pstnconferencing.</span></span>

## <a name="what-else-should-you-know-about-pins"></a><span data-ttu-id="876d5-121">O que mais você deve saber sobre PINs?</span><span class="sxs-lookup"><span data-stu-id="876d5-121">What else should you know about PINs?</span></span>

- <span data-ttu-id="876d5-122">Para fins de segurança, o PIN só é mostrado a um administrador uma vez, quando o PIN é redefinido.</span><span class="sxs-lookup"><span data-stu-id="876d5-122">For security purposes, the PIN is only shown to an administrator one time, when the PIN is reset.</span></span> <span data-ttu-id="876d5-123">Depois que o PIN for redefinido por um administrador, o PIN será listado como \*\*\*\*\*\*\*\*\*.</span><span class="sxs-lookup"><span data-stu-id="876d5-123">After the PIN is reset by an administrator, the PIN will be listed as \*\*\*\*\*\*\*\*\*\*\*.</span></span>
    
- <span data-ttu-id="876d5-124">O envio automático de emails para usuários está habilitado por padrão e os usuários receberão um email com seu PIN quando eles estão habilitados para audioconferência ou quando o PIN for redefinido.</span><span class="sxs-lookup"><span data-stu-id="876d5-124">Automatically sending emails to users is enabled by default, and users will receive an email with their PIN when they're enabled for audio conferencing or when the PIN is reset.</span></span> <span data-ttu-id="876d5-125">Mas se você tiver desabilitado o envio automático de emails, um email de redefinição de PIN não será enviado para um usuário e você terá que enviar manualmente as informações de PIN para o usuário.</span><span class="sxs-lookup"><span data-stu-id="876d5-125">But if you have disabled automatically sending emails, a PIN reset email won't be sent to a user and you will have to manually send the PIN information to the user.</span></span>
    
- <span data-ttu-id="876d5-126">Quando uma reunião é iniciada, todos os usuários no lobby ingressarão automaticamente.</span><span class="sxs-lookup"><span data-stu-id="876d5-126">When a meeting starts, all of the users in the lobby will automatically join it.</span></span> <span data-ttu-id="876d5-127">Por exemplo, se dois participantes tentarem ingressar em uma reunião antes de começar, eles serão colocados no lobby e ouvirão música em espera, e quando o organizador da reunião ingressar usando seu PIN por telefone, a reunião será iniciada e os participantes no lobby ingressarão na reunião.</span><span class="sxs-lookup"><span data-stu-id="876d5-127">For example, if two participants try to join a meeting before it has been started, they will be put in the lobby and will listen to music on hold, and when the meeting organizer joins using their PIN via phone, the meeting will start and the participants in the lobby will join the meeting.</span></span>
    
- <span data-ttu-id="876d5-128">A configuração padrão é não permitir que uma reunião seja iniciada por chamadores anônimos.</span><span class="sxs-lookup"><span data-stu-id="876d5-128">The default setting is to not allow a meeting to be started by anonymous callers.</span></span>
    
- <span data-ttu-id="876d5-129">Quando você habilita um usuário para audioconferência, por padrão, eles são enviados emails que incluem informações de conferência e seu PIN.</span><span class="sxs-lookup"><span data-stu-id="876d5-129">When you enable a user for audio conferencing, by default they are sent emails that include conferencing information and their PIN.</span></span> <span data-ttu-id="876d5-130">O usuário deve ter uma caixa de correio do Microsoft 365 ou Office 365, pois quando um PIN é redefinido, um novo PIN será enviado ao usuário por email para seu endereço SMTP principal (alias) definido para o usuário.</span><span class="sxs-lookup"><span data-stu-id="876d5-130">The user must have a Microsoft 365 or Office 365 mailbox, because when a PIN is reset, a new PIN will be sent to the user in email to their primary SMTP address (alias) that is set for the user.</span></span>
    
- <span data-ttu-id="876d5-131">Quando você configura serviços de audioconferência, você pode definir os dígitos que são necessários para os PINs em sua organização.</span><span class="sxs-lookup"><span data-stu-id="876d5-131">When you set up audio conferencing, you set the digits that are required for the PINs in your organization.</span></span> <span data-ttu-id="876d5-132">PINs podem ter somente de 4 a 12 dígitos, o padrão é 5.</span><span class="sxs-lookup"><span data-stu-id="876d5-132">PINs can be from 4 to 12 digits - the default is 5.</span></span> <span data-ttu-id="876d5-133">Se você alterar a configuração do tamanho do PIN, a configuração será aplicada somente aos PINs recém-gerados e não será aplicada à configuração do PIN para usuários existentes que estejam habilitados para audioconferência.</span><span class="sxs-lookup"><span data-stu-id="876d5-133">If you change the PIN length setting, the setting is only applied on newly generated PINs and isn't applied to the PIN setting for existing users that are enabled for audio conferencing.</span></span> <span data-ttu-id="876d5-134">Consulte [Definir o tamanho do PIN para reuniões de Audioconferência.](Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="876d5-134">See [Set the length of the PIN for Audio Conferencing meetings](Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams.md).</span></span>
    
- <span data-ttu-id="876d5-135">O email por padrão será definido como o endereço SMTP principal do usuário do Microsoft 365 ou Office 365.</span><span class="sxs-lookup"><span data-stu-id="876d5-135">The email by default will be set to the Microsoft 365 or Office 365 primary SMTP address of the user.</span></span> <span data-ttu-id="876d5-136">Você pode enviar um email para um endereço que não seja do Microsoft 365 ou que não seja do Office 365, como um endereço de email hotmail ou MSN.</span><span class="sxs-lookup"><span data-stu-id="876d5-136">You can send an email to a non-Microsoft 365 or non-Office 365 address such as a Hotmail or MSN email address.</span></span> <span data-ttu-id="876d5-137">Você pode substituir o endereço de email padrão usando o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="876d5-137">You can override the default email address by using Windows PowerShell.</span></span> <span data-ttu-id="876d5-138">Isso será útil se os usuários não têm uma caixa de correio do Exchange no Microsoft 365 ou no Office 365.</span><span class="sxs-lookup"><span data-stu-id="876d5-138">This is useful if the users don't have an Exchange mailbox in Microsoft 365 or Office 365.</span></span>

    

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="876d5-139">Deseja saber mais sobre o Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="876d5-139">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="876d5-140">O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer.</span><span class="sxs-lookup"><span data-stu-id="876d5-140">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="876d5-141">Com Windows PowerShell, você pode gerenciar o Microsoft 365 ou o Office 365 usando um único ponto de administração que pode simplificar seu trabalho diário quando você tem várias tarefas a fazer.</span><span class="sxs-lookup"><span data-stu-id="876d5-141">With Windows PowerShell, you can manage Microsoft 365 or Office 365 by using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="876d5-142">Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:</span><span class="sxs-lookup"><span data-stu-id="876d5-142">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="876d5-143">Por que você precisa usar o PowerShell do Office 365</span><span class="sxs-lookup"><span data-stu-id="876d5-143">Why you need to use Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - <span data-ttu-id="876d5-144">[Melhores maneiras de gerenciar o Microsoft 365 ou o Office 365 com Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="876d5-144">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
<span data-ttu-id="876d5-145">Para obter mais informações sobre o Windows PowerShell, consulte a [referência do Microsoft Teams PowerShell](/powershell/module/teams/?view=teams-ps) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="876d5-145">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="876d5-146">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="876d5-146">Related topics</span></span>

[<span data-ttu-id="876d5-147">Redefinir a ID de conferência de um usuário</span><span class="sxs-lookup"><span data-stu-id="876d5-147">Reset a conference ID for a user</span></span>](reset-a-conference-id-for-a-user-in-teams.md)