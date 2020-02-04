---
title: Planeje a alta disponibilidade e a recuperação de desastres no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
f1.keywords:
- ms.lync.plan.HighAvailabilityType
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 3543eb40-54f4-49ef-a058-03aceed4773a
description: O Skype for Business Server oferece alta disponibilidade com pool de servidores, recuperação de desastres com emparelhamento de pool e vários modos de alta disponibilidade de servidor back-end, incluindo grupos de disponibilidade AlwaysOn, espelhamento de banco de dados e cluster de failover de SQL.
ms.openlocfilehash: 31059936249aa4e691f3e6b4b467841fd66a04ea
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41695966"
---
# <a name="plan-for-high-availability-and-disaster-recovery-in-skype-for-business-server"></a><span data-ttu-id="b9aac-103">Planeje a alta disponibilidade e a recuperação de desastres no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="b9aac-103">Plan for high availability and disaster recovery in Skype for Business Server</span></span>
 
<span data-ttu-id="b9aac-104">O Skype for Business Server oferece alta disponibilidade com pool de servidores, recuperação de desastres com emparelhamento de pool e vários modos de alta disponibilidade de servidor back-end, incluindo grupos de disponibilidade AlwaysOn, espelhamento de banco de dados e cluster de failover de SQL.</span><span class="sxs-lookup"><span data-stu-id="b9aac-104">Skype for Business Server offers high availability with server pooling, disaster recovery with pool pairing, and several modes of Back End Server high availability, including AlwaysOn Availability groups, database mirroring, and SQL failover clustering.</span></span> 
  
<span data-ttu-id="b9aac-105">Alta disponibilidade refere-se a garantir que os serviços do Skype for Business Server estejam disponíveis mesmo se um ou mais servidores ficarem inativos.</span><span class="sxs-lookup"><span data-stu-id="b9aac-105">High availability refers to making sure that Skype for Business Server services are available even if one or more servers goes down.</span></span> <span data-ttu-id="b9aac-106">Disaster recovery refers to keeping services going in the event of a natural or human-caused disaster, and preserving as much data from before the disaster as possible.</span><span class="sxs-lookup"><span data-stu-id="b9aac-106">Disaster recovery refers to keeping services going in the event of a natural or human-caused disaster, and preserving as much data from before the disaster as possible.</span></span>
  
<span data-ttu-id="b9aac-107">Como nas versões anteriores do Lync Server, o principal recurso de alta disponibilidade para a maioria das funções de servidor no Skype for Business Server é a redundância do servidor via pooling.</span><span class="sxs-lookup"><span data-stu-id="b9aac-107">As in previous versions of Lync Server, the main high availability feature for most server roles in Skype for Business Server is server redundancy via pooling.</span></span> <span data-ttu-id="b9aac-108">Se um servidor que executa determinada função falhar, os demais servidores do pool que executam a mesma função assumirão a carga desse servidor.</span><span class="sxs-lookup"><span data-stu-id="b9aac-108">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span> <span data-ttu-id="b9aac-109">Isso se aplica a Servidores Front-End, Servidores de Borda, Servidores de Mediação e Diretores.</span><span class="sxs-lookup"><span data-stu-id="b9aac-109">This applies to Front End Servers, Edge Servers, Mediation Servers, and Directors.</span></span>
  
<span data-ttu-id="b9aac-110">O Skype for Business Server também fornece opções de recuperação de desastres para pools front-end.</span><span class="sxs-lookup"><span data-stu-id="b9aac-110">Skype for Business Server also provides disaster recovery options for Front End pools.</span></span> <span data-ttu-id="b9aac-111">Você pode configurar dois pools em diferentes áreas geográficas para servirem de backup um do outro.</span><span class="sxs-lookup"><span data-stu-id="b9aac-111">You can set up two pools in different geographical areas to serve as backups for each other.</span></span> <span data-ttu-id="b9aac-112">Assim, se um local ou pool inteiro ficar inoperante, o pool de backup continuará fornecendo serviço aos usuários de ambos os locais.</span><span class="sxs-lookup"><span data-stu-id="b9aac-112">Then if you have an entire pool or site go down, the backup pool can continue to provide service to users at both sites.</span></span>
  
<span data-ttu-id="b9aac-113">O Skype for Business Server também oferece suporte a quatro modos de alta disponibilidade para seus servidores back-end: espelhamento do SQL, grupos de disponibilidade AlwaysOn, instâncias de cluster de failover AlwaysOn (FCI) e cluster de failover do SQL.</span><span class="sxs-lookup"><span data-stu-id="b9aac-113">Skype for Business Server also supports four modes of high availability for your Back End Servers: SQL mirroring, AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances (FCI), and SQL failover clustering.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b9aac-114">O espelhamento do SQL está disponível no Skype for Business Server 2015, mas não é mais compatível com o Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="b9aac-114">SQL Mirroring is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="b9aac-115">Os grupos de disponibilidade AlwaysOn, as instâncias de cluster de failover AlwaysOn (FCI) e os métodos de cluster de failover do SQL são preferidos com o Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="b9aac-115">The  AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances (FCI), and SQL failover clustering methods are preferred with Skype for Business Server 2019.</span></span>

> [!NOTE]
> <span data-ttu-id="b9aac-116">Os grupos de disponibilidade AlwaysOn não são compatíveis com servidores de chat persistentes.</span><span class="sxs-lookup"><span data-stu-id="b9aac-116">AlwaysOn Availability Groups are not supported with Persistent Chat Servers.</span></span> 
  
<span data-ttu-id="b9aac-117">Esta seção explica esses recursos de alta disponibilidade e também detalha os passos que você pode tomar para ter alta disponibilidade e recuperação de desastres em algumas das demais funções de servidor.</span><span class="sxs-lookup"><span data-stu-id="b9aac-117">This section explains these features, and also covers what steps you can take for high availability and disaster recovery for some of your other server roles.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="b9aac-118">Confira também</span><span class="sxs-lookup"><span data-stu-id="b9aac-118">See also</span></span>

[<span data-ttu-id="b9aac-119">Alta disponibilidade e gerenciamento de Pool de Front-Ends</span><span class="sxs-lookup"><span data-stu-id="b9aac-119">Front End Pool high availability and management</span></span>](high-availability.md)
  
[<span data-ttu-id="b9aac-120">Recuperação de desastre do pool de front-end no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="b9aac-120">Front End pool disaster recovery in Skype for Business Server</span></span>](disaster-recovery.md)
  
[<span data-ttu-id="b9aac-121">Experiência do usuário durante uma falha de pool no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="b9aac-121">User experience during pool failure in Skype for Business Server</span></span>](user-experience.md)
  
[<span data-ttu-id="b9aac-122">Back-end Server alta disponibilidade no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="b9aac-122">Back End Server high availability in Skype for Business Server</span></span>](back-end-server.md)
  
[<span data-ttu-id="b9aac-123">Compartilhamento de arquivos com alta disponibilidade no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="b9aac-123">File sharing high availability in Skype for Business Server</span></span>](file-sharing.md)
