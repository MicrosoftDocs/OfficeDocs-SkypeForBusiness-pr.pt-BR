---
title: Gerenciamento de recuperação de desastres, alta disponibilidade e serviço de backup
ms.reviewer: ''
author: lanachin
ms.author: v-lanac
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Saiba mais sobre os procedimentos para operações de recuperação de desastres, bem como para manter o serviço de backup, que sincroniza os dados em pools front-ends emparelhados.
ms.openlocfilehash: bb8178b98d355159a92d7187884e5502912f4436
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818332"
---
# <a name="managing-skype-for-business-server-disaster-recovery-high-availability-and-backup-service"></a><span data-ttu-id="82f34-103">Gerenciamento de recuperação de desastres do Skype for Business Server, alta disponibilidade e serviço de backup</span><span class="sxs-lookup"><span data-stu-id="82f34-103">Managing Skype for Business Server disaster recovery, high availability, and Backup Service</span></span>

<span data-ttu-id="82f34-104">Esta seção contém procedimentos para operações de recuperação de desastres, bem como para manter o serviço de backup, que sincroniza os dados em pools front-ends emparelhados.</span><span class="sxs-lookup"><span data-stu-id="82f34-104">This section contains procedures for disaster recovery operations, as well as for maintaining the Backup Service, which synchronizes the data in paired Front End pools.</span></span>

<span data-ttu-id="82f34-105">Procedimentos de recuperação de desastre, failover e failback, são manuais.</span><span class="sxs-lookup"><span data-stu-id="82f34-105">Disaster recovery procedures, both failover and failback, are manual.</span></span> <span data-ttu-id="82f34-106">Se houver um desastre, o administrador deve invocar manualmente os procedimentos de failover.</span><span class="sxs-lookup"><span data-stu-id="82f34-106">If there is a disaster, the administrator must manually invoke the failover procedures.</span></span> <span data-ttu-id="82f34-107">O mesmo se aplica a failback após o rereparo do pool.</span><span class="sxs-lookup"><span data-stu-id="82f34-107">The same applies to failback after the pool is repaired.</span></span>

<span data-ttu-id="82f34-108">Os procedimentos de recuperação de desastres nesta seção pressupõem o seguinte:</span><span class="sxs-lookup"><span data-stu-id="82f34-108">The disaster recovery procedures in this section assume the following:</span></span>

  - <span data-ttu-id="82f34-109">Você tem uma implantação com pools front-end emparelhados, localizada em sites diferentes, conforme descrito em [planejar a alta disponibilidade e a recuperação de desastres](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="82f34-109">You have a deployment with paired Front End pools, located in different sites, as described in [Plan for high availability and disaster recovery](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span> <span data-ttu-id="82f34-110">O serviço de backup está em execução nesses pools emparelhados para mantê-los sincronizados.</span><span class="sxs-lookup"><span data-stu-id="82f34-110">The Backup Service has been running on these paired pools to keep them synchronized.</span></span>

  - <span data-ttu-id="82f34-111">Se o repositório de gerenciamento central estiver hospedado em qualquer um dos pools, ele será instalado e executado em ambos os pools emparelhados, com um desses pools que hospeda o mestre ativo e o outro pool que hospeda o modo de espera.</span><span class="sxs-lookup"><span data-stu-id="82f34-111">If the Central Management store is hosted on either pool, it is installed and running on both of the paired pools, with one of those pools hosting the active master and the other pool hosting the standby.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="82f34-112">Nos procedimentos a seguir, o parâmetro *PoolFQDN* refere-se ao FQDN do pool afetado pelo desastre, e não ao pool em que os usuários afetados estão sendo redirecionados.</span><span class="sxs-lookup"><span data-stu-id="82f34-112">In the following procedures, the *PoolFQDN* parameter refers to the FQDN of the pool that is affected by disaster, not the pool that affected users are being redirected from.</span></span> <span data-ttu-id="82f34-113">Para o mesmo conjunto de usuários afetados, ele se refere ao mesmo pool em cmdlets de failover e failback (ou seja, o pool que primeiro hospeda os usuários antes do failover).</span><span class="sxs-lookup"><span data-stu-id="82f34-113">For the same set of affected users, it refers to the same pool in both failover and failback cmdlets (that is, the pool that first homed the users before the failover).</span></span><BR><br><span data-ttu-id="82f34-114">Por exemplo, suponha que um caso em que todos os usuários hospedados em um pool P1 tivessem falhado para o pool de backup, P2.</span><span class="sxs-lookup"><span data-stu-id="82f34-114">For example, assume a case in which all users homed on a pool P1 were failed over to the backup pool, P2.</span></span> <span data-ttu-id="82f34-115">Se o administrador quiser mover todos os usuários atualmente atendidos pelo P2 a serem atendidos pelo P1, o administrador deve executar as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="82f34-115">If the administrator wants to move all the users currently serviced by P2 to be serviced by P1, the administrator must perform the following steps:</span></span> 
> <OL>
> <LI>
> <P><span data-ttu-id="82f34-116">Faça o failback de todos os usuários originalmente hospedados no P1 do P2 para P1 usando o cmdlet failback.</span><span class="sxs-lookup"><span data-stu-id="82f34-116">Fail back all the users originally homed on P1 from P2 to P1 using the failback cmdlet.</span></span> <span data-ttu-id="82f34-117">Nesse caso, o *PoolFQDN* é P1's FQDN.</span><span class="sxs-lookup"><span data-stu-id="82f34-117">In this case, the *PoolFQDN* is P1’s FQDN.</span></span></P>
> <LI>
> <P><span data-ttu-id="82f34-118">Fazer failover de todos os usuários originalmente hospedados no P2 do P1 usando o cmdlet de failover.</span><span class="sxs-lookup"><span data-stu-id="82f34-118">Fail over all the users originally homed on P2 to P1 using the failover cmdlet.</span></span> <span data-ttu-id="82f34-119">Nesse caso, o PoolFQDN é P2's FQDN.</span><span class="sxs-lookup"><span data-stu-id="82f34-119">In this case, the PoolFQDN is P2’s FQDN.</span></span></P>
> <LI>
> <P><span data-ttu-id="82f34-120">Se o administrador mais tarde quiser fazer failback desses usuários de P2 de volta para P2, o PoolFQDN será P2's FQDN.</span><span class="sxs-lookup"><span data-stu-id="82f34-120">If the administrator later wants to fail back those P2 users back to P2, the PoolFQDN is P2’s FQDN.</span></span></P></LI></OL><br><span data-ttu-id="82f34-121">Observe que a etapa 1 acima deve ser realizada antes da etapa 2 para preservar a integridade do pool.</span><span class="sxs-lookup"><span data-stu-id="82f34-121">Note that step 1 above must be performed before step 2 to preserve pool integrity.</span></span> <span data-ttu-id="82f34-122">Se você tentar a etapa 2 antes da etapa 1, o cmdlet etapa 2 falhará.</span><span class="sxs-lookup"><span data-stu-id="82f34-122">If you try step 2 before step 1, the step 2 cmdlet will fail.</span></span>


## <a name="see-also"></a><span data-ttu-id="82f34-123">Confira também</span><span class="sxs-lookup"><span data-stu-id="82f34-123">See Also</span></span>

[<span data-ttu-id="82f34-124">Planejar alta disponibilidade e recuperação de desastre</span><span class="sxs-lookup"><span data-stu-id="82f34-124">Plan for high availability and disaster recovery</span></span>](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md) 
  
