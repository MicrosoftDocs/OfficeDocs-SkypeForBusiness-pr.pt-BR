---
title: 'Lync Server 2013: Componentes e topologias para o Servidor de Mediação'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Components and topologies for Mediation Server
ms:assetid: 71397168-36c3-4d21-b8ef-db6a751634ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398537(v=OCS.15)
ms:contentKeyID: 48184487
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1f9c353dc65f5e943e082df9321a934ea8f14be1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836525"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-mediation-server-in-lync-server-2013"></a>Componentes e topologias para o Servidor de Mediação no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-21_

Este tópico descreve os componentes nos quais o servidor de mediação é dependente e as topologias nas quais o servidor de mediação pode ser implantado

<div>

## <a name="dependencies"></a>Dependências

O servidor de mediação tem as seguintes dependências:

  - **Profissional.** Obrigatório. O registrador é o próximo nó para sinalizar nas interações do servidor de mediação com a rede do Lync Server 2013. Observe que o servidor de mediação pode ser posicionado em um servidor front-end juntamente com o registrador, além de ser instalado em um pool autônomo que consiste apenas em servidores de mediação. O registrador é posicionado com um servidor de mediação e um gateway PSTN em um aparelho de ramificação sobreviventes.

  - **Monitoring Server.** Opcional, mas altamente recomendado. O Monitoring Server permite que o servidor de mediação Registre métricas de qualidade associadas a suas sessões de mídia.

  - **Servidor de borda.** Obrigatório para suporte externo a usuários. O servidor de borda permite que o servidor de mediação interaja com os usuários que estão localizados atrás de um NAT ou firewall.

</div>

<div>

## <a name="topologies"></a>Topologia

O servidor de mediação do Lync Server 2013, por padrão, é posicionado com uma instância do registrador em um servidor de edição padrão, um pool de front-end ou um aparelho de ramificação sobreviventes. Todos os servidores de mediação em um pool Front-end devem ser configurados de maneira idêntica.

Onde o desempenho é um problema, pode ser preferível implantar um ou mais servidores de mediação em um pool autônomo dedicado. Ou, se você estiver implantando o entroncamento SIP, recomendamos que implante um pool autônomo do servidor de mediação.

Se você implantar conexões SIP diretas em um gateway PSTN qualificado que ofereça suporte ao bypass de mídia e ao balanceamento de carga de DNS, um pool autônomo do servidor de mediação não será necessário. Um pool autônomo do servidor de mediação não é necessário porque gateways qualificados são capazes de balanceamento de carga de DNS para um pool de servidores de mediação e podem receber tráfego de qualquer servidor de mediação em um pool.

Também recomendamos que você colocar o servidor de mediação em um pool de front-end quando tiver implantado PBXs de IP ou conectar-se a um controlador de borda de sessão (SBC) do provedor de servidor de telefonia pela Internet, contanto que qualquer uma das seguintes condições seja atendida:

  - O IP-PBX ou o SBC está configurado para receber tráfego de qualquer servidor de mediação no pool e pode rotear o tráfego uniformemente para todos os servidores de mediação no pool.

  - O IP-PBX não é compatível com o bypass de mídia, mas o pool de front-end que hospeda o servidor de mediação pode manipular a transcodificação de voz para chamadas para as quais o bypass de mídia não se aplica.

Você pode usar o Microsoft Lync Server 2013, ferramenta de planejamento para avaliar se o pool de front-ends em que você deseja colocar o servidor de mediação pode manipular a carga. Se o seu ambiente não puder atender a esses requisitos, você deve implantar um pool autônomo do servidor de mediação.

Para obter detalhes sobre qual topologia implantar, consulte [diretrizes de implantação para o servidor de mediação no Lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md).

A figura a seguir mostra uma topologia simples que consiste em dois locais conectados por um link WAN. O servidor de mediação está posicionado com o registrador em um pool de front-end no site 1. Os servidores de mediação no site 1 controlam o gateway PSTN no site 1 e o gateway no site 2. Nessa topologia, o bypass de mídia está habilitado globalmente para usar as informações do local e da região, e os troncos até cada gateway PSTN (GW1 e GW2) têm bypass habilitado.

**Exemplo de sites conectados por um link WAN com um Servidor de Mediação no Site 1 e um gateway PSTN no Site 2**

![Topologia de voz com gateway de WAN servidor de mediação] (images/Gg398537.67872e61-1444-447b-918c-abe89abc3004(OCS.15).jpg "Topologia de voz com gateway de WAN servidor de mediação")

A próxima figura mostra uma topologia simples em que o servidor de mediação está posicionado com o registrador no pool de front-end no site 1 e tem uma conexão SIP direta com o IP-PBX no site 1. Nesta figura, o servidor de mediação também controla um gateway PSTN no site 2. Suponha que os usuários do Lync existam nos dois locais: 1 e 2. Além disso, presumir que o IP-PBX tem um processador de mídia associado que deve ser percorrido por toda a mídia originada dos pontos de extremidade do Lync antes de ser enviada a pontos de extremidade de mídia controlados pelo IP-PBX. Nessa topologia, o bypass de mídia está habilitado globalmente para usar as informações do local e da região, e os troncos até o PBX e o gateway PSTN têm o bypass de mídia habilitado.

**Exemplo de sites conectados por um link WAN com um Servidor de Mediação no Site 1 e um PBX no Site 2**

![Wan Topology Mediation Server PBX PBX] (images/Gg398537.df6c8a5b-8431-4187-907d-ff5ca26eeeec(OCS.15).jpg "Wan Topology Mediation Server PBX PBX")

Para obter detalhes sobre o planejamento de topologias PBX, consulte [diretrizes de implantação para o servidor de mediação no Lync server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md) e [Opções de implantação do SIP direto no Lync Server 2013](lync-server-2013-direct-sip-deployment-options.md).

O último número neste tópico mostra uma topologia em que o servidor de mediação está conectado ao SBC de um provedor de serviços de telefonia pela Internet. Para obter detalhes sobre as topologias de tronco SIP, consulte [entroncamento SIP no Lync Server 2013](lync-server-2013-sip-trunking.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

