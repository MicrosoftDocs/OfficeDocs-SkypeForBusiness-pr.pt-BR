---
title: Experiência de chat nativo para usuários externos (federados) no Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
ms.reviewer: vinbel
search.appverid: MET150
f1.keywords:
- NOCSH
description: Saiba mais sobre a experiência de chat de equipes nativas para usuários de acesso externo (federado) no Microsoft Teams, disponível entre usuários externos onde os dois usuários estão no modo de atualização do TeamsOnly.
ms.openlocfilehash: 0d6f7ed00482ee68233b4d93cc101e9c820a6f14
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41832681"
---
<a name="native-chat-experience-for-external-federated-users-in-microsoft-teams"></a>Experiência de chat nativo para usuários externos (federados) no Microsoft Teams
======================================

Quando um usuário do Microsoft Teams está conversando com um usuário externo (federado), a experiência de chat é limitada ao texto. No entanto, se tanto o locatário do teams quanto o do usuário externo estiverem no modo de atualização do TeamsOnly, você poderá ter uma "experiência de chat de equipe nativa", que inclui formatação rica, @mentions e outros recursos de chat. Em outras palavras, você pode ter a mesma experiência de chat do teams 1:1 com usuários externos qualificados da mesma forma que faria com os usuários da sua organização. Os chats de equipes nativas com usuários externos ainda estão limitados a chats de 1:1 (os usuários externos não podem fazer chats em grupo).

A experiência de chat nativa para usuários externos está ativada para todos os locatários de equipes, mas nem todos os usuários estão qualificados. Para ser oferecida uma experiência de chat nativa, tanto o remetente quanto o destinatário precisam estar em um locatário do teams que esteja executando o modo de atualização do TeamsOnly. Para saber mais sobre as políticas de atualização, leia [configuração de suas configurações de coexistência e atualização](setting-your-coexistence-and-upgrade-settings.md).

Para ver uma lista de recursos para usuários de acesso externo no Teams, consulte [comparar o acesso externo e de convidado](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access).

## <a name="how-do-i-know-if-im-in-a-native-chat"></a>Como posso saber se estou em um chat nativo?

Se você só puder trocar texto em seu chat com um usuário externo, então você está em um chat de acesso externo padrão (federado). Se você tem todas as outras funcionalidades de chat, incluindo formatação, @mentions, emojis, etc., você está em um chat de equipes nativa com o usuário externo. 

O Teams verifica periodicamente o modo de atualização para usuários externos e, quando encontra um usuário externo executando o Microsoft Teams no modo de atualização do TeamsOnly, ele solicitará que você alterne para um chat de equipe nativo e bloqueie o chat original.

Quando você muda para um chat nativo do Teams, o Teams não mescla as duas conversas. Em vez disso, você verá os dois chats em seu feed de chat. O novo chat de equipes nativas está ativo, mas o antigo chat somente com texto está bloqueado.



## <a name="what-happens-if-a-user-isnt-in-teams-only-mode-anymore"></a>O que acontece se um usuário não está mais em modo Microsoft Teams?

Se você tiver um chat de equipe nativa com um usuário externo e depois um for desconectado do modo de atualização do TeamsOnly, o Microsoft Teams bloqueará o chat de equipes nativas e fornecerá um link para um chat limitado e apenas texto. Você não poderá continuar no chat das equipes nativas. Você ainda pode ler o chat das equipes nativas, mas não pode continuar a conversa.

Se o Microsoft Teams encontrar um chat de somente texto antigo com esse usuário externo, ele reutilizará esse chat. Caso contrário, o Teams cria um novo chat somente texto.


## <a name="related-topics"></a>Tópicos relacionados

[Gerenciar o acesso externo no Teams](manage-external-access.md)
