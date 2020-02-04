---
title: Considerações de coexistência
ms.reviewer: ''
ms.author: kenwith
author: kenwith
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
ms.openlocfilehash: e53c57b90a85024ed5375129ce23c6ff0060edc4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727971"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="coexistence-considerations"></a><span data-ttu-id="0641e-102">Considerações de coexistência</span><span class="sxs-lookup"><span data-stu-id="0641e-102">Coexistence considerations</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0641e-103">_**Tópico da última modificação:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="0641e-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="0641e-104">Após a migração, apenas um servidor do Lync 2013, o pool do servidor de chat persistente existirá, e você poderá encerrar sua implantação herdada.</span><span class="sxs-lookup"><span data-stu-id="0641e-104">After migration, only a Lync Server 2013, Persistent Chat Server pool will exist, and you can decommission your legacy deployment.</span></span>

<span data-ttu-id="0641e-105">Antes de a migração ser concluída e antes de você ter desativado a implantação do servidor de chat de grupo atual completamente, você pode ter qualquer uma das seguintes implantações:</span><span class="sxs-lookup"><span data-stu-id="0641e-105">Before migration completes and before you have decommissioned your current Group Chat Server deployment completely, you may have any of the following deployments:</span></span>

  - <span data-ttu-id="0641e-106">Lync Server 2013, pool de servidor de chat persistente, que deve ser hospedado em um pool do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0641e-106">Lync Server 2013, Persistent Chat Server pool, which must be homed on a Lync Server 2013 pool.</span></span>

  - <span data-ttu-id="0641e-107">Lync Server 2010, pool de chat em grupo, que deve ser hospedado em um pool do Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="0641e-107">Lync Server 2010, Group Chat pool, which must be homed on a Lync Server 2010 pool.</span></span>

  - <span data-ttu-id="0641e-108">Pool de chat do grupo do Office Communications Server 2007 R2, que deve ser hospedado em um pool do Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="0641e-108">Office Communications Server 2007 R2 Group Chat pool, which must be homed on an Office Communications Server 2007 R2 pool.</span></span>

<span data-ttu-id="0641e-109">Essas implantações podem existir lado a lado.</span><span class="sxs-lookup"><span data-stu-id="0641e-109">These deployments can exist side by side.</span></span> <span data-ttu-id="0641e-110">No entanto, as categorias, salas e suplementos em uma implantação não interagem com as da implantação que o acompanha.</span><span class="sxs-lookup"><span data-stu-id="0641e-110">However the categories, rooms, and add-ins in one deployment do not interact with those in the accompanying deployment.</span></span>

<span data-ttu-id="0641e-111">Usando a configuração manual, um cliente herdado (cliente de chat em grupo) pode se conectar a um pool por vez para o Office Communications Server 2007 R2, o Lync Server 2010, o chat em grupo ou o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0641e-111">Using manual configuration, a legacy client (Group Chat client) can connect to one pool at a time for Office Communications Server 2007 R2, Lync Server 2010, Group Chat, or Lync Server 2013.</span></span>

<span data-ttu-id="0641e-112">O Lync 2013 (cliente) só pode interagir com o servidor de chat do Lync 2013, o pool persistente do servidor de chat, não com pools de servidores de chat em grupo herdado.</span><span class="sxs-lookup"><span data-stu-id="0641e-112">The Lync 2013 (client) can interact only with the Lync Server 2013, Persistent Chat Server pool, not with legacy Group Chat Server pools.</span></span> <span data-ttu-id="0641e-113">Para usar o chat persistente em um Lync 2013 (cliente), o usuário deve ser hospedado no Lync 2013 e habilitado pela política.</span><span class="sxs-lookup"><span data-stu-id="0641e-113">To use Persistent Chat in a Lync 2013 (client), the user must be homed on Lync 2013 and enabled by policy.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

