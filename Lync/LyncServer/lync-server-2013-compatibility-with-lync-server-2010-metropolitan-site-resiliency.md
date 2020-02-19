---
title: Lync Server 2013 compatibilidade com o Lync Server 2010 Metropolitan site resiliência
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server 2010 metropolitan site resiliency
ms:assetid: 18673ff6-b664-4a57-a89b-cbda8b129e6a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204715(v=OCS.15)
ms:contentKeyID: 48183526
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 589120a382d07f611eeb6c8c78ee31a9f2e367ef
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138452"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="lync-server-2010-metropolitan-site-resiliency"></a><span data-ttu-id="84023-102">Lync Server 2010 Metropolitan de resiliência de site</span><span class="sxs-lookup"><span data-stu-id="84023-102">Lync Server 2010 metropolitan site resiliency</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="84023-103">_**Última modificação do tópico:** 2014-03-19_</span><span class="sxs-lookup"><span data-stu-id="84023-103">_**Topic Last Modified:** 2014-03-19_</span></span>

<span data-ttu-id="84023-104">A solução de resiliência de site metropolitana compatível com o Lync Server 2010 não é suportada pelo Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="84023-104">The metropolitan site resiliency solution supported for Lync Server 2010 is not supported for Lync Server 2013.</span></span> <span data-ttu-id="84023-105">Essa solução envolvia a extensão de um único pool de Front-Ends por dois data centers na mesma área metropolitana.</span><span class="sxs-lookup"><span data-stu-id="84023-105">This solution involved spanning a single Front End pool across two data centers in the same metropolitan area.</span></span>

<span data-ttu-id="84023-106">A solução Metropolitana de resiliência de site foi projetada para recuperar-se da perda de um data center completo.</span><span class="sxs-lookup"><span data-stu-id="84023-106">The metropolitan site resiliency solution was designed to recover from the loss of a full datacenter.</span></span> <span data-ttu-id="84023-107">Quando você expande o pool em dois datacenters, normalmente coloca metade dos seus front-ends em um datacenter e a outra metade no segundo datacenter.</span><span class="sxs-lookup"><span data-stu-id="84023-107">When you span your pool across two datacenters, you typically put half of your front ends in one datacenter and the other half in the second datacenter.</span></span> <span data-ttu-id="84023-108">Se você perder um datacenter inteiro, você perdeu metade dos seus servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="84023-108">If you lose an entire datacenter, you have lost half of your Front End Servers.</span></span> <span data-ttu-id="84023-109">Isso pode causar problemas com o novo modelo de sistema distribuído para pools de front-ends no Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="84023-109">This can cause issues with the new distributed system model for Front End Pools in Lync Server 2013.</span></span> <span data-ttu-id="84023-110">Para obter mais informações, consulte [topologias e componentes para servidores front-end, mensagens instantâneas e presença no Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).</span><span class="sxs-lookup"><span data-stu-id="84023-110">For more information, see [Topologies and components for Front End Servers, instant messaging, and presence in Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

