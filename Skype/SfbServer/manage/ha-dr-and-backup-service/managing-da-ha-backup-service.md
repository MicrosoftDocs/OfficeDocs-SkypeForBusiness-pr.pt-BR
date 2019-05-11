---
title: Gerenciando o serviço de Backup, alta disponibilidade e recuperação de desastres
ms.reviewer: ''
author: lanachin
ms.author: v-lanac
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Saiba mais sobre os procedimentos para operações de recuperação de desastres, bem como para manter o serviço de Backup, que sincroniza os dados nos pools de Front-Ends emparelhados.
ms.openlocfilehash: 9215dba11b388b3ffbd3e5c0f3de4ccf1cb85c7d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33903127"
---
# <a name="managing-skype-for-business-server-disaster-recovery-high-availability-and-backup-service"></a><span data-ttu-id="2bc7b-103">Gerenciando Skype para o serviço de Backup, alta disponibilidade e recuperação de desastres Business Server</span><span class="sxs-lookup"><span data-stu-id="2bc7b-103">Managing Skype for Business Server disaster recovery, high availability, and Backup Service</span></span>

<span data-ttu-id="2bc7b-104">Esta seção contém procedimentos para operações de recuperação de desastres, bem como para manter o serviço de Backup, que sincroniza os dados nos pools de Front-Ends emparelhados.</span><span class="sxs-lookup"><span data-stu-id="2bc7b-104">This section contains procedures for disaster recovery operations, as well as for maintaining the Backup Service, which synchronizes the data in paired Front End pools.</span></span>

<span data-ttu-id="2bc7b-105">Procedimentos de recuperação de desastres, failover e failback, são manuais.</span><span class="sxs-lookup"><span data-stu-id="2bc7b-105">Disaster recovery procedures, both failover and failback, are manual.</span></span> <span data-ttu-id="2bc7b-106">Se houver um desastre, o administrador deve chamar manualmente os procedimentos de failover.</span><span class="sxs-lookup"><span data-stu-id="2bc7b-106">If there is a disaster, the administrator must manually invoke the failover procedures.</span></span> <span data-ttu-id="2bc7b-107">O mesmo se aplica a failback depois que o pool for reparado.</span><span class="sxs-lookup"><span data-stu-id="2bc7b-107">The same applies to failback after the pool is repaired.</span></span>

