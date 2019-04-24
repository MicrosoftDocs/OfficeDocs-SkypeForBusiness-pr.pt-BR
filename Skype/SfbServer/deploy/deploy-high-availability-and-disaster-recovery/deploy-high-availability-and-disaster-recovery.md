---
title: Implantar alta disponibilidade e recuperação de desastre
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 21007bad-62ce-4553-98e0-02aaa1345781
description: Skype para Business Server oferece alta disponibilidade com servidor pooling de recuperação de desastres com pareamento do pool e vários modos de alta disponibilidade servidor Back-End, incluindo grupos de disponibilidade do AlwaysOn, espelhamento de banco de dados e o cluster de failover do SQL.
ms.openlocfilehash: bbd3c4092962e757a7565f1da054c82438a79ded
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32225494"
---
# <a name="deploy-high-availability-and-disaster-recovery"></a><span data-ttu-id="e5f41-103">Implantar alta disponibilidade e recuperação de desastre</span><span class="sxs-lookup"><span data-stu-id="e5f41-103">Deploy high availability and disaster recovery</span></span>
 
<span data-ttu-id="e5f41-104">Skype para Business Server oferece alta disponibilidade com servidor pooling de recuperação de desastres com pareamento do pool e vários modos de alta disponibilidade servidor Back-End, incluindo grupos de disponibilidade do AlwaysOn, espelhamento de banco de dados e o cluster de failover do SQL.</span><span class="sxs-lookup"><span data-stu-id="e5f41-104">Skype for Business Server offers high availability with server pooling, disaster recovery with pool pairing, and several modes of Back End Server high availability, including AlwaysOn Availability groups, database mirroring, and SQL failover clustering.</span></span> 
  
<span data-ttu-id="e5f41-105">Alta disponibilidade refere-se ao certificando-se de que o Skype para serviços de Business Server estão disponíveis, mesmo se um ou mais servidores cair. Recuperação de desastres refere-se aos serviços keeping indo em caso de um desastre natural ou causado por humanos e preservação de todos os dados antes do desastre possível.</span><span class="sxs-lookup"><span data-stu-id="e5f41-105">High availability refers to making sure that Skype for Business Server services are available even if one or more servers goes down.Disaster recovery refers to keeping services going in the event of a natural or human-caused disaster, and preserving as much data from before the disaster as possible.</span></span>
  
<span data-ttu-id="e5f41-106">Esta seção explica como implantar esses recursos e também aborda as etapas que você pode seguir para assegurar alta disponibilidade e recuperação de desastre para algumas das outras funções de servidor.</span><span class="sxs-lookup"><span data-stu-id="e5f41-106">This section tells how to deploy these features, and also covers what steps you can take for high availability and disaster recovery for some of your other server roles.</span></span>

> [!NOTE]
> <span data-ttu-id="e5f41-107">Espelhamento do SQL está disponível no Skype para Business Server 2015, mas não é mais suportado no Skype para Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="e5f41-107">SQL Mirroring is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="e5f41-108">Os métodos de cluster de failover de grupos de disponibilidade AlwaysOn, instâncias de Cluster de Failover AlwaysOn (FCI) e SQL terão preferência com Skype para Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="e5f41-108">The  AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances (FCI), and SQL failover clustering methods are preferred with Skype for Business Server 2019.</span></span>
  
## <a name="related-sections"></a><span data-ttu-id="e5f41-109">Seções relacionadas</span><span class="sxs-lookup"><span data-stu-id="e5f41-109">Related sections</span></span>

[<span data-ttu-id="e5f41-110">Planejar para alta disponibilidade e recuperação de desastres no Skype Business Server</span><span class="sxs-lookup"><span data-stu-id="e5f41-110">Plan for high availability and disaster recovery in Skype for Business Server</span></span>](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)
  
## <a name="see-also"></a><span data-ttu-id="e5f41-111">Confira também</span><span class="sxs-lookup"><span data-stu-id="e5f41-111">See also</span></span>

[<span data-ttu-id="e5f41-112">Implantar um grupo de disponibilidade do AlwaysOn em um servidor de Back-End no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="e5f41-112">Deploy an AlwaysOn Availability Group on a Back End Server in Skype for Business Server</span></span>](alwayson-availability-group.md)

[<span data-ttu-id="e5f41-113">Implantar pools de Front-End pareados para recuperação de desastres em Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="e5f41-113">Deploy paired Front End pools for disaster recovery in Skype for Business Server</span></span>](front-end-pools-for-disaster-recovery.md)
  
[<span data-ttu-id="e5f41-114">Implantar espelhamento de SQL para alta disponibilidade do servidor back-end no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="e5f41-114">Deploy SQL mirroring for Back End Server high availability in Skype for Business Server 2015</span></span>](sql-mirroring-for-high-availability.md)
  
