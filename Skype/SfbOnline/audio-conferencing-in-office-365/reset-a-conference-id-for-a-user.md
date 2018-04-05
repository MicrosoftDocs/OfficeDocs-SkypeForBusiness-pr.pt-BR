---
title: Redefinir o ID de conferência de um usuário
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 6e12242c-55f7-4bf4-90d7-0f36c0326b8e
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: "Learn the steps to reset a user's meeting conference ID, and get links to meeting update and migration tools. "
ms.openlocfilehash: 6cc73876d188f1ae00ec267e14af4771ded7b957
ms.sourcegitcommit: ffca287cf70db2cab14cc1a6cb7cea68317bedd1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/05/2018
---
# <a name="reset-a-conference-id-for-a-user"></a><span data-ttu-id="e4178-103">Redefinir o ID de conferência de um usuário</span><span class="sxs-lookup"><span data-stu-id="e4178-103">Reset a conference ID for a user</span></span>

<span data-ttu-id="e4178-104">Quando suas organizações não tiver sido habilitado para IDs de conferência dinâmico, uma ID de conferência estática é criada automaticamente quando um Skype para negócios ou Microsoft Teams usuário está habilitado para conferência de áudio usando o Microsoft como o provedor.</span><span class="sxs-lookup"><span data-stu-id="e4178-104">When your organizations hasn't been enabled for dynamic conference IDs, a static conference ID is automatically created when a Skype for Business or Microsoft Teams user is enabled for Audio Conferencing using Microsoft as the provider.</span></span> <span data-ttu-id="e4178-105">Esta ID de conferência é incluído na parte inferior da reunião convites, juntamente com os números de telefone de discagem que podem ser usados por chamadores para efetuar uma chamada para uma reunião.</span><span class="sxs-lookup"><span data-stu-id="e4178-105">This conference ID is included at the bottom of meeting invitations along with the dial-in phone numbers that can be used by callers to call in to a meeting.</span></span> <span data-ttu-id="e4178-106">Quando o usuário disca o número de telefone, o atendedor automático para a reunião pedirá que o chamador para inserir esta ID de conferência, de forma que eles podem participar da reunião.</span><span class="sxs-lookup"><span data-stu-id="e4178-106">When the user dials the phone number, the auto attendant for the meeting will ask the caller to enter this conference ID so they can attend the meeting.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e4178-107">Se seu provedor de conferência for Microsoft, IDs de conferência dos usuários são definidos para somente dinâmico por padrão.</span><span class="sxs-lookup"><span data-stu-id="e4178-107">If your conferencing provider is Microsoft, your users' conference IDs are set to Dynamic Only by default.</span></span> <span data-ttu-id="e4178-108">Infelizmente, você não poderá alterá-lo no Skype para o Centro de administração de negócios ou usando o Windows Powershell.</span><span class="sxs-lookup"><span data-stu-id="e4178-108">Unfortunately, you won't be able to change it in the Skype for Business Admin Center or using Windows Powershell.</span></span> <span data-ttu-id="e4178-109">Você precisará contatar o suporte da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e4178-109">You will have to contact Microsoft support.</span></span> 
  
