---
title: Gerenciando recuperação de desastre, alta disponibilidade e Serviço de Backup
ms.reviewer: ''
author: cichur
ms.author: v-cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Saiba mais sobre os procedimentos para operações de recuperação de desastres, bem como para manter o Serviço de Backup, que sincroniza os dados em pools de Front-End emparelhados.
ms.openlocfilehash: e486a71203b64b4fc351888869ac64a24689ba7b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817151"
---
# <a name="managing-skype-for-business-server-disaster-recovery-high-availability-and-backup-service"></a><span data-ttu-id="f1dc9-103">Gerenciamento de recuperação de desastre, alta disponibilidade e Serviço de Backup do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="f1dc9-103">Managing Skype for Business Server disaster recovery, high availability, and Backup Service</span></span>

<span data-ttu-id="f1dc9-104">Esta seção contém procedimentos para operações de recuperação de desastres, bem como para manter o Serviço de Backup, que sincroniza os dados em pools de Front-End emparelhados.</span><span class="sxs-lookup"><span data-stu-id="f1dc9-104">This section contains procedures for disaster recovery operations, as well as for maintaining the Backup Service, which synchronizes the data in paired Front End pools.</span></span>

<span data-ttu-id="f1dc9-p101">Os procedimentos de recuperação de desastres, o failover e o failback, são manuais. Se ocorrer um desastre, o administrador deve chamar manualmente os procedimentos de failover. O mesmo se aplica ao failback após a reparação do pool.</span><span class="sxs-lookup"><span data-stu-id="f1dc9-p101">Disaster recovery procedures, both failover and failback, are manual. If there is a disaster, the administrator must manually invoke the failover procedures. The same applies to failback after the pool is repaired.</span></span>

<span data-ttu-id="f1dc9-108">Os procedimentos de recuperação de desastres nesta seção pressupom o seguinte:</span><span class="sxs-lookup"><span data-stu-id="f1dc9-108">The disaster recovery procedures in this section assume the following:</span></span>

  - <span data-ttu-id="f1dc9-109">Você tem uma implantação com pools de front-end emparelhados, localizados em sites diferentes, conforme descrito em Planejar alta [disponibilidade e recuperação de desastres.](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)</span><span class="sxs-lookup"><span data-stu-id="f1dc9-109">You have a deployment with paired Front End pools, located in different sites, as described in [Plan for high availability and disaster recovery](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span> <span data-ttu-id="f1dc9-110">O Serviço de Backup é executado nestes pools emparelhados para mantê-los sincronizados.</span><span class="sxs-lookup"><span data-stu-id="f1dc9-110">The Backup Service has been running on these paired pools to keep them synchronized.</span></span>

  - <span data-ttu-id="f1dc9-111">Se o armazenamento de Gerenciamento Central estiver hospedado em qualquer pool, ele será instalado e executado em ambos os pools emparelhados, com um desses pools hospedando o mestre ativo e o outro pool hospedando o modo de espera.</span><span class="sxs-lookup"><span data-stu-id="f1dc9-111">If the Central Management store is hosted on either pool, it is installed and running on both of the paired pools, with one of those pools hosting the active master and the other pool hosting the standby.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f1dc9-p103">Nos procedimentos a seguir, o parâmetro *PoolFQDN* se refere ao FQDN do pool afetado pelo desastre, e não o pool para o qual os usuários afetados foram redirecionados. Para o mesmo conjunto de usuários afetados, ele se refere ao mesmo pool em ambos os cmdlets de failover e failback (ou seja, o pool que primeiramente hospedou os usuários antes do failover).</span><span class="sxs-lookup"><span data-stu-id="f1dc9-p103">In the following procedures, the *PoolFQDN* parameter refers to the FQDN of the pool that is affected by disaster, not the pool that affected users are being redirected from. For the same set of affected users, it refers to the same pool in both failover and failback cmdlets (that is, the pool that first homed the users before the failover).</span></span><BR><br><span data-ttu-id="f1dc9-p104">Por exemplo, pressuponha um caso em que todos os usuários hospedados no pool P1 foram transferidos para o pool de backup, o P2. Se o administrador deseja mover todos os usuários que utilizam os serviços de P2 para utilizarem os serviços de P1, o administrador deve executar as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="f1dc9-p104">For example, assume a case in which all users homed on a pool P1 were failed over to the backup pool, P2. If the administrator wants to move all the users currently serviced by P2 to be serviced by P1, the administrator must perform the following steps:</span></span> 
> <OL>
> <LI>
> <P><span data-ttu-id="f1dc9-p105">Retorne do P2 para o P1 todos os usuários originalmente hospedados em P1 utilizando o cmdlet de failback. Nesse caso, *PoolFQDN* é o FQDN de P1.</span><span class="sxs-lookup"><span data-stu-id="f1dc9-p105">Fail back all the users originally homed on P1 from P2 to P1 using the failback cmdlet. In this case, the *PoolFQDN* is P1’s FQDN.</span></span></P>
> <LI>
> <P><span data-ttu-id="f1dc9-118">Transfira todos os usuários originalmente hospedados em P2 para o P1 utilizando o cmdlet de failover.</span><span class="sxs-lookup"><span data-stu-id="f1dc9-118">Fail over all the users originally homed on P2 to P1 using the failover cmdlet.</span></span> <span data-ttu-id="f1dc9-119">Nesse caso, a propriedade PoolFQDN é o FQDN de P2.</span><span class="sxs-lookup"><span data-stu-id="f1dc9-119">In this case, the PoolFQDN is P2’s FQDN.</span></span></P>
> <LI>
> <P><span data-ttu-id="f1dc9-120">Se o administrador desejar retornar posteriormente os usuários para o P2, o PoolFQDN é o FQDN do P2.</span><span class="sxs-lookup"><span data-stu-id="f1dc9-120">If the administrator later wants to fail back those P2 users back to P2, the PoolFQDN is P2’s FQDN.</span></span></P></LI></OL><br><span data-ttu-id="f1dc9-p107">Observe que a etapa 1 acima deve ser realizada antes da etapa 2 para preservar a integridade do pool. Se você executar a etapa 2 antes da etapa 1, o cmdlet da etapa 2 falhará.</span><span class="sxs-lookup"><span data-stu-id="f1dc9-p107">Note that step 1 above must be performed before step 2 to preserve pool integrity. If you try step 2 before step 1, the step 2 cmdlet will fail.</span></span>


## <a name="see-also"></a><span data-ttu-id="f1dc9-123">Confira também</span><span class="sxs-lookup"><span data-stu-id="f1dc9-123">See Also</span></span>

[<span data-ttu-id="f1dc9-124">Planejar alta disponibilidade e recuperação de desastre</span><span class="sxs-lookup"><span data-stu-id="f1dc9-124">Plan for high availability and disaster recovery</span></span>](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md) 
  
