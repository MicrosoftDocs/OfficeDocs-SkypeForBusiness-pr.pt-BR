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
- Teams_ITAdmin_Help
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
ms.openlocfilehash: 8cc418b050b254930a74db8b0894dc14ccc090e5
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/25/2018
ms.locfileid: "25014127"
---
# <a name="reset-a-conference-id-for-a-user-in-microsoft-teams"></a><span data-ttu-id="5b9a6-103">Redefinir o ID de conferência de um usuário no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5b9a6-103">Reset a conference ID for a user in Microsoft Teams</span></span>

<span data-ttu-id="5b9a6-104">Uma ID de conferência dinâmico é incluída na parte inferior da reunião convites, juntamente com os números de telefone de discagem que podem ser usados por chamadores para efetuar uma chamada para uma reunião.</span><span class="sxs-lookup"><span data-stu-id="5b9a6-104">A dynamic conference ID is included at the bottom of meeting invitations along with the dial-in phone numbers that can be used by callers to call in to a meeting.</span></span> <span data-ttu-id="5b9a6-105">Quando o usuário disca o número de telefone, o atendedor automático para a reunião pedirá que o chamador para inserir esta ID de conferência, de forma que eles podem participar da reunião.</span><span class="sxs-lookup"><span data-stu-id="5b9a6-105">When the user dials the phone number, the auto attendant for the meeting will ask the caller to enter this conference ID so they can attend the meeting.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5b9a6-106">Se seu provedor de conferência for Microsoft, IDs de conferência dos usuários são definidos para somente dinâmico por padrão.</span><span class="sxs-lookup"><span data-stu-id="5b9a6-106">If your conferencing provider is Microsoft, your users' conference IDs are set to Dynamic Only by default.</span></span> <span data-ttu-id="5b9a6-107">Infelizmente, não há nenhuma capacidade para alterá-lo a se tornar estáticas, como agora está sem suporte.</span><span class="sxs-lookup"><span data-stu-id="5b9a6-107">Unfortunately, there's no ability to change it to become static, as this is now unsupported.</span></span> <span data-ttu-id="5b9a6-108">IDs de conferência são definidas automaticamente apenas para usuários de Microsoft Teams habilitados para conferência de áudio.</span><span class="sxs-lookup"><span data-stu-id="5b9a6-108">Conference IDs are only automatically set for Microsoft Teams users enabled for Audio Conferencing.</span></span> 


## <a name="resetting-the-conference-id-for-a-user"></a><span data-ttu-id="5b9a6-109">Redefinir o ID de conferência de um usuário</span><span class="sxs-lookup"><span data-stu-id="5b9a6-109">Resetting the conference ID for a user</span></span>

1. <span data-ttu-id="5b9a6-110">No painel de navegação à esquerda, clique em **Usuários** e selecione o usuário na lista de usuários disponíveis.</span><span class="sxs-lookup"><span data-stu-id="5b9a6-110">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="5b9a6-111">No topo da página, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="5b9a6-111">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="5b9a6-112">Em **Audioconferência** clique em **Redefinir ID de conferência**.</span><span class="sxs-lookup"><span data-stu-id="5b9a6-112">Under **Audio Conferencing** click **Reset conference ID**.</span></span>

