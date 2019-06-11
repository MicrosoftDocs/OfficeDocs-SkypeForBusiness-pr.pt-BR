---
title: 'Lync Server 2013: Opções de implantação do gateway PSTN'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: PSTN gateway deployment options
ms:assetid: d1ab4f74-18aa-40c7-a8cf-ec806cf6e28a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398899(v=OCS.15)
ms:contentKeyID: 48185445
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 137c9996429e953db22bea0c0dbd382f5a7af9a2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823816"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="pstn-gateway-deployment-options-in-lync-server-2013"></a>Opções de implantação do gateway PSTN no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-21_

<div>

## <a name="pstn-gateways"></a>Gateways PSTN

Gateways de rede telefônica pública comutada (PSTN) são componentes de hardware de terceiros que traduzem sinais e mídias entre a infraestrutura de voz empresarial e a PSTN, diretamente ou por meio da conexão com troncos SIP. Em qualquer topologia, o gateway termina a PSTN. O gateway está isolado em sua própria sub-rede e está conectado à rede corporativa por meio do servidor de mediação.

Uma empresa com vários sites normalmente implantou um ou mais gateways em cada site. Os sites de ramificação podem se conectar à PSTN por meio de um gateway ou por meio de um aparelho de ramificação sobreviventes, que combina o gateway e os servidores em uma única caixa. Se os sites de filiais usarem um gateway, um servidor de registrador e mediação será necessário no site, a menos que o link de WAN seja resiliente. Um ou mais servidores de mediação, que são posicionados em servidores front-end, podem encaminhar chamadas para um ou mais gateways em cada site. Recomendamos que o registrador, o servidor de mediação e o gateway necessários no site sejam implantados como um aparelho de ramificação sobreviventes.

Determinar o número, o tamanho e a localização dos gateways PSTN talvez seja a decisão mais importante e cara que você deve fazer ao planejar sua infraestrutura empresarial.

Aqui estão as principais perguntas a serem consideradas. Tenha em mente que as respostas para essas perguntas são todas interdependentes

  - Quantos gateways PSTN são necessários? A resposta depende do número de usuários, do número previsto de chamadas simultâneas (carga de tráfego) e do número de sites (cada site precisa de um).

  - Qual é o tamanho dos gateways? A resposta depende do número de usuários no site e na carga do tráfego.

  - Onde os gateways devem estar localizados? A resposta depende em parte da topologia e em parte da distribuição geográfica da sua organização.

Você também deve considerar as opções de topologia do gateway (para obter detalhes, consulte Topologias de gateway mais adiante neste tópico).

<div>

## <a name="mn-trunk-support"></a>Suporte de Tronco M:N

Os servidores de mediação podem rotear chamadas por meio de vários gateways, Session Borderting (SBCs) fornecido pelos provedores de serviços de telefonia pela Internet ou uma combinação dos dois. Além disso, vários servidores de mediação no pool podem interagir com vários gateways. A rota lógica definida entre um servidor de mediação e um gateway é chamada de *tronco*. Quando um usuário interno coloca uma chamada PSTN, a lógica de roteamento de saída no pool de front-ends escolhe qual tronco deve ser roteado por todas as combinações possíveis que podem estar disponíveis para roteamento com essa chamada específica. Com o balanceamento de carga de DNS, se uma chamada não entrar em contato com um gateway devido a um problema com um servidor de mediação específico no pool, a chamada será repetida em um servidor de mediação alternativo no pool.

Para obter detalhes sobre o planejamento de vários gateways, consulte [M:N trunk in Lync Server 2013](lync-server-2013-m-n-trunk.md).

Para obter detalhes sobre outros aprimoramentos de roteamento de saída, consulte [rotas de voz no Lync Server 2013](lync-server-2013-voice-routes.md).

</div>

<div>

## <a name="gateway-topologies"></a>Topologias de gateway

Ao considerar as questões fundamentais de implantação de gateway, siga estas etapas:

1.  Conte os sites nos quais você deseja fornecer conectividade PSTN usando o Enterprise Voice.

