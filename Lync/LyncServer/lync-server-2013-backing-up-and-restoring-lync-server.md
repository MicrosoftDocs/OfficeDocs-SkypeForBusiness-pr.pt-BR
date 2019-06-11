---
title: 'Lync Server 2013: fazer backup e restaurar o Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Backing up and restoring Lync Server 2013
ms:assetid: 07dc1f5e-af66-4e18-bf39-881dceff8bc3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202160(v=OCS.15)
ms:contentKeyID: 51541443
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5a0cf9f9baabd095e54373c31acd4f4522974a82
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836897"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backing-up-and-restoring-lync-server-2013"></a><span data-ttu-id="ed851-102">Fazer backup e restaurar o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ed851-102">Backing up and restoring Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ed851-103">_**Tópico da última modificação:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="ed851-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="ed851-104">Nesta seção, você encontrará as práticas recomendadas para fazer backup dos dados do Lync Server 2013 e para restaurá-lo se você tiver uma falha.</span><span class="sxs-lookup"><span data-stu-id="ed851-104">In this section, you’ll find the best practices for backing up your Lync Server 2013 data, and for restoring it if you have a failure.</span></span> <span data-ttu-id="ed851-105">Estas práticas recomendadas se aplicam às seguintes situações:</span><span class="sxs-lookup"><span data-stu-id="ed851-105">These best practices apply to the following situations:</span></span>

  - <span data-ttu-id="ed851-106">Um pool de qualquer tipo do Lync Server inteiro (servidor front-end, servidor de borda, servidor de mediação, servidor de chat persistente ou diretor) ou um servidor individual em um desses pools.</span><span class="sxs-lookup"><span data-stu-id="ed851-106">An entire Lync Server pool of any type (Front End Server, Edge Server, Mediation Server, Persistent Chat Server, or Director), or an individual server in one of these pools.</span></span>

  - <span data-ttu-id="ed851-107">O servidor de gerenciamento central</span><span class="sxs-lookup"><span data-stu-id="ed851-107">The Central Management Server</span></span>

  - <span data-ttu-id="ed851-108">Um servidor Standard Edition</span><span class="sxs-lookup"><span data-stu-id="ed851-108">A Standard Edition server</span></span>

  - <span data-ttu-id="ed851-109">Um servidor back-end do Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="ed851-109">An Enterprise Edition Back End Server</span></span>

  - <span data-ttu-id="ed851-110">Um repositório de arquivos</span><span class="sxs-lookup"><span data-stu-id="ed851-110">A File Store</span></span>

  - <span data-ttu-id="ed851-111">Um banco de dados de arquivamento, banco de dados de monitoramento ou banco de dados de chat persistente</span><span class="sxs-lookup"><span data-stu-id="ed851-111">An Archiving database, Monitoring database, or Persistent Chat database</span></span>

<span data-ttu-id="ed851-112">Esta seção não inclui informações sobre como restaurar um site inteiro ou para desenvolver um site em espera.</span><span class="sxs-lookup"><span data-stu-id="ed851-112">This section does not include information about restoring an entire site or for developing a standby site.</span></span> <span data-ttu-id="ed851-113">Para obter detalhes sobre o desenvolvimento de uma solução de recuperação de desastres com pools front-ends emparelhados, consulte [planejando a alta disponibilidade e a recuperação de desastres no Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="ed851-113">For details about developing a disaster recovery solution with paired Front End pools, see [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span> <span data-ttu-id="ed851-114">Esse é o método recomendado para planejar a recuperação de desastres.</span><span class="sxs-lookup"><span data-stu-id="ed851-114">This is the recommended method for planning for disaster recovery.</span></span>

<span data-ttu-id="ed851-115">Se você implantou pools front-end emparelhados, se um desses pools falhar e se tornar irrecuperável, você pode restaurar esse pool com um novo nome de domínio totalmente qualificado (FQDN) de seu pool emparelhado.</span><span class="sxs-lookup"><span data-stu-id="ed851-115">If you have deployed paired Front End pools, if one of these pools fails and becomes unrecoverable, you can restore this pool with a new fully qualified domain name (FQDN) from its paired pool.</span></span> <span data-ttu-id="ed851-116">Para obter detalhes sobre as etapas para realizar essa recuperação, consulte [falha em um pool no Lync Server 2013](lync-server-2013-failing-over-a-pool.md).</span><span class="sxs-lookup"><span data-stu-id="ed851-116">For details on the steps to perform this recovery, see [Failing over a pool in Lync Server 2013](lync-server-2013-failing-over-a-pool.md).</span></span> <span data-ttu-id="ed851-117">Além disso, se você quiser recriar mais tarde um pool com falha e irrecuperável que fazia parte de um par de front-end, você pode usar as etapas em [executando um failover de pool de front-end da ABC no Lync Server 2013](lync-server-2013-performing-an-abc-front-end-pool-failover.md).</span><span class="sxs-lookup"><span data-stu-id="ed851-117">Additionally, if you later want to recreate a failed and unrecoverable pool that was part of a Front End pair, you can use the steps in [Performing an ABC Front End pool failover in Lync Server 2013](lync-server-2013-performing-an-abc-front-end-pool-failover.md).</span></span>

<span data-ttu-id="ed851-118">A metodologia descrita neste documento envolve considerações especiais durante a fase de planejamento.</span><span class="sxs-lookup"><span data-stu-id="ed851-118">The methodology described in this document involves special considerations during the planning phase.</span></span> <span data-ttu-id="ed851-119">Para obter detalhes, consulte [estabelecendo um plano de backup e restauração para o Lync Server 2013](lync-server-2013-establishing-a-backup-and-restoration-plan.md).</span><span class="sxs-lookup"><span data-stu-id="ed851-119">For details, see [Establishing a backup and restoration plan for Lync Server 2013](lync-server-2013-establishing-a-backup-and-restoration-plan.md).</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="ed851-120">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="ed851-120">In This Section</span></span>

  - [<span data-ttu-id="ed851-121">Preparando para backup e restauração do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ed851-121">Preparing for Lync Server 2013 backup and restoration</span></span>](lync-server-2013-preparing-for-lync-server-backup-and-restoration.md)

  - [<span data-ttu-id="ed851-122">Fazer backup de dados e configurações no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ed851-122">Backing up data and settings in Lync Server 2013</span></span>](lync-server-2013-backing-up-data-and-settings.md)

  - [<span data-ttu-id="ed851-123">Restaurando dados e configurações no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ed851-123">Restoring data and settings in Lync Server 2013</span></span>](lync-server-2013-restoring-data-and-settings.md)

  - [<span data-ttu-id="ed851-124">Planilhas de backup e restauração para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ed851-124">Backup and restoration worksheets for Lync Server 2013</span></span>](lync-server-2013-backup-and-restoration-worksheets.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

