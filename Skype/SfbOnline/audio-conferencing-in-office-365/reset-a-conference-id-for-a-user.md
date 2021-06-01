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
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 'Saiba as etapas para redefinir a ID da conferência de reunião do usuário no Skype for Business Online e obter links para ferramentas de atualização e migração de reunião. '
ms.openlocfilehash: 24037de3849ae54920777636e7eb745671ae2f57
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237767"
---
# <a name="reset-a-conference-id-for-a-user-in-skype-for-business-online"></a><span data-ttu-id="cebe8-103">Redefinir uma ID de conferência para um usuário no Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="cebe8-103">Reset a conference ID for a user in Skype for Business Online</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!NOTE]
> <span data-ttu-id="cebe8-104">Para obter informações sobre como redefinir a ID de conferência Microsoft Teams, consulte Redefinir uma [ID](/MicrosoftTeams/reset-a-conference-id-for-a-user-in-teams)de conferência para um usuário em Microsoft Teams .</span><span class="sxs-lookup"><span data-stu-id="cebe8-104">For information about resetting conference ID in Microsoft Teams, see [Reset a conference ID for a user in Microsoft Teams](/MicrosoftTeams/reset-a-conference-id-for-a-user-in-teams).</span></span>

<span data-ttu-id="cebe8-105">Uma ID de conferência dinâmica é incluída na parte inferior dos convites de reunião, juntamente com os números de telefone discados que podem ser usados pelos chamadores para ligar para uma reunião.</span><span class="sxs-lookup"><span data-stu-id="cebe8-105">A dynamic conference ID is included at the bottom of meeting invitations along with the dial-in phone numbers that can be used by callers to call in to a meeting.</span></span> <span data-ttu-id="cebe8-106">Quando o usuário discar o número de telefone, o atendedor automático da reunião solicitará que o chamador insira essa ID de conferência para que ele possa participar da reunião.</span><span class="sxs-lookup"><span data-stu-id="cebe8-106">When the user dials the phone number, the auto attendant for the meeting will ask the caller to enter this conference ID so they can attend the meeting.</span></span>
  
> [!NOTE]
> <span data-ttu-id="cebe8-107">Se o provedor de conferência for a Microsoft, as IDs de conferência dos usuários serão definidas como Somente Dinâmica.</span><span class="sxs-lookup"><span data-stu-id="cebe8-107">If your conferencing provider is Microsoft, your users' conference IDs are set to Dynamic Only.</span></span> <span data-ttu-id="cebe8-108">Isso não pode ser alterado.</span><span class="sxs-lookup"><span data-stu-id="cebe8-108">This cannot be changed.</span></span> <span data-ttu-id="cebe8-109">As IDs de conferência são definidas automaticamente somente para Skype for Business usuários habilitados para Audioconferência.</span><span class="sxs-lookup"><span data-stu-id="cebe8-109">Conference IDs are automatically set only for Skype for Business users enabled for Audio Conferencing.</span></span> 

## <a name="resetting-the-conference-id-for-a-user"></a><span data-ttu-id="cebe8-110">Redefinindo a ID da conferência para um usuário</span><span class="sxs-lookup"><span data-stu-id="cebe8-110">Resetting the conference ID for a user</span></span>
   
1. <span data-ttu-id="cebe8-111">No centro **Skype for Business de** administração, clique em Usuários de Audioconferência, selecione um usuário e, no painel Ação em   >   **ID** de Conferência, clique em **Redefinir**.</span><span class="sxs-lookup"><span data-stu-id="cebe8-111">In the **Skype for Business admin center**, click **Audio conferencing** > **Users**, select a user, and then in the Action pane under **Conference ID** click **Reset**.</span></span>
    
2. <span data-ttu-id="cebe8-112">Na janela **Redefinir iD** da conferência? clique em **Sim**.</span><span class="sxs-lookup"><span data-stu-id="cebe8-112">In the **Reset conference ID?** window, click **Yes**.</span></span> <span data-ttu-id="cebe8-113">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span><span class="sxs-lookup"><span data-stu-id="cebe8-113">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span> <span data-ttu-id="cebe8-114">Por padrão, os emails são enviados aos usuários, mas isso pode ser desligado.</span><span class="sxs-lookup"><span data-stu-id="cebe8-114">By default, emails are sent to users, but this can be turned off.</span></span>
    
> [!NOTE]
> <span data-ttu-id="cebe8-115">Depois de redefinir a ID da conferência, um email com a nova ID de conferência será enviado ao usuário.</span><span class="sxs-lookup"><span data-stu-id="cebe8-115">After you reset the conference ID, an email with the new conference ID will be sent to the user.</span></span> <span data-ttu-id="cebe8-116">Esse email será enviado para o endereço de email principal, em muitos casos, seus Microsoft 365 ou Office 365 caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="cebe8-116">This email will be sent to the primary email address, in many cases, their Microsoft 365 or Office 365 mailbox.</span></span> <span data-ttu-id="cebe8-117">O email contém a nova ID da conferência, os números de telefone de discagem padrão e as instruções para usar a Ferramenta de Atualização de Reunião Skype for Business para atualizar reuniões existentes.</span><span class="sxs-lookup"><span data-stu-id="cebe8-117">The email contains the new conference ID, default dial-in phone number(s) and instructions to use the Skype for Business Meeting Update Tool to update existing meetings.</span></span> 
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="what-else-should-i-know"></a><span data-ttu-id="cebe8-118">O que mais devo saber?</span><span class="sxs-lookup"><span data-stu-id="cebe8-118">What else should I know?</span></span>

