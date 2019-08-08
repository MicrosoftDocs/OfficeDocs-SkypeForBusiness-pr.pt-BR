---
title: Migrar vários sites e pools
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'O Skype for Business Server 2019 oferece suporte a implantações de vários locais e vários pools. O processo de migração de vários pools para o Skype for Business Server 2019 requer as seguintes considerações:'
ms.openlocfilehash: e2577b6af1430be90e30fff3236d7ea3cf473cd5
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36237871"
---
# <a name="migrating-multiple-sites-and-pools"></a><span data-ttu-id="309ec-104">Migrar vários sites e pools</span><span class="sxs-lookup"><span data-stu-id="309ec-104">Migrating multiple sites and pools</span></span>

<span data-ttu-id="309ec-105">O Skype for Business Server 2019 oferece suporte a implantações de vários locais e vários pools.</span><span class="sxs-lookup"><span data-stu-id="309ec-105">Skype for Business Server 2019 supports multi-site and multi-pool deployments.</span></span> <span data-ttu-id="309ec-106">O processo de migração de vários pools para o Skype for Business Server 2019 requer as seguintes considerações:</span><span class="sxs-lookup"><span data-stu-id="309ec-106">The process of migrating multiple pools to Skype for Business Server 2019 requires the following considerations:</span></span> 
  
1. <span data-ttu-id="309ec-107">Depois de implantar um pool piloto do Skype for Business Server 2019, você precisa definir um subconjunto de usuários pilotos que serão movidos para o pool do Skype for Business Server 2019 e uma metodologia para validar a funcionalidade dos usuários.</span><span class="sxs-lookup"><span data-stu-id="309ec-107">After deploying a Skype for Business Server 2019 pilot pool, you need to define a subset of pilot users that will be moved to the Skype for Business Server 2019 pool, and a methodology for validating the functionality of the users.</span></span> <span data-ttu-id="309ec-108">Por exemplo, depois de mover um usuário para o pool piloto, verifique se a política de conferência do usuário mudou para o Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="309ec-108">For example, after moving a user to the pilot pool, verify that the user's conference policy has moved to Skype for Business Server 2019.</span></span> 
    
2. <span data-ttu-id="309ec-109">Depois de implantar um servidor de borda no pool piloto, você precisa validar que os usuários externos podem se comunicar com o pool do Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="309ec-109">After deploying an Edge Server in the pilot pool, you need to validate that external users can communicate with the Skype for Business Server 2019 pool.</span></span>

3. <span data-ttu-id="309ec-110">O chat persistente, o espelhamento do SQL e a funcionalidade do XMPP são preteridos no Skype for Business Server 2019 e não estão mais disponíveis como recursos do Skype for Business Server 2019, mas eles podem continuar em um ambiente de coexistência se eles foram implantados anteriormente em um ambiente herdado.</span><span class="sxs-lookup"><span data-stu-id="309ec-110">Persistent Chat, SQL Mirroring, and XMPP functionality are deprecated in Skype for Business Server 2019 and no longer available as Skype for Business Server 2019 features, but they can be continued in a coexistence environment if they were previously deployed in a legacy environment.</span></span> <span data-ttu-id="309ec-111">Se quiser continuar a usar esses recursos, você deve planejar para continuar com um ambiente de coexistência em que determinados usuários permanecerão em pools herdados.</span><span class="sxs-lookup"><span data-stu-id="309ec-111">If you want to continue using these features, you should plan to continue with a coexistence environment where certain users will remain in legacy pools.</span></span>
    
4. <span data-ttu-id="309ec-112">Depois de fazer a transição dos servidores de borda de rotas federadas para os servidores piloto do Skype for Business Server 2019, você precisa validar que os usuários federados podem se comunicar com o pool do Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="309ec-112">After transitioning the federated routes' Edge Servers to the pilot Skype for Business Server 2019 Edge Servers, you need to validate that federated users can communicate with the Skype for Business Server 2019 pool.</span></span>
    
5. <span data-ttu-id="309ec-113">Depois de mover todos os usuários e objetos de contato que não sejam usuários, você precisa validar que o pool herdado está vazio.</span><span class="sxs-lookup"><span data-stu-id="309ec-113">After moving all users and non-user contact objects, you need to validate that the legacy pool is empty.</span></span>
    
6. <span data-ttu-id="309ec-114">Depois de verificar se o pool herdado está vazio, você pode desativar o pool.</span><span class="sxs-lookup"><span data-stu-id="309ec-114">After verifying that the legacy pool is empty, you can then deactivate the pool.</span></span> 
    
    <span data-ttu-id="309ec-115">Para obter detalhes sobre como desativar o pool herdado e os servidores, consulte [fase 8:](phase-8-decommission-legacy-pools.md)descomissionar pools herdados.</span><span class="sxs-lookup"><span data-stu-id="309ec-115">For details about how to deactivate the legacy pool and servers, see [Phase 8: Decommission legacy pools](phase-8-decommission-legacy-pools.md).</span></span>
    

