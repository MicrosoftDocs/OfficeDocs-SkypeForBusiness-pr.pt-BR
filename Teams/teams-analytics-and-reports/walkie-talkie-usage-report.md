---
title: Relatório de desempenho e uso do Walkie Talkie
author: LanaChin
ms.author: v-lanachin
manager: samanro
audience: admin
ms.topic: article
ms.service: microsoft-365-frontline
ms.reviewer: prastogi
f1.keywords:
- NOCSH
ms.localizationpriority: high
search.appverid: MET150
ms.collection:
- M365-collaboration
- m365-frontline
- highpri
- tier2
description: Saiba como usar o relatório de desempenho e uso do Walkie Talkie no centro de administração do Microsoft Teams para obter uma visão geral da atividade de uso do Walkie Talkie em sua organização.
appliesto:
- Microsoft Teams
- Microsoft 365 for frontline workers
ms.openlocfilehash: 85f92e715efe2b9608691151a08d006816658095
ms.sourcegitcommit: 776820a6c927fafabdfad9f50654fe7648d77bf3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/20/2023
ms.locfileid: "69846043"
---
# <a name="walkie-talkie-usage-and-performance-report"></a>Relatório de desempenho e uso do Walkie Talkie

O relatório de desempenho e uso do Walkie Talkie no centro de administração do Microsoft Teams fornece uma visão geral da atividade do [Walkie Talkie](../walkie-talkie.md) em sua organização. O relatório fornece informações como o número de transmissões PTT (push-to-talk) feitas e recebidas, atividade do canal, duração da transmissão e detalhes do dispositivo e do participante.

Use este relatório para obter informações sobre as tendências de uso e o desempenho do Walkie Talkie em sua organização. Para acessar o relatório, você deve ser um administrador global, administrador do Teams, leitor global ou leitor de relatório.

## <a name="download-and-view-the-report"></a>Baixar e exibir o relatório

1. Na navegação à esquerda do centro de administração do Microsoft Teams, escolha **Análise & relatórios** > **Relatórios de uso**. Na guia **Exibir relatórios** , em **Relatório**, selecione **Uso do Walkie Talkie**.
1. Em **Intervalo de datas**, selecione um intervalo de datas de 7 dias ou 30 dias. Em seguida, escolha **Executar relatório**.
1. Selecione **Gerar relatório**.
1. Na guia **Downloads** , em **Status**, escolha **Baixar** para baixar o relatório no formato CSV.

## <a name="interpret-the-report"></a>Interpretar relatório

O relatório fornece uma divisão de cada transmissão feita durante o intervalo de datas selecionado. Estas são as informações incluídas no relatório.

|Nome da coluna |Descrição |
|---------|---------|
|TenantId|ID do locatário.|
|Userid|ID do usuário.|
|Deviceid|ID do dispositivo.|
|ChannelId|O canal Walkie Talkie no qual a comunicação acontece.|
|clientCallStatus | Indica se o dispositivo foi capaz de receber a transmissão sem nenhum problema.|
|ConversationId|ID de cada transmissão PTT.|
|TeamId|ID da equipe que corresponde ao canal Walkie Talkie ao qual o usuário se conecta.|
|UnreachableParticipantsCount|Número de participantes sinalizados como inacessíveis e ocultos da lista porque não foram capazes de receber nenhuma das últimas cinco transmissões.|
|TransmissionDuration|Duração do tempo (em milissegundos) entre quando o serviço recebe a notificação de que um participante está prestes a iniciar uma transmissão para quando o serviço entrega o último pacote dessa transmissão.|
|TotalParticipantsCount|Número total de participantes conectados ao canal do Walkie Talkie.|
|PacketCount|Número de pacotes usados para enviar a transmissão de áudio.|
|NotifiedParticipants|Os participantes para os quais uma notificação por push é enviada quando uma transmissão é iniciada. Em cenários em que a conexão entre o dispositivo e o serviço é perdida, uma notificação é enviada ao dispositivo para restabelecer a conexão o mais rápido possível porque uma transmissão está chegando.|
|AudioDurationMilliseconds|Duração da transmissão em milissegundos.|
|Connectionid|ID de cada conexão com um canal do Walkie Talkie estabelecido pelo dispositivo.|
|TransmissionStartTime |Data e hora em que o primeiro pacote de áudio é recebido pelo serviço.
|TransmissionEndTime|Data e hora em que o último pacote de áudio é recebido pelo serviço.|
|Lista de Participantes|Uma lista delimitada de ponto semiautônomos de IDs dos dispositivos conectados ao canal no momento em que a transmissão é enviada.|
|CallTimedOut|Se a transmissão excedeu o limite de duração. Este é um valor booliano.|
|Plataforma|Sistema operacional do dispositivo.|
|ParticipantType|Se o participante era o transmissor ou um receptor da transmissão.|
|WebSocketState|Se o status da conexão entre o dispositivo e o serviço já estava estabelecido quando a transmissão começou.|
|AppVersion|Versão do aplicativo Teams instalado no dispositivo.|

## <a name="related-articles"></a>Artigos relacionados

- [Aplicativo Walkie Talkie no Teams](../walkie-talkie.md)
- [Introdução ao Walkie Talkie](https://support.microsoft.com/office/get-started-with-teams-walkie-talkie-25bdc3d5-bbb2-41b7-89bf-650fae0c8e0c)