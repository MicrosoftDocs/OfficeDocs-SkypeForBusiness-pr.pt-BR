---
title: 'Lync Server 2013: opções de implantação do gateway PSTN'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: PSTN gateway deployment options
ms:assetid: d1ab4f74-18aa-40c7-a8cf-ec806cf6e28a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398899(v=OCS.15)
ms:contentKeyID: 48185445
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d90fdcb368bf6ed9d610f214122900add5b15547
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42139002"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="pstn-gateway-deployment-options-in-lync-server-2013"></a>Opções de implantação de gateway PSTN no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-21_

<div>

## <a name="pstn-gateways"></a>Gateways PSTN

Gateways PSTN são componentes de hardware de terceiros que convertem sinais e mídia entre a infraestrutura do Enterprise Voice e da PSTN, diretamente ou por meio de troncos SIP. Em qualquer uma das topologias, o gateway encerra o PSTN. O gateway é isolado em sua própria sub-rede e está conectado à rede corporativa através do servidor de mediação.

Normalmente, uma empresa com vários sites implantaria um ou mais gateways em cada site. Os sites de filial podem se conectar à PSTN através de um gateway ou por meio de um aparelho de filial persistente, que combina o gateway e os servidores em uma única caixa. Se os sites de filial usarem um gateway, tanto um servidor de registrador quanto de mediação serão necessários no site, a menos que o link WAN seja resiliente. Um ou mais servidores de mediação, que são colocados em servidores front-end, podem encaminhar chamadas para um ou mais gateways em cada site. Recomendamos que o registrador, o servidor de mediação e o gateway necessários no site sejam implantados como um aparelho de filial persistente.

Determinar o número, o tamanho e o local de gateways PSTN é, talvez, a decisão mais importante e dispendiosa que você deve tomar ao planejar sua infraestrutura do Enterprise Voice.

Há várias perguntas a considerar. Tenha em mente que as respostas destas perguntas são interdependentes

  - Quantos gateways PSTN são necessários? A resposta depende do número de usuários, do número antecipado de chamadas simultâneas (carga de tráfego) e do número de sites (cada site precisa de um).

  - Qual deve ser o tamanho dos gateways? A resposta depende do número de usuários no site e da carga de tráfego.

  - Onde os gateways devem ser localizados? A resposta depende em parte da topologia e em parte da distribuição geográfica de sua organização.

Você também deve considerar suas opções de topologia de gateway (para obter detalhes, consulte Topologias de Gateway posteriormente neste tópico).

<div>

## <a name="mn-trunk-support"></a>Suporte de Tronco M:N

Os servidores de mediação podem rotear chamadas por vários gateways, controladores de borda de sessão (SBCs) fornecidos por provedores de serviços de telefonia da Internet ou uma combinação dos dois. Além disso, vários servidores de mediação no pool podem interagir com vários gateways. A rota lógica definida entre um servidor de mediação e gateway é chamada de *tronco*. Quando um usuário interno coloca uma chamada PSTN, a lógica de roteamento de saída no pool de front-ends escolhe o tronco a ser roteado para todas as combinações possíveis que podem estar disponíveis para roteamento de determinada chamada. Com o balanceamento de carga DNS, se uma chamada falhar ao alcançar um gateway devido a um problema com um servidor de mediação específico no pool, a chamada será tentada novamente em um servidor de mediação alternativo no pool.

Para obter detalhes sobre o planejamento de vários gateways, consulte [M:N trunk in Lync Server 2013](lync-server-2013-m-n-trunk.md).

Para obter detalhes sobre outros aprimoramentos de roteamento de saída, consulte [rotas de voz no Lync Server 2013](lync-server-2013-voice-routes.md).

</div>

<div>

## <a name="gateway-topologies"></a>Topologias de gateway

Ao considerar as perguntas fundamentais da implantação de gateway, siga estas etapas:

1.  Conte os sites nos quais você deseja fornecer conectividade PSTN usando o Enterprise Voice.

