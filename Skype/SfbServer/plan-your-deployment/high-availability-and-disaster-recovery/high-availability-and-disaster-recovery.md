---
title: Planejamento para alta disponibilidade e recuperação de desastre no Skype for Business Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 1/29/2018
ms.audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.lync.plan.HighAvailabilityType
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 3543eb40-54f4-49ef-a058-03aceed4773a
description: Skype para Business Server oferece alta disponibilidade com servidor pooling de recuperação de desastres com pareamento do pool e vários modos de alta disponibilidade servidor Back-End, incluindo grupos de disponibilidade do AlwaysOn, espelhamento de banco de dados e o cluster de failover do SQL.
ms.openlocfilehash: e2e433112146e3be771abb12ef50e09749e8e325
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="plan-for-high-availability-and-disaster-recovery-in-skype-for-business-server-2015"></a><span data-ttu-id="17889-103">Planejamento para alta disponibilidade e recuperação de desastre no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="17889-103">Plan for high availability and disaster recovery in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="17889-104">Skype para Business Server oferece alta disponibilidade com servidor pooling de recuperação de desastres com pareamento do pool e vários modos de alta disponibilidade servidor Back-End, incluindo grupos de disponibilidade do AlwaysOn, espelhamento de banco de dados e o cluster de failover do SQL.</span><span class="sxs-lookup"><span data-stu-id="17889-104">Skype for Business Server offers high availability with server pooling, disaster recovery with pool pairing, and several modes of Back End Server high availability, including AlwaysOn Availability groups, database mirroring, and SQL failover clustering.</span></span> 
  
<span data-ttu-id="17889-105">Alta disponibilidade refere-se ao certificando-se de que o Skype para serviços de Business Server estão disponíveis, mesmo se um ou mais servidores cair.</span><span class="sxs-lookup"><span data-stu-id="17889-105">High availability refers to making sure that Skype for Business Server services are available even if one or more servers goes down.</span></span> <span data-ttu-id="17889-106">Recuperação de desastre significa manter esses servidores em atividade na ocorrência de um desastre natural ou causado pelo homem, e preservar, na medida do possível, os dados anteriores ao desastre.</span><span class="sxs-lookup"><span data-stu-id="17889-106">Disaster recovery refers to keeping services going in the event of a natural or human-caused disaster, and preserving as much data from before the disaster as possible.</span></span>
  
<span data-ttu-id="17889-107">Como nas versões anteriores do Microsoft Lync Server, o recurso de alta disponibilidade principal para a maioria das funções de servidor em Skype para Business Server é redundância de servidor por meio do pool.</span><span class="sxs-lookup"><span data-stu-id="17889-107">As in previous versions of Lync Server, the main high availability feature for most server roles in Skype for Business Server is server redundancy via pooling.</span></span> <span data-ttu-id="17889-108">Se um servidor que executa determinada função falhar, os demais servidores do pool que executam a mesma função assumirão a carga desse servidor.</span><span class="sxs-lookup"><span data-stu-id="17889-108">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span> <span data-ttu-id="17889-109">Isso se aplica a Servidores Front-End, Servidores de Borda, Servidores de Mediação e Diretores.</span><span class="sxs-lookup"><span data-stu-id="17889-109">This applies to Front End Servers, Edge Servers, Mediation Servers, and Directors.</span></span>
  
<span data-ttu-id="17889-110">Skype para Business Server também oferece desastres opções de recuperação para pools de Front-End.</span><span class="sxs-lookup"><span data-stu-id="17889-110">Skype for Business Server also provides disaster recovery options for Front End pools.</span></span> <span data-ttu-id="17889-111">Você pode configurar dois pools em diferentes áreas geográficas para servirem de backup um do outro.</span><span class="sxs-lookup"><span data-stu-id="17889-111">You can set up two pools in different geographical areas to serve as backups for each other.</span></span> <span data-ttu-id="17889-112">Assim, se um local ou pool inteiro ficar inoperante, o pool de backup continuará fornecendo serviço aos usuários de ambos os locais.</span><span class="sxs-lookup"><span data-stu-id="17889-112">Then if you have an entire pool or site go down, the backup pool can continue to provide service to users at both sites.</span></span>
  
<span data-ttu-id="17889-113">Skype para Business Server também oferece suporte a quatro modos de alta disponibilidade para seus servidores Back-End: grupos de disponibilidade AlwaysOn, espelhamento de banco de dados, instâncias de Cluster de Failover AlwaysOn (FCI) e clustering de failover do SQL.</span><span class="sxs-lookup"><span data-stu-id="17889-113">Skype for Business Server also supports four modes of high availability for your Back End Servers: database mirroring, AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances (FCI), and SQL failover clustering.</span></span>
  
> [!NOTE]
> <span data-ttu-id="17889-114">Não há suporte para grupos de disponibilidade do AlwaysOn com servidores de Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="17889-114">AlwaysOn Availability Groups are not supported with Persistent Chat Servers.</span></span> 
  
<span data-ttu-id="17889-115">Esta seção explica esses recursos de alta disponibilidade e também detalha os passos que você pode tomar para ter alta disponibilidade e recuperação de desastres em algumas das demais funções de servidor.</span><span class="sxs-lookup"><span data-stu-id="17889-115">This section explains these features, and also covers what steps you can take for high availability and disaster recovery for some of your other server roles.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="17889-116">Consulte também</span><span class="sxs-lookup"><span data-stu-id="17889-116">See also</span></span>

#### 

[<span data-ttu-id="17889-117">Gerenciamento e alta disponibilidade de front End Pool</span><span class="sxs-lookup"><span data-stu-id="17889-117">Front End Pool high availability and management</span></span>](high-availability.md)
  
[<span data-ttu-id="17889-118">Front-End pool disaster recovery no Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="17889-118">Front End pool disaster recovery in Skype for Business Server 2015</span></span>](disaster-recovery.md)
  
[<span data-ttu-id="17889-119">Experiência do usuário durante falha do pool no Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="17889-119">User experience during pool failure in Skype for Business Server 2015</span></span>](user-experience.md)
  
[<span data-ttu-id="17889-120">Back End alta disponibilidade do servidor no Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="17889-120">Back End Server high availability in Skype for Business Server 2015</span></span>](back-end-server.md)
  
[<span data-ttu-id="17889-121">Alta disponibilidade de compartilhamento de arquivos no Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="17889-121">File sharing high availability in Skype for Business Server 2015</span></span>](file-sharing.md)

