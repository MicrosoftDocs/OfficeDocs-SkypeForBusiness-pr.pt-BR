---
title: Preparo da rede da sua organização para o Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 08/21/2018
ms.topic: article
ms.service: msteams
ms.reviewer: arachman
description: Saiba como preparar e gerenciar sua rede para o Microsoft Teams. As informações incluem requisitos de rede, requisitos de largura de banda e considerações adicionais.
localization_priority: Priority
search.appverid: MET150
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8a65f12399c18708b54404cb5df60bc5e24190f6
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23855357"
---
<a name="prepare-your-organizations-network-for-microsoft-teams"></a>Preparo da rede da sua organização para o Microsoft Teams
=================================================

O Microsoft Teams combina três formas de tráfego:

-   O tráfego de dados entre o ambiente online do Office 365 e o cliente Microsoft Teams (sinalização, presença, chat, upload e download de arquivos, sincronização do OneNote).

-   Tráfego de comunicação ponto a ponto em tempo real (compartilhamento de áudio, vídeo e área de trabalho).

-   Tráfego de comunicação de conferências em tempo real (compartilhamento de áudio, vídeo e área de trabalho).

Isso impacta a rede em dois níveis: o tráfego fluirá entre os clientes Microsoft Teams diretamente para cenários ponto a ponto, e o tráfego fluirá entre o ambiente do Office 365 e os clientes Microsoft Teams para os cenários de reunião. Para garantir um fluxo de tráfego ideal, o tráfego deve ser permitido entre os segmentos internos da rede (por exemplo, entre sites da WAN), bem como entre os sites da rede e do Office 365. Deixar de abrir as portas corretas ou bloquear ativamente as portas especificadas prejudicará a experiência.

> [!IMPORTANT]
> No momento, as reuniões têm suporte em dispositivos móveis iOS e Android, mas não no Windows Phone.

Para ter uma experiência ideal com mídia em tempo real no Microsoft Teams, é necessário atender aos requisitos de rede do Office 365. Para mais informações, consulte [Qualidade de mídia e desempenho de conectividade de rede para o Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance).

Para os dois determinantes segmentos de rede (cliente para Microsoft Edge) e a extremidade do cliente para o Microsoft Edge, considere as seguintes recomendações.


|Valor  |Cliente para o Microsoft Edge  |Edge do cliente para o Microsoft Edge  |
|---------|---------|---------|
|**Latência (unidirecional)**     |< 50 ms          |< 30 ms          |
|**Latência (RTT ou tempo-resposta)** |< 100 ms         |< 60 ms         |
|**Perda de pacote de intermitência**    |<10% durante qualquer intervalo de 200 ms         |<1% durante qualquer intervalo de 200 ms         |
|**Perda de pacote**     |<1% durante qualquer intervalo de 15 s          |<0,1% durante qualquer intervalo de 15 s         |
|**Tremulação entre chegadas de pacote**    |<30 ms durante qualquer intervalo de 15 s         |<15 ms durante qualquer intervalo de 15 s         |
|**Novo pedido de pacotes**    |<0,05% de pacotes com problemas         |<0,01% de pacotes com problemas         |

