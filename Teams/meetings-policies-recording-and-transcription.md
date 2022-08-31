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
description: Saiba como gerenciar as configurações de política de reunião no Teams para gravação e transcrição.
ms.openlocfilehash: 57e90984cde312f1804d5d2144c82a4d252822b6
ms.sourcegitcommit: 7a1fb6e15c21368afa34cd212865437781f721e2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/31/2022
ms.locfileid: "67466199"
---
# <a name="meeting-policy-settings-for-recording--transcription"></a>Configurações de política de reunião para gravação & transcrição

Este artigo descreve as configurações de política de reunião específicas para gravação e transcrição em uma reunião do Teams. Essas configurações podem ser encontradas no Centro de administração da equipe em **Políticas de Reunião** > **.**

## <a name="transcription"></a>Transcrição

Esta é uma combinação de uma política por usuário e por organizador. Essa configuração controla se as legendas e os recursos de transcrição estão disponíveis durante a reprodução das gravações de reunião. A pessoa que iniciou a gravação precisa dessa configuração ativada para que esses recursos funcionem com a gravação.

Ativar essa configuração cria uma cópia da transcrição armazenada com a gravação da reunião que habilita **Pesquisa**, **CC** e **transcrições** na gravação da reunião.

Atualmente, a transcrição para reuniões gravadas só tem suporte para usuários que definem o idioma ou falam inglês em reuniões do Teams.

## <a name="cloud-recording"></a>Gravação na nuvem

Essa configuração é uma combinação de uma política por organizador e por usuário e controla se as reuniões podem ser gravadas. A gravação poderá ser iniciada pelo organizador da reunião ou por outro participante se a configuração de política estiver ativada para o participante e se for um usuário autenticado da mesma organização.

Pessoas de fora da sua organização, como usuários federados e anônimos, não conseguem iniciar a gravação. Os convidados não podem iniciar ou parar a gravação.

![Captura de tela mostrando as opções de gravação](media/meeting-policies-recording.png)

Observe o exemplo a seguir.

| Usuário                 | Políticas de reunião         | Permitir gravação na nuvem |
|----------------------|------------------------|-----------------------|
| Daniela              | Global                 | Desabilitado                   |
| Amanda               | Location1MeetingPolicy | Habilitado                    |
| João (externo) | Não aplicável         | Não aplicável        |

- As reuniões organizadas por Daniela não podem ser gravadas.
- Amanda não pode gravar reuniões organizadas por Daniela.
- As reuniões organizadas por Amanda podem ser gravadas.
- Daniela não pode gravar reuniões organizadas por Amanda.
- John não pode gravar reuniões organizadas por Amanda.

Para saber mais sobre a gravação de reunião na nuvem, confira [Gravação de reunião na nuvem do Teams](cloud-recording.md).

## <a name="meetings-automatically-expire"></a>As reuniões expiram automaticamente

Essa configuração controla se as gravações de reunião expiram automaticamente. Depois de ativar essa configuração, você terá a opção de definir um tempo de expiração padrão, medido em dias.

:::image type="content" source="media/meeting-expiration-policy.jpg" alt-text="Captura de tela do centro de administração do Teams da configuração de expiração automática de reunião.":::

Essa configuração fornece uma ferramenta simples que reduz a quantidade de armazenamento usado por gravações mais antigas. O sistema OneDrive e SharePoint monitorará o conjunto de expiração em todas as gravações de reunião e moverá automaticamente as gravações para a lixeira na data de validade.

### <a name="default-expiration-time"></a>Tempo de expiração padrão

Todas as gravações de reunião recém-criadas terão uma expiração padrão de 120 dias; todas as gravações criadas depois que esse recurso foi ativado serão excluídas 120 dias após a data de criação.

> [!NOTE]
> O tempo de expiração padrão máximo para usuários A1 é de 30 dias.

#### <a name="changing-default-expiration-time"></a>Alterando o tempo de expiração padrão

