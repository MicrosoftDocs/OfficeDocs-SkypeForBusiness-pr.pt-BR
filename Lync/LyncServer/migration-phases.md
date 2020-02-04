---
title: Fases de migração
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migration phases
ms:assetid: cb7747ba-b872-42ca-ab41-76e3c4e77d06
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205336(v=OCS.15)
ms:contentKeyID: 48185642
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 76719513d3b9df6b3259efef57fc0bd5ae94050f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730941"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-phases"></a><span data-ttu-id="959b6-102">Fases de migração</span><span class="sxs-lookup"><span data-stu-id="959b6-102">Migration phases</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="959b6-103">_**Tópico da última modificação:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="959b6-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="959b6-104">No Lync Server 2013, você define sites em sua rede que contenham componentes do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="959b6-104">In Lync Server 2013, you define sites on your network that contain Lync Server 2013 components.</span></span> <span data-ttu-id="959b6-105">Um site é um conjunto de computadores que são bem conectados por uma rede de alta velocidade e baixa latência, como uma única rede local (LAN) ou duas redes conectadas por uma rede de fibra ótica de alta velocidade.</span><span class="sxs-lookup"><span data-stu-id="959b6-105">A site is a set of computers that are well-connected by a high-speed, low-latency network, such as a single local area network (LAN) or two networks connected by a high-speed fiber optic network.</span></span>

<span data-ttu-id="959b6-106">Um *pool de front-ends* é um conjunto de servidores front-end que são configurados de maneira idêntica e trabalham juntos para fornecer serviços para um grupo comum de usuários.</span><span class="sxs-lookup"><span data-stu-id="959b6-106">A *Front End pool* is a set of Front End Servers that are configured identically and work together to provide services for a common group of users.</span></span> <span data-ttu-id="959b6-107">Um pool fornece recursos de escalabilidade e failover para seus usuários.</span><span class="sxs-lookup"><span data-stu-id="959b6-107">A pool provides scalability and failover capability to your users.</span></span> <span data-ttu-id="959b6-108">Cada servidor de um pool deve executar funções idênticas de servidor.</span><span class="sxs-lookup"><span data-stu-id="959b6-108">Each server in a pool must run an identical server role or roles.</span></span> <span data-ttu-id="959b6-109">Um servidor Standard Edition, projetado para pequenas organizações, também define um pool e é executado em um único servidor.</span><span class="sxs-lookup"><span data-stu-id="959b6-109">A Standard Edition server, designed for small organizations, also defines a pool and runs on a single server.</span></span> <span data-ttu-id="959b6-110">Isso permite que você tenha a funcionalidade do Lync Server 2013 para um custo menor, mas não oferece uma solução real de alta disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="959b6-110">This enables you to have Lync Server 2013 functionality for a lesser cost, but does not provide a true high-availability solution.</span></span>

<span data-ttu-id="959b6-111">As fases a seguir descrevem o processo de uma migração de pool do Lync Server 2010 para o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="959b6-111">The following phases describe the process of a pool migration from Lync Server 2010 to Lync Server 2013.</span></span> <span data-ttu-id="959b6-112">Para vários sites que contêm vários pools, cada pool individual deve seguir essa abordagem em fases.</span><span class="sxs-lookup"><span data-stu-id="959b6-112">For multiple sites containing multiple pools, each individual pool should follow this phased approach.</span></span>

1.  [<span data-ttu-id="959b6-113">Fase 1: planejar a migração do Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="959b6-113">Phase 1: Plan your migration from Lync Server 2010</span></span>](phase-1-plan-your-migration-from-lync-server-2010.md)

2.  [<span data-ttu-id="959b6-114">Fase 2: Preparar para migração</span><span class="sxs-lookup"><span data-stu-id="959b6-114">Phase 2: Prepare for migration</span></span>](phase-2-prepare-for-migration.md)

3.  [<span data-ttu-id="959b6-115">Fase 3: implantar o pool piloto do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="959b6-115">Phase 3: Deploy Lync Server 2013 pilot pool</span></span>](phase-3-deploy-lync-server-2013-pilot-pool.md)

4.  [<span data-ttu-id="959b6-116">Fase 4: mover os usuários de teste para o pool piloto</span><span class="sxs-lookup"><span data-stu-id="959b6-116">Phase 4: Move test users to the pilot pool</span></span>](phase-4-move-test-users-to-the-pilot-pool.md)

5.  [<span data-ttu-id="959b6-117">Fase 5: Adicionar o servidor de borda do Lync Server 2013 ao pool piloto</span><span class="sxs-lookup"><span data-stu-id="959b6-117">Phase 5: Add Lync Server 2013 Edge Server to pilot pool</span></span>](phase-5-add-lync-server-2013-edge-server-to-pilot-pool.md)

6.  [<span data-ttu-id="959b6-118">Fase 6: Mover da implantação piloto para produção</span><span class="sxs-lookup"><span data-stu-id="959b6-118">Phase 6: Move from pilot deployment into production</span></span>](phase-6-move-from-pilot-deployment-into-production.md)

7.  [<span data-ttu-id="959b6-119">Fase 7: Concluir tarefas pós-migração</span><span class="sxs-lookup"><span data-stu-id="959b6-119">Phase 7: Complete post-migration tasks</span></span>](phase-7-complete-post-migration-tasks.md)

8.  [<span data-ttu-id="959b6-120">Fase 8: Encerrar os pools herdados</span><span class="sxs-lookup"><span data-stu-id="959b6-120">Phase 8: Decommission legacy pools</span></span>](phase-8-decommission-legacy-pools.md)

</div>

<span> </span>

</div>

</div>

</div>

