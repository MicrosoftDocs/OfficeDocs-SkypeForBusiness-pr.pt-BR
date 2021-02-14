---
title: Migrar vários sites e pools
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
description: 'O Skype for Business Server 2019 oferece suporte a implantações de vários sites e de vários pools. O processo de migração de vários pools para o Skype for Business Server 2019 requer as seguintes considerações:'
ms.openlocfilehash: 4906b05138d546e685a06acecc4f7adc4e88516e
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752653"
---
# <a name="migrating-multiple-sites-and-pools"></a><span data-ttu-id="7c885-104">Migrar vários sites e pools</span><span class="sxs-lookup"><span data-stu-id="7c885-104">Migrating multiple sites and pools</span></span>

<span data-ttu-id="7c885-105">O Skype for Business Server 2019 oferece suporte a implantações de vários sites e de vários pools.</span><span class="sxs-lookup"><span data-stu-id="7c885-105">Skype for Business Server 2019 supports multi-site and multi-pool deployments.</span></span> <span data-ttu-id="7c885-106">O processo de migração de vários pools para o Skype for Business Server 2019 requer as seguintes considerações:</span><span class="sxs-lookup"><span data-stu-id="7c885-106">The process of migrating multiple pools to Skype for Business Server 2019 requires the following considerations:</span></span> 
  
1. <span data-ttu-id="7c885-107">Depois de implantar um pool piloto do Skype for Business Server 2019, você precisará definir um subconjunto de usuários piloto que serão movidos para o pool do Skype for Business Server 2019 e uma metodologia para validar a funcionalidade dos usuários.</span><span class="sxs-lookup"><span data-stu-id="7c885-107">After deploying a Skype for Business Server 2019 pilot pool, you need to define a subset of pilot users that will be moved to the Skype for Business Server 2019 pool, and a methodology for validating the functionality of the users.</span></span> <span data-ttu-id="7c885-108">Por exemplo, depois de mover um usuário para o pool piloto, verifique se a política de conferência do usuário foi movida para o Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="7c885-108">For example, after moving a user to the pilot pool, verify that the user's conference policy has moved to Skype for Business Server 2019.</span></span> 
    
2. <span data-ttu-id="7c885-109">Depois de implantar um Servidor de Borda no pool piloto, você precisará validar se os usuários externos podem se comunicar com o pool do Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="7c885-109">After deploying an Edge Server in the pilot pool, you need to validate that external users can communicate with the Skype for Business Server 2019 pool.</span></span>

3. <span data-ttu-id="7c885-110">As funcionalidades de Chat Persistente, Espelhamento SQL e XMPP foram preteridas no Skype for Business Server 2019 e não estão mais disponíveis como recursos do Skype for Business Server 2019, mas podem continuar em um ambiente de coexistência se foram implantadas anteriormente em um ambiente herdado.</span><span class="sxs-lookup"><span data-stu-id="7c885-110">Persistent Chat, SQL Mirroring, and XMPP functionality are deprecated in Skype for Business Server 2019 and no longer available as Skype for Business Server 2019 features, but they can be continued in a coexistence environment if they were previously deployed in a legacy environment.</span></span> <span data-ttu-id="7c885-111">Se você quiser continuar usando esses recursos, planeje continuar com um ambiente de coexistência onde determinados usuários permanecerão em pools herdado.</span><span class="sxs-lookup"><span data-stu-id="7c885-111">If you want to continue using these features, you should plan to continue with a coexistence environment where certain users will remain in legacy pools.</span></span>
    
4. <span data-ttu-id="7c885-112">Após a transição dos Servidores de Borda das rotas federadas para os Servidores de Borda do Skype for Business Server 2019 piloto, você precisa validar se os usuários federados podem se comunicar com o pool do Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="7c885-112">After transitioning the federated routes' Edge Servers to the pilot Skype for Business Server 2019 Edge Servers, you need to validate that federated users can communicate with the Skype for Business Server 2019 pool.</span></span>
    
5. <span data-ttu-id="7c885-113">Depois de mover todos os objetos de contato de usuários e não usuários, você precisa validar se o pool herdado está vazio.</span><span class="sxs-lookup"><span data-stu-id="7c885-113">After moving all users and non-user contact objects, you need to validate that the legacy pool is empty.</span></span>
    
6. <span data-ttu-id="7c885-114">Depois de verificar se o pool herdado está vazio, você pode desativar o pool.</span><span class="sxs-lookup"><span data-stu-id="7c885-114">After verifying that the legacy pool is empty, you can then deactivate the pool.</span></span> 
    
    <span data-ttu-id="7c885-115">Para obter detalhes sobre como desativar o pool e servidores herdados, consulte a Fase [8: Desativar pools herdados.](phase-8-decommission-legacy-pools.md)</span><span class="sxs-lookup"><span data-stu-id="7c885-115">For details about how to deactivate the legacy pool and servers, see [Phase 8: Decommission legacy pools](phase-8-decommission-legacy-pools.md).</span></span>
    

