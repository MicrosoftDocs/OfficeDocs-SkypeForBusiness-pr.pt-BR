---
title: Gerenciar políticas de reunião para gravação e transcrição
author: mkbond007
ms.author: mabond
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: jastark
audience: admin
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.meetingpolicies.recordingandtranscription
description: Saiba como gerenciar as configurações de política de reunião Teams para gravação e transcrição.
ms.openlocfilehash: da7a5d43231abcb00339f2ffc2c57c7e90ff2d2e
ms.sourcegitcommit: 9532eb79310cd653010565607fa394f2b8dd182d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/23/2022
ms.locfileid: "65646360"
---
# <a name="meeting-policy-settings-for-recording--transcription"></a>Configurações de política de reunião para gravação & transcrição

Este artigo descreve as configurações de política de reunião específicas para gravação e transcrição, incluindo o seguinte:

- [Permitir transcrição](#allow-transcription)
- [Permitir gravação em nuvem](#allow-cloud-recording)
- [Armazenar gravações fora de seu país ou região](#store-recordings-outside-of-your-country-or-region)

## <a name="allow-transcription"></a>Permitir transcrição

Esta é uma combinação de uma política por usuário e por organizador. Essa configuração controla se as legendas e os recursos de transcrição estão disponíveis durante a reprodução das gravações de reunião. A pessoa que iniciou a gravação precisa dessa configuração ativada para que esses recursos funcionem com a gravação.

Ativar essa configuração cria uma cópia da transcrição armazenada com a gravação da reunião que habilita **Pesquisa**, **CC** e **transcrições** na gravação da reunião.

Atualmente, a transcrição para reuniões gravadas só tem suporte para usuários que definem o idioma ou falam inglês em Teams reuniões.

## <a name="allow-cloud-recording"></a>Permitir gravação na nuvem

Essa configuração é uma combinação de uma política por organizador e por usuário e controla se as reuniões podem ser gravadas. A gravação poderá ser iniciada pelo organizador da reunião ou por outro participante se a configuração de política estiver ativada para o participante e se for um usuário autenticado da mesma organização.

Pessoas de fora da sua organização, como usuários federados e anônimos, não conseguem iniciar a gravação. Os usuários convidados não podem iniciar ou interromper a gravação.

![Captura de tela mostrando as opções de gravação](media/meeting-policies-recording.png)

Observe o exemplo a seguir.

|Usuário |Políticas de reunião  |Permitir gravação na nuvem |
|---------|---------|---------|
|Daniela | Global   | Desabilitado |
|Amanda | Location1MeetingPolicy | Habilitado|
|João (usuário externo) | Não aplicável | Não aplicável|

- As reuniões organizadas por Daniela não podem ser gravadas.
- Amanda não pode gravar reuniões organizadas por Daniela.
- As reuniões organizadas por Amanda podem ser gravadas.
- Daniela não pode gravar reuniões organizadas por Amanda.
- John não pode gravar reuniões organizadas por Amanda.

Para saber mais sobre a gravação de reunião na nuvem, confira [Gravação de reunião na nuvem do Teams](cloud-recording.md).

## <a name="store-recordings-outside-of-your-country-or-region"></a>Armazenar gravações fora de seu país ou região

Essa política controla se os registros de reunião podem ser armazenados permanentemente em outro país ou região. Se ela estiver habilitada, as gravações não poderão ser migradas. Para obter mais informações sobre reuniões na nuvem e onde as gravações são armazenadas, [consulte Teams de reunião na nuvem](cloud-recording.md).

## <a name="related-topics"></a>Tópicos relacionados

- [Atribuir políticas a usuários no Teams](policy-assignment-overview.md)
- [Gravação de reunião na nuvem](cloud-recording.md)
