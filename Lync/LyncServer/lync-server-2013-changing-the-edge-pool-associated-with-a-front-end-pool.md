---
title: 'Lync Server 2013: alterar o pool de borda associado a um pool de front-ends'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Changing the Edge pool associated with a Front End pool
ms:assetid: 369468c7-2c0b-48cc-bbc3-825dad7b85aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688023(v=OCS.15)
ms:contentKeyID: 49733613
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b7ad6ee6e40edb76d4ef5d7d53524f89e44a2aee
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043513"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changing-the-edge-pool-associated-with-a-front-end-pool-in-lync-server-2013"></a><span data-ttu-id="066fc-102">Alterar o pool de borda associado a um pool de front-ends no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="066fc-102">Changing the Edge pool associated with a Front End pool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="066fc-103">_**Última modificação do tópico:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="066fc-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="066fc-104">Se um pool de borda cair, mas o pool de front-ends do mesmo local ainda estiver em execução, será preciso configurar o pool de front-ends para que use o pool de borda de um local diferente até que o pool de borda com falha seja restaurado.</span><span class="sxs-lookup"><span data-stu-id="066fc-104">If an Edge pool goes down but the Front End pool at the same site is still running, you will need to set the Front End pool to use an Edge pool at a different site until the failed Edge pool is restored.</span></span>

<div>

## <a name="changing-the-edge-pool-associated-with-a-front-end-pool"></a><span data-ttu-id="066fc-105">Alterando o pool de borda associado a um pool de front-ends</span><span class="sxs-lookup"><span data-stu-id="066fc-105">Changing the Edge Pool Associated with a Front End Pool</span></span>

1.  <span data-ttu-id="066fc-106">NO Construtor de Topologias, navegue até o nome no pool de front-ends que precisa ser alterado.</span><span class="sxs-lookup"><span data-stu-id="066fc-106">In Topology Builder, navigate to the name of the Front End pool you need to change.</span></span>

2.  <span data-ttu-id="066fc-107">Clique com o botão direito do mouse no nome do pool e, então, em **Editar Propriedades**</span><span class="sxs-lookup"><span data-stu-id="066fc-107">Right-click the pool, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="066fc-108">Na seção **Associações**, em **Associar Pool de Borda (para componentes de mídia)**, use a caixa suspensa para selecionar o pool de borda ao qual deseja associar o pool de front-ends.</span><span class="sxs-lookup"><span data-stu-id="066fc-108">In the **Associations** section, under **Associate Edge Pool (for media components)**, use the drop down box to select the Edge pool you want to associate this Front End pool with.</span></span>

4.  <span data-ttu-id="066fc-109">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="066fc-109">Click **OK**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="066fc-110">Confira Também</span><span class="sxs-lookup"><span data-stu-id="066fc-110">See Also</span></span>


[<span data-ttu-id="066fc-111">Recuperação de desastre do servidor de borda no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="066fc-111">Edge Server disaster recovery in Lync Server 2013</span></span>](lync-server-2013-edge-server-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

