---
title: Preparo da rede da sua organização para o Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/25/2019
ms.topic: reference
ms.service: msteams
ms.reviewer: arachman
description: Saiba como preparar e gerenciar sua rede para o Microsoft Teams. As informações incluem requisitos de rede, requisitos de largura de banda e considerações adicionais.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: d203aefa4ba6991fbe6cf6a2ac463f4649f2aaa9
ms.sourcegitcommit: a388aec386b1a72b44c24d5f189a8c1cd401f706
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/24/2019
ms.locfileid: "35198417"
---
# <a name="prepare-your-organizations-network-for-microsoft-teams"></a>Preparo da rede da sua organização para o Microsoft Teams


O Microsoft Teams combina três formas de tráfego:

-   O tráfego de dados entre o ambiente online do Office 365 e o cliente Microsoft Teams (sinalização, presença, chat, upload e download de arquivos, sincronização do OneNote).

-   Tráfego de comunicação ponto a ponto em tempo real (compartilhamento de áudio, vídeo e área de trabalho).

-   Tráfego de comunicação de conferências em tempo real (compartilhamento de áudio, vídeo e área de trabalho).

Isso impacta a rede em dois níveis: o tráfego fluirá entre os clientes Microsoft Teams diretamente para cenários ponto a ponto, e o tráfego fluirá entre o ambiente do Office 365 e os clientes Microsoft Teams para os cenários de reunião. Para garantir um fluxo de tráfego ideal, o tráfego deve ser permitido entre os segmentos internos da rede (por exemplo, entre sites da WAN), bem como entre os sites da rede e do Office 365. Deixar de abrir as portas corretas ou bloquear ativamente as portas especificadas prejudicará a experiência.

> [!NOTE]
> As reuniões têm suporte em dispositivos móveis iOS e Android. 

Para ter uma experiência ideal com mídia em tempo real no Microsoft Teams, sua rede deve atender aos requisitos de rede do Office 365. Para obter mais informações, consulte [Qualidade de mídia e desempenho de conectividade de rede para o Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance).

Os dois segmentos de rede a ser definidos (Cliente para o Microsoft Edge e Edge do cliente para o Microsoft Edge), considere os seguintes requisitos.


|Valor  |Cliente para o Microsoft Edge  |Edge do cliente para o Microsoft Edge  |
|:--- |:--- |:--- |
|**Latência (de uma maneira)**\*  |< 50 ms          |< 30 ms         |
|**Latência (RTT ou tempo de viagem de ida e volta)**\* |< 100 ms   |< 60 ms |
|**Perda de pacote de intermitência**    |<10% durante qualquer intervalo de 200 ms         |<1% durante qualquer intervalo de 200 ms         |
|**Perda de pacote**     |<1% durante qualquer intervalo de 15 s          |<0,1% durante qualquer intervalo de 15 s         |
|**Tremulação entre chegadas de pacote**    |<30 ms durante qualquer intervalo de 15 s         |<15 ms durante qualquer intervalo de 15 s         |
|**Novo pedido de pacotes**    |<0,05% de pacotes com problemas         |<0,01% de pacotes com problemas         |

\*Os destinos de métrica de latência assumem que o site ou os sites da empresa e as bordas da Microsoft estão no mesmo continente.

A conexão do site da sua empresa com o Microsoft Network Edge inclui o acesso de rede de primeiro salto, que pode ser WiFi ou outra tecnologia sem fio.

Os destinos de desempenho de rede pressupõem largura de banda e/ou [planejamento de QoS](QoS-in-Teams.md)adequado. Em outras palavras, os requisitos se aplicam diretamente ao tráfego de mídia em tempo real do teams quando a conexão de rede está com carga de pico.

