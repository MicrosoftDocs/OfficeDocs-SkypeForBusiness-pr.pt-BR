---
title: Redefinir um ID de conferência para um usuário no Skype Business Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
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
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Saiba as etapas para redefinir um usuário da reunião ID de conferência no Skype para Business Online e get links para ferramentas de atualização e migração da reunião. '
ms.openlocfilehash: ac37d682d45b22eff61392ee05d7c369d67c3b67
ms.sourcegitcommit: 6207b98e8395f6c640b61cfb3f6c85d96520e33b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/20/2018
ms.locfileid: "22490531"
---
# <a name="reset-a-conference-id-for-a-user-in-skype-for-business-online"></a><span data-ttu-id="f25fd-103">Redefinir um ID de conferência para um usuário no Skype Business Online</span><span class="sxs-lookup"><span data-stu-id="f25fd-103">Reset a conference ID for a user in Skype for Business Online</span></span>

> [!NOTE]
> <span data-ttu-id="f25fd-104">Para obter informações sobre como redefinir o ID de conferência no Microsoft Teams, consulte [Redefinir uma ID de conferência para um usuário em equipes da Microsoft](/MicrosoftTeams/reset-a-conference-id-for-a-user-in-teams).</span><span class="sxs-lookup"><span data-stu-id="f25fd-104">For information about resetting conference ID in Microsoft Teams, see [Reset a conference ID for a user in Microsoft Teams](/MicrosoftTeams/reset-a-conference-id-for-a-user-in-teams).</span></span>

<span data-ttu-id="f25fd-105">Uma ID de conferência dinâmico é incluída na parte inferior da reunião convites, juntamente com os números de telefone de discagem que podem ser usados por chamadores para efetuar uma chamada para uma reunião.</span><span class="sxs-lookup"><span data-stu-id="f25fd-105">A dynamic conference ID is included at the bottom of meeting invitations along with the dial-in phone numbers that can be used by callers to call in to a meeting.</span></span> <span data-ttu-id="f25fd-106">Quando o usuário disca o número de telefone, o atendedor automático para a reunião pedirá que o chamador para inserir esta ID de conferência, de forma que eles podem participar da reunião.</span><span class="sxs-lookup"><span data-stu-id="f25fd-106">When the user dials the phone number, the auto attendant for the meeting will ask the caller to enter this conference ID so they can attend the meeting.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f25fd-107">Se seu provedor de conferência for Microsoft, IDs de conferência dos usuários são definidos para somente dinâmico por padrão.</span><span class="sxs-lookup"><span data-stu-id="f25fd-107">If your conferencing provider is Microsoft, your users' conference IDs are set to Dynamic Only by default.</span></span> <span data-ttu-id="f25fd-108">Infelizmente, não há nenhuma capacidade para alterá-lo no Skype para o Centro de administração de negócios ou usando o Windows Powershell para se tornar estáticas, como agora está sem suporte.</span><span class="sxs-lookup"><span data-stu-id="f25fd-108">Unfortunately, there's no ability to change it in the Skype for Business Admin Center or using Windows Powershell to become static, as this is now unsupported.</span></span> <span data-ttu-id="f25fd-109">IDs de conferência são definidas automaticamente somente para Skype para usuários de negócios habilitados para conferência de áudio.</span><span class="sxs-lookup"><span data-stu-id="f25fd-109">Conference IDs are automatically set only for Skype for Business users enabled for Audio Conferencing.</span></span> 

## <a name="resetting-the-conference-id-for-a-user"></a><span data-ttu-id="f25fd-110">Redefinindo o ID de conferência para um usuário</span><span class="sxs-lookup"><span data-stu-id="f25fd-110">Resetting the conference ID for a user</span></span>
   
1. <span data-ttu-id="f25fd-111">No **Skype para centro de administração de negócios**, clique em **conferência de áudio** > **usuários**, selecione um usuário e clique em **Redefinir**no painel de ação em **ID da conferência** .</span><span class="sxs-lookup"><span data-stu-id="f25fd-111">In the **Skype for Business admin center**, click **Audio conferencing** > **Users**, select a user, and then in the Action pane under **Conference ID** click **Reset**.</span></span>
    
2. <span data-ttu-id="f25fd-112">No **Redefinir ID de conferência?** janela, clique em **Sim**.</span><span class="sxs-lookup"><span data-stu-id="f25fd-112">In the **Reset conference ID?** window, click **Yes**.</span></span> <span data-ttu-id="f25fd-113">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span><span class="sxs-lookup"><span data-stu-id="f25fd-113">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span> <span data-ttu-id="f25fd-114">Por padrão, os emails são enviados aos usuários, mas isso pode ser desativado.</span><span class="sxs-lookup"><span data-stu-id="f25fd-114">By default, emails are sent to users, but this can be turned off.</span></span>
    
> [!NOTE]
> <span data-ttu-id="f25fd-p104">[!OBSERVAçãO] Depois de redefinir a ID de conferência, um email com a nova ID de conferência será enviado para o usuário. Esse email será enviado para o endereço de email primário do usuário. Em muitos casos, para a caixa de correio do Office 365. O email contém a nova ID de conferência, o(s) número(s) de telefone padrão de discagem e as instruções de como usar a Ferramenta de Atualização de Reunião do Skype for Business para atualizar reuniões existentes.</span><span class="sxs-lookup"><span data-stu-id="f25fd-p104">After you reset the conference ID, an email with the new conference ID will be sent to the user. This email will be sent to the primary email address, in many cases, their Office 365 mailbox. The email contains the new conference ID, default dial-in phone number(s) and instructions to use the Skype for Business Meeting Update Tool to update existing meetings.</span></span> 
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="what-else-should-i-know"></a><span data-ttu-id="f25fd-118">O que mais devo saber?</span><span class="sxs-lookup"><span data-stu-id="f25fd-118">What else should I know?</span></span>

