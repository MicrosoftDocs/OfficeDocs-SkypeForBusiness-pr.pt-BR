---
title: Experiência de chat nativa para usuários externos (federados) no Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.custom: chat-teams-channels-revamp
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-externalcollab
ms.reviewer: vinbel
search.appverid: MET150
f1.keywords:
- NOCSH
description: Saiba mais sobre a experiência de chat do Teams nativo para usuários de acesso externo (federado) no Microsoft Teams, onde ambos os usuários estão no modo de atualização do TeamsOnly.
ms.openlocfilehash: 759ad4f03de099637df0e92a7a8925a7c18ae3fd
ms.sourcegitcommit: 8f26bf0ff88f1f6881de32914be00d5f0cc7396a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/09/2023
ms.locfileid: "69740796"
---
# <a name="native-chat-experience-for-external-federated-users-in-microsoft-teams"></a>Experiência de chat nativa para usuários externos (federados) no Microsoft Teams

Quando um usuário do Microsoft Teams está conversando com um usuário externo (federado), a experiência de chat é limitada ao texto. No entanto, se o usuário do Teams e a pessoa em outra organização estiverem no modo de atualização do TeamsOnly, você poderá ter uma "experiência de chat do Native-Teams", que inclui formatação avançada, @mentions e outros recursos de chat.

A experiência de chat nativo para pessoas em outras organizações está ativada para todos os locatários do Teams, mas nem todas as pessoas são qualificadas. Para oferecer uma experiência de chat nativo, o remetente e o receptor precisam ser configurados para o modo de atualização TeamsOnly. Para saber mais sobre políticas de atualização, leia [Configurando as configurações de coexistência e atualização](setting-your-coexistence-and-upgrade-settings.md).

Para ver uma lista de recursos para usuários de acesso externo no Teams, confira [Comparar acesso externo e convidado](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access).

> [!NOTE]
> A experiência de chat nativo não está disponível para ambientes de nuvem entre Microsoft 365: Microsoft 365 WorldWide (incluindo GCC) de/para GCC High, GCC High de/para DoD ou WW de/para DoD.

## <a name="how-do-i-know-if-im-in-a-native-chat"></a>Como fazer sabe se estou em uma conversa nativa?

Se você só puder trocar texto no chat com pessoas em outras organizações, você estará em um chat padrão de acesso externo (federado). Se você tiver outras funcionalidades de chat, incluindo formatação, @mentions, emojis etc., você estará em um chat nativo do Teams. 

O Teams verifica periodicamente o modo de atualização para pessoas em outras organizações e, quando encontrar um deles executando o Teams no modo de atualização teamsOnly, ele solicitará que você alterne para um chat nativo do Teams e bloqueie o chat original.

Quando você muda para um chat nativo do Teams, o Teams não mescla as duas conversas. Em vez disso, você verá os dois chats no feed de chat. O novo chat nativo do Teams está ativo, mas o chat antigo, somente texto, está bloqueado.



## <a name="what-happens-if-a-user-isnt-in-teams-only-mode-anymore"></a>O que acontecerá se um usuário não estiver mais no modo Somente do Teams?

Se você estiver tendo um chat nativo do Teams com pessoas em outras organizações e um de vocês for desligado do modo de atualização do TeamsOnly, o Teams bloqueará o chat nativo do Teams e fornecerá um link para um chat limitado e somente texto. Você não poderá continuar no chat nativo do Teams. Você ainda pode ler o chat nativo do Teams, mas não pode continuar a conversa lá.

Se o Teams encontrar um chat antigo somente texto com essa pessoa, ele reviverá esse chat. Caso contrário, o Teams cria um novo chat somente texto.


## <a name="related-topics"></a>Tópicos relacionados

[Gerenciar o acesso externo no Teams](manage-external-access.md)
