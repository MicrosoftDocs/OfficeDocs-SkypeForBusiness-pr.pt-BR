---
title: Fases da migração
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
description: No Skype for Business Server 2019, você define sites em sua rede que contêm componentes do Skype for Business Server 2019. Um site é um conjunto de computadores bem conectados por uma rede de baixa latência e alta velocidade, como uma única LAN ou duas redes conectadas por uma rede de fibra óptica de alta velocidade.
ms.openlocfilehash: d05fc0c4eb7d12a6d96b638fe7f59acc830fbcd1
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752623"
---
# <a name="migration-phases"></a><span data-ttu-id="5e10c-104">Fases da migração</span><span class="sxs-lookup"><span data-stu-id="5e10c-104">Migration phases</span></span>

<span data-ttu-id="5e10c-105">No Skype for Business Server 2019, você define sites em sua rede que contêm componentes do Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="5e10c-105">In Skype for Business Server 2019, you define sites on your network that contain Skype for Business Server 2019 components.</span></span> <span data-ttu-id="5e10c-106">Um site é um conjunto de computadores bem conectados por uma rede de baixa latência e alta velocidade, como uma única LAN ou duas redes conectadas por uma rede de fibra óptica de alta velocidade.</span><span class="sxs-lookup"><span data-stu-id="5e10c-106">A site is a set of computers that are well-connected by a high-speed, low-latency network, such as a single local area network (LAN) or two networks connected by a high-speed fiber optic network.</span></span> 
  
<span data-ttu-id="5e10c-107">Um Pool de front-end é um conjunto de servidores de front-end configurados identicamente e que trabalham juntos para oferecer serviços para um grupo de usuários comum.</span><span class="sxs-lookup"><span data-stu-id="5e10c-107">A Front End pool is a set of Front End Servers that are configured identically and work together to provide services for a common group of users.</span></span> <span data-ttu-id="5e10c-108">Um pool oferece escalabilidade e capacidade de failover aos seus usuários.</span><span class="sxs-lookup"><span data-stu-id="5e10c-108">A pool provides scalability and failover capability to your users.</span></span> <span data-ttu-id="5e10c-109">Cada servidor em um pool deve executar uma função ou funções do servidor idênticas.</span><span class="sxs-lookup"><span data-stu-id="5e10c-109">Each server in a pool must run an identical server role or roles.</span></span> <span data-ttu-id="5e10c-110">Um servidor Standard Edition, projetado para pequenas organizações, também define um pool e é executado em um único servidor.</span><span class="sxs-lookup"><span data-stu-id="5e10c-110">A Standard Edition server, designed for small organizations, also defines a pool and runs on a single server.</span></span> <span data-ttu-id="5e10c-111">Isso permite que você tenha a funcionalidade do Skype for Business Server 2019 por um custo menor, mas não fornece uma verdadeira solução de alta disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="5e10c-111">This enables you to have Skype for Business Server 2019 functionality for a lesser cost, but does not provide a true high-availability solution.</span></span> 
  
<span data-ttu-id="5e10c-112">As fases a seguir descrevem o processo de uma migração de pool para o Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="5e10c-112">The following phases describe the process of a pool migration to Skype for Business Server 2019.</span></span> <span data-ttu-id="5e10c-113">Para vários sites que contêm pools, cada pool individual deve seguir esta abordagem por fase.</span><span class="sxs-lookup"><span data-stu-id="5e10c-113">For multiple sites containing multiple pools, each individual pool should follow this phased approach.</span></span>
  
1. [<span data-ttu-id="5e10c-114">Fase 1: Planejar sua migração</span><span class="sxs-lookup"><span data-stu-id="5e10c-114">Phase 1: Plan your migration</span></span>](phase-1-plan-your-migration.md)
    
2. [<span data-ttu-id="5e10c-115">Fase 2: Preparar para migração</span><span class="sxs-lookup"><span data-stu-id="5e10c-115">Phase 2: Prepare for migration</span></span>](phase-2-prepare-for-migration.md)
    
3. [<span data-ttu-id="5e10c-116">Fase 3: Implantar o pool piloto do Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="5e10c-116">Phase 3: Deploy Skype for Business Server 2019 pilot pool</span></span>](phase-3-deploy-pilot-pool.md)
    
4. [<span data-ttu-id="5e10c-117">Fase 4: Mover usuários de teste para o pool piloto</span><span class="sxs-lookup"><span data-stu-id="5e10c-117">Phase 4: Move test users to the pilot pool</span></span>](phase-4-move-test-users-to-the-pilot-pool.md)
    
5. [<span data-ttu-id="5e10c-118">Fase 5: Adicionar o Servidor de Borda do Skype for Business Server 2019 ao pool piloto</span><span class="sxs-lookup"><span data-stu-id="5e10c-118">Phase 5: Add Skype for Business Server 2019 Edge Server to pilot pool</span></span>](phase-5-add-edge-server-to-pilot-pool.md)
    
6. [<span data-ttu-id="5e10c-119">Fase 6: Mover da implantação piloto para produção</span><span class="sxs-lookup"><span data-stu-id="5e10c-119">Phase 6: Move from pilot deployment into production</span></span>](phase-6-move-from-pilot-deployment-into-production.md)
    
7. [<span data-ttu-id="5e10c-120">Fase 7: Concluir tarefas pós-migração</span><span class="sxs-lookup"><span data-stu-id="5e10c-120">Phase 7: Complete post-migration tasks</span></span>](phase-7-complete-post-migration-tasks.md)
    
8. [<span data-ttu-id="5e10c-121">Fase 8: Encerrar os pools herdados</span><span class="sxs-lookup"><span data-stu-id="5e10c-121">Phase 8: Decommission legacy pools</span></span>](phase-8-decommission-legacy-pools.md)
    

