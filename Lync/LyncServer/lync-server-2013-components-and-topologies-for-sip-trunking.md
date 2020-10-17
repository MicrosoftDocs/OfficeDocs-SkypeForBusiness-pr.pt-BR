---
title: 'Lync Server 2013: componentes e topologias para tronco SIP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components and topologies for SIP trunking
ms:assetid: 8ed9a9d0-517e-4f36-a131-22cdafa257fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398720(v=OCS.15)
ms:contentKeyID: 48184775
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 08961982f382e5b5c670f6a1640884a4540a4c20
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502488"
---
# <a name="components-and-topologies-for-sip-trunking-in-lync-server-2013"></a>Componentes e topologias para tronco SIP no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-21_

A figura a seguir ilustra a topologia de tronco SIP no Lync Server.

**Topologia de tronco SIP**

![Topologia de tronco SIP](images/Gg398720.669fb55d-7c81-4e21-9421-fabc43d6e064(OCS.15).jpg "Topologia de tronco SIP")

Conforme mostrado no diagrama, uma rede virtual privada (VPN) de IP é usada para conectividade entre a rede corporativa e o provedor de serviços PSTN (rede telefônica pública comutada). A finalidade dessa rede privada é fornecer conectividade IP, aumentar a segurança e (opcionalmente) obter garantias de qualidade de serviço (QoS). Devido à natureza de uma VPN, não é necessário usar o protocolo TLS (Transport Layer Security) para o tráfego de sinalização SIP ou SRTP (Secure real-time Transport Protocol) para o tráfego de mídia. As conexões entre a empresa e o provedor de serviços consistem em conexões TCP simples para SIP e RTP (protocolo de transporte em tempo real) simples (via UDP) para mídia encapsulada por meio de uma VPN IP. Certifique-se de que todos os firewalls entre os roteadores VPN tenham portas abertas para permitir que os roteadores VPN se comuniquem e que os endereços IP nas bordas externas dos roteadores VPN sejam roteáveis publicamente.

<div>


> [!IMPORTANT]  
> Entre em contato com seu provedor de serviços para determinar se ele oferece suporte para alta disponibilidade, incluindo failover. Em caso afirmativo, será necessário determinar os procedimentos para configurá-lo. Por exemplo, você precisa configurar apenas um endereço IP e um tronco SIP em cada servidor de mediação ou precisa configurar vários troncos SIP em cada servidor de mediação?<BR>Se você tiver vários sites centrais, verifique também se o provedor de serviços tem a capacidade de habilitar conexões de e para outro site central.



</div>

<div>


> [!NOTE]  
> Para troncos SIP, é altamente recomendável implantar servidores de mediação autônomos. Para obter detalhes, consulte <A href="lync-server-2013-deploying-mediation-servers-and-defining-peers.md">Deploying Mediation Servers and define Peers in Lync Server 2013</A> na documentação de implantação.



</div>

<div>

## <a name="securing-the-mediation-server-for-sip-trunking"></a>Protegendo o servidor de mediação para tronco SIP

Para fins de segurança, você deve configurar uma VLAN (LAN virtual) para cada conexão entre os dois roteadores VPN. O processo real para configurar uma VLAN varia de um fabricante de roteador para outro. Para obter detalhes, entre em contato com o fornecedor do roteador.

Recomendamos que você siga estas diretrizes:

  - Configure uma LAN virtual (VLAN) entre o servidor de mediação e o roteador VPN na rede de perímetro (também conhecida como DMZ, zona desmilitarizada e sub-rede filtrada).

  - Não permita que pacotes de difusão ou multicast sejam transferidos do roteador para a VLAN.

  - Bloquear qualquer regra de roteamento que roteia o tráfego do roteador para qualquer lugar, exceto o servidor de mediação.

Se você usar um servidor VPN, recomendamos seguir estas diretrizes:

  - Configure uma VLAN entre o servidor VPN e o servidor de mediação.

  - Não permita que pacotes de difusão ou multicast sejam transmitidos do servidor VPN para a VLAN.

  - Bloquear qualquer regra de roteamento que roteia o tráfego do servidor VPN para qualquer lugar, exceto o servidor de mediação.

  - Criptografe os dados na VPN usando o GRE (encapsulamento de roteamento genérico).

</div>

</div>

<span> </span>

</div>

</div>

</div>

