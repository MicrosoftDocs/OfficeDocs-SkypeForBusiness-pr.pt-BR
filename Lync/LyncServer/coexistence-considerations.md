---
title: Considerações de coexistência
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Coexistence considerations
ms:assetid: 9d1a3c0f-492a-4e37-bc2f-63509e328785
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205131(v=OCS.15)
ms:contentKeyID: 48184990
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cdad93eaf8debbc616099c1454d5e39438a63474
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48499668"
---
# <a name="coexistence-considerations"></a><span data-ttu-id="a0b22-102">Considerações de coexistência</span><span class="sxs-lookup"><span data-stu-id="a0b22-102">Coexistence considerations</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a0b22-103">_**Última modificação do tópico:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="a0b22-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="a0b22-104">Após a migração, somente um pool do servidor de chat persistente do Lync Server 2013, existirá, e você poderá encerrar sua implantação herdada.</span><span class="sxs-lookup"><span data-stu-id="a0b22-104">After migration, only a Lync Server 2013, Persistent Chat Server pool will exist, and you can decommission your legacy deployment.</span></span>

<span data-ttu-id="a0b22-105">Antes que a migração seja concluída e antes de você tenha descomissionado completamente sua implantação do servidor de chat de grupo atual, você pode ter qualquer uma das seguintes implantações:</span><span class="sxs-lookup"><span data-stu-id="a0b22-105">Before migration completes and before you have decommissioned your current Group Chat Server deployment completely, you may have any of the following deployments:</span></span>

  - <span data-ttu-id="a0b22-106">Lync Server 2013, pool de servidor de chat persistente, que deve ser hospedado em um pool do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a0b22-106">Lync Server 2013, Persistent Chat Server pool, which must be homed on a Lync Server 2013 pool.</span></span>

  - <span data-ttu-id="a0b22-107">Lync Server 2010, pool de chat de grupo, que deve ser hospedado em um pool do Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a0b22-107">Lync Server 2010, Group Chat pool, which must be homed on a Lync Server 2010 pool.</span></span>

  - <span data-ttu-id="a0b22-108">Pool de chat do grupo do Office Communications Server 2007 R2, que deve estar hospedado em um pool do Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="a0b22-108">Office Communications Server 2007 R2 Group Chat pool, which must be homed on an Office Communications Server 2007 R2 pool.</span></span>

<span data-ttu-id="a0b22-p101">Essas implantações podem coexistir. No entanto, as categorias, salas e complementos em uma implantação não interagem com aquelas na implantação acompanhante.</span><span class="sxs-lookup"><span data-stu-id="a0b22-p101">These deployments can exist side by side. However the categories, rooms, and add-ins in one deployment do not interact with those in the accompanying deployment.</span></span>

<span data-ttu-id="a0b22-111">Usando a configuração manual, um cliente herdado (cliente de chat de grupo) pode se conectar a um pool por vez para o Office Communications Server 2007 R2, o Lync Server 2010, o chat de grupo ou o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a0b22-111">Using manual configuration, a legacy client (Group Chat client) can connect to one pool at a time for Office Communications Server 2007 R2, Lync Server 2010, Group Chat, or Lync Server 2013.</span></span>

<span data-ttu-id="a0b22-112">O Lync 2013 (cliente) pode interagir somente com o pool do servidor de chat persistente do Lync Server 2013, não com pools do servidor de chat de grupo herdado.</span><span class="sxs-lookup"><span data-stu-id="a0b22-112">The Lync 2013 (client) can interact only with the Lync Server 2013, Persistent Chat Server pool, not with legacy Group Chat Server pools.</span></span> <span data-ttu-id="a0b22-113">Para usar o chat persistente em um Lync 2013 (cliente), o usuário deve estar hospedado no Lync 2013 e habilitado por política.</span><span class="sxs-lookup"><span data-stu-id="a0b22-113">To use Persistent Chat in a Lync 2013 (client), the user must be homed on Lync 2013 and enabled by policy.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

