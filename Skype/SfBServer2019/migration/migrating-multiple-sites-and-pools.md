---
title: Migrando múltiplos sites e pools
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Skype para Business Server 2019 oferece suporte a implantações de vários locais e do pool de múltiplos. O processo de migração de vários pools para Skype for Business Server 2019 requer as seguintes considerações:'
ms.openlocfilehash: ecd7e795c7cde9265f26c9c7533fcfd6ec87d684
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/13/2018
ms.locfileid: "26293545"
---
# <a name="migrating-multiple-sites-and-pools"></a><span data-ttu-id="9bce6-104">Migrando múltiplos sites e pools</span><span class="sxs-lookup"><span data-stu-id="9bce6-104">Migrating multiple sites and pools</span></span>

<span data-ttu-id="9bce6-105">Skype para Business Server 2019 oferece suporte a implantações de vários locais e do pool de múltiplos.</span><span class="sxs-lookup"><span data-stu-id="9bce6-105">Skype for Business Server 2019 supports multi-site and multi-pool deployments.</span></span> <span data-ttu-id="9bce6-106">O processo de migração de vários pools para Skype for Business Server 2019 requer as seguintes considerações:</span><span class="sxs-lookup"><span data-stu-id="9bce6-106">The process of migrating multiple pools to Skype for Business Server 2019 requires the following considerations:</span></span> 
  
1. <span data-ttu-id="9bce6-107">Após implantar um Skype para Business Server 2019 o pool piloto, você precisará definir um subconjunto dos usuários piloto que serão movidas para o Skype para Business Server 2019 pool e uma metodologia para validar a funcionalidade dos usuários.</span><span class="sxs-lookup"><span data-stu-id="9bce6-107">After deploying a Skype for Business Server 2019 pilot pool, you need to define a subset of pilot users that will be moved to the Skype for Business Server 2019 pool, and a methodology for validating the functionality of the users.</span></span> <span data-ttu-id="9bce6-108">Por exemplo, depois de mover um usuário para o pool piloto, verifique se que a política de conferência do usuário foi movido para Skype para Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="9bce6-108">For example, after moving a user to the pilot pool, verify that the user's conference policy has moved to Skype for Business Server 2019.</span></span> 
    
2. <span data-ttu-id="9bce6-109">Depois de implantar um servidor de borda no pool piloto, você precisará validar que os usuários externos podem se comunicar com o Skype para Business Server 2019 pool.</span><span class="sxs-lookup"><span data-stu-id="9bce6-109">After deploying an Edge Server in the pilot pool, you need to validate that external users can communicate with the Skype for Business Server 2019 pool.</span></span>

3. <span data-ttu-id="9bce6-110">Chat persistente, espelhamento SQL e a funcionalidade XMPP são preteridos no Skype para Business Server 2019 e não está disponível como Skype para recursos de Business Server 2019, mas pode ser continuadas em um ambiente de coexistência se eles foram implantados anteriormente em um ambiente de legado.</span><span class="sxs-lookup"><span data-stu-id="9bce6-110">Persistent Chat, SQL Mirroring, and XMPP functionality are deprecated in Skype for Business Server 2019 and no longer available as Skype for Business Server 2019 features, but they can be continued in a coexistence environment if they were previously deployed in a legacy environment.</span></span> <span data-ttu-id="9bce6-111">Se você deseja continuar a usar esses recursos, você deve planejar continuar com um ambiente de coexistência onde determinados usuários permanecerá em pools herdados.</span><span class="sxs-lookup"><span data-stu-id="9bce6-111">If you want to continue using these features, you should plan to continue with a coexistence environment where certain users will remain in legacy pools.</span></span>
    
4. <span data-ttu-id="9bce6-112">Após a transição servidores das rotas federadas de borda para o piloto Skype para os servidores de borda de 2019 Business Server, você precisará validar que os usuários federados podem se comunicar com o Skype para Business Server 2019 pool.</span><span class="sxs-lookup"><span data-stu-id="9bce6-112">After transitioning the federated routes' Edge Servers to the pilot Skype for Business Server 2019 Edge Servers, you need to validate that federated users can communicate with the Skype for Business Server 2019 pool.</span></span>
    
5. <span data-ttu-id="9bce6-113">Depois de mover todos os usuários e objetos de contato não usuários, você precisará validar que o pool herdado está vazio.</span><span class="sxs-lookup"><span data-stu-id="9bce6-113">After moving all users and non-user contact objects, you need to validate that the legacy pool is empty.</span></span>
    
6. <span data-ttu-id="9bce6-114">Depois de verificar se o pool herdado está vazio, você pode desativar o pool.</span><span class="sxs-lookup"><span data-stu-id="9bce6-114">After verifying that the legacy pool is empty, you can then deactivate the pool.</span></span> 
    
    <span data-ttu-id="9bce6-115">Para obter detalhes sobre como desativar o pool herdado herdado e servidores, consulte [fase 8: encerre os pools herdados](phase-8-decommission-legacy-pools.md).</span><span class="sxs-lookup"><span data-stu-id="9bce6-115">For details about how to deactivate the legacy legacy pool and servers, see [Phase 8: Decommission legacy pools](phase-8-decommission-legacy-pools.md).</span></span>
    

