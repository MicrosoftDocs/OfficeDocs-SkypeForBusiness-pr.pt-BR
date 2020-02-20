---
title: 'Lync Server 2013: falha em um banco de dados espelhado'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failing over a mirrored database
ms:assetid: 70185476-e3d4-440a-9316-fa24b226343e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204991(v=OCS.15)
ms:contentKeyID: 48184450
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a02b82757f3754bd792e18f89f9133a764dc3341
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145870"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="failing-over-a-mirrored-database-in-lync-server-2013"></a><span data-ttu-id="e9e2d-102">Failover de um banco de dados espelhado no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e9e2d-102">Failing over a mirrored database in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e9e2d-103">_**Última modificação do tópico:** 2014-03-14_</span><span class="sxs-lookup"><span data-stu-id="e9e2d-103">_**Topic Last Modified:** 2014-03-14_</span></span>

<span data-ttu-id="e9e2d-p101">Caso tenha configurado o banco de dados back-end para usar espelhamento sincronizado com uma testemunha, o failover será automático. Caso tenha configurado o espelhamento automático sem uma testemunha, você poderá usar os procedimentos a seguir para realizar failover e failback do banco de dados. Você também pode usar esses procedimentos para realizar failover e failback manual dos bancos de dados mesmo com uma testemunha configurada.</span><span class="sxs-lookup"><span data-stu-id="e9e2d-p101">If you have configured your back-end database to use synchronized mirroring with a witness, failover is automatic. If you have configured synchronized mirroring without a witness, you can use the following procedures to failover and failback your database. You can also use these procedures to manually failover and failback your databases even if you have configured a witness.</span></span>

<div>

## <a name="to-fail-over-your-back-end-database"></a><span data-ttu-id="e9e2d-107">Para realizar failover do banco de dados back-end</span><span class="sxs-lookup"><span data-stu-id="e9e2d-107">To fail over your back-end database</span></span>

1.  <span data-ttu-id="e9e2d-108">Antes de realizar o failover, determine qual é o banco de dados back-end principal e qual é o espelho digitando o cmdlet a seguir:</span><span class="sxs-lookup"><span data-stu-id="e9e2d-108">Before failing over, determine which back-end database is the principal and which is the mirror by typing the following cmdlet:</span></span>
    
        Get-CsDatabaseMirrorState -PoolFqdn <poolFQDN> -DatabaseType User

2.  <span data-ttu-id="e9e2d-109">Se o repositório de gerenciamento central estiver hospedado neste pool, digite o seguinte cmdlet para determinar qual é a entidade de segurança e qual é o espelho do repositório de gerenciamento central:</span><span class="sxs-lookup"><span data-stu-id="e9e2d-109">If the Central Management store is hosted in this pool, type the following cmdlet to determine which is the principal and which is the mirror for the Central Management store:</span></span>
    
        Get-CsDatabaseMirrorState -PoolFqdn <poolFQDN> -DatabaseType CentralMgmt

3.  <span data-ttu-id="e9e2d-110">Realize o failover do banco de dados do usuário:</span><span class="sxs-lookup"><span data-stu-id="e9e2d-110">Perform the failover of the user database:</span></span>
    
      - <span data-ttu-id="e9e2d-111">Se o principal falhar e você estiver realizando failover para o espelho, digite:</span><span class="sxs-lookup"><span data-stu-id="e9e2d-111">If the primary has failed and you are failing over to the mirror, type:</span></span>
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType User -NewPrincipal mirror -Verbose
    
      - <span data-ttu-id="e9e2d-112">Se o espelho falhar e você estiver realizando failover para o principal, digite:</span><span class="sxs-lookup"><span data-stu-id="e9e2d-112">If the mirror has failed and you are failing over to the primary, type:</span></span>
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType User -NewPrincipal primary -Verbose

4.  <span data-ttu-id="e9e2d-113">Se o pool hospedar o servidor de gerenciamento central, execute o failover do repositório de gerenciamento central.</span><span class="sxs-lookup"><span data-stu-id="e9e2d-113">If the pool hosts the Central Management Server, perform the failover of the Central Management store.</span></span>
    
      - <span data-ttu-id="e9e2d-114">Se o principal falhar e você estiver realizando failover para o espelho, digite:</span><span class="sxs-lookup"><span data-stu-id="e9e2d-114">If the primary has failed and you are failing over to the mirror, type:</span></span>
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType CentralMgmt -NewPrincipal mirror -Verbose
    
      - <span data-ttu-id="e9e2d-115">Se o espelho falhar e você estiver realizando failover para o principal, digite:</span><span class="sxs-lookup"><span data-stu-id="e9e2d-115">If the mirror has failed and you are failing over to the primary, type:</span></span>
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType CentralMgmt -NewPrincipal primary -Verbose

</div>

</div>

<span> </span>

</div>

</div>

</div>

