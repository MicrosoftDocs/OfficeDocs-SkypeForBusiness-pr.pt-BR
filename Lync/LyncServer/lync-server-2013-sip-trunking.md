---
title: 'Lync Server 2013: tronco SIP'
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
ms.openlocfilehash: fe2ea13628e9a4ede3daa2b14ebbb3941ce30aa1
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038982"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sip-trunking-in-lync-server-2013"></a><span data-ttu-id="13bde-102">Tronco SIP no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="13bde-102">SIP trunking in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="13bde-103">_**Última modificação do tópico:** 2012-08-13_</span><span class="sxs-lookup"><span data-stu-id="13bde-103">_**Topic Last Modified:** 2012-08-13_</span></span>

<span data-ttu-id="13bde-p101">O SIP é usado para iniciar e gerenciar sessões de comunicações de VoIP (voz sobre IP) para o serviço telefônico básico e para vários serviços de comunicação em tempo real adicionais, como serviços de mensagens instantâneas, conferência, detecção de presença e multimídia. Esta seção oferece informações de planejamento para a implementação de *troncos SIP*, um tipo de conexão SIP que se estende além do limite da rede local.</span><span class="sxs-lookup"><span data-stu-id="13bde-p101">Session Initiation Protocol (SIP) is used to initiate and manage Voice over IP (VoIP) communications sessions for basic telephone service and for additional real-time communication services, such as instant messaging, conferencing, presence detection, and multimedia. This section provides planning information for implementing *SIP trunks*, a type of SIP connection that extends beyond the boundary of your local network.</span></span>

<div>

## <a name="what-is-sip-trunking"></a><span data-ttu-id="13bde-106">O que é o tronco SIP?</span><span class="sxs-lookup"><span data-stu-id="13bde-106">What is SIP Trunking?</span></span>

<span data-ttu-id="13bde-p102">Um tronco SIP é uma conexão do IP estabelece um vínculo de comunicações SIP entre sua organização e um provedor de serviços de telefonia de Internet (ITSP), além do firewall. Normalmente, um tronco SIP é usado para conectar o site central da organização a um ITSP. Em alguns casos, você também pode optar por usar um tronco SIP para conectar o site da filial a um ITSP.</span><span class="sxs-lookup"><span data-stu-id="13bde-p102">A SIP trunk is an IP connection that establishes a SIP communications link between your organization and an Internet telephony service provider (ITSP) beyond your firewall. Typically, a SIP trunk is used to connect your organization’s central site to an ITSP. In some cases, you may also opt to use SIP trunking to connect your branch site to an ITSP.</span></span>

<div>

## <a name="sip-trunks-vs-direct-sip-connections"></a><span data-ttu-id="13bde-110">Troncos SIP vs. Conexões diretas do cabo SIP</span><span class="sxs-lookup"><span data-stu-id="13bde-110">SIP Trunks vs. Direct SIP Connections</span></span>

<span data-ttu-id="13bde-111">O termo \*tronco \* deriva da tecnologia de comutação de circuitos.</span><span class="sxs-lookup"><span data-stu-id="13bde-111">The term *trunk* is derived from circuit-switched technology.</span></span> <span data-ttu-id="13bde-112">Refere-se a uma linha física dedicada que conecta o equipamento de comutação telefônica.</span><span class="sxs-lookup"><span data-stu-id="13bde-112">It refers to a dedicated physical line that connects telephone switching equipment.</span></span> <span data-ttu-id="13bde-113">Assim como seus troncos do predecessor, a multiplexação de divisão de tempo (TDM), os troncos SIP são conexões entre duas redes SIP separadas, o Lync Server 2013 Enterprise e o ITSP.</span><span class="sxs-lookup"><span data-stu-id="13bde-113">Like their predecessor, time division multiplexing (TDM) trunks, SIP trunks are connections between two separate SIP networks—the Lync Server 2013 enterprise and the ITSP.</span></span> <span data-ttu-id="13bde-114">Diferentemente dos troncos de comutação de circuitos, os troncos SIP são conexões virtuais que podem ser estabelecidas sobre qualquer tipo de conexão de troncos SIP compatíveis.</span><span class="sxs-lookup"><span data-stu-id="13bde-114">Unlike circuit-switched trunks, SIP trunks are virtual connections that can be established over any of the supported SIP trunking connection types.</span></span> <span data-ttu-id="13bde-115">Para obter detalhes sobre os tipos de conexão suportados, consulte [como implementar o tronco SIP no Lync Server 2013?](lync-server-2013-how-do-i-implement-sip-trunking.md).</span><span class="sxs-lookup"><span data-stu-id="13bde-115">For details about the supported connection types, see [How do I implement SIP trunking in Lync Server 2013?](lync-server-2013-how-do-i-implement-sip-trunking.md).</span></span>

<span data-ttu-id="13bde-116">As conexões SIP diretas, por outro lado, são conexões de SIP que não atravessam o limite de rede local (ou seja, elas se conectam a um gateway PSTN ou PBX dentro de sua rede interna).</span><span class="sxs-lookup"><span data-stu-id="13bde-116">Direct SIP connections, on the other hand, are SIP connections that do not cross the local network boundary (that is, they connect to a public switched telephone network (PSTN) gateway or private branch exchange (PBX) within your internal network).</span></span> <span data-ttu-id="13bde-117">Para obter detalhes sobre como você pode usar as conexões SIP diretas com o Lync Server 2013, consulte [Direct SIP Connections in Lync server 2013](lync-server-2013-direct-sip-connections.md).</span><span class="sxs-lookup"><span data-stu-id="13bde-117">For details about how you can use direct SIP connections with Lync Server 2013, see [Direct SIP connections in Lync Server 2013](lync-server-2013-direct-sip-connections.md).</span></span>

</div>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="13bde-118">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="13bde-118">In This Section</span></span>

  - [<span data-ttu-id="13bde-119">Visão geral do tronco SIP no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="13bde-119">Overview of SIP trunking in Lync Server 2013</span></span>](lync-server-2013-overview-of-sip-trunking.md)

  - [<span data-ttu-id="13bde-120">Como faço para implementar o tronco SIP no Lync Server 2013?</span><span class="sxs-lookup"><span data-stu-id="13bde-120">How do I implement SIP trunking in Lync Server 2013?</span></span>](lync-server-2013-how-do-i-implement-sip-trunking.md)

  - [<span data-ttu-id="13bde-121">Componentes e topologias para tronco SIP no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="13bde-121">Components and topologies for SIP trunking in Lync Server 2013</span></span>](lync-server-2013-components-and-topologies-for-sip-trunking.md)

  - [<span data-ttu-id="13bde-122">Tronco SIP do site de filial no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="13bde-122">Branch site SIP trunking in Lync Server 2013</span></span>](lync-server-2013-branch-site-sip-trunking.md)

  - [<span data-ttu-id="13bde-123">Lista de verificação de implantação de tronco SIP para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="13bde-123">SIP trunk deployment checklist for Lync Server 2013</span></span>](lync-server-2013-sip-trunk-deployment-checklist.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

