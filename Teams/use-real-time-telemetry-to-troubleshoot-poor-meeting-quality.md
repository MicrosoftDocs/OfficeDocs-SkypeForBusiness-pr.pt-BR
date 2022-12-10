---
title: Usar telemetria em tempo real para solucionar problemas de qualidade de reunião
author: CarolynRowe
ms.author: crowe
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
description: Use a telemetria em tempo real com detalhes sobre dispositivos, redes e conectividade para solucionar problemas do usuário com Microsoft reuniões agendadas pelo Teams.
ms.openlocfilehash: bbda6d34a990ad810b22ce1742ab60a886295a6a
ms.sourcegitcommit: feb9b7d10e38f5a629ee9202b5aaec5beef4de9b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2022
ms.locfileid: "69343271"
---
# <a name="use-real-time-telemetry-to-troubleshoot-poor-meeting-quality"></a>Usar telemetria em tempo real para solucionar problemas de qualidade de reunião

Este artigo explica como usar Real-Time Analytics (RTA) para solucionar problemas de má qualidade de reunião do Teams Microsoft para usuários individuais. Você pode acessar Real-Time Analytics se tiver uma das seguintes funções:

- Administrador do Teams
- Especialista em Suporte de Comunicações do Teams
- Engenheiro de Suporte de Comunicações de Equipes

Para obter mais informações sobre funções de administrador do Teams, consulte [Usar Microsoft funções de administrador do Teams para gerenciar o Teams](/MicrosoftTeams/using-admin-roles).

Real-Time Analytics permite que os administradores de TI examinem as reuniões agendadas de seus usuários importantes e vejam problemas relacionados a áudio, vídeo, compartilhamento de conteúdo e rede. Como administrador, você pode usar essa telemetria para investigar esses problemas durante reuniões e solucionar problemas em tempo real.

## <a name="what-is-real-time-analytics"></a>O que é Real-Time Analytics?

Hoje, a solução de problemas de reunião individual está disponível para administradores do Teams por meio do [Call Analytics](use-call-analytics-to-troubleshoot-poor-call-quality.md) após o término da reunião. Real-Time Analytics permite que os administradores resolvam problemas de reuniões agendadas enquanto estão em andamento.

Real-Time Analytics mostra informações detalhadas sobre reuniões do Teams para cada usuário em sua conta Office 365, atualizadas em tempo real. Ele inclui informações sobre dispositivos, rede, conectividade, áudio, vídeo e problemas de compartilhamento de conteúdo, o que ajudará os administradores a solucionar problemas de qualidade de chamada de forma mais eficaz.

