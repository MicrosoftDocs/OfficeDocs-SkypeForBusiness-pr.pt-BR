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
ms.openlocfilehash: a05aaf65418e46f7b631bac6f7d88d8bbdf4c806
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802361"
---
# <a name="manage-teams-policies-in-microsoft-teams"></a>Gerenciar políticas de equipes no Microsoft Teams

Como administrador, você pode usar as políticas do Teams no Microsoft Teams para controlar o que os usuários em sua organização podem fazer em equipes e canais. Por exemplo, você pode definir se os usuários têm permissão para criar canais privados.

Você gerencia as políticas de equipes indo para as **políticas**  >  **do Teams** no centro de administração do Microsoft Teams. Você pode usar a política global (padrão em toda a organização) ou criar e atribuir políticas personalizadas. Os usuários da sua organização terão automaticamente a política global, a menos que você crie e atribua uma política personalizada.

Você pode editar a política global ou criar e atribuir uma política personalizada. Depois de editar a política global ou atribuir uma política, pode levar algumas horas para que as alterações entrem em vigor.

## <a name="create-a-custom-teams-policy"></a>Criar uma política personalizada de equipes

1. Na navegação à esquerda do centro de administração do Microsoft Teams, acesse as políticas **do**  >  **Teams.**
2. Clique em **Adicionar**.
3. Insira um nome e uma descrição para a política.

    ![Captura de tela das configurações de política do Teams](media/teams-policies.png)
4. A turn on or turn <a name="createchannels"></a> off Create private **channels**, depending on whether you want to allow users to create private channels.

5. Clique em **Salvar**.

## <a name="edit-a-teams-policy"></a>Editar uma política de equipes

Você pode editar a política global ou quaisquer políticas personalizadas que criar.

1. Na navegação à esquerda do centro de administração do Microsoft Teams, acesse as políticas **do**  >  **Teams.**
2. Selecione a política clicando à esquerda do nome da política e clique em **Editar**.
3. A turn on or turn off the settings that you want, and then click **Save**.

## <a name="assign-a-custom-teams-policy-to-users"></a>Atribuir uma política personalizada de equipes aos usuários

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="related-topics"></a>Tópicos relacionados

[Canais privados no Teams](private-channels.md)

[Atribuir políticas aos usuários no Microsoft Teams](assign-policies.md)

[New-CsTeamsChannelsPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamschannelspolicy?view=skype-ps)