Para testar ambos os segmentos de rede, você pode usar a [ferramenta de avaliação de rede](https://go.microsoft.com/fwlink/?linkid=855799). Essa ferramenta pode ser implantada diretamente no PC cliente e em um PC conectado à borda de rede do cliente. A ferramenta inclui documentação limitada, mas uma documentação mais profunda sobre o uso da ferramenta pode ser encontrada aqui: [avaliação de prontidão de rede](https://go.microsoft.com/fwlink/?linkid=855800). Ao executar esta avaliação de preparação de rede, você pode validar a preparação da sua rede para executar aplicativos de mídia em tempo real, como o Microsoft Teams.

> [!NOTE]
> Esta é a mesma avaliação de preparação de rede que é recomendada para os clientes que pretendem implantar o Skype for Business com êxito.


## <a name="bandwidth-requirements"></a>Requisitos de largura de banda
O Microsoft Teams oferece a melhor experiência de áudio, vídeo e compartilhamento de conteúdo, independentemente das condições da rede. Com os codecs variáveis, a mídia pode ser negociada em ambientes limitados de largura de banda com impacto mínimo. Mas onde a largura de banda não é uma preocupação, as experiências podem ser otimizadas para qualidade, incluindo até 1080p de resolução de vídeo, até 30 qps para vídeo e 15fps para conteúdo e áudio de alta fidelidade.

[!INCLUDE [Bandwidth requirements](includes/bandwidth-requirements.md)]


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

#### <a name="external-name-resolution"></a>Resolução de nomes externos

Verifique se todos os computadores cliente que executam o cliente do teams podem resolver consultas DNS externas para descobrir os serviços fornecidos pelo Office 365 e se seus firewalls não impedem o acesso. Para obter informações sobre como configurar portas de firewall, vá para [URLs e intervalos de IP do Office 365](office-365-urls-ip-address-ranges.md).

#### <a name="nat-pool-size"></a>Tamanho do pool NAT

Quando vários usuários/dispositivos acessam o Office 365 usando a NAT (conversão de endereços de rede) ou PAT (conversão de endereço de porta), você precisa garantir que os dispositivos ocultos atrás de cada endereço IP roteável publicamente não exceda o número compatível.

Para reduzir esse risco, certifique-se de que os endereços IP públicos adequados sejam atribuídos aos pools de NAT para evitar a exaustão de portabilidade. A exaustão da porta fará com que usuários finais e dispositivos internos tenham problemas quando se conectar aos serviços do Office 365. Para obter mais informações, consulte [suporte a NAT com o Office 365](https://support.office.com/article/NAT-support-with-Office-365-170e96ea-d65d-4e51-acac-1de56abe39b9).

#### <a name="intrusion-detection-and-prevention-guidance"></a>**Orientação de detecção e prevenção de invasões**

Se seu ambiente tem um sistema de prevenção de intrusão e/ou prevenção (IDS/IPS) implantado para obter uma camada adicional de segurança para conexões de saída, certifique-se de que qualquer tráfego com o destino para URLs do Office 365 seja da lista branca.

<a name="network-health-determination"></a>Determinação da integridade da rede
-----------------

Ao planejar a implementação do Microsoft Teams em sua rede, você deve certificar-se de que tem a largura de banda necessária, ter acesso a todos os endereços IP necessários, às portas corretas abertas e a atender aos requisitos de desempenho de mídia em tempo real .

Se você sabe que não atenderá a esses critérios, seus usuários finais não receberão uma experiência ideal do teams devido à qualidade ruim durante chamadas e reuniões.

Se você não atender a esses critérios, essa é a hora de considerar a pausa do projeto para garantir que você atenda aos critérios antes de continuar.


|  |  |  |
|---------|---------|---------|
|![Um ícone representando um ponto de decisão](media/Prepare_your_organizations_network_for_Microsoft_Teams_image3.png)    |Ponto de decisão         |Você avaliou seus recursos de rede para oferecer suporte à mídia em tempo real?<br></br>Se a sua rede não tiver sido corretamente avaliada ou você souber que ela não será compatível com a mídia em tempo real, você desabilitará os recursos de vídeo e compartilhamento de tela para reduzir o impacto na rede e as experiências de equipes deficientes?         |
|![Um ícone que representa as próximas etapas](media/Prepare_your_organizations_network_for_Microsoft_Teams_image4.png)     |Próximos passos         |Qualidade de rede desconhecida: realize uma avaliação de prontidão de rede para determinar se sua rede está pronta para mídia em tempo real.<br></br>Qualidade da rede ruim: realize as etapas de correção de rede para fornecer um ambiente adequado para mídia de alta qualidade em tempo real.<br></br>Rede satisfatória: Assegure-se de que todos os endereços IP e portas estejam acessíveis corretamente.           |

## <a name="related-topics"></a>Tópicos Relacionados

[Vídeo: planejamento de rede](https://aka.ms/teams-networking)
