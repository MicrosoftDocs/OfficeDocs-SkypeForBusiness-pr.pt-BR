---
title: Teams e interoperabilidade do Skype
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: vinbel
search.appverid: MET150
description: Saiba mais sobre os recursos de interoperabilidade entre usuários do teams na sua organização e usuários do Skype (cliente).
localization_priority: Normal
ms.openlocfilehash: 87e860a49f235713ed4e9cea5c818912f2a352f5
ms.sourcegitcommit: 93c5afed49f47574f1b00305e5dfbb8a89be02a7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/24/2020
ms.locfileid: "44859636"
---
# <a name="teams-and-skype-interoperability"></a>Teams e interoperabilidade do Skype

Este artigo oferece uma visão geral dos recursos de interoperabilidade entre o Microsoft Teams e o Skype (consumidor). Saiba como os usuários do Microsoft Teams e usuários do Skype podem se comunicar por meio de chats e chamadas e dos controles de administração que se aplicam.

Os usuários do teams em sua organização podem conversar com usuários do Skype e fazer chamadas para usuários do Skype usando o endereço de e-mail e vice-versa.

- Os usuários do teams podem pesquisar e iniciar uma conversa apenas com texto único ou uma chamada de áudio/vídeo com um usuário do Skype.
- Os usuários do Skype podem pesquisar e iniciar uma conversa apenas com texto único ou uma chamada de áudio/vídeo com um usuário do teams.

Isso está disponível nos clientes de área de trabalho, Web e móvel (Android e iOS) para tanto o Microsoft Teams quanto o Skype. Para obter uma experiência ideal, recomendamos o Skype versão 8,58 e posterior.

## <a name="chat-and-calling-experience"></a>Experiência de chat e chamadas

Aqui está uma visão geral da experiência de chat e chamadas.

### <a name="teams-user-starts-a-chat-or-call-with-a-skype-user"></a>O usuário do teams inicia um chat ou uma chamada com um usuário do Skype

Os usuários do teams podem pesquisar um usuário do Skype, digitando o endereço de e-mail deles em um novo chat ou na barra de pesquisa.  O usuário do teams pode, em seguida, selecionar o usuário do Skype nos resultados da pesquisa para iniciar um chat ou uma chamada.

Um usuário do Skype pode optar por não aparecer nos resultados da pesquisa. Nesse caso, eles não aparecerão nos resultados da pesquisa no Teams e os usuários do Teams não poderão encontrá-los.

### <a name="skype-user-starts-a-chat-or-call-with-a-teams-user"></a>O usuário do Skype inicia um chat ou uma chamada com um usuário do teams

Os usuários do Skype podem pesquisar e iniciar um chat com um usuário do teams usando o endereço de e-mail deles. O usuário do teams é notificado de que ele tem uma nova mensagem de um usuário do Skype e precisa primeiro aceitar a mensagem para poder respondê-la.

- Se o usuário do teams selecionar **aceitar**, a conversa é aceita, e ambos os usuários podem conversar entre si e fazer chamadas.
- Se o usuário do teams selecionar **Bloquear**, a conversa será bloqueada e as chamadas e mensagens subsequentes desse usuário do Skype serão bloqueadas.
- Se o usuário do teams selecionar **Exibir mensagens**, a mensagem será exibida no Microsoft Teams, o que ajuda o usuário a decidir se deseja aceitar ou bloquear a conversa.

> [!NOTE]
> Se você atualizou do Skype for Business para o Teams e seus usuários estão no modo somente equipes, chats e chamadas de usuários do Skype para o Teams usuários são entregues ao Teams. Se os usuários estiverem no modo de ilhas, chats e chamadas de usuários do Skype para os usuários do teams serão entregues ao Skype for Business.

### <a name="teams-user-blocks-or-unblocks-a-skype-user"></a>O usuário do teams bloqueia ou desbloqueia um usuário do Skype

Depois que um usuário do teams aceita ou bloqueia a solicitação de conversa inicial de um usuário do Skype, ele pode optar por bloquear ou desbloquear essa pessoa a qualquer momento, seja na conversa ou em suas configurações de privacidade no Microsoft Teams. Os usuários do Skype não saberão que foram bloqueados.

Os usuários bloqueados do Skype, juntamente com outras pessoas e números de telefone PSTN (rede telefônica pública comutada) que o usuário do teams bloqueou, estão listados na lista de contatos bloqueados do usuário no Microsoft Teams.

## <a name="limitations"></a>Relacionadas

- As conversas são somente texto. Isso significa que não há formatação avançada, @mentions, emojis ou outros outros recursos de chat que estão disponíveis em uma experiência de chat de [equipes nativas](native-chat-for-external-users.md).
- As conversas são apenas uma a uma. Não há suporte para chats em grupo.
- Os usuários do Microsoft Teams e os usuários do Skype não conseguem ver a presença dos outros.
- Não há suporte para a pesquisa de usuários do Skype usando sua ID Skype ou número de telefone.

## <a name="set-whether-teams-users-can-communicate-with-skype-users"></a>Definir se os usuários do teams podem se comunicar com usuários do Skype

Como administrador, você usa o centro de administração do Microsoft Teams ou o PowerShell para definir as configurações de acesso externo para controlar se os usuários de equipes em sua organização podem se comunicar com os usuários do Skype. Por padrão, essa funcionalidade está ativada para novos locatários.

Se você atualizou do Skype for Business para o Teams, as configurações de comunicações externas que você configurou no centro de administração do Skype for Business serão migradas para o Microsoft Teams.

### <a name="in-the-microsoft-teams-admin-center"></a>No Centro de administração do Microsoft Teams

No centro de administração do Microsoft Teams, vá para **configurações de toda a organização**  >  **acesso externo**e ative **os usuários podem se comunicar com usuários do Skype**. Para obter orientação passo a passo sobre como definir essa e outras configurações de acesso externo, consulte [gerenciar o acesso externo no Teams](https://docs.microsoft.com/microsoftteams/manage-external-access#allow-or-block-domains).

### <a name="using-powershell"></a>Usando o PowerShell

Use o cmdlet [set-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/set-csexternalaccesspolicy) juntos com o ```EnablePublicCloudAccess``` parâmetro para controlar se os usuários do teams podem se comunicar com os usuários do Skype. Definir o parâmetro para ```true``` permitir que os usuários do Team se comuniquem com usuários do Skype. Observe que o ```EnablePublicCloudAudioVideoAccess``` parâmetro pode ser usado para habilitar/desabilitar chamadas de áudio/vídeo.

## <a name="related-topics"></a>Tópicos relacionados

- [Gerenciar o acesso externo no Teams](manage-external-access.md)
- [Visão Geral do PowerShell do Teams](teams-powershell-overview.md)
