---
title: 'Lync Server 2013: Local do usuário'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: User's location
ms:assetid: ce57941d-086b-448e-8ada-c7d636a2a1c9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994073(v=OCS.15)
ms:contentKeyID: 51803984
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4e9eac8fce71d99e0817c57841e2539ed6423f2a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844531"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="users-location-in-lync-server-2013"></a>Local do usuário no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-03-09_

O roteamento baseado em local aproveita as mesmas regiões de rede, sites e sub-redes, conforme definido no Lync Server usado por E9-1-1, CAC e bypass de mídia para aplicar restrições de roteamento de chamadas para impedir o bypass de chamada PSTN. A localização de um usuário é determinada pela sub-rede IP do (s) ponto (s) do Lync do usuário está conectado (s). Cada sub-rede IP está associada a um local de rede que, por sua vez, está agregado a regiões de rede definidas pelo administrador. O Roteamento Baseado na Localização é imposto com base no local de rede do usuário.

As regras de roteamento baseadas em local são aplicadas por site de rede, o que significa que um determinado conjunto de regras será aplicado a todos os pontos de extremidade habilitados para roteamento baseado em local localizado dentro do mesmo local de rede. Os administradores podem aplicar o Roteamento Baseado na Localização aos locais de rede que necessitarem dele.

As políticas de roteamento de voz podem ser definidas por local de rede a fim de determinar um gateway PSTN específico que deve ser usado por todos os usuários localizados no local de rede para chamar números de telefone PSTN. Essas políticas de roteamento de voz terão precedência sobre o roteamento definido pela política de voz do usuário quando o usuário estiver localizado em um site de rede habilitado para roteamento baseado em local, e ele impedirá o roteamento de chamadas por meio de outros gateways PSTN habilitados para Roteamento baseado em local. Quando um usuário do Lync coloca uma chamada PSTN, a política de voz do usuário determina se o usuário pode ser autorizado a fazer a chamada. Se a política de voz do usuário permitir que o usuário faça a chamada, o roteamento baseado em local determinará de qual gateway PSTN a chamada deve fazer a saída. O roteamento baseado em local faz essa determinação com base na localização do usuário.

O local de um usuário pode ser categorizado das seguintes maneiras:

  - O usuário está localizado em um site de rede conhecido habilitado para roteamento baseado em localização, e seu número DID (Direct Inward Dial) termina em um gateway PSTN colocado no mesmo local de rede (por exemplo, Office). O roteamento das chamadas de saída será feito pela política de roteamento de voz do local de rede em que o usuário está localizado. As chamadas PSTN de entrada para o usuário serão encaminhadas para pontos de extremidade localizados no mesmo local de rede do gateway PSTN.

  - O usuário está em um local de rede conhecido que fica em um local de rede diferente do gateway PSTN (isto é, o usuário viajou para outro escritório da empresa). O roteamento das chamadas de saída será feito pela política de roteamento de voz do local de rede em que o usuário está localizado. As chamadas PSTN de entrada para o usuário não serão encaminhadas para pontos de extremidade localizados em locais diferentes do gateway PSTN a fim de impedir bypass das chamadas tarifadas PSTN.

  - Quando um usuário está localizado em um site de rede desconhecido para a implantação do Lync Server, o roteamento de chamadas de saída será baseado na política de voz atribuída ao usuário a gateways PSTN não ligados às restrições de roteamento baseadas em localização. As chamadas PSTN de entrada não serão encaminhadas para os pontos de extremidade localizados em locais de rede desconhecidos a fim de impedir bypass de chamadas tarifadas PSTN.

<div>

## <a name="see-also"></a>Confira também


[Orientação para Roteamento Baseado em Local no Lync Server 2013](lync-server-2013-guidance-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

