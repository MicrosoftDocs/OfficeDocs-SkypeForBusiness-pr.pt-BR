---
title: Fases da migração
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Skype para Business Server 2019, você define sites em sua rede que contêm Skype para componentes de negócios Server 2019. Um site é um conjunto de computadores que estão bem conectados por uma rede de alta velocidade e baixa latência, como duas redes conectadas por uma rede de alta velocidade de fibra ótica ou de uma única rede local (LAN).
ms.openlocfilehash: cb6529ac09c10f73a01d3454ef9518d7fe960e1f
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "25027729"
---
# <a name="migration-phases"></a><span data-ttu-id="f3ff2-104">Fases da migração</span><span class="sxs-lookup"><span data-stu-id="f3ff2-104">Migration phases</span></span>

<span data-ttu-id="f3ff2-105">Skype para Business Server 2019, você define sites em sua rede que contêm Skype para componentes de negócios Server 2019.</span><span class="sxs-lookup"><span data-stu-id="f3ff2-105">In Skype for Business Server 2019, you define sites on your network that contain Skype for Business Server 2019 components.</span></span> <span data-ttu-id="f3ff2-106">Um site é um conjunto de computadores que estão bem conectados por uma rede de alta velocidade e baixa latência, como duas redes conectadas por uma rede de alta velocidade de fibra ótica ou de uma única rede local (LAN).</span><span class="sxs-lookup"><span data-stu-id="f3ff2-106">A site is a set of computers that are well-connected by a high-speed, low-latency network, such as a single local area network (LAN) or two networks connected by a high-speed fiber optic network.</span></span> 
  
<span data-ttu-id="f3ff2-107">Um pool de Front-End é um conjunto de servidores Front-End que são configurados de forma idêntica e trabalhar juntos para fornecer serviços para um grupo de usuários comuns.</span><span class="sxs-lookup"><span data-stu-id="f3ff2-107">A Front End pool is a set of Front End Servers that are configured identically and work together to provide services for a common group of users.</span></span> <span data-ttu-id="f3ff2-108">Um pool oferece escalabilidade e o recurso de failover para seus usuários.</span><span class="sxs-lookup"><span data-stu-id="f3ff2-108">A pool provides scalability and failover capability to your users.</span></span> <span data-ttu-id="f3ff2-109">Cada servidor de um pool deve executar funções idênticas de servidor.</span><span class="sxs-lookup"><span data-stu-id="f3ff2-109">Each server in a pool must run an identical server role or roles.</span></span> <span data-ttu-id="f3ff2-110">Um servidor Standard Edition, projetado para pequenas organizações, também define um pool e é executado em um único servidor.</span><span class="sxs-lookup"><span data-stu-id="f3ff2-110">A Standard Edition server, designed for small organizations, also defines a pool and runs on a single server.</span></span> <span data-ttu-id="f3ff2-111">Isso permite que você tenha Skype para a funcionalidade do Business Server 2019 um custo menor, mas não oferece uma verdadeira solução de alta disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="f3ff2-111">This enables you to have Skype for Business Server 2019 functionality for a lesser cost, but does not provide a true high-availability solution.</span></span> 
  
<span data-ttu-id="f3ff2-112">As fases a seguir descrevem o processo de uma migração de pool para Skype para Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="f3ff2-112">The following phases describe the process of a pool migration to Skype for Business Server 2019.</span></span> <span data-ttu-id="f3ff2-113">Para vários sites que contém vários pools, cada pool individual deve seguir essa abordagem em fases.</span><span class="sxs-lookup"><span data-stu-id="f3ff2-113">For multiple sites containing multiple pools, each individual pool should follow this phased approach.</span></span>
  
1. [<span data-ttu-id="f3ff2-114">Fase 1: Planejar a migração</span><span class="sxs-lookup"><span data-stu-id="f3ff2-114">Phase 1: Plan your migration</span></span>](phase-1-plan-your-migration.md)
    
2. [<span data-ttu-id="f3ff2-115">Fase 2: Preparar para migração</span><span class="sxs-lookup"><span data-stu-id="f3ff2-115">Phase 2: Prepare for migration</span></span>](phase-2-prepare-for-migration.md)
    
3. [<span data-ttu-id="f3ff2-116">Fase 3: Implantar Skype para o pool piloto Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="f3ff2-116">Phase 3: Deploy Skype for Business Server 2019 pilot pool</span></span>](phase-3-deploy-pilot-pool.md)
    
4. [<span data-ttu-id="f3ff2-117">Fase 4: Mover usuários de teste para o pool piloto</span><span class="sxs-lookup"><span data-stu-id="f3ff2-117">Phase 4: Move test users to the pilot pool</span></span>](phase-4-move-test-users-to-the-pilot-pool.md)
    
5. [<span data-ttu-id="f3ff2-118">Fase 5: Adicionar Skype para o servidor de borda do Business Server 2019 ao pool piloto</span><span class="sxs-lookup"><span data-stu-id="f3ff2-118">Phase 5: Add Skype for Business Server 2019 Edge Server to pilot pool</span></span>](phase-5-add-edge-server-to-pilot-pool.md)
    
6. [<span data-ttu-id="f3ff2-119">Fase 6: Mover da implantação piloto para a produção</span><span class="sxs-lookup"><span data-stu-id="f3ff2-119">Phase 6: Move from pilot deployment into production</span></span>](phase-6-move-from-pilot-deployment-into-production.md)
    
7. [<span data-ttu-id="f3ff2-120">Fase 7: Concluir tarefas pós-migração</span><span class="sxs-lookup"><span data-stu-id="f3ff2-120">Phase 7: Complete post-migration tasks</span></span>](phase-7-complete-post-migration-tasks.md)
    
8. [<span data-ttu-id="f3ff2-121">Fase 8: Encerrar os pools herdados</span><span class="sxs-lookup"><span data-stu-id="f3ff2-121">Phase 8: Decommission legacy pools</span></span>](phase-8-decommission-legacy-pools.md)
    