Os administradores podem editar a configuração de tempo de expiração padrão no PowerShell ou no Centro de administração do Teams. Todas as alterações afetarão apenas as gravações de reunião recém-criadas desse ponto em diante; eles não afetarão as gravações criadas antes dessa data.

Os administradores não podem alterar o tempo de expiração nas gravações de reunião existentes. Isso é feito para proteger a decisão do usuário que possui a gravação. As reuniões e chamadas podem ser controladas por essa configuração.

O valor de expiração é um inteiro para dias.  Isso pode ser definido da seguinte maneira:

- Valor mínimo: **1**
- Valor máximo: **99999**
- Você também pode definir o tempo de expiração como **-1** no PowerShell para que as gravações nunca expirem.

Exemplo de comando do PowerShell:

```powershell
Set-CsTeamsMeetingPolicy -Identity Global -NewMeetingRecordingExpirationDays 50
```

### <a name="compliance"></a>Conformidade

Você não deve depender das configurações de expiração de reunião para proteção legal, pois os usuários finais podem modificar a data de validade de todas as gravações que eles controlam.

#### <a name="recording-expiration-settings-and-microsoft-365-retention-policies-in-microsoft-purview"></a>Configurações de expiração de gravação e políticas de retenção do Microsoft 365 no Microsoft Purview

A retenção de arquivo tem precedência sobre a exclusão de arquivo. Uma gravação de reunião do Teams com uma política de retenção do Purview não pode ser excluída por uma política de expiração de gravação de reunião do Teams até que o período de retenção seja concluído. Por exemplo, se você tiver uma política de retenção do Purview que diz que um arquivo será mantido por cinco anos e uma política de expiração de gravação de reunião do Teams definida por 60 dias, a política de expiração de gravação de reunião do Teams excluirá a gravação após cinco anos.

Se você tiver uma política de expiração de gravação de reunião do Teams e uma política de exclusão do Purview com datas de exclusão diferentes, o arquivo será excluído no início das duas datas. Por exemplo, se você tiver uma política de exclusão do Purview que diz que um arquivo será excluído após um ano e uma expiração de gravação de reunião do Teams definida por 120 dias, a política de expiração de gravação de reunião do Teams excluirá o arquivo após 120 dias.

Os usuários podem excluir manualmente suas gravações antes da data de validade, a menos que haja uma política de retenção do Purview que a impeça.

### <a name="deletion-of-recordings"></a>Exclusão de gravações

A gravação geralmente é excluída dentro de um dia após a data de validade, mas em instâncias raras pode levar até cinco dias. O proprietário do arquivo receberá uma notificação por email quando a gravação expirar e será direcionado para a lixeira para recuperar a gravação.

> [!NOTE]
> Na data de validade, a gravação é movida para a lixeira e o campo de data de validade é limpo. Se você recuperar a gravação da lixeira, ela não será excluída por esse recurso novamente porque a data de validade foi desmarcada.

### <a name="expiration-of-migrated-recordings-from-stream-classic"></a>Expiração de gravações migradas do Stream (Clássico)

As gravações migradas do Stream (Clássico) não virão com uma expiração definida. Em vez disso, incentivamos os administradores a migrar apenas as gravações que eles querem reter. Mais detalhes podem ser encontrados na [documentação Stream (Clássico) migração](/stream/streamnew/stream-classic-to-new-migration-overview).

## <a name="store-recordings-outside-of-your-country-or-region"></a>Armazenar gravações fora de seu país ou região

Essa política controla se os registros de reunião podem ser armazenados permanentemente em outro país ou região. Se ela estiver habilitada, as gravações não poderão ser migradas. Para obter mais informações sobre reuniões na nuvem e onde as gravações são armazenadas, consulte a gravação [de reuniões na nuvem do Teams](cloud-recording.md).

## <a name="related-topics"></a>Tópicos relacionados

- [Gerenciar políticas de reunião no Teams](meeting-policies-overview.md)
- [Atribuir políticas a usuários no Teams](policy-assignment-overview.md)
- [Gravação de reunião na nuvem](cloud-recording.md)
- [Gerenciar quem pode agendar reuniões](manage-who-can-schedule-meetings.md)
