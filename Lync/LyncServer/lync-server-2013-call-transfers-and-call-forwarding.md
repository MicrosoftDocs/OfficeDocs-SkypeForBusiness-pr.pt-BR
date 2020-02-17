---
title: 'Lync Server 2013: transferências de chamadas e encaminhamento de chamadas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call transfers and call forwarding
ms:assetid: 978610ec-63c7-4cf6-ad7a-9ef91559bf12
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994051(v=OCS.15)
ms:contentKeyID: 51803962
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 46b16ad2faac58a5999b803c75d02e01da0da2dd
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044293"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-transfers-and-call-forwarding-in-lync-server-2013"></a>Transferências de chamadas e encaminhamento de chamadas no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-03-09_

Quando um ponto de extremidade PSTN está envolvido, o roteamento baseado em local analisa o local do ponto de extremidade do Calle e o ponto de extremidade onde a chamada será transferida ou encaminhada (ou seja, transferir/direcionar destino). O roteamento baseado em local determina se a chamada deve ser transferida ou encaminhada, dependendo do local dos dois pontos de extremidade.

A tabela a seguir ilustra o cenário de um usuário do Lync em uma chamada com um ponto de extremidade PSTN e o usuário do Lync transfere a chamada para outro usuário do Lync. Dependendo do local do site de rede do ponto de extremidade do intermediário, o roteamento baseado em local afeta o roteamento da transferência de chamada ou do encaminhamento.

### <a name="initiating-call-transfer-or-forward"></a>Iniciando transferência ou encaminhamento de chamadas

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Usuário iniciando a transferência/encaminhamento de chamada</th>
<th>O ponto de extremidade de destino está no mesmo local de rede que o usuário que inicia a transferência de chamada ou encaminha</th>
<th>O ponto de extremidade de destino está em um local de rede diferente como usuário Iniciando transferência de chamada ou encaminhar</th>
<th>O ponto de extremidade de destino está em um site de rede desconhecido ou site de rede não habilitado para roteamento baseado em local</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Usuário do Lync</p></td>
<td><p>Encaminhamento ou transferência de chamada permitido</p></td>
<td><p>Encaminhamento ou transferência de chamada não permitido</p></td>
<td><p>Encaminhamento ou transferência de chamada não permitido</p></td>
</tr>
</tbody>
</table>

  

Por exemplo: um usuário do Lync em uma chamada com um ponto de extremidade PSTN transfere a chamada para outro usuário do Lync que esteja no mesmo local de rede. Nesse caso, a transferência de chamada é permitida.

A tabela a seguir ilustra o cenário de um usuário do Lync em uma chamada com outro usuário do Lync e um dos usuários transfere a chamada para um ponto de extremidade PSTN. Dependendo do local do usuário para o qual a chamada está sendo transferida, a tabela detalha como o roteamento baseado em local afeta a chamada.

### <a name="call-transfer-or-forward-to-pstn-endpoint"></a>Transferência de chamada ou encaminhamento para ponto de extremidade PSTN

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Transferência de chamada/destino de ponto de extremidade de encaminhamento</th>
<th>Usuários do Lync no mesmo local de rede</th>
<th>Usuários do Lync em diferentes locais de rede</th>
<th>Um ou ambos os usuários do Lync em um site de rede desconhecido ou site de rede não habilitado para roteamento baseado em local</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Ponto de extremidade PSTN</p></td>
<td><p>Encaminhamento ou transferência de chamada permitida pela política de roteamento de voz do site do usuário transferido</p></td>
<td><p>Encaminhamento ou transferência de chamada permitida pela política de roteamento de voz do site do usuário transferido</p></td>
<td><p>Encaminhamento ou transferência de chamada permitida pela política de voz do usuário transferido apenas por meio de troncos não habilitados para roteamento baseado em local</p></td>
</tr>
</tbody>
</table>

  
Por exemplo: um usuário do Lync em uma chamada com outro usuário do Lync que está no mesmo local de rede transfere a chamada para um ponto de extremidade PSTN e a transferência de chamada é permitida.

<div>

## <a name="see-also"></a>Confira Também


[Cenários para roteamento baseado em local no Lync Server 2013](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

