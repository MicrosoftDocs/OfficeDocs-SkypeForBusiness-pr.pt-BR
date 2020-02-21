---
title: 'Lync Server 2013: componente do servidor de mediação'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Mediation Server component
ms:assetid: 5b19edef-4a54-43c9-aa12-5643b8108355
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398399(v=OCS.15)
ms:contentKeyID: 48184239
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2c068e284e871caf5848ba9616f8bf7afa380b49
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42185174"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="mediation-server-component-in-lync-server-2013"></a>Componente do servidor de mediação no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-21_

Você deve implantar o Lync Server 2013, servidor de mediação se implantar a carga de trabalho do Enterprise Voice. Esta seção descreve a funcionalidade básica, as dependências, as topologias básicas e as diretrizes de planejamento.

O servidor de mediação converte a sinalização e, em algumas configurações, mídia entre sua infraestrutura interna do Lync Server 2013, Enterprise Voice e um gateway PSTN (rede telefônica pública comutada) ou um tronco SIP (protocolo de iniciação de sessão). No Lync Server 2013 Side, o servidor de mediação escuta em um único endereço de transporte de protocolo universal (MTLS) mútuo. No lado do gateway, o Servidor de Mediação escuta em todas as portas de escuta associadas a troncos definidos no documento da topologia. Todos os gateways qualificados devem oferecer suporte a TLS, mas também podem habilitar TCP. TCP tem suporte em gateways que não oferecem suporte a TLS.

Se você também tiver um PBX (Public Branch Exchange) existente em seu ambiente, o servidor de mediação tratará as chamadas entre os usuários do Enterprise Voice e o PBX. Se seu PBX for um IP-PBX, você poderá criar uma conexão SIP direta entre o PBX e o servidor de mediação. Se seu PBX for um PBX TDM (Time Division multiplex), você também deverá implantar um gateway PSTN entre o servidor de mediação e o PBX.

Por padrão, o servidor de mediação é colocado com o servidor front-end. O servidor de mediação também pode ser implantado em um pool autônomo por motivos de desempenho, ou se você implantar o tronco SIP, caso em que o pool autônomo seja altamente recomendado.

Se você implantar conexões SIP diretas com um gateway PSTN qualificado que oferece suporte a bypass de mídia e balanceamento de carga DNS, um pool do Servidor de Mediação autônomo não será necessário. Um pool de Servidores de Mediação autônomo não é necessário, pois os gateways qualificados são capazes de balanceamento de carga DNS para um pool de Servidores de Mediação e podem receber tráfego de qualquer Servidor de Mediação em um pool.

Também recomendamos que você posicione o Servidor de Mediação em um pool Front-End após implantar o IP-PBXs ou se conectar ao controlador de borda da sessão (SBC) de um Internet Telephony Server Provider, contanto que qualquer uma das seguintes condições seja atendida:

  - O IP-PBX ou SBC está configurado para receber tráfego de qualquer Servidor de Mediação no pool e pode rotear tráfego uniformemente para todos os Servidores de Mediação no pool.

  - O IP-PBX não suporta bypass de mídia, mas o pool de front-ends que está hospedando o servidor de mediação pode lidar com a transcodificação de voz para chamadas às quais o bypass de mídia não se aplica.

Você pode usar a ferramenta de planejamento do Microsoft Lync Server 2013 para avaliar se o pool de front-ends onde você deseja colocar o servidor de mediação pode lidar com a carga. Se o seu ambiente não pode cumprir estes requisitos, você deve implantar um pool do Servidor de Mediação autônomo.

As principais funções do servidor de mediação são as seguintes:

  - Criptografar e descriptografar SRTP no lado do Lync Server

  - Conversão do SIP em TCP (para gateways que não oferecem suporte a TLS) para SIP em MTLS (TLS mútuo)

  - Conversão de fluxos de mídia entre o Lync Server e o par de gateway do servidor de mediação

  - Conexão de clientes externos à rede com componentes internos de ICE, que permitem a passagem de NATs e firewalls.

  - Atuar como um intermediário para fluxos de chamadas aos quais um gateway não oferece suporte, como chamadas de trabalhadores remotos em um cliente do Enterprise Voice

  - Em implantações que incluem tronco SIP, trabalho conjunto com o provedor de serviços de tronco SIP para oferecer suporte à PSTN, o que elimina a necessidade de um gateway PSTN

A figura a seguir mostra os protocolos de sinalização e de mídia usados pelo servidor de mediação ao se comunicar com um gateway PSTN básico e a infraestrutura Enterprise Voice.

**Protocolos de sinalização e a mídia usados pelo Servidor de Mediação**

![Diagrama de protocolos de servidor de mediação](images/Gg398399.c3d39ba0-e323-4a58-8f07-4e80d3278af2(OCS.15).jpg "Diagrama de protocolos de servidor de mediação")

<div>


> [!NOTE]  
> Se você estiver usando TCP ou RTP/RTCP (em vez de SRTP ou SRTCP) na rede entre o gateway PSTN e o servidor de mediação, recomendamos que você faça medidas para ajudar a garantir a segurança e a privacidade da rede.



</div>

<div>

## <a name="in-this-section"></a>Nesta seção

  - [Tronco M:N no Lync Server 2013](lync-server-2013-m-n-trunk.md)

  - [Controle de admissão de chamadas e servidor de mediação no Lync Server 2013](lync-server-2013-call-admission-control-and-mediation-server.md)

  - [Enhanced 9-1-1 (E9-1-1) e servidor de mediação no Lync Server 2013](lync-server-2013-enhanced-9-1-1-e9-1-1-and-mediation-server.md)

  - [Bypass de mídia e servidor de mediação no Lync Server 2013](lync-server-2013-media-bypass-and-mediation-server.md)

  - [Componentes e topologias para o servidor de mediação no Lync Server 2013](lync-server-2013-components-and-topologies-for-mediation-server.md)

  - [Diretrizes de implantação para o servidor de mediação no Lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

