---
title: 'Lync Server 2013: considerações de migração e de coexistência para IPv6'
description: 'Lync Server 2013: considerações de migração e de coexistência para IPv6.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Migration and coexistence considerations for IPv6
ms:assetid: 8c769c4f-c8a9-4cbf-9080-beee3be9848a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205068(v=OCS.15)
ms:contentKeyID: 48184751
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e8618cc14ff3c2467ea41df34e39f5094d1206dc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560987"
---
# <a name="migration-and-coexistence-considerations-for-ipv6-in-lync-server-2013"></a><span data-ttu-id="dab8a-103">Considerações de migração e de coexistência para IPv6 no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dab8a-103">Migration and coexistence considerations for IPv6 in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dab8a-104">_**Última modificação do tópico:** 2012-06-14_</span><span class="sxs-lookup"><span data-stu-id="dab8a-104">_**Topic Last Modified:** 2012-06-14_</span></span>

<span data-ttu-id="dab8a-105">O IP versão 6 (IPv6) não é suportado no Lync Server 2010 ou no Office Communications Server.</span><span class="sxs-lookup"><span data-stu-id="dab8a-105">IP version 6 (IPv6) is not supported on Lync Server 2010 or Office Communications Server.</span></span> <span data-ttu-id="dab8a-106">Para fins de piloto, é possível testar a coexistência de pilha dupla do Lync Server 2010 e do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="dab8a-106">For piloting purposes, you can test Lync Server 2010 and Lync Server 2013 dual-stack coexistence.</span></span> <span data-ttu-id="dab8a-107">Recomendamos que todos os pools de um determinado site central sejam atualizados para o Lync Server 2013 antes de habilitar o IPv6 (rede de pilha dupla) para qualquer um dos pools.</span><span class="sxs-lookup"><span data-stu-id="dab8a-107">We recommend that all pools for a given central site are upgraded to Lync Server 2013 before you enable IPv6 (dual-stack network) for any of the pools.</span></span> <span data-ttu-id="dab8a-108">Se for necessário configurar um pool apenas para IPv6, recomendamos que você defina um pool somente de IPv6 em seu ambiente de laboratório para testes.</span><span class="sxs-lookup"><span data-stu-id="dab8a-108">If you need to configure a pool for IPv6 only, we recommend that you set up an IPv6-only pool in your lab environment for testing.</span></span>

<span data-ttu-id="dab8a-109">Os cenários a seguir são suportados durante a migração e coexistência:</span><span class="sxs-lookup"><span data-stu-id="dab8a-109">The following scenarios are supported during migration and coexistence:</span></span>

  - <span data-ttu-id="dab8a-110">Lync Server 2013, Lync Server 2010 e Office Communications Server 2007 pools R2 no modo IPv4, coexistindo com o Lync Server 2013 no modo de pilha dupla.</span><span class="sxs-lookup"><span data-stu-id="dab8a-110">Lync Server 2013, Lync Server 2010, and Office Communications Server 2007 R2 pools in IPv4 mode, coexisting with Lync Server 2013 in dual-stack mode.</span></span>

  - <span data-ttu-id="dab8a-111">Lync Server 2013 pool no modo somente IPv6, se o pool somente IPv6 estiver em silo.</span><span class="sxs-lookup"><span data-stu-id="dab8a-111">Lync Server 2013 pool in IPv6-only mode, if the IPv6-only pool is siloed.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