- <span data-ttu-id="cebe8-119">Você pode enviar todas as informações de conferência para o usuário em um email que inclui a ID da conferência e números de telefone discados clicando em Enviar informações de conferência por **email** para o usuário no painel Ação.</span><span class="sxs-lookup"><span data-stu-id="cebe8-119">You can send all of the conferencing information to the user in an email that includes the conference ID and dial-in phone numbers by clicking **Send conference info via email** for the user in the Action pane.</span></span> <span data-ttu-id="cebe8-120">Isso não envia o PIN.</span><span class="sxs-lookup"><span data-stu-id="cebe8-120">It doesn't send the PIN.</span></span>
    
- <span data-ttu-id="cebe8-121">Uma ID de conferência conterá 7 dígitos e você não poderá alterar seu tamanho no centro de administração Skype for Business ou usando Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cebe8-121">A conference ID will contain 7 digits, and you can't change its length in the Skype for Business admin center or by using Windows PowerShell.</span></span>
    
- <span data-ttu-id="cebe8-122">Depois que for redefinido, o novo ID de conferência será listado em **ID de Conferência**.</span><span class="sxs-lookup"><span data-stu-id="cebe8-122">After it has been reset, you can see the new conference ID listed under **Conference ID**.</span></span>
    
- <span data-ttu-id="cebe8-123">A ID da conferência de um usuário para audioconferência pode ser exibida na parte inferior do painel Ação em **Audioconferência** quando você seleciona o usuário na **página Usuários.**</span><span class="sxs-lookup"><span data-stu-id="cebe8-123">The conference ID for a user for audio conferencing can be viewed at the bottom of the Action pane under **Audio conferencing** when you select the user on the **Users** page.</span></span>
    
- <span data-ttu-id="cebe8-124">[!IMPORTANTE]  Depois que um novo ID de conferência for criado, o ID antigo não poderá ser usado por chamadores.</span><span class="sxs-lookup"><span data-stu-id="cebe8-124">After a new conference ID is created, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="cebe8-125">Você deve notificar aos usuários para reagendarem suas reuniões existentes para garantir que o novo ID de conferência seja incluído nos convites.</span><span class="sxs-lookup"><span data-stu-id="cebe8-125">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> <span data-ttu-id="cebe8-126">Os usuários podem usar Skype for Business Ferramenta de Reunião para atualizar suas reuniões existentes.</span><span class="sxs-lookup"><span data-stu-id="cebe8-126">The users can use Skype for Business Meeting Tool to update their existing meetings.</span></span> <span data-ttu-id="cebe8-127">Para ver como baixar, instalar e executar a ferramenta de atualização Skype for Business reunião, consulte:</span><span class="sxs-lookup"><span data-stu-id="cebe8-127">To see how to download, install, and run the Skype for Business Meeting Update Tool, see:</span></span>
    
  - [<span data-ttu-id="cebe8-128">Skype for Business (Lync) Meeting Update Tool</span><span class="sxs-lookup"><span data-stu-id="cebe8-128">Meeting Update Tool for Skype for Business and Lync</span></span>](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)
    
  - [<span data-ttu-id="cebe8-129">Skype for Business Online, ferramenta de migração de reuniões (64 bits)</span><span class="sxs-lookup"><span data-stu-id="cebe8-129">Skype for Business Online, Meeting Migration Tool (64-bit)</span></span>](https://go.microsoft.com/fwlink/?LinkID=626047)
    
  - [<span data-ttu-id="cebe8-130">Skype for Business Online, ferramenta de migração de reuniões (32 bits)</span><span class="sxs-lookup"><span data-stu-id="cebe8-130">Skype for Business Online, Meeting Migration Tool (32-bit)</span></span>](https://www.microsoft.com/download/details.aspx?id=54079)
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="cebe8-131">Quer saber como gerenciar com o Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="cebe8-131">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="cebe8-132">O Windows PowerShell serve para o gerenciamento de usuários e do que os usuários podem ou não podem fazer.</span><span class="sxs-lookup"><span data-stu-id="cebe8-132">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="cebe8-133">Com Windows PowerShell, você pode gerenciar o Microsoft 365 ou Office 365 e Skype for Business Online usando um único ponto de administração que pode simplificar seu trabalho diário, quando você tem várias tarefas a fazer.</span><span class="sxs-lookup"><span data-stu-id="cebe8-133">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="cebe8-134">Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:</span><span class="sxs-lookup"><span data-stu-id="cebe8-134">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="cebe8-135">Uma introdução ao Windows PowerShell e ao Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="cebe8-135">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="cebe8-136">Por que você precisa usar Microsoft 365 ou Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="cebe8-136">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
 
- <span data-ttu-id="cebe8-137">Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade sobre o uso apenas do centro de administração do Microsoft 365, como quando você está fazendo alterações de configuração para muitos usuários ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="cebe8-137">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="cebe8-138">Saiba mais sobre essas vantagens nos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="cebe8-138">Learn about these advantages in the following topics:</span></span>
    
  - <span data-ttu-id="cebe8-139">[Melhores maneiras de gerenciar Microsoft 365 ou Office 365 com Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="cebe8-139">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
  - [<span data-ttu-id="cebe8-140">Usar o Windows PowerShell para gerenciar o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="cebe8-140">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="cebe8-141">Usando o Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="cebe8-141">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
## <a name="related-topics"></a><span data-ttu-id="cebe8-142">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="cebe8-142">Related topics</span></span>

[<span data-ttu-id="cebe8-143">Redefinir o PIN de audioconferência</span><span class="sxs-lookup"><span data-stu-id="cebe8-143">Reset the Audio Conferencing PIN</span></span>](reset-the-audio-conferencing-pin.md)
