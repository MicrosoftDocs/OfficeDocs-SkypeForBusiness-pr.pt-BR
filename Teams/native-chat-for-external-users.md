---
title: Experiência de chat nativo para usuários externos (federados) no Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-externalcollab
ms.reviewer: vinbel
search.appverid: MET150
f1.keywords:
- NOCSH
description: Saiba mais sobre a experiência de chat de equipes nativas para usuários de acesso externo (federado) no Microsoft Teams, disponível entre usuários externos onde os dois usuários estão no modo de atualização do TeamsOnly.
ms.openlocfilehash: d3ff414420f8d1d68965307e9303aed4b5cf00ff
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/13/2020
ms.locfileid: "49030597"
---
<a name="native-chat-experience-for-external-federated-users-in-microsoft-teams"></a><span data-ttu-id="3cb7c-103">Experiência de chat nativo para usuários externos (federados) no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3cb7c-103">Native chat experience for external (federated) users in Microsoft Teams</span></span>
======================================

<span data-ttu-id="3cb7c-104">Quando um usuário do Microsoft Teams está conversando com um usuário externo (federado), a experiência de chat é limitada ao texto.</span><span class="sxs-lookup"><span data-stu-id="3cb7c-104">When a Microsoft Teams user is chatting with an external (federated) user, the chat experience is limited to text.</span></span> <span data-ttu-id="3cb7c-105">No entanto, se tanto o usuário do Microsoft Teams quanto o usuário externo estiverem no modo de atualização do TeamsOnly, você poderá ter uma "experiência de chat de equipe nativa", que inclui formatação rica, @mentions e outros recursos de chat.</span><span class="sxs-lookup"><span data-stu-id="3cb7c-105">However, if both your Teams user and the external user is in the TeamsOnly upgrade mode, you can have a "native-Teams chat experience," which includes rich formatting, @mentions, and other chat features.</span></span> <span data-ttu-id="3cb7c-106">Em outras palavras, você pode ter a mesma experiência de chat do teams 1:1 com usuários externos qualificados da mesma forma que faria com os usuários da sua organização.</span><span class="sxs-lookup"><span data-stu-id="3cb7c-106">In other words, you can have the same rich 1:1 Teams chat experience with eligible external users as you'd have with users in your organization.</span></span> <span data-ttu-id="3cb7c-107">Os chats de equipes nativas com usuários externos ainda estão limitados a chats de 1:1 (os usuários externos não podem fazer chats em grupo).</span><span class="sxs-lookup"><span data-stu-id="3cb7c-107">Native Teams chats with external users are still limited to 1:1 chats only (external users can't do group chats).</span></span>

<span data-ttu-id="3cb7c-108">A experiência de chat nativa para usuários externos está ativada para todos os locatários de equipes, mas nem todos os usuários estão qualificados.</span><span class="sxs-lookup"><span data-stu-id="3cb7c-108">The native chat experience for external users is turned on for all Teams tenants, but not all users are eligible.</span></span> <span data-ttu-id="3cb7c-109">Para oferecer uma experiência de chat nativa, o remetente e o destinatário precisam estar configurados para o modo de atualização do TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="3cb7c-109">To be offered a native chat experience, both the sender and receiver need to be configured for TeamsOnly upgrade mode.</span></span> <span data-ttu-id="3cb7c-110">Para saber mais sobre as políticas de atualização, leia [configuração de suas configurações de coexistência e atualização](setting-your-coexistence-and-upgrade-settings.md).</span><span class="sxs-lookup"><span data-stu-id="3cb7c-110">To learn more about upgrade policies, read [Setting your coexistence and upgrade settings](setting-your-coexistence-and-upgrade-settings.md).</span></span>

<span data-ttu-id="3cb7c-111">Para ver uma lista de recursos para usuários de acesso externo no Teams, consulte [comparar o acesso externo e de convidado](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access).</span><span class="sxs-lookup"><span data-stu-id="3cb7c-111">To see a list of capabilities for external access users in Teams, see [Compare external and guest access](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access).</span></span>

## <a name="how-do-i-know-if-im-in-a-native-chat"></a><span data-ttu-id="3cb7c-112">Como posso saber se estou em um chat nativo?</span><span class="sxs-lookup"><span data-stu-id="3cb7c-112">How do I know if I'm in a native chat?</span></span>

