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
# <a name="native-chat-experience-for-external-federated-users-in-microsoft-teams"></a>Experiência de chat nativo para usuários externos (federados) no Microsoft Teams

Quando um usuário do Microsoft Teams está conversando com um usuário externo (federado), a experiência de chat é limitada ao texto. Entretanto, se ambos os usuários do Microsoft Teams e a pessoa em outra organização estiverem no modo de atualização do TeamsOnly, você poderá ter uma "experiência de chat de equipe nativa", que inclui formatação avançada, @mentions e outros recursos de chat. Em outras palavras, você pode ter a mesma experiência de chat de equipes de 1:1 avançada com pessoas qualificadas em outras organizações como faria com usuários em sua organização. Chats de equipes nativas com pessoas em outras organizações são limitados somente a chats do 1:1.

A experiência de chat nativa para pessoas em outras organizações está ativada para todos os locatários de equipes, mas nem todas as pessoas estão qualificadas. Para oferecer uma experiência de chat nativa, o remetente e o destinatário precisam estar configurados para o modo de atualização do TeamsOnly. Para saber mais sobre as políticas de atualização, leia [configuração de suas configurações de coexistência e atualização](setting-your-coexistence-and-upgrade-settings.md).

Para ver uma lista de recursos para usuários de acesso externo no Teams, consulte [comparar o acesso externo e de convidado](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access).

## <a name="how-do-i-know-if-im-in-a-native-chat"></a>Como posso saber se estou em um chat nativo?

Se você só puder trocar texto em seu chat com pessoas em outras organizações, então você está em um chat de acesso externo padrão (federado). Se você tem todas as outras funcionalidades de chat, incluindo formatação, @mentions, emojis, etc., você está em um chat de equipes nativa. 

O Teams verifica periodicamente o modo de atualização para pessoas em outras organizações e, quando encontra uma pessoa executando o Microsoft Teams no modo de atualização do TeamsOnly, ele solicitará que você alterne para um chat de equipe nativo e bloqueie o chat original.

Quando você muda para um chat nativo do Teams, o Teams não mescla as duas conversas. Em vez disso, você verá os dois chats em seu feed de chat. O novo chat de equipes nativas está ativo, mas o antigo chat somente com texto está bloqueado.



## <a name="what-happens-if-a-user-isnt-in-teams-only-mode-anymore"></a>O que acontece se um usuário não está mais em modo Microsoft Teams?

Se você tiver um chat de equipes nativa com pessoas em outras organizações e uma delas estiver desligada do modo de atualização do TeamsOnly, o Microsoft Teams bloqueará o chat de equipes nativas e fornecerá um link para um chat limitado e apenas texto. Você não poderá continuar no chat das equipes nativas. Você ainda pode ler o chat das equipes nativas, mas não pode continuar a conversa.

Se o Microsoft Teams encontrar um chat de somente texto antigo com esta pessoa, ele reutilizará esse chat. Caso contrário, o Teams cria um novo chat somente texto.


## <a name="related-topics"></a>Tópicos relacionados

[Gerenciar o acesso externo no Teams](manage-external-access.md)
