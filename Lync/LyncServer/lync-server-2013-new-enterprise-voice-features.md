---
title: 'Lync Server 2013: novos recursos do Enterprise Voice'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New Enterprise Voice features
ms:assetid: db0ad7b9-e469-4c29-89d9-52fed018ef08
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398964(v=OCS.15)
ms:contentKeyID: 48185591
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ea00bc092f12a81ca9804b60e31aa88858455657
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504128"
---
# <a name="new-enterprise-voice-features-in-lync-server-2013"></a><span data-ttu-id="32ca8-102">Novos recursos do Enterprise Voice no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="32ca8-102">New Enterprise Voice features in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="32ca8-103">_**Última modificação do tópico:** 2013-05-01_</span><span class="sxs-lookup"><span data-stu-id="32ca8-103">_**Topic Last Modified:** 2013-05-01_</span></span>

<span data-ttu-id="32ca8-104">O Lync Server 2013 introduz vários novos recursos de roteamento e gerenciamento de chamadas que aprimoram o Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="32ca8-104">Lync Server 2013 introduces several new routing and call management features that enhance Enterprise Voice.</span></span>

<span data-ttu-id="32ca8-105">O Lync Server 2013 oferece suporte a vários troncos entre servidores de mediação e gateways.</span><span class="sxs-lookup"><span data-stu-id="32ca8-105">Lync Server 2013 supports multiple trunks between Mediation Servers and gateways.</span></span> <span data-ttu-id="32ca8-106">Um *tronco* é uma associação lógica entre um número de porta e um servidor de mediação com um número de porta e gateway.</span><span class="sxs-lookup"><span data-stu-id="32ca8-106">A *trunk* is a logical association between a port number and Mediation Server with a port number and gateway.</span></span> <span data-ttu-id="32ca8-107">Isso significa que um servidor de mediação pode ter vários troncos para diferentes gateways, e um gateway pode ter vários troncos para diferentes servidores de mediação.</span><span class="sxs-lookup"><span data-stu-id="32ca8-107">This means that a Mediation Server can have multiple trunks to different gateways, and a gateway can have multiple trunks to different Mediation Servers.</span></span> <span data-ttu-id="32ca8-108">O roteamento entre troncos possibilita que o Lync Server 2013 interconecte um IP-PBX a um gateway PSTN (rede telefônica pública comutada) ou interconecte vários sistemas IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="32ca8-108">Intertrunk routing makes it possible for Lync Server 2013 to interconnect an IP-PBX to a public switched telephone network (PSTN) gateway or to interconnect multiple IP-PBX systems.</span></span> <span data-ttu-id="32ca8-109">O Lync Server 2013 serve como a cola (ou seja, a interconexão) entre sistemas de telefonia diferentes.</span><span class="sxs-lookup"><span data-stu-id="32ca8-109">Lync Server 2013 serves as the glue (that is, the interconnection) between different telephony systems.</span></span>

<span data-ttu-id="32ca8-110">O Microsoft Lync Server 2013 faz melhorias nas áreas de encaminhamento de chamadas, toque simultâneo, tratamento de caixa postal e apresentação de ID de chamada.</span><span class="sxs-lookup"><span data-stu-id="32ca8-110">Microsoft Lync Server 2013 makes improvements in the areas of call forwarding, simultaneous ringing, voice mail handling, and caller ID presentation.</span></span> <span data-ttu-id="32ca8-111">Esses recursos enriquecem a experiência de chamada do Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="32ca8-111">These features enrich the Enterprise Voice call experience.</span></span>

<span data-ttu-id="32ca8-112">O Lync Server 2013 apresenta os seguintes aprimoramentos novos para o Enterprise Voice:</span><span class="sxs-lookup"><span data-stu-id="32ca8-112">Lync Server 2013 introduces the following new enhancements to Enterprise Voice:</span></span>

  - [<span data-ttu-id="32ca8-113">Novos recursos de chamada no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="32ca8-113">New call features in Lync Server 2013</span></span>](lync-server-2013-new-call-features.md)

  - [<span data-ttu-id="32ca8-114">Novo recurso de ID de chamadas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="32ca8-114">New caller ID feature in Lync Server 2013</span></span>](lync-server-2013-new-caller-id-feature.md)

  - [<span data-ttu-id="32ca8-115">Novo recurso de caixa postal no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="32ca8-115">New voice mail feature in Lync Server 2013</span></span>](lync-server-2013-new-voice-mail-feature.md)

  - [<span data-ttu-id="32ca8-116">Novo recurso de tronco no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="32ca8-116">New trunk feature in Lync Server 2013</span></span>](lync-server-2013-new-trunk-feature.md)

  - [<span data-ttu-id="32ca8-117">Novo recurso entre troncos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="32ca8-117">New intertrunk feature in Lync Server 2013</span></span>](lync-server-2013-new-intertrunk-feature.md)

  - [<span data-ttu-id="32ca8-118">Novos recursos de gerenciamento de chamadas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="32ca8-118">New call management features in Lync Server 2013</span></span>](lync-server-2013-new-call-management-features.md)

</div>

<span> </span>

</div>

</div>

</div>

