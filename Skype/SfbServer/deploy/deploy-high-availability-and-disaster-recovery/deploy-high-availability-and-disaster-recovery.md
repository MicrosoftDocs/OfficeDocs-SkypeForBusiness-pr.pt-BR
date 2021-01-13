---
title: Implantar alta disponibilidade e recuperação de desastres
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 21007bad-62ce-4553-98e0-02aaa1345781
description: 'O Skype for Business Server oferece alta disponibilidade com pool de servidores, recuperação de desastre com emparelhamento de pool e vários modos de alta disponibilidade do Servidor #A0, incluindo grupos de Disponibilidade AlwaysOn, espelhamento de banco de dados e cluster de failover sql.'
ms.openlocfilehash: 68baae183ff45571e38e922035d287e733bcc930
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830611"
---
# <a name="deploy-high-availability-and-disaster-recovery"></a><span data-ttu-id="afaac-103">Implantar alta disponibilidade e recuperação de desastres</span><span class="sxs-lookup"><span data-stu-id="afaac-103">Deploy high availability and disaster recovery</span></span>
 
<span data-ttu-id="afaac-104">O Skype for Business Server oferece alta disponibilidade com pool de servidores, recuperação de desastre com emparelhamento de pool e vários modos de alta disponibilidade do Servidor #A0, incluindo grupos de Disponibilidade AlwaysOn, espelhamento de banco de dados e cluster de failover sql.</span><span class="sxs-lookup"><span data-stu-id="afaac-104">Skype for Business Server offers high availability with server pooling, disaster recovery with pool pairing, and several modes of Back End Server high availability, including AlwaysOn Availability groups, database mirroring, and SQL failover clustering.</span></span> 
  
<span data-ttu-id="afaac-105">Alta disponibilidade refere-se a garantir que os serviços do Skype for Business Server estão disponíveis mesmo que um ou mais servidores caiam. A recuperação de desastre refere-se a manter os serviços em caso de desastre natural ou causado por humanos e preservar o máximo de dados de antes do desastre possível.</span><span class="sxs-lookup"><span data-stu-id="afaac-105">High availability refers to making sure that Skype for Business Server services are available even if one or more servers goes down.Disaster recovery refers to keeping services going in the event of a natural or human-caused disaster, and preserving as much data from before the disaster as possible.</span></span>
  
<span data-ttu-id="afaac-106">Esta seção mostra como implantar esses recursos e também aborda quais etapas você pode seguir para alta disponibilidade e recuperação de desastres para algumas de suas outras funções de servidor.</span><span class="sxs-lookup"><span data-stu-id="afaac-106">This section tells how to deploy these features, and also covers what steps you can take for high availability and disaster recovery for some of your other server roles.</span></span>

> [!NOTE]
> <span data-ttu-id="afaac-107">O espelhamento sql está disponível no Skype for Business Server 2015, mas não é mais suportado no Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="afaac-107">SQL Mirroring is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="afaac-108">Os grupos de disponibilidade AlwaysOn, instâncias de cluster de failover AlwaysOn (FCI) e métodos de cluster de failover SQL são preferenciais com o Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="afaac-108">The  AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances (FCI), and SQL failover clustering methods are preferred with Skype for Business Server 2019.</span></span>
  
## <a name="related-sections"></a><span data-ttu-id="afaac-109">Seções relacionadas</span><span class="sxs-lookup"><span data-stu-id="afaac-109">Related sections</span></span>

[<span data-ttu-id="afaac-110">Planejar alta disponibilidade e recuperação de desastre no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="afaac-110">Plan for high availability and disaster recovery in Skype for Business Server</span></span>](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)
  
## <a name="see-also"></a><span data-ttu-id="afaac-111">Confira também</span><span class="sxs-lookup"><span data-stu-id="afaac-111">See also</span></span>

[<span data-ttu-id="afaac-112">Implantar um grupo de disponibilidade AlwaysOn em um servidor back-end no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="afaac-112">Deploy an AlwaysOn Availability Group on a Back End Server in Skype for Business Server</span></span>](alwayson-availability-group.md)

[<span data-ttu-id="afaac-113">Implantar pools de front-end emparelhados para recuperação de desastre no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="afaac-113">Deploy paired Front End pools for disaster recovery in Skype for Business Server</span></span>](front-end-pools-for-disaster-recovery.md)
  
[<span data-ttu-id="afaac-114">Implantar espelhamento SQL para alta disponibilidade do Servidor #A0 no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="afaac-114">Deploy SQL mirroring for Back End Server high availability in Skype for Business Server 2015</span></span>](sql-mirroring-for-high-availability.md)
  
