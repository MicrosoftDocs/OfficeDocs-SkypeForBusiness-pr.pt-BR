---
title: 'Lync Server 2013: Chamadas de entrada'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Incoming calls
ms:assetid: 65b9c1b4-6af7-4527-8c33-22c4442bd209
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994038(v=OCS.15)
ms:contentKeyID: 51803948
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c007fbaec317a8e9d9d374ea62dafcab6c7a63f4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829015"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="incoming-calls-in-lync-server-2013"></a>Chamadas de entrada no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-03-09_

O roteamento de chamadas de entrada para usuários habilitados para roteamento baseado em locais depende do local do ponto de extremidade do usuário. Veja a seguir como o roteamento das chamadas de entrada é afetado. Se um usuário tiver uma chamada de entrada para um ponto de extremidade localizado em um site de rede habilitado para roteamento baseado em local, e o ponto de extremidade estiver localizado no mesmo site de rede que o gateway PSTN, a chamada será roteada. Se um usuário tiver uma chamada de entrada para um ponto de extremidade localizado em um site de rede habilitado para roteamento baseado em local, e o ponto de extremidade estiver localizado em um site de rede diferente do que o gateway PSTN, a chamada não será roteada. Quando um usuário não tiver pontos de extremidade localizados no mesmo local de rede do gateway PSTN do qual a chamada de entrada é originada, a chamada de entrada será encaminhada diretamente para o correio de voz do usuário e uma notificação de chamada perdida será enviada para a parte chamada.

As configurações de encaminhamento de chamadas de um usuário habilitado para roteamento baseado em local continuarão a ser impostas, entretanto, as chamadas encaminhadas estarão sujeitas às restrições de roteamento baseadas em localização do usuário.

A tabela a seguir ilustra como o roteamento baseado em localização afeta o roteamento de chamadas recebidas dependendo da localização do ponto de extremidade do chamador. O site de rede do gateway PSTN está habilitado para roteamento baseado em localização, e o roteamento baseado em local permite o roteamento de chamadas PSTN para pontos de extremidade dentro do mesmo site de rede.

### <a name="callee-receiving-an-inbound-call-from-the-pstn"></a>O destinatário da chamada recebe uma chamada de entrada da PSTN

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
<th>O ponto de extremidade do destinatário da chamada está localizado no mesmo local de rede do gateway PSTN</th>
<th>O ponto de extremidade do destinatário da chamada não fica no mesmo local de rede que o gateway PSTN</th>
<th>O ponto de extremidade do destinatário da chamada está localizado em um local de rede desconhecido ou não habilitado para Roteamento Baseado na Localização</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Roteamento da chamada PSTN recebida</p></td>
<td><p>A chamada de entrada é encaminhada para os pontos de extremidade do destinatário da chamada</p></td>
<td><p>A chamada de entrada não é encaminhada para os pontos de extremidade do destinatário da chamada</p></td>
<td><p>A chamada de entrada não é encaminhada para os pontos de extremidade do destinatário da chamada</p></td>
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