2.  Estimar o tráfego em cada site (número de usuários e número médio de chamadas por hora por hora por usuário).

3.  Implante um ou mais gateways em cada site para manipular o tráfego previsto.

A topologia de gateway distribuído resultante é mostrada na figura a seguir.

**Topologia de gateway distribuído**

![Diagrama de topologia de gateway distribuído] (images/Gg398899.f0f65a0b-a462-491a-878b-4d4bf0a96f6d(OCS.15).jpg "Diagrama de topologia de gateway distribuído")

Com essa topologia, chamadas entre trabalhadores em cada site e entre sites são roteadas pela intranet. As chamadas para a PSTN são roteadas na rede de IP da empresa para os gateways mais próximos ao local dos números de destino. Mas e se a sua organização oferecer suporte a dezenas ou centenas de sites ou até a milhares de sites distribuídos em um ou mais continentes, pois muitas instituições financeiras e outras grandes empresas fazem? Nesses casos, a implantação de um gateway separado em cada site não é prática.

Para solucionar esse problema, muitas grandes empresas preferem implantar um ou alguns sites centrais de telefonia grandes, conforme mostrado na figura a seguir.

**Topologia de site central de telefonia**

![Topologia de gateway do Data Center] (images/Gg398899.927f4808-bf74-405a-be20-2cd9cd87af6d(OCS.15).jpg "Topologia de gateway do Data Center")

Nessa topologia, vários gateways grandes suficientes para acomodar a carga de usuário prevista são implantados em cada site central. Todas as chamadas para os usuários na empresa são encaminhadas pelo provedor de serviços telefônicos da empresa para um site central. A lógica de roteamento no site central determina se a chamada deve ser roteada pela intranet ou pela PSTN.

</div>

<div>

## <a name="gateway-location"></a>Localização do gateway

O local do gateway também pode determinar os tipos de gateway que você escolher e como eles são configurados. Há dezenas de protocolos PSTN, nenhum dos quais é um padrão mundial. Se todos os seus gateways estiverem localizados em um único país/região, isso não é um problema, mas se você localizar gateways em vários países/regiões, cada um deve ser configurado de acordo com os padrões PSTN desse país/região. Além disso, os gateways certificados para a operação, por exemplo, no Canadá, podem não ser certificados na Índia, Brasil ou na União Européia.

</div>

<div>

## <a name="gateway-size-and-number"></a>Tamanho e número do gateway

Os gateways PSTN que a maioria das organizações considerará a implantação de intervalo em tamanho de 2 a até 960 portas. (Ainda há gateways maiores, mas eles são usados principalmente por provedores de serviço de telefonia.) Ao estimar o número de portas necessárias para sua organização, use as seguintes diretrizes:

  - Organizações com uso leve de telefonia (uma chamada PSTN por usuário por hora) devem atribuir uma porta para cada 15 usuários. Por exemplo, se você tiver 20 usuários, será necessário um gateway com duas portas.

  - Organizações com uso moderado de telefonia (duas chamadas PSTN por usuário por hora) devem atribuir uma porta para cada 10 usuários. Por exemplo, se você tiver usuários do 100, precisará de um total de 10 portas alocadas entre um ou mais gateways.

  - Organizações com uso intenso de telefonia (três ou mais chamadas PSTN por usuário por hora) devem atribuir uma porta para cada cinco usuários. Por exemplo, se você tiver usuários do 47.000, precisará de um total de 9.400 portas alocadas entre pelo menos 10 gateways maiores.

  - Portas adicionais podem ser adquiridas à medida que aumenta o número de usuários ou o volume de tráfego da sua organização.

Para qualquer número específico de usuários que você precisa dar suporte, você tem a opção de implantar mais gateways ou menos, ou menores. Como regra, um mínimo de dois gateways para uma organização é recomendado para manter a disponibilidade se um gateway falha.

Cada gateway PSTN que você implantar deve ter pelo menos um servidor de mediação correspondente.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

