---
title: Lync Server 2013 opções de emparelhamento de pool compatível e práticas recomendadas
description: Lync Server 2013 opções de emparelhamento de pool compatível e práticas recomendadas.
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
ms.openlocfilehash: 76d0f8331c0b6998008efff8af70ae3c4b43a9c2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560277"
---
# <a name="supported-pool-pairing-options-and-best-practices-for-lync-server-2013"></a><span data-ttu-id="db38c-103">Opções de emparelhamento de pool com suporte e práticas recomendadas para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="db38c-103">Supported pool pairing options and best practices for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="db38c-104">_**Última modificação do tópico:** 2017-03-09_</span><span class="sxs-lookup"><span data-stu-id="db38c-104">_**Topic Last Modified:** 2017-03-09_</span></span>

<span data-ttu-id="db38c-p101">Não há restrições de distância entre dois data centers que incluirão pools de Front End emparelhados entre si. É recomendável usar dois data centers na mesma região geográfica com links de alta velocidade entre eles. É melhor se os dois data centers estiverem suficientemente distantes para evitar que um único desastre atinja ambos ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="db38c-p101">There is no restriction on the distance between two data centers that are to include Front End pools paired with each other. We recommend that you use two data centers in the same world region, with high-speed links between them. It is best if the two data centers are separated enough to avoid a single disaster hitting both at the same time.</span></span>

<span data-ttu-id="db38c-108">Ter dois data centers em regiões geográficas distintas é possível, mas poderia incorrer em maior perda de dados devido à latência na replicação dos dados.</span><span class="sxs-lookup"><span data-stu-id="db38c-108">Having two data centers across world regions is possible, but could incur higher data loss due to latency in data replication.</span></span>

<span data-ttu-id="db38c-109">Ao planejar quais pools emparelhar, você deve ter em mente que somente os seguintes pares têm suporte:</span><span class="sxs-lookup"><span data-stu-id="db38c-109">When you plan which pools to pair, you must keep in mind that only the following pairings are supported:</span></span>

  - <span data-ttu-id="db38c-p102">Pools do Enterprise Edition só podem ser emparelhados com outros pools do Enterprise Edition. Da mesma forma, pools do Standard Edition podem ser emparelhados somente com outros pools do Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="db38c-p102">Enterprise Edition pools can be paired only with other Enterprise Edition pools. Similarly, Standard Edition pools can be paired only with other Standard Edition pools.</span></span>

  - <span data-ttu-id="db38c-p103">Pools físicos só podem ser emparelhados com outros pools físicos. Da mesma forma, pools virtuais só podem ser emparelhados com outros pools virtuais.</span><span class="sxs-lookup"><span data-stu-id="db38c-p103">Physical pools can be paired only with other physical pools. Similarly, virtual pools can be paired only with other virtual pools.</span></span>

  - <span data-ttu-id="db38c-114">Os pools emparelhados devem estar executando o mesmo sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="db38c-114">Pools that are paired together must be running the same operating system.</span></span>

<span data-ttu-id="db38c-115">Nem o Construtor de Topologias nem a validação da topologia proibirão o emparelhamento de dois pools de uma forma que estas recomendações não sejam seguidas.</span><span class="sxs-lookup"><span data-stu-id="db38c-115">Neither Topology Builder nor topology validation will prohibit pairing two pools in a way that does not follow these recommendations.</span></span> <span data-ttu-id="db38c-116">Por exemplo, o Construtor de Topologias permite o emparelhamento de um pool do Enterprise Edition com um pool do Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="db38c-116">For example, Topology Builder allows you to pair an Enterprise Edition pool with a Standard Edition pool.</span></span> <span data-ttu-id="db38c-117">No entanto, esses tipos de emparelhamento não são suportados.</span><span class="sxs-lookup"><span data-stu-id="db38c-117">However, these types of pairings are not supported.</span></span>

<span data-ttu-id="db38c-118">Cada pool em um emparelhamento deve ter a capacidade de atender todos os usuários de ambos os pools em caso de desastre.</span><span class="sxs-lookup"><span data-stu-id="db38c-118">Each pool in a pair should have the capacity to serve all users from both pools in the event of a disaster.</span></span>

<span data-ttu-id="db38c-119">Se você emparelhar pools do Enterprise Edition, também poderá implementar alta disponibilidade nos servidores de Back End, mas para pares de pools do Standard Edition somente as medidas da recuperação de desastres estão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="db38c-119">If you pair Enterprise Edition pools, you can also implement high availability on the Back End Servers, but for pairs of Standard Edition pools only the disaster recovery measures are available.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

