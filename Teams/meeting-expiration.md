---
title: Políticas de reunião e expiração de reunião no Microsoft Teams
author: cichur
ms.author: v-cichur
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
ms.openlocfilehash: 6e8821781eab70696c9b24c8df18cc8dd0b46870
ms.sourcegitcommit: 2d725b9925696e61e3e7338f890f086e009c28f2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/06/2021
ms.locfileid: "51598610"
---
# <a name="meeting-policies-and-meeting-expiration-in-microsoft-teams"></a>Políticas de reunião e expiração de reunião no Microsoft Teams

[!INCLUDE [preview-feature](includes/preview-feature.md)]

## <a name="overview"></a>Visão Geral

[As políticas de](meeting-policies-in-teams.md) reunião no Microsoft Teams são usadas para controlar se os usuários em sua organização podem iniciar e agendar reuniões e os recursos disponíveis para os participantes da reunião para reuniões agendadas pelos usuários. Você pode usar a política global (padrão para toda a organização) ou criar e atribuir políticas personalizadas. Você gerencia as políticas de reunião no centro de administração do Microsoft Teams ou usando os cmdlets [Get](/powershell/module/skype/get-csteamsmeetingpolicy), [New](/powershell/module/skype/new-csteamsmeetingpolicy), [Set,](/powershell/module/skype/set-csteamsmeetingpolicy) [Remove](/powershell/module/skype/remove-csteamsmeetingpolicy), [Grant](/powershell/module/skype/grant-csteamsmeetingpolicy) -CsTeamsMeetingPolicy PowerShell.

As configurações de política de reunião que controlam se os usuários podem iniciar e agendar reuniões também controlam a expiração das reuniões agendadas pelos usuários. Quando um link de junção de reunião e a ID de conferência de uma reunião expiram, ninguém pode participar da reunião. As configurações de política de reunião a seguir determinam se os usuários podem iniciar e agendar reuniões no Teams e nos referimos a eles ao longo deste artigo.

