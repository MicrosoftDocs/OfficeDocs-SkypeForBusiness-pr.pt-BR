---
title: Gerenciar políticas de canal em Microsoft Teams
author: MikePlumleyMSFT
ms.author: mikeplum
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
ms.localizationpriority: medium
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
description: Saiba como usar e gerenciar políticas de canal de equipes em sua organização para controlar o que os usuários podem fazer em equipes e canais.
ms.openlocfilehash: 5acac362485b1004e1db61229c437810fdbcbc6d
ms.sourcegitcommit: fcac607fb4ad342a0936527f848e04c85f153ba5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/22/2022
ms.locfileid: "63711775"
---
# <a name="manage-channel-policies-in-microsoft-teams"></a>Gerenciar políticas de canal em Microsoft Teams

Como administrador, você pode usar políticas no Microsoft Teams para controlar o que os usuários em sua organização podem fazer em equipes e canais. Por exemplo, você pode definir se os usuários têm permissão para criar canais privados ou compartilhados.

Você gerencia políticas de equipes Teams  > **Teams no** centro de administração Microsoft Teams de gerenciamento. Você pode usar a política global (padrão para toda a organização) ou criar e atribuir políticas personalizadas. Os usuários em sua organização obterão automaticamente a política global, a menos que você crie e atribua uma política personalizada.

Você pode editar a política global ou criar e atribuir uma política personalizada. Depois de editar a política global ou atribuir uma política, pode levar 24 horas para que as alterações entre em vigor.

## <a name="channel-policies"></a>Políticas de canal

As seguintes políticas estão disponíveis para canais de equipe:

|Política|Descrição|
|:-----|:----------|
|**Criar canais privados**|Quando **on**, os proprietários e membros da equipe podem criar canais privados. (Os proprietários da equipe podem controlar se os membros podem criar canais privados em cada equipe.)|
|**Criar canais compartilhados**|Quando **on**, os proprietários da equipe podem criar canais compartilhados. Teams aplicativos que estão disponíveis para sua organização também estão disponíveis em canais compartilhados.|
|**Convidar usuários externos para canais compartilhados**|Quando **On**, proprietários e membros de canais compartilhados podem convidar participantes externos de organizações onde uma confiança entre organizações foi configurada. Teams políticas para sua organização se aplicam a esses canais.|
|**Ingressar em canais compartilhados externos**|Quando **on**, os usuários podem participar de canais compartilhados criados por outras organizações em que uma confiança entre organizações foi configurada. Teams políticas para a outra organização se aplicam a esses canais.|

## <a name="create-a-custom-teams-policy"></a>Criar uma política de equipe personalizada

1. Na navegação à esquerda do centro de administração Microsoft Teams, **acesse Teams** >  **Teams.**
2. Clique em **Adicionar**.
3. Insira um nome e uma descrição para a política.

    ![Captura de tela das configurações de política do teams.](media/teams-policies.png)
4. A opção Ativar ou desativar as configurações que você deseja e clique em **Salvar**.

5. Clique em **Salvar**.

## <a name="edit-a-teams-policy"></a>Editar uma política de equipe

Você pode editar a política global ou quaisquer políticas personalizadas que você criar.

1. Na navegação à esquerda do centro de administração Microsoft Teams, **acesse Teams** >  **Teams.**
2. Selecione a política clicando à esquerda do nome da política e, a seguir, clique em **Editar**.
3. A opção Ativar ou desativar as configurações que você deseja e clique em **Salvar**.

## <a name="assign-a-custom-teams-policy-to-users"></a>Atribuir uma política de equipe personalizada aos usuários

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="related-topics"></a>Tópicos relacionados

[Gerenciar Teams sites conectados e sites de canal](/SharePoint/teams-connected-sites)

[Canais privados no Teams](private-channels.md)

[Atribuir políticas aos usuários no Microsoft Teams](policy-assignment-overview.md)

[New-CsTeamsChannelsPolicy](/powershell/module/skype/new-csteamschannelspolicy)
