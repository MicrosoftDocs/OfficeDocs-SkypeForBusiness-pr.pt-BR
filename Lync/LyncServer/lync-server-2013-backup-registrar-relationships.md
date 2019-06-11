---
title: 'Lync Server 2013: Relacionamentos de Registradores de backup'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Backup Registrar relationships
ms:assetid: 7e078271-84b9-4666-989c-c4507a0cdf4a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205033(v=OCS.15)
ms:contentKeyID: 48184631
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3a642c8d8872b2c0d1372a209c9c05dac704ee20
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836741"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backup-registrar-relationships-in-lync-server-2013"></a><span data-ttu-id="ed81b-102">Relacionamentos de Registradores de backup no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ed81b-102">Backup Registrar relationships in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ed81b-103">_**Tópico da última modificação:** 2012-06-28_</span><span class="sxs-lookup"><span data-stu-id="ed81b-103">_**Topic Last Modified:** 2012-06-28_</span></span>

<span data-ttu-id="ed81b-104">Além de permitir a recuperação de desastre, dois pools emparelhados atuam como os Registradores de backup entre si.</span><span class="sxs-lookup"><span data-stu-id="ed81b-104">In addition to providing disaster recovery ability, two paired pools serve as the backup Registrars for each other.</span></span> <span data-ttu-id="ed81b-105">No Lync Server 2013, as relações de registrador de backup entre os pools front-end são sempre 1:1 e recíprocos.</span><span class="sxs-lookup"><span data-stu-id="ed81b-105">In Lync Server 2013, backup Registrar relationships between Front End pools are always 1:1 and reciprocal.</span></span> <span data-ttu-id="ed81b-106">Isso significa que, se P1 for o backup para P2, então P2 deve ser o backup do P1, e nenhum deles pode ser o backup de qualquer outro pool de front-end.</span><span class="sxs-lookup"><span data-stu-id="ed81b-106">This means that if P1 is the backup for P2, then P2 must be the backup for P1, and neither can be the backup for any other Front End pool.</span></span> <span data-ttu-id="ed81b-107">Isso é uma alteração do Lync Server 2010, no qual as relações de backup de pool de front-end podem ser muitos para um.</span><span class="sxs-lookup"><span data-stu-id="ed81b-107">This is a change from Lync Server 2010, in which Front End pool backup relationships could be many to one.</span></span>

<span data-ttu-id="ed81b-108">Embora as relações de backup entre dois pools de front-end sejam 1:1 e simétrica, cada pool de front-ends ainda pode ser o registrador de backup para qualquer número de aparelhos de ramificação sobreviventes, assim como no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="ed81b-108">Even though backup relationships between two Front End pools must be 1:1 and symmetrical, each Front End pool can still also be the backup registrar for any number of Survivable Branch Appliances, just as in Lync Server 2010.</span></span>

<span data-ttu-id="ed81b-109">Observe que o Lync Server 2013 não estende o suporte à recuperação de desastres para usuários hospedados em um aparelho de ramificação sobreviventes.</span><span class="sxs-lookup"><span data-stu-id="ed81b-109">Note that Lync Server 2013 does not extend disaster recovery support to users homed on a Survivable Branch Appliance.</span></span> <span data-ttu-id="ed81b-110">Se um pool de front-end que funciona como o backup para um aparelho de ramificação sobreviventes parar, os usuários que entrarem no aparelho de ramificação sobreviventes ficarão em modo de resiliência, mesmo depois que os usuários hospedados no pool de front-ends tiverem failover para o pool de front-ends de backup.</span><span class="sxs-lookup"><span data-stu-id="ed81b-110">If a Front End pool that serves as the backup for a Survivable Branch Appliance goes down, users signed into the Survivable Branch Appliance fall into resiliency mode even after users homed on the Front End pool are failed over to the backup Front End pool.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

