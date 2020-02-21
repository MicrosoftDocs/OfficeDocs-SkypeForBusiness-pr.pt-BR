---
title: 'Lync Server 2013: fazendo backup e restaurando o Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backing up and restoring Lync Server 2013
ms:assetid: 07dc1f5e-af66-4e18-bf39-881dceff8bc3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202160(v=OCS.15)
ms:contentKeyID: 51541443
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 00f2f907c8efb663816ca50152643cea70fcc2ff
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42196954"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="backing-up-and-restoring-lync-server-2013"></a><span data-ttu-id="0647d-102">Fazendo backup e restaurando o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0647d-102">Backing up and restoring Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0647d-103">_**Última modificação do tópico:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="0647d-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="0647d-104">Nesta seção, você encontrará as práticas recomendadas para fazer backup dos dados do Lync Server 2013 e para restaurá-lo se você tiver uma falha.</span><span class="sxs-lookup"><span data-stu-id="0647d-104">In this section, you’ll find the best practices for backing up your Lync Server 2013 data, and for restoring it if you have a failure.</span></span> <span data-ttu-id="0647d-105">Essas práticas recomendadas aplicam-se às seguintes situações:</span><span class="sxs-lookup"><span data-stu-id="0647d-105">These best practices apply to the following situations:</span></span>

  - <span data-ttu-id="0647d-106">Um pool completo do Lync Server de qualquer tipo (servidor front-end, servidor de borda, servidor de mediação, servidor de chat persistente ou diretor) ou um servidor individual em um desses pools.</span><span class="sxs-lookup"><span data-stu-id="0647d-106">An entire Lync Server pool of any type (Front End Server, Edge Server, Mediation Server, Persistent Chat Server, or Director), or an individual server in one of these pools.</span></span>

  - <span data-ttu-id="0647d-107">O servidor de gerenciamento central</span><span class="sxs-lookup"><span data-stu-id="0647d-107">The Central Management Server</span></span>

  - <span data-ttu-id="0647d-108">Um servidor Standard Edition</span><span class="sxs-lookup"><span data-stu-id="0647d-108">A Standard Edition server</span></span>

  - <span data-ttu-id="0647d-109">Um servidor back-end Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="0647d-109">An Enterprise Edition Back End Server</span></span>

  - <span data-ttu-id="0647d-110">Um repositório de arquivos</span><span class="sxs-lookup"><span data-stu-id="0647d-110">A File Store</span></span>

  - <span data-ttu-id="0647d-111">Banco de dados de arquivamento, banco de dados de monitoramento ou banco de dados de chat persistente</span><span class="sxs-lookup"><span data-stu-id="0647d-111">An Archiving database, Monitoring database, or Persistent Chat database</span></span>

<span data-ttu-id="0647d-112">Esta seção não inclui informações sobre a restauração de um site inteiro ou para o desenvolvimento de um site em espera.</span><span class="sxs-lookup"><span data-stu-id="0647d-112">This section does not include information about restoring an entire site or for developing a standby site.</span></span> <span data-ttu-id="0647d-113">Para obter detalhes sobre o desenvolvimento de uma solução de recuperação de desastres com pools de front-ends emparelhados, consulte [Planning for High Availability and Disaster Recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="0647d-113">For details about developing a disaster recovery solution with paired Front End pools, see [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span> <span data-ttu-id="0647d-114">Este é o método recomendado para o planejamento da recuperação de desastres.</span><span class="sxs-lookup"><span data-stu-id="0647d-114">This is the recommended method for planning for disaster recovery.</span></span>

<span data-ttu-id="0647d-115">Se você tiver implantado pools de front-ends emparelhados, se um desses pools falhar e tornar-se irrecuperável, você poderá restaurar esse pool com um novo FQDN (nome de domínio totalmente qualificado) de seu pool emparelhado.</span><span class="sxs-lookup"><span data-stu-id="0647d-115">If you have deployed paired Front End pools, if one of these pools fails and becomes unrecoverable, you can restore this pool with a new fully qualified domain name (FQDN) from its paired pool.</span></span> <span data-ttu-id="0647d-116">Para obter detalhes sobre as etapas para realizar essa recuperação, consulte [failover de um pool no Lync Server 2013](lync-server-2013-failing-over-a-pool.md).</span><span class="sxs-lookup"><span data-stu-id="0647d-116">For details on the steps to perform this recovery, see [Failing over a pool in Lync Server 2013](lync-server-2013-failing-over-a-pool.md).</span></span> <span data-ttu-id="0647d-117">Além disso, se você quiser recriar um pool com falha e irrecuperável que faz parte de um par de front-ends, poderá usar as etapas de [execução de um failover de pool de front-ends ABC no Lync Server 2013](lync-server-2013-performing-an-abc-front-end-pool-failover.md).</span><span class="sxs-lookup"><span data-stu-id="0647d-117">Additionally, if you later want to recreate a failed and unrecoverable pool that was part of a Front End pair, you can use the steps in [Performing an ABC Front End pool failover in Lync Server 2013](lync-server-2013-performing-an-abc-front-end-pool-failover.md).</span></span>

<span data-ttu-id="0647d-118">O método descrito neste documento envolve considerações especiais durante a fase de planejamento.</span><span class="sxs-lookup"><span data-stu-id="0647d-118">The methodology described in this document involves special considerations during the planning phase.</span></span> <span data-ttu-id="0647d-119">Para obter detalhes, consulte [estabelecendo um plano de backup e restauração para o Lync Server 2013](lync-server-2013-establishing-a-backup-and-restoration-plan.md).</span><span class="sxs-lookup"><span data-stu-id="0647d-119">For details, see [Establishing a backup and restoration plan for Lync Server 2013](lync-server-2013-establishing-a-backup-and-restoration-plan.md).</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="0647d-120">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="0647d-120">In This Section</span></span>

  - [<span data-ttu-id="0647d-121">Preparando para backup e restauração do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0647d-121">Preparing for Lync Server 2013 backup and restoration</span></span>](lync-server-2013-preparing-for-lync-server-backup-and-restoration.md)

  - [<span data-ttu-id="0647d-122">Fazendo backup de dados e configurações no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0647d-122">Backing up data and settings in Lync Server 2013</span></span>](lync-server-2013-backing-up-data-and-settings.md)

  - [<span data-ttu-id="0647d-123">Restaurando dados e configurações no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0647d-123">Restoring data and settings in Lync Server 2013</span></span>](lync-server-2013-restoring-data-and-settings.md)

  - [<span data-ttu-id="0647d-124">Planilhas de backup e restauração para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0647d-124">Backup and restoration worksheets for Lync Server 2013</span></span>](lync-server-2013-backup-and-restoration-worksheets.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

