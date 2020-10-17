---
title: Migrar vários sites e pools
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrating multiple sites and pools
ms:assetid: a6d726d2-564d-4b39-a97c-5656a673292a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205165(v=OCS.15)
ms:contentKeyID: 48185079
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d95f38ab0adc1457abee7cdd90e8f385f7176ce3
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527358"
---
# <a name="migrating-multiple-sites-and-pools"></a><span data-ttu-id="bb908-102">Migrar vários sites e pools</span><span class="sxs-lookup"><span data-stu-id="bb908-102">Migrating multiple sites and pools</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bb908-103">_**Última modificação do tópico:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="bb908-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="bb908-104">O Lync Server 2013 oferece suporte a implantações de vários locais e vários pools.</span><span class="sxs-lookup"><span data-stu-id="bb908-104">Lync Server 2013 supports multi-site and multi-pool deployments.</span></span> <span data-ttu-id="bb908-105">O processo de migração de vários pools do Lync Server 2010 para o Lync Server 2013 requer as seguintes considerações:</span><span class="sxs-lookup"><span data-stu-id="bb908-105">The process of migrating multiple pools from Lync Server 2010 to Lync Server 2013 requires the following considerations:</span></span>

1.  <span data-ttu-id="bb908-106">Depois de implantar um pool piloto do Lync Server 2013, você precisa definir um subconjunto de usuários piloto que serão movidos para o pool do Lync Server 2013 e uma metodologia para validar a funcionalidade dos usuários.</span><span class="sxs-lookup"><span data-stu-id="bb908-106">After deploying a Lync Server 2013 pilot pool, you need to define a subset of pilot users that will be moved to the Lync Server 2013 pool, and a methodology for validating the functionality of the users.</span></span> <span data-ttu-id="bb908-107">Por exemplo, depois de mover um usuário para o pool piloto, verifique se a política de conferência do usuário foi movida para o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bb908-107">For example, after moving a user to the pilot pool, verify the user’s conference policy has moved to Lync Server 2013.</span></span>

2.  <span data-ttu-id="bb908-108">Após implantar um servidor de borda no pool piloto, você precisará validar que os usuários externos podem se comunicar com o pool do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bb908-108">After deploying an Edge Server in the pilot pool, you need to validate that external users can communicate with the Lync Server 2013 pool.</span></span>

3.  <span data-ttu-id="bb908-109">Após a transição das rotas federadas dos servidores de borda do Lync Server 2010 para os servidores de borda do Lync Server 2013 piloto, você precisará validar que os usuários federados podem se comunicar com o pool 2013 do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="bb908-109">After transitioning the federated routes from Lync Server 2010 Edge Servers to the pilot Lync Server 2013 Edge Servers, you need to validate that federated users can communicate with the Lync Server 2013 pool.</span></span>

4.  <span data-ttu-id="bb908-110">Depois de mover todos os objetos de contato usuários e não usuários, é necessário validar que o pool do Lync Server 2010 está vazio.</span><span class="sxs-lookup"><span data-stu-id="bb908-110">After moving all the users and non-user contact objects, you need to validate that the Lync Server 2010 pool is empty.</span></span>

5.  <span data-ttu-id="bb908-111">Depois de verificar se o pool do Lync Server 2010 está vazio, você pode desativar o pool.</span><span class="sxs-lookup"><span data-stu-id="bb908-111">After verifying that the Lync Server 2010 pool is empty, you can then deactivate the pool.</span></span>
    
    <span data-ttu-id="bb908-112">Para obter detalhes sobre como desativar o pool e servidores herdados do Lync Server 2010, consulte [fase 8: encerrar pools herdados](phase-8-decommission-legacy-pools.md).</span><span class="sxs-lookup"><span data-stu-id="bb908-112">For details about how to deactivate the legacy Lync Server 2010 pool and servers, see [Phase 8: Decommission legacy pools](phase-8-decommission-legacy-pools.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

