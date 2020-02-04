---
title: 'Lync Server 2013: M:N trunk'
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
ms.openlocfilehash: 4485380d6de5d247511b863761fcf7c75d38a29b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725631"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mn-trunk-in-lync-server-2013"></a>Tronco M:N no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-01_

O Lync Server 2013 dá suporte a maior flexibilidade na definição de um tronco para fins de roteamento de chamadas de versões anteriores. Um tronco é uma associação lógica entre um servidor de mediação e um número de porta de escuta com um gateway e um número de porta de escuta. Isso implica várias coisas: um servidor de mediação pode ter vários troncos para o mesmo gateway; um servidor de mediação pode ter vários troncos para gateways diferentes; por outro lado, um gateway pode ter vários troncos para diferentes servidores de mediação.

Um tronco raiz ainda precisa ser criado quando um gateway é adicionado à topologia do Lync usando o construtor de topologias. O número de gateways que um determinado servidor de mediação pode manipular depende da capacidade de processamento do servidor durante o pico de horas de ocupação. Se você implantar um servidor de mediação em hardware que exceda os requisitos mínimos de hardware para o Lync Server 2013, conforme descrito em [hardware com suporte para o Lync server 2013](lync-server-2013-supported-hardware.md) na documentação de suporte, então a estimativa de quantas chamadas sem bypass ativas um servidor de mediação autônomo pode manipular é aproximadamente 1000 chamadas. Quando implantado em um hardware que atenda a essas especificações, espera-se que o servidor de mediação execute transcodificação, mas ainda roteia chamadas para vários gateways, mesmo que os gateways não tenham suporte para bypass de mídia.

Ao definir um roteiro de chamada, especifique os troncos associados a essa rota, mas você não especifica quais servidores de mediação estão associados a essa rota. Em vez disso, use o construtor de topologias para associar troncos a servidores de mediação. Em outras palavras, o roteamento determina qual tronco usar para uma chamada e, subsequentemente, o servidor de mediação associado a esse tronco é enviado à sinalização para essa chamada.

O servidor de mediação pode ser implantado como um pool; esse pool pode ser colocado em um pool de front-ends ou pode ser implantado como um pool autônomo. Quando um servidor de mediação é posicionado com um pool de front-end, o tamanho do pool pode ser no máximo 12 (o limite do tamanho do pool do registrador). Juntos, esses novos recursos aumentam a confiabilidade e a flexibilidade de implantação para servidores de mediação, mas exigem recursos associados nas seguintes entidades de par:

  - **Gateway PSTN.** Um gateway qualificado do Lync Server 2013 deve implementar o balanceamento de carga de DNS, o que permite que um gateway PSTN (rede telefônica pública comutada) compatível atue como um balanceador de carga para um pool de servidores de mediação e, portanto, para carregar chamadas no pool.

  - **Controlador de Borda da Sessão.** Para um tronco SIP, a entidade par é um SBC (Controlador de Borda da Sessão) no provedor de serviços de telefonia da Internet. Na direção do pool do servidor de mediação para o SBC, o SBC pode receber conexões de qualquer servidor de mediação no pool. Na direção do SBC para o pool, o tráfego pode ser enviado para qualquer servidor de mediação no pool. Um método que permite isso é através do balanceamento de carga DNS, se ele tiver suporte do provedor de serviços e do SBC. Uma alternativa é conceder ao provedor de serviços os endereços IP de todos os servidores de mediação do pool, e o provedor de serviço provisionará esses endereços no SBC como um tronco SIP separado para cada servidor de mediação. O provedor de serviços tratará o balanceamento de carga de seus próprios servidores. Nem todos os provedores de serviços ou SBCs podem dar suporte a essas funcionalidades. Além disso, o provedor de serviços pode cobrar mais por essa funcionalidade. Geralmente, cada tronco SIP até o SBC é tarifado mensalmente.

  - **IP-PBX.** Na direção do pool do servidor de mediação para o cancelamento SIP IP-PBX, o IP-PBX pode receber conexões de qualquer servidor de mediação no pool. Na direção do PBX IP para o pool, o tráfego pode ser enviado para qualquer servidor de mediação no pool. Como a maioria dos PBXs IP não é compatível com o balanceamento de carga de DNS, recomendamos que as conexões SIP diretas SIP sejam definidas a partir do IP-PBX para cada servidor de mediação do pool. Depois disso, o IP-PBX tratará seu próprio balanceamento de carga distribuindo o tráfego pelo grupo de troncos. Presume-se que o grupo de troncos tenha um conjunto de regras de roteamento consistente no IP-PBX. Se um IP-PBX específico dá suporte a esse conceito de grupo de troncos e como ele faz a interseção entre a redundância do IP-PBX e a arquitetura de clustering precisa ser determinada antes que você possa decidir se um cluster do servidor de mediação pode interagir corretamente com um IP-PBX.

Um pool de servidores de mediação deve ter uma exibição uniforme do gateway de par com o qual ele interage. Isso significa que todos os membros do pool acessam a mesma definição do gateway par a partir do repositório de configurações e têm a mesma probabilidade de interagir com ele para as chamadas de saída. Portanto, não há nenhuma maneira de segmentar o pool para que alguns servidores de mediação se comuniquem somente em determinados pares de gateway para chamadas feitas. Se tal segmentação for necessária, um pool separado de servidores de mediação deve ser usado. Isso seria o caso, por exemplo, se as funcionalidades associadas nos gateways PSTN, nos troncos SIP ou nos IP-PBXs para interagir com um pool, conforme detalhado anteriormente neste tópico, não estivessem presentes.

Um determinado gateway PSTN, IP-PBX ou par de tronco SIP podem ser roteados para vários servidores de mediação ou troncos. O número de gateways que um determinado pool de servidores de mediação pode controlar depende do número de chamadas que usam bypass de mídia. Se um grande número de chamadas usar bypass de mídia, um servidor de mediação no pool pode manipular muitas outras chamadas, pois somente o processamento da camada de sinalização é necessário.

</div>

<span> </span>

</div>

</div>

</div>

