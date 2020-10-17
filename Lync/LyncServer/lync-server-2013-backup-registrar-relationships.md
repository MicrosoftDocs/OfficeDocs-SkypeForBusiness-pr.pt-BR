---
title: Relações de registrador de backup do Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backup Registrar relationships
ms:assetid: 7e078271-84b9-4666-989c-c4507a0cdf4a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205033(v=OCS.15)
ms:contentKeyID: 48184631
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cd41595fed0d16327f65f4e6af39fe80c049daa4
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48499328"
---
# <a name="backup-registrar-relationships-in-lync-server-2013"></a><span data-ttu-id="e45f0-102">Relações de registradores de backup no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e45f0-102">Backup Registrar relationships in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e45f0-103">_**Última modificação do tópico:** 2012-06-28_</span><span class="sxs-lookup"><span data-stu-id="e45f0-103">_**Topic Last Modified:** 2012-06-28_</span></span>

<span data-ttu-id="e45f0-104">Além de oferecer capacidade para recuperação de desastre, dois pools pareados servem como backup de Registrars.</span><span class="sxs-lookup"><span data-stu-id="e45f0-104">In addition to providing disaster recovery ability, two paired pools serve as the backup Registrars for each other.</span></span> <span data-ttu-id="e45f0-105">No Lync Server 2013, as relações de registrador de backup entre os pools front-end são sempre 1:1 e recíprocos.</span><span class="sxs-lookup"><span data-stu-id="e45f0-105">In Lync Server 2013, backup Registrar relationships between Front End pools are always 1:1 and reciprocal.</span></span> <span data-ttu-id="e45f0-106">Isso significa que se P1 for backup de P2, P2 deve ser o backup de P1 e nenhum pode ser backup de outro pool Front End.</span><span class="sxs-lookup"><span data-stu-id="e45f0-106">This means that if P1 is the backup for P2, then P2 must be the backup for P1, and neither can be the backup for any other Front End pool.</span></span> <span data-ttu-id="e45f0-107">Essa é uma alteração do Lync Server 2010, em que as relações de backup do pool de front-ends podem ser muitos para um.</span><span class="sxs-lookup"><span data-stu-id="e45f0-107">This is a change from Lync Server 2010, in which Front End pool backup relationships could be many to one.</span></span>

<span data-ttu-id="e45f0-108">Embora as relações de backup entre dois pools de front-ends devam ser 1:1 e symmetric, cada pool de front-ends ainda pode ser o registrador de backup para qualquer número de aparelhos de filial persistente, assim como no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="e45f0-108">Even though backup relationships between two Front End pools must be 1:1 and symmetrical, each Front End pool can still also be the backup registrar for any number of Survivable Branch Appliances, just as in Lync Server 2010.</span></span>

<span data-ttu-id="e45f0-109">Observe que o Lync Server 2013 não estende o suporte à recuperação de desastres para usuários hospedados em um aparelho de filial persistente.</span><span class="sxs-lookup"><span data-stu-id="e45f0-109">Note that Lync Server 2013 does not extend disaster recovery support to users homed on a Survivable Branch Appliance.</span></span> <span data-ttu-id="e45f0-110">Se um pool de front-ends que serve como backup para um aparelho de filial persistente falhar, os usuários conectados ao aparelho de filial persistente se enquadram no modo de resiliência, mesmo depois que os usuários hospedados no pool de front-ends têm failover para o pool de front-ends de backup.</span><span class="sxs-lookup"><span data-stu-id="e45f0-110">If a Front End pool that serves as the backup for a Survivable Branch Appliance goes down, users signed into the Survivable Branch Appliance fall into resiliency mode even after users homed on the Front End pool are failed over to the backup Front End pool.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

