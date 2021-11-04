---
title: Usar Teams com serviços de área de trabalho remota
author: serdars
ms.author: v-mahoffman
ms.reviewer: alivano
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Saiba como usar o Microsoft Teams com serviços de área de trabalho remota.
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: 063ded4b2e2963ab30126c5af967017bf4981cef
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60774361"
---
# <a name="teams-in-remote-desktop-services"></a>Teams serviços de área de trabalho remota

Este artigo descreve os requisitos e limitações para o uso Microsoft Teams em um ambiente de serviços de área de trabalho remota (RDS).

## <a name="what-is-rds"></a>O que é RDS?

O RDS (Remote Desktop Services) é a plataforma preferida para criar soluções de virtualização para cada necessidade do cliente final. O RDS permite que você forneça aplicativos virtualizados individuais, forneça acesso seguro à área de trabalho móvel e remota e forneça aos usuários finais a capacidade de executar seus aplicativos e áreas de trabalho na nuvem.

O RDS oferece flexibilidade de implantação, eficiência de custo e extensibilidade. O RDS é fornecido por meio de várias opções de implantação, incluindo Windows Server 2016 para implantações locais, Microsoft Azure para implantações na nuvem e uma matriz robusta de soluções de parceiros.
Dependendo do ambiente e das preferências, você pode configurar a solução RDS para virtualização baseada em sessão, como uma infraestrutura de área de trabalho virtual (VDI)

Atualmente, o Teams em um ambiente de serviços de área de trabalho remota está disponível com suporte para a funcionalidade de colaboração e chat. Para garantir uma experiência de usuário ideal, siga as diretrizes neste artigo.

## <a name="teams-on-rds-with-chat-and-collaboration"></a>Teams no RDS com chat e colaboração

Se sua organização quiser usar apenas recursos de chat e colaboração no Teams, você pode definir políticas no nível do usuário para desativar a funcionalidade de chamada e reunião em Teams.

### <a name="set-policies-to-turn-off-calling-and-meeting-functionality"></a>Definir políticas para desativar a funcionalidade de chamada e reunião

Você pode definir políticas usando o centro de administração Microsoft Teams ou o PowerShell. Pode levar algum tempo (algumas horas) para que as alterações de política se propaguem. Se você não vir alterações para uma determinada conta imediatamente, tente novamente em algumas horas.

[**Políticas de chamada**](teams-calling-policy.md): Teams inclui a política de chamada DisallowCalling interna, na qual todos os recursos de chamada estão desligados. Atribua a política DisallowCalling a todos os usuários da sua organização que usam Teams em um ambiente virtualizado.

[**Políticas de**](meeting-policies-overview.md)reunião : Teams inclui a política de reunião AllOff interna, na qual todos os recursos de reunião estão desligados. Atribua a política AllOff a todos os usuários da sua organização que usam Teams em um ambiente virtualizado.

#### <a name="assign-policies-using-the-microsoft-teams-admin-center"></a>Atribuir políticas usando o Microsoft Teams de administração

Para atribuir a política de chamada DisallowCalling e a política de reunião AllOff a um usuário:

1. Na navegação à esquerda do centro de administração Microsoft Teams, vá para **Usuários**.
2. Selecione o usuário selecionando à esquerda do nome de usuário e selecione **Editar configurações**.
3. Faça as seguintes etapas:

    a.  Em **Política de Chamada,** selecione **DisallowCalling**.

    b.  Em **Política de reunião,** selecione **AllOff**.

4. Selecione **Aplicar**.

Para atribuir uma política a vários usuários por vez:

1. Na barra de navegação à esquerda do centro de administração do Microsoft Teams, vá para **Usuários** e, em seguida, pesquise os usuários ou filtre o modo de exibição para mostrar os usuários que você deseja.
2. Na coluna **&#x2713;** (marca de seleção), selecione os usuários. Para selecionar todos os usuários, selecione o &#x2713; (marca de seleção) na parte superior da tabela.
3. Selecione **Editar configurações,** faça as alterações que você deseja e selecione **Aplicar**.

Ou você também pode fazer as seguintes etapas:

1. Na navegação à esquerda do centro de administração Microsoft Teams, vá para a política que você deseja atribuir. Por exemplo:

    - Vá para **Políticas de Chamada**  >  **de** Voz e selecione **DisallowCalling**.
    - Vá para **Políticas de Reunião** de  >  **Reuniões** e selecione **AllOff**.

2. Escolha **Gerenciar usuários**.
3. No painel **Gerenciar usuários**, procure o usuário pelo nome de exibição ou pelo nome de usuário, escolha o nome e marque **Adicionar**. Repita esta etapa para cada usuário que você deseja adicionar.
4. Quando terminar de adicionar usuários, selecione **Salvar**.

#### <a name="assign-policies-using-powershell"></a>Atribuir políticas usando o PowerShell

O exemplo a seguir mostra como usar [Grant-CsTeamsCallingPolicy](/powershell/module/skype/grant-csteamscallingpolicy) para atribuir a política de chamada DisallowCalling a um usuário.

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName DisallowCalling -Identity "user email id"
```

Para saber mais sobre como usar o PowerShell para gerenciar políticas de chamadas, consulte [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy).

O exemplo a seguir mostra como usar [Grant-CsTeamsMeetingPolicy](/powershell/module/skype/grant-csteamsmeetingpolicy) para atribuir a política de reunião AllOff a um usuário.

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOff -Identity "user email id"
```

Para saber mais sobre como usar o PowerShell para gerenciar políticas de reunião, consulte [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy).