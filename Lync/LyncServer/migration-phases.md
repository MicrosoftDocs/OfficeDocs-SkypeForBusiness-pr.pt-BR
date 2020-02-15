---
title: Fases da migração
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
ms.openlocfilehash: 08379ec217cc684ae9b6bc11c44b89a3d642f6df
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030695"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-phases"></a><span data-ttu-id="fe068-102">Fases da migração</span><span class="sxs-lookup"><span data-stu-id="fe068-102">Migration phases</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fe068-103">_**Última modificação do tópico:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="fe068-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="fe068-104">No Lync Server 2013, você define sites em sua rede que contenham componentes do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fe068-104">In Lync Server 2013, you define sites on your network that contain Lync Server 2013 components.</span></span> <span data-ttu-id="fe068-105">Um site é um conjunto de computadores bem conectados por uma rede de baixa latência e alta velocidade, como uma única LAN ou duas redes conectadas por uma rede de fibra óptica de alta velocidade.</span><span class="sxs-lookup"><span data-stu-id="fe068-105">A site is a set of computers that are well-connected by a high-speed, low-latency network, such as a single local area network (LAN) or two networks connected by a high-speed fiber optic network.</span></span>

<span data-ttu-id="fe068-106">Um *Pool de front-end* é um conjunto de servidores de front-end configurados identicamente e que trabalham juntos para oferecer serviços para um grupo de usuários comum.</span><span class="sxs-lookup"><span data-stu-id="fe068-106">A *Front End pool* is a set of Front End Servers that are configured identically and work together to provide services for a common group of users.</span></span> <span data-ttu-id="fe068-107">Um pool oferece escalabilidade e capacidade de failover aos seus usuários.</span><span class="sxs-lookup"><span data-stu-id="fe068-107">A pool provides scalability and failover capability to your users.</span></span> <span data-ttu-id="fe068-108">Cada servidor em um pool deve executar uma função ou funções do servidor idênticas.</span><span class="sxs-lookup"><span data-stu-id="fe068-108">Each server in a pool must run an identical server role or roles.</span></span> <span data-ttu-id="fe068-109">Um servidor Standard Edition, projetado para pequenas organizações, também define um pool e é executado em um único servidor.</span><span class="sxs-lookup"><span data-stu-id="fe068-109">A Standard Edition server, designed for small organizations, also defines a pool and runs on a single server.</span></span> <span data-ttu-id="fe068-110">Isso permite que você tenha a funcionalidade do Lync Server 2013 para um custo menor, mas não fornece uma solução de alta disponibilidade real.</span><span class="sxs-lookup"><span data-stu-id="fe068-110">This enables you to have Lync Server 2013 functionality for a lesser cost, but does not provide a true high-availability solution.</span></span>

<span data-ttu-id="fe068-111">As fases a seguir descrevem o processo de migração de pool do Lync Server 2010 para o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fe068-111">The following phases describe the process of a pool migration from Lync Server 2010 to Lync Server 2013.</span></span> <span data-ttu-id="fe068-112">Para vários sites que contêm pools, cada pool individual deve seguir esta abordagem por fase.</span><span class="sxs-lookup"><span data-stu-id="fe068-112">For multiple sites containing multiple pools, each individual pool should follow this phased approach.</span></span>

1.  [<span data-ttu-id="fe068-113">Fase 1: planejar a migração do Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="fe068-113">Phase 1: Plan your migration from Lync Server 2010</span></span>](phase-1-plan-your-migration-from-lync-server-2010.md)

2.  [<span data-ttu-id="fe068-114">Fase 2: preparar-se para a migração</span><span class="sxs-lookup"><span data-stu-id="fe068-114">Phase 2: Prepare for migration</span></span>](phase-2-prepare-for-migration.md)

3.  [<span data-ttu-id="fe068-115">Fase 3: implantar o pool piloto do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fe068-115">Phase 3: Deploy Lync Server 2013 pilot pool</span></span>](phase-3-deploy-lync-server-2013-pilot-pool.md)

4.  [<span data-ttu-id="fe068-116">Fase 4: mover usuários de teste para o pool piloto</span><span class="sxs-lookup"><span data-stu-id="fe068-116">Phase 4: Move test users to the pilot pool</span></span>](phase-4-move-test-users-to-the-pilot-pool.md)

5.  [<span data-ttu-id="fe068-117">Fase 5: Adicionar o servidor de borda do Lync Server 2013 ao pool piloto</span><span class="sxs-lookup"><span data-stu-id="fe068-117">Phase 5: Add Lync Server 2013 Edge Server to pilot pool</span></span>](phase-5-add-lync-server-2013-edge-server-to-pilot-pool.md)

6.  [<span data-ttu-id="fe068-118">Fase 6: mover da implantação piloto para a produção</span><span class="sxs-lookup"><span data-stu-id="fe068-118">Phase 6: Move from pilot deployment into production</span></span>](phase-6-move-from-pilot-deployment-into-production.md)

7.  [<span data-ttu-id="fe068-119">Fase 7: concluir tarefas de migração</span><span class="sxs-lookup"><span data-stu-id="fe068-119">Phase 7: Complete post-migration tasks</span></span>](phase-7-complete-post-migration-tasks.md)

8.  [<span data-ttu-id="fe068-120">Fase 8: encerrar pools herdados</span><span class="sxs-lookup"><span data-stu-id="fe068-120">Phase 8: Decommission legacy pools</span></span>](phase-8-decommission-legacy-pools.md)

</div>

<span> </span>

</div>

</div>

</div>

