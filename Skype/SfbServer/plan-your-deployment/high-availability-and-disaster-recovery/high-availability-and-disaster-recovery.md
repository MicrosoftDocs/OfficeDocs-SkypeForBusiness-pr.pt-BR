---
title: Planejar alta disponibilidade e recuperação de desastre no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.custom:
- ms.lync.plan.HighAvailabilityType
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 3543eb40-54f4-49ef-a058-03aceed4773a
description: 'O Skype for Business Server oferece alta disponibilidade com pool de servidores, recuperação de desastre com emparelhamento de pool e vários modos de alta disponibilidade do Servidor #A0, incluindo grupos de Disponibilidade AlwaysOn, espelhamento de banco de dados e cluster de failover sql.'
ms.openlocfilehash: 61b720bc9dce5bc8dc54a6c493429b0a3c9b27d2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802811"
---
# <a name="plan-for-high-availability-and-disaster-recovery-in-skype-for-business-server"></a><span data-ttu-id="5fe66-103">Planejar alta disponibilidade e recuperação de desastre no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="5fe66-103">Plan for high availability and disaster recovery in Skype for Business Server</span></span>
 
<span data-ttu-id="5fe66-104">O Skype for Business Server oferece alta disponibilidade com pool de servidores, recuperação de desastre com emparelhamento de pool e vários modos de alta disponibilidade do Servidor #A0, incluindo grupos de Disponibilidade AlwaysOn, espelhamento de banco de dados e cluster de failover sql.</span><span class="sxs-lookup"><span data-stu-id="5fe66-104">Skype for Business Server offers high availability with server pooling, disaster recovery with pool pairing, and several modes of Back End Server high availability, including AlwaysOn Availability groups, database mirroring, and SQL failover clustering.</span></span> 
  
<span data-ttu-id="5fe66-105">Alta disponibilidade refere-se a garantir que os serviços do Skype for Business Server estão disponíveis mesmo que um ou mais servidores caiam.</span><span class="sxs-lookup"><span data-stu-id="5fe66-105">High availability refers to making sure that Skype for Business Server services are available even if one or more servers goes down.</span></span> <span data-ttu-id="5fe66-106">A recuperação de desastre refere-se à manutenção dos serviços em caso de desastre natural ou causado por humanos e à preservação da maior parte dos dados de antes do desastre possível.</span><span class="sxs-lookup"><span data-stu-id="5fe66-106">Disaster recovery refers to keeping services going in the event of a natural or human-caused disaster, and preserving as much data from before the disaster as possible.</span></span>
  
<span data-ttu-id="5fe66-107">Como nas versões anteriores do Lync Server, o principal recurso de alta disponibilidade para a maioria das funções de servidor no Skype for Business Server é a redundância de servidor via pooling.</span><span class="sxs-lookup"><span data-stu-id="5fe66-107">As in previous versions of Lync Server, the main high availability feature for most server roles in Skype for Business Server is server redundancy via pooling.</span></span> <span data-ttu-id="5fe66-108">Se um servidor executando uma certa função de servidor falha, os ouros servidores no pool executando a mesma função assumem a carga daquele servidor.</span><span class="sxs-lookup"><span data-stu-id="5fe66-108">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span> <span data-ttu-id="5fe66-109">Isso se aplica a servidores Front-End, Servidores de Borda, Servidores de Mediação e Diretores.</span><span class="sxs-lookup"><span data-stu-id="5fe66-109">This applies to Front End Servers, Edge Servers, Mediation Servers, and Directors.</span></span>
  
<span data-ttu-id="5fe66-110">O Skype for Business Server também fornece opções de recuperação de desastre para pools de Front-End.</span><span class="sxs-lookup"><span data-stu-id="5fe66-110">Skype for Business Server also provides disaster recovery options for Front End pools.</span></span> <span data-ttu-id="5fe66-111">Você pode configurar dois pools em áreas geográficas diferentes para servirem como backups um do outro.</span><span class="sxs-lookup"><span data-stu-id="5fe66-111">You can set up two pools in different geographical areas to serve as backups for each other.</span></span> <span data-ttu-id="5fe66-112">Em seguida, se você tiver um pool ou site inteiro para baixo, o pool de backup pode continuar a fornecer serviço aos usuários em ambos os sites.</span><span class="sxs-lookup"><span data-stu-id="5fe66-112">Then if you have an entire pool or site go down, the backup pool can continue to provide service to users at both sites.</span></span>
  
<span data-ttu-id="5fe66-113">O Skype for Business Server também oferece suporte a quatro modos de alta disponibilidade para seus Servidores #A0: espelhamento SQL, Grupos de Disponibilidade AlwaysOn, Instâncias de Cluster de Failover AlwaysOn (FCI) e clustering de failover sql.</span><span class="sxs-lookup"><span data-stu-id="5fe66-113">Skype for Business Server also supports four modes of high availability for your Back End Servers: SQL mirroring, AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances (FCI), and SQL failover clustering.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5fe66-114">O espelhamento sql está disponível no Skype for Business Server 2015, mas não é mais suportado no Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="5fe66-114">SQL Mirroring is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="5fe66-115">Os grupos de disponibilidade AlwaysOn, instâncias de cluster de failover AlwaysOn (FCI) e métodos de cluster de failover SQL são preferenciais com o Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="5fe66-115">The  AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances (FCI), and SQL failover clustering methods are preferred with Skype for Business Server 2019.</span></span>

> [!NOTE]
> <span data-ttu-id="5fe66-116">Os Grupos de Disponibilidade AlwaysOn não são suportados com Servidores de Chat Persistente.</span><span class="sxs-lookup"><span data-stu-id="5fe66-116">AlwaysOn Availability Groups are not supported with Persistent Chat Servers.</span></span> 
  
<span data-ttu-id="5fe66-117">Esta seção explica esses recursos e também aborda quais etapas você pode seguir para alta disponibilidade e recuperação de desastres para algumas de suas outras funções de servidor.</span><span class="sxs-lookup"><span data-stu-id="5fe66-117">This section explains these features, and also covers what steps you can take for high availability and disaster recovery for some of your other server roles.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="5fe66-118">Confira também</span><span class="sxs-lookup"><span data-stu-id="5fe66-118">See also</span></span>

[<span data-ttu-id="5fe66-119">Alta disponibilidade e gerenciamento do Pool de Front-End</span><span class="sxs-lookup"><span data-stu-id="5fe66-119">Front End Pool high availability and management</span></span>](high-availability.md)
  
[<span data-ttu-id="5fe66-120">Recuperação de desastre do pool de front-end no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="5fe66-120">Front End pool disaster recovery in Skype for Business Server</span></span>](disaster-recovery.md)
  
[<span data-ttu-id="5fe66-121">Experiência do usuário durante falha do pool no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="5fe66-121">User experience during pool failure in Skype for Business Server</span></span>](user-experience.md)
  
[<span data-ttu-id="5fe66-122">Alta disponibilidade do Servidor back-end no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="5fe66-122">Back End Server high availability in Skype for Business Server</span></span>](back-end-server.md)
  
[<span data-ttu-id="5fe66-123">Alta disponibilidade de compartilhamento de arquivos no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="5fe66-123">File sharing high availability in Skype for Business Server</span></span>](file-sharing.md)
