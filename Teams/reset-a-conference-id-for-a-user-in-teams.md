---
title: Redefinir o ID de conferência de um usuário no Microsoft Teams
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
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Conheça as etapas para redefinir o ID de conferência de reunião de um usuário no Microsoft Teams e obtenha links para as ferramentas de atualização e migração da reunião. '
ms.openlocfilehash: 4e338e5ad00792a48e0a6c9e0791c0c5e4b759ac
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23887848"
---
# <a name="reset-a-conference-id-for-a-user-in-microsoft-teams"></a><span data-ttu-id="f09c6-103">Redefinir o ID de conferência de um usuário no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f09c6-103">Reset a conference ID for a user</span></span>

<span data-ttu-id="f09c6-104">Esse ID de conferência dinâmico é incluído no final dos convites de reunião, juntamente com os números de telefone que podem ser discados para que os chamadores participem de uma reunião.</span><span class="sxs-lookup"><span data-stu-id="f09c6-104">This conference ID is included at the bottom of Skype for Business Online meeting invitations along with the dial-in phone numbers that can be used by callers to call into a meeting.</span></span> <span data-ttu-id="f09c6-105">Quando o usuário discar para o número de telefone, um atendedor automático da reunião solicitará que ele insira esse ID de conferência para que possam participar da reunião.</span><span class="sxs-lookup"><span data-stu-id="f09c6-105">When the user dials the phone number, the auto attendant for the meeting will ask the caller to input this conference ID so they can attend the meeting.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f09c6-106">Se o seu provedor de conferência for da Microsoft, os IDs de conferência dos usuários serão definidos como Somente dinâmicos por padrão.</span><span class="sxs-lookup"><span data-stu-id="f09c6-106">If your conferencing provider is Microsoft, your users' conference IDs are set to Dynamic Only by default.</span></span> <span data-ttu-id="f09c6-107">Infelizmente, não é possível alterá-lo para que se torne estático, pois isso não tem mais suporte.</span><span class="sxs-lookup"><span data-stu-id="f09c6-107">Unfortunately, there's no ability to change it to become static, as this is now unsupported.</span></span> <span data-ttu-id="f09c6-108">Os IDs de conferência são definidos automaticamente somente para usuários do Microsoft Teams habilitados para a audioconferência.</span><span class="sxs-lookup"><span data-stu-id="f09c6-108">Conference IDs are only automatically set for Microsoft Teams users enabled for Audio Conferencing.</span></span> 


## <a name="resetting-the-conference-id-for-a-user"></a><span data-ttu-id="f09c6-109">Redefinir o ID de conferência de um usuário</span><span class="sxs-lookup"><span data-stu-id="f09c6-109">Resetting the meeting conference ID for a user</span></span>

1. <span data-ttu-id="f09c6-110">No painel de navegação à esquerda, clique em **Usuários** e selecione o usuário na lista de usuários disponíveis.</span><span class="sxs-lookup"><span data-stu-id="f09c6-110">In the **Skype for Business admin center**, in the left navigation go to Dial-in conferencingDial-in users, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="f09c6-111">No topo da página, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="f09c6-111">At the top of the Conference Bridges page, click Bridge Settings.</span></span>

3. <span data-ttu-id="f09c6-112">Em **Audioconferência** clique em **Redefinir ID de conferência**.</span><span class="sxs-lookup"><span data-stu-id="f09c6-112">Under **Audio Conferencing** click **Reset conference ID**.</span></span>

