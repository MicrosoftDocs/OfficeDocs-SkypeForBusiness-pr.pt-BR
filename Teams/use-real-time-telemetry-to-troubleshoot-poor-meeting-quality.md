---
title: Usar telemetria em tempo real para solucionar problemas de qualidade de reunião
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
description: Use a telemetria em tempo real com detalhes sobre dispositivos, redes e conectividade para solucionar problemas do usuário com reuniões agendadas do Microsoft Teams.
ms.openlocfilehash: c7bc5ee0415a289782cad1dd7daa5c13bdaf7364
ms.sourcegitcommit: f2253162a23d0683e7424211da1a0a8760c8a91b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/29/2022
ms.locfileid: "66494718"
---
# <a name="use-real-time-telemetry-to-troubleshoot-poor-meeting-quality"></a>Usar telemetria em tempo real para solucionar problemas de qualidade de reunião

Este artigo explica como usar o Real-Time Analytics (RTA) para solucionar problemas de baixa qualidade de reunião do Microsoft Teams para usuários individuais. Você pode acessar Real-Time Analytics se tiver uma das seguintes funções:

- Administrador do Teams
- Especialista em Suporte de Comunicações do Teams
- Engenheiro de Suporte de Comunicações de Equipes

Para obter mais informações sobre as funções de administrador do Teams, [consulte Usar funções de administrador do Microsoft Teams para gerenciar o Teams](/MicrosoftTeams/using-admin-roles).

Real-Time Analytics permite que os administradores de TI examinem as reuniões agendadas de seus usuários importantes e vejam áudio, vídeo, compartilhamento de conteúdo e problemas relacionados à rede. Como administrador, você pode usar essa telemetria para investigar esses problemas durante as reuniões e solucionar problemas em tempo real.

## <a name="what-is-real-time-analytics"></a>O que é Real-Time Analytics?

Hoje, a solução de problemas de reunião individual está disponível para administradores do Teams por meio da [Análise](use-call-analytics-to-troubleshoot-poor-call-quality.md) de Chamadas após o término da reunião. Real-Time Analytics permite que os administradores solucionem problemas de reuniões agendadas enquanto estão em andamento.

Real-Time Analytics mostra informações detalhadas sobre reuniões do Teams para cada usuário em sua Office 365, atualizadas em tempo real. Ele inclui informações sobre dispositivos, rede, conectividade, áudio, vídeo e problemas de compartilhamento de conteúdo, o que ajudará os administradores a solucionar problemas de qualidade de chamada com mais eficiência.

