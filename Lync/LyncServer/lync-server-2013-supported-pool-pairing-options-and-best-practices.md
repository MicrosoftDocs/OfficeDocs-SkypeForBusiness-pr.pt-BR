---
title: Lync Server 2013 opções de emparelhamento de pool compatível e práticas recomendadas
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supported pool pairing options and best practices
ms:assetid: 142caf34-0f20-47f3-9d32-ce25ab622fad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204697(v=OCS.15)
ms:contentKeyID: 48183478
ms.date: 03/09/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 963f1532ca7a1aa5402a54936909a22727ab9716
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006839"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supported-pool-pairing-options-and-best-practices-for-lync-server-2013"></a><span data-ttu-id="e295e-102">Opções de emparelhamento de pool com suporte e práticas recomendadas para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e295e-102">Supported pool pairing options and best practices for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e295e-103">_**Última modificação do tópico:** 2017-03-09_</span><span class="sxs-lookup"><span data-stu-id="e295e-103">_**Topic Last Modified:** 2017-03-09_</span></span>

<span data-ttu-id="e295e-p101">Não há restrições de distância entre dois data centers que incluirão pools de Front End emparelhados entre si. É recomendável usar dois data centers na mesma região geográfica com links de alta velocidade entre eles. É melhor se os dois data centers estiverem suficientemente distantes para evitar que um único desastre atinja ambos ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="e295e-p101">There is no restriction on the distance between two data centers that are to include Front End pools paired with each other. We recommend that you use two data centers in the same world region, with high-speed links between them. It is best if the two data centers are separated enough to avoid a single disaster hitting both at the same time.</span></span>

<span data-ttu-id="e295e-107">Ter dois data centers em regiões geográficas distintas é possível, mas poderia incorrer em maior perda de dados devido à latência na replicação dos dados.</span><span class="sxs-lookup"><span data-stu-id="e295e-107">Having two data centers across world regions is possible, but could incur higher data loss due to latency in data replication.</span></span>

<span data-ttu-id="e295e-108">Ao planejar quais pools emparelhar, você deve ter em mente que somente os seguintes pares têm suporte:</span><span class="sxs-lookup"><span data-stu-id="e295e-108">When you plan which pools to pair, you must keep in mind that only the following pairings are supported:</span></span>

  - <span data-ttu-id="e295e-p102">Pools do Enterprise Edition só podem ser emparelhados com outros pools do Enterprise Edition. Da mesma forma, pools do Standard Edition podem ser emparelhados somente com outros pools do Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="e295e-p102">Enterprise Edition pools can be paired only with other Enterprise Edition pools. Similarly, Standard Edition pools can be paired only with other Standard Edition pools.</span></span>

  - <span data-ttu-id="e295e-p103">Pools físicos só podem ser emparelhados com outros pools físicos. Da mesma forma, pools virtuais só podem ser emparelhados com outros pools virtuais.</span><span class="sxs-lookup"><span data-stu-id="e295e-p103">Physical pools can be paired only with other physical pools. Similarly, virtual pools can be paired only with other virtual pools.</span></span>

  - <span data-ttu-id="e295e-113">Os pools emparelhados devem estar executando o mesmo sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="e295e-113">Pools that are paired together must be running the same operating system.</span></span>

<span data-ttu-id="e295e-114">Nem o Construtor de Topologias nem a validação da topologia proibirão o emparelhamento de dois pools de uma forma que estas recomendações não sejam seguidas.</span><span class="sxs-lookup"><span data-stu-id="e295e-114">Neither Topology Builder nor topology validation will prohibit pairing two pools in a way that does not follow these recommendations.</span></span> <span data-ttu-id="e295e-115">Por exemplo, o Construtor de Topologias permite o emparelhamento de um pool do Enterprise Edition com um pool do Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="e295e-115">For example, Topology Builder allows you to pair an Enterprise Edition pool with a Standard Edition pool.</span></span> <span data-ttu-id="e295e-116">No entanto, esses tipos de emparelhamento não são suportados.</span><span class="sxs-lookup"><span data-stu-id="e295e-116">However, these types of pairings are not supported.</span></span>

<span data-ttu-id="e295e-117">Cada pool em um emparelhamento deve ter a capacidade de atender todos os usuários de ambos os pools em caso de desastre.</span><span class="sxs-lookup"><span data-stu-id="e295e-117">Each pool in a pair should have the capacity to serve all users from both pools in the event of a disaster.</span></span>

<span data-ttu-id="e295e-118">Se você emparelhar pools do Enterprise Edition, também poderá implementar alta disponibilidade nos servidores de Back End, mas para pares de pools do Standard Edition somente as medidas da recuperação de desastres estão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="e295e-118">If you pair Enterprise Edition pools, you can also implement high availability on the Back End Servers, but for pairs of Standard Edition pools only the disaster recovery measures are available.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

