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
description: Aprenda a gerenciar configurações de política de reunião no Teams para gravação e transcrição.
ms.openlocfilehash: 06a05d2eb8a8c1542b79fa4c37b68ea4a3aa6d32
ms.sourcegitcommit: 00a526c5b9829302f7c4e0631d0c2dac50b7d004
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/16/2022
ms.locfileid: "69436758"
---
# <a name="meeting-policy-settings-for-recording--transcription"></a>Configurações de política de reunião para gravação & transcrição

Este artigo descreve as configurações da política de reunião específicas para gravação e transcrição em uma reunião do Teams. Essas configurações podem ser encontradas no centro de administração da equipe em **Políticas** >  de **reunião de reuniões**.

## <a name="transcription"></a>Transcrição

Esta é uma combinação de uma política por usuário e por organizador. Essa configuração controla se as legendas e os recursos de transcrição estão disponíveis durante a reprodução das gravações de reunião. A pessoa que iniciou a gravação precisa dessa configuração ativada para que esses recursos funcionem com a gravação.

Ativar essa configuração cria uma cópia da transcrição armazenada com a gravação da reunião que habilita **Pesquisa**, **CC** e **transcrições** na gravação da reunião.

## <a name="cloud-recording"></a>Gravação em nuvem

Essa configuração é uma combinação de uma política por organizador e por usuário e controla se as reuniões podem ser gravadas. A gravação poderá ser iniciada pelo organizador da reunião ou por outro participante se a configuração de política estiver ativada para o participante e se for um usuário autenticado da mesma organização.

Pessoas de fora da sua organização, como usuários federados e anônimos, não conseguem iniciar a gravação. Os convidados não podem iniciar ou parar a gravação.

![Captura de tela mostrando opções de gravação](media/meeting-policies-recording.png)

Observe o exemplo a seguir.

| Usuário                 | Políticas de reunião         | Permitir gravação na nuvem |
|----------------------|------------------------|-----------------------|
| Daniela              | Global                 | Desabilitado                   |
| Amanda               | Location1MeetingPolicy | Habilitado                    |
| John (externo) | Não aplicável         | Não aplicável        |

- As reuniões organizadas por Daniela não podem ser gravadas.
- Amanda não consegue gravar reuniões organizadas por Daniela.
- Reuniões organizadas por Amanda podem ser gravadas.
- Daniela não consegue gravar reuniões organizadas por Amanda.
- John não pode gravar reuniões organizadas por Amanda.

Para saber mais sobre a gravação de reunião na nuvem, confira [Gravação de reunião na nuvem do Teams](cloud-recording.md).

## <a name="meetings-automatically-expire"></a>As reuniões expiram automaticamente

Essa configuração controla se as gravações de reunião expiram automaticamente ou não. Depois de ativar essa configuração, você terá a opção de definir um tempo de validade padrão, medido em dias.

:::image type="content" source="media/meeting-expiration-policy.jpg" alt-text="Captura de tela do centro de administração do Teams da configuração automática de expiração da reunião.":::

Essa configuração fornece uma ferramenta simples que reduz a quantidade de gravações mais antigas de armazenamento. O sistema OneDrive e SharePoint monitorará o conjunto de expiração em todas as gravações de reunião e moverá automaticamente as gravações para a lixeira na data de validade.

### <a name="default-expiration-time"></a>Tempo de expiração padrão

Todas as gravações de reunião recém-criadas terão um vencimento padrão de 120 dias; todas as gravações criadas após a ativação desse recurso serão excluídas 120 dias após a data de criação.

> [!NOTE]
> O tempo máximo de validade padrão para usuários A1 é de 30 dias.

#### <a name="changing-default-expiration-time"></a>Alterando o tempo de expiração padrão

Os administradores podem editar a configuração de tempo de expiração padrão no PowerShell ou no centro de administração do Teams. Qualquer alteração afetará apenas as gravações de reunião recém-criadas a partir desse ponto em diante; elas não afetarão nenhuma gravação criada antes dessa data.

Os administradores não podem alterar o tempo de expiração em gravações de reunião existentes. Isso é feito para proteger a decisão do usuário que possui a gravação. As reuniões e chamadas podem ser controladas por essa configuração.

