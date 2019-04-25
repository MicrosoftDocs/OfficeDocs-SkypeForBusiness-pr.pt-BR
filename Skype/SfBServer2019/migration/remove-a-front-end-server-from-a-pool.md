---
title: Remover um Servidor Front-End de um pool
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Servidor Front-End não pode existir como um computador autônomo. Ele deve ser definido como um pool de Front-End, mesmo se houver apenas um único computador no pool.
ms.openlocfilehash: f026570f0dff377ba7ca0c28975a685e236a9e13
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32231427"
---
# <a name="remove-a-front-end-server-from-a-pool"></a><span data-ttu-id="c14d0-104">Remover um Servidor Front-End de um pool</span><span class="sxs-lookup"><span data-stu-id="c14d0-104">Remove a Front End Server from a pool</span></span>

<span data-ttu-id="c14d0-105">Servidor Front-End não pode existir como um computador autônomo.</span><span class="sxs-lookup"><span data-stu-id="c14d0-105">The Front End Server cannot exist as a stand-alone computer.</span></span> <span data-ttu-id="c14d0-106">Ele deve ser definido como um pool de Front-End, mesmo se houver apenas um único computador no pool.</span><span class="sxs-lookup"><span data-stu-id="c14d0-106">It must be defined as a Front End pool, even if there is only a single computer in the pool.</span></span>
  
<span data-ttu-id="c14d0-107">Este tópico o orienta no processo de remover um servidor Front-End individuais de um pool de Front-End existente.</span><span class="sxs-lookup"><span data-stu-id="c14d0-107">This topic guides you through the process of removing an individual Front End Server from an existing Front End pool.</span></span> <span data-ttu-id="c14d0-108">Se o servidor Front-End for o último servidor no pool ou se você estiver removendo completamente o pool, consulte [Remover Front End pool ou servidor Standard Edition](remove-front-end-pool-or-standard-edition-server.md).</span><span class="sxs-lookup"><span data-stu-id="c14d0-108">If the Front End Server is the last server in the pool or if you are removing the pool completely, see [Remove Front End pool or Standard Edition server](remove-front-end-pool-or-standard-edition-server.md).</span></span> <span data-ttu-id="c14d0-109">Não há nenhuma necessidade para remover os servidores Front-End individuais antes de remover o pool de Front-End.</span><span class="sxs-lookup"><span data-stu-id="c14d0-109">There is no need to remove the individual Front End Servers before you remove the Front End pool.</span></span> <span data-ttu-id="c14d0-110">Quando você remove o pool, você pode remover cada servidor Front-End.</span><span class="sxs-lookup"><span data-stu-id="c14d0-110">When you remove the pool, you remove each Front End Server.</span></span>
  
### <a name="to-remove-a-front-end-server-from-a-pool"></a><span data-ttu-id="c14d0-111">Para remover um servidor Front-End de um pool</span><span class="sxs-lookup"><span data-stu-id="c14d0-111">To remove a Front End Server from a pool</span></span>

1. <span data-ttu-id="c14d0-112">No Skype para Business Server 2019 servidor Front-End, abra o construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="c14d0-112">On the Skype for Business Server 2019 Front End Server, open Topology Builder.</span></span>
    
2. <span data-ttu-id="c14d0-113">Navegue até o nó install herdado.</span><span class="sxs-lookup"><span data-stu-id="c14d0-113">Navigate to the legacy install node.</span></span>
    
3. <span data-ttu-id="c14d0-114">Expanda **pools de Front End do Enterprise Edition**, expanda o pool de Front-End com o servidor Front-End que você deseja remover, clique com o botão servidor Front-End que você deseja remover e clique em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="c14d0-114">Expand **Enterprise Edition Front End pools**, expand the Front End pool with the Front End Server that you want to remove, right-click the Front End Server that you want to remove, and then click **Delete**.</span></span>
    

