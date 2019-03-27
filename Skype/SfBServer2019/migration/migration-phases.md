---
title: Fases de migração
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Skype para Business Server 2019, você define sites em sua rede que contêm Skype para componentes de negócios Server 2019. Um site é um conjunto de computadores que estão bem conectados por uma rede de alta velocidade e baixa latência, como duas redes conectadas por uma rede de alta velocidade de fibra ótica ou de uma única rede local (LAN).
ms.openlocfilehash: d34351b551262450dee852efd7679f17cbe1e161
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30886522"
---
# <a name="migration-phases"></a><span data-ttu-id="e7ce0-104">Fases de migração</span><span class="sxs-lookup"><span data-stu-id="e7ce0-104">Migration phases</span></span>

<span data-ttu-id="e7ce0-105">Skype para Business Server 2019, você define sites em sua rede que contêm Skype para componentes de negócios Server 2019.</span><span class="sxs-lookup"><span data-stu-id="e7ce0-105">In Skype for Business Server 2019, you define sites on your network that contain Skype for Business Server 2019 components.</span></span> <span data-ttu-id="e7ce0-106">Um site é um conjunto de computadores que estão bem conectados por uma rede de alta velocidade e baixa latência, como duas redes conectadas por uma rede de alta velocidade de fibra ótica ou de uma única rede local (LAN).</span><span class="sxs-lookup"><span data-stu-id="e7ce0-106">A site is a set of computers that are well-connected by a high-speed, low-latency network, such as a single local area network (LAN) or two networks connected by a high-speed fiber optic network.</span></span> 
  
<span data-ttu-id="e7ce0-107">Um pool de Front-End é um conjunto de servidores Front-End que são configurados de forma idêntica e trabalhar juntos para fornecer serviços para um grupo de usuários comuns.</span><span class="sxs-lookup"><span data-stu-id="e7ce0-107">A Front End pool is a set of Front End Servers that are configured identically and work together to provide services for a common group of users.</span></span> <span data-ttu-id="e7ce0-108">Um pool oferece escalabilidade e o recurso de failover para seus usuários.</span><span class="sxs-lookup"><span data-stu-id="e7ce0-108">A pool provides scalability and failover capability to your users.</span></span> <span data-ttu-id="e7ce0-109">Cada servidor de um pool deve executar funções idênticas de servidor.</span><span class="sxs-lookup"><span data-stu-id="e7ce0-109">Each server in a pool must run an identical server role or roles.</span></span> <span data-ttu-id="e7ce0-110">Um servidor Standard Edition, projetado para pequenas organizações, também define um pool e é executado em um único servidor.</span><span class="sxs-lookup"><span data-stu-id="e7ce0-110">A Standard Edition server, designed for small organizations, also defines a pool and runs on a single server.</span></span> <span data-ttu-id="e7ce0-111">Isso permite que você tenha Skype para a funcionalidade do Business Server 2019 um custo menor, mas não oferece uma verdadeira solução de alta disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="e7ce0-111">This enables you to have Skype for Business Server 2019 functionality for a lesser cost, but does not provide a true high-availability solution.</span></span> 
  
<span data-ttu-id="e7ce0-112">As fases a seguir descrevem o processo de uma migração de pool para Skype para Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="e7ce0-112">The following phases describe the process of a pool migration to Skype for Business Server 2019.</span></span> <span data-ttu-id="e7ce0-113">Para vários sites que contém vários pools, cada pool individual deve seguir essa abordagem em fases.</span><span class="sxs-lookup"><span data-stu-id="e7ce0-113">For multiple sites containing multiple pools, each individual pool should follow this phased approach.</span></span>
  
1. [<span data-ttu-id="e7ce0-114">Fase 1: Planejar sua migração</span><span class="sxs-lookup"><span data-stu-id="e7ce0-114">Phase 1: Plan your migration</span></span>](phase-1-plan-your-migration.md)
    
2. [<span data-ttu-id="e7ce0-115">Fase 2: Preparar para migração</span><span class="sxs-lookup"><span data-stu-id="e7ce0-115">Phase 2: Prepare for migration</span></span>](phase-2-prepare-for-migration.md)
    
3. [<span data-ttu-id="e7ce0-116">Fase 3: Implantar Skype para o pool piloto Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="e7ce0-116">Phase 3: Deploy Skype for Business Server 2019 pilot pool</span></span>](phase-3-deploy-pilot-pool.md)
    
4. [<span data-ttu-id="e7ce0-117">Fase 4: Mover usuários de teste para o pool piloto</span><span class="sxs-lookup"><span data-stu-id="e7ce0-117">Phase 4: Move test users to the pilot pool</span></span>](phase-4-move-test-users-to-the-pilot-pool.md)
    
5. [<span data-ttu-id="e7ce0-118">Fase 5: Adicionar Skype para o servidor de borda do Business Server 2019 ao pool piloto</span><span class="sxs-lookup"><span data-stu-id="e7ce0-118">Phase 5: Add Skype for Business Server 2019 Edge Server to pilot pool</span></span>](phase-5-add-edge-server-to-pilot-pool.md)
    
6. [<span data-ttu-id="e7ce0-119">Fase 6: Mover da implantação piloto para produção</span><span class="sxs-lookup"><span data-stu-id="e7ce0-119">Phase 6: Move from pilot deployment into production</span></span>](phase-6-move-from-pilot-deployment-into-production.md)
    
7. [<span data-ttu-id="e7ce0-120">Fase 7: Concluir tarefas pós-migração</span><span class="sxs-lookup"><span data-stu-id="e7ce0-120">Phase 7: Complete post-migration tasks</span></span>](phase-7-complete-post-migration-tasks.md)
    
8. [<span data-ttu-id="e7ce0-121">Fase 8: Encerrar os pools herdados</span><span class="sxs-lookup"><span data-stu-id="e7ce0-121">Phase 8: Decommission legacy pools</span></span>](phase-8-decommission-legacy-pools.md)
    

