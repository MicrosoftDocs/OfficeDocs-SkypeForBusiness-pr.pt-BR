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
- Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Saiba como usar e gerenciar políticas de equipe em sua organização para controlar o que os usuários podem fazer em equipes e canais.
f1keywords:
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.discoverteams
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.createchannels
- ms.teamsadmincenter.teams.teamsandchannelpolicies.overview
- ms.teamsadmincenter.teamsandchannelpolicies.overview
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.discover
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.create
ms.openlocfilehash: 40647aec4f55d3d922f29c853ec84ee175dc8166
ms.sourcegitcommit: d4e69d46de564c445feb855cbee55954a7063bba
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/21/2019
ms.locfileid: "36483197"
---
# <a name="manage-teams-policies-in-microsoft-teams"></a>Gerenciar políticas do teams no Microsoft Teams

Como administrador, você pode usar políticas do teams no Microsoft Teams para controlar o que os usuários em sua organização podem fazer em equipes e canais. Por exemplo, você pode definir se os usuários podem descobrir equipes particulares nos resultados da pesquisa e na Galeria da equipe e se os usuários podem criar canais privados.

Você gerencia políticas do teams no centro de administração do Microsoft Teams. Você pode usar a política global (padrão para toda a organização) ou criar políticas personalizadas e atribuí-las aos usuários. Os usuários em sua organização receberão automaticamente a política global, a menos que você crie e atribua uma política personalizada.

Você pode editar a política global ou criar e atribuir uma política personalizada. Se for atribuída uma política personalizada a um usuário, essa política se aplicará ao usuário. Se um usuário não estiver atribuído a uma política personalizada, a política global se aplicará ao usuário. Depois de editar a política global ou atribuir uma política, pode levar até 24 horas para que as alterações entrem em vigor.

## <a name="create-a-custom-teams-policy"></a>Criar uma política personalizada do Microsoft Teams

1. Na navegação à esquerda do centro de administração do Microsoft Teams, **** > vá para**políticas**do teams Teams.
2. Clique em **Adicionar**.
3. Insira um nome e uma descrição para a política.

    ![Captura de tela das configurações de política do teams](media/teams-policies.png)
4. Escolha as configurações desejadas:

- [**Descubra equipes particulares**](https://docs.microsoft.com/MicrosoftTeams/teams-policies#discoverteams): Ative essa configuração para permitir que os usuários descubram equipes particulares nos resultados da pesquisa e na Galeria de equipe.
- [**Criar canais privados**](https://docs.microsoft.com/MicrosoftTeams/teams-policies#createchannels): Ative essa configuração para permitir que os usuários criem canais privados.

5. Clique em **Salvar**.

## <a name="edit-a-teams-policy"></a>Editar uma política de equipe

Você pode editar a política global ou qualquer política personalizada criada.

1. Na navegação à esquerda do centro de administração do Microsoft Teams, **** > vá para**políticas**do teams Teams.
2. Selecione a política clicando à esquerda do nome da política e, em seguida, clique em **Editar**.
3. Ative ou desative as configurações desejadas e clique em **salvar**.

## <a name="assign-a-custom-teams-policy-to-users"></a>Atribuir uma política personalizada do teams aos usuários

Você pode usar o centro de administração do Microsoft Teams para atribuir uma política personalizada a um ou mais usuários ou ao módulo do PowerShell do Skype for Business para atribuir uma política personalizada a grupos de usuários, como um grupo de segurança ou grupo de distribuição.

### <a name="assign-a-custom-teams-policy-to-a-user"></a>Atribuir uma política personalizada do teams a um usuário

1. Na navegação à esquerda do centro de administração do Microsoft Teams, vá para **usuários**e, em seguida, clique no usuário.
2. Clique em **políticas**e, em seguida, ao lado de **políticas atribuídas**, clique em **Editar**.
3. Em **políticas**do Teams, selecione a política que você deseja atribuir e clique em **salvar**.

Para atribuir uma política personalizada do teams a vários usuários de uma só vez, consulte [Editar configurações de usuários do teams em massa](edit-user-settings-in-bulk.md).

Ou, você também pode fazer o seguinte:

1. Na navegação à esquerda do centro de administração do Microsoft Teams, **** > vá para**políticas**do teams Teams.
2. Selecione a política clicando à esquerda do nome da política.
3. Selecione **gerenciar usuários**.
4. No painel **gerenciar usuários** , procure pelo usuário por nome para exibição ou por nome de usuário, selecione o nome e, em seguida, selecione **Adicionar**. Repita esta etapa para cada usuário que você deseja adicionar.
5. Quando tiver terminado de adicionar usuários, clique em **salvar**.

### <a name="assign-a-custom-teams-policy-to-users-in-a-group"></a>Atribuir uma política personalizada do teams a usuários em um grupo

Você pode querer atribuir uma política personalizada do teams a vários usuários que você já tenha identificado. Por exemplo, você pode querer atribuir uma política a todos os usuários de um grupo de segurança. Você pode fazer isso conectando-se ao módulo do PowerShell do Azure Active Directory e ao módulo do PowerShell do Skype for Business. Para obter mais informações sobre como usar o PowerShell para gerenciar o Microsoft Teams, consulte [visão geral do teams PowerShell](teams-powershell-overview.md).

Neste exemplo, atribuímos uma política de equipe chamada política de equipe de marketing a todos os usuários do grupo de marketing da contoso.  

> [!NOTE]
> Verifique se você se conectou primeiro ao módulo do PowerShell do Azure Active Directory e do módulo do PowerShell do Skype for Business seguindo as etapas em [conectar a todos os serviços do Office 365 em uma única janela do Windows PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).

Obtenha o GroupObjectId do grupo específico.
```
$group = Get-AzureADGroup -SearchString "Contoso Marketing"
```
Obter os membros do grupo especificado.
```
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
Atribua todos os usuários do grupo a uma política específica do teams. Neste exemplo, a política de equipe de marketing.
```
$members | ForEach-Object { Grant-CsTeamsChannelsPolicy -PolicyName "Marketing Teams Policy" -Identity $_.EmailAddress}
``` 
Dependendo do número de membros do grupo, esse comando pode levar alguns minutos para ser executado.

## <a name="related-topics"></a>Tópicos relacionados

- [Gerenciar a descoberta de equipes particulares no Teams](manage-discovery-of-private-teams.md)
