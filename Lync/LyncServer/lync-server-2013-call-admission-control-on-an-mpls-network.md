---
title: 'Lync Server 2013: controle de admissão de chamadas em uma rede MPLS'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call admission control on an MPLS network
ms:assetid: 0beec6be-2431-4255-a3d2-512dd030e66a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398168(v=OCS.15)
ms:contentKeyID: 48183387
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8da29eb8825154f3e149d56b6bd9e4c4e7452652
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043993"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-admission-control-on-an-mpls-network-with-lync-server-2013"></a><span data-ttu-id="792c1-102">Controle de admissão de chamadas em uma rede MPLS com o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="792c1-102">Call admission control on an MPLS network with Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="792c1-103">_**Última modificação do tópico:** 2012-09-22_</span><span class="sxs-lookup"><span data-stu-id="792c1-103">_**Topic Last Modified:** 2012-09-22_</span></span>

<span data-ttu-id="792c1-p101">Em uma rede de Comutação de Rótulo Multiprotocolo (MPLS), todos os sites são conectados por uma malha completa. Isto é, todos os sites são conectados diretamente à nuvem MPLS, e cada site é provisionado com largura de banda a ser usada em um link WAN para a nuvem MPLS. Não existe hub de rede nem local central para controlar o roteamento IP. A figura abaixo mostra uma rede simples com base na tecnologia MPLS.</span><span class="sxs-lookup"><span data-stu-id="792c1-p101">In a Multiprotocol Label Switching (MPLS) network, all sites are connected by a full-mesh. That is, all sites are connected directly to the MPLS backbone of the Internet service provider, and each site is provisioned bandwidth to be used across a WAN link to the MPLS cloud. There is no network hub or central site to control IP routing. The following figure shows a simple network based on MPLS technology.</span></span>

<span data-ttu-id="792c1-108">**Exemplo de rede MPLS**</span><span class="sxs-lookup"><span data-stu-id="792c1-108">**Example MPLS network**</span></span>

<span data-ttu-id="792c1-109">![CAC com MPLS](images/Gg398168.54602e6e-ec11-4dae-936d-b01acda8a179(OCS.15).jpg "CAC com MPLS")</span><span class="sxs-lookup"><span data-stu-id="792c1-109">![CAC with MPLS](images/Gg398168.54602e6e-ec11-4dae-936d-b01acda8a179(OCS.15).jpg "CAC with MPLS")</span></span>

<span data-ttu-id="792c1-p102">Para implantar um controle de admissão de chamada (CAC) em uma rede MPLS, é preciso criar uma região de rede para representar a nuvem MPLS, bem como criar um site de rede para representar cada site de satélite MPLS. A figura a seguir ilustra como a região de rede e os sites de rede devem ser configurados para representar a rede MPLS de exemplo na figura anterior. Os limites gerais da largura de banda e os limites de sessão da largura de banda têm base na capacidade do link WAN a partir de cada site de rede até a região de rede que representa a nuvem MPLS.</span><span class="sxs-lookup"><span data-stu-id="792c1-p102">To deploy call admission control (CAC) in an MPLS network, you create a network region to represent the MPLS cloud, and create a network site to represent each MPLS satellite site. The following figure illustrates how the network region and network sites should be configured to represent the example MPLS network in the previous figure. The overall bandwidth limits and bandwidth session limits are then based on the capacity of the WAN link from each network site to the network region that represents the MPLS cloud.</span></span>

<span data-ttu-id="792c1-113">**Região de rede e sites de rede para uma rede MPLS**</span><span class="sxs-lookup"><span data-stu-id="792c1-113">**Network region and network sites for an MPLS network**</span></span>

<span data-ttu-id="792c1-114">![Controle de admissão de chamadas (CAC) com diagrama MPLS](images/Gg398168.f8f76283-5c0c-4133-8a78-3fbbfd016dc4(OCS.15).jpg "Controle de admissão de chamadas (CAC) com diagrama MPLS")</span><span class="sxs-lookup"><span data-stu-id="792c1-114">![Call Admission Control (CAC) with MPLS diagram](images/Gg398168.f8f76283-5c0c-4133-8a78-3fbbfd016dc4(OCS.15).jpg "Call Admission Control (CAC) with MPLS diagram")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

