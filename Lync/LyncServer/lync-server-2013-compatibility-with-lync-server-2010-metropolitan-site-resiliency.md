---
title: Compatibilidade do Lync Server 2013 com resiliência de site metropolitano do Lync Server 2010
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
ms.openlocfilehash: 395ec568ebafea5c7a06e19340ff5ad10158ffb3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742741"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-server-2010-metropolitan-site-resiliency"></a>Resiliência de site metropolitano no Lync Server 2010

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2014-03-19_

A solução de resiliência de site metropolitana compatível com o Lync Server 2010 não é compatível com o Lync Server 2013. Esta solução envolve a inclusão de um único pool de front-end em dois data centers na mesma área metropolitana.

A solução Metropolitana de resiliência de site foi projetada para recuperar-se da perda de um data center completo. Quando você se estende pelo pool em dois datacenters, geralmente coloca metade dos seus front-ends em um datacenter e a outra metade do segundo datacenter. Se você perder um datacenter inteiro, perderá metade dos seus servidores front-end. Isso pode causar problemas com o novo modelo de sistema distribuído para pools de front-end no Lync Server 2013. Para obter mais informações, consulte [topologias e componentes para servidores front-end, mensagens instantâneas e presença no Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).

</div>

<span> </span>

</div>

</div>

</div>

