---
title: Requisitos de infraestrutura de rede do Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Network infrastructure requirements
ms:assetid: 35c7bb3f-8e0f-48b7-8a2c-857d4b42a4c4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425841(v=OCS.15)
ms:contentKeyID: 48183804
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bc1f74705469bf3a024d84848942eae972e0a629
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826525"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="network-infrastructure-requirements-for-lync-server-2013"></a>Requisitos da infraestrutura de rede para o Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-18_

A placa adaptadora de rede de cada servidor na topologia do Lync Server 2013 deve dar suporte a pelo menos 1 gigabit por segundo (Gbps). Em geral, você deve conectar todas as funções de servidor na topologia do Lync Server usando uma rede local de baixa latência e alta largura de banda (LAN). O tamanho da LAN depende do tamanho da topologia:

  - Em topologias de edição padrão, os servidores devem estar em uma rede que suporte Ethernet de 1 Gbps ou equivalente.

  - Em topologias de pool Front-end, a maioria dos servidores deve estar em uma rede com suporte para mais de 1 Gbps, especialmente quando oferecer suporte à conferência de áudio/vídeo (A/V) e compartilhamento de aplicativos.

Para a integração com Rede Telefônica Pública Comutada (PSTN), você pode usar linhas T1/E1 ou tronco SIP.

<div>

## <a name="audiovideo-network-requirements"></a>Requisitos de rede de áudio/vídeo

Os requisitos de rede para áudio/vídeo (A/V) em uma implantação do Lync Server incluem o seguinte:

  - Se você estiver implantando um servidor de borda único ou um pool de bordas usando o balanceamento de carga de DNS, poderá configurar o firewall externo como um NAT. Você não pode configurar o firewall interno como um NAT. Para obter detalhes sobre esses requisitos, consulte [determinar requisitos de firewall e porta externo A/V para o Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md) na documentação de planejamento.
    
    <div>
    

    > [!IMPORTANT]  
    > Se você tiver um pool de bordas e estiver usando um balanceador de carga de hardware, será necessário usar endereços IP públicos em cada um dos servidores de borda e não poderá usar o NAT para os servidores ou o pool em seu dispositivo NAT (por exemplo, o firewall ou outro dispositivo de infraestrutura que faria o NAT inbou nd ou tráfego de saída). Para obter detalhes, consulte <A href="lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md">Resumo de portabilidade-dimensionamento consolidado com balanceadores de carga de hardware no Lync Server 2013</A> na documentação planejando para acesso de usuário externo.

    
    </div>

  - Se a sua organização usa uma infraestrutura de QoS (Qualidade de Serviço), o subsistema de mídia é projetado para funcionar com essa infraestrutura existente.

  - Caso você utilize o protocolo IPsec, é recomendável desabilitá-lo nos intervalos de portas usados para o tráfego de A/V. Para obter detalhes, consulte [exceções de IPsec no Lync Server 2013](lync-server-2013-ipsec-exceptions.md) na documentação de planejamento.

Para garantir a qualidade de mídia ideal, faça o seguinte:

  - Provisione seus links de rede para dar suporte a throughput de 65 kilobits por segundo (Kbps) por fluxo de áudio e 500 kbps por fluxo de vídeo, se habilitados, durante períodos de pico de uso. Uma sessão de áudio ou de vídeo bidirecional consiste em dois fluxos.

  - Para lidar com picos inesperados no tráfego acima desse nível e maior utilização ao longo do tempo, os pontos de extremidade de mídia do Lync Server podem se adaptar às diferentes condições de rede e às cargas de suporte de três vezes a taxa de transferência (consulte o parágrafo anterior) para áudio e vídeo enquanto ainda retenção de qualidade aceitável. No entanto, não presuma que essa capacidade de adaptação dará suporte a uma rede subvisionada. Em uma rede subprovisionada, a capacidade dos pontos de extremidade de mídia do Lync Server de lidar dinamicamente com condições de rede variáveis (por exemplo, perda de pacotes de alta capacidade temporária) é reduzida.

  - Para links de rede em que o provisionamento é extremamente dispendioso e difícil, talvez seja necessário considerar o provisionamento para um volume menor de tráfego. Nesse cenário, permita que a elasticidade dos pontos de extremidade de mídia do Lync Server absorvesse a diferença entre o volume de tráfego e o nível de tráfego de pico, ao custo de uma redução na qualidade de voz. Além disso, há uma redução no espaço de qualquer outra forma disponível para absorver picos repentinos de tráfego.

  - Para links que não podem ser provisionados corretamente em curto prazo (por exemplo, um site com links WAN muito ruins), considere a possibilidade de desabilitar o vídeo para determinados usuários.

  - Provisione sua rede para garantir um atraso máximo de ponto a ponto (latência) de 150 milissegundos (MS) em carga máxima. A latência é a única deficiência da rede que os componentes de mídia do Lync Server não podem reduzir e é importante localizar e eliminar os pontos fracos.

  - Para servidores que executam o software antivírus, inclua todos os servidores que executam o Lync Server na lista de exceções para fornecer desempenho e qualidade de áudio ideais.

</div>

<div>

## <a name="conferencing-network-requirements"></a>Requisitos de rede de conferência

A largura de banda usada para baixar o conteúdo da conferência do servidor dos serviços de informações da Internet (IIS) depende do tamanho do conteúdo que foi carregado.

</div>

</div>

<span> </span>

</div>

</div>

</div>

