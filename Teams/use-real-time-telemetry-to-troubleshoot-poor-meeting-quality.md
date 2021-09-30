---
title: Usar a telemetria em tempo real para solucionar problemas de qualidade de reunião ruim
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: mikedav, vkorlep
ms.topic: article
ms.assetid: 66945036-ae87-4c08-a0bb-984e50d6b009
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.directrouting.callanalytics
- ms.teamsadmincenter.users.activity.audioqualitycolumn
- Reporting
description: Use a telemetria em tempo real com detalhes sobre dispositivos, redes e conectividade para solucionar problemas do usuário com Microsoft Teams reuniões agendadas.
ms.openlocfilehash: c33e3309995d82fd16e9eb1deb2fa5fe24b04330
ms.sourcegitcommit: 5eb5acd7910724f7f4a598ecc28b003e5bbe5ea5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/29/2021
ms.locfileid: "60007885"
---
# <a name="use-real-time-telemetry-to-troubleshoot-poor-meeting-quality"></a>Usar a telemetria em tempo real para solucionar problemas de qualidade de reunião ruim

> [!NOTE]
> Esse recurso está atualmente em visualização pública.

Este artigo explica como usar a telemetria em tempo real para solucionar problemas Microsoft Teams qualidade de reunião para usuários individuais. Você pode ver a telemetria em tempo real se tiver uma das seguintes funções:

- Administrador do Teams
- Teams Especialista em Suporte de Comunicações
- Engenheiro de Suporte de Comunicações de Equipes

Para obter mais informações sobre Teams funções de administrador, consulte Use Microsoft Teams de administrador [para gerenciar Teams](/MicrosoftTeams/using-admin-roles).

A telemetria em tempo real permite que os administradores de IT vejam as reuniões agendadas de seus usuários importantes e vejam áudio, vídeo, compartilhamento de conteúdo e problemas relacionados à rede. Como administrador, você pode usar a telemetria para investigar esses problemas durante as reuniões e solucionar problemas em tempo real.

## <a name="what-is-real-time-telemetry"></a>O que é telemetria em tempo real?

Hoje, a solução de problemas de reunião individual está disponível para Teams administradores por meio da análise de chamada [após](use-call-analytics-to-troubleshoot-poor-call-quality.md) o final da reunião. A telemetria em tempo real permite que os administradores solucionem problemas de reuniões agendadas enquanto estão em andamento.

A telemetria em tempo real mostra informações detalhadas sobre Teams reuniões para cada usuário em sua conta Office 365 atualizada em tempo real. Ele inclui informações sobre dispositivos, rede, conectividade, áudio, vídeo e problemas de compartilhamento de conteúdo, o que ajudará o administrador a solucionar problemas de qualidade de chamada com mais eficiência.

Como administrador Teams, você tem acesso total a todos os dados de telemetria em tempo real para cada usuário. Além disso, você pode atribuir Azure Active Directory funções para dar suporte à equipe. Para saber mais sobre essas funções, consulte [Give permission to support and help desk staff](set-up-call-analytics.md#give-permission-to-support-and-helpdesk-staff).

## <a name="where-to-find-per-user-real-time-troubleshooting-telemetry"></a>Onde encontrar a telemetria de solução de problemas em tempo real por usuário

Para ver todas as informações de reunião e dados de um usuário, vá para o centro [Teams administrador.](https://admin.teams.microsoft.com) Em **Usuários**  >  **Gerenciar usuários,** selecione um usuário e abra a guia **Reuniões & chamadas** na página de perfil do usuário. Em **Reuniões recentes,** você verá uma lista de reuniões que o usuário participou nas últimas 24 horas para as quais *a telemetria* em tempo real está disponível , incluindo todas as reuniões em andamento. Se a reunião não estiver em andamento ou não tiver dados de telemetria em tempo real, ela será aparecer em **reuniões passadas.**

![Captura de tela da tabela de reuniões recentes.](media/recent-meetings.png)

Para obter informações adicionais sobre os participantes de uma reunião em andamento, incluindo suas estatísticas  de dispositivo, rede  e áudio, encontre a reunião em Reuniões recentes e selecione o link na coluna Participantes.

![Captura de tela da tabela de detalhes do participante.](media/participant-details.png)

Para ver a telemetria em tempo real de um determinado usuário para uma reunião em andamento, incluindo informações sobre detalhes de compartilhamento de dispositivo, rede, áudio, vídeo e conteúdo, selecione a **ID** da Reunião .

![Captura de tela dos dados de sessão do usuário de análise de chamada.](media/real-time-telemetry.png)

## <a name="platforms-supported-for-real-time-telemetry"></a>Plataformas com suporte para telemetria em tempo real

- Windows
- macOS
- Linux
- Android
- iOS

## <a name="teams-devices-support-with-real-time-telemetry"></a>Teams dispositivos suportam com telemetria em tempo real

- MTR - Surface Hub
- MTR - Teams Display
- MTR - Barra de colaboração
- Dispositivos ip Telefone ip

## <a name="limitations"></a>Limitações

- A telemetria em tempo real só está disponível para reuniões agendadas. Para reuniões ad hoc como Meet Now, PSTN, chamadas 1:1 e chamadas de grupo, a telemetria em tempo real não funcionará.
- A telemetria em tempo real só está disponível para apresentadores de evento ao vivo agendado. No momento, ele não está disponível para participantes do evento ao vivo.
- Os dados de telemetria em tempo real estão disponíveis para uma reunião em **Reuniões recentes** por 24 horas após o fim da reunião. Após 24 horas, você não pode acessar os dados e a reunião muda para **reuniões passadas.** Se uma reunião for maior que 3 horas, a telemetria em tempo real só estará disponível nas *últimas 3 horas.*
- A telemetria não funciona com versões mais antigas Teams. Se nenhuma telemetria estiver disponível, tente atualizar seu cliente.
- Se participantes externos ou usuários anônimos ingressarem  em uma reunião, seu nome de exibição mostrará como indisponível manter a privacidade entre locatários.

## <a name="related-topics"></a>Tópicos relacionados

[Configurar análise de chamada por usuário](set-up-call-analytics.md)

[Use Microsoft Teams funções de administrador para gerenciar Teams](/MicrosoftTeams/using-admin-roles).