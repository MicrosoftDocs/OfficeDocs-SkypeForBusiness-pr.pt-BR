---
title: Políticas de gravação de eventos ao vivo
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: christi.balaki
audience: admin
search.appverid: MET150
f1.keywords:
- CSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
description: Saiba mais sobre as políticas de gravação de eventos ao vivo.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 5ae98255edf26843e59839192a9f20096182bfa2
ms.sourcegitcommit: 4d88637f510a78d5709d1213c3e285d83a022014
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/14/2022
ms.locfileid: "66794109"
---
# <a name="live-event-recording-policies-in-microsoft-teams"></a>Políticas de gravação de eventos ao vivo no Microsoft Teams

Você tem várias opções para gravar um evento ao vivo do Microsoft Teams. As opções de gravação são definidas usando políticas de gravação. Este artigo descreve as várias configurações.

As opções de gravação são definidas usando o comando [Set-CsTeamsMeetingBroadcastPolicy](/powershell/module/skype/set-csteamsmeetingbroadcastpolicy) do PowerShell.

## <a name="scheduling-and-option-behaviors"></a>Comportamentos de agendamento e opção

Há duas opções de organizador ao agendar uma gravação de evento ao vivo:

- Gravação disponível para produtores e apresentadores

  - Arquivo de gravação: fornece um arquivo de gravação que os produtores e apresentadores podem baixar após o fim do evento.

- Gravação disponível para participantes

  - DVR: Um DVR (gravador de vídeo digital) permite que os participantes rebobinem e pausem durante o evento

  - VOD: um vídeo sob demanda (VOD) permite que os participantes assistam após o fim do evento

## <a name="broadcast-recording-policy-setting"></a>Configuração da política de gravação de difusão

Como parte da política de difusão, há uma configuração que você pode alternar para ativar ou desativar a gravação de um evento ao vivo.

| &nbsp;| Gravação disponível para produtores e apresentadores | Gravação disponível para participantes |
| ------------------------------- | ---------------------------------------------------- | ------------------------------------- |
| Sempre gravar               | Desabilitado e selecionado                                | Habilitado e selecionado         |
| O organizador pode gravar ou não | Habilitado e selecionado por padrão                  | Habilitado e selecionado por padrão   |
| Nunca gravar               | Desabilitado e não selecionado                            | Desabilitado e não selecionado      |

## <a name="storage-and-persistence-behavior"></a>Comportamento de armazenamento e persistência

| Opção                                       | Estado   | DVR                                                   | VOD                                                     | Gravando                |
| ------------------------------------------------ | ------------ | --------------------------------------------------------- | ----------------------------------------------------------- | ---------------------------- |
| Gravação disponível para participantes | Selecionado     | O DVR está disponível e o ativo dos Serviços de Mídia do Azure (AMS) é armazenado por 180 dias | O participante pode acessar e assistir ao evento                     |                              |
|                                                  | Não Selecionado | O DVR está disponível e o ativo AMS é armazenado por 180 dias | O participante não obterá acesso ao evento após o fim |                              |
||Desabilitado (não selecionado)|O DVR está disponível e o ativo AMS é excluído após o evento|O participante não obterá acesso ao evento após o fim||
| Gravação disponível para produtores e apresentadores | Selecionado     |                                                           |                                                             | Um MP4 é criado e armazenado por 180 dias |
|                                                  | Não Selecionado |                                                           |                                                             | Nenhum arquivo é criado           |

### <a name="related-topics"></a>Tópicos relacionados

- [O que são eventos ao vivo de Teams?](what-are-teams-live-events.md)
- [Planejar eventos ao vivo do Teams](plan-for-teams-live-events.md)
- [Definir configurações de eventos ao vivo do Teams](configure-teams-live-events.md)
- [Gravação de reunião de nuvens do Teams](../cloud-recording.md)