2. <span data-ttu-id="5b9a6-113">Na janela **Redefinir ID de conferência** , clique em **Redefinir**.</span><span class="sxs-lookup"><span data-stu-id="5b9a6-113">In the **Reset conference ID** window, click **Reset**.</span></span> <span data-ttu-id="5b9a6-114">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span><span class="sxs-lookup"><span data-stu-id="5b9a6-114">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span> <span data-ttu-id="5b9a6-115">Por padrão, os emails são enviados aos usuários, mas isso pode ser desativado.</span><span class="sxs-lookup"><span data-stu-id="5b9a6-115">By default, emails are sent to users, but this can be turned off.</span></span>   

    
> [!NOTE]
> <span data-ttu-id="5b9a6-116">Após você redefinir o ID de conferência, um email com a nova ID de conferência será enviado ao usuário.</span><span class="sxs-lookup"><span data-stu-id="5b9a6-116">After you reset the conference ID, an email with the new conference ID will be sent to the user.</span></span> <span data-ttu-id="5b9a6-117">Este email será enviado para o endereço de email primário, em muitos casos, suas caixas de correio do Office 365.</span><span class="sxs-lookup"><span data-stu-id="5b9a6-117">This email will be sent to the primary email address, in many cases, their Office 365 mailbox.</span></span> <span data-ttu-id="5b9a6-118">O email contém a nova ID de conferência, números de telefone de discagem padrão e instruções para atualizar as reuniões existentes.</span><span class="sxs-lookup"><span data-stu-id="5b9a6-118">The email contains the new conference ID, default dial-in phone number(s) and instructions for updating existing meetings.</span></span> 
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="what-else-should-i-know"></a><span data-ttu-id="5b9a6-119">O que mais preciso saber?</span><span class="sxs-lookup"><span data-stu-id="5b9a6-119">What else should I know?</span></span>

- <span data-ttu-id="5b9a6-120">Você pode enviar todas as informações de conferência para o usuário em um email que inclua a ID de conferência e os números de telefone de discagem ao clicar em **Enviar informações de conferência no email** para o usuário na seção de **Conferência de áudio** .</span><span class="sxs-lookup"><span data-stu-id="5b9a6-120">You can send all of the conferencing information to the user in an email that includes the conference ID and dial-in phone numbers by clicking **Send conference info in email** for the user in the **Audio Conferencing** section.</span></span> <span data-ttu-id="5b9a6-121">Isso não envia o PIN.</span><span class="sxs-lookup"><span data-stu-id="5b9a6-121">It doesn't send the PIN.</span></span>
    
- <span data-ttu-id="5b9a6-122">Um ID de conferência contém sete dígitos e o tamanho não pode ser alterado.</span><span class="sxs-lookup"><span data-stu-id="5b9a6-122">A conference ID will contain 7 digits, and you can't change its length.</span></span>
    
- <span data-ttu-id="5b9a6-123">Depois que for redefinido, o novo ID de conferência será listado em **ID de Conferência**.</span><span class="sxs-lookup"><span data-stu-id="5b9a6-123">After it has been reset, you can see the new conference ID listed under **Conference ID**.</span></span>
    
- <span data-ttu-id="5b9a6-124">[!IMPORTANTE] Depois que um novo ID de conferência for criado, o ID antigo não poderá ser usado por chamadores.</span><span class="sxs-lookup"><span data-stu-id="5b9a6-124">After a new conference ID is created, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="5b9a6-125">Você deve notificar aos usuários para reagendarem suas reuniões existentes para garantir que a nova ID de conferência seja incluída nos convites.</span><span class="sxs-lookup"><span data-stu-id="5b9a6-125">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> 

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="5b9a6-126">Deseja saber mais sobre o Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="5b9a6-126">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="5b9a6-p107">O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com o Windows PowerShell, você pode gerenciar o Office 365 usando um ponto único de administração para simplificar seu trabalho diário quando houver várias tarefas a serem feitas. Para começar a usar o Windows PowerShell, consulte estes tópicos:</span><span class="sxs-lookup"><span data-stu-id="5b9a6-p107">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="5b9a6-130">Por que você precisa usar o PowerShell do Office 365</span><span class="sxs-lookup"><span data-stu-id="5b9a6-130">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="5b9a6-131">Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="5b9a6-131">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="5b9a6-132">Para obter mais informações sobre o Windows PowerShell, consulte a [referência do Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="5b9a6-132">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="5b9a6-133">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="5b9a6-133">Related topics</span></span>

[<span data-ttu-id="5b9a6-134">Redefinir o PIN de audioconferência</span><span class="sxs-lookup"><span data-stu-id="5b9a6-134">Reset the Audio Conferencing PIN</span></span>](reset-the-audio-conferencing-pin-in-teams.md)
