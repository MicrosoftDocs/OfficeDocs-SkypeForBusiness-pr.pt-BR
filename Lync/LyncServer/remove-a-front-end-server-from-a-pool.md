---
title: Remover um servidor front-end de um pool
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Remove a Front End Server from a pool
ms:assetid: 767225c9-7c0b-4d54-a407-d77134ba2abe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688095(v=OCS.15)
ms:contentKeyID: 49733694
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2e9cd348d6a96009e92dfa8a3ef50dae39eb013d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42189574"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="remove-a-front-end-server-from-a-pool"></a><span data-ttu-id="b39ad-102">Remover um servidor front-end de um pool</span><span class="sxs-lookup"><span data-stu-id="b39ad-102">Remove a Front End Server from a pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b39ad-103">_**Última modificação do tópico:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="b39ad-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="b39ad-104">O servidor front-end do Microsoft Lync Server 2010 Enterprise Edition não pode existir como um computador autônomo.</span><span class="sxs-lookup"><span data-stu-id="b39ad-104">The Microsoft Lync Server 2010 Enterprise Edition Front End Server cannot exist as a stand-alone computer.</span></span> <span data-ttu-id="b39ad-105">Ele deve ser definido como um pool de front-ends, mesmo se houver apenas um único computador no pool.</span><span class="sxs-lookup"><span data-stu-id="b39ad-105">It must be defined as a Front End pool, even if there is only a single computer in the pool.</span></span>

<span data-ttu-id="b39ad-106">Este tópico orienta você durante o processo de remoção de um servidor front-end individual de um pool de front-ends existente.</span><span class="sxs-lookup"><span data-stu-id="b39ad-106">This topic guides you through the process of removing an individual Front End Server from an existing Front End pool.</span></span> <span data-ttu-id="b39ad-107">Se o servidor front-end for o último servidor do pool ou se você estiver removendo o pool completamente, consulte [Remove front end pool ou Standard Edition Server](remove-front-end-pool-or-standard-edition-server.md).</span><span class="sxs-lookup"><span data-stu-id="b39ad-107">If the Front End Server is the last server in the pool or if you are removing the pool completely, see [Remove Front End pool or Standard Edition server](remove-front-end-pool-or-standard-edition-server.md).</span></span> <span data-ttu-id="b39ad-108">Não é necessário remover os servidores front-end individuais antes de remover o pool de front-ends.</span><span class="sxs-lookup"><span data-stu-id="b39ad-108">There is no need to remove the individual Front End Servers before you remove the Front End pool.</span></span> <span data-ttu-id="b39ad-109">Ao remover o pool, você remove cada servidor de front-end.</span><span class="sxs-lookup"><span data-stu-id="b39ad-109">When you remove the pool, you remove each Front End Server.</span></span>

<div>

## <a name="to-remove-a-front-end-server-from-a-pool"></a><span data-ttu-id="b39ad-110">Para remover um servidor Front-End de um pool</span><span class="sxs-lookup"><span data-stu-id="b39ad-110">To remove a Front End Server from a pool</span></span>

1.  <span data-ttu-id="b39ad-111">Abra o servidor front-end do Lync Server 2013, abra o construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="b39ad-111">Open the Lync Server 2013 Front End Server, open Topology Builder.</span></span>

2.  <span data-ttu-id="b39ad-112">Navegue até o nó do Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="b39ad-112">Navigate to the Lync Server 2010 node.</span></span>

3.  <span data-ttu-id="b39ad-113">Expanda **pools de front-ends Enterprise Edition**, expanda o pool de front-ends com o servidor front-end que você deseja remover, clique com o botão direito do mouse no servidor front-end que você deseja remover e clique em **excluir**.</span><span class="sxs-lookup"><span data-stu-id="b39ad-113">Expand **Enterprise Edition Front End pools**, expand the Front End pool with the Front End Server that you want to remove, right-click the Front End Server that you want to remove, and then click **Delete**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

