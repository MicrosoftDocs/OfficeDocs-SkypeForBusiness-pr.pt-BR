---
title: Políticas de gravação de eventos ao vivo
author: HowlinWolf-92
ms.author: v-mahoffman
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
description: Saiba mais sobre políticas de gravação de eventos ao vivo.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 9dbed75a7f9c9655cc52bb798eefb0038cc5fe4a
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60844924"
---
# <a name="live-event-recording-policies-in-microsoft-teams"></a>Políticas de gravação de eventos ao vivo Microsoft Teams

Você tem várias opções para gravar um evento Microsoft Teams ao vivo. As opções de gravação são definidas usando políticas de gravação. Este artigo descreve as várias configurações.

As opções de gravação são definidas usando o comando Do PowerShell [Set-CsTeamsMeetingBroadcastPolicy](/powershell/module/skype/set-csteamsmeetingbroadcastpolicy).

## <a name="scheduling-and-option-behaviors"></a>Agendamento e comportamentos de opção

Há duas opções de organizador durante o agendamento de uma gravação de eventos ao vivo:

- Gravação disponível para produtores e apresentadores

  - Arquivo de gravação: fornece um arquivo de gravação que os produtores e apresentadores podem baixar depois que o evento acabar.

- Gravação disponível para participantes

  - DVR: um gravador de vídeo digital (DVR) permite que os participantes rebobinem e pausem durante o evento

  - VOD: um vídeo sob demanda (VOD) permite que os participantes assistam após o evento ter acabado

## <a name="broadcast-recording-policy-setting"></a>Configuração da política de gravação de transmissão

Como parte da política de transmissão, há uma configuração que você pode alternar para ativar ou desativar a gravação para um evento ao vivo.

| &nbsp;| Gravação disponível para produtores e apresentadores | Gravação disponível para participantes |
| ------------------------------- | ---------------------------------------------------- | ------------------------------------- |
| Sempre gravar               | Desabilitado e selecionado                                | Habilitado e selecionado         |
| O organizador pode gravar ou não | Habilitado e selecionado por padrão                  | Habilitado e selecionado por padrão   |
| Nunca gravar               | Desabilitado e não selecionado                            | Desabilitado e não selecionado      |

## <a name="storage-and-persistence-behavior"></a>Armazenamento e comportamento de persistência

| Opção                                       | Estado   | DVR                                                   | VOD                                                     | Gravando                |
| ------------------------------------------------ | ------------ | --------------------------------------------------------- | ----------------------------------------------------------- | ---------------------------- |
| Gravação disponível para participantes | Selecionado     | O DVR está disponível e o ativo Serviços de Mídia do Azure (AMS) é armazenado por 180 dias | O participante pode acessar e assistir ao evento                     |                              |
|                                                  | Não Selecionado | O DVR está disponível e o ativo AMS é armazenado por 180 dias | O participante não terá acesso ao evento após o fim |                              |
||Desabilitado (Não selecionado)|DVR está disponível e o ativo AMS é excluído após o evento|O participante não terá acesso ao evento após o fim||
| Gravação disponível para produtores e apresentadores | Selecionado     |                                                           |                                                             | Um MP4 é criado e armazenado |
|                                                  | Não Selecionado |                                                           |                                                             | Nenhum arquivo é criado           |

### <a name="related-topics"></a>Tópicos relacionados

- [O que são eventos ao vivo de Teams?](what-are-teams-live-events.md)
- [Planejar eventos ao vivo do Teams](plan-for-teams-live-events.md)
- [Definir configurações de eventos ao vivo do Teams](configure-teams-live-events.md)
- [Teams de reunião de nuvens](../cloud-recording.md)
