---
title: 'Lync Server 2013: Failover de banco de dados espelhado'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Failing over a mirrored database
ms:assetid: 70185476-e3d4-440a-9316-fa24b226343e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204991(v=OCS.15)
ms:contentKeyID: 48184450
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a943705f13cff4f015285b1ef74feb11dc540091
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829174"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-over-a-mirrored-database-in-lync-server-2013"></a><span data-ttu-id="8d83d-102">Failover de banco de dados espelhado no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8d83d-102">Failing over a mirrored database in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8d83d-103">_**Tópico da última modificação:** 2014-03-14_</span><span class="sxs-lookup"><span data-stu-id="8d83d-103">_**Topic Last Modified:** 2014-03-14_</span></span>

<span data-ttu-id="8d83d-104">Se você tiver configurado seu banco de dados back-end para usar o espelhamento sincronizado com uma testemunha, o failover será automático.</span><span class="sxs-lookup"><span data-stu-id="8d83d-104">If you have configured your back-end database to use synchronized mirroring with a witness, failover is automatic.</span></span> <span data-ttu-id="8d83d-105">Se você configurou o espelhamento sincronizado sem uma testemunha, poderá usar os procedimentos a seguir para fazer failover e failback do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="8d83d-105">If you have configured synchronized mirroring without a witness, you can use the following procedures to failover and failback your database.</span></span> <span data-ttu-id="8d83d-106">Você também pode usar esses procedimentos para fazer failover e failback manualmente dos bancos de dados, mesmo se tiver configurado uma testemunha.</span><span class="sxs-lookup"><span data-stu-id="8d83d-106">You can also use these procedures to manually failover and failback your databases even if you have configured a witness.</span></span>

<div>

## <a name="to-fail-over-your-back-end-database"></a><span data-ttu-id="8d83d-107">Para fazer failover em seu banco de dados back-end</span><span class="sxs-lookup"><span data-stu-id="8d83d-107">To fail over your back-end database</span></span>

1.  <span data-ttu-id="8d83d-108">Antes de realizar o failover, determine qual banco de dados back-end é o principal e qual é o espelho digitando o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="8d83d-108">Before failing over, determine which back-end database is the principal and which is the mirror by typing the following cmdlet:</span></span>
    
        Get-CsDatabaseMirrorState -PoolFqdn <poolFQDN> -DatabaseType User

2.  <span data-ttu-id="8d83d-109">Se o repositório de gerenciamento central estiver hospedado nesse pool, digite o cmdlet a seguir para determinar qual é a entidade de segurança e qual é o espelho do repositório de gerenciamento central:</span><span class="sxs-lookup"><span data-stu-id="8d83d-109">If the Central Management store is hosted in this pool, type the following cmdlet to determine which is the principal and which is the mirror for the Central Management store:</span></span>
    
        Get-CsDatabaseMirrorState -PoolFqdn <poolFQDN> -DatabaseType CentralMgmt

3.  <span data-ttu-id="8d83d-110">Executar o failover do banco de dados do usuário:</span><span class="sxs-lookup"><span data-stu-id="8d83d-110">Perform the failover of the user database:</span></span>
    
      - <span data-ttu-id="8d83d-111">Se o principal falhar e você estiver falhando no espelho, digite:</span><span class="sxs-lookup"><span data-stu-id="8d83d-111">If the primary has failed and you are failing over to the mirror, type:</span></span>
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType User -NewPrincipal mirror -Verbose
    
      - <span data-ttu-id="8d83d-112">Se o espelhamento falhar e você estiver falhando para o principal, digite:</span><span class="sxs-lookup"><span data-stu-id="8d83d-112">If the mirror has failed and you are failing over to the primary, type:</span></span>
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType User -NewPrincipal primary -Verbose

4.  <span data-ttu-id="8d83d-113">Se o pool hospedar o servidor central de gerenciamento, realize o failover do repositório de gerenciamento central.</span><span class="sxs-lookup"><span data-stu-id="8d83d-113">If the pool hosts the Central Management Server, perform the failover of the Central Management store.</span></span>
    
      - <span data-ttu-id="8d83d-114">Se o principal falhar e você estiver falhando no espelho, digite:</span><span class="sxs-lookup"><span data-stu-id="8d83d-114">If the primary has failed and you are failing over to the mirror, type:</span></span>
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType CentralMgmt -NewPrincipal mirror -Verbose
    
      - <span data-ttu-id="8d83d-115">Se o espelhamento falhar e você estiver falhando para o principal, digite:</span><span class="sxs-lookup"><span data-stu-id="8d83d-115">If the mirror has failed and you are failing over to the primary, type:</span></span>
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType CentralMgmt -NewPrincipal primary -Verbose

</div>

</div>

<span> </span>

</div>

</div>

</div>

