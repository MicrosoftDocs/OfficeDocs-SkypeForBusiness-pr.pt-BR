---
title: 'Lync Server 2013: cmdlets do servidor de chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Persistent Chat Server cmdlets
ms:assetid: 5aa59edb-db57-406f-9fbd-54bf1a55d31b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204920(v=OCS.15)
ms:contentKeyID: 48184226
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 62d0c554cb9c0ae5cbc21aea08eddf8c1d087601
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006899"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="persistent-chat-server-cmdlets-in-lync-server-2013"></a><span data-ttu-id="6cb4b-102">Cmdlets do servidor de chat persistente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6cb4b-102">Persistent Chat Server cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6cb4b-103">_**Última modificação do tópico:** 2012-06-27_</span><span class="sxs-lookup"><span data-stu-id="6cb4b-103">_**Topic Last Modified:** 2012-06-27_</span></span>

<span data-ttu-id="6cb4b-104">Os cmdlets de chat persistente permitem que você gerencie e configure o serviço de chat persistente do Microsoft Lync Server 2013 (anteriormente conhecido como serviço de chat de grupo).</span><span class="sxs-lookup"><span data-stu-id="6cb4b-104">The Persistent Chat cmdlets enable you to manage and configure the Microsoft Lync Server 2013 Persistent Chat service (formerly known as the Group Chat service).</span></span> <span data-ttu-id="6cb4b-105">O Chat Persistente permite que os usuários participem de sessões de mensagens instantâneas online.</span><span class="sxs-lookup"><span data-stu-id="6cb4b-105">Persistent Chat enables users to participate in online instant messaging sessions.</span></span> <span data-ttu-id="6cb4b-106">Embora essas seções possam ocorrer em tempo real, o conteúdo de cada sessão é persistente, ou seja, essas conversas podem ser retomadas por qualquer pessoa, a qualquer momento.</span><span class="sxs-lookup"><span data-stu-id="6cb4b-106">Although these sessions can take place in real time, the content of each session is persistent; that means these conversations can be resumed by anyone at any time.</span></span>

<div>

## <a name="persistent-chat-cmdlets"></a><span data-ttu-id="6cb4b-107">Cmdlets do Chat Persistente</span><span class="sxs-lookup"><span data-stu-id="6cb4b-107">Persistent Chat Cmdlets</span></span>

<span data-ttu-id="6cb4b-108">Os cmdlets de chat persistente permitem que você gerencie e configure o serviço de chat persistente do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6cb4b-108">The Persistent Chat cmdlets enable you to manage and configure the Lync Server Persistent Chat service.</span></span>

