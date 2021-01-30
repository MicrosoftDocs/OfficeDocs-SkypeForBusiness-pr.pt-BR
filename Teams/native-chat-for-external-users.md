---
title: Experiência de chat nativo para usuários externos (federados) no Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
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
description: Saiba mais sobre a experiência de chat de equipes nativas para usuários de acesso externo (federado) no Microsoft Teams em que os dois usuários estão no modo de atualização do TeamsOnly.
ms.openlocfilehash: df9e1e41992e105937deacf898833995cdfb7714
ms.sourcegitcommit: 2639da2c9f903a9a82866be9db2b69a705c54200
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2021
ms.locfileid: "50055653"
---
# <a name="native-chat-experience-for-external-federated-users-in-microsoft-teams"></a><span data-ttu-id="fcf27-103">Experiência de chat nativo para usuários externos (federados) no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="fcf27-103">Native chat experience for external (federated) users in Microsoft Teams</span></span>

<span data-ttu-id="fcf27-104">Quando um usuário do Microsoft Teams está conversando com um usuário externo (federado), a experiência de chat é limitada ao texto.</span><span class="sxs-lookup"><span data-stu-id="fcf27-104">When a Microsoft Teams user is chatting with an external (federated) user, the chat experience is limited to text.</span></span> <span data-ttu-id="fcf27-105">Entretanto, se ambos os usuários do Microsoft Teams e a pessoa em outra organização estiverem no modo de atualização do TeamsOnly, você poderá ter uma "experiência de chat de equipe nativa", que inclui formatação avançada, @mentions e outros recursos de chat.</span><span class="sxs-lookup"><span data-stu-id="fcf27-105">However, if both your Teams user and the person in another organization is in the TeamsOnly upgrade mode, you can have a "native-Teams chat experience," which includes rich formatting, @mentions, and other chat features.</span></span> <span data-ttu-id="fcf27-106">Em outras palavras, você pode ter a mesma experiência de chat de equipes de 1:1 avançada com pessoas qualificadas em outras organizações como faria com usuários em sua organização.</span><span class="sxs-lookup"><span data-stu-id="fcf27-106">In other words, you can have the same rich 1:1 Teams chat experience with eligible people in other organizations as you'd have with users in your organization.</span></span> <span data-ttu-id="fcf27-107">Chats de equipes nativas com pessoas em outras organizações são limitados somente a chats do 1:1.</span><span class="sxs-lookup"><span data-stu-id="fcf27-107">Native Teams chats with people in other organizations are limited to 1:1 chats only.</span></span>

<span data-ttu-id="fcf27-108">A experiência de chat nativa para pessoas em outras organizações está ativada para todos os locatários de equipes, mas nem todas as pessoas estão qualificadas.</span><span class="sxs-lookup"><span data-stu-id="fcf27-108">The native chat experience for people in other organizations is turned on for all Teams tenants, but not all people are eligible.</span></span> <span data-ttu-id="fcf27-109">Para oferecer uma experiência de chat nativa, o remetente e o destinatário precisam estar configurados para o modo de atualização do TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="fcf27-109">To be offered a native chat experience, both the sender and receiver need to be configured for TeamsOnly upgrade mode.</span></span> <span data-ttu-id="fcf27-110">Para saber mais sobre as políticas de atualização, leia [configuração de suas configurações de coexistência e atualização](setting-your-coexistence-and-upgrade-settings.md).</span><span class="sxs-lookup"><span data-stu-id="fcf27-110">To learn more about upgrade policies, read [Setting your coexistence and upgrade settings](setting-your-coexistence-and-upgrade-settings.md).</span></span>

<span data-ttu-id="fcf27-111">Para ver uma lista de recursos para usuários de acesso externo no Teams, consulte [comparar o acesso externo e de convidado](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access).</span><span class="sxs-lookup"><span data-stu-id="fcf27-111">To see a list of capabilities for external access users in Teams, see [Compare external and guest access](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access).</span></span>

## <a name="how-do-i-know-if-im-in-a-native-chat"></a><span data-ttu-id="fcf27-112">Como posso saber se estou em um chat nativo?</span><span class="sxs-lookup"><span data-stu-id="fcf27-112">How do I know if I'm in a native chat?</span></span>