- [Permitir Reunir agora em canais](meeting-policies-in-teams-general.md#allow-meet-now-in-channels): controla se um usuário pode iniciar uma reunião improvisada em um canal.
- [Permitir agendamento de reunião de canal](meeting-policies-in-teams-general.md#allow-channel-meeting-scheduling): controla se um usuário pode agendar uma reunião em um canal.
- [Permitir o agendamento de reuniões privadas](meeting-policies-in-teams-general.md#allow-scheduling-private-meetings): controla se um usuário pode agendar uma reunião privada no Teams. Uma reunião é particular quando não é publicada em um canal de uma equipe.
- [Permitir que o Outlook adicione :](meeting-policies-in-teams-general.md#allow-the-outlook-add-in)controla se um usuário pode agendar uma reunião privada do Outlook. Uma reunião é particular quando não é publicada em um canal de uma equipe.
- [Permitir Reunião agora em reuniões privadas](meeting-policies-in-teams-general.md#allow-meet-now-in-private-meetings): controla se um usuário pode iniciar uma reunião privada improvisada.

Por padrão, essas configurações estão em. Quando qualquer uma dessas configurações é desligada, qualquer usuário que recebe a política não pode iniciar ou agendar novas reuniões desse tipo. Ao mesmo tempo, os links de junção de reunião e as IDs de conferência de todas as reuniões existentes desse tipo que o usuário iniciou ou programou expiram anteriormente.

Por exemplo, se um usuário recebe uma política de reunião na qual essas configurações  de política de reunião estão definidas como **On** e, em seguida, você desliga a configuração Permitir Reunir agora em canais, esse usuário não pode mais iniciar reuniões improvisadas em canais e o canal Reunir agora inserir links que o usuário criou anteriormente estão expirados. O usuário ainda pode iniciar e agendar outros tipos de reunião e participar de reuniões organizadas por outras pessoas.

## <a name="what-happens-when-the-meeting-join-link-and-conference-id-expire"></a>O que acontece quando o link de junção de reunião e a ID da conferência expiram?

Quando o link de junção de reunião e a ID de conferência de uma reunião expiram, ninguém pode participar da reunião. Quando um usuário tenta ingressar na reunião por meio do link ou por telefone, ele receberá uma mensagem informando que a reunião não está mais disponível. Conversas, arquivos, quadro de diálogo, gravações, transcrições e outros conteúdos relacionados à reunião são mantidos e os usuários ainda podem acessá-los.

## <a name="what-happens-when-you-turn-on-and-turn-off-a-meeting-policy-setting"></a>O que acontece quando você ativar e desativar uma configuração de política de reunião?

### <a name="switch-a-meeting-policy-setting-from-on-to-off"></a>Alternar uma configuração de política de reunião de um para outro

Quando uma configuração de política de reunião é definida como **On**, os usuários que são atribuídos à política podem iniciar ou agendar reuniões desse tipo e todos podem ingressar. Quando você alterna a configuração da política de reunião para Off **,** os usuários que são atribuídos à política não podem iniciar ou agendar novas reuniões desse tipo, e os links de junção de reunião e as IDs de conferência de reuniões existentes que o usuário agendava anteriormente expiram.

Lembre-se de que o usuário ainda pode participar de reuniões organizadas por outras pessoas.

### <a name="switch-a-meeting-policy-setting-from-off-to-on"></a>Alternar uma configuração de política de reunião de off para on

Quando você alterna uma configuração de política de reunião de **Off** para **On**, os usuários que são atribuídos à política podem iniciar ou agendar reuniões desse tipo. Se uma configuração de política de reunião estiver desligada e, em seguida, ativa novamente para um usuário, todas as reuniões agendadas (e expiradas) anteriormente organizadas pelo usuário se tornam ativas e as pessoas podem ingressar neles usando o link de participação da reunião ou por telefone.  

## <a name="meeting-expiration-scenarios"></a>Cenários de expiração de reunião

Aqui está um resumo de como funciona a expiração da reunião para cada uma das configurações de política de reunião discutidas neste artigo. 

|Se desejar... |Faça isso  |Comportamento de junção de reunião  |
|---------|---------|---------|
|Expire channel Reunir agora reuniões iniciadas por um usuário  |Desativar Permitir **Reunir agora em canais**.|Ninguém pode ingressar no canal Reunir agora reuniões iniciadas pelo usuário.         |
|Expirar reuniões de canal agendadas por um usuário   |Desativar **Permitir agendamento de reunião do canal**.         |Ninguém pode participar de reuniões de canal agendadas pelo usuário. Isso impede que as pessoas participem do seguinte:<ul><li>Reuniões de canal que ocorreram no passado.</li> <li>Reuniões de canal agendadas para o futuro e que ainda não ocorreram.</li><li>Instâncias futuras de reuniões de canal recorrentes.</li></ul>       |
|Expirar reuniões privadas agendadas por um usuário    |Desativar **Permitir agendamento de reuniões privadas** *e* desativar **Permitir o complemento do Outlook**.          |Ninguém pode participar de reuniões privadas agendadas pelo usuário. Isso impede que as pessoas participem do seguinte: <ul><li>Reuniões privadas que ocorreram no passado.</li> <li>Reuniões privadas agendadas para o futuro e que ainda não ocorreram.</li><li>Instâncias futuras de reuniões privadas recorrentes.</li></ul> Tanto **Permitir o agendamento de reuniões privadas** quanto Permitir que o complemento do **Outlook** devem estar desligados para expirar reuniões privadas agendadas por um usuário. Se uma configuração estiver desligada e a outra estiver ativa, os links de junção de reunião e as IDs de conferência de reuniões existentes permanecerão ativos e não expiram.      |
|Expire private Meet now meetings started by a user  |Desativar Permitir **Reunião agora em reuniões privadas**.          |Ninguém pode participar de reuniões privadas do Meet now iniciadas pelo usuário.         |

Se você quiser que as pessoas acessem reuniões que foram agendadas anteriormente ou iniciadas por um usuário específico, você pode:

- A opção Ativar a configuração da política de reunião para esse usuário.
- Desativar a configuração da política de reunião para esse usuário e ter outro usuário com a configuração de política habilitada criar uma nova reunião para substituir a reunião expirada.

> [!NOTE]
> Se a reunião foi enviada por um representante, que recebeu permissões para enviar convites de reunião em nome de outra pessoa, como um gerente, a configuração da política de reunião será aplicada à pessoa que concedeu permissão (o gerente).

## <a name="related-topics"></a>Tópicos relacionados

[Gerenciar políticas de reunião no Teams](meeting-policies-in-teams.md)

[Atribua políticas a seus usuários no Teams](assign-policies.md)

[Visão Geral do PowerShell do Teams](teams-powershell-overview.md)