---
title: Remover um Servidor Front-End de um pool
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
ms.openlocfilehash: e0637754c6e7b1a03c233025703297c182dc3099
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727311"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-a-front-end-server-from-a-pool"></a><span data-ttu-id="7f1ec-102">Remover um Servidor Front-End de um pool</span><span class="sxs-lookup"><span data-stu-id="7f1ec-102">Remove a Front End Server from a pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7f1ec-103">_**Tópico da última modificação:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="7f1ec-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="7f1ec-104">O servidor front-end do Microsoft Lync Server 2010 Enterprise Edition não pode existir como um computador autônomo.</span><span class="sxs-lookup"><span data-stu-id="7f1ec-104">The Microsoft Lync Server 2010 Enterprise Edition Front End Server cannot exist as a stand-alone computer.</span></span> <span data-ttu-id="7f1ec-105">Ele deve ser definido como um pool de front-end, mesmo se houver apenas um único computador no pool.</span><span class="sxs-lookup"><span data-stu-id="7f1ec-105">It must be defined as a Front End pool, even if there is only a single computer in the pool.</span></span>

<span data-ttu-id="7f1ec-106">Este tópico orienta você pelo processo de remoção de um servidor front-end individual de um pool de front-end existente.</span><span class="sxs-lookup"><span data-stu-id="7f1ec-106">This topic guides you through the process of removing an individual Front End Server from an existing Front End pool.</span></span> <span data-ttu-id="7f1ec-107">Se o servidor front-end for o último servidor do pool ou se você estiver removendo o pool completamente, consulte [remover o pool de front-end ou o servidor Standard Edition](remove-front-end-pool-or-standard-edition-server.md).</span><span class="sxs-lookup"><span data-stu-id="7f1ec-107">If the Front End Server is the last server in the pool or if you are removing the pool completely, see [Remove Front End pool or Standard Edition server](remove-front-end-pool-or-standard-edition-server.md).</span></span> <span data-ttu-id="7f1ec-108">Não é necessário remover os servidores front-end individuais antes de remover o pool de front-ends.</span><span class="sxs-lookup"><span data-stu-id="7f1ec-108">There is no need to remove the individual Front End Servers before you remove the Front End pool.</span></span> <span data-ttu-id="7f1ec-109">Ao remover o pool, você remove cada servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="7f1ec-109">When you remove the pool, you remove each Front End Server.</span></span>

<div>

## <a name="to-remove-a-front-end-server-from-a-pool"></a><span data-ttu-id="7f1ec-110">Para remover um servidor front-end de um pool</span><span class="sxs-lookup"><span data-stu-id="7f1ec-110">To remove a Front End Server from a pool</span></span>

1.  <span data-ttu-id="7f1ec-111">Abra o servidor front-end do Lync Server 2013, abra o construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="7f1ec-111">Open the Lync Server 2013 Front End Server, open Topology Builder.</span></span>

2.  <span data-ttu-id="7f1ec-112">Navegue até o nó do Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="7f1ec-112">Navigate to the Lync Server 2010 node.</span></span>

3.  <span data-ttu-id="7f1ec-113">Expanda **pools de front-end do Enterprise Edition**, expanda o pool de front-ends com o servidor front-end que você deseja remover, clique com o botão direito do mouse no servidor front-end que você deseja remover e clique em **excluir**.</span><span class="sxs-lookup"><span data-stu-id="7f1ec-113">Expand **Enterprise Edition Front End pools**, expand the Front End pool with the Front End Server that you want to remove, right-click the Front End Server that you want to remove, and then click **Delete**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