Para testar os dois segmentos de rede, use a [ferramenta de avaliação de rede](https://go.microsoft.com/fwlink/?linkid=855799). Essa ferramenta pode ser implantada diretamente no computador cliente e em um computador conectado ao Customer Network Edge. Essa ferramenta contém uma documentação limitada, mas uma documentação mais profunda do uso da ferramenta pode ser encontrada aqui: [Avaliação da prontidão da rede](https://go.microsoft.com/fwlink/?linkid=855800). Ao executar essa Avaliação da prontidão da rede, você pode validar a prontidão da sua rede para executar aplicativos de mídia em tempo real, como o Microsoft Teams.

> [!NOTE]
> Essa é a mesma Avaliação da prontidão da rede recomendada para clientes que estão buscando implantar o Skype for Business.

<a name="bandwidth-requirements"></a>Requisitos de largura de banda
----------

Os cálculos de largura de banda do Microsoft Teams são complexos e, para ajudar, foi criada uma calculadora. Para acessar a calculadora, vá para [Planejador de Rede no MyAdvisor](https://aka.ms/bwcalc/).

<!--
The content you will find below can be used as supplemental background information; however, it is recommended that customers use [Network Planner](https://aka.ms/bwcalc) to track their needs.

> [!IMPORTANT]
>If the required bandwidth is not available, the media stack inside Teams will degrade the quality of the audio/video session to accommodate for that lower amount of available bandwidth, impacting the quality of the call/meeting. The Teams client will attempt to prioritize the quality of audio over the quality of video. It is therefore extremely important to have the expected bandwidth available.


|Activity  |Download Bandwidth  |Upload Bandwidth  |Traffic Flow |
|---------|---------|---------|---------|
|**Peer to peer Audio Call**     |0.1 Mb         |0.1Mb         |Client <> Client         |
|**Peer to peer Video Call (full screen)**     |4 Mb         |4Mb         |Client <> Client          |
|**Peer to peer Desktop Sharing (1920*1080 resolution)**     |4 Mb         |4 Mb         |Client <> Client          |
|**2 Participant Meeting**     |4 Mb         |4 Mb         |Client <> Office 365         |
|**3 participant meeting**     |8 Mb         |6.5 Mb         |Client <> Office 365           |
|**4 participant meeting**     |5.5 Mb         |4 Mb         |Client <> Office 365           |
|**5 participant+ meeting**     |6 Mb         |1.5 Mb         |Client <> Office 365           |
-->

<a name="additional-network-considerations"></a>Considerações de rede adicionais
---------------

#### <a name="external-name-resolution"></a>**Resolução do nome externo**

Certifique-se de que todos os computadores cliente que executam o cliente Microsoft Teams possam resolver consultas externas de DNS para descobrir os serviços fornecidos pelo Office 365.

#### <a name="nat-pool-size"></a>**Tamanho do pool de NAT**

Quando vários usuários/dispositivos acessam o Office 365 usando Conversão de Endereços de Rede (NAT) ou Conversão de Endereços de Porta (PAT), você precisa assegurar que os dispositivos ocultos em cada um dos endereços IP publicamente roteáveis não excedam o número suportado.

Para reduzir esse risco, garanta que os endereços IP públicos adequados sejam atribuídos aos pools de NAT para prevenir o esgotamento de portas. O esgotamento de portas fará com que dispositivos e usuários finais internos enfrentem problemas ao se conectarem aos serviços do Office 365. Para mais informações, consulte o [guia Suporte de NAT com o Office 365](https://support.office.com/article/NAT-support-with-Office-365-170e96ea-d65d-4e51-acac-1de56abe39b9).

#### <a name="intrusion-detection-and-prevention-guidance"></a>**Detecção de intrusões e guia de prevenção**

Se o seu ambiente tiver um Sistema de Detecção e/u Prevenção de Intrusões (IDS / IPS) implantado para uma camada extra de segurança para conexões de saída, certifique-se de que qualquer tráfego com destino para URLs do Office 365 esteja na lista de permissões.

<a name="network-health-determination"></a>Determinação da integridade de rede
-----------------

Ao planejar a implementação do Microsoft Teams na sua rede, você precisa garantir ter a largura de banda necessária, ter acesso a todos os endereços IP necessários, ter as portas corretas abertas e atender aos requisitos de desempenho para mídias em tempo real.

Caso saiba da impossibilidade de atender a esses critérios, seus usuários finais não terão a experiência ideal no Microsoft Teams devido à má qualidade das chamadas e reuniões.

Caso não atenda a esses critérios, essa é a hora de considerar pausar o projeto para garantir que você esteja atendendo ao critérios antes de prosseguir.


|  |  |  |
|---------|---------|---------|
|![Ícone de ponto de decisão.](media/Prepare_your_organizations_network_for_Microsoft_Teams_image3.png)    |Ponto de decisão         |Você avaliou seus recursos de rede para suporte a mídia em tempo real?<br></br>Caso sua rede não tenha sido devidamente avaliada ou caso saiba que ela não consegue suportar mídia em tempo real, você vai desativar os recursos de vídeo e compartilhamento de tela para reduzir o impacto de rede e as experiências deficientes do Teams?         |
|![Ícone de próximos passos.](media/Prepare_your_organizations_network_for_Microsoft_Teams_image4.png)     |Próximos passos         |Qualidade de rede desconhecida: siga as orientações da [Avaliação da prontidão da rede](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers?pageState=NetworkReadiness) em para determinar se a sua rede está preparada para reproduzir mídia em tempo real.<br></br>Qualidade de rede deficiente: Execute as etapas de remediação de rede para proporcionar um ambiente adequado e de alta qualidade para mídia em tempo real.<br></br>Satisfatoriedade de rede: Garanta que todas as portas e endereços IP possam ser acessados adequadamente.           |