Como administrador do Teams, você obtém acesso total a todos os dados de telemetria em tempo real para cada usuário. Além disso, você pode atribuir funções do Azure Active Directory para dar suporte à equipe. Para saber mais sobre essas funções, confira [Dar permissão para dar suporte e ajudar a equipe do desk](set-up-call-analytics.md#give-permission-to-support-and-helpdesk-staff).

## <a name="where-to-find-per-user-real-time-troubleshooting-telemetry"></a>Onde encontrar a telemetria de solução de problemas por usuário em tempo real

Para ver todas as informações e dados de reunião de um usuário, acesse o [centro de administração do Teams](https://admin.teams.microsoft.com). Em **Usuários** > **Gerenciar usuários**, selecione um usuário e abra a guia **Reuniões & chamadas** na página de perfil do usuário. Em **Reuniões recentes**, você verá uma lista de reuniões que o usuário participou nas últimas 24 horas *para as quais a telemetria em tempo real está disponível*, incluindo todas as reuniões em andamento. Se a reunião não estiver em andamento ou não tiver dados de telemetria em tempo real, ela aparecerá em **reuniões passadas**.

:::image type="content" alt-text="Captura de tela da tabela de reuniões recentes." source="media/recent-meetings.png" lightbox="media/recent-meetings.png":::

> [!NOTE]
> Para que uma reunião apareça em "Reuniões Recentes", um administrador do Teams deve ter clicado na reunião no Real-Time Analytics enquanto a reunião estava em andamento para iniciar o fluxo de telemetria do cliente em tempo real.


Para obter informações adicionais sobre os participantes de uma reunião que está em andamento, incluindo suas estatísticas de dispositivo, rede e áudio, localize a reunião em **reuniões recentes** e selecione o link na coluna **Participantes** .

:::image type="content" alt-text="Captura de tela da tabela de detalhes do participante." source="media/participant-details-edit.png" lightbox="media/participant-details-edit.png":::

Para examinar a telemetria de um determinado usuário para uma reunião em andamento, incluindo informações sobre dispositivo, rede, áudio, vídeo e detalhes de compartilhamento de conteúdo, selecione a **ID da Reunião**.

:::image type="content" alt-text="Captura de tela dos dados da sessão do usuário da análise de chamadas." source="media/real-time-telemetry-edit.png" lightbox="media/real-time-telemetry-edit.png":::

## <a name="details-and-measures-available-in-real-time-analytics"></a>Detalhes e medidas disponíveis no Real-Time Analytics

### <a name="device-information"></a>Informações do dispositivo
| Nome | Descrição | Possíveis motivos para valores em branco|
|:---|:---|:---|
| Dispositivo de captura de áudio | Nome do dispositivo de captura de áudio (por exemplo: microfone) em uso | O sistema pode não ter um nome associado ao dispositivo (por exemplo: área de trabalho remota ou dispositivo 'Áudio remoto' da máquina virtual)  |
| Dispositivo de renderização de áudio | Nome do dispositivo de renderização de áudio (por exemplo: alto-falantes ou fones de ouvido) em uso | O sistema pode não ter um nome associado ao dispositivo (por exemplo: área de trabalho remota ou dispositivo 'Áudio remoto' da máquina virtual)  |
| Dispositivo de captura de vídeo | Nome do dispositivo de captura de vídeo em uso | O usuário não está enviando vídeo do ponto de extremidade que está sendo monitorado |

### <a name="connectivity-information"></a>Informações de conectividade
| Indicador | Unidades /Valores possíveis | Descrição | Possíveis motivos para valores em branco|
|:---|:---|:---|:---|
| Tipo de rede | &bull; Ethernet <br/> &bull; Wi-Fi | Tipo de conexão de rede em uso | |
| Wi-Fi força | &bull; Excelente : -50 dBm ou superior <br/> &bull; Bom : -51 dBm para -64 dBm<br/> &bull; Pobre: -65 dBm ou inferior | Força da conexão de Wi-Fi atual do usuário | O usuário não está conectado a Wi-Fi |
| canal Wi-Fi | Inteiro | Canal sobre o qual o ponto de acesso da rede Wi-Fi está transmitindo | O usuário não está conectado a Wi-Fi |
| Tipo físico | Cadeia de caracteres <br/> &bull; Exemplo: 802.11ac | Tipo de infraestrutura sem fio em uso | O usuário não está conectado a Wi-Fi |
| banda Wi-Fi | 2,4 GHz ou 5 GHz | Wi-Fi banda à qual o usuário está conectado | O usuário não está conectado a Wi-Fi |
| Localização | Cadeia de caracteres | País no qual o usuário está localizado | As informações de localização do usuário estão bloqueadas ou indisponíveis |
| Endereço IP local | Cadeia de caracteres (IP:Port) | Endereço IP local do ponto de extremidade do usuário e da porta de mídia | |
| Endereço IP reflexivo do servidor | Cadeia de caracteres (IP:Port) | Endereço IP público do ponto de extremidade do usuário e da porta de mídia | |
| Tipo de conectividade | UDP ou TCP | Protocolo de camada de transporte em uso; O UDP é preferido para mídia em tempo real | |

### <a name="user-signals"></a>Sinais de usuário
Os sinais de usuário identificam quando um usuário está participando ativamente da chamada, não está falando, mas não está conectado ou está mudo. Atualmente, os sinais de usuário só estão disponíveis para áudio.

| Modalidade | Valores possíveis | Descrição |
|:---|:---|:---|
| Áudio | &bull; Sem deslocamento, falando de participante <br/> &bull; Desmutado, sem falar <br/> &bull; Silenciado | Indica o comportamento do usuário para a parte de áudio da chamada  |


### <a name="audio"></a>Áudio
|Nome da medida |Unidades |Bom limite |Descrição |
|:---|:---|:---|:---|
|Tremulação |Milissegundos |Menos de 30 ms |O nervosismo é uma medida da variação do atraso do pacote para um fluxo de dados. Quando isso é muito alto, o áudio pode ficar agitado. | 
|Perda de pacote |Porcentagem |Menos de 5% |A perda de pacotes ocorre quando os pacotes de dados não chegam ao destino. A porcentagem de pacotes perdidos baseia-se no número total de pacotes enviados. |
|Tempo de viagem de ida e volta |Milissegundos |Menos de 500 ms |O tempo de ida e volta é o tempo necessário para um único pacote viajar do cliente para o ponto de extremidade remoto e voltar para o cliente. O tempo de viagem de ida e volta alto pode causar atrasos na reprodução do fluxo. Um exemplo disso é quando duas pessoas em uma reunião estão falando involuntariamente uma sobre a outra devido ao atraso. Mostrado somente para áudio de saída. |
|Bitrate |Quilobits por segundo (Kbps) |Maior que 24 Kbps |Taxa de transferência do fluxo de áudio expresso em quilobits por segundo. |
| Codec | Cadeia de caracteres <br/> &bull; Exemplo: SATIN | Somente informações | Exibe o codec de áudio que está sendo enviado e recebido. Um codec diferente pode ser recebido do que o que está sendo enviado. |


### <a name="video"></a>Vídeo
|Nome da medida |Unidades |Bom limite |Descrição |
|:---|:---|:---|:---|
|Tempo de viagem de ida e volta |Milissegundos |Menos de 500 ms |O tempo de ida e volta é o tempo necessário para um único pacote viajar do cliente para o ponto de extremidade remoto e voltar para o cliente. O tempo de viagem de ida e volta alto pode causar atrasos na reprodução do fluxo. Um exemplo disso é quando duas pessoas em uma reunião estão falando involuntariamente uma sobre a outra devido ao atraso. |
|Bitrate |Megabits por segundo (Mbps) | Somente informações |Taxa de transferência do fluxo de vídeo expresso em megabits por segundo. |
|Taxa de quadros (vídeo) |Quadros por segundo |360p ou melhor: 25-30 FPS <br/> 270p ou inferior: 7-15 FPS |Para fluxos de vídeo de saída, a taxa de quadros (FPS) é o número de quadros por segundo de vídeo que o cliente está enviando. Valores inferiores aos esperados aqui podem sugerir restrições de recurso do sistema, largura de banda de rede insuficiente ou mau comportamento de dispositivos de captura de vídeo. Resoluções diferentes têm diferentes intervalos de FPS aceitáveis. |
|Codec |Cadeia de caracteres | Somente informações |Exibe o codec de vídeo e o modo de renderização do fluxo de vídeo de saída. (Exemplo: H264 SW HW indica um fluxo de vídeo H264 usando a renderização de software e hardware.)|
|Resolução |Pixels | Somente informações |A resolução do vídeo que está sendo enviado. A resolução de vídeo de saída é dinâmica, com base nos requisitos mais altos de um ponto de extremidade na reunião. Um cliente capaz de vídeo 1920 x 1080 só enviará vídeo 640 x 360 se nenhum cliente estiver exibindo o vídeo desse usuário em um quadro maior que 640 x 360 |


### <a name="application-sharing-vbss"></a>Compartilhamento de aplicativos (VBSS)
|Nome da medida |Unidades |Bom limite |Descrição |
|:---|:---|:---|:---|
|Perda de pacote |Porcentagem |Menos de 5% |A perda de pacotes ocorre quando os pacotes de dados não chegam ao destino. A porcentagem de pacotes perdidos baseia-se no número total de pacotes enviados. |
|Tempo de viagem de ida e volta |Milissegundos |Menos de 500 ms |O tempo de ida e volta é o tempo necessário para um único pacote viajar do cliente para o ponto de extremidade remoto e voltar para o cliente. O tempo de viagem de ida e volta alto pode causar atrasos na reprodução do fluxo. Um exemplo disso é quando duas pessoas em uma reunião estão falando involuntariamente uma sobre a outra devido ao atraso. |
|Bitrate |Megabits por segundo (Mbps) | Somente informações |Taxa de transferência do fluxo VBSS expresso em megabits por segundo. |
|Taxa de Quadros |Quadros por segundo (FPS) | Somente informações |Para VBSS, a taxa de quadros está ciente do conteúdo para garantir que quantos quadros necessários sejam enviados para garantir uma boa experiência, evitando o envio de quadros se eles não forem necessários. Por exemplo, compartilhar um documento de texto na tela requer apenas 1 quadro por segundo para produzir uma boa experiência, enquanto compartilhar um vídeo ou conteúdo com mais atividade aumentará os quadros por segundo para um máximo de 30 FPS para produzir uma experiência mais suave. |
|Codec |Cadeia de caracteres | Somente informações |Exibe o codec e o modo de renderização do fluxo VBSS. (Exemplo: H264 SW HW indica um fluxo de VBSS H264 usando a renderização de software e hardware.)|
|Resolução |Pixels | Somente informações |A resolução do fluxo VBSS que está sendo enviado e recebido. |


## <a name="client-platforms-supported-for-real-time-telemetry"></a>Plataformas cliente com suporte para telemetria em tempo real

- Windows
- macOS
- Linux
- Android
- iOS

> [!NOTE]
> O cliente Web do Teams (incluindo o VDI) não dá suporte à entrega de telemetria em tempo real.

## <a name="teams-devices-with-support-for-real-time-telemetry"></a>Dispositivos do Teams com suporte para telemetria em tempo real

- Exibição do Teams
- Telefone do Teams
- Salas do Teams
- Salas do Teams no Surface Hub

> [!NOTE]
> Não há suporte para dispositivos que ingressaram na reunião usando soluções CVI (Cloud Video Interop) no Real-Time Analytics.


## <a name="limitations"></a>Limitações

- A assinatura de telemetria em tempo real não é automática para todas as reuniões e deve ser iniciada por um administrador do Teams enquanto a reunião está em andamento.
- A telemetria em tempo real só estará disponível para os pontos de extremidade com suporte de uma reunião a partir do ponto em que o administrador primeiro clicou na reunião em andamento no Real-Time Analytics.
- A telemetria em tempo real só está disponível para reuniões agendadas e para o Meet Now. Para PSTN, chamadas 1:1 e chamadas em grupo, a telemetria em tempo real não está disponível.
- A telemetria em tempo real só está disponível para os apresentadores do evento ao vivo agendado. No momento, ele não está disponível para participantes do evento ao vivo.
- Os dados de telemetria em tempo real estão disponíveis para uma reunião em **reuniões recentes** por 24 horas após o término da reunião. Após 24 horas, você não pode acessar os dados e a reunião passa para **reuniões anteriores**. Se uma reunião for maior que 3 horas, a telemetria em tempo real só estará disponível nas *últimas 3 horas*.
- A telemetria não está disponível em tempo real ao usar versões mais antigas do Teams. Se nenhuma telemetria estiver disponível, tente atualizar seu cliente.
- Se participantes externos ou usuários anônimos ingressarem em uma reunião, seu nome de exibição será mostrado como **indisponível** para manter a privacidade entre locatários.

> [!NOTE]
> Como parte de uma visualização pública por tempo limitado, os dados de telemetria em tempo real estão disponíveis atualmente por **7 dias** após o término de uma reunião. Após o término da visualização, apenas locatários com licenciamento de complemento de Comunicações Avançadas terão telemetria disponível para o período estendido de 7 dias. Todos os outros locatários estarão sujeitos aos limites acima mencionados.

## <a name="related-topics"></a>Tópicos relacionados

[Configurar análise de chamadas por usuário](set-up-call-analytics.md)

[Use Microsoft funções de administrador do Teams para gerenciar o Teams](/MicrosoftTeams/using-admin-roles).