O valor de expiração é um inteiro por dias.  Isso pode ser definido da seguinte maneira:

- Valor mínimo: **1**
- Valor máximo: **99999**
- Você também pode definir o tempo de expiração como **-1** no PowerShell para que as gravações nunca expirem.

Exemplo de comando do PowerShell:

```powershell
Set-CsTeamsMeetingPolicy -Identity Global -NewMeetingRecordingExpirationDays 50
```

### <a name="compliance"></a>Conformidade

Você não deve confiar nas configurações de expiração da reunião para proteção legal, pois os usuários finais podem modificar a data de validade de todas as gravações que controlarem.

#### <a name="recording-expiration-settings-and-microsoft-365-retention-policies-in-microsoft-purview"></a>Configurações de expiração de gravação e Microsoft 365 políticas de retenção no Microsoft Purview

A retenção de arquivos tem precedência sobre a exclusão de arquivo. Uma gravação de reunião do Teams com uma política de retenção do Purview não pode ser excluída por uma política de expiração de gravação de reunião do Teams até que o período de retenção seja concluído. Por exemplo, se você tiver uma política de retenção do Purview que diz que um arquivo será mantido por cinco anos e uma política de expiração de gravação de reunião do Teams definida por 60 dias, a política de expiração de gravação de reunião do Teams excluirá permanentemente a gravação após cinco anos.

Se você tiver uma política de expiração de gravação de reunião do Teams e uma política de exclusão do Purview com datas de exclusão diferentes, o arquivo será excluído no início das duas datas. Por exemplo, se você tiver uma política de exclusão do Purview que diga que um arquivo será excluído após um ano e uma expiração de gravação de reunião do Teams definida por 120 dias, a política de expiração de gravação de reunião do Teams excluirá o arquivo após 120 dias.

Os usuários podem excluir manualmente suas gravações antes da data de validade, a menos que haja uma política de retenção do Purview que a impeça. Se uma gravação que ainda estiver no período de retenção for excluída manualmente por um usuário, a gravação será realizada na biblioteca de Retenção de Preservação. No entanto, a gravação será exibida como excluída para o usuário final. Para saber mais, confira [Saiba mais sobre retenção para SharePoint e OneDrive](/microsoft-365/compliance/retention-policies-sharepoint#how-retention-works-for-sharepoint-and-onedrive).

### <a name="deletion-of-recordings"></a>Exclusão de gravações

A gravação geralmente é excluída dentro de um dia após a data de validade, mas em instâncias raras pode levar até cinco dias. O proprietário do arquivo receberá uma notificação por email quando a gravação expirar e será direcionado para a lixeira para recuperar a gravação.

> [!NOTE]
> Na data de validade, a gravação é movida para a lixeira e o campo data de validade é limpo. Se você recuperar a gravação da lixeira, ela não será excluída por esse recurso novamente porque a data de validade foi desmarcada.

### <a name="expiration-of-migrated-recordings-from-stream-classic"></a>Expiração de gravações migradas de Stream (Clássico)

As gravações migradas de Stream (Clássico) não virão com um conjunto de expiração nelas. Em vez disso, incentivamos os administradores a migrar apenas gravações que eles desejam reter. Mais detalhes podem ser encontrados [na documentação de migração Stream (Clássico)](/stream/streamnew/stream-classic-to-new-migration-overview).

## <a name="store-recordings-outside-of-your-country-or-region"></a>Armazenar gravações fora do seu país ou região

Essa política controla se os registros de reunião podem ser armazenados permanentemente em outro país ou região. Se estiver habilitado, as gravações não poderão ser migradas. Para obter mais informações sobre reuniões na nuvem e onde as gravações são armazenadas, consulte [Gravação de reunião na nuvem do Teams](cloud-recording.md).

## <a name="related-topics"></a>Tópicos relacionados

- [Gerenciar políticas de reunião no Teams](meeting-policies-overview.md)
- [Atribuir políticas aos usuários no Teams](policy-assignment-overview.md)
- [Gravação de reunião na nuvem](cloud-recording.md)
- [Gerenciar quem pode agendar reuniões](manage-who-can-schedule-meetings.md)
