---
title: Usar o Teams com serviços de área de trabalho remota
ms.author: mikeplum
author: MikePlumleyMSFT
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
- highpri
appliesto:
- Microsoft Teams
ms.openlocfilehash: bf113e8d14b70382d6b1704b8574385038099210
ms.sourcegitcommit: cbcf37f395832bed871fe709b87c6eecb1fdfd72
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2022
ms.locfileid: "68584312"
---
# <a name="teams-in-remote-desktop-services"></a>Teams nos Serviços de Área de Trabalho Remota

Este artigo descreve os requisitos e limitações para usar o Microsoft Teams em um ambiente de serviços de área de trabalho remota (RDS).

## <a name="what-is-rds"></a>O que é o RDS?

O RDS (Serviços de Área de Trabalho Remota) é a plataforma escolhida para criar soluções de virtualização para cada necessidade do cliente final. O RDS permite que você forneça aplicativos virtualizados individuais, forneça acesso seguro à área de trabalho remota e móvel e forneça aos usuários finais a capacidade de executar seus aplicativos e áreas de trabalho da nuvem.

O RDS oferece flexibilidade de implantação, eficiência de custo e extensibilidade. O RDS é fornecido por meio de uma variedade de opções de implantação, incluindo o Windows Server 2016 para implantações locais, o Microsoft Azure para implantações na nuvem e uma matriz robusta de soluções de parceiros.
Dependendo do ambiente e das preferências, você pode configurar a solução RDS para virtualização baseada em sessão, como uma VDI (infraestrutura de área de trabalho virtual)

Atualmente, o Teams em um ambiente de serviços de área de trabalho remota está disponível com suporte para a funcionalidade de colaboração e chat. Para garantir uma experiência de usuário ideal, siga as diretrizes neste artigo.

## <a name="teams-on-rds-with-chat-and-collaboration"></a>Teams no RDS com chat e colaboração

Se sua organização quiser usar apenas recursos de chat e colaboração no Teams, você poderá definir políticas de nível de usuário para desativar a funcionalidade de chamada e reunião no Teams.

### <a name="set-policies-to-turn-off-calling-and-meeting-functionality"></a>Definir políticas para desativar a funcionalidade de chamada e reunião

Você pode definir políticas usando o centro de administração do Microsoft Teams ou o PowerShell. Pode levar algum tempo (algumas horas) para que as alterações de política se propaguem. Se você não vir alterações para uma determinada conta imediatamente, tente novamente em algumas horas.

[**Políticas de chamada**](teams-calling-policy.md): o Teams inclui a política interna de chamada DisallowCalling, na qual todos os recursos de chamada são desativados. Atribua a política DisallowCalling a todos os usuários em sua organização que usam o Teams em um ambiente virtualizado.

[**Políticas de**](meeting-policies-overview.md) reunião: o Teams inclui a política de reunião AllOff interna, na qual todos os recursos da reunião estão desativados. Atribua a política AllOff a todos os usuários em sua organização que usam o Teams em um ambiente virtualizado.

#### <a name="assign-policies-using-the-microsoft-teams-admin-center"></a>Atribuir políticas usando o centro de administração do Microsoft Teams

Para atribuir a política de chamada DisallowCalling e a política de reunião AllOff a um usuário:

1. Na navegação à esquerda do centro de administração do Microsoft Teams, acesse **Usuários**.
2. Selecione o usuário selecionando à esquerda do nome de usuário e, em seguida, selecione **Editar configurações**.
3. Execute as seguintes etapas:

    a.  Em **Política de chamada**, selecione **DisallowCalling**.

    b.  Em **Política de reunião**, selecione **AllOff**.

4. Selecione **Aplicar**.

Para atribuir uma política a vários usuários por vez:

1. Na barra de navegação à esquerda do centro de administração do Microsoft Teams, vá para **Usuários** e, em seguida, pesquise os usuários ou filtre o modo de exibição para mostrar os usuários que você deseja.
2. Na coluna **&#x2713;** (marca de seleção), selecione os usuários. Para selecionar todos os usuários, selecione o &#x2713; (marca de seleção) na parte superior da tabela.
3. Selecione **Editar configurações**, faça as alterações desejadas e, em seguida, **selecione Aplicar**.

Ou você também pode executar as seguintes etapas:

1. No painel de navegação esquerdo do Centro de administração do Microsoft Teams, vá para a política que você deseja atribuir. Por exemplo:

    - Vá para **políticas de** > **Chamada de** Voz e selecione **DisallowCalling**.
    - Vá para **as políticas de** > **Reunião de** Reuniões e selecione **AllOff**.

2. Selecione **Gerenciar usuários**.
3. No painel **Gerenciar usuários**, procure o usuário pelo nome de exibição ou pelo nome de usuário, escolha o nome e marque **Adicionar**. Repita esta etapa para cada usuário que você deseja adicionar.
4. Quando terminar de adicionar usuários, selecione **Salvar**.

#### <a name="assign-policies-using-powershell"></a>Atribuir políticas usando o PowerShell

O exemplo a seguir mostra como usar [Grant-CsTeamsCallingPolicy](/powershell/module/skype/grant-csteamscallingpolicy) para atribuir a política de chamada DisallowCalling a um usuário.

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName DisallowCalling -Identity "user email id"
```

Para saber mais sobre como usar o PowerShell para gerenciar políticas de chamada, consulte [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy).

O exemplo a seguir mostra como usar [Grant-CsTeamsMeetingPolicy](/powershell/module/skype/grant-csteamsmeetingpolicy) para atribuir a política de reunião AllOff a um usuário.

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOff -Identity "user email id"
```

Para saber mais sobre como usar o PowerShell para gerenciar políticas de reunião, consulte [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy).