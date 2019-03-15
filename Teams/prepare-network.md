---
title: Preparo da rede da sua organização para o Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 08/21/2018
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
ms.openlocfilehash: 57f8ffc7d5cedeb6117deffb99ad48ccbe17b48f
ms.sourcegitcommit: 3014331fff89a0842c4db0b9adf0ef32f9728ade
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/15/2019
ms.locfileid: "30640726"
---
# <a name="prepare-your-organizations-network-for-microsoft-teams"></a>Preparo da rede da sua organização para o Microsoft Teams

> [!Tip]
> Assista a sessão de seguir para saber como equipes aproveita sua rede e como planejar melhor conectividade de rede ideal: [Planejamento da rede de equipes](https://aka.ms/teams-networking)


As equipes combina três formas de tráfego:

-   Tráfego de dados entre o ambiente online do Office 365 e o cliente de equipes (sinalização, presença, bate-papo, carregamento de arquivo e download, sincronização do OneNote).

-   Tráfego de comunicação em tempo real do ponto a ponto (áudio, vídeo, da área de trabalho compartilhamento).

-   Tráfego de comunicação em tempo real de conferência (áudio, vídeo, da área de trabalho compartilhamento).

Isso afeta a rede em dois níveis: tráfego fluirá entre os clientes do Microsoft Teams diretamente para os cenários de ponto a ponto e tráfego fluirá entre o ambiente do Office 365 e os clientes do Microsoft Teams para cenários de reunião. Para garantir o fluxo de tráfego ideal, o tráfego deve ter permissão para fluxo ambos entre os segmentos de rede interna (por exemplo, entre sites pela WAN), bem como entre os sites de rede e o Office 365. Não abrir as portas corretas ou ativamente Bloqueando portas específicas levarão à redução uma experiência de degradação.

> [!NOTE]
> Reuniões são suportados no iOS e dispositivos móveis Android. 

Para obter uma experiência ideal com mídia de tempo real dentro Teams da Microsoft, a sua rede deve atender os requisitos de rede para o Office 365. Para obter mais informações, consulte [qualidade de mídia e o desempenho de conectividade de rede para Skype para negócios Online](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance).

Para os dois determinantes segmentos de rede (cliente para Microsoft Edge) e a extremidade do cliente para o Microsoft Edge, considere as seguintes recomendações.


|Valor  |Cliente para a borda da Microsoft  |Borda de cliente para a borda da Microsoft  |
|:--- |:--- |:--- |
|**Latência (uma maneira)**\*  |< 50 MS          |< 30ms         |
|**Latência (tempo de resposta ou tempo de ida e volta)**\* |< 100ms   |< seja, 60 MS |
|**Perda de pacotes de intermitência**    |% de <10 durante qualquer intervalo de 200 MS         |% de <1 durante qualquer intervalo de 200 MS         |
|**Perda de pacote**     |% de <1 durante qualquer 15 s intervalo          |<0.1% durante qualquer 15 s intervalo         |
|**Tremulação de entre chegada de pacotes**    |<30ms durante qualquer 15 s intervalo         |<15ms durante qualquer 15 s intervalo         |
|**Reordenar de pacotes**    |pacotes de fora de ordem <0.05%         |pacotes de fora de ordem <0.01%         |

\*As metas de latência métrico pressupõem que seu site da empresa ou sites e as bordas da Microsoft estão em continente o mesmo.

Sua conexão de site da empresa até a borda da rede Microsoft inclui primeiro salto acesso à rede, que pode ser WiFi ou outra tecnologia sem fio.

As metas de desempenho de rede pressupõem que a largura de banda adequada e/ou o [planejamento de QoS](QoS-in-Teams.md). Em outras palavras, os requisitos se aplicam diretamente para o tráfego de mídia em tempo real de equipes quando a conexão de rede está sob uma carga de pico.

Para testar os dois segmentos de rede, você pode usar a [Ferramenta de avaliação de rede](https://go.microsoft.com/fwlink/?linkid=855799). Essa ferramenta pode ser implantada em ambos o cliente PC diretamente e em um PC conectado a borda da rede do cliente. A ferramenta inclui documentação limitada, mas uma documentação mais aprofundada alternativa para o uso da ferramenta pode ser encontrada aqui: [Avaliação de prontidão de rede](https://go.microsoft.com/fwlink/?linkid=855800). Executando esta avaliação de prontidão de rede, é possível validar a preparação da sua rede para executar aplicativos de mídia em tempo real, como o Microsoft Teams.

> [!NOTE]
> Esta é a avaliação de prontidão de rede mesmo recomendado para ser executado para os clientes que desejam para implantar com êxito o Skype para negócios.


## <a name="bandwidth-requirements"></a>Requisitos de largura de banda

Cálculos de largura de banda for Microsoft Teams são complexos e para ajudar com isso, uma calculadora foi criada. Para acessar a Calculadora, vá para [Planejador de rede](https://aka.ms/bwcalc/) em MyAdvisor.

> [!NOTE]
> Tratamento de largura de banda de equipes aprimorou Skype para Business Online: para obter uma qualidade alta chamando ou experiência (com áudio, vídeo e compartilhamento) de reunião, equipes requer apenas 1.2 Mbps. Ele também pode ser dimensionado ainda mais para super alta qualidade se não houver largura de banda suficiente disponível. Quando uma solicitação de equipes encontra uma condição de baixa largura de banda, as equipes podem rapidamente reajustar o uso de largura de banda para adaptar-se a largura de banda disponível.

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