---
title: 'Lync Server 2013: Componentes e topologias para tronco SIP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Components and topologies for SIP trunking
ms:assetid: 8ed9a9d0-517e-4f36-a131-22cdafa257fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398720(v=OCS.15)
ms:contentKeyID: 48184775
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dc1b80078f942f3f70957a7af6b27b7dd9210046
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836509"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-sip-trunking-in-lync-server-2013"></a>Componentes e topologias para tronco SIP no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-21_

A figura a seguir ilustra a topologia de entroncamento SIP no Lync Server.

**Topologia de troncos SIP**

![Topologia de entroncamento SIP] (images/Gg398720.669fb55d-7c81-4e21-9421-fabc43d6e064(OCS.15).jpg "Topologia de entroncamento SIP")

Conforme mostra o diagrama, uma VPN (rede virtual privada) IP é usada para a conectividade entre a rede corporativa e o provedor de serviços da rede de telefonia pública comutada (PSTN). O objetivo desta rede privada é fornecer conectividade IP, aprimorar a segurança e (opcionalmente) obter garantias de qualidade de serviços (QoS). Devido à natureza de uma VPN, não é necessário usar protocolo TLS para o tráfego de sinalização SIP ou SRTP para tráfego de mídia.  As conexões entre a empresa e o provedor de serviços consistem, portanto, em conexões TCP básicas para SIP e RTP básico (via protocolo UDP) em mídia encapsulada através de uma VPN IP. Certifique-se de que todos os firewalls entre os roteadores VPN possuem portas abertas para permitir a comunicação e que os endereços IP nas bordas externas dos roteadores VPN sejam roteáveis publicamente.

<div>


> [!IMPORTANT]  
> Contate seu provedor de serviços para determinar se ele oferece suporte para alta disponibilidade, incluindo failover. Em caso positivo, você precisará determinar os procedimentos para configurá-lo. Por exemplo, você precisa configurar apenas um endereço IP e um tronco SIP em cada servidor de mediação ou precisa configurar vários troncos SIP em cada servidor de mediação?<BR>Se você tiver vários sites centrais, verifique também se o provedor de serviço tem a capacidade de habilitar conexões para e de outro site central.



</div>

<div>


> [!NOTE]  
> Para o entroncamento SIP, é altamente recomendável implantar servidores de mediação autônomos. Para obter detalhes, consulte <A href="lync-server-2013-deploying-mediation-servers-and-defining-peers.md">implantação de servidores de mediação e definição de pares no Lync Server 2013</A> na documentação de implantação.



</div>

<div>

## <a name="securing-the-mediation-server-for-sip-trunking"></a>Como proteger o Servidor de Mediação para troncos SIP

Para fins de segurança, você deve configurar uma LAN virtual (VLAN) para cada conexão entre os dois roteadores VPN. O processo real para configurar uma VLAN varia de um fabricante de roteador para outro. Para detalhes, entre em contato com o fornecedor do seu roteador.

É recomendável seguir estas diretrizes:

  - Configure uma VLAN (LAN virtual) entre o servidor de mediação e o roteador VPN na rede de perímetro (também conhecido como DMZ, zona desmilitarizada e sub-rede filtrada).

  - Não permita que pacotes de transmissão ou multicast sejam transferidos do roteador para a VLAN.

  - Bloqueie todas as regras de roteamento que roteiam o tráfego do roteador para qualquer lugar, mas o servidor de mediação.

Se você usa um servidor VPN, é recomendável seguir as seguintes diretrizes:

  - Configurar uma VLAN entre o servidor VPN e o servidor de mediação.

  - Não permita que pacotes de transmissão ou multicast sejam transferidos do servidor VPN para a VLAN.

  - Bloqueie qualquer regra de roteamento que roteia o tráfego do servidor VPN para qualquer lugar, mas o servidor de mediação.

  - Criptografe dados na VPN usando GRE (encapsulamento de roteamento genérico).

</div>

</div>

<span> </span>

</div>

</div>

</div>

