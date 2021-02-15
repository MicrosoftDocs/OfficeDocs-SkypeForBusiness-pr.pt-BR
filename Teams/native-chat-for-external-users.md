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
description: Saiba mais sobre a experiência de chat nativa do Teams para usuários de acesso externo (federado) no Microsoft Teams, onde os dois usuários estão no modo de atualização do TeamsOnly.
ms.openlocfilehash: df9e1e41992e105937deacf898833995cdfb7714
ms.sourcegitcommit: 2639da2c9f903a9a82866be9db2b69a705c54200
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2021
ms.locfileid: "50055653"
---
# <a name="native-chat-experience-for-external-federated-users-in-microsoft-teams"></a>Experiência de chat nativo para usuários externos (federados) no Microsoft Teams

Quando um usuário do Microsoft Teams está conversando com um usuário externo (federado), a experiência de chat é limitada ao texto. No entanto, se o usuário do Teams e a pessoa em outra organização estiver no modo de atualização do TeamsOnly, você poderá ter uma "experiência de chat nativa do Teams", que inclui formatação rica, @mentions e outros recursos de chat. Em outras palavras, você pode ter a mesma experiência de chat do Teams 1:1 com pessoas qualificadas em outras organizações que teria com os usuários em sua organização. Os chats nativos do Teams com pessoas em outras organizações são limitados apenas a chats 1:1.

A experiência de chat nativo para as pessoas em outras organizações está habiiada para todos os locatários do Teams, mas nem todas as pessoas estão qualificadas. Para ter uma experiência de chat nativa, o remetente e o destinatário precisam ser configurados para o modo de atualização do TeamsOnly. Para saber mais sobre políticas de atualização, leia [Configurando suas configurações de coexistência e atualização.](setting-your-coexistence-and-upgrade-settings.md)

Para ver uma lista de recursos para usuários de acesso externo no Teams, consulte [Comparar acesso externo e de convidado.](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access)

## <a name="how-do-i-know-if-im-in-a-native-chat"></a>Como saber se estou em um chat nativo?

Se você só puder trocar texto em seu chat com pessoas em outras organizações, então você está em um chat de acesso externo padrão (federado). Se você tem todas as outras funcionalidades de chat, incluindo formatação, @mentions, emojis etc., então você está em um chat nativo do Teams. 

O Teams verifica periodicamente o modo de atualização de pessoas em outras organizações e, quando encontrar uma pessoa executando o Teams no modo de atualização do TeamsOnly, ele solicitará que você mude para um chat nativo do Teams e bloqueie o chat original.

Quando você alterna para um chat nativo do Teams, o Teams não mescla as duas conversas. Em vez disso, você verá os dois chats em seu feed de chat. O novo chat nativo do Teams está ativo, mas o antigo chat somente de texto está bloqueado.



## <a name="what-happens-if-a-user-isnt-in-teams-only-mode-anymore"></a>O que acontece se um usuário não estiver mais no modo Somente equipes?

Se você estava tendo um chat nativo do Teams com pessoas em outras organizações e, em seguida, uma de vocês é trocada do modo de atualização do TeamsOnly, o Teams bloqueia o chat nativo do Teams e fornece um link para um chat limitado somente de texto. Você não poderá continuar no chat nativo do Teams. Você ainda pode ler o chat nativo do Teams, mas não pode continuar a conversa lá.

Se o Teams encontrar um chat antigo somente de texto com essa pessoa, ele irá se desesmá-lo. Caso contrário, o Teams criará um novo chat somente de texto.


## <a name="related-topics"></a>Tópicos relacionados

[Gerenciar o acesso externo no Teams](manage-external-access.md)
