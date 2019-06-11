---
title: 'Lync Server 2013: Failback de pool'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Failing back a pool
ms:assetid: 6232b644-ef57-4c9c-abec-14ff8ffc9fe7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204945(v=OCS.15)
ms:contentKeyID: 48184289
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cade83015f57e86e08978ac3bfd9fb848dae9563
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829178"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-back-a-pool-in-lync-server-2013"></a>Failback de pool no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-11-01_

Após o pool que sofreu o desastre ficar online novamente (ou seja, Pool1 neste exemplo), siga as etapas a seguir para restaurar a implantação para o status de trabalho normal.

Observe que o processo de failback demora vários minutos para ser concluído.Para referência, a expectativa é de até 60 minutos para um pool de 20.000 usuários.

1.  Reproduza os usuários que estavam originalmente hospedados no Pool1 e que falharam no Pool2 digitando o seguinte cmdlet:
    
        Invoke-CsPoolFailback -PoolFQDN <Pool1 FQDN> -Verbose

Nenhuma outra etapa é necessária. Se você tiver reprovado o servidor central de gerenciamento, poderá deixá-lo no Pool2.

</div>

<span> </span>

</div>

</div>

</div>

