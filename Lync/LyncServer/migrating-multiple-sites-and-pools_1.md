---
title: Migrar vários sites e pools
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrating multiple sites and pools
ms:assetid: 3bf677d4-a5af-4f73-8fad-1abf5b668cc1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688025(v=OCS.15)
ms:contentKeyID: 49733615
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 71ff9164dcd824d6b836577b04783954cb81b067
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731051"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrating-multiple-sites-and-pools"></a><span data-ttu-id="21942-102">Migrar vários sites e pools</span><span class="sxs-lookup"><span data-stu-id="21942-102">Migrating multiple sites and pools</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="21942-103">_**Tópico da última modificação:** 2012-08-26_</span><span class="sxs-lookup"><span data-stu-id="21942-103">_**Topic Last Modified:** 2012-08-26_</span></span>

<span data-ttu-id="21942-104">O Lync Server 2013 oferece suporte a implantações de vários locais e vários pools.</span><span class="sxs-lookup"><span data-stu-id="21942-104">Lync Server 2013 supports multi-site and multi-pool deployments.</span></span> <span data-ttu-id="21942-105">O processo de migração de vários pools do Office Communications Server 2007 R2 para o Lync Server 2013 requer as seguintes considerações:</span><span class="sxs-lookup"><span data-stu-id="21942-105">The process of migrating multiple pools from Office Communications Server 2007 R2 to Lync Server 2013 requires the following considerations:</span></span>

1.  <span data-ttu-id="21942-106">Depois de implantar um pool piloto do Lync Server 2013, você precisa definir um subconjunto de usuários pilotos que serão movidos para o pool do Lync Server 2013 e uma metodologia para validar a funcionalidade dos usuários.</span><span class="sxs-lookup"><span data-stu-id="21942-106">After deploying a Lync Server 2013 pilot pool, you need to define a subset of pilot users that will be moved to the Lync Server 2013 pool, and a methodology for validating the functionality of the users.</span></span>

2.  <span data-ttu-id="21942-107">Depois de implantar um servidor de borda no pool piloto, você precisa validar que os usuários externos podem se comunicar com o pool do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="21942-107">After deploying an Edge Server in the pilot pool, you need to validate that external users can communicate with the Lync Server 2013 pool.</span></span>

3.  <span data-ttu-id="21942-108">Após a transição de rotas federadas dos servidores do Office Communications Server 2007 R2 Edge para os servidores piloto do Lync Server 2013 Edge, você precisa validar que os usuários federados podem se comunicar com o pool do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="21942-108">After transitioning the federated routes from Office Communications Server 2007 R2 Edge Servers to the pilot Lync Server 2013 Edge Servers, you need to validate that federated users can communicate with the Lync Server 2013 pool.</span></span>

4.  <span data-ttu-id="21942-109">Depois de mover todos os usuários e objetos de contato que não sejam usuários, você precisa validar que o pool do Office Communications Server 2007 R2 está vazio.</span><span class="sxs-lookup"><span data-stu-id="21942-109">After moving all the users and non-user contact objects, you need to validate that the Office Communications Server 2007 R2 pool is empty.</span></span>

5.  <span data-ttu-id="21942-110">Depois de verificar se o pool do Office Communications Server 2007 R2 está vazio, você pode desativar o pool.</span><span class="sxs-lookup"><span data-stu-id="21942-110">After verifying that the Office Communications Server 2007 R2 pool is empty, you can then deactivate the pool.</span></span>
    
    <span data-ttu-id="21942-111">Para obter detalhes sobre como desativar o pool herdado do Office Communications Server 2007 R2 e servidores, consulte [fase 10: descomissionar site herdado](phase-10-decommission-legacy-site.md).</span><span class="sxs-lookup"><span data-stu-id="21942-111">For details about how to deactivate the legacy Office Communications Server 2007 R2 pool and servers, see [Phase 10: Decommission legacy site](phase-10-decommission-legacy-site.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

