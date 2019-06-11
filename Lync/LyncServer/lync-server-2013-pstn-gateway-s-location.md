---
title: 'Lync Server 2013: Local do gateway PSTN'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: PSTN gateway's location
ms:assetid: 49693a35-fad3-49ee-a71e-c7e4537b79aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994031(v=OCS.15)
ms:contentKeyID: 51803940
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b897d9ce438844cde7617bb7c3e1dae086605f09
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823543"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="pstn-gateways-location-in-lync-server-2013"></a>Local do gateway PSTN no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-03-09_

Chamadas roteadas por meio de gateways PSTN e PBXs podem exigir restrições de roteamento baseado em localização, dependendo do local de tais sistemas. O roteamento baseado em localização pode ser habilitado na granularidade com base em cada tronco.

O roteamento baseado em local introduz o seguinte conjunto de regras quando habilitado em um tronco:

  - Quando o roteamento baseado em localização estiver habilitado em uma base por tronco, as regras definidas nesse tronco serão aplicadas somente a chamadas roteadas por meio desse tronco.

  - Para evitar que as tarifas PSTNs ignorem onde as chamadas são originadas de um site de rede diferente que o site de rede onde o gateway PSTN está localizado, o roteamento baseado em local introduz a associação de um site de rede a um determinado tronco. Isso definirá o local de rede que permite o encaminhamento de chamadas para um tronco específico.

Os troncos podem ser habilitados para roteamento baseado em local de duas maneiras:

  - O tronco é definido para um gateway PSTN que egressa chamadas para a PSTN. As chamadas de entrada encaminhadas por um tronco desse tipo serão encaminhadas apenas para os pontos de extremidade localizados dentro do mesmo local de rede do tronco.

  - O tronco é definido para um peer do servidor de mediação que não faz chamadas para os usuários de serviços PSTN e PSTN com telefones herdados em locais estáticos (por exemplo, telefones PBX). Para essa configuração específica, todas as chamadas de entrada encaminhadas por um tronco desse tipo serão consideradas como originadas do mesmo local de rede do tronco. As chamadas de usuários do PBX terão a mesma imposição de roteamento com base no local que os usuários do Lync que estão localizados no mesmo local de rede que o tronco. Se dois sistemas PBX localizados em sites de rede separados estiverem conectados por meio do Lync Server, o roteamento baseado em local permitirá o roteamento de um ponto de extremidade de PBX em um site de rede para outro ponto de extremidade de PBX no outro site de rede. Esse cenário não será bloqueado pelo roteamento baseado em local. Além desse cenário e, de forma semelhante, como um usuário do Lync no mesmo local, os pontos de extremidade conectados a um servidor de mediação de servidor com essa configuração poderão fazer ou receber chamadas para e de outros pontos do servidor de mediação que não roteiam chamadas para o PSTN (i. e. um ponto de extremidade conectado a um PBX diferente) independentemente do site de rede ao qual o servidor de mediação está associado. Todas as chamadas recebidas, chamadas de saída, transferências de chamadas e encaminhamentos de chamadas que envolvem pontos de extremidade PSTN estarão sujeitas ao roteamento baseado em localização para usar somente gateways PSTN definidos como locais para o peer do servidor de mediação.

<div>

## <a name="see-also"></a>Confira também


[Orientação para Roteamento Baseado em Local no Lync Server 2013](lync-server-2013-guidance-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

