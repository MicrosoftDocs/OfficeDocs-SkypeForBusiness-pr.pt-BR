---
title: 'Lync Server 2013: M:N trunk'
description: 'Lync Server 2013: M:N trunk.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: M:N trunk
ms:assetid: dc4c5d66-297c-48a5-91b9-b9b8ce44a6e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398971(v=OCS.15)
ms:contentKeyID: 48185592
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5e0bcee237128046985b5313a47872ad83bf6513
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542557"
---
# <a name="mn-trunk-in-lync-server-2013"></a>Tronco M:N no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-01_

O Lync Server 2013 oferece suporte à maior flexibilidade na definição de um tronco para fins de roteamento de chamadas de versões anteriores. Um tronco é uma associação lógica entre um servidor de mediação e um número de porta de escuta com um gateway e um número de porta de escuta. Isso implica em várias coisas: um servidor de mediação pode ter vários troncos para o mesmo gateway; um servidor de mediação pode ter vários troncos para diferentes gateways; por outro lado, um gateway pode ter vários troncos para diferentes servidores de mediação.

Um tronco raiz ainda precisa ser criado quando um gateway é adicionado à topologia do Lync usando o construtor de topologias. O número de gateways que um determinado servidor de mediação pode lidar depende da capacidade de processamento do servidor durante o pico de horas de atividade. Se você implantar um servidor de mediação em hardware que exceda os requisitos mínimos de hardware para o Lync Server 2013, conforme descrito em [hardware suportado para o Lync server 2013](lync-server-2013-supported-hardware.md) na documentação de suporte, então a estimativa de quantas chamadas não-bypass ativas podem lidar com um servidor de mediação autônomo é aproximadamente 1000 chamadas. Quando implantado em hardware de reunião dessas especificações, espera-se que o servidor de mediação execute transcodificação, mas ainda roteia as chamadas para vários gateways, mesmo que os gateways não ofereçam suporte a bypass de mídia.

Ao definir uma rota de chamada, você especifica os troncos associados a essa rota, mas não especifica quais servidores de mediação estão associados a essa rota. Em vez disso, use o construtor de topologias para associar troncos a servidores de mediação. Em outras palavras, o roteamento determina qual tronco usar para uma chamada e, subsequentemente, o servidor de mediação associado a esse tronco é enviado à sinalização para essa chamada.

O servidor de mediação pode ser implantado como um pool; esse pool pode ser colocado em um pool de front-ends ou pode ser implantado como um pool autônomo. Quando um servidor de mediação é colocado em um pool de front-ends, o tamanho do pool pode ser no máximo 12 (o limite do tamanho do pool do registrador). Juntos, esses novos recursos aumentam a confiabilidade e a flexibilidade de implantação para servidores de mediação, mas exigem recursos associados nas seguintes entidades de mesmo nível:

  - **Gateway PSTN.** Um gateway qualificado do Lync Server 2013 deve implementar o balanceamento de carga DNS, o que permite que um gateway PSTN (rede telefônica pública comutada) atue como um balanceador de carga para um pool de servidores de mediação e, portanto, carregar chamadas de balanceamento no pool.

  - **Controlador de borda de sessão.** Para um tronco SIP, a entidade par é um controlador de borda de sessão (SBC) em um provedor de serviços de telefonia da Internet. Na direção do pool do servidor de mediação até o SBC, o SBC pode receber conexões de qualquer servidor de mediação no pool. Na direção do SBC para o pool, o tráfego pode ser enviado para qualquer servidor de mediação no pool. Um método de obter isso é por meio do balanceamento de carga DNS, se houver suporte do provedor de serviços e do SBC. Uma alternativa é fornecer ao provedor de serviços os endereços IP de todos os servidores de mediação no pool e o provedor de serviços provisioná-los em seu SBC como um tronco SIP separado para cada servidor de mediação. O provedor de serviços irá manipular o balanceamento de carga para seus próprios servidores. Nem todos os provedores de serviços ou SBCs podem oferecer suporte a esses recursos. Além disso, o provedor de serviços pode cobrar extra por esse recurso. Geralmente, cada tronco SIP para o SBC provoca uma taxa mensal.

  - **IP-PBX.** Na direção do pool do servidor de mediação para o encerramento SIP IP-PBX, o IP-PBX pode receber conexões de qualquer servidor de mediação no pool. Na direção do IP-PBX ao pool, o tráfego pode ser enviado para qualquer servidor de mediação no pool. Como a maioria dos IP-PBXs não dá suporte ao balanceamento de carga DNS, recomendamos que as conexões SIP diretas individuais sejam definidas a partir do IP-PBX para cada servidor de mediação no pool. O IP-PBX manipulará seu próprio balanceamento de carga distribuindo o tráfego no grupo de troncos. A pressuposição é que o grupo de troncos tem um conjunto consistente de regras de roteamento no IP-PBX. Se um IP-PBX específico oferece suporte a esse conceito de grupo de tronco e como ele faz interseção com a redundância de IP-PBX e a arquitetura de clustering precisa ser determinada para que você possa decidir se um cluster de servidor de mediação pode interagir corretamente com um IP-PBX.

Um pool de servidor de mediação deve ter uma visão uniforme do gateway par com o qual ele interage. Isso significa que todos os membros do pool acessam a mesma definição do gateway par do repositório de configuração e têm igualmente de interagir com ele para chamadas de saída. Portanto, não há uma maneira de segmentar o pool para que alguns servidores de mediação se comuniquem somente com determinados pares de gateway para chamadas de saída. Se essa segmentação for necessária, um pool separado de servidores de mediação deverá ser usado. Esse será o caso, por exemplo, se os recursos associados em gateways PSTN, troncos SIP ou IP-PBXs para interagir com um pool, conforme descrito anteriormente neste tópico, não estão presentes.

Um gateway PSTN específico, IP-PBX ou par de tronco SIP pode ser roteado para vários servidores de mediação ou troncos. O número de gateways que um pool específico de servidores de mediação pode controlar depende do número de chamadas que usam bypass de mídia. Se um grande número de chamadas usar o bypass de mídia, um servidor de mediação no pool pode lidar com muito mais chamadas, porque apenas o processamento da camada de sinalização é necessário.

</div>

<span> </span>

</div>

</div>

</div>

