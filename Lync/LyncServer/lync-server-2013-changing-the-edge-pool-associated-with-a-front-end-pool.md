---
title: 'Lync Server 2013: Alterando o Pool de borda associado ao pool Front-End'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Changing the Edge pool associated with a Front End pool
ms:assetid: 369468c7-2c0b-48cc-bbc3-825dad7b85aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688023(v=OCS.15)
ms:contentKeyID: 49733613
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0bbb2e6ffdaa238dcbd4a184c8db890c26dd6340
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836588"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changing-the-edge-pool-associated-with-a-front-end-pool-in-lync-server-2013"></a><span data-ttu-id="2303d-102">Alterando o Pool de borda associado ao pool Front-End no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2303d-102">Changing the Edge pool associated with a Front End pool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2303d-103">_**Tópico da última modificação:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="2303d-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="2303d-104">Se um pool de bordas ficar inoperante, mas o pool de front-end no mesmo site ainda estiver em execução, será necessário definir o pool de front-ends para usar um pool de bordas em um site diferente até que o pool de bordas com falha seja restaurado.</span><span class="sxs-lookup"><span data-stu-id="2303d-104">If an Edge pool goes down but the Front End pool at the same site is still running, you will need to set the Front End pool to use an Edge pool at a different site until the failed Edge pool is restored.</span></span>

<div>

## <a name="changing-the-edge-pool-associated-with-a-front-end-pool"></a><span data-ttu-id="2303d-105">Alterar o pool de bordas associado a um pool de front-end</span><span class="sxs-lookup"><span data-stu-id="2303d-105">Changing the Edge Pool Associated with a Front End Pool</span></span>

1.  <span data-ttu-id="2303d-106">No construtor de topologias, navegue até o nome do pool de front-ends que você precisa alterar.</span><span class="sxs-lookup"><span data-stu-id="2303d-106">In Topology Builder, navigate to the name of the Front End pool you need to change.</span></span>

2.  <span data-ttu-id="2303d-107">Clique com o botão direito do mouse no pool e, em seguida, clique em **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="2303d-107">Right-click the pool, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="2303d-108">Na seção **associações** , em associar a um **pool de bordas (para componentes de mídia)**, use a caixa suspensa para selecionar o pool de bordas ao qual você deseja associar esse pool de front-ends.</span><span class="sxs-lookup"><span data-stu-id="2303d-108">In the **Associations** section, under **Associate Edge Pool (for media components)**, use the drop down box to select the Edge pool you want to associate this Front End pool with.</span></span>

4.  <span data-ttu-id="2303d-109">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="2303d-109">Click **OK**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2303d-110">Confira também</span><span class="sxs-lookup"><span data-stu-id="2303d-110">See Also</span></span>


[<span data-ttu-id="2303d-111">Recuperação de desastres do servidor de borda no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2303d-111">Edge Server disaster recovery in Lync Server 2013</span></span>](lync-server-2013-edge-server-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

