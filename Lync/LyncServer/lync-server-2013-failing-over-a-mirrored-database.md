---
title: 'Lync Server 2013: Failover de banco de dados espelhado'
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
ms.openlocfilehash: 822a7a2fa13ce444bbaf590ee0d8ba2144debcc7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756145"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-over-a-mirrored-database-in-lync-server-2013"></a>Failover de banco de dados espelhado no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2014-03-14_

Se você tiver configurado seu banco de dados back-end para usar o espelhamento sincronizado com uma testemunha, o failover será automático. Se você configurou o espelhamento sincronizado sem uma testemunha, poderá usar os procedimentos a seguir para fazer failover e failback do banco de dados. Você também pode usar esses procedimentos para fazer failover e failback manualmente dos bancos de dados, mesmo se tiver configurado uma testemunha.

<div>

## <a name="to-fail-over-your-back-end-database"></a>Para fazer failover em seu banco de dados back-end

1.  Antes de realizar o failover, determine qual banco de dados back-end é o principal e qual é o espelho digitando o seguinte cmdlet:
    
        Get-CsDatabaseMirrorState -PoolFqdn <poolFQDN> -DatabaseType User

2.  Se o repositório de gerenciamento central estiver hospedado nesse pool, digite o cmdlet a seguir para determinar qual é a entidade de segurança e qual é o espelho do repositório de gerenciamento central:
    
        Get-CsDatabaseMirrorState -PoolFqdn <poolFQDN> -DatabaseType CentralMgmt

3.  Executar o failover do banco de dados do usuário:
    
      - Se o principal falhar e você estiver falhando no espelho, digite:
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType User -NewPrincipal mirror -Verbose
    
      - Se o espelhamento falhar e você estiver falhando para o principal, digite:
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType User -NewPrincipal primary -Verbose

4.  Se o pool hospedar o servidor central de gerenciamento, realize o failover do repositório de gerenciamento central.
    
      - Se o principal falhar e você estiver falhando no espelho, digite:
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType CentralMgmt -NewPrincipal mirror -Verbose
    
      - Se o espelhamento falhar e você estiver falhando para o principal, digite:
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType CentralMgmt -NewPrincipal primary -Verbose

</div>

</div>

<span> </span>

</div>

</div>

</div>