<span data-ttu-id="3cb7c-113">Se você só puder trocar texto em seu chat com um usuário externo, então você está em um chat de acesso externo padrão (federado).</span><span class="sxs-lookup"><span data-stu-id="3cb7c-113">If you can only exchange text in your chat with an external user, then you're in a standard external-access (federated) chat.</span></span> <span data-ttu-id="3cb7c-114">Se você tem todas as outras funcionalidades de chat, incluindo formatação, @mentions, emojis, etc., você está em um chat de equipes nativa com o usuário externo.</span><span class="sxs-lookup"><span data-stu-id="3cb7c-114">If you've got all of the other chat functionality, including formatting, @mentions, emojis, etc., then you're in a native Teams chat with your external user.</span></span> 

<span data-ttu-id="3cb7c-115">O Teams verifica periodicamente o modo de atualização para usuários externos e, quando encontra um usuário externo executando o Microsoft Teams no modo de atualização do TeamsOnly, ele solicitará que você alterne para um chat de equipe nativo e bloqueie o chat original.</span><span class="sxs-lookup"><span data-stu-id="3cb7c-115">Teams periodically checks the upgrade mode for external users and, when it finds an external user running Teams in the TeamsOnly upgrade mode, it'll prompt you to switch to a native Teams chat and lock the original chat.</span></span>

<span data-ttu-id="3cb7c-116">Quando você muda para um chat nativo do Teams, o Teams não mescla as duas conversas.</span><span class="sxs-lookup"><span data-stu-id="3cb7c-116">When you switch to a native Teams chat, Teams doesn't merge the two conversations.</span></span> <span data-ttu-id="3cb7c-117">Em vez disso, você verá os dois chats em seu feed de chat.</span><span class="sxs-lookup"><span data-stu-id="3cb7c-117">Instead, you'll see both of the chats in your chat feed.</span></span> <span data-ttu-id="3cb7c-118">O novo chat de equipes nativas está ativo, mas o antigo chat somente com texto está bloqueado.</span><span class="sxs-lookup"><span data-stu-id="3cb7c-118">The new, native-Teams chat is active, but the old, text-only chat is locked.</span></span>



## <a name="what-happens-if-a-user-isnt-in-teams-only-mode-anymore"></a><span data-ttu-id="3cb7c-119">O que acontece se um usuário não está mais em modo Microsoft Teams?</span><span class="sxs-lookup"><span data-stu-id="3cb7c-119">What happens if a user isn't in Teams Only mode anymore?</span></span>

<span data-ttu-id="3cb7c-120">Se você tiver um chat de equipe nativa com um usuário externo e depois um for desconectado do modo de atualização do TeamsOnly, o Microsoft Teams bloqueará o chat de equipes nativas e fornecerá um link para um chat limitado e apenas texto.</span><span class="sxs-lookup"><span data-stu-id="3cb7c-120">If you were having a native Teams chat with an external user and then one of you gets switched out of the TeamsOnly upgrade mode, Teams locks the native Teams chat and gives you a link for a limited, text-only chat.</span></span> <span data-ttu-id="3cb7c-121">Você não poderá continuar no chat das equipes nativas.</span><span class="sxs-lookup"><span data-stu-id="3cb7c-121">You won't be able to continue in the native Teams chat.</span></span> <span data-ttu-id="3cb7c-122">Você ainda pode ler o chat das equipes nativas, mas não pode continuar a conversa.</span><span class="sxs-lookup"><span data-stu-id="3cb7c-122">You can still read the native Teams chat, but you can't continue the conversation there.</span></span>

<span data-ttu-id="3cb7c-123">Se o Microsoft Teams encontrar um chat de somente texto antigo com esse usuário externo, ele reutilizará esse chat.</span><span class="sxs-lookup"><span data-stu-id="3cb7c-123">If Teams finds an old text-only chat with this external user, it'll revive that chat.</span></span> <span data-ttu-id="3cb7c-124">Caso contrário, o Teams cria um novo chat somente texto.</span><span class="sxs-lookup"><span data-stu-id="3cb7c-124">Otherwise, Teams creates a new text-only chat.</span></span>


## <a name="related-topics"></a><span data-ttu-id="3cb7c-125">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="3cb7c-125">Related topics</span></span>

[<span data-ttu-id="3cb7c-126">Gerenciar o acesso externo no Teams</span><span class="sxs-lookup"><span data-stu-id="3cb7c-126">Manage external access in Teams</span></span>](manage-external-access.md)
