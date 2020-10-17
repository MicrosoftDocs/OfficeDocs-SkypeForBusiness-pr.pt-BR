---
title: 'Lync Server 2013: tronco SIP'
description: 'Lync Server 2013: tronco SIP.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SIP trunking
ms:assetid: 7c586401-d0e5-4017-b3e1-fe5e7f8fc6db
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398619(v=OCS.15)
ms:contentKeyID: 48184615
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 60b68d9d0400c87de2832d7fe7bdabe4057ec47a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559007"
---
# <a name="sip-trunking-in-lync-server-2013"></a><span data-ttu-id="878a7-103">Tronco SIP no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="878a7-103">SIP trunking in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="878a7-104">_**Última modificação do tópico:** 2012-08-13_</span><span class="sxs-lookup"><span data-stu-id="878a7-104">_**Topic Last Modified:** 2012-08-13_</span></span>

<span data-ttu-id="878a7-p101">O SIP é usado para iniciar e gerenciar sessões de comunicações de VoIP (voz sobre IP) para o serviço telefônico básico e para vários serviços de comunicação em tempo real adicionais, como serviços de mensagens instantâneas, conferência, detecção de presença e multimídia. Esta seção oferece informações de planejamento para a implementação de *troncos SIP*, um tipo de conexão SIP que se estende além do limite da rede local.</span><span class="sxs-lookup"><span data-stu-id="878a7-p101">Session Initiation Protocol (SIP) is used to initiate and manage Voice over IP (VoIP) communications sessions for basic telephone service and for additional real-time communication services, such as instant messaging, conferencing, presence detection, and multimedia. This section provides planning information for implementing *SIP trunks*, a type of SIP connection that extends beyond the boundary of your local network.</span></span>

<div>

## <a name="what-is-sip-trunking"></a><span data-ttu-id="878a7-107">O que é o tronco SIP?</span><span class="sxs-lookup"><span data-stu-id="878a7-107">What is SIP Trunking?</span></span>

<span data-ttu-id="878a7-p102">Um tronco SIP é uma conexão do IP estabelece um vínculo de comunicações SIP entre sua organização e um provedor de serviços de telefonia de Internet (ITSP), além do firewall. Normalmente, um tronco SIP é usado para conectar o site central da organização a um ITSP. Em alguns casos, você também pode optar por usar um tronco SIP para conectar o site da filial a um ITSP.</span><span class="sxs-lookup"><span data-stu-id="878a7-p102">A SIP trunk is an IP connection that establishes a SIP communications link between your organization and an Internet telephony service provider (ITSP) beyond your firewall. Typically, a SIP trunk is used to connect your organization’s central site to an ITSP. In some cases, you may also opt to use SIP trunking to connect your branch site to an ITSP.</span></span>

<div>

## <a name="sip-trunks-vs-direct-sip-connections"></a><span data-ttu-id="878a7-111">Troncos SIP vs. Conexões diretas do cabo SIP</span><span class="sxs-lookup"><span data-stu-id="878a7-111">SIP Trunks vs. Direct SIP Connections</span></span>

<span data-ttu-id="878a7-112">O termo \*tronco \* deriva da tecnologia de comutação de circuitos.</span><span class="sxs-lookup"><span data-stu-id="878a7-112">The term *trunk* is derived from circuit-switched technology.</span></span> <span data-ttu-id="878a7-113">Refere-se a uma linha física dedicada que conecta o equipamento de comutação telefônica.</span><span class="sxs-lookup"><span data-stu-id="878a7-113">It refers to a dedicated physical line that connects telephone switching equipment.</span></span> <span data-ttu-id="878a7-114">Assim como seus troncos do predecessor, a multiplexação de divisão de tempo (TDM), os troncos SIP são conexões entre duas redes SIP separadas, o Lync Server 2013 Enterprise e o ITSP.</span><span class="sxs-lookup"><span data-stu-id="878a7-114">Like their predecessor, time division multiplexing (TDM) trunks, SIP trunks are connections between two separate SIP networks—the Lync Server 2013 enterprise and the ITSP.</span></span> <span data-ttu-id="878a7-115">Diferentemente dos troncos de comutação de circuitos, os troncos SIP são conexões virtuais que podem ser estabelecidas sobre qualquer tipo de conexão de troncos SIP compatíveis.</span><span class="sxs-lookup"><span data-stu-id="878a7-115">Unlike circuit-switched trunks, SIP trunks are virtual connections that can be established over any of the supported SIP trunking connection types.</span></span> <span data-ttu-id="878a7-116">Para obter detalhes sobre os tipos de conexão suportados, consulte [como implementar o tronco SIP no Lync Server 2013?](lync-server-2013-how-do-i-implement-sip-trunking.md).</span><span class="sxs-lookup"><span data-stu-id="878a7-116">For details about the supported connection types, see [How do I implement SIP trunking in Lync Server 2013?](lync-server-2013-how-do-i-implement-sip-trunking.md).</span></span>

<span data-ttu-id="878a7-117">As conexões SIP diretas, por outro lado, são conexões de SIP que não atravessam o limite de rede local (ou seja, elas se conectam a um gateway PSTN ou PBX dentro de sua rede interna).</span><span class="sxs-lookup"><span data-stu-id="878a7-117">Direct SIP connections, on the other hand, are SIP connections that do not cross the local network boundary (that is, they connect to a public switched telephone network (PSTN) gateway or private branch exchange (PBX) within your internal network).</span></span> <span data-ttu-id="878a7-118">Para obter detalhes sobre como você pode usar as conexões SIP diretas com o Lync Server 2013, consulte [Direct SIP Connections in Lync server 2013](lync-server-2013-direct-sip-connections.md).</span><span class="sxs-lookup"><span data-stu-id="878a7-118">For details about how you can use direct SIP connections with Lync Server 2013, see [Direct SIP connections in Lync Server 2013](lync-server-2013-direct-sip-connections.md).</span></span>

</div>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="878a7-119">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="878a7-119">In This Section</span></span>

  - [<span data-ttu-id="878a7-120">Visão geral do tronco SIP no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="878a7-120">Overview of SIP trunking in Lync Server 2013</span></span>](lync-server-2013-overview-of-sip-trunking.md)

  - [<span data-ttu-id="878a7-121">Como faço para implementar o tronco SIP no Lync Server 2013?</span><span class="sxs-lookup"><span data-stu-id="878a7-121">How do I implement SIP trunking in Lync Server 2013?</span></span>](lync-server-2013-how-do-i-implement-sip-trunking.md)

  - [<span data-ttu-id="878a7-122">Componentes e topologias para tronco SIP no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="878a7-122">Components and topologies for SIP trunking in Lync Server 2013</span></span>](lync-server-2013-components-and-topologies-for-sip-trunking.md)

  - [<span data-ttu-id="878a7-123">Tronco SIP do site de filial no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="878a7-123">Branch site SIP trunking in Lync Server 2013</span></span>](lync-server-2013-branch-site-sip-trunking.md)

  - [<span data-ttu-id="878a7-124">Lista de verificação de implantação de tronco SIP para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="878a7-124">SIP trunk deployment checklist for Lync Server 2013</span></span>](lync-server-2013-sip-trunk-deployment-checklist.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

