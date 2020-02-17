---
title: 'Lync Server 2013: chamadas de saída'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Outgoing calls
ms:assetid: 885ffe6f-cd51-4f21-8d4f-a1ff8d818858
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994049(v=OCS.15)
ms:contentKeyID: 51803960
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ca0cdc7781143b0e76ff83a980f00da58c814f02
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049563"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="outgoing-calls-in-lync-server-2013"></a>Chamadas de saída no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-03-09_

O roteamento de chamadas de saída de usuários habilitados para roteamento baseado em local é afetado pelo local de rede do ponto de extremidade do usuário. A tabela a seguir ilustra como o roteamento baseado em local afeta o roteamento de chamadas de saída, dependendo do local do ponto de extremidade do chamador.

### <a name="caller-placing-an-outbound-call-to-the-pstn"></a>Chamador colocando uma chamada de saída para o PSTN

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>Ponto de extremidade do usuário localizado em um site de rede habilitado para roteamento baseado em local</th>
<th>Ponto de extremidade do usuário localizado em um local de rede desconhecido ou não habilitado para roteamento baseado em local</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Autorização de chamadas de saída</p></td>
<td><p>A chamada é autorizada com base na política de voz do usuário</p></td>
<td><p>A chamada é autorizada com base na política de voz do usuário</p></td>
</tr>
<tr class="even">
<td><p>Roteamento de chamada de saída</p></td>
<td><p>A chamada é roteada de acordo com a política de roteamento de voz do site da rede</p></td>
<td><p>A chamada é roteada de acordo com a política de voz do usuário e apenas por troncos não habilitados para roteamento baseado em local (se disponível)</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a>Confira Também


[Cenários para roteamento baseado em local no Lync Server 2013](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

