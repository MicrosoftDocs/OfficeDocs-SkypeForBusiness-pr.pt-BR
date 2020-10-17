---
title: 'Lync Server 2013: planejamento para emparelhamento de pool de front-ends'
description: 'Lync Server 2013: planejamento para emparelhamento de pool de front-ends.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for Front End pool pairing
ms:assetid: cca5773d-57ff-45ce-a7b4-f82ae697c477
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205293(v=OCS.15)
ms:contentKeyID: 48185508
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ac235cf682e286132836e13b34b457adf2bfc233
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562787"
---
# <a name="planning-for-front-end-pool-pairing-in-lync-server-2013"></a><span data-ttu-id="6437a-103">Planejamento para emparelhamento de pool de front-ends no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6437a-103">Planning for Front End pool pairing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6437a-104">_**Última modificação do tópico:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="6437a-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="6437a-105">Para obter os melhores recursos de recuperação de desastre no Lync Server 2013, implante pares de pools de front-ends em dois locais geograficamente dispersos.</span><span class="sxs-lookup"><span data-stu-id="6437a-105">For the best disaster recovery abilities in Lync Server 2013, deploy pairs of Front End pools across two geographically dispersed sites.</span></span> <span data-ttu-id="6437a-106">Cada site contém um pool de Front-End que é emparelhado com um pool de Front-End correspondente em outro local.</span><span class="sxs-lookup"><span data-stu-id="6437a-106">Each site contains a Front End pool which is paired with a corresponding Front End pool in the other site.</span></span> <span data-ttu-id="6437a-107">Ambos os sites estão ativos, e o serviço de backup do Lync Server fornece replicação de dados em tempo real para manter os pools sincronizados.</span><span class="sxs-lookup"><span data-stu-id="6437a-107">Both sites are active, and the Lync Server Backup Service provides real-time data replication to keep the pools synchronized.</span></span> <span data-ttu-id="6437a-108">O serviço de backup é um novo recurso no Lync Server 2013, projetado para oferecer suporte à solução de recuperação de desastres.</span><span class="sxs-lookup"><span data-stu-id="6437a-108">The Backup Service is a new feature in Lync Server 2013, designed to support the disaster recovery solution.</span></span> <span data-ttu-id="6437a-109">Está instalado em um pool de Front-End ao emparelhar o pool com outro pool de Front-End.</span><span class="sxs-lookup"><span data-stu-id="6437a-109">It is installed on a Front End pool when you pair the pool with another Front End pool.</span></span>

<span data-ttu-id="6437a-p102">Se o pool em um local falhar, é possível fazer o failover dos usuários deste pool para o pool em outro local, que oferece serviços para todos os usuários em ambos os pools. Para fins de planejamento de capacidade, cada pool deve ser atribuído para lidar com cargas de trabalho de todos os usuários em ambos os pools em caso de desastre.</span><span class="sxs-lookup"><span data-stu-id="6437a-p102">If the pool in one site fails, you can fail over the users from that pool to the pool in the other site, which then provides services to all the users in both pools. For capacity planning purposes, each pool should be designed to handle the workloads of all users in both pools in the event of a disaster.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="6437a-112">Nesta Seção</span><span class="sxs-lookup"><span data-stu-id="6437a-112">In This Section</span></span>

  - [<span data-ttu-id="6437a-113">Opções de emparelhamento de pool com suporte e práticas recomendadas para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6437a-113">Supported pool pairing options and best practices for Lync Server 2013</span></span>](lync-server-2013-supported-pool-pairing-options-and-best-practices.md)

  - [<span data-ttu-id="6437a-114">Relações de registradores de backup no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6437a-114">Backup Registrar relationships in Lync Server 2013</span></span>](lync-server-2013-backup-registrar-relationships.md)

  - [<span data-ttu-id="6437a-115">Tempo de recuperação para failover de pool e failback de pool no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6437a-115">Recovery time for pool failover and pool failback in Lync Server 2013</span></span>](lync-server-2013-recovery-time-for-pool-failover-and-pool-failback.md)

  - [<span data-ttu-id="6437a-116">Failover do repositório de gerenciamento central no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6437a-116">Central Management store failover in Lync Server 2013</span></span>](lync-server-2013-central-management-store-failover.md)

  - [<span data-ttu-id="6437a-117">Segurança de dados de emparelhamento do pool de front-ends no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6437a-117">Front End pool pairing data security in Lync Server 2013</span></span>](lync-server-2013-front-end-pool-pairing-data-security.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

