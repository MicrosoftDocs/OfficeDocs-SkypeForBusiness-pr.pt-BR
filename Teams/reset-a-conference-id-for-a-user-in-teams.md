---
title: Redefinir o ID de conferência de um usuário no Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 6e12242c-55f7-4bf4-90d7-0f36c0326b8e
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Conheça as etapas para redefinir o ID de conferência de reunião de um usuário no Microsoft Teams e obtenha links para as ferramentas de atualização e migração da reunião. '
ms.openlocfilehash: 894761811bfc9c353c7a145c83c7a201a587f1e2
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2019
ms.locfileid: "37568362"
---
# <a name="reset-a-conference-id-for-a-user-in-microsoft-teams"></a><span data-ttu-id="4d03c-103">Redefinir o ID de conferência de um usuário no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4d03c-103">Reset a conference ID for a user in Microsoft Teams</span></span>

<span data-ttu-id="4d03c-104">Esse ID de conferência dinâmico é incluído no final dos convites de reunião, juntamente com os números de telefone que podem ser discados para que os chamadores participem de uma reunião.</span><span class="sxs-lookup"><span data-stu-id="4d03c-104">A dynamic conference ID is included at the bottom of meeting invitations along with the dial-in phone numbers that can be used by callers to call in to a meeting.</span></span> <span data-ttu-id="4d03c-105">Quando o usuário discar para o número de telefone, um atendedor automático da reunião solicitará que ele insira esse ID de conferência para que possam participar da reunião.</span><span class="sxs-lookup"><span data-stu-id="4d03c-105">When the user dials the phone number, the auto attendant for the meeting will ask the caller to enter this conference ID so they can attend the meeting.</span></span>
  
> [!NOTE]
> <span data-ttu-id="4d03c-106">Se o seu provedor de conferência for da Microsoft, os IDs de conferência dos usuários serão definidos como Somente dinâmicos por padrão.</span><span class="sxs-lookup"><span data-stu-id="4d03c-106">If your conferencing provider is Microsoft, your users' conference IDs are set to Dynamic Only by default.</span></span> <span data-ttu-id="4d03c-107">Infelizmente, não é possível alterá-lo para que se torne estático, pois isso não tem mais suporte.</span><span class="sxs-lookup"><span data-stu-id="4d03c-107">Unfortunately, there's no ability to change it to become static, as this is now unsupported.</span></span> <span data-ttu-id="4d03c-108">Os IDs de conferência são definidos automaticamente somente para usuários do Microsoft Teams habilitados para a audioconferência.</span><span class="sxs-lookup"><span data-stu-id="4d03c-108">Conference IDs are only automatically set for Microsoft Teams users enabled for Audio Conferencing.</span></span> 


## <a name="resetting-the-conference-id-for-a-user"></a><span data-ttu-id="4d03c-109">Redefinir o ID de conferência de um usuário</span><span class="sxs-lookup"><span data-stu-id="4d03c-109">Resetting the conference ID for a user</span></span>

<span data-ttu-id="4d03c-110">![Um ícone mostrando o logotipo](media/teams-logo-30x30.png) do Microsoft Teams **usando o centro de administração do Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="4d03c-110">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="4d03c-111">Na navegação à esquerda, clique em **usuários**e selecione o usuário na lista de usuários disponíveis.</span><span class="sxs-lookup"><span data-stu-id="4d03c-111">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="4d03c-112">Clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="4d03c-112">Click **Edit**.</span></span>

3. <span data-ttu-id="4d03c-113">Em **videoconferências** , clique em **Redefinir ID de conferência**.</span><span class="sxs-lookup"><span data-stu-id="4d03c-113">Under **Audio Conferencing** click **Reset conference ID**.</span></span>

2. <span data-ttu-id="4d03c-114">Na janela **Redefinir ID de conferência** , clique em **Redefinir**.</span><span class="sxs-lookup"><span data-stu-id="4d03c-114">In the **Reset conference ID** window, click **Reset**.</span></span> <span data-ttu-id="4d03c-115">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span><span class="sxs-lookup"><span data-stu-id="4d03c-115">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span> <span data-ttu-id="4d03c-116">Por padrão, os emails são enviados para os usuários, mas isso pode ser desativado.</span><span class="sxs-lookup"><span data-stu-id="4d03c-116">By default, emails are sent to users, but this can be turned off.</span></span>   

    
> [!NOTE]
> <span data-ttu-id="4d03c-117">Depois de redefinir o ID de conferência, um email com a nova ID de conferência será enviado ao usuário.</span><span class="sxs-lookup"><span data-stu-id="4d03c-117">After you reset the conference ID, an email with the new conference ID will be sent to the user.</span></span> <span data-ttu-id="4d03c-118">Este e-mail será enviado ao endereço de email principal, em muitos casos, a sua caixa de correio do Office 365.</span><span class="sxs-lookup"><span data-stu-id="4d03c-118">This email will be sent to the primary email address, in many cases, their Office 365 mailbox.</span></span> <span data-ttu-id="4d03c-119">O email contém a nova ID de conferência, os números de telefone de discagem padrão e as instruções para a atualização das reuniões existentes.</span><span class="sxs-lookup"><span data-stu-id="4d03c-119">The email contains the new conference ID, default dial-in phone number(s) and instructions for updating existing meetings.</span></span> 
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="what-else-should-i-know"></a><span data-ttu-id="4d03c-120">O que mais devo saber?</span><span class="sxs-lookup"><span data-stu-id="4d03c-120">What else should I know?</span></span>

- <span data-ttu-id="4d03c-121">Você pode enviar todas as informações da conferência para o usuário em um email que inclua a ID de conferência e os números de telefone de discagem clicando em **enviar informações de conferência em um email** para o usuário na seção **conferência de áudio** .</span><span class="sxs-lookup"><span data-stu-id="4d03c-121">You can send all of the conferencing information to the user in an email that includes the conference ID and dial-in phone numbers by clicking **Send conference info in email** for the user in the **Audio Conferencing** section.</span></span> <span data-ttu-id="4d03c-122">Isso não envia o PIN.</span><span class="sxs-lookup"><span data-stu-id="4d03c-122">It doesn't send the PIN.</span></span>
    
- <span data-ttu-id="4d03c-123">Uma ID de conferência terá 7 dígitos e você não poderá alterar seu comprimento.</span><span class="sxs-lookup"><span data-stu-id="4d03c-123">A conference ID will contain 7 digits, and you can't change its length.</span></span>
    
- <span data-ttu-id="4d03c-124">Depois que for redefinido, o novo ID de conferência será listado em **ID de Conferência**.</span><span class="sxs-lookup"><span data-stu-id="4d03c-124">After it has been reset, you can see the new conference ID listed under **Conference ID**.</span></span>
    
- <span data-ttu-id="4d03c-125">[!IMPORTANTE]  Depois que um novo ID de conferência for criado, o ID antigo não poderá ser usado por chamadores.</span><span class="sxs-lookup"><span data-stu-id="4d03c-125">After a new conference ID is created, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="4d03c-126">Você deve notificar aos usuários para reagendarem suas reuniões existentes para garantir que o novo ID de conferência seja incluído nos convites.</span><span class="sxs-lookup"><span data-stu-id="4d03c-126">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> 

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="4d03c-127">Deseja saber mais sobre o Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="4d03c-127">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="4d03c-p107">O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com o Windows PowerShell, você pode gerenciar o Office 365 usando um ponto único de administração para simplificar seu trabalho diário quando houver várias tarefas a serem feitas. Para começar a usar o Windows PowerShell, consulte estes tópicos:</span><span class="sxs-lookup"><span data-stu-id="4d03c-p107">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="4d03c-131">Por que você precisa usar o PowerShell do Office 365</span><span class="sxs-lookup"><span data-stu-id="4d03c-131">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="4d03c-132">Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4d03c-132">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="4d03c-133">Para obter mais informações sobre o Windows PowerShell, consulte a [referência do Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="4d03c-133">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="4d03c-134">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="4d03c-134">Related topics</span></span>

[<span data-ttu-id="4d03c-135">Redefinir o PIN de audioconferência</span><span class="sxs-lookup"><span data-stu-id="4d03c-135">Reset the Audio Conferencing PIN</span></span>](reset-the-audio-conferencing-pin-in-teams.md)
