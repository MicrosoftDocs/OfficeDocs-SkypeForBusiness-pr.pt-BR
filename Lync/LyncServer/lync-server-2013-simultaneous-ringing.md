---
title: 'Lync Server 2013: toque simultâneo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Simultaneous ringing
ms:assetid: df02f919-4d50-4832-9300-6c51f8b4fc56
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994079(v=OCS.15)
ms:contentKeyID: 51803990
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: da250e04b3547e7ce6f00a73028ac3fcd083c30d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42200344"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="simultaneous-ringing-in-lync-server-2013"></a>Toque simultâneo no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-03-09_

Quando a parte chamada tem o toque simultâneo habilitado, o roteamento baseado em local analisa o local da parte de chamadas e os pontos de extremidade das partes chamadas para determinar se a chamada deve ser encaminhada.

A tabela a seguir ilustra um usuário configurado com toque simultâneo, e o alvo de toque simultâneo é um usuário no mesmo local de rede, em um site de rede diferente ou em um site de rede desconhecido.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Chamada PSTN de entrada para</th>
<th>Localizado no mesmo local de rede que o receptor da chamada</th>
<th>Localizado em um local de rede diferente do chamado</th>
<th>Localizado no local de rede desconhecido ou não habilitado para roteamento baseado em local</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Usuário do Lync</p></td>
<td><p>Anel simultâneo permitido</p></td>
<td><p>Toque simultâneo não permitido</p></td>
<td><p>Toque simultâneo não permitido</p></td>
</tr>
</tbody>
</table>

  
A tabela a seguir ilustra uma chamada de um usuário do Lync (ou seja, o chamador do Lync) no mesmo local de rede, em um site de rede diferente ou de um site de rede desconhecido. O receptor tem um ponto de extremidade PSTN (i.e. celular) configurado como um alvo de anel simultâneo. Neste cenário, o roteamento baseado em local determinará se a chamada deve ser roteada para o alvo de anel simultâneo (ou seja, celular) do receptor ou não.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Alvo de anel simultâneo</th>
<th>Localizado no mesmo local de rede que o receptor da chamada</th>
<th>Localizado em um local de rede diferente do chamado</th>
<th>Localizado no local de rede desconhecido ou não habilitado para roteamento baseado em local</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Ponto de extremidade PSTN</p></td>
<td><p>Toque simultâneo permitido por meio da política de roteamento de voz do site do chamador</p></td>
<td><p>Toque simultâneo permitido por meio da política de roteamento de voz do site do chamador</p></td>
<td><p>Toque simultâneo permitido por meio da política de voz do chamador para troncos não habilitados para roteamento baseado em local</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a>Confira também


[Cenários para roteamento baseado em local no Lync Server 2013](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

