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
ms.openlocfilehash: 3d94c55dc184d80edbc22be53f1df18c256423c5aa04b7e342b8964463db1aa7
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54350593"
---
# <a name="native-chat-experience-for-external-federated-users-in-microsoft-teams"></a>Experiência de chat nativa para usuários externos (federados) no Microsoft Teams

Quando um Microsoft Teams usuário está conversando com um usuário externo (federado), a experiência de chat é limitada ao texto. No entanto, se o usuário do Teams e a pessoa em outra organização estão no modo de atualização do TeamsOnly, você pode ter uma "experiência de chat nativa Teams", que inclui formatação rica, @mentions e outros recursos de chat. Os Teams nativos conversam com pessoas em outras organizações são limitados apenas a chats 1:1.

A experiência de chat nativa para pessoas em outras organizações está Teams locatários, mas nem todas as pessoas são qualificadas. Para ter uma experiência de chat nativa, o remetente e o receptor precisam ser configurados para o modo de atualização do TeamsOnly. Para saber mais sobre políticas de atualização, leia [Configurando suas configurações de coexistência e atualização.](setting-your-coexistence-and-upgrade-settings.md)

Para ver uma lista de recursos para usuários de acesso externo Teams, consulte [Compare external and guest access](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access).

## <a name="how-do-i-know-if-im-in-a-native-chat"></a>Como saber se estou em um chat nativo?

Se você só puder trocar texto em seu chat com pessoas em outras organizações, então você está em um chat padrão de acesso externo (federado). Se você tiver outras funcionalidades de chat, incluindo formatação, @mentions, emojis, etc., então você está em um chat Teams nativo. 

Teams verifica periodicamente o modo de atualização para pessoas em outras organizações e, quando encontrar um deles executando o Teams no modo de atualização do TeamsOnly, ele solicitará que você alternar para um chat nativo Teams e bloquear o chat original.

Quando você alterna para um chat Teams nativo, Teams não mescla as duas conversas. Em vez disso, você verá ambos os chats no feed de chat. O novo chat Teams nativo está ativo, mas o chat antigo somente texto está bloqueado.



## <a name="what-happens-if-a-user-isnt-in-teams-only-mode-anymore"></a>O que acontece se um usuário não estiver mais Teams modo Somente?

Se você estava tendo uma conversa Teams nativa com pessoas em outras organizações e, em seguida, uma de vocês é trocada para fora do modo de atualização do TeamsOnly, o Teams bloqueia o chat nativo do Teams e fornece um link para um chat limitado somente texto. Você não poderá continuar no chat Teams nativo. Você ainda pode ler o chat Teams nativo, mas não pode continuar a conversa lá.

Se Teams encontrar um chat antigo somente de texto com essa pessoa, ele irá reavivar esse chat. Caso contrário, Teams criar um novo chat somente texto.


## <a name="related-topics"></a>Tópicos relacionados

[Gerenciar acesso externo em Teams](manage-external-access.md)
