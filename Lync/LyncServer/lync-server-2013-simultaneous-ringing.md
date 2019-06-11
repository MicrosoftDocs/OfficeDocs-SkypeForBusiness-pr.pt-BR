---
title: 'Lync Server 2013: Toque simultâneo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Simultaneous ringing
ms:assetid: df02f919-4d50-4832-9300-6c51f8b4fc56
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994079(v=OCS.15)
ms:contentKeyID: 51803990
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f7303c1fc77d109bd08044c8acff56aaf538790d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844916"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="simultaneous-ringing-in-lync-server-2013"></a>Toque simultâneo no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-03-09_

Quando a parte chamada tem o toque simultâneo habilitado, o roteamento baseado em local analisa o local da parte de chamada e os pontos de extremidade das partes chamadas para determinar se a chamada deve ser roteada.

A tabela a seguir ilustra um usuário configurado com toque simultâneo, e o destino do toque simultâneo é um usuário no mesmo local de rede, em um local de rede diferente ou em um local de rede desconhecido.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Chamadas de entrada do PSTN para</th>
<th>Localizado no mesmo local de rede do destinatário da chamada</th>
<th>Localizado em um local de rede diferente do chamador</th>
<th>Localizado no site desconhecido de rede ou não habilitado para roteamento baseado em local</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Usuário do Lync</p></td>
<td><p>Toque simultâneo permitido</p></td>
<td><p>Toque simultâneo não permitido</p></td>
<td><p>Toque simultâneo não permitido</p></td>
</tr>
</tbody>
</table>

  
A tabela a seguir ilustra uma chamada de um usuário do Lync (ou seja, o chamador do Lync) no mesmo site de rede, em um site de rede diferente ou em um site de rede desconhecido. O destinatário da chamada tem um ponto de extremidade PSTN (ou seja, um telefone celular) configurado como um destino de toque simultâneo. Nesse cenário, o roteamento baseado em localização determinará se a chamada deve ser roteada para o destino de toque simultâneo (isto é, o celular) do receptor ou não.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Destino de toque simultâneo</th>
<th>Localizado no mesmo local de rede do destinatário da chamada</th>
<th>Localizado em um local de rede diferente do chamador</th>
<th>Localizado no site desconhecido de rede ou não habilitado para roteamento baseado em local</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Ponto de extremidade PSTN</p></td>
<td><p>Toque simultâneo permitido por meio da política de roteamento de voz do local do chamador</p></td>
<td><p>Toque simultâneo permitido por meio da política de roteamento de voz do local do chamador</p></td>
<td><p>Toque simultâneo permitido por meio da política de roteamento de voz do local do chamador para troncos não habilitados para o Roteamento com Base no Local</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a>Confira também


[Cenários para Roteamento Baseado em Local no Lync Server 2013](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

