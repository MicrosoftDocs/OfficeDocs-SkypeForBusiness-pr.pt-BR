---
title: 'Lync Server 2013: local do gateway PSTN'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: PSTN gateway's location
ms:assetid: 49693a35-fad3-49ee-a71e-c7e4537b79aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994031(v=OCS.15)
ms:contentKeyID: 51803940
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b3ff0e3ea426a8f3aa053b057b616148a42ad409
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042058"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="pstn-gateways-location-in-lync-server-2013"></a>Local do gateway PSTN no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-03-09_

Chamadas roteadas por meio de gateways PSTN e PBXs podem exigir restrições de roteamento com base no local dependendo do local desses sistemas. O roteamento baseado em local pode ser habilitado na granularidade em uma base por tronco.

O roteamento baseado em local introduz o seguinte conjunto de regras quando habilitado em um tronco:

  - Quando o roteamento baseado em local é habilitado em uma base por tronco, as regras definidas nesse tronco serão aplicadas apenas às chamadas encaminhadas através desse tronco.

  - Para evitar que as chamadas PSTN ignorem o local em que as chamadas são originadas de um site de rede diferente que o local da rede onde o gateway PSTN está localizado, o roteamento baseado em local introduz a associação de um site de rede a um determinado tronco. Isso define o local de rede que permite que as chamadas sejam roteadas para um determinado tronco.

Os troncos podem ser habilitados para roteamento baseado em local de duas maneiras:

  - O tronco é definido para um gateway PSTN que egresso as chamadas para a PSTN. As chamadas de entrada encaminhadas por um tronco desse tipo serão roteadas somente para pontos de extremidade localizados no mesmo local de rede que o tronco.

  - O tronco é definido para um ponto de servidor de mediação que não faz chamadas de saída para os usuários PSTN e serviços com telefones herdados em locais estáticos (por exemplo, telefones PBX). Para essa configuração específica, todas as chamadas de entrada encaminhadas por um tronco desse tipo serão consideradas originadas do mesmo local de rede que o tronco. As chamadas de usuários PBX terão a mesma imposição de roteamento com base no local que os usuários do Lync localizados no mesmo local de rede do tronco. Se dois sistemas PBX localizados em sites de rede separados estiverem conectados por meio do Lync Server, o roteamento baseado em local permitirá o roteamento de um ponto de extremidade de PBX em um local de rede para outro ponto de extremidade de PBX no outro site de rede. Este cenário não será bloqueado pelo roteamento baseado em local. Além desse cenário e, de forma semelhante, como um usuário do Lync no mesmo local, os pontos de extremidade conectados a um ponto de servidor de mediação com essa configuração poderão fazer ou receber chamadas para e de outro ponto de servidor de mediação que não roteia chamadas para o PSTN (i. e. um ponto de extremidade conectado a um PBX diferente), independentemente do local de rede ao qual o ponto do servidor de mediação está associado. Todas as chamadas de entrada, chamadas de saída, transferências de chamadas e encaminhamentos de chamadas envolvendo pontos de extremidade PSTN serão sujeitas ao roteamento baseado em local para usar somente gateways PSTN definidos como locais para esse ponto de servidor de mediação.

<div>

## <a name="see-also"></a>Confira também


[Orientação para roteamento baseado em local no Lync Server 2013](lync-server-2013-guidance-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

