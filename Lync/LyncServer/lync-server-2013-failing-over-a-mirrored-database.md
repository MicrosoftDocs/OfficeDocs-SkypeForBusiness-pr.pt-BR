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
ms.openlocfilehash: a5be1bfa3a2c9cfac24529de65d91d7b58f13842
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035003"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-over-a-mirrored-database-in-lync-server-2013"></a>Failover de um banco de dados espelhado no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2014-03-14_

Caso tenha configurado o banco de dados back-end para usar espelhamento sincronizado com uma testemunha, o failover será automático. Caso tenha configurado o espelhamento automático sem uma testemunha, você poderá usar os procedimentos a seguir para realizar failover e failback do banco de dados. Você também pode usar esses procedimentos para realizar failover e failback manual dos bancos de dados mesmo com uma testemunha configurada.

<div>

## <a name="to-fail-over-your-back-end-database"></a>Para realizar failover do banco de dados back-end

1.  Antes de realizar o failover, determine qual é o banco de dados back-end principal e qual é o espelho digitando o cmdlet a seguir:
    
        Get-CsDatabaseMirrorState -PoolFqdn <poolFQDN> -DatabaseType User

2.  Se o repositório de gerenciamento central estiver hospedado neste pool, digite o seguinte cmdlet para determinar qual é a entidade de segurança e qual é o espelho do repositório de gerenciamento central:
    
        Get-CsDatabaseMirrorState -PoolFqdn <poolFQDN> -DatabaseType CentralMgmt

3.  Realize o failover do banco de dados do usuário:
    
      - Se o principal falhar e você estiver realizando failover para o espelho, digite:
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType User -NewPrincipal mirror -Verbose
    
      - Se o espelho falhar e você estiver realizando failover para o principal, digite:
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType User -NewPrincipal primary -Verbose

4.  Se o pool hospedar o servidor de gerenciamento central, execute o failover do repositório de gerenciamento central.
    
      - Se o principal falhar e você estiver realizando failover para o espelho, digite:
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType CentralMgmt -NewPrincipal mirror -Verbose
    
      - Se o espelho falhar e você estiver realizando failover para o principal, digite:
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType CentralMgmt -NewPrincipal primary -Verbose

</div>

</div>

<span> </span>

</div>

</div>

</div>

