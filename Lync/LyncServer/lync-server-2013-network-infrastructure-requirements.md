---
title: Requisitos de infraestrutura de rede do Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Network infrastructure requirements
ms:assetid: 35c7bb3f-8e0f-48b7-8a2c-857d4b42a4c4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425841(v=OCS.15)
ms:contentKeyID: 48183804
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ea383a77ff8d6089e2a01d7fb00df434f6d805e5
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42129374"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="network-infrastructure-requirements-for-lync-server-2013"></a>Requisitos de infraestrutura de rede para o Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-18_

A placa de adaptador de rede de cada servidor na topologia do Lync Server 2013 deve suportar pelo menos 1 gigabit por segundo (Gbps). Em geral, você deve conectar todas as funções de servidor dentro da topologia do Lync Server usando uma rede local de baixa latência e alta largura de banda (LAN). O tamanho da LAN depende do tamanho da topologia:

  - Nas topologias do Standard Edition, os servidores devem estar em uma rede que ofereça suporte a Ethernet de 1 Gbps ou equivalente.

  - Nas topologias do pool de front-ends, a maioria dos servidores deve estar em uma rede que ofereça suporte a mais de 1 Gbps, especialmente quando houver suporte para conferência de áudio/vídeo (A/V) e compartilhamento de aplicativos.

Para a integração com PSTN, você pode usar linhas T1/E1 ou troncos SIP.

<div>

## <a name="audiovideo-network-requirements"></a>Requisitos de rede para áudio/vídeo

Os requisitos de rede para áudio/vídeo (A/V) em uma implantação do Lync Server incluem o seguinte:

  - Se você estiver implantando um único servidor de borda ou um pool de borda usando o balanceamento de carga DNS, é possível configurar o firewall externo como NAT. Você não pode configurar o firewall interno como NAT. Para obter detalhes sobre esses requisitos, consulte [determine external A/V Firewall and Port Requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md) na documentação de planejamento.
    
    <div>
    

    > [!IMPORTANT]  
    > Se você tiver um pool de borda e estiver usando um balanceador de carga de hardware, deverá usar endereços IP públicos em cada um dos servidores de borda e não poderá usar o NAT para os servidores ou o pool no seu dispositivo NAT (por exemplo, o firewall ou outro dispositivo de infraestrutura que iria NAT inbou nd ou tráfego de saída). Para obter detalhes, consulte <A href="lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md">port SUMMARY-escalada Consolidated Edge with hardware Load balancers in Lync Server 2013</A> na documentação Planning for External User Access.

    
    </div>

  - Caso sua organização use uma infraestrutura de QoS (Qualidade de Serviço), o subsistema de mídia estará projetado para operar dentro dessa infraestrutura existente.

  - Caso você utilize o protocolo IPsec, é recomendável desabilitá-lo nos intervalos de portas usados para o tráfego de A/V. Para obter detalhes, consulte [exceções de IPsec no Lync Server 2013](lync-server-2013-ipsec-exceptions.md) na documentação de planejamento.

Para garantir a melhor qualidade da mídia, siga este procedimento:

  - Provisione os vínculos da rede para dar suporte a uma taxa de transferência de 65 Kbps (quilobits por segundo) por fluxo de áudio e 500 Kbps por fluxo de vídeo, se estiver habilitado, durante os períodos de uso máximo. Uma sessão de áudio ou vídeo bidirecional consiste em dois fluxos.

  - Para lidar com picos inesperados no tráfego acima desse nível e maior uso com o passar do tempo, os pontos de extremidade de mídia do Lync Server podem se adaptar às diferentes condições de rede e às cargas de suporte de três vezes a taxa de transferência (consulte o parágrafo anterior) para áudio e vídeo enquanto ainda manter a qualidade aceitável. No entanto, não presuma que essa adaptabilidade suportará uma rede subprovisionada. Em uma rede subvisionada, a capacidade dos pontos de extremidade de mídia do Lync Server de lidar dinamicamente com condições de rede variáveis (por exemplo, perda de pacote de alta capacidade temporária) é reduzida.

  - Para vínculos de rede em que o provisionamento envolve altíssimo custo e dificuldade, considere a opção de provisionar para um volume menor de tráfego. Neste cenário, deixe a elasticidade dos pontos de extremidade de mídia do Lync Server absorver a diferença entre o volume de tráfego e o nível de tráfego de pico, ao custo de alguma redução na qualidade de voz. Além disso, há uma diminuição na reserva dinâmica que, de outra forma, estaria disponível para absorver picos súbitos de tráfego.

  - Para os vínculos que não podem ser provisionados corretamente a curto prazo (por exemplo, um local com vínculos de WAN de péssima qualidade), considere a possibilidade de desabilitar o vídeo para determinados usuários.

  - Provisione sua rede para assegurar um atraso máximo de ponta a ponta (latência) de 150 ms (milissegundos) sob carga máxima. Latência é a única deficiência da rede que os componentes de mídia do Lync Server não podem reduzir e é importante encontrar e eliminar os pontos fracos.

  - Para servidores que executam software antivírus, inclua todos os servidores que executam o Lync Server na lista de exceções a fim de fornecer desempenho e qualidade de áudio ideais.

</div>

<div>

## <a name="conferencing-network-requirements"></a>Requisitos da Rede de Conferência

A largura de banda usada para baixar o conteúdo da conferência do servidor de serviços de informações da Internet (IIS) depende do tamanho do conteúdo carregado.

</div>

</div>

<span> </span>

</div>

</div>

</div>