Como administrador do Teams, você obtém acesso completo a todos os dados de telemetria em tempo real para cada usuário. Além disso, você pode atribuir funções do Azure Active Directory para dar suporte à equipe. Para saber mais sobre essas funções, confira [Conceder permissão para suporte e equipe de suporte técnico](set-up-call-analytics.md#give-permission-to-support-and-helpdesk-staff).

## <a name="where-to-find-per-user-real-time-troubleshooting-telemetry"></a>Onde encontrar telemetria de solução de problemas por usuário em tempo real

Para ver todas as informações e dados de reunião de um usuário, acesse o Centro [de administração do Teams](https://admin.teams.microsoft.com). Em **Gerenciar** > **Usuários**, selecione um usuário e abra a guia **Reuniões & chamadas na** página de perfil do usuário. Em **Reuniões recentes**, você verá uma lista de reuniões que o usuário participou nas últimas 24 horas para as quais a *telemetria* em tempo real está disponível, incluindo todas as reuniões em andamento. Se a reunião não estiver em andamento ou não tiver dados de telemetria em tempo real, ela aparecerá em **reuniões anteriores**.

:::image type="content" alt-text="Captura de tela da tabela de reuniões recentes." source="media/recent-meetings.png" lightbox="media/recent-meetings.png":::

Para obter informações adicionais sobre os participantes de uma reunião que está em andamento, incluindo suas estatísticas de dispositivo, rede e áudio, localize a reunião em  Reuniões recentes e selecione o link na coluna  Participantes.

:::image type="content" alt-text="Captura de tela da tabela de detalhes do participante." source="media/participant-details-edit.png" lightbox="media/participant-details-edit.png":::

Para examinar a telemetria de um determinado usuário para uma reunião em andamento, incluindo informações sobre detalhes de dispositivo, rede, áudio, vídeo e compartilhamento de conteúdo, selecione a **ID da Reunião**.

:::image type="content" alt-text="Captura de tela dos dados de sessão do usuário da análise de chamada." source="media/real-time-telemetry-edit.png" lightbox="media/real-time-telemetry-edit.png":::

## <a name="details-and-measures-available-in-real-time-analytics"></a>Detalhes e medidas disponíveis no Real-Time Analytics

### <a name="device-information"></a>Informações do dispositivo
| Nome | Descrição | Possíveis motivos para valores em branco|
|:---|:---|:---|
| Dispositivo de captura de áudio | Nome do dispositivo de captura de áudio (por exemplo: microfone) em uso | O sistema pode não ter um nome associado ao dispositivo (por exemplo: Área de Trabalho Remota ou Dispositivo de 'Áudio remoto' da máquina virtual)  |
| Dispositivo de renderização de áudio | Nome do dispositivo de renderização de áudio (por exemplo: alto-falantes ou fones de ouvido) em uso | O sistema pode não ter um nome associado ao dispositivo (por exemplo: Área de Trabalho Remota ou Dispositivo de 'Áudio remoto' da máquina virtual)  |
| Dispositivo de captura de vídeo | Nome do dispositivo de captura de vídeo em uso | O usuário não está enviando vídeo do ponto de extremidade que está sendo monitorado |

### <a name="connectivity-information"></a>Informações de conectividade
| Indicador | Unidades/Valores possíveis | Descrição | Possíveis motivos para valores em branco|
|:---|:---|:---|:---|
| Tipo de rede | &bull; Ethernet <br/> &bull; Wi-Fi | Tipo de conexão de rede em uso | |
| Wi-Fi força | &bull; Excelente: -50dBm ou superior <br/> &bull; Bom: -51 dBm a -64 dBm<br/> &bull; Ruim: -65 dBm ou inferior | Força da conexão de Wi-Fi atual do usuário | O usuário não está conectado ao Wi-Fi |
| Wi-Fi canal | Inteiro | Canal sobre o qual o Wi-Fi de acesso da rede está transmitindo | O usuário não está conectado ao Wi-Fi |
| Tipo físico | Cadeia de caracteres <br/> &bull; Exemplo: 802.11ac | Tipo de infraestrutura sem fio em uso | O usuário não está conectado ao Wi-Fi |
| Wi-Fi banda | 2,4 GHz ou 5 GHz | Wi-Fi banda à qual o usuário está conectado | O usuário não está conectado ao Wi-Fi |
| Localização | Cadeia de caracteres | País no qual o usuário está localizado | As informações de localização do usuário estão bloqueadas ou indisponíveis |
| Endereço IP local | Cadeia de caracteres (IP:Port) | Endereço IP local do ponto de extremidade do usuário e da porta de mídia | |
| Endereço IP reflexivo do servidor | Cadeia de caracteres (IP:Port) | Endereço IP público do ponto de extremidade do usuário e da porta de mídia | |
| Tipo de conectividade | UDP ou TCP | Protocolo de camada de transporte em uso; O UDP é preferencial para mídia em tempo real | |

### <a name="user-signals"></a>Sinais do usuário
Os sinais do usuário identificam quando um usuário está participando ativamente da chamada, não está falando, mas não está mudo ou está mudo. Atualmente, os sinais do usuário só estão disponíveis para áudio.

| Modalidade | Valores possíveis | Descrição |
|:---|:---|:---|
| Áudio | &bull; Inmutável, participante falando <br/> &bull; Sem deslocamento, sem falar <br/> &bull; Silenciado | Indica o comportamento do usuário para a parte de áudio da chamada  |


### <a name="audio"></a>Áudio
|Nome da Medida |Unidades |Limite bom |Descrição |
|:---|:---|:---|:---|
|Tremulação |Milissegundos |Menos de 30 ms |Tremulação é uma medida da variação no atraso de pacotes para um fluxo de dados. Quando isso é muito alto, o áudio pode ficar indisponindo. | 
|Perda de pacotes |Porcentagem |Menos de 5% |A perda de pacotes ocorre quando os pacotes de dados não chegam ao destino. O percentual de pacotes perdidos baseia-se no número total de pacotes enviados. |
|Tempo de ida e volta |Milissegundos |Menos de 500 ms |O tempo de viagem de ida e volta é o tempo necessário para que um único pacote viaje do cliente para o ponto de extremidade remoto e volte para o cliente. O tempo de viagem de ida e volta alto pode causar atrasos na reprodução do fluxo. Um exemplo disso é quando duas pessoas em uma reunião estão falando sem querer umas sobre as outras devido ao atraso. Mostrado somente para áudio de saída. |
|Bitrate |Quilobits por segundo (Kbps) |Maior que 24 Kbps |Taxa de transferência do fluxo de áudio expressa em quilobits por segundo. |
| Codec | Cadeia de caracteres <br/> &bull; Exemplo: SATIN | Somente informações | Exibe o codec de áudio que está sendo enviado e recebido. Um codec diferente pode ser recebido do que aquele que está sendo enviado. |


### <a name="video"></a>Vídeo
|Nome da Medida |Unidades |Limite bom |Descrição |
|:---|:---|:---|:---|
|Tempo de ida e volta |Milissegundos |Menos de 500 ms |O tempo de viagem de ida e volta é o tempo necessário para que um único pacote viaje do cliente para o ponto de extremidade remoto e volte para o cliente. O tempo de viagem de ida e volta alto pode causar atrasos na reprodução do fluxo. Um exemplo disso é quando duas pessoas em uma reunião estão falando sem querer umas sobre as outras devido ao atraso. |
|Bitrate |Megabits por segundo (Mbps) | Somente informações |Taxa de transferência do fluxo de vídeo expressa em megabits por segundo. |
|Taxa de Quadros (Vídeo) |Quadros por segundo |360p ou melhor: 25-30 FPS <br/> 270p ou inferior: 7 a 15 FPS |Para fluxos de vídeo de saída, a taxa de quadros (FPS) é o número de quadros por segundo do vídeo que o cliente está enviando. Valores menores do que o esperado aqui podem sugerir restrições de recursos do sistema, largura de banda de rede insuficiente ou dispositivos de captura de vídeo com comportamento inadequado. Resoluções diferentes têm diferentes intervalos de FPS aceitáveis. |
|Codec |Cadeia de caracteres | Somente informações |Exibe o codec de vídeo e o modo de renderização do fluxo de vídeo de saída. (Exemplo: H264 SW HW indica um fluxo de vídeo H264 usando a renderização de hardware e software.)|
|Resolução |Pixels | Somente informações |A resolução do vídeo que está sendo enviado. A resolução de vídeo de saída é dinâmica, com base no requisito mais alto de um ponto de extremidade na reunião. Um cliente capaz de vídeo 1920 x 1080 enviará apenas vídeo 640 x 360 se nenhum cliente estiver exibindo o vídeo desse usuário em um quadro maior que 640 x 360 |


### <a name="application-sharing-vbss"></a>Compartilhamento de Aplicativos (VBSS)
|Nome da Medida |Unidades |Limite bom |Descrição |
|:---|:---|:---|:---|
|Perda de pacotes |Porcentagem |Menos de 5% |A perda de pacotes ocorre quando os pacotes de dados não chegam ao destino. O percentual de pacotes perdidos baseia-se no número total de pacotes enviados. |
|Tempo de ida e volta |Milissegundos |Menos de 500 ms |O tempo de viagem de ida e volta é o tempo necessário para que um único pacote viaje do cliente para o ponto de extremidade remoto e volte para o cliente. O tempo de viagem de ida e volta alto pode causar atrasos na reprodução do fluxo. Um exemplo disso é quando duas pessoas em uma reunião estão falando sem querer umas sobre as outras devido ao atraso. |
|Bitrate |Megabits por segundo (Mbps) | Somente informações |Taxa de transferência do fluxo VBSS expresso em megabits por segundo. |
|Taxa de quadros |Quadros por segundo (FPS) | Somente informações |Para o VBSS, a taxa de quadros reconhece o conteúdo para garantir que tantos quadros quantos forem necessários sejam enviados para garantir uma boa experiência, evitando o envio de quadros se eles não forem necessários. Por exemplo, compartilhar um documento de texto na tela requer apenas 1 quadro por segundo para produzir uma boa experiência, enquanto o compartilhamento de um vídeo ou conteúdo com mais atividades aumentará quadros por segundo para um máximo de 30 FPS para produzir uma experiência mais suave. |
|Codec |Cadeia de caracteres | Somente informações |Exibe o codec e o modo de renderização do fluxo VBSS. (Exemplo: H264 SW HW indica um fluxo VBSS H264 usando a renderização de hardware e software.)|
|Resolução |Pixels | Somente informações |A resolução do fluxo VBSS que está sendo enviado e recebido. |


## <a name="client-platforms-supported-for-real-time-telemetry"></a>Plataformas cliente com suporte para telemetria em tempo real

- Windows
- macOS
- Linux
- Android
- iOS

> [!NOTE]
> O cliente Web do Teams (incluindo VDI) não dá suporte à entrega de telemetria em tempo real.

## <a name="teams-devices-with-support-for-real-time-telemetry"></a>Dispositivos do Teams com suporte para telemetria em tempo real

- MTR – Surface Hub
- MTR – Exibição do Teams
- MTR – Barra de colaboração
- Dispositivos ip phone

> [!NOTE]
> Dispositivos que ingressaram na reunião usando soluções de CVI (Interoperabilidade de Vídeo na Nuvem) não têm suporte no Real-Time Analytics.


## <a name="limitations"></a>Limitações

- A telemetria em tempo real só está disponível para reuniões agendadas e Reunir Agora. Para PSTN, chamadas 1:1 e chamadas de grupo, a telemetria em tempo real não está disponível.
- A telemetria em tempo real só está disponível para apresentadores de evento ao vivo agendado. No momento, ele não está disponível para participantes do evento ao vivo.
- Os dados de telemetria em tempo real estão disponíveis para uma reunião em **Reuniões recentes** por 24 horas após o término da reunião. Após 24 horas, você não poderá acessar os dados e a reunião será movida para **reuniões anteriores**. Se uma reunião tiver mais de 3 horas, a telemetria em tempo real só estará disponível nas *últimas 3 horas*.
- A telemetria não está disponível em tempo real ao usar versões mais antigas do Teams. Se nenhuma telemetria estiver disponível, tente atualizar o cliente.
- Se participantes externos ou usuários anônimos ingressarem em uma reunião, seu nome de exibição será exibido **como** indisponível para manter a privacidade entre locatários.

## <a name="related-topics"></a>Tópicos relacionados

[Configurar a análise de chamadas por usuário](set-up-call-analytics.md)

[Use as funções de administrador do Microsoft Teams para gerenciar o Teams](/MicrosoftTeams/using-admin-roles).
