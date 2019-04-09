---
title: Preparo da rede da sua organização para o Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
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
ms.openlocfilehash: cf48da12ddd1088c499f9d0703dc229d5b5df605
ms.sourcegitcommit: 58fec9aebd80029e1f1e71376efe222f9abf707e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/08/2019
ms.locfileid: "31516787"
---
# <a name="prepare-your-organizations-network-for-microsoft-teams"></a>Preparo da rede da sua organização para o Microsoft Teams


O Microsoft Teams combina três formas de tráfego:

-   O tráfego de dados entre o ambiente online do Office 365 e o cliente Microsoft Teams (sinalização, presença, chat, upload e download de arquivos, sincronização do OneNote).

-   Tráfego de comunicação ponto a ponto em tempo real (compartilhamento de áudio, vídeo e área de trabalho).

-   Tráfego de comunicação de conferências em tempo real (compartilhamento de áudio, vídeo e área de trabalho).

Isso impacta a rede em dois níveis: o tráfego fluirá entre os clientes Microsoft Teams diretamente para cenários ponto a ponto, e o tráfego fluirá entre o ambiente do Office 365 e os clientes Microsoft Teams para os cenários de reunião. Para garantir um fluxo de tráfego ideal, o tráfego deve ser permitido entre os segmentos internos da rede (por exemplo, entre sites da WAN), bem como entre os sites da rede e do Office 365. Deixar de abrir as portas corretas ou bloquear ativamente as portas especificadas prejudicará a experiência.

> [!NOTE]
> Reuniões são suportados no iOS e dispositivos móveis Android. 

Para obter uma experiência ideal com mídia de tempo real dentro Teams da Microsoft, a sua rede deve atender os requisitos de rede para o Office 365. Para obter mais informações, consulte [Qualidade de mídia e desempenho de conectividade de rede para o Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance).

Os dois segmentos de rede a ser definidos (Cliente para o Microsoft Edge e Edge do cliente para o Microsoft Edge), considere os seguintes requisitos.


|Valor  |Cliente para o Microsoft Edge  |Edge do cliente para o Microsoft Edge  |
|:--- |:--- |:--- |
|**Latência (uma maneira)**\*  |< 50 ms          |< 30 ms         |
|**Latência (tempo de resposta ou tempo de ida e volta)**\* |< 100 ms   |< 60 ms |
|**Perda de pacote de intermitência**    |<10% durante qualquer intervalo de 200 ms         |<1% durante qualquer intervalo de 200 ms         |
|**Perda de pacote**     |<1% durante qualquer intervalo de 15 s          |<0,1% durante qualquer intervalo de 15 s         |
|**Tremulação entre chegadas de pacote**    |<30 ms durante qualquer intervalo de 15 s         |<15 ms durante qualquer intervalo de 15 s         |
|**Novo pedido de pacotes**    |<0,05% de pacotes com problemas         |<0,01% de pacotes com problemas         |

\*As metas de latência métrico pressupõem que seu site da empresa ou sites e as bordas da Microsoft estão em continente o mesmo.

Sua conexão de site da empresa até a borda da rede Microsoft inclui primeiro salto acesso à rede, que pode ser WiFi ou outra tecnologia sem fio.

As metas de desempenho de rede pressupõem que a largura de banda adequada e/ou o [planejamento de QoS](QoS-in-Teams.md). Em outras palavras, os requisitos se aplicam diretamente para o tráfego de mídia em tempo real de equipes quando a conexão de rede está sob uma carga de pico.