<span data-ttu-id="2bc7b-108">Os procedimentos de recuperação de desastres nesta seção supõem o seguinte:</span><span class="sxs-lookup"><span data-stu-id="2bc7b-108">The disaster recovery procedures in this section assume the following:</span></span>

  - <span data-ttu-id="2bc7b-109">Você possuir uma implantação com emparelhados pools de Front-End, localizado em diferentes sites, conforme descrito em [plano para alta disponibilidade e recuperação de desastres](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="2bc7b-109">You have a deployment with paired Front End pools, located in different sites, as described in [Plan for high availability and disaster recovery](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span> <span data-ttu-id="2bc7b-110">O serviço de Backup está sendo executado nesses pools emparelhados para mantê-los sincronizados.</span><span class="sxs-lookup"><span data-stu-id="2bc7b-110">The Backup Service has been running on these paired pools to keep them synchronized.</span></span>

  - <span data-ttu-id="2bc7b-111">Se o repositório de gerenciamento Central está hospedado em um pool, é instalado e em execução em ambos os pools emparelhados, com um desses pools que hospedam o mestre ativo e outro pool hospedando em espera.</span><span class="sxs-lookup"><span data-stu-id="2bc7b-111">If the Central Management store is hosted on either pool, it is installed and running on both of the paired pools, with one of those pools hosting the active master and the other pool hosting the standby.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2bc7b-112">Nos procedimentos a seguir, o parâmetro *PoolFQDN* se refere ao FQDN do pool que é afetado por desastre, não o pool que afetaram os usuários são redirecionadas a partir do.</span><span class="sxs-lookup"><span data-stu-id="2bc7b-112">In the following procedures, the *PoolFQDN* parameter refers to the FQDN of the pool that is affected by disaster, not the pool that affected users are being redirected from.</span></span> <span data-ttu-id="2bc7b-113">Para o mesmo conjunto de usuários afetados, ele se refere ao mesmo pool nos cmdlets de failover e failback (ou seja, o pool que primeiro hospedados os usuários antes do failover).</span><span class="sxs-lookup"><span data-stu-id="2bc7b-113">For the same set of affected users, it refers to the same pool in both failover and failback cmdlets (that is, the pool that first homed the users before the failover).</span></span><BR><br><span data-ttu-id="2bc7b-114">Por exemplo, suponha que um caso em que todos os usuários hospedados em um pool P1 sofreram failover para o pool de backup, P2.</span><span class="sxs-lookup"><span data-stu-id="2bc7b-114">For example, assume a case in which all users homed on a pool P1 were failed over to the backup pool, P2.</span></span> <span data-ttu-id="2bc7b-115">Se o administrador deseja mover todos os usuários atualmente atendidos pelo P2 sejam atendidas pelo P1, o administrador deve executar as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="2bc7b-115">If the administrator wants to move all the users currently serviced by P2 to be serviced by P1, the administrator must perform the following steps:</span></span> 
> <OL>
> <LI>
> <P><span data-ttu-id="2bc7b-116">Fazer o fail todos os usuários originalmente hospedados no P1 de P2 a P1 usando o cmdlet de failback.</span><span class="sxs-lookup"><span data-stu-id="2bc7b-116">Fail back all the users originally homed on P1 from P2 to P1 using the failback cmdlet.</span></span> <span data-ttu-id="2bc7b-117">Nesse caso, o *PoolFQDN* é P1 FQDN.</span><span class="sxs-lookup"><span data-stu-id="2bc7b-117">In this case, the *PoolFQDN* is P1’s FQDN.</span></span></P>
> <LI>
> <P><span data-ttu-id="2bc7b-118">Failover de todos os usuários originalmente hospedados no P2 a P1 usando o cmdlet de failover.</span><span class="sxs-lookup"><span data-stu-id="2bc7b-118">Fail over all the users originally homed on P2 to P1 using the failover cmdlet.</span></span> <span data-ttu-id="2bc7b-119">Nesse caso, o PoolFQDN é do P2 FQDN.</span><span class="sxs-lookup"><span data-stu-id="2bc7b-119">In this case, the PoolFQDN is P2’s FQDN.</span></span></P>
> <LI>
> <P><span data-ttu-id="2bc7b-120">Se o administrador deseje posteriormente failback esses usuários P2 para o P2, o PoolFQDN é do P2 FQDN.</span><span class="sxs-lookup"><span data-stu-id="2bc7b-120">If the administrator later wants to fail back those P2 users back to P2, the PoolFQDN is P2’s FQDN.</span></span></P></LI></OL><br><span data-ttu-id="2bc7b-121">Observe que essa etapa 1 acima deve ser executada antes da etapa 2 para preservar a integridade do pool.</span><span class="sxs-lookup"><span data-stu-id="2bc7b-121">Note that step 1 above must be performed before step 2 to preserve pool integrity.</span></span> <span data-ttu-id="2bc7b-122">Se você tentar etapa 2 antes da etapa 1, o cmdlet de etapa 2 falhará.</span><span class="sxs-lookup"><span data-stu-id="2bc7b-122">If you try step 2 before step 1, the step 2 cmdlet will fail.</span></span>


## <a name="see-also"></a><span data-ttu-id="2bc7b-123">Confira também</span><span class="sxs-lookup"><span data-stu-id="2bc7b-123">See Also</span></span>

[<span data-ttu-id="2bc7b-124">Planejar alta disponibilidade e recuperação de desastre</span><span class="sxs-lookup"><span data-stu-id="2bc7b-124">Plan for high availability and disaster recovery</span></span>](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md) 
  
