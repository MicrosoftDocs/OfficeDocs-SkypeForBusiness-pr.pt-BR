---
title: Gerenciar políticas de equipes no Microsoft Teams
author: cichur
ms.author: v-cichur
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
description: Saiba como usar e gerenciar políticas de equipes em sua organização para controlar o que os usuários podem fazer em equipes e canais.
ms.openlocfilehash: 81541c08ac963f0bcef18ba589b2341915c20d5d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094201"
---
# <a name="manage-teams-policies-in-microsoft-teams"></a>Gerenciar políticas de equipes no Microsoft Teams

Como administrador, você pode usar políticas de equipe no Microsoft Teams para controlar o que os usuários em sua organização podem fazer em equipes e canais. Por exemplo, você pode definir se os usuários têm permissão para criar canais privados.

Você gerencia políticas de equipes indo para políticas do **Teams** no centro de  >   administração do Microsoft Teams. Você pode usar a política global (padrão para toda a organização) ou criar e atribuir políticas personalizadas. Os usuários em sua organização obterão automaticamente a política global, a menos que você crie e atribua uma política personalizada.

Você pode editar a política global ou criar e atribuir uma política personalizada. Depois de editar a política global ou atribuir uma política, pode levar algumas horas para que as alterações entre em vigor.

## <a name="create-a-custom-teams-policy"></a>Criar uma política de equipe personalizada

1. Na navegação à esquerda do centro de administração do Microsoft Teams, acesse Políticas **do Teams**  >  .
2. Clique em **Adicionar**.
3. Insira um nome e uma descrição para a política.

    ![Captura de tela das configurações de política do teams](media/teams-policies.png)
4. Ativar ou desativar Criar canais <a name="createchannels"></a> **privados,** dependendo se você deseja permitir que os usuários criem canais privados.

5. Clique em **Salvar**.

## <a name="edit-a-teams-policy"></a>Editar uma política de equipe

Você pode editar a política global ou quaisquer políticas personalizadas que você criar.

1. Na navegação à esquerda do centro de administração do Microsoft Teams, acesse Políticas **do Teams**  >  .
2. Selecione a política clicando à esquerda do nome da política e, a seguir, clique em **Editar**.
3. Ativar ou desativar as configurações que você deseja e clique em **Salvar**.

## <a name="assign-a-custom-teams-policy-to-users"></a>Atribuir uma política de equipe personalizada aos usuários

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="related-topics"></a>Tópicos relacionados

[Canais privados no Teams](private-channels.md)

[Atribua políticas a seus usuários no Teams](assign-policies.md)

[New-CsTeamsChannelsPolicy](/powershell/module/skype/new-csteamschannelspolicy?view=skype-ps)