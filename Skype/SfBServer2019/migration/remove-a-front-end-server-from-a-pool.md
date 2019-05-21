---
title: Remover um Servidor Front-End de um pool
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: O servidor front-end não pode existir como um computador autônomo. Ele deve ser definido como um pool de front-end, mesmo se houver apenas um único computador no pool.
ms.openlocfilehash: 5c1cd06e4cbe5cd6cecd8484e9c7874fb5ba590e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34301136"
---
# <a name="remove-a-front-end-server-from-a-pool"></a><span data-ttu-id="6bdb6-104">Remover um Servidor Front-End de um pool</span><span class="sxs-lookup"><span data-stu-id="6bdb6-104">Remove a Front End Server from a pool</span></span>

<span data-ttu-id="6bdb6-105">O servidor front-end não pode existir como um computador autônomo.</span><span class="sxs-lookup"><span data-stu-id="6bdb6-105">The Front End Server cannot exist as a stand-alone computer.</span></span> <span data-ttu-id="6bdb6-106">Ele deve ser definido como um pool de front-end, mesmo se houver apenas um único computador no pool.</span><span class="sxs-lookup"><span data-stu-id="6bdb6-106">It must be defined as a Front End pool, even if there is only a single computer in the pool.</span></span>
  
<span data-ttu-id="6bdb6-107">Este tópico orienta você pelo processo de remoção de um servidor front-end individual de um pool de front-end existente.</span><span class="sxs-lookup"><span data-stu-id="6bdb6-107">This topic guides you through the process of removing an individual Front End Server from an existing Front End pool.</span></span> <span data-ttu-id="6bdb6-108">Se o servidor front-end for o último servidor do pool ou se você estiver removendo o pool completamente, consulte [remover o pool de front-end ou o servidor Standard Edition](remove-front-end-pool-or-standard-edition-server.md).</span><span class="sxs-lookup"><span data-stu-id="6bdb6-108">If the Front End Server is the last server in the pool or if you are removing the pool completely, see [Remove Front End pool or Standard Edition server](remove-front-end-pool-or-standard-edition-server.md).</span></span> <span data-ttu-id="6bdb6-109">Não é necessário remover os servidores front-end individuais antes de remover o pool de front-ends.</span><span class="sxs-lookup"><span data-stu-id="6bdb6-109">There is no need to remove the individual Front End Servers before you remove the Front End pool.</span></span> <span data-ttu-id="6bdb6-110">Ao remover o pool, você remove cada servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="6bdb6-110">When you remove the pool, you remove each Front End Server.</span></span>
  
### <a name="to-remove-a-front-end-server-from-a-pool"></a><span data-ttu-id="6bdb6-111">Para remover um servidor front-end de um pool</span><span class="sxs-lookup"><span data-stu-id="6bdb6-111">To remove a Front End Server from a pool</span></span>

1. <span data-ttu-id="6bdb6-112">No servidor front-end do Skype for Business Server 2019, abra o construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="6bdb6-112">On the Skype for Business Server 2019 Front End Server, open Topology Builder.</span></span>
    
2. <span data-ttu-id="6bdb6-113">Navegue até o nó instalação herdada.</span><span class="sxs-lookup"><span data-stu-id="6bdb6-113">Navigate to the legacy install node.</span></span>
    
3. <span data-ttu-id="6bdb6-114">Expanda Pools de **front-end do Enterprise Edition**, expanda o pool de front-ends com o servidor front-end que você deseja remover, clique com o botão direito do mouse no servidor front-end que você deseja remover e clique em **excluir**.</span><span class="sxs-lookup"><span data-stu-id="6bdb6-114">Expand **Enterprise Edition Front End pools**, expand the Front End pool with the Front End Server that you want to remove, right-click the Front End Server that you want to remove, and then click **Delete**.</span></span>
    