<span data-ttu-id="e4178-110">IDs estáticas são usadas quando as pessoas na sua organização não desejam Lembre-se de um número aleatório; eles podem selecionar um certo número ou use um que seja fácil de lembrar.</span><span class="sxs-lookup"><span data-stu-id="e4178-110">Static IDs are used when people in your organization don't want to remember a random number; they can select a certain number or use one that's easy to remember.</span></span> <span data-ttu-id="e4178-111">Se IDs de conferência dinâmicas estiverem sendo usadas, cada reunião agendada por um usuário terá uma ID de conferência exclusiva atribuída.</span><span class="sxs-lookup"><span data-stu-id="e4178-111">When dynamic conference IDs are used, each meeting that a user schedules will get assigned a unique conference ID.</span></span> <span data-ttu-id="e4178-112">Se você deseja atribuir dinâmico em vez de conferência estática IDs, [acesse aqui](using-audio-conferencing-dynamic-ids-in-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="e4178-112">If you want to assign dynamic rather than static conference IDs, [go here](using-audio-conferencing-dynamic-ids-in-your-organization.md).</span></span>
  
<span data-ttu-id="e4178-113">IDs de conferência são definidas apenas automaticamente somente para Skype para usuários empresariais e Microsoft Teams habilitado para serviços de audioconferência usando o Microsoft como seu provedor de serviços de audioconferência.</span><span class="sxs-lookup"><span data-stu-id="e4178-113">Conference IDs are only automatically set only for Skype for Business and Microsoft Teams users enabled for Audio Conferencing using Microsoft as their audio conferencing provider.</span></span> <span data-ttu-id="e4178-114">Se você precisar redefinir uma ID de conferência para um usuário que está usando um provedor de serviços de audioconferência de terceiros (ACP), você precisará digitar manualmente uma ID de conferência na página Propriedades do usuário.</span><span class="sxs-lookup"><span data-stu-id="e4178-114">If you need to reset a conference ID for a user who is using a third-party audio conferencing provider (ACP), you will need to manually enter a conference ID on the properties page for the user.</span></span>
  
## <a name="resetting-the-conference-id-for-a-user"></a><span data-ttu-id="e4178-115">Redefinindo o ID de conferência para um usuário</span><span class="sxs-lookup"><span data-stu-id="e4178-115">Resetting the conference ID for a user</span></span>

<span data-ttu-id="e4178-116">**Usando equipes da Microsoft e Skype para Business Admin Center**</span><span class="sxs-lookup"><span data-stu-id="e4178-116">**Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="e4178-117">No painel de navegação esquerdo, clique em **usuários**e, em seguida, selecione o usuário da lista de usuários disponíveis.</span><span class="sxs-lookup"><span data-stu-id="e4178-117">In the left navigation, click **Users**, and then select the user from teh list of available users.</span></span>

2. <span data-ttu-id="e4178-118">Na parte superior da página, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="e4178-118">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="e4178-119">Clique no menu ao lado de **Pontes de conferência**e, em seguida, clique em **Redefinir id de conferência** na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="e4178-119">Click the menu next to **Conference Bridges**, and then click **Reset conference id** in the drop-down list.</span></span>

2. <span data-ttu-id="e4178-120">Na janela **Redefinir id de conferência** , clique em **Okey**.</span><span class="sxs-lookup"><span data-stu-id="e4178-120">In the **Reset conference id** window, click **Ok**.</span></span> <span data-ttu-id="e4178-121">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span><span class="sxs-lookup"><span data-stu-id="e4178-121">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span> <span data-ttu-id="e4178-122">Por padrão, os emails são enviados aos usuários, mas isso pode ser desativado.</span><span class="sxs-lookup"><span data-stu-id="e4178-122">By default, emails are sent to users, but this can be turned off.</span></span>   

<span data-ttu-id="e4178-123">**Usando o Skype para o Centro de administração de negócios**</span><span class="sxs-lookup"><span data-stu-id="e4178-123">**Using the Skype for Business admin center**</span></span>
    
1. <span data-ttu-id="e4178-124">No **Skype para centro de administração de negócios**, clique em **conferência de áudio** > **usuários**, selecione um usuário e clique em **Redefinir**no painel de ação em **ID da conferência** .</span><span class="sxs-lookup"><span data-stu-id="e4178-124">In the **Skype for Business admin center**, click **Audio conferencing** > **Users**, select a user, and then in the Action pane under **Conference ID** click **Reset**.</span></span>
    
2. <span data-ttu-id="e4178-125">No **Redefinir ID de conferência?** janela, clique em **Sim**.</span><span class="sxs-lookup"><span data-stu-id="e4178-125">In the **Reset conference ID?** window, click **Yes**.</span></span> <span data-ttu-id="e4178-126">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span><span class="sxs-lookup"><span data-stu-id="e4178-126">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span> <span data-ttu-id="e4178-127">Por padrão, os emails são enviados aos usuários, mas isso pode ser desativado.</span><span class="sxs-lookup"><span data-stu-id="e4178-127">By default, emails are sent to users, but this can be turned off.</span></span>
    
> [!NOTE]
> <span data-ttu-id="e4178-p107">[!OBSERVAçãO] Depois de redefinir a ID de conferência, um email com a nova ID de conferência será enviado para o usuário. Esse email será enviado para o endereço de email primário do usuário. Em muitos casos, para a caixa de correio do Office 365. O email contém a nova ID de conferência, o(s) número(s) de telefone padrão de discagem e as instruções de como usar a Ferramenta de Atualização de Reunião do Skype for Business para atualizar reuniões existentes.</span><span class="sxs-lookup"><span data-stu-id="e4178-p107">After you reset the conference ID, an email with the new conference ID will be sent to the user. This email will be sent to the primary email address, in many cases, their Office 365 mailbox. The email contains the new conference ID, default dial-in phone number(s) and instructions to use the Skype for Business Meeting Update Tool to update existing meetings.</span></span> 
  
## <a name="what-else-should-i-know"></a><span data-ttu-id="e4178-131">O que mais devo saber?</span><span class="sxs-lookup"><span data-stu-id="e4178-131">What else should I know?</span></span>

- <span data-ttu-id="e4178-132">Você pode enviar todas as informações de conferência para o usuário em um email que inclua a ID de conferência e os números de telefone de discagem ao clicar em **Enviar informações de conferência via email** para o usuário no painel de ações.</span><span class="sxs-lookup"><span data-stu-id="e4178-132">You can send all of the conferencing information to the user in an email that includes the conference ID and dial-in phone numbers by clicking **Send conference info via email** for the user in the Action pane.</span></span> <span data-ttu-id="e4178-133">Isso não envia o PIN.</span><span class="sxs-lookup"><span data-stu-id="e4178-133">It doesn't send the PIN.</span></span>
    
- <span data-ttu-id="e4178-134">Uma ID de conferência conterá 7 dígitos, e você não poderá alterar seu tamanho no Skype para centro de administração de negócios ou usando o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e4178-134">A conference ID will contain 7 digits, and you can't change its length in the Skype for Business admin center or by using Windows PowerShell.</span></span>
    
- <span data-ttu-id="e4178-135">Depois que for redefinido, o novo ID de conferência será listado em **ID de Conferência**.</span><span class="sxs-lookup"><span data-stu-id="e4178-135">After it has been reset, you can see the new conference ID listed under **Conference ID**.</span></span>
    
- <span data-ttu-id="e4178-136">O ID de conferência para um usuário para conferência de áudio pode ser exibido na parte inferior do painel de ação em **conferência de áudio** quando você seleciona o usuário na página **usuários** .</span><span class="sxs-lookup"><span data-stu-id="e4178-136">The conference ID for a user for audio conferencing can be viewed at the bottom of the Action pane under **Audio conferencing** when you select the user on the **Users** page.</span></span>
    
- <span data-ttu-id="e4178-137">Depois que uma nova ID de conferência for criada, a ID antiga não poderá ser usada por chamadores.</span><span class="sxs-lookup"><span data-stu-id="e4178-137">After a new conference ID is created, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="e4178-138">Você deve notificar aos usuários para reagendarem suas reuniões existentes para garantir que a nova ID de conferência seja incluída nos convites.</span><span class="sxs-lookup"><span data-stu-id="e4178-138">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> <span data-ttu-id="e4178-139">Os usuários podem usar Skype para ferramenta de reunião de negócios para atualizar suas reuniões existentes.</span><span class="sxs-lookup"><span data-stu-id="e4178-139">The users can use Skype for Business Meeting Tool to update their existing meetings.</span></span> <span data-ttu-id="e4178-140">Para ver como baixar, instalar e executar o Skype para ferramenta de atualização de reunião de negócios, consulte:</span><span class="sxs-lookup"><span data-stu-id="e4178-140">To see how to download, install, and run the Skype for Business Meeting Update Tool, see:</span></span>
    
  - [<span data-ttu-id="e4178-141">Skype for Business (Lync) Meeting Update Tool</span><span class="sxs-lookup"><span data-stu-id="e4178-141">Meeting Update Tool for Skype for Business and Lync</span></span>](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)
    
  - [<span data-ttu-id="e4178-142">Skype for Business Online, ferramenta de migração de reuniões (64 bits)</span><span class="sxs-lookup"><span data-stu-id="e4178-142">Skype for Business Online, Meeting Migration Tool (64-bit)</span></span>](https://go.microsoft.com/fwlink/?LinkID=626047)
    
  - [<span data-ttu-id="e4178-143">Skype for Business Online, ferramenta de migração de reuniões (32 bits)</span><span class="sxs-lookup"><span data-stu-id="e4178-143">Skype for Business Online, Meeting Migration Tool (32-bit)</span></span>](https://www.microsoft.com/en-us/download/details.aspx?id=54079)
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="e4178-144">Quer saber como gerenciar com o Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="e4178-144">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="e4178-p110">O Windows PowerShell serve para o gerenciamento de usuários e do que os usuários podem ou não podem fazer. Com o Windows PowerShell, você pode gerenciar o Office 365 e o Skype for Business Online usando um único ponto de administração, o que pode simplificar o seu trabalho diário quando tiver várias tarefas para fazer. Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:</span><span class="sxs-lookup"><span data-stu-id="e4178-p110">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="e4178-148">Uma introdução ao Windows PowerShell e ao Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="e4178-148">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="e4178-149">Por que você precisa usar o PowerShell do Office 365</span><span class="sxs-lookup"><span data-stu-id="e4178-149">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="e4178-p111">O Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade em relação a usar somente o centro de administração do Office 365, como para fazer alterações de configuração para vários usuários ao mesmo tempo. Saiba mais sobre essas vantagens nos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="e4178-p111">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="e4178-152">Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e4178-152">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="e4178-153">Usar o Windows PowerShell para gerenciar o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="e4178-153">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="e4178-154">Usando o Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="e4178-154">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="e4178-155">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="e4178-155">Related topics</span></span>

[<span data-ttu-id="e4178-156">Redefinir o PIN de audioconferência de um usuário</span><span class="sxs-lookup"><span data-stu-id="e4178-156">Reset the Audio Conferencing PIN for a user</span></span>](reset-the-audio-conferencing-pin-for-a-user.md)
