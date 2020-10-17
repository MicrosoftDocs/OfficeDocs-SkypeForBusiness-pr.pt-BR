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
ms.openlocfilehash: 05147e469ce120663992e5ae7b8a3ee59acaf78c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526608"
---
# <a name="incoming-calls-in-lync-server-2013"></a>Chamadas de entrada no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-03-09_

O roteamento de chamadas de entrada para usuários habilitados para roteamento Location-Based depende do local do ponto de extremidade do usuário. O roteamento de chamadas de entrada é afetado da seguinte maneira. Se um usuário tiver uma chamada de entrada para um ponto de extremidade localizado em um site de rede habilitado para roteamento Location-Based e o ponto de extremidade estiver localizado no mesmo local de rede que o gateway PSTN, a chamada será encaminhada. Se um usuário tiver uma chamada de entrada para um ponto de extremidade localizado em um local de rede habilitado para roteamento Location-Based e o ponto de extremidade estiver localizado em um local de rede diferente do gateway PSTN, a chamada não será encaminhada. Quando um usuário não tem pontos de extremidade localizados no mesmo local de rede que o gateway PSTN em que a chamada de entrada é originada, a chamada de entrada será roteada diretamente para a caixa postal do usuário e uma notificação de chamada não atendida será enviada à parte chamada.

As configurações de encaminhamento de chamadas de um usuário habilitado para roteamento de Location-Based continuarão a ser impostas, no entanto, as chamadas encaminhadas serão sujeitas às restrições de roteamento Location-Based do usuário.

A tabela a seguir ilustra como Location-Based roteamento afeta o roteamento de chamadas de entrada, dependendo do local do ponto de extremidade do destinatário da chamada. O site de rede do gateway PSTN é habilitado para roteamento Location-Based e Location-Based roteamento permite o roteamento de chamadas PSTN para pontos de extremidade dentro do mesmo local de rede.

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
<th>Ponto de extremidade do receptor localizado no local de rede desconhecido ou não habilitado para roteamento de Location-Based</th>
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


[Cenários para Location-Based roteamento no Lync Server 2013](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

