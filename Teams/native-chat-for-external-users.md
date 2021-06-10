---
title: Experiência de chat nativa para usuários externos (federados) no Microsoft Teams
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
description: Saiba mais sobre a experiência Teams de chat nativa para usuários de acesso externo (federado) no Microsoft Teams onde ambos os usuários estão no modo de atualização do TeamsOnly.
ms.openlocfilehash: 02bf09a7623079eb207ffca1b122bc03bf07c5c8
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52240457"
---
# <a name="native-chat-experience-for-external-federated-users-in-microsoft-teams"></a><span data-ttu-id="42ac3-103">Experiência de chat nativa para usuários externos (federados) no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="42ac3-103">Native chat experience for external (federated) users in Microsoft Teams</span></span>

<span data-ttu-id="42ac3-104">Quando um Microsoft Teams usuário está conversando com um usuário externo (federado), a experiência de chat é limitada ao texto.</span><span class="sxs-lookup"><span data-stu-id="42ac3-104">When a Microsoft Teams user is chatting with an external (federated) user, the chat experience is limited to text.</span></span> <span data-ttu-id="42ac3-105">No entanto, se o usuário do Teams e a pessoa em outra organização estão no modo de atualização do TeamsOnly, você pode ter uma "experiência de chat nativa Teams", que inclui formatação rica, @mentions e outros recursos de chat.</span><span class="sxs-lookup"><span data-stu-id="42ac3-105">However, if both your Teams user and the person in another organization are in the TeamsOnly upgrade mode, you can have a "native-Teams chat experience," which includes rich formatting, @mentions, and other chat features.</span></span> <span data-ttu-id="42ac3-106">Os Teams nativos conversam com pessoas em outras organizações são limitados apenas a chats 1:1.</span><span class="sxs-lookup"><span data-stu-id="42ac3-106">Native Teams chats with people in other organizations are limited to 1:1 chats only.</span></span>

<span data-ttu-id="42ac3-107">A experiência de chat nativa para pessoas em outras organizações está Teams locatários, mas nem todas as pessoas são qualificadas.</span><span class="sxs-lookup"><span data-stu-id="42ac3-107">The native chat experience for people in other organizations is turned on for all Teams tenants, but not all people are eligible.</span></span> <span data-ttu-id="42ac3-108">Para ter uma experiência de chat nativa, o remetente e o receptor precisam ser configurados para o modo de atualização do TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="42ac3-108">To be offered a native chat experience, both the sender and receiver need to be configured for TeamsOnly upgrade mode.</span></span> <span data-ttu-id="42ac3-109">Para saber mais sobre políticas de atualização, leia [Configurando suas configurações de coexistência e atualização.](setting-your-coexistence-and-upgrade-settings.md)</span><span class="sxs-lookup"><span data-stu-id="42ac3-109">To learn more about upgrade policies, read [Setting your coexistence and upgrade settings](setting-your-coexistence-and-upgrade-settings.md).</span></span>

<span data-ttu-id="42ac3-110">Para ver uma lista de recursos para usuários de acesso externo Teams, consulte [Compare external and guest access](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access).</span><span class="sxs-lookup"><span data-stu-id="42ac3-110">To see a list of capabilities for external access users in Teams, see [Compare external and guest access](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access).</span></span>

## <a name="how-do-i-know-if-im-in-a-native-chat"></a><span data-ttu-id="42ac3-111">Como saber se estou em um chat nativo?</span><span class="sxs-lookup"><span data-stu-id="42ac3-111">How do I know if I'm in a native chat?</span></span>

<span data-ttu-id="42ac3-112">Se você só puder trocar texto em seu chat com pessoas em outras organizações, então você está em um chat padrão de acesso externo (federado).</span><span class="sxs-lookup"><span data-stu-id="42ac3-112">If you can only exchange text in your chat with people in other organizations, then you're in a standard external-access (federated) chat.</span></span> <span data-ttu-id="42ac3-113">Se você tiver outras funcionalidades de chat, incluindo formatação, @mentions, emojis, etc., então você está em um chat Teams nativo.</span><span class="sxs-lookup"><span data-stu-id="42ac3-113">If you've got other chat functionality, including formatting, @mentions, emojis, etc., then you're in a native Teams chat.</span></span> 

