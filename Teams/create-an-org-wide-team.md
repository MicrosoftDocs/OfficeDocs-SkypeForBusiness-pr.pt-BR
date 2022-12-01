---
title: Usar equipes de toda a organização no Microsoft Teams para ajudar todos a colaborar
ms.author: mikeplum
author: MikePlumleyMSFT
ms.reviewer: phlouie
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Saiba como criar e gerenciar uma equipe em toda a organização no Teams para fornecer uma maneira de todos em uma organização de pequeno a médio porte colaborarem.
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- EngageScoreOct2022
- ContentEnagagementFY23
appliesto:
- Microsoft Teams
ms.custom:
- seo-marvel-apr2020
- chat-teams-channels-revamp
ms.openlocfilehash: 5acc918c4fbe3994a93020e7b4b09db4ab1671f3
ms.sourcegitcommit: dc5b3870fd338f7e9ab0a602a44eaf9feb595b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/30/2022
ms.locfileid: "69198913"
---
# <a name="use-organization-wide-teams-in-microsoft-teams-to-help-everyone-collaborate"></a>Usar equipes de toda a organização no Microsoft Teams para ajudar todos a colaborar

Os administradores globais podem criar equipes em toda a organização que fornecem uma maneira para que todos em uma organização de pequeno a médio porte façam parte de uma equipe única e colaborativa. As equipes de toda a organização incluem automaticamente todos os usuários da organização e mantêm a associação atualizada à medida que os usuários se juntam e saem da organização.

Se sua organização for nova no Teams e não tiver mais de 5.000 usuários, uma equipe em toda a organização será criada automaticamente. As equipes em toda a organização estão limitadas a organizações com não mais de 10.000 usuários. Você pode ter até cinco equipes em toda a organização. 

## <a name="create-an-organization-wide-team"></a>Criar uma equipe em toda a organização

Há duas maneiras de criar uma equipe em toda a organização:

- Converta uma equipe existente em uma equipe de toda a organização. Acesse o nome da equipe e clique em **Mais opções** > **Editar equipe**.

- [Crie uma nova equipe do zero](https://support.microsoft.com/office/174adf5f-846b-4780-b765-de1a0a737e2b) e escolha a opção **Em toda a organização** .

    ![Captura de tela da opção em toda a organização para criar uma equipe em toda a organização.](media/create-org-wide-team.png "Captura de tela da opção em toda a organização para criar uma equipe em toda a organização")

## <a name="types-of-users-in-an-organization-wide-team"></a>Tipos de usuários em uma equipe de toda a organização

Quando uma equipe em toda a organização é criada, todos os administradores globais e administradores do Teams são adicionados como proprietários de equipe e todos os usuários ativos são adicionados como membros da equipe. Os membros da equipe não podem deixar uma equipe em toda a organização, mas os proprietários da equipe podem adicionar ou remover usuários manualmente, se necessário. Quando o Teams adiciona ou remove alguém automaticamente, uma notificação é enviada para o canal Geral.

Os usuários não licenciados também são adicionados à equipe. Na primeira vez que um usuário não licenciado entra no Teams, ele recebe uma licença exploratória Microsoft Teams. Para saber mais sobre a licença Exploratory, confira [gerenciar a licença do Microsoft Teams Exploratory](teams-exploratory.md).

Os seguintes tipos de contas não serão adicionados à sua equipe em toda a organização:

- Contas bloqueadas da entrada
- Convidados
- Contas de recurso ou serviço (por exemplo, contas associadas a atendentes automáticos e filas de chamadas)
- Contas de sala ou equipamento
- Contas com caixa de correio compartilhada

> [!NOTE]
> Salas que não fazem parte de uma lista de salas, equipamentos e contas de recursos podem ser adicionadas ou sincronizadas com a equipe de toda a organização. Os proprietários da equipe podem remover facilmente essas contas da equipe.

## <a name="options-to-get-the-most-out-of-an-organization-wide-team"></a>Opções para aproveitar ao máximo uma equipe de toda a organização

Para aproveitar ao máximo sua equipe em toda a organização, recomendamos que os proprietários da equipe façam as seguintes tarefas:

### <a name="allow-only-team-owners-to-post-to-the-general-channel"></a>Permitir que somente proprietários de equipe publiquem no canal Geral

Reduza o ruído do canal fazendo com que somente os proprietários da equipe publiquem no canal Geral.

1. Vá para a equipe, localize o canal Geral e selecione **... Mais opções** > **Gerenciar canal**.
2. Na guia **Configurações do Canal** , clique em **Permissões** e selecione **Somente proprietários podem postar mensagens**.

### <a name="turn-off-team-and-team-name-mentions"></a>Desativar as menções à @equipe e @[nome da equipe]

Reduza as @menções para evitar que elas sobrecarreguem toda a organização.

1. Vá para a equipe e clique **em ... Mais opções** \> **Gerenciar Equipe**.
2. Na guia Configurações, clique **em @mentions** \> **desative** **Mostrar aos membros a opção de @team ou @[nome da equipe]**.

### <a name="automatically-show-important-channels"></a>Mostrar canais importantes automaticamente

Mostre canais importantes para garantir que todos em sua organização se envolvam em conversas específicas. Para saber mais, confira [Adicionar canais aos Favoritos automaticamente para toda a equipe](https://support.office.com/article/auto-favorite-channels-for-the-whole-team-a948272c-5aa5-429c-863c-4e1e1cd6b0f6).

### <a name="set-up-channel-moderation"></a>Configurar a moderação de canal

Considere configurar a moderação de canal e conceder recursos de moderador a determinados membros da equipe. (Quando a moderação é configurada, os proprietários da equipe recebem recursos de moderador automaticamente.) Os moderadores podem:

- Controlar quem pode iniciar uma nova postagem em um canal
- Adicionar e remover moderadores
- Controlar se os membros da equipe podem responder às mensagens de canal existentes
- Controle se bots e conectores podem enviar mensagens de canal.

Para mais informações, consulte [Configurar e gerenciar a moderação de canal no Microsoft Teams](manage-channel-moderation-in-teams.md).

### <a name="remove-accounts-that-might-not-belong"></a>Remover contas que possam não pertencer

Mesmo que os membros não possam deixar uma equipe em toda a organização, como proprietário de uma equipe, você pode gerenciar a lista de equipe removendo contas que não pertencem. **Certifique-se de usar o Teams para remover usuários da sua equipe de toda a organização.** Se você usar outra maneira de remover um usuário, como o Centro de administração do Microsoft 365 ou de um grupo no Outlook, o usuário poderá ser adicionado de volta à equipe de toda a organização.

## <a name="related-topics"></a>Tópicos relacionados

Assista a um vídeo sobre [como criar uma equipe em toda a organização no Microsoft Teams](https://www.youtube.com/watch?v=x3qGlwwCz_w).
