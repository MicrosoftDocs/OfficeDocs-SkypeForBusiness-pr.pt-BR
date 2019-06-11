---
title: 'Lync Server 2013: Transferência e encaminhamento de chamadas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Call transfers and call forwarding
ms:assetid: 978610ec-63c7-4cf6-ad7a-9ef91559bf12
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994051(v=OCS.15)
ms:contentKeyID: 51803962
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6d5b0661cfaaef2e514f070260f44abc4ea00572
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836685"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-transfers-and-call-forwarding-in-lync-server-2013"></a>Transferência e encaminhamento de chamadas no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-03-09_

Quando um ponto de extremidade PSTN está envolvido, o roteamento baseado em localização analisa o local do ponto de extremidade do Calle e o ponto de extremidade onde a chamada será transferida ou encaminhada (ou seja, transferência/destino para encaminhamento). O roteamento baseado em local determina se a chamada deve ser transferida ou encaminhada, dependendo da localização dos dois pontos de extremidade.

A tabela a seguir ilustra o cenário de um usuário do Lync em uma chamada com um ponto de extremidade PSTN, e o usuário do Lync transfere a chamada para outro usuário do Lync. Dependendo do local do site de rede do ponto de extremidade do transportador, o roteamento baseado em local afeta o roteamento da transferência ou encaminhamento de chamadas.

### <a name="initiating-call-transfer-or-forward"></a>Iniciando a transferência ou o encaminhamento de chamada

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Usuário que inicia a transferência/encaminhamento da chamada</th>
<th>O ponto de extremidade de destino está no mesmo local de rede do usuário que inicia a transferência ou o encaminhamento da chamada</th>
<th>O ponto de extremidade de destino está em um local de rede diferente do que o do usuário que inicia a transferência ou o encaminhamento da chamada</th>
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

  

Por exemplo: um usuário do Lync em uma chamada com um ponto de extremidade PSTN transfere a chamada para outro usuário do Lync que esteja no mesmo site de rede. Nesse caso, a transferência de chamada é permitida.

A tabela a seguir ilustra o cenário de um usuário do Lync em uma chamada com outro usuário do Lync, e um dos usuários transfere a chamada para um ponto de extremidade PSTN. Dependendo do local do usuário para o qual a chamada está sendo transferida, a tabela detalhará como o Roteamento Baseado na Localização afeta a chamada.

### <a name="call-transfer-or-forward-to-pstn-endpoint"></a>Transferência ou encaminhamento de chamada para um ponto de extremidade PSTN

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Destino do ponto de extremidade da transferência/encaminhamento de chamada</th>
<th>Usuários do Lync no mesmo local de rede</th>
<th>Usuários do Lync em diferentes sites de rede</th>
<th>Um ou ambos os usuários do Lync em um site de rede desconhecido ou site de rede não estão habilitados para roteamento baseado em local</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Ponto de extremidade PSTN</p></td>
<td><p>O encaminhamento ou a transferência de chamada é permitida pela política de roteamento de voz do local do usuário transferido</p></td>
<td><p>O encaminhamento ou a transferência de chamada é permitida pela política de roteamento de voz do local do usuário transferido</p></td>
<td><p>O encaminhamento ou a transferência da chamada é permitida pela política de voz do destinatário da transferência somente pelos troncos não habilitados para o Roteamento com Base no Local</p></td>
</tr>
</tbody>
</table>

  
Por exemplo: um usuário do Lync em uma chamada com outro usuário do Lync que esteja no mesmo local de rede transfere a chamada para um ponto de extremidade PSTN e a transferência de chamada é permitida.

<div>

## <a name="see-also"></a>Confira também


[Cenários para Roteamento Baseado em Local no Lync Server 2013](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

