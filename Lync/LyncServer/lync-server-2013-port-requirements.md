---
title: Requisitos de porta do Lync Server 2013
description: Requisitos de porta do Lync Server 2013.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port requirements
ms:assetid: 9a6c1300-ef88-4181-a8f1-43cd3093962b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398798(v=OCS.15)
ms:contentKeyID: 48184886
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ba7ae9a1ee098f55c61ae476f12c3b856c69f90e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543157"
---
# <a name="port-requirements-for-lync-server-2013"></a><span data-ttu-id="dd6bc-103">Requisitos de porta para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dd6bc-103">Port requirements for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dd6bc-104">_**Última modificação do tópico:** 2013-03-27_</span><span class="sxs-lookup"><span data-stu-id="dd6bc-104">_**Topic Last Modified:** 2013-03-27_</span></span>

<span data-ttu-id="dd6bc-105">O Lync Server requer que determinadas portas no firewall estejam abertas.</span><span class="sxs-lookup"><span data-stu-id="dd6bc-105">Lync Server requires that specific ports on the firewall be open.</span></span> <span data-ttu-id="dd6bc-106">Além disso, se a segurança do protocolo Internet (IPsec) for implantada em sua organização, o IPsec deverá ser desabilitado no intervalo de portas usadas para a entrega de áudio, vídeo e vídeo panorâmico.</span><span class="sxs-lookup"><span data-stu-id="dd6bc-106">Additionally, if Internet Protocol security (IPsec) is deployed in your organization, IPsec must be disabled over the range of ports used for the delivery of audio, video, and panorama video.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="dd6bc-107">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="dd6bc-107">In This Section</span></span>

<span data-ttu-id="dd6bc-108">Esta seção inclui os seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="dd6bc-108">This section includes the following topics:</span></span>

  - [<span data-ttu-id="dd6bc-109">Portas e protocolos para servidores internos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dd6bc-109">Ports and protocols for internal servers in Lync Server 2013</span></span>](lync-server-2013-ports-and-protocols-for-internal-servers.md)

  - [<span data-ttu-id="dd6bc-110">Exceções de IPsec no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dd6bc-110">IPsec exceptions in Lync Server 2013</span></span>](lync-server-2013-ipsec-exceptions.md)

  - [<span data-ttu-id="dd6bc-111">Resumo de porta-borda consolidada única com endereços IP privados usando NAT no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dd6bc-111">Port summary - Single consolidated edge with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-port-summary-single-consolidated-edge-with-private-ip-addresses-using-nat.md)

  - [<span data-ttu-id="dd6bc-112">Resumo de porta-borda consolidada única com endereços IP públicos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dd6bc-112">Port summary - Single consolidated edge with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-port-summary-single-consolidated-edge-with-public-ip-addresses.md)

  - [<span data-ttu-id="dd6bc-113">Resumo de porta-borda consolidada em escala, balanceamento de carga de DNS com endereços IP privados usando NAT no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dd6bc-113">Port summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-port-summary-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

  - [<span data-ttu-id="dd6bc-114">Resumo de porta-borda consolidada em escala, balanceamento de carga de DNS com endereços IP públicos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dd6bc-114">Port summary - Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-port-summary-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)

  - [<span data-ttu-id="dd6bc-115">Resumo de porta-borda consolidada em escala com balanceadores de carga de hardware no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dd6bc-115">Port summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>](lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)

  - [<span data-ttu-id="dd6bc-116">Resumo de porta-proxy reverso no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dd6bc-116">Port summary - Reverse proxy in Lync Server 2013</span></span>](lync-server-2013-port-summary-reverse-proxy.md)

  - [<span data-ttu-id="dd6bc-117">Resumo de porta-SIP, Federação XMPP e mensagens instantâneas públicas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dd6bc-117">Port summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-port-summary-sip-xmpp-federation-and-public-instant-messaging.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

