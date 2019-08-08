---
title: Implantar alta disponibilidade e recuperação de desastre
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 21007bad-62ce-4553-98e0-02aaa1345781
description: O Skype for Business Server oferece alta disponibilidade com pool de servidores, recuperação de desastres com emparelhamento de pool e vários modos de alta disponibilidade de servidor back-end, incluindo grupos de disponibilidade AlwaysOn, espelhamento de banco de dados e cluster de failover de SQL.
ms.openlocfilehash: cb4d39df7f6a12a14c25533d8c6fb1ae95da24d4
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240058"
---
# <a name="deploy-high-availability-and-disaster-recovery"></a><span data-ttu-id="7f026-103">Implantar alta disponibilidade e recuperação de desastre</span><span class="sxs-lookup"><span data-stu-id="7f026-103">Deploy high availability and disaster recovery</span></span>
 
<span data-ttu-id="7f026-104">O Skype for Business Server oferece alta disponibilidade com pool de servidores, recuperação de desastres com emparelhamento de pool e vários modos de alta disponibilidade de servidor back-end, incluindo grupos de disponibilidade AlwaysOn, espelhamento de banco de dados e cluster de failover de SQL.</span><span class="sxs-lookup"><span data-stu-id="7f026-104">Skype for Business Server offers high availability with server pooling, disaster recovery with pool pairing, and several modes of Back End Server high availability, including AlwaysOn Availability groups, database mirroring, and SQL failover clustering.</span></span> 
  
<span data-ttu-id="7f026-105">Alta disponibilidade refere-se a garantir que os serviços do Skype for Business Server estejam disponíveis mesmo se um ou mais servidores ficarem inativos. A recuperação de desastres refere-se à manutenção de serviços em caso de desastres naturais ou naturais, e preservando o máximo de dados de antes do desastre possível.</span><span class="sxs-lookup"><span data-stu-id="7f026-105">High availability refers to making sure that Skype for Business Server services are available even if one or more servers goes down.Disaster recovery refers to keeping services going in the event of a natural or human-caused disaster, and preserving as much data from before the disaster as possible.</span></span>
  
<span data-ttu-id="7f026-106">Esta seção explica como implantar esses recursos e também aborda as etapas que você pode seguir para assegurar alta disponibilidade e recuperação de desastre para algumas das outras funções de servidor.</span><span class="sxs-lookup"><span data-stu-id="7f026-106">This section tells how to deploy these features, and also covers what steps you can take for high availability and disaster recovery for some of your other server roles.</span></span>

> [!NOTE]
> <span data-ttu-id="7f026-107">O espelhamento do SQL está disponível no Skype for Business Server 2015, mas não é mais compatível com o Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="7f026-107">SQL Mirroring is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="7f026-108">Os grupos de disponibilidade AlwaysOn, as instâncias de cluster de failover AlwaysOn (FCI) e os métodos de cluster de failover do SQL são preferidos com o Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="7f026-108">The  AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances (FCI), and SQL failover clustering methods are preferred with Skype for Business Server 2019.</span></span>
  
## <a name="related-sections"></a><span data-ttu-id="7f026-109">Seções relacionadas</span><span class="sxs-lookup"><span data-stu-id="7f026-109">Related sections</span></span>

[<span data-ttu-id="7f026-110">Planeje a alta disponibilidade e a recuperação de desastres no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="7f026-110">Plan for high availability and disaster recovery in Skype for Business Server</span></span>](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)
  
## <a name="see-also"></a><span data-ttu-id="7f026-111">Confira também</span><span class="sxs-lookup"><span data-stu-id="7f026-111">See also</span></span>

[<span data-ttu-id="7f026-112">Implantar um grupo de disponibilidade AlwaysOn em um servidor back-end no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="7f026-112">Deploy an AlwaysOn Availability Group on a Back End Server in Skype for Business Server</span></span>](alwayson-availability-group.md)

[<span data-ttu-id="7f026-113">Implantar pools de front-end emparelhados para recuperação de desastres no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="7f026-113">Deploy paired Front End pools for disaster recovery in Skype for Business Server</span></span>](front-end-pools-for-disaster-recovery.md)
  
[<span data-ttu-id="7f026-114">Implantar espelhamento de SQL para alta disponibilidade do servidor back-end no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="7f026-114">Deploy SQL mirroring for Back End Server high availability in Skype for Business Server 2015</span></span>](sql-mirroring-for-high-availability.md)
  
