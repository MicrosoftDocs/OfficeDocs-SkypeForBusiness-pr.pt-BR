---
title: Lync Server 2013 tempo de recuperação para failover de pool e failback de pool
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Recovery time for pool failover and pool failback
ms:assetid: 902c658f-8442-4d0d-b3ad-bf795ecd550d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205079(v=OCS.15)
ms:contentKeyID: 48184786
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fb165fa762b23bd271dde56c0846ccb18adfbf7f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42183244"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="recovery-time-for-pool-failover-and-pool-failback-in-lync-server-2013"></a><span data-ttu-id="8e42d-102">Tempo de recuperação para failover de pool e failback de pool no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8e42d-102">Recovery time for pool failover and pool failback in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8e42d-103">_**Última modificação do tópico:** 2012-09-10_</span><span class="sxs-lookup"><span data-stu-id="8e42d-103">_**Topic Last Modified:** 2012-09-10_</span></span>

<span data-ttu-id="8e42d-p101">Para failover e failback de pool, o alvo projetado para objetivo de tempo de recuperação (RTO) é de 30 minutos. Este é o tempo necessário para o failover acontecer, após os administradores terem determinado que houve um desastre e iniciar os procedimentos de failover. Isso não inclui o tempo para os administradores avaliarem a situação e tomar uma decisão, nem inclui o tempo dos usuários entrarem novamente após o failover ser concluído.</span><span class="sxs-lookup"><span data-stu-id="8e42d-p101">For pool failover and pool failback, the engineering target for recovery time objective (RTO) is 30 minutes. This is the time required for the failover to happen, after administrators have determined there was a disaster and initiated the failover procedures. It does not include the time for administrators to assess the situation and make a decision, nor does it include the time for users to sign in again after failover is complete.</span></span>

<span data-ttu-id="8e42d-107">Para failover e failback de pool, o alvo projetado para objetivo de tempo de recuperação (RTO) é de 30 minutos.</span><span class="sxs-lookup"><span data-stu-id="8e42d-107">For pool failover and pool failback, the engineering target for recovery point objective (RPO) is 30 minutes.</span></span> <span data-ttu-id="8e42d-108">Isso representa o tempo medido dos dados que pode ser perdido devido ao desastre, devido à latência de replicação do serviço de backup.</span><span class="sxs-lookup"><span data-stu-id="8e42d-108">This represents the time measure of data that could be lost due to the disaster, due to replication latency of the Backup Service.</span></span> <span data-ttu-id="8e42d-109">Por exemplo, se um pool for desativado às 10:00 A.M., e o RPO for de 30 minutos, os dados gravados no pool entre 9:30 A.M.</span><span class="sxs-lookup"><span data-stu-id="8e42d-109">For example, if a pool goes down at 10:00 A.M., and the RPO is 30 minutes, data written to the pool between 9:30 A.M.</span></span> <span data-ttu-id="8e42d-110">e 10:00 A. M. podem não ter sido replicados para o pool de backup e serão perdidos.</span><span class="sxs-lookup"><span data-stu-id="8e42d-110">and 10:00 A.M.might not have replicated to the backup pool, and would be lost.</span></span>

<span data-ttu-id="8e42d-111">Todos os números de RTO e RPO neste documento supõem que os dois data centers estão localizados na mesma região com alta velocidade e trasporte de baixa latência entre os dois locais.</span><span class="sxs-lookup"><span data-stu-id="8e42d-111">All RTO and RPO numbers in this document assume that the two data centers are located within the same world region with high-speed, low-latency transport between the two sites.</span></span> <span data-ttu-id="8e42d-112">Esses números são medidos para um pool com usuários simultâneos de 40.000 e 200.000 usuários habilitados para o Lync com relação a um modelo de usuário predefinido onde não há nenhuma lista de pendências na replicação de dados.</span><span class="sxs-lookup"><span data-stu-id="8e42d-112">These numbers are measured for a pool with 40,000 concurrently active users and 200,000 users enabled for Lync with respect to a pre-defined user model where there is no backlog in data replication.</span></span> <span data-ttu-id="8e42d-113">Eles estão sujeitos à alteração baseado no teste e validação de desempenho.</span><span class="sxs-lookup"><span data-stu-id="8e42d-113">They are subject to change based on performance testing and validation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

