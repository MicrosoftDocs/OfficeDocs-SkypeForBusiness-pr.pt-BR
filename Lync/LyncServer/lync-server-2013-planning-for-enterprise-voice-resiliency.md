---
title: 'Lync Server 2013: planejamento para resiliência do Enterprise Voice'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for Enterprise Voice resiliency
ms:assetid: ca116700-1055-4ca5-9b87-4c7f380c3655
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398840(v=OCS.15)
ms:contentKeyID: 48185408
ms.date: 10/17/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 635e252953956d9dc6619ab51eea88804c2905c9
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036903"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-enterprise-voice-resiliency-in-lync-server-2013"></a><span data-ttu-id="d014b-102">Planejamento para resiliência do Enterprise Voice no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d014b-102">Planning for Enterprise Voice resiliency in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d014b-103">_**Última modificação do tópico:** 2014-10-17_</span><span class="sxs-lookup"><span data-stu-id="d014b-103">_**Topic Last Modified:** 2014-10-17_</span></span>

<span data-ttu-id="d014b-104">A resiliência de voz refere-se à capacidade de os usuários continuarem a fazer e receber chamadas se um site central que hospeda o Lync Server 2013 ficar indisponível, seja por uma falha de rede de longa distância (WAN) ou outra causa.</span><span class="sxs-lookup"><span data-stu-id="d014b-104">Voice resiliency refers to the ability of users to continue making and receiving calls if a central site that hosts Lync Server 2013 becomes unavailable, whether through a wide area network (WAN) failure or another cause.</span></span> <span data-ttu-id="d014b-105">Se um site central falhar, o serviço Enterprise Voice deverá continuar sem interrupção através de failover contínuo para um local de backup.</span><span class="sxs-lookup"><span data-stu-id="d014b-105">If a central site fails, Enterprise Voice service must continue uninterrupted through seamless failover to a backup site.</span></span> <span data-ttu-id="d014b-106">No caso de falha de WAN, as chamadas do site de filial devem ser redirecionadas para um gateway PSTN local.</span><span class="sxs-lookup"><span data-stu-id="d014b-106">In the event of WAN failure, branch site calls must be redirected to a local PSTN gateway.</span></span> <span data-ttu-id="d014b-107">Esta seção discute o planejamento da resiliência de voz no caso de falha de site central ou WAN.</span><span class="sxs-lookup"><span data-stu-id="d014b-107">This section discusses planning for voice resiliency in the event of central-site or WAN failure.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="d014b-108">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="d014b-108">In This Section</span></span>

  - [<span data-ttu-id="d014b-109">Planejamento da resiliência de voz do site central no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d014b-109">Planning for central site voice resiliency in Lync Server 2013</span></span>](lync-server-2013-planning-for-central-site-voice-resiliency.md)

  - [<span data-ttu-id="d014b-110">Planejamento de resiliência de voz no site de filial no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d014b-110">Planning for branch-site voice resiliency in Lync Server 2013</span></span>](lync-server-2013-planning-for-branch-site-voice-resiliency.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

