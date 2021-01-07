---
title: Gerenciar políticas do teams no Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.discoverteams
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.createchannels
- ms.teamsadmincenter.teams.teamsandchannelpolicies.overview
- ms.teamsadmincenter.teamsandchannelpolicies.overview
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.discover
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.create
description: Saiba como usar e gerenciar políticas de equipe em sua organização para controlar o que os usuários podem fazer em equipes e canais.
ms.openlocfilehash: 0b4664c36f24a057a7c8237823b7eafaad8ea6ba
ms.sourcegitcommit: 44bd56f67b1ad85ef8c21bb30d5b0d47e5a80339
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/06/2021
ms.locfileid: "49772015"
---
# <a name="manage-teams-policies-in-microsoft-teams"></a>Gerenciar políticas do teams no Microsoft Teams

Como administrador, você pode usar políticas do teams no Microsoft Teams para controlar o que os usuários em sua organização podem fazer em equipes e canais. Por exemplo, você pode definir se os usuários podem criar canais privados.

Você gerencia políticas do teams acessando políticas **do teams**  >  **Team** no centro de administração do Microsoft Teams. Você pode usar a política global (padrão para toda a organização) ou criar e atribuir políticas personalizadas. Os usuários da sua organização terão automaticamente a política global, a menos que você crie e atribua uma política personalizada.

Você pode editar a política global ou criar e atribuir uma política personalizada. Depois de editar a política global ou atribuir uma política, pode demorar algumas horas para que as alterações entrem em vigor.

## <a name="create-a-custom-teams-policy"></a>Criar uma política personalizada do Microsoft Teams

1. Na navegação à esquerda do centro de administração do Microsoft Teams, **vá para políticas do teams**  >  **Teams**.
2. Clique em **Adicionar**.
3. Insira um nome e uma descrição para a política.

    ![Captura de tela das configurações de política de equipes](media/teams-policies.png)
4. Ative ou desative **criar canais privados**, <a name="createchannels"></a> dependendo se você deseja permitir que os usuários criem canais privados.

5. Clique em **Salvar**.

## <a name="edit-a-teams-policy"></a>Editar uma política de equipe

Você pode editar a política global ou qualquer política personalizada criada.

1. Na navegação à esquerda do centro de administração do Microsoft Teams, **vá para políticas do teams**  >  **Teams**.
2. Selecione a política clicando à esquerda do nome da política e, em seguida, clique em **Editar**.
3. Ative ou desative as configurações desejadas e clique em **salvar**.

## <a name="assign-a-custom-teams-policy-to-users"></a>Atribuir uma política personalizada do teams aos usuários

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="related-topics"></a>Tópicos relacionados

[Canais privados no Teams](private-channels.md)

[Atribuir políticas aos usuários no Microsoft Teams](assign-policies.md)

[New-CsTeamsChannelsPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamschannelspolicy?view=skype-ps)