<span data-ttu-id="6cb4b-109">**Cmdlets do Chat Persistente**</span><span class="sxs-lookup"><span data-stu-id="6cb4b-109">**Persistent Chat Cmdlets**</span></span>

  - <span data-ttu-id="6cb4b-110">[Get-CsAdPrincipal](https://technet.microsoft.com/library/JJ205326(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6cb4b-110">[Get-CsAdPrincipal](https://technet.microsoft.com/library/JJ205326(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="6cb4b-111">[Set-CsPersistentChatActiveServer](https://technet.microsoft.com/library/JJ205065(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6cb4b-111">[Set-CsPersistentChatActiveServer](https://technet.microsoft.com/library/JJ205065(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="6cb4b-112">[Get-CsPersistentChatAddin](https://technet.microsoft.com/library/JJ204670(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6cb4b-112">[Get-CsPersistentChatAddin](https://technet.microsoft.com/library/JJ204670(v=OCS.15))</span></span>

  - <span data-ttu-id="6cb4b-113">[New-CsPersistentChatAddin](https://technet.microsoft.com/library/JJ204641(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6cb4b-113">[New-CsPersistentChatAddin](https://technet.microsoft.com/library/JJ204641(v=OCS.15))</span></span>

  - <span data-ttu-id="6cb4b-114">[Remove-CsPersistentChatAddin](https://technet.microsoft.com/library/JJ205350(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6cb4b-114">[Remove-CsPersistentChatAddin](https://technet.microsoft.com/library/JJ205350(v=OCS.15))</span></span>

  - <span data-ttu-id="6cb4b-115">[Set-CsPersistentChatAddin](https://technet.microsoft.com/library/JJ204721(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6cb4b-115">[Set-CsPersistentChatAddin](https://technet.microsoft.com/library/JJ204721(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="6cb4b-116">[Get-CsPersistentChatCategory](https://technet.microsoft.com/library/JJ204771(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6cb4b-116">[Get-CsPersistentChatCategory](https://technet.microsoft.com/library/JJ204771(v=OCS.15))</span></span>

  - <span data-ttu-id="6cb4b-117">[New-CsPersistentChatCategory](https://technet.microsoft.com/library/JJ204803(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6cb4b-117">[New-CsPersistentChatCategory](https://technet.microsoft.com/library/JJ204803(v=OCS.15))</span></span>

  - <span data-ttu-id="6cb4b-118">[Remove-CsPersistentChatCategory](https://technet.microsoft.com/library/JJ204660(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6cb4b-118">[Remove-CsPersistentChatCategory](https://technet.microsoft.com/library/JJ204660(v=OCS.15))</span></span>

  - <span data-ttu-id="6cb4b-119">[Set-CsPersistentChatCategory](https://technet.microsoft.com/library/JJ204952(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6cb4b-119">[Set-CsPersistentChatCategory](https://technet.microsoft.com/library/JJ204952(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="6cb4b-120">[Get-CsPersistentChatComplianceConfiguration](https://technet.microsoft.com/library/JJ204625(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6cb4b-120">[Get-CsPersistentChatComplianceConfiguration](https://technet.microsoft.com/library/JJ204625(v=OCS.15))</span></span>

  - <span data-ttu-id="6cb4b-121">[New-CsPersistentChatComplianceConfiguration](https://technet.microsoft.com/library/JJ205163(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6cb4b-121">[New-CsPersistentChatComplianceConfiguration](https://technet.microsoft.com/library/JJ205163(v=OCS.15))</span></span>

  - <span data-ttu-id="6cb4b-122">[Remove-CsPersistentChatComplianceConfiguration](https://technet.microsoft.com/library/JJ204767(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6cb4b-122">[Remove-CsPersistentChatComplianceConfiguration](https://technet.microsoft.com/library/JJ204767(v=OCS.15))</span></span>

  - <span data-ttu-id="6cb4b-123">[Set-CsPersistentChatComplianceConfiguration](https://technet.microsoft.com/library/JJ204949(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6cb4b-123">[Set-CsPersistentChatComplianceConfiguration](https://technet.microsoft.com/library/JJ204949(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="6cb4b-124">[Get-CsPersistentChatConfiguration](https://technet.microsoft.com/library/JJ205140(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6cb4b-124">[Get-CsPersistentChatConfiguration](https://technet.microsoft.com/library/JJ205140(v=OCS.15))</span></span>

  - <span data-ttu-id="6cb4b-125">[New-CsPersistentChatConfiguration](https://technet.microsoft.com/library/JJ205330(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6cb4b-125">[New-CsPersistentChatConfiguration](https://technet.microsoft.com/library/JJ205330(v=OCS.15))</span></span>

  - <span data-ttu-id="6cb4b-126">[Remove-CsPersistentChatConfiguration](https://technet.microsoft.com/library/JJ204927(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6cb4b-126">[Remove-CsPersistentChatConfiguration](https://technet.microsoft.com/library/JJ204927(v=OCS.15))</span></span>

  - <span data-ttu-id="6cb4b-127">[Set-CsPersistentChatConfiguration](https://technet.microsoft.com/library/JJ205122(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6cb4b-127">[Set-CsPersistentChatConfiguration](https://technet.microsoft.com/library/JJ205122(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="6cb4b-128">[Export-CsPersistentChatData](https://technet.microsoft.com/library/JJ205378(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6cb4b-128">[Export-CsPersistentChatData](https://technet.microsoft.com/library/JJ205378(v=OCS.15))</span></span>

  - <span data-ttu-id="6cb4b-129">[Import-CsPersistentChatData](https://technet.microsoft.com/library/JJ204709(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6cb4b-129">[Import-CsPersistentChatData](https://technet.microsoft.com/library/JJ204709(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="6cb4b-130">[Get-CsPersistentChatEligiblePrincipal](https://technet.microsoft.com/library/JJ204891(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6cb4b-130">[Get-CsPersistentChatEligiblePrincipal](https://technet.microsoft.com/library/JJ204891(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="6cb4b-131">[Get-CsPersistentChatEndpoint](https://technet.microsoft.com/library/JJ204764(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6cb4b-131">[Get-CsPersistentChatEndpoint](https://technet.microsoft.com/library/JJ204764(v=OCS.15))</span></span>

  - <span data-ttu-id="6cb4b-132">[New-CsPersistentChatEndpoint](https://technet.microsoft.com/library/JJ204811(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6cb4b-132">[New-CsPersistentChatEndpoint](https://technet.microsoft.com/library/JJ204811(v=OCS.15))</span></span>

  - <span data-ttu-id="6cb4b-133">[Remove-CsPersistentChatEndpoint](https://technet.microsoft.com/library/JJ204626(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6cb4b-133">[Remove-CsPersistentChatEndpoint](https://technet.microsoft.com/library/JJ204626(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="6cb4b-134">[Remove-CsPersistentChatMessage](https://technet.microsoft.com/library/JJ204668(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6cb4b-134">[Remove-CsPersistentChatMessage](https://technet.microsoft.com/library/JJ204668(v=OCS.15))</span></span>

  - <span data-ttu-id="6cb4b-135">[Test-CsPersistentChatMessage](https://technet.microsoft.com/library/JJ204656(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6cb4b-135">[Test-CsPersistentChatMessage](https://technet.microsoft.com/library/JJ204656(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="6cb4b-136">[Get-CsPersistentChatPolicy](https://technet.microsoft.com/library/JJ204673(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6cb4b-136">[Get-CsPersistentChatPolicy](https://technet.microsoft.com/library/JJ204673(v=OCS.15))</span></span>

  - <span data-ttu-id="6cb4b-137">[Grant-CsPersistentChatPolicy](https://technet.microsoft.com/library/JJ204907(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6cb4b-137">[Grant-CsPersistentChatPolicy](https://technet.microsoft.com/library/JJ204907(v=OCS.15))</span></span>

  - <span data-ttu-id="6cb4b-138">[New-CsPersistentChatPolicy](https://technet.microsoft.com/library/JJ205396(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6cb4b-138">[New-CsPersistentChatPolicy](https://technet.microsoft.com/library/JJ205396(v=OCS.15))</span></span>

  - <span data-ttu-id="6cb4b-139">[Remove-CsPersistentChatPolicy](https://technet.microsoft.com/library/JJ205301(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6cb4b-139">[Remove-CsPersistentChatPolicy](https://technet.microsoft.com/library/JJ205301(v=OCS.15))</span></span>

  - <span data-ttu-id="6cb4b-140">[Set-CsPersistentChatPolicy](https://technet.microsoft.com/library/JJ205192(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6cb4b-140">[Set-CsPersistentChatPolicy](https://technet.microsoft.com/library/JJ205192(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="6cb4b-141">[Clear-CsPersistentChatRoom](https://technet.microsoft.com/library/JJ204976(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6cb4b-141">[Clear-CsPersistentChatRoom](https://technet.microsoft.com/library/JJ204976(v=OCS.15))</span></span>

  - <span data-ttu-id="6cb4b-142">[Get-CsPersistentChatRoom](https://technet.microsoft.com/library/JJ205123(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6cb4b-142">[Get-CsPersistentChatRoom](https://technet.microsoft.com/library/JJ205123(v=OCS.15))</span></span>

  - <span data-ttu-id="6cb4b-143">[New-CsPersistentChatRoom](https://technet.microsoft.com/library/JJ205166(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6cb4b-143">[New-CsPersistentChatRoom](https://technet.microsoft.com/library/JJ205166(v=OCS.15))</span></span>

  - <span data-ttu-id="6cb4b-144">[Remove-CsPersistentChatRoom](https://technet.microsoft.com/library/JJ204639(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6cb4b-144">[Remove-CsPersistentChatRoom](https://technet.microsoft.com/library/JJ204639(v=OCS.15))</span></span>

  - <span data-ttu-id="6cb4b-145">[Set-CsPersistentChatRoom](https://technet.microsoft.com/library/JJ204801(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6cb4b-145">[Set-CsPersistentChatRoom](https://technet.microsoft.com/library/JJ204801(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="6cb4b-146">[Get-CsPersistentChatState](https://technet.microsoft.com/library/JJ204915(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6cb4b-146">[Get-CsPersistentChatState](https://technet.microsoft.com/library/JJ204915(v=OCS.15))</span></span>

  - <span data-ttu-id="6cb4b-147">[Set-CsPersistentChatState](https://technet.microsoft.com/library/JJ205109(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6cb4b-147">[Set-CsPersistentChatState](https://technet.microsoft.com/library/JJ205109(v=OCS.15))</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

