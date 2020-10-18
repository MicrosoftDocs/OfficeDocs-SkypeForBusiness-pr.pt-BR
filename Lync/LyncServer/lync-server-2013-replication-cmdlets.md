---
title: 'Lync Server 2013: cmdlets de replicação'
description: 'Lync Server 2013: cmdlets de replicação.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Replication cmdlets
ms:assetid: e0c49601-d2a3-45a1-b05c-26c7ff820708
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415677(v=OCS.15)
ms:contentKeyID: 48185527
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b253176101de61a07630ec141a318dd114776392
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576107"
---
# <a name="replication-cmdlets-in-lync-server-2013"></a><span data-ttu-id="f0c7b-103">Cmdlets de replicação no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f0c7b-103">Replication cmdlets in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f0c7b-104">_**Última modificação do tópico:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="f0c7b-104">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="f0c7b-105">Os cmdlets de replicação fornecem uma maneira de monitorar e gerenciar a replicação do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f0c7b-105">The replication cmdlets provide a way for you to both monitor and manage Lync Server replication.</span></span> <span data-ttu-id="f0c7b-106">Você pode usar esses cmdlets para definir as configurações de replicação; para monitorar o progresso da replicação; e forçar manualmente a replicação em um servidor.</span><span class="sxs-lookup"><span data-stu-id="f0c7b-106">You can use these cmdlets to configure replication settings; to monitor replication progress; and to manually force replication on a server.</span></span>

<div>

## <a name="replication-cmdlets"></a><span data-ttu-id="f0c7b-107">Replication Cmdlets</span><span class="sxs-lookup"><span data-stu-id="f0c7b-107">Replication Cmdlets</span></span>

<span data-ttu-id="f0c7b-108">Veja a seguir uma lista de cmdlets relacionados diretamente ao gerenciamento de replicação:</span><span class="sxs-lookup"><span data-stu-id="f0c7b-108">The following is a list of cmdlets that relate directly to managing replication:</span></span>

<span data-ttu-id="f0c7b-109">**CRR**</span><span class="sxs-lookup"><span data-stu-id="f0c7b-109">**Replication**</span></span>

  - <span></span>  
    <span data-ttu-id="f0c7b-110">[Debug-CsInterPoolReplication](https://technet.microsoft.com/library/JJ619185(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f0c7b-110">[Debug-CsInterPoolReplication](https://technet.microsoft.com/library/JJ619185(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="f0c7b-111">[Invoke-CsManagementStoreReplication](https://technet.microsoft.com/library/Gg413060(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f0c7b-111">[Invoke-CsManagementStoreReplication](https://technet.microsoft.com/library/Gg413060(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="f0c7b-112">[Get-CsManagementStoreReplicationStatus](https://technet.microsoft.com/library/Gg399052(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f0c7b-112">[Get-CsManagementStoreReplicationStatus](https://technet.microsoft.com/library/Gg399052(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="f0c7b-113">[Enable-CsReplica](https://technet.microsoft.com/library/Gg425965(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f0c7b-113">[Enable-CsReplica](https://technet.microsoft.com/library/Gg425965(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="f0c7b-114">[Test-CsReplica](https://technet.microsoft.com/library/JJ205289(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f0c7b-114">[Test-CsReplica](https://technet.microsoft.com/library/JJ205289(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="f0c7b-115">[Get-CsUserReplicatorConfiguration](https://technet.microsoft.com/library/Gg398548(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f0c7b-115">[Get-CsUserReplicatorConfiguration](https://technet.microsoft.com/library/Gg398548(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="f0c7b-116">[New-CsUserReplicatorConfiguration](https://technet.microsoft.com/library/Gg399059(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f0c7b-116">[New-CsUserReplicatorConfiguration](https://technet.microsoft.com/library/Gg399059(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="f0c7b-117">[Remove-CsUserReplicatorConfiguration](https://technet.microsoft.com/library/Gg425738(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f0c7b-117">[Remove-CsUserReplicatorConfiguration](https://technet.microsoft.com/library/Gg425738(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="f0c7b-118">[Set-CsUserReplicatorConfiguration](https://technet.microsoft.com/library/Gg398540(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f0c7b-118">[Set-CsUserReplicatorConfiguration](https://technet.microsoft.com/library/Gg398540(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f0c7b-119">Confira também</span><span class="sxs-lookup"><span data-stu-id="f0c7b-119">See Also</span></span>


[<span data-ttu-id="f0c7b-120">Blog do PowerShell do Lync Server</span><span class="sxs-lookup"><span data-stu-id="f0c7b-120">Lync Server PowerShell Blog</span></span>](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