<span data-ttu-id="fcf27-113">Se você só puder trocar texto em seu chat com pessoas em outras organizações, então você está em um chat de acesso externo padrão (federado).</span><span class="sxs-lookup"><span data-stu-id="fcf27-113">If you can only exchange text in your chat with people in other organizations, then you're in a standard external-access (federated) chat.</span></span> <span data-ttu-id="fcf27-114">Se você tem todas as outras funcionalidades de chat, incluindo formatação, @mentions, emojis, etc., você está em um chat de equipes nativa.</span><span class="sxs-lookup"><span data-stu-id="fcf27-114">If you've got all of the other chat functionality, including formatting, @mentions, emojis, etc., then you're in a native Teams chat.</span></span> 

<span data-ttu-id="fcf27-115">O Teams verifica periodicamente o modo de atualização para pessoas em outras organizações e, quando encontra uma pessoa executando o Microsoft Teams no modo de atualização do TeamsOnly, ele solicitará que você alterne para um chat de equipe nativo e bloqueie o chat original.</span><span class="sxs-lookup"><span data-stu-id="fcf27-115">Teams periodically checks the upgrade mode for people in other organizations and, when it finds an them running Teams in the TeamsOnly upgrade mode, it'll prompt you to switch to a native Teams chat and lock the original chat.</span></span>

<span data-ttu-id="fcf27-116">Quando você muda para um chat nativo do Teams, o Teams não mescla as duas conversas.</span><span class="sxs-lookup"><span data-stu-id="fcf27-116">When you switch to a native Teams chat, Teams doesn't merge the two conversations.</span></span> <span data-ttu-id="fcf27-117">Em vez disso, você verá os dois chats em seu feed de chat.</span><span class="sxs-lookup"><span data-stu-id="fcf27-117">Instead, you'll see both of the chats in your chat feed.</span></span> <span data-ttu-id="fcf27-118">O novo chat de equipes nativas está ativo, mas o antigo chat somente com texto está bloqueado.</span><span class="sxs-lookup"><span data-stu-id="fcf27-118">The new, native-Teams chat is active, but the old, text-only chat is locked.</span></span>



## <a name="what-happens-if-a-user-isnt-in-teams-only-mode-anymore"></a><span data-ttu-id="fcf27-119">O que acontece se um usuário não está mais em modo Microsoft Teams?</span><span class="sxs-lookup"><span data-stu-id="fcf27-119">What happens if a user isn't in Teams Only mode anymore?</span></span>

<span data-ttu-id="fcf27-120">Se você tiver um chat de equipes nativa com pessoas em outras organizações e uma delas estiver desligada do modo de atualização do TeamsOnly, o Microsoft Teams bloqueará o chat de equipes nativas e fornecerá um link para um chat limitado e apenas texto.</span><span class="sxs-lookup"><span data-stu-id="fcf27-120">If you were having a native Teams chat with people in other organizations and then one of you gets switched out of the TeamsOnly upgrade mode, Teams locks the native Teams chat and gives you a link for a limited, text-only chat.</span></span> <span data-ttu-id="fcf27-121">Você não poderá continuar no chat das equipes nativas.</span><span class="sxs-lookup"><span data-stu-id="fcf27-121">You won't be able to continue in the native Teams chat.</span></span> <span data-ttu-id="fcf27-122">Você ainda pode ler o chat das equipes nativas, mas não pode continuar a conversa.</span><span class="sxs-lookup"><span data-stu-id="fcf27-122">You can still read the native Teams chat, but you can't continue the conversation there.</span></span>

<span data-ttu-id="fcf27-123">Se o Microsoft Teams encontrar um chat de somente texto antigo com esta pessoa, ele reutilizará esse chat.</span><span class="sxs-lookup"><span data-stu-id="fcf27-123">If Teams finds an old text-only chat with this person, it'll revive that chat.</span></span> <span data-ttu-id="fcf27-124">Caso contrário, o Teams cria um novo chat somente texto.</span><span class="sxs-lookup"><span data-stu-id="fcf27-124">Otherwise, Teams creates a new text-only chat.</span></span>


## <a name="related-topics"></a><span data-ttu-id="fcf27-125">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="fcf27-125">Related topics</span></span>

[<span data-ttu-id="fcf27-126">Gerenciar o acesso externo no Teams</span><span class="sxs-lookup"><span data-stu-id="fcf27-126">Manage external access in Teams</span></span>](manage-external-access.md)
