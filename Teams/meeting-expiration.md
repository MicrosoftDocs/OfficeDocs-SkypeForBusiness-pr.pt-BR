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
ms.openlocfilehash: e1efb8ac21cbe669bcea3569a5e231469685a249
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827521"
---
# <a name="meeting-policies-and-meeting-expiration-in-microsoft-teams"></a>Políticas de reunião e expiração de reunião no Microsoft Teams

[!INCLUDE [preview-feature](includes/preview-feature.md)]

## <a name="overview"></a>Visão Geral

[As políticas de](meeting-policies-in-teams.md) reunião no Microsoft Teams são usadas para controlar se os usuários em sua organização podem iniciar e agendar reuniões e os recursos que estão disponíveis para os participantes da reunião para reuniões agendadas por usuários. Você pode usar a política global (padrão para toda a organização) ou criar e atribuir políticas personalizadas. Você gerencia políticas de reunião no centro de administração do Microsoft Teams ou usando cmdlets [Get,](https://docs.microsoft.com/powershell/module/skype/get-csteamsmeetingpolicy) [New,](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) [Set,](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) [Remove,](https://docs.microsoft.com/powershell/module/skype/remove-csteamsmeetingpolicy) [Grant](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) -CsTeamsMeetingPolicy PowerShell.

As configurações de política de reunião que controlam se os usuários podem iniciar e agendar reuniões também controlam a expiração das reuniões agendadas pelos usuários. Quando o link de ingressar em uma reunião e a ID de conferência de uma reunião expirar, ninguém poderá ingressar na reunião. As seguintes configurações de política de reunião determinam se os usuários podem iniciar e agendar reuniões no Teams, e nós os referimos ao longo deste artigo.

- [Permitir Reunir agora em canais:](meeting-policies-in-teams.md#allow-meet-now-in-channels)controla se um usuário pode iniciar uma reunião improvisada em um canal.
- [Permitir o agendamento de reunião de canal:](meeting-policies-in-teams.md#allow-channel-meeting-scheduling)controla se um usuário pode agendar uma reunião em um canal.
- [Permitir o agendamento de reuniões privadas:](meeting-policies-in-teams.md#allow-scheduling-private-meetings)controla se um usuário pode agendar uma reunião privada no Teams. Uma reunião é particular quando não é publicada em um canal de uma equipe.
- [Permitir que o Outlook adicione:](meeting-policies-in-teams.md#allow-the-outlook-add-in)controla se um usuário pode agendar uma reunião privada a partir do Outlook. Uma reunião é particular quando não é publicada em um canal de uma equipe.
- [Permitir Reunião agora em reuniões privadas:](meeting-policies-in-teams.md#allow-meet-now-in-private-meetings)controla se um usuário pode iniciar uma reunião privada improvisada.

Por padrão, essas configurações estão ativas. Quando qualquer uma dessas configurações está desligada, qualquer usuário que recebe a política não pode iniciar ou agendar novas reuniões desse tipo. Ao mesmo tempo, os links de ingressar na reunião e as IDs de conferência de todas as reuniões existentes desse tipo que o usuário iniciou ou agendou anteriormente expiram.

Por exemplo, se um usuário recebe uma política de reunião na qual essas configurações  de política de reunião estão definidas como Ativar e, em seguida, você desliga a configuração Permitir Reunião agora na configuração de canais, esse usuário não pode mais iniciar reuniões improvisadas em canais, e o canal Reunir agora insinuou links que o usuário criou anteriormente expiraram. O usuário ainda pode iniciar e agendar outros tipos de reunião e ingressar em reuniões organizadas por outras pessoas.

## <a name="what-happens-when-the-meeting-join-link-and-conference-id-expire"></a>O que acontece quando o link de ingressar na reunião e a ID de conferência expiram?

Quando o link de ingressar na reunião e a ID de conferência de uma reunião expirar, ninguém poderá ingressar na reunião. Quando um usuário tenta ingressar na reunião por meio do link ou por telefone, ele verá uma mensagem informando que a reunião não está mais disponível. Conversas, arquivos, quadro de diálogo, gravações, transcrições e outros conteúdos relacionados à reunião são mantidos e os usuários ainda podem acessá-los.

## <a name="what-happens-when-you-turn-on-and-turn-off-a-meeting-policy-setting"></a>O que acontece quando você ativar e desativar uma configuração de política de reunião?

### <a name="switch-a-meeting-policy-setting-from-on-to-off"></a>Alternar uma configuração de política de reunião de um para outro

Quando uma configuração de política de reunião está definida como **Em,** os usuários que têm a política atribuída podem iniciar ou agendar reuniões desse tipo e todos podem ingressar. Quando você alterna a configuração da política de reunião para **Desligado,** os usuários que têm a política atribuída a ela não podem iniciar ou agendar novas reuniões desse tipo, e os links de ingressar na reunião e as IDs de conferência das reuniões existentes que o usuário agendou anteriormente expiram.

Lembre-se de que o usuário ainda pode ingressar em reuniões organizadas por outras pessoas.

### <a name="switch-a-meeting-policy-setting-from-off-to-on"></a>Alternar uma configuração de política de reunião de off para a

Quando você alterna uma  configuração de política de reunião de Off para **On,** os usuários que têm a política atribuída podem iniciar ou agendar reuniões desse tipo. Se uma configuração de política de reunião estiver desligada e, em seguida, ativada novamente para um usuário, todas as reuniões agendadas (e expiradas) anteriormente organizadas pelo usuário se tornam ativas e as pessoas podem ingressar usando o link de participação da reunião ou por telefone.  

## <a name="meeting-expiration-scenarios"></a>Cenários de expiração de reunião

Aqui está um resumo de como funciona a expiração da reunião para cada uma das configurações de política de reunião abordadas neste artigo. 

|Se desejar... |Faça isto  |Comportamento de junção de reunião  |
|---------|---------|---------|
|Expire channel Meet now meetings started by a user  |Desativar Permitir **Reunião agora em canais.**|Ninguém pode ingressar nas reuniões do canal Reunir agora iniciadas pelo usuário.         |
|Expirar reuniões de canal agendadas por um usuário   |Desativar o **agendamento de reunião do canal Permitir.**         |Ninguém pode ingressar em reuniões de canal agendadas pelo usuário. Isso impede que as pessoas in unam o seguinte:<ul><li>Reuniões de canal que ocorreram no passado.</li> <li>Reuniões de canal agendadas para o futuro e que ainda não ocorreram.</li><li>Instâncias futuras de reuniões de canal recorrente.</li></ul>       |
|Expirar reuniões particulares agendadas por um usuário    |Desativar Permitir **o agendamento de reuniões particulares** *e* desativar Permitir o **complemento Outlook.**          |Ninguém pode ingressar em reuniões particulares agendadas pelo usuário. Isso impede que as pessoas in unam o seguinte: <ul><li>Reuniões privadas que ocorreram no passado.</li> <li>Reuniões particulares agendadas para o futuro e que ainda não ocorreram.</li><li>Instâncias futuras de reuniões privadas recorrentes.</li></ul> Tanto **Permitir o agendamento de reuniões particulares** quanto Permitir o complemento **do Outlook** devem estar de folga para expirar reuniões privadas agendadas por um usuário. Se uma configuração estiver desligada e a outra estiver ativa, os links de participação da reunião e as IDs de conferência das reuniões existentes permanecerão ativos e não expirarão.      |
|Expirar reuniões privadas de Reunião agora iniciadas por um usuário  |Desativar Permitir **Reunião agora em reuniões privadas.**          |Ninguém pode ingressar em reuniões privadas reunir agora iniciadas pelo usuário.         |

Se quiser que as pessoas acessem reuniões que foram agendadas anteriormente ou iniciadas por um determinado usuário, você pode:

- Ativar a configuração da política de reunião para esse usuário.
- Desativar a configuração da política de reunião para esse usuário e deixar que outro usuário que tenha a configuração de política habilitada crie uma nova reunião para substituir a reunião expirada.

> [!NOTE]
> Se a reunião foi enviada por um representante, que recebeu permissões para enviar convites de reunião em nome de outra pessoa, como um gerente, a configuração da política de reunião será aplicada à pessoa que concedeu permissão (o gerente).

## <a name="related-topics"></a>Tópicos relacionados

[Gerenciar políticas de reunião no Teams](meeting-policies-in-teams.md)

[Atribua políticas a seus usuários no Teams](assign-policies.md)

[Visão Geral do PowerShell do Teams](teams-powershell-overview.md)