---
title: 'Lync Server 2013: componente do servidor de mediação'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Mediation Server component
ms:assetid: 5b19edef-4a54-43c9-aa12-5643b8108355
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398399(v=OCS.15)
ms:contentKeyID: 48184239
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a1f3476f8b4e99b2abccb67f1d75446a126df03d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827225"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mediation-server-component-in-lync-server-2013"></a>Componente servidor de mediação no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-21_

Você deve implantar o Lync Server 2013, o servidor de mediação se implantar a carga de trabalho do Enterprise Voice. Esta seção descreve funcionalidade básica, dependências, topologias básicas e diretrizes de planejamento.

O servidor de mediação traduz a sinalização e, em algumas configurações, mídia entre a sua rede do Lync Server 2013, a infraestrutura do Enterprise Voice e um gateway de rede telefônica pública comutada (PSTN) ou um tronco de protocolo de iniciação de sessão (SIP). Na 2013 do Lync Server, o servidor de mediação escuta em um único endereço de transporte de protocolo NNTP (MTLS) mútuo. No lado do gateway, o servidor de mediação escuta todas as portas de escuta associadas a troncos definidas no documento de topologia. Todos os gateways qualificados devem dar suporte a TLS, mas também podem habilitar o TCP. O TCP é aceito para gateways que não dão suporte a TLS.

Se você também tiver um PBX (Exchange Branch Exchange) existente em seu ambiente, o servidor de mediação manipulará chamadas entre usuários do Enterprise Voice e o PBX. Se o seu PBX for um PBX IP, você poderá criar uma conexão SIP direta entre o PBX e o servidor de mediação. Se o seu PBX for um PBX TDM (Time Division multiplex), você também deve implantar um gateway PSTN entre o servidor de mediação e o PBX.

O servidor de mediação é posicionado com o servidor front-end por padrão. O servidor de mediação também pode ser implantado em um pool autônomo por motivos de desempenho, ou se você implantar o entroncamento SIP, caso em que o pool autônomo seja altamente recomendado.

Se você implantar conexões SIP diretas em um gateway PSTN qualificado que ofereça suporte ao bypass de mídia e ao balanceamento de carga de DNS, um pool autônomo do servidor de mediação não será necessário. Um pool autônomo do servidor de mediação não é necessário porque gateways qualificados são capazes de balanceamento de carga de DNS para um pool de servidores de mediação e podem receber tráfego de qualquer servidor de mediação em um pool.

Também recomendamos que você colocar o servidor de mediação em um pool de front-end quando tiver implantado PBXs de IP ou conectar-se a um controlador de borda de sessão (SBC) do provedor de servidor de telefonia pela Internet, contanto que qualquer uma das seguintes condições seja atendida:

  - O IP-PBX ou o SBC está configurado para receber tráfego de qualquer servidor de mediação no pool e pode rotear o tráfego uniformemente para todos os servidores de mediação no pool.

  - O IP-PBX não é compatível com o bypass de mídia, mas o pool de front-end que hospeda o servidor de mediação pode manipular a transcodificação de voz para chamadas para as quais o bypass de mídia não se aplica.

Você pode usar o Microsoft Lync Server 2013, ferramenta de planejamento para avaliar se o pool de front-ends em que você deseja colocar o servidor de mediação pode manipular a carga. Se o seu ambiente não puder atender a esses requisitos, você deve implantar um pool autônomo do servidor de mediação.

As principais funções do servidor de mediação são as seguintes:

  - Criptografar e descriptografar SRTP no lado do Lync Server

  - Convertendo SIP via TCP (para gateways que não são compatíveis com TLS) para SIP em TLS mútuo

  - Traduzir fluxos de mídia entre o Lync Server e o peer do gateway do servidor de mediação

  - Conectando clientes que estão fora da rede para componentes ICE internos, que permitem a passagem de mídia de NAT e firewalls

  - Atuar como intermediário para fluxos de chamadas aos quais um gateway não oferece suporte, como chamadas de trabalhadores remotos em um cliente Enterprise Voice

  - Em implantações que incluem entroncamento SIP, trabalhando com o provedor de serviço de entroncamento SIP para fornecer suporte a PSTN, o que elimina a necessidade de um gateway PSTN

A figura a seguir mostra os protocolos de sinalização e mídia usados pelo servidor de mediação durante a comunicação com um gateway PSTN básico e com a infraestrutura Enterprise Voice.

**Protocolos de sinalização e a mídia usados pelo Servidor de Mediação**

![Diagrama de protocolos do servidor] de mediação (images/Gg398399.c3d39ba0-e323-4a58-8f07-4e80d3278af2(OCS.15).jpg "Diagrama de protocolos do servidor") de mediação

<div>


> [!NOTE]  
> Se você estiver usando TCP ou RTP/RTCP (em vez do SRTP ou SRTCP) na rede entre o gateway PSTN e o servidor de mediação, recomendamos que você tome medidas para ajudar a garantir a segurança e a privacidade da rede.



</div>

<div>

## <a name="in-this-section"></a>Nesta seção

  - [Tronco M:N no Lync Server 2013](lync-server-2013-m-n-trunk.md)

  - [Controle de admissão de chamada e Servidor de Mediação no Lync Server 2013](lync-server-2013-call-admission-control-and-mediation-server.md)

  - [9-1-1 Avançado (E9-1-1) e Servidor de Mediação no Lync Server 2013](lync-server-2013-enhanced-9-1-1-e9-1-1-and-mediation-server.md)

  - [Bypass de mídia e Servidor de Mediação no Lync Server 2013](lync-server-2013-media-bypass-and-mediation-server.md)

  - [Componentes e topologias para o Servidor de Mediação no Lync Server 2013](lync-server-2013-components-and-topologies-for-mediation-server.md)

  - [Diretrizes de implantação para o servidor de mediação no Lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

