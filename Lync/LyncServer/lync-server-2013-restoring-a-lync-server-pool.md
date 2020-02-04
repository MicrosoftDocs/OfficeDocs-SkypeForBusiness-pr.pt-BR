---
title: 'Lync Server 2013: restaurar um pool do Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring a Lync Server pool
ms:assetid: 6fe80fb3-38ad-4931-a07b-1763b61aa448
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202176(v=OCS.15)
ms:contentKeyID: 51541488
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f43cbe049fdedc2f0b4d31eecc4a0506a4a62201
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723531"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-a-lync-server-pool-in-lync-server-2013"></a><span data-ttu-id="ea2ae-102">Restaurando um pool do Lync Server no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ea2ae-102">Restoring a Lync Server pool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ea2ae-103">_**Tópico da última modificação:** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="ea2ae-103">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="ea2ae-104">A implantação do Lync Server pode incluir qualquer um dos seguintes tipos de pool:</span><span class="sxs-lookup"><span data-stu-id="ea2ae-104">Your Lync Server deployment may include any of the following types of pools:</span></span>

  - <span data-ttu-id="ea2ae-105">Servidor Front-End</span><span class="sxs-lookup"><span data-stu-id="ea2ae-105">Front End Server</span></span>

  - <span data-ttu-id="ea2ae-106">Servidor de Mediação</span><span class="sxs-lookup"><span data-stu-id="ea2ae-106">Mediation Server</span></span>

  - <span data-ttu-id="ea2ae-107">Servidor de Chat Persistente</span><span class="sxs-lookup"><span data-stu-id="ea2ae-107">Persistent Chat Server</span></span>

  - <span data-ttu-id="ea2ae-108">Servidor de Borda</span><span class="sxs-lookup"><span data-stu-id="ea2ae-108">Edge Server</span></span>

<span data-ttu-id="ea2ae-109">Se um pool inteiro apresentar uma falha, siga estes procedimentos para cada servidor membro do pool.</span><span class="sxs-lookup"><span data-stu-id="ea2ae-109">If an entire pool experiences an outage, follow these procedures for each member server in the pool.</span></span>

  - <span data-ttu-id="ea2ae-110">Para um pool de front-ends, restaure primeiro o servidor back-end e, em seguida, restaure cada servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="ea2ae-110">For a Front End pool, restore the Back End Server first, and then restore each Front End Server.</span></span> <span data-ttu-id="ea2ae-111">Para obter detalhes, consulte [restaurando um servidor back-end do Enterprise Edition no Lync server 2013](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md) e [restaurando um servidor membro da Enterprise Edition no Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).</span><span class="sxs-lookup"><span data-stu-id="ea2ae-111">For details, see [Restoring an Enterprise Edition Back End Server in Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md) and [Restoring an Enterprise Edition member server in Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).</span></span>

  - <span data-ttu-id="ea2ae-112">Para todos os outros tipos de pools, restaure cada servidor membro.</span><span class="sxs-lookup"><span data-stu-id="ea2ae-112">For all other types of pools, restore each member server.</span></span> <span data-ttu-id="ea2ae-113">Para obter detalhes, consulte [restaurando um servidor membro do Enterprise Edition no Lync server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).</span><span class="sxs-lookup"><span data-stu-id="ea2ae-113">For details, see [Restoring an Enterprise Edition member server in Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