<span data-ttu-id="42ac3-114">Teams verifica periodicamente o modo de atualização para pessoas em outras organizações e, quando encontrar um deles executando o Teams no modo de atualização do TeamsOnly, ele solicitará que você alternar para um chat nativo Teams e bloquear o chat original.</span><span class="sxs-lookup"><span data-stu-id="42ac3-114">Teams periodically checks the upgrade mode for people in other organizations and, when it finds an them running Teams in the TeamsOnly upgrade mode, it'll prompt you to switch to a native Teams chat and lock the original chat.</span></span>

<span data-ttu-id="42ac3-115">Quando você alterna para um chat Teams nativo, Teams não mescla as duas conversas.</span><span class="sxs-lookup"><span data-stu-id="42ac3-115">When you switch to a native Teams chat, Teams doesn't merge the two conversations.</span></span> <span data-ttu-id="42ac3-116">Em vez disso, você verá ambos os chats no feed de chat.</span><span class="sxs-lookup"><span data-stu-id="42ac3-116">Instead, you'll see both of the chats in your chat feed.</span></span> <span data-ttu-id="42ac3-117">O novo chat Teams nativo está ativo, mas o chat antigo somente texto está bloqueado.</span><span class="sxs-lookup"><span data-stu-id="42ac3-117">The new, native-Teams chat is active, but the old, text-only chat is locked.</span></span>



## <a name="what-happens-if-a-user-isnt-in-teams-only-mode-anymore"></a><span data-ttu-id="42ac3-118">O que acontece se um usuário não estiver mais Teams modo Somente?</span><span class="sxs-lookup"><span data-stu-id="42ac3-118">What happens if a user isn't in Teams Only mode anymore?</span></span>

<span data-ttu-id="42ac3-119">Se você estava tendo uma conversa Teams nativa com pessoas em outras organizações e, em seguida, uma de vocês é trocada para fora do modo de atualização do TeamsOnly, o Teams bloqueia o chat nativo do Teams e fornece um link para um chat limitado somente texto.</span><span class="sxs-lookup"><span data-stu-id="42ac3-119">If you were having a native Teams chat with people in other organizations and then one of you gets switched out of the TeamsOnly upgrade mode, Teams locks the native Teams chat and gives you a link for a limited, text-only chat.</span></span> <span data-ttu-id="42ac3-120">Você não poderá continuar no chat Teams nativo.</span><span class="sxs-lookup"><span data-stu-id="42ac3-120">You won't be able to continue in the native Teams chat.</span></span> <span data-ttu-id="42ac3-121">Você ainda pode ler o chat Teams nativo, mas não pode continuar a conversa lá.</span><span class="sxs-lookup"><span data-stu-id="42ac3-121">You can still read the native Teams chat, but you can't continue the conversation there.</span></span>

<span data-ttu-id="42ac3-122">Se Teams encontrar um chat antigo somente de texto com essa pessoa, ele irá reavivar esse chat.</span><span class="sxs-lookup"><span data-stu-id="42ac3-122">If Teams finds an old text-only chat with this person, it'll revive that chat.</span></span> <span data-ttu-id="42ac3-123">Caso contrário, Teams criar um novo chat somente texto.</span><span class="sxs-lookup"><span data-stu-id="42ac3-123">Otherwise, Teams creates a new text-only chat.</span></span>


## <a name="related-topics"></a><span data-ttu-id="42ac3-124">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="42ac3-124">Related topics</span></span>

[<span data-ttu-id="42ac3-125">Gerenciar acesso externo em Teams</span><span class="sxs-lookup"><span data-stu-id="42ac3-125">Manage external access in Teams</span></span>](manage-external-access.md)