2. <span data-ttu-id="f09c6-113">Na janela **Redefinir ID de conferência**, clique em **Redefinir**.</span><span class="sxs-lookup"><span data-stu-id="f09c6-113">In the **Reset conference ID** window, click **Reset**.</span></span> <span data-ttu-id="f09c6-114">Um ID de conferência será criado automaticamente e um e-mail será enviado ao usuário com o novo ID de conferência.</span><span class="sxs-lookup"><span data-stu-id="f09c6-114">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span> <span data-ttu-id="f09c6-115">Por padrão, os e-mails são enviados aos usuários, mas isso pode ser desativado.</span><span class="sxs-lookup"><span data-stu-id="f09c6-115">By default, emails are sent to users, but it can be turned off.</span></span>   

    
> [!NOTE]
> <span data-ttu-id="f09c6-116">Depois de redefinir o ID de conferência, um e-mail com o novo ID de conferência será enviado ao usuário.</span><span class="sxs-lookup"><span data-stu-id="f09c6-116">After you reset the conference ID, an email with the new conference ID will be sent to the user.</span></span> <span data-ttu-id="f09c6-117">Esse e-mail será enviado para o endereço de e-mail principal, em muitos casos, para a caixa de correio do Office 365.</span><span class="sxs-lookup"><span data-stu-id="f09c6-117">This email will be sent to the primary email address, in many cases, their Office 365 mailbox.</span></span> <span data-ttu-id="f09c6-118">O e-mail contém o novo ID de conferência, o(s) número(s) de telefone de discagem padrão e instruções para atualizar as reuniões existentes.</span><span class="sxs-lookup"><span data-stu-id="f09c6-118">The email contains the new conference ID, default dial-in phone number(s) and instructions for updating existing meetings.</span></span> 
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="what-else-should-i-know"></a><span data-ttu-id="f09c6-119">O que mais preciso saber?</span><span class="sxs-lookup"><span data-stu-id="f09c6-119">What else should I know?</span></span>

- <span data-ttu-id="f09c6-120">Você pode enviar todas as informações da conferência para o usuário em um único e-mail, que inclui o ID de conferência e os números de telefone de discagem, clicando em **Enviar informações de conferência por e-mail** para o usuário na seção **Audioconferência**.</span><span class="sxs-lookup"><span data-stu-id="f09c6-120">You can send all of the conferencing information to the user in an email that includes the conference ID and dial-in phone numbers by clicking the **Send conference info via email**.</span></span> <span data-ttu-id="f09c6-121">O e-mail não envia o PIN.</span><span class="sxs-lookup"><span data-stu-id="f09c6-121">It doesn't send the PIN.</span></span>
    
- <span data-ttu-id="f09c6-122">Um ID de conferência contém sete dígitos e o tamanho não pode ser alterado.</span><span class="sxs-lookup"><span data-stu-id="f09c6-122">A conference ID will contain 7 digits and you can't change it's length in either the Skype for Business admin center or using Windows PowerShell.</span></span>
    
- <span data-ttu-id="f09c6-123">Depois que for redefinido, o novo ID de conferência será listado em **ID de Conferência**.</span><span class="sxs-lookup"><span data-stu-id="f09c6-123">After it has been reset, you can see the new conference ID listed under **Conference ID**.</span></span>
    
- <span data-ttu-id="f09c6-124">Depois que um novo ID de conferência for criado, o ID antigo não poderá ser usado pelos chamadores.</span><span class="sxs-lookup"><span data-stu-id="f09c6-124">After a new conference ID is created, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="f09c6-125">Você deve notificar os usuários para que reagendem suas reuniões existentes para garantir que o novo ID de conferência seja incluído nos convites.</span><span class="sxs-lookup"><span data-stu-id="f09c6-125">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> 

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="f09c6-126">Deseja saber mais sobre o Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="f09c6-126">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="f09c6-p107">O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com o Windows PowerShell, você pode gerenciar o Office 365 usando um ponto único de administração para simplificar seu trabalho diário quando houver várias tarefas a serem feitas. Para começar a usar o Windows PowerShell, consulte estes tópicos:</span><span class="sxs-lookup"><span data-stu-id="f09c6-p107">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="f09c6-130">Por que você precisa usar o PowerShell do Office 365</span><span class="sxs-lookup"><span data-stu-id="f09c6-130">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="f09c6-131">Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f09c6-131">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="f09c6-132">Para obter mais informações sobre o Windows PowerShell, consulte a [referência do Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="f09c6-132">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="f09c6-133">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="f09c6-133">Related topics</span></span>

<span data-ttu-id="f09c6-134">[Redefinir o PIN de audioconferência](reset-the-audio-conferencing-pin-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="f09c6-134">[](reset-the-audio-conferencing-pin-in-teams.md)Reset the Audio Conferencing PIN for a user</span></span>
