---
title: Redefinir uma ID de conferência para um usuário no Skype for Business Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 6e12242c-55f7-4bf4-90d7-0f36c0326b8e
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Saiba quais são as etapas para redefinir a ID de conferência da reunião de um usuário no Skype for Business Online e obter links para as ferramentas de migração e atualização de reunião. '
ms.openlocfilehash: dd6d97400f5fdde9d1821f2843f1b48060b5886e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34299102"
---
# <a name="reset-a-conference-id-for-a-user-in-skype-for-business-online"></a><span data-ttu-id="c5e4f-103">Redefinir uma ID de conferência para um usuário no Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="c5e4f-103">Reset a conference ID for a user in Skype for Business Online</span></span>

> [!NOTE]
> <span data-ttu-id="c5e4f-104">Para obter informações sobre como redefinir a ID de conferência no Microsoft Teams, consulte [redefinir uma ID de conferência para um usuário no Microsoft Teams](/MicrosoftTeams/reset-a-conference-id-for-a-user-in-teams).</span><span class="sxs-lookup"><span data-stu-id="c5e4f-104">For information about resetting conference ID in Microsoft Teams, see [Reset a conference ID for a user in Microsoft Teams](/MicrosoftTeams/reset-a-conference-id-for-a-user-in-teams).</span></span>

<span data-ttu-id="c5e4f-105">Uma ID de conferência dinâmica está incluída na parte inferior dos convites para reunião juntamente com os números de telefone de discagem que podem ser usados pelos chamadores para ligar para uma reunião.</span><span class="sxs-lookup"><span data-stu-id="c5e4f-105">A dynamic conference ID is included at the bottom of meeting invitations along with the dial-in phone numbers that can be used by callers to call in to a meeting.</span></span> <span data-ttu-id="c5e4f-106">Quando o usuário discar o número de telefone, o atendedor automático da reunião solicitará que o chamador digite essa ID de conferência para que ela possa participar da reunião.</span><span class="sxs-lookup"><span data-stu-id="c5e4f-106">When the user dials the phone number, the auto attendant for the meeting will ask the caller to enter this conference ID so they can attend the meeting.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c5e4f-107">Se o seu provedor de serviços de conferência for a Microsoft, os IDs de Conferência dos seus usuários serão definidos como somente dinâmico.</span><span class="sxs-lookup"><span data-stu-id="c5e4f-107">If your conferencing provider is Microsoft, your users' conference IDs are set to Dynamic Only.</span></span> <span data-ttu-id="c5e4f-108">Isso não pode ser alterado.</span><span class="sxs-lookup"><span data-stu-id="c5e4f-108">This cannot be changed.</span></span> <span data-ttu-id="c5e4f-109">As IDs de conferência são definidas automaticamente somente para usuários do Skype for Business habilitados para videoconferências.</span><span class="sxs-lookup"><span data-stu-id="c5e4f-109">Conference IDs are automatically set only for Skype for Business users enabled for Audio Conferencing.</span></span> 

## <a name="resetting-the-conference-id-for-a-user"></a><span data-ttu-id="c5e4f-110">Redefinir a ID de conferência de um usuário</span><span class="sxs-lookup"><span data-stu-id="c5e4f-110">Resetting the conference ID for a user</span></span>
   
1. <span data-ttu-id="c5e4f-111">No **centro de administração do Skype for Business**, clique em**usuários**de **audioconferência** > , selecione um usuário e, no painel Ação, em **ID de conferência** , clique em **Redefinir**.</span><span class="sxs-lookup"><span data-stu-id="c5e4f-111">In the **Skype for Business admin center**, click **Audio conferencing** > **Users**, select a user, and then in the Action pane under **Conference ID** click **Reset**.</span></span>
    
2. <span data-ttu-id="c5e4f-112">Na janela **Redefinir ID de conferência?** , clique em **Sim**.</span><span class="sxs-lookup"><span data-stu-id="c5e4f-112">In the **Reset conference ID?** window, click **Yes**.</span></span> <span data-ttu-id="c5e4f-113">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span><span class="sxs-lookup"><span data-stu-id="c5e4f-113">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span> <span data-ttu-id="c5e4f-114">Por padrão, os emails são enviados para os usuários, mas isso pode ser desativado.</span><span class="sxs-lookup"><span data-stu-id="c5e4f-114">By default, emails are sent to users, but this can be turned off.</span></span>
    
> [!NOTE]
> <span data-ttu-id="c5e4f-p104">[!OBSERVAçãO] Depois de redefinir a ID de conferência, um email com a nova ID de conferência será enviado para o usuário. Esse email será enviado para o endereço de email primário do usuário. Em muitos casos, para a caixa de correio do Office 365. O email contém a nova ID de conferência, o(s) número(s) de telefone padrão de discagem e as instruções de como usar a Ferramenta de Atualização de Reunião do Skype for Business para atualizar reuniões existentes.</span><span class="sxs-lookup"><span data-stu-id="c5e4f-p104">After you reset the conference ID, an email with the new conference ID will be sent to the user. This email will be sent to the primary email address, in many cases, their Office 365 mailbox. The email contains the new conference ID, default dial-in phone number(s) and instructions to use the Skype for Business Meeting Update Tool to update existing meetings.</span></span> 
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="what-else-should-i-know"></a><span data-ttu-id="c5e4f-118">O que mais devo saber?</span><span class="sxs-lookup"><span data-stu-id="c5e4f-118">What else should I know?</span></span>

- <span data-ttu-id="c5e4f-119">Você pode enviar todas as informações da conferência para o usuário em um email que inclua a ID de conferência e os números de telefone de discagem clicando em **enviar informações de conferência por email** para o usuário no painel ação.</span><span class="sxs-lookup"><span data-stu-id="c5e4f-119">You can send all of the conferencing information to the user in an email that includes the conference ID and dial-in phone numbers by clicking **Send conference info via email** for the user in the Action pane.</span></span> <span data-ttu-id="c5e4f-120">Isso não envia o PIN.</span><span class="sxs-lookup"><span data-stu-id="c5e4f-120">It doesn't send the PIN.</span></span>
    
- <span data-ttu-id="c5e4f-121">Uma ID de conferência terá 7 dígitos e você não poderá alterar seu comprimento no centro de administração do Skype for Business ou usando o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c5e4f-121">A conference ID will contain 7 digits, and you can't change its length in the Skype for Business admin center or by using Windows PowerShell.</span></span>
    
- <span data-ttu-id="c5e4f-122">Depois que for redefinido, o novo ID de conferência será listado em **ID de Conferência**.</span><span class="sxs-lookup"><span data-stu-id="c5e4f-122">After it has been reset, you can see the new conference ID listed under **Conference ID**.</span></span>
    
- <span data-ttu-id="c5e4f-123">A ID de conferência de um usuário para videoconferência pode ser visualizada na parte inferior do painel de ação, em **videoconferência** , quando você seleciona o usuário na página **usuários** .</span><span class="sxs-lookup"><span data-stu-id="c5e4f-123">The conference ID for a user for audio conferencing can be viewed at the bottom of the Action pane under **Audio conferencing** when you select the user on the **Users** page.</span></span>
    
- <span data-ttu-id="c5e4f-124">[!IMPORTANTE]  Depois que um novo ID de conferência for criado, o ID antigo não poderá ser usado por chamadores.</span><span class="sxs-lookup"><span data-stu-id="c5e4f-124">After a new conference ID is created, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="c5e4f-125">Você deve notificar aos usuários para reagendarem suas reuniões existentes para garantir que o novo ID de conferência seja incluído nos convites.</span><span class="sxs-lookup"><span data-stu-id="c5e4f-125">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> <span data-ttu-id="c5e4f-126">Os usuários podem usar a ferramenta de reunião do Skype for Business para atualizar suas reuniões existentes.</span><span class="sxs-lookup"><span data-stu-id="c5e4f-126">The users can use Skype for Business Meeting Tool to update their existing meetings.</span></span> <span data-ttu-id="c5e4f-127">Para ver como baixar, instalar e executar a ferramenta de atualização de reunião do Skype for Business, consulte:</span><span class="sxs-lookup"><span data-stu-id="c5e4f-127">To see how to download, install, and run the Skype for Business Meeting Update Tool, see:</span></span>
    
  - [<span data-ttu-id="c5e4f-128">Skype for Business (Lync) Meeting Update Tool</span><span class="sxs-lookup"><span data-stu-id="c5e4f-128">Meeting Update Tool for Skype for Business and Lync</span></span>](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)
    
  - [<span data-ttu-id="c5e4f-129">Skype for Business Online, ferramenta de migração de reuniões (64 bits)</span><span class="sxs-lookup"><span data-stu-id="c5e4f-129">Skype for Business Online, Meeting Migration Tool (64-bit)</span></span>](https://go.microsoft.com/fwlink/?LinkID=626047)
    
  - [<span data-ttu-id="c5e4f-130">Skype for Business Online, ferramenta de migração de reuniões (32 bits)</span><span class="sxs-lookup"><span data-stu-id="c5e4f-130">Skype for Business Online, Meeting Migration Tool (32-bit)</span></span>](https://www.microsoft.com/en-us/download/details.aspx?id=54079)
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="c5e4f-131">Quer saber como gerenciar com o Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="c5e4f-131">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="c5e4f-p107">O Windows PowerShell serve para o gerenciamento de usuários e do que os usuários podem ou não podem fazer. Com o Windows PowerShell, você pode gerenciar o Office 365 e o Skype for Business Online usando um único ponto de administração, o que pode simplificar o seu trabalho diário quando tiver várias tarefas para fazer. Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:</span><span class="sxs-lookup"><span data-stu-id="c5e4f-p107">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="c5e4f-135">Uma introdução ao Windows PowerShell e ao Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="c5e4f-135">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="c5e4f-136">Por que você precisa usar o PowerShell do Office 365</span><span class="sxs-lookup"><span data-stu-id="c5e4f-136">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="c5e4f-p108">O Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade em relação a usar somente o centro de administração do Office 365, como para fazer alterações de configuração para vários usuários ao mesmo tempo. Saiba mais sobre essas vantagens nos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="c5e4f-p108">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="c5e4f-139">Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c5e4f-139">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="c5e4f-140">Usar o Windows PowerShell para gerenciar o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="c5e4f-140">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="c5e4f-141">Usando o Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="c5e4f-141">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="c5e4f-142">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="c5e4f-142">Related topics</span></span>

[<span data-ttu-id="c5e4f-143">Redefinir o PIN de audioconferência</span><span class="sxs-lookup"><span data-stu-id="c5e4f-143">Reset the Audio Conferencing PIN</span></span>](reset-the-audio-conferencing-pin.md)