- <span data-ttu-id="f25fd-119">Você pode enviar todas as informações de conferência para o usuário em um email que inclua a ID de conferência e os números de telefone de discagem ao clicar em **Enviar informações de conferência via email** para o usuário no painel de ações.</span><span class="sxs-lookup"><span data-stu-id="f25fd-119">You can send all of the conferencing information to the user in an email that includes the conference ID and dial-in phone numbers by clicking **Send conference info via email** for the user in the Action pane.</span></span> <span data-ttu-id="f25fd-120">Isso não envia o PIN.</span><span class="sxs-lookup"><span data-stu-id="f25fd-120">It doesn't send the PIN.</span></span>
    
- <span data-ttu-id="f25fd-121">Uma ID de conferência conterá 7 dígitos, e você não poderá alterar seu tamanho no Skype para centro de administração de negócios ou usando o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f25fd-121">A conference ID will contain 7 digits, and you can't change its length in the Skype for Business admin center or by using Windows PowerShell.</span></span>
    
- <span data-ttu-id="f25fd-122">Depois que for redefinido, o novo ID de conferência será listado em **ID de Conferência**.</span><span class="sxs-lookup"><span data-stu-id="f25fd-122">After it has been reset, you can see the new conference ID listed under **Conference ID**.</span></span>
    
- <span data-ttu-id="f25fd-123">O ID de conferência para um usuário para conferência de áudio pode ser exibido na parte inferior do painel de ação em **conferência de áudio** quando você seleciona o usuário na página **usuários** .</span><span class="sxs-lookup"><span data-stu-id="f25fd-123">The conference ID for a user for audio conferencing can be viewed at the bottom of the Action pane under **Audio conferencing** when you select the user on the **Users** page.</span></span>
    
- <span data-ttu-id="f25fd-124">Depois que uma nova ID de conferência for criada, a ID antiga não poderá ser usada por chamadores.</span><span class="sxs-lookup"><span data-stu-id="f25fd-124">After a new conference ID is created, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="f25fd-125">Você deve notificar aos usuários para reagendarem suas reuniões existentes para garantir que a nova ID de conferência seja incluída nos convites.</span><span class="sxs-lookup"><span data-stu-id="f25fd-125">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> <span data-ttu-id="f25fd-126">Os usuários podem usar Skype para ferramenta de reunião de negócios para atualizar suas reuniões existentes.</span><span class="sxs-lookup"><span data-stu-id="f25fd-126">The users can use Skype for Business Meeting Tool to update their existing meetings.</span></span> <span data-ttu-id="f25fd-127">Para ver como baixar, instalar e executar o Skype para ferramenta de atualização de reunião de negócios, consulte:</span><span class="sxs-lookup"><span data-stu-id="f25fd-127">To see how to download, install, and run the Skype for Business Meeting Update Tool, see:</span></span>
    
  - [<span data-ttu-id="f25fd-128">Skype for Business (Lync) Meeting Update Tool</span><span class="sxs-lookup"><span data-stu-id="f25fd-128">Meeting Update Tool for Skype for Business and Lync</span></span>](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)
    
  - [<span data-ttu-id="f25fd-129">Skype for Business Online, ferramenta de migração de reuniões (64 bits)</span><span class="sxs-lookup"><span data-stu-id="f25fd-129">Skype for Business Online, Meeting Migration Tool (64-bit)</span></span>](https://go.microsoft.com/fwlink/?LinkID=626047)
    
  - [<span data-ttu-id="f25fd-130">Skype for Business Online, ferramenta de migração de reuniões (32 bits)</span><span class="sxs-lookup"><span data-stu-id="f25fd-130">Skype for Business Online, Meeting Migration Tool (32-bit)</span></span>](https://www.microsoft.com/en-us/download/details.aspx?id=54079)
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="f25fd-131">Quer saber como gerenciar com o Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="f25fd-131">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="f25fd-p107">O Windows PowerShell serve para o gerenciamento de usuários e do que os usuários podem ou não podem fazer. Com o Windows PowerShell, você pode gerenciar o Office 365 e o Skype for Business Online usando um único ponto de administração, o que pode simplificar o seu trabalho diário quando tiver várias tarefas para fazer. Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:</span><span class="sxs-lookup"><span data-stu-id="f25fd-p107">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="f25fd-135">Uma introdução ao Windows PowerShell e ao Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="f25fd-135">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="f25fd-136">Por que você precisa usar o PowerShell do Office 365</span><span class="sxs-lookup"><span data-stu-id="f25fd-136">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="f25fd-p108">O Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade em relação a usar somente o centro de administração do Office 365, como para fazer alterações de configuração para vários usuários ao mesmo tempo. Saiba mais sobre essas vantagens nos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="f25fd-p108">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="f25fd-139">Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f25fd-139">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="f25fd-140">Usar o Windows PowerShell para gerenciar o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="f25fd-140">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="f25fd-141">Usando o Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="f25fd-141">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="f25fd-142">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="f25fd-142">Related topics</span></span>

[<span data-ttu-id="f25fd-143">Redefinir o PIN de conferência de áudio</span><span class="sxs-lookup"><span data-stu-id="f25fd-143">Reset the Audio Conferencing PIN</span></span>](reset-the-audio-conferencing-pin.md)