2.  Estime o tráfego em cada site (número de usuários e número médio de chamadas por hora, por usuário).

3.  Implante um ou mais gateways em cada site a fim de manipular o tráfego antecipado.

A topologia de gateway distribuído resultante é exibida na figura a seguir.

**Topologia de gateway distribuída**

![Diagrama de topologia de gateway distribuído](images/Gg398899.f0f65a0b-a462-491a-878b-4d4bf0a96f6d(OCS.15).jpg "Diagrama de topologia de gateway distribuído")

Com essa topologia, as chamadas entre os trabalhadores em cada site e entre sites são todas roteadas através de sua intranet. As chamadas para o PSTN são roteadas sobre a rede IP da empresa até os gateways mais próximos do local dos números de destino. Mas e se sua organização suportar dezenas ou centenas ou até mesmo milhares de sites espalhados em um ou mais continentes, assim como fazem muitas instituições financeiras e outras grandes empresas? Nesses casos, a implantação de um gateway separado em cada site não é prática.

Para resolver esse problema, muitas empresas grandes preferem implantar um ou alguns sites centrais de telefonia grandes, conforme mostrado na figura a seguir.

**Topologia de site central de telefonia**

![Topologia de gateway do Data Center](images/Gg398899.927f4808-bf74-405a-be20-2cd9cd87af6d(OCS.15).jpg "Topologia de gateway do Data Center")

Nessa topologia, vários gateways grandes o suficiente para acomodar a carga de usuário prevista são implantados em cada site central. Todas as chamadas aos usuários na empresa são encaminhadas pelo provedor de serviço de telefonia da empresa a um site central. A lógica de roteamento no site central determina se a chamada deve ser roteada pela intranet ou pela PSTN.

</div>

<div>

## <a name="gateway-location"></a>Local do gateway

O local do gateway também pode determinar os tipos de gateways que você escolhe e como eles são configurados. Há dezenas de protocolos PSTN, nenhum em um padrão mundial. Se todos os seus gateways estiverem localizados em um único país/região, isso não será um problema, mas se você localizar os gateways em diversos países/regiões, cada um precisa estar configurado de acordo com os padrões de PSTN nesse país/região. Além disso, os gateways certificados para operação no, por exemplo, Canadá, talvez não sejam certificados na Índia, Brasil ou União Europeia.

</div>

<div>

## <a name="gateway-size-and-number"></a>Tamanho e número de gateways

Os gateways PSTN que a maioria das organizações considerará implantar variam com relação ao tamanho de 2 a 960 portas. (Há gateways ainda maiores, mas eles são usados principalmente pelos provedores de serviço de telefonia.) Ao estimar o número de portas exigido por sua organização, use as seguintes diretrizes:

  - Organizações com uso leve de telefonia (uma chamada PSTN por usuário, por hora) deve alocar uma porta para cada 15 usuários. Por exemplo, se você tiver 20 usuários, precisará de um gateway com duas portas.

  - Organizações com um uso moderado de telefonia (duas chamadas PSTN por usuário, por hora) deve alocar uma porta para cada 10 usuários. Por exemplo, se você tiver 100 usuários, precisará de um total de 10 portas alocadas entre um ou mais gateways.

  - Organizações com uso pesado de telefonia (três ou mais chamadas PSTN por usuário, por hora) devem alocar uma porta para cada cinco usuários. Por exemplo, se você tiver 47.000 usuários, precisará de um total de 9.400 portas alocadas entre pelo menos 10 grandes gateways.

  - É possível adquirir portas adicionais à medida que o número de usuários ou quantidade de tráfego em sua organização aumenta.

Para qualquer quantidade de usuários que você deve suportar, você tem a opção de implantar uma quantidade menor de gateways maiores ou menores. Como regra, recomenda-se um mínimo de dois gateways para uma organização a fim de manter a disponibilidade, caso um gateway falhe.

Cada gateway PSTN que você implantar deve ter pelo menos um servidor de mediação correspondente.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

