---
title: Políticas de reunião e expiração da reunião no Microsoft Teams
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: nej
audience: admin
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom: ''
description: Saiba como usar as configurações de política de reunião para controlar a expiração da reunião no Microsoft Teams.
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 4e25ea1c55890a78e9e492dd2c2dd419a6ed34f2
ms.sourcegitcommit: b72bf3827e7145b9b6a95c84e88a7879c6e8c337
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2020
ms.locfileid: "46640966"
---
# <a name="meeting-policies-and-meeting-expiration-in-microsoft-teams"></a>Políticas de reunião e expiração da reunião no Microsoft Teams

[!INCLUDE [preview-feature](includes/preview-feature.md)]

## <a name="overview"></a>Visão geral

[As políticas de reunião](meeting-policies-in-teams.md) no Microsoft Teams são usadas para controlar se os usuários em sua organização podem iniciar e agendar reuniões e os recursos que estão disponíveis para os participantes da reunião em reuniões agendadas pelos usuários. Você pode usar a política global (padrão para toda a organização) ou criar e atribuir políticas personalizadas. Você gerencia políticas de reunião no centro de administração do Microsoft Teams ou usando cmdlets [Get](https://docs.microsoft.com/powershell/module/skype/get-csteamsmeetingpolicy), [New](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy), [set](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy), [Remove](https://docs.microsoft.com/powershell/module/skype/remove-csteamsmeetingpolicy), [Grant](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) -CsTeamsMeetingPolicy do PowerShell.

As configurações de política de reunião que controlam se os usuários podem iniciar e agendar reuniões também controlam a expiração de reuniões agendadas por usuários. Quando um link de ingresso na reunião e uma ID de conferência para uma reunião expirar, ninguém poderá ingressar na reunião. As seguintes configurações de política de reunião determinam se os usuários podem iniciar e agendar reuniões no Teams e nos referimos a eles neste artigo.

- [Permitir reunião agora em canais](meeting-policies-in-teams.md#allow-meet-now-in-channels): controla se um usuário pode iniciar uma reunião improvisada em um canal.
- [Permitir agendamento de reunião de canal](meeting-policies-in-teams.md#allow-channel-meeting-scheduling): controla se um usuário pode agendar uma reunião em um canal.
- [Permitir agendamento de reuniões particulares](meeting-policies-in-teams.md#allow-scheduling-private-meetings): controla se um usuário pode agendar uma reunião particular no Teams. Uma reunião é particular quando não é publicada em um canal de uma equipe.
- [Permitir o suplemento do Outlook](meeting-policies-in-teams.md#allow-the-outlook-add-in): controla se um usuário pode agendar uma reunião particular pelo Outlook. Uma reunião é particular quando não é publicada em um canal de uma equipe.
- [Permitir reunião agora em reuniões privadas](meeting-policies-in-teams.md#allow-meet-now-in-private-meetings): controla se um usuário pode iniciar uma reunião particular improvisada.

Por padrão, essas configurações estão ativadas. Quando qualquer uma dessas configurações estiver desativada, qualquer usuário atribuído a política não poderá iniciar ou agendar novas reuniões desse tipo. Ao mesmo tempo, a reunião ingressa em links e IDs de conferência de todas as reuniões existentes do tipo que o usuário iniciou anteriormente ou agendou a expirar.

Por exemplo, se um usuário for atribuído a uma política de reunião na qual essas configurações de política de reunião estão definidas como **ativado**e, em seguida, você desativar a configuração **permitir reunião agora em canais** , esse usuário não poderá mais iniciar reuniões improvisadas em canais, e o canal reunir-se agora links de junção que o usuário criou anteriormente venceu. O usuário ainda pode iniciar e agendar outros tipos de reunião e ingressar em reuniões organizadas por outras pessoas.

## <a name="what-happens-when-the-meeting-join-link-and-conference-id-expire"></a>O que acontece quando o link de ingresso na reunião e a ID de conferência vencem?

Quando o link ingressar na reunião e a ID de conferência de uma reunião expirar, ninguém poderá ingressar na reunião. Quando um usuário tenta ingressar na reunião por meio do link ou por telefone, ele recebe uma mensagem dizendo que a reunião não está mais disponível. Conversas, arquivos, quadros de comunicações, gravações, transcrições e outros conteúdos relacionados à reunião são mantidos e os usuários ainda podem acessá-los.

## <a name="what-happens-when-you-turn-on-and-turn-off-a-meeting-policy-setting"></a>O que acontece quando você ativar e desativar uma configuração de política de reunião?

### <a name="switch-a-meeting-policy-setting-from-on-to-off"></a>Alternar uma configuração de política de reunião de ativado para desativado

Quando uma configuração de política de reunião está definida como **ativada**, os usuários atribuídos à política podem iniciar ou agendar reuniões desse tipo e todos podem participar. Quando você alterna a configuração de política de reunião para **desativado**, os usuários atribuídos a política não podem iniciar ou agendar novas reuniões desse tipo, e a reunião ingressar em links e IDs de conferência de reuniões existentes que o usuário agendou anteriormente venceu.

Tenha em mente que o usuário ainda pode ingressar em reuniões organizadas por outras pessoas.

### <a name="switch-a-meeting-policy-setting-from-off-to-on"></a>Alternar uma configuração de política de reunião de desativado para ativado

Quando você alterna uma configuração de política de reunião de **desativado** para **ativado**, os usuários atribuídos à política podem iniciar ou agendar reuniões desse tipo. Se uma configuração de política de reunião estiver desativada e, em seguida, ativada novamente para um usuário, todas as reuniões agendadas anteriormente organizadas pelo usuário ficarão ativas e as pessoas poderão participar delas usando o link de ingresso na reunião ou por telefone.  

## <a name="meeting-expiration-scenarios"></a>Cenários de expiração de reunião

Aqui está um resumo de como a expiração da reunião funciona para cada uma das configurações de política de reunião discutidas neste artigo. 

|Se quiser... |Faça isto  |Comportamento da junção de reunião  |
|---------|---------|---------|
|Expirar reunião de canal de reunião agora iniciada por um usuário  |Desativar o recurso **permitir reunião agora em canais**.|Ninguém pode participar do canal reunir-se agora reuniões iniciadas pelo usuário.         |
|Expirar reuniões de canal agendadas por um usuário   |Desativar a opção **permitir agendamento de reunião de canal**.         |Ninguém pode ingressar em reuniões de canal programadas pelo usuário. Isso impede que as pessoas ingressem nos seguintes itens:<ul><li>Reuniões de canal que ocorreram no passado.</li> <li>Reuniões de canal agendadas para o futuro e ainda não ocorreram.</li><li>Instâncias futuras de reuniões de canal recorrentes.</li></ul>       |
|Expirar reuniões particulares agendadas por um usuário    |Desative o recurso **permitir agendamento de reuniões privadas** *e* desative **permitir o suplemento do Outlook**.          |Ninguém pode ingressar em reuniões privadas programadas pelo usuário. Isso impede que as pessoas ingressem nos seguintes itens: <ul><li>Reuniões particulares que ocorreram no passado.</li> <li>Reuniões particulares agendadas para o futuro e ainda não ocorreram.</li><li>Instâncias futuras de reuniões particulares recorrentes.</li></ul> Ambas **permitem o agendamento de reuniões privadas** e **permitir que o suplemento do Outlook** deva estar desligado para expirar reuniões privadas agendadas por um usuário. Se uma configuração estiver desativada e a outra estiver ativada, os links de ingresso na reunião e as IDs de conferência das reuniões existentes permanecerão ativos e não vencerão.      |
|Expirar reunião particular agora reuniões iniciadas por um usuário  |Desativar o recurso **permitir reunião agora em reuniões privadas**.          |Ninguém pode ingressar em reuniões privadas de reunião agora iniciadas pelo usuário.         |

Se quiser que as pessoas acessem as reuniões que foram agendadas anteriormente ou iniciadas por um usuário específico, você pode:

- Ative a configuração de política de reunião para esse usuário.
- Desative a configuração de política de reunião para esse usuário e tenha outro usuário que tenha a configuração de política habilitada criar uma nova reunião para substituir a reunião expirada.

> [!NOTE]
> Se a reunião foi enviada por um representante, que recebeu permissões para enviar convites de reunião em nome de outra pessoa, como um gerente, a configuração de política de reunião será aplicada à pessoa que concedeu permissão (o gerente).

## <a name="related-topics"></a>Tópicos relacionados

[Gerenciar políticas de reunião no Teams](meeting-policies-in-teams.md)

[Atribuir políticas a seus usuários no Teams](assign-policies.md)

[Visão Geral do PowerShell do Teams](teams-powershell-overview.md)