---
title: Fases de migração
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: No Skype for Business Server 2019, você define sites em sua rede que contenham componentes do Skype for Business Server 2019. Um site é um conjunto de computadores que são bem conectados por uma rede de alta velocidade e baixa latência, como uma única rede local (LAN) ou duas redes conectadas por uma rede de fibra ótica de alta velocidade.
ms.openlocfilehash: b7d7fbddfe77c1303f0f6bde95827d94d7483f32
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813419"
---
# <a name="migration-phases"></a><span data-ttu-id="331c8-104">Fases de migração</span><span class="sxs-lookup"><span data-stu-id="331c8-104">Migration phases</span></span>

<span data-ttu-id="331c8-105">No Skype for Business Server 2019, você define sites em sua rede que contenham componentes do Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="331c8-105">In Skype for Business Server 2019, you define sites on your network that contain Skype for Business Server 2019 components.</span></span> <span data-ttu-id="331c8-106">Um site é um conjunto de computadores que são bem conectados por uma rede de alta velocidade e baixa latência, como uma única rede local (LAN) ou duas redes conectadas por uma rede de fibra ótica de alta velocidade.</span><span class="sxs-lookup"><span data-stu-id="331c8-106">A site is a set of computers that are well-connected by a high-speed, low-latency network, such as a single local area network (LAN) or two networks connected by a high-speed fiber optic network.</span></span> 
  
<span data-ttu-id="331c8-107">Um pool de front-ends é um conjunto de servidores front-end que são configurados de maneira idêntica e trabalham juntos para fornecer serviços para um grupo comum de usuários.</span><span class="sxs-lookup"><span data-stu-id="331c8-107">A Front End pool is a set of Front End Servers that are configured identically and work together to provide services for a common group of users.</span></span> <span data-ttu-id="331c8-108">Um pool fornece recursos de escalabilidade e failover para seus usuários.</span><span class="sxs-lookup"><span data-stu-id="331c8-108">A pool provides scalability and failover capability to your users.</span></span> <span data-ttu-id="331c8-109">Cada servidor de um pool deve executar funções idênticas de servidor.</span><span class="sxs-lookup"><span data-stu-id="331c8-109">Each server in a pool must run an identical server role or roles.</span></span> <span data-ttu-id="331c8-110">Um servidor Standard Edition, projetado para pequenas organizações, também define um pool e é executado em um único servidor.</span><span class="sxs-lookup"><span data-stu-id="331c8-110">A Standard Edition server, designed for small organizations, also defines a pool and runs on a single server.</span></span> <span data-ttu-id="331c8-111">Isso permite que você tenha a funcionalidade do Skype for Business Server 2019 para um custo menor, mas não oferece uma solução real de alta disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="331c8-111">This enables you to have Skype for Business Server 2019 functionality for a lesser cost, but does not provide a true high-availability solution.</span></span> 
  
<span data-ttu-id="331c8-112">As fases a seguir descrevem o processo de migração de pool para o Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="331c8-112">The following phases describe the process of a pool migration to Skype for Business Server 2019.</span></span> <span data-ttu-id="331c8-113">Para vários sites que contêm vários pools, cada pool individual deve seguir essa abordagem em fases.</span><span class="sxs-lookup"><span data-stu-id="331c8-113">For multiple sites containing multiple pools, each individual pool should follow this phased approach.</span></span>
  
1. [<span data-ttu-id="331c8-114">Fase 1: Planejar sua migração</span><span class="sxs-lookup"><span data-stu-id="331c8-114">Phase 1: Plan your migration</span></span>](phase-1-plan-your-migration.md)
    
2. [<span data-ttu-id="331c8-115">Fase 2: Preparar para migração</span><span class="sxs-lookup"><span data-stu-id="331c8-115">Phase 2: Prepare for migration</span></span>](phase-2-prepare-for-migration.md)
    
3. [<span data-ttu-id="331c8-116">Fase 3: implantar o pool piloto do Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="331c8-116">Phase 3: Deploy Skype for Business Server 2019 pilot pool</span></span>](phase-3-deploy-pilot-pool.md)
    
4. [<span data-ttu-id="331c8-117">Fase 4: mover os usuários de teste para o pool piloto</span><span class="sxs-lookup"><span data-stu-id="331c8-117">Phase 4: Move test users to the pilot pool</span></span>](phase-4-move-test-users-to-the-pilot-pool.md)
    
5. [<span data-ttu-id="331c8-118">Fase 5: Adicionar o servidor de borda do Skype for Business Server 2019 ao pool piloto</span><span class="sxs-lookup"><span data-stu-id="331c8-118">Phase 5: Add Skype for Business Server 2019 Edge Server to pilot pool</span></span>](phase-5-add-edge-server-to-pilot-pool.md)
    
6. [<span data-ttu-id="331c8-119">Fase 6: Mover da implantação piloto para produção</span><span class="sxs-lookup"><span data-stu-id="331c8-119">Phase 6: Move from pilot deployment into production</span></span>](phase-6-move-from-pilot-deployment-into-production.md)
    
7. [<span data-ttu-id="331c8-120">Fase 7: Concluir tarefas pós-migração</span><span class="sxs-lookup"><span data-stu-id="331c8-120">Phase 7: Complete post-migration tasks</span></span>](phase-7-complete-post-migration-tasks.md)
    
8. [<span data-ttu-id="331c8-121">Fase 8: Encerrar os pools herdados</span><span class="sxs-lookup"><span data-stu-id="331c8-121">Phase 8: Decommission legacy pools</span></span>](phase-8-decommission-legacy-pools.md)
    

