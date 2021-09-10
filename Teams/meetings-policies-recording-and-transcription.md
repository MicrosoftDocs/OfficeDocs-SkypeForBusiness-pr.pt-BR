---
title: Gerenciar políticas de reunião para gravação e transcrição
author: KarliStites
ms.author: kastites
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
description: Aprenda a gerenciar configurações de política de reunião em Teams para gravação e transcrição.
ms.openlocfilehash: c89fc88c46ae8b614021417ab2aa02832f64fce1
ms.sourcegitcommit: 69a5d4994ef75b9c16efa99554fb7f2ee1ccf52a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/10/2021
ms.locfileid: "58973160"
---
# <a name="meeting-policy-settings-for-recording--transcription"></a>Configurações de política de reunião para gravação & transcrição

Este artigo descreve as configurações de política de reunião específicas para gravação e transcrição, incluindo o seguinte:

- [Permitir transcrição](#allow-transcription)
- [Permitir gravação em nuvem](#allow-cloud-recording)
- [Armazenar gravações fora do seu país ou região](#store-recordings-outside-of-your-country-or-region)

## <a name="allow-transcription"></a>Permitir transcrição

Esta é uma combinação de uma política por usuário e por organizador. Essa configuração controla se as legendas e os recursos de transcrição estão disponíveis durante a reprodução das gravações de reunião. Se você desativar essa configuração, as opções **De** pesquisa e **CC** não estarão disponíveis durante a reprodução de uma gravação de reunião. A pessoa que iniciou a gravação precisa dessa configuração ativada para que a gravação também inclua a transcrição.

Atualmente, a transcrição para reuniões gravadas só é suportada para usuários que definirem seu idioma ou falarem inglês em Teams reuniões.

## <a name="allow-cloud-recording"></a>Permitir gravação na nuvem

Essa configuração é uma combinação de uma política por organizador e por usuário e controla se as reuniões podem ser gravadas. A gravação poderá ser iniciada pelo organizador da reunião ou por outro participante se a configuração de política estiver ativada para o participante e se for um usuário autenticado da mesma organização.

Pessoas de fora da sua organização, como usuários federados e anônimos, não conseguem iniciar a gravação. Os usuários convidados não podem iniciar ou interromper a gravação.

![Captura de tela mostrando opções de gravação](media/meeting-policies-recording.png)

Observe o exemplo a seguir.

|Usuário |Políticas de reunião  |Permitir gravação na nuvem |
|---------|---------|---------|
|Daniela | Global   | Desabilitado |
|Amanda | Location1MeetingPolicy | Habilitado|
|João (usuário externo) | Não aplicável | Não aplicável|

- As reuniões organizadas por Daniela não podem ser gravadas.
- A Amanda não pode gravar reuniões organizadas por Daniela.
- As reuniões organizadas por Amanda podem ser gravadas.
- Daniela não pode gravar reuniões organizadas por Amanda.
- John não pode gravar reuniões organizadas por Amanda.

Para saber mais sobre a gravação de reunião na nuvem, confira [Gravação de reunião na nuvem do Teams](cloud-recording.md).

## <a name="store-recordings-outside-of-your-country-or-region"></a>Armazenar gravações fora do seu país ou região

Essa política controla se os registros de reunião podem ser armazenados permanentemente em outro país ou região. Se estiver habilitado, as gravações não poderão ser migradas. Para obter mais informações sobre reuniões na nuvem e onde as gravações são armazenadas, [consulte Teams gravação de reunião na nuvem.](cloud-recording.md)

## <a name="related-topics"></a>Tópicos relacionados

- [Atribuir políticas aos usuários no Teams](policy-assignment-overview.md)
- [Gravação de reunião na nuvem](cloud-recording.md)