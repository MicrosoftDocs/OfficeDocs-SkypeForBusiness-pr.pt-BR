---
title: 'Lync Server 2013: chamadas de entrada'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Incoming calls
ms:assetid: 65b9c1b4-6af7-4527-8c33-22c4442bd209
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994038(v=OCS.15)
ms:contentKeyID: 51803948
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c153af6e14c291189f714f7054f72301d6859a88
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036831"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="incoming-calls-in-lync-server-2013"></a>Chamadas de entrada no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-03-09_

O roteamento de chamadas de entrada para usuários habilitados para roteamento baseado em local depende do local do ponto de extremidade do usuário. O roteamento de chamadas de entrada é afetado da seguinte maneira. Se um usuário tiver uma chamada de entrada para um ponto de extremidade localizado em um local de rede habilitado para roteamento baseado em local e o ponto de extremidade estiver localizado no mesmo local de rede que o gateway PSTN, a chamada será encaminhada. Se um usuário tiver uma chamada de entrada para um ponto de extremidade localizado em um local de rede habilitado para roteamento baseado em local e o ponto de extremidade estiver localizado em um local de rede diferente do gateway PSTN, a chamada não será roteada. Quando um usuário não tem pontos de extremidade localizados no mesmo local de rede que o gateway PSTN em que a chamada de entrada é originada, a chamada de entrada será roteada diretamente para a caixa postal do usuário e uma notificação de chamada não atendida será enviada à parte chamada.

As configurações de encaminhamento de chamadas de um usuário habilitado para roteamento baseado em local continuarão a ser impostas, no entanto, as chamadas encaminhadas serão sujeitas a restrições de roteamento com base no local do usuário.

A tabela a seguir ilustra como o roteamento baseado em local afeta o roteamento de chamadas de entrada, dependendo do local do ponto de extremidade do destinatário da chamada. O site de rede do gateway PSTN está habilitado para roteamento baseado em local e o roteamento baseado em local permite o roteamento de chamadas PSTN para pontos de extremidade no mesmo local de rede.

### <a name="callee-receiving-an-inbound-call-from-the-pstn"></a>Receptor que recebe uma chamada de entrada da PSTN

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>Ponto de extremidade do receptor localizado no mesmo local de rede que o gateway PSTN</th>
<th>Ponto de extremidade do receptor não localizado no mesmo local de rede que o gateway PSTN</th>
<th>Ponto de extremidade do receptor localizado no local de rede desconhecido ou não habilitado para roteamento baseado em local</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Roteamento de chamadas PSTN de entrada</p></td>
<td><p>A chamada de entrada é encaminhada para os pontos de extremidade do destinatário da chamada</p></td>
<td><p>A chamada de entrada não é encaminhada para os pontos de extremidade do destinatário da chamada</p></td>
<td><p>A chamada de entrada não é encaminhada para os pontos de extremidade do destinatário da chamada</p></td>
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

