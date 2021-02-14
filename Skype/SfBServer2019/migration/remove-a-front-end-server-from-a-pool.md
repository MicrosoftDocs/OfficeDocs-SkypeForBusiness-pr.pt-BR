---
title: Remover um Servidor Front-End de um pool
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: O Servidor Front End não pode existir como um computador autônomo. Ele deve ser definido como um pool de Front-End, mesmo se houver apenas um único computador no pool.
ms.openlocfilehash: 7675ba119fa2937d765d5f4e497fca0a040b3b62
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752313"
---
# <a name="remove-a-front-end-server-from-a-pool"></a><span data-ttu-id="f59b5-104">Remover um Servidor Front-End de um pool</span><span class="sxs-lookup"><span data-stu-id="f59b5-104">Remove a Front End Server from a pool</span></span>

<span data-ttu-id="f59b5-105">O Servidor Front End não pode existir como um computador autônomo.</span><span class="sxs-lookup"><span data-stu-id="f59b5-105">The Front End Server cannot exist as a stand-alone computer.</span></span> <span data-ttu-id="f59b5-106">Ele deve ser definido como um pool de Front-End, mesmo se houver apenas um único computador no pool.</span><span class="sxs-lookup"><span data-stu-id="f59b5-106">It must be defined as a Front End pool, even if there is only a single computer in the pool.</span></span>
  
<span data-ttu-id="f59b5-107">Este tópico orienta você durante o processo de remoção de um Servidor front-end individual de um pool de front-end existente.</span><span class="sxs-lookup"><span data-stu-id="f59b5-107">This topic guides you through the process of removing an individual Front End Server from an existing Front End pool.</span></span> <span data-ttu-id="f59b5-108">Se o Servidor front-end for o último servidor no pool ou se você estiver removendo o pool completamente, consulte Remover pool de [front-end](remove-front-end-pool-or-standard-edition-server.md)ou servidor Standard Edition .</span><span class="sxs-lookup"><span data-stu-id="f59b5-108">If the Front End Server is the last server in the pool or if you are removing the pool completely, see [Remove Front End pool or Standard Edition server](remove-front-end-pool-or-standard-edition-server.md).</span></span> <span data-ttu-id="f59b5-109">Não é necessário remover os Servidores front-end individuais antes de remover o pool de Front-End.</span><span class="sxs-lookup"><span data-stu-id="f59b5-109">There is no need to remove the individual Front End Servers before you remove the Front End pool.</span></span> <span data-ttu-id="f59b5-110">Ao remover o pool, você remove cada Servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="f59b5-110">When you remove the pool, you remove each Front End Server.</span></span>
  
### <a name="to-remove-a-front-end-server-from-a-pool"></a><span data-ttu-id="f59b5-111">Para remover um servidor Front-End de um pool</span><span class="sxs-lookup"><span data-stu-id="f59b5-111">To remove a Front End Server from a pool</span></span>

1. <span data-ttu-id="f59b5-112">No Servidor front-end do Skype for Business Server 2019, abra o Construtor de Topologias.</span><span class="sxs-lookup"><span data-stu-id="f59b5-112">On the Skype for Business Server 2019 Front End Server, open Topology Builder.</span></span>
    
2. <span data-ttu-id="f59b5-113">Navegue até o nó de instalação herddo.</span><span class="sxs-lookup"><span data-stu-id="f59b5-113">Navigate to the legacy install node.</span></span>
    
3. <span data-ttu-id="f59b5-114">Expanda os pools de **front-end** do Enterprise Edition, expanda o pool de front-end com o servidor front-end que você deseja remover, clique com o botão direito do mouse no Servidor front-end que você deseja remover e clique em **Excluir.**</span><span class="sxs-lookup"><span data-stu-id="f59b5-114">Expand **Enterprise Edition Front End pools**, expand the Front End pool with the Front End Server that you want to remove, right-click the Front End Server that you want to remove, and then click **Delete**.</span></span>
    