Para testar os dois segmentos de rede, você pode usar a [Ferramenta de avaliação de rede](https://go.microsoft.com/fwlink/?linkid=855799). Essa ferramenta pode ser implantada em ambos o cliente PC diretamente e em um PC conectado a borda da rede do cliente. A ferramenta inclui documentação limitada, mas uma documentação mais aprofundada alternativa para o uso da ferramenta pode ser encontrada aqui: [Avaliação de prontidão de rede](https://go.microsoft.com/fwlink/?linkid=855800). Executando esta avaliação de prontidão de rede, é possível validar a preparação da sua rede para executar aplicativos de mídia em tempo real, como o Microsoft Teams.

> [!NOTE]
> Esta é a avaliação de prontidão de rede mesmo recomendado para ser executado para os clientes que desejam para implantar com êxito o Skype para negócios.


## <a name="bandwidth-requirements"></a>Requisitos de largura de banda
Teams da Microsoft oferece a melhor conteúdo de áudio, vídeo e compartilhamento experiência independentemente condições da sua rede. Com a variáveis codecs, mídia pode ser negociada em ambientes de largura de banda limitada com um impacto mínimo. Mas onde a largura de banda não for uma preocupação, experiências podem ser otimizadas por qualidade, incluindo backup resolução de vídeo 1080p, até 30fps para vídeo e 15fps para conteúdo e áudio de alta fidelidade.

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

#### <a name="external-name-resolution"></a>Resolução de nome externo

Certifique-se de que todos os computadores cliente executando o cliente de equipes podem resolver consultas DNS externas para descobrir os serviços fornecidos pelo Office 365 e que seus firewalls não estão impedindo o acesso. Para obter informações sobre como configurar portas de firewall, vá para o [Office 365 URLs e intervalos IP](office-365-urls-ip-address-ranges.md).

#### <a name="nat-pool-size"></a>Tamanho do Pool NAT

Quando vários dispositivos/usuários acessam o Office 365 usando a conversão de endereço de rede (NAT) ou Port Address Translation (PAT), você precisará garantir que os dispositivos ocultos por trás de cada endereço IP roteável publicamente exceder o número com suporte.

Para atenuar esse risco, certifique-se de adequada endereços de IP públicos são atribuídos para os pools NAT para evitar o esgotamento de porta. Esgotamento de porta fará com que os usuários finais internos e dispositivos enfrentando problemas ao conectar-se aos serviços do Office 365. Para obter mais informações, consulte [suporte a NAT com o Office 365](https://support.office.com/article/NAT-support-with-Office-365-170e96ea-d65d-4e51-acac-1de56abe39b9).

#### <a name="intrusion-detection-and-prevention-guidance"></a>**Orientações de prevenção e detecção de invasão**

Se seu ambiente tiver um sistema de prevenção contra (IDS/IPS) implantados para uma camada adicional de segurança para conexões de saída e/ou detecção de invasão, certifique-se de que nenhum tráfego com destino para URLs do Office 365 está na lista branca.

<a name="network-health-determination"></a>Determinação de integridade da rede
-----------------

Quando planejar na implementação do Microsoft Teams dentro de sua rede, você deverá garantir você tem a largura de banda necessária, você tem acesso a todos os endereços IP necessários, as portas corretas estão abertas, e você está cumprindo os requisitos de desempenho para a mídia em tempo real .

Se você souber que você não atenderá a esses critérios, os usuários finais não obterá uma experiência ideal de equipes devido à qualidade ruim durante as reuniões e chamadas.

Deve você não atender a esses critérios, este é um tempo para considerar pausando o projeto para garantir que atendam aos critérios antes de continuar.


|  |  |  |
|---------|---------|---------|
|![Ícone de ponto de decisão.](media/Prepare_your_organizations_network_for_Microsoft_Teams_image3.png)    |Ponto de decisão         |Você avaliou os recursos de rede para dar suporte a mídia de tempo real?<br></br>Se sua rede não foi avaliada corretamente ou se você sabe que ele não dará suporte a mídia de tempo real, você desativará vídeo e recursos para reduzir o impacto na rede e baixa experiências de equipes de compartilhamento de tela?         |
|![Ícone de próximos passos.](media/Prepare_your_organizations_network_for_Microsoft_Teams_image4.png)     |Próximos passos         |Qualidade de rede desconhecido: siga as orientações de [Avaliação de prontidão de rede](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers?pageState=NetworkReadiness) para determinar se a sua rede está pronta para a mídia de Tempo Real.<br></br>Baixa qualidade de rede: Execute etapas de atualização de rede para fornecer um ambiente adequado para alta qualidade de mídia de Tempo Real.<br></br>Satisfatório de rede: Verifique se todas as portas e endereços IP estão adequadamente acessíveis.           |

## <a name="related-topics"></a>Tópicos Relacionados

[Vídeo: Planejamento de rede](https://aka.ms/teams-networking)
