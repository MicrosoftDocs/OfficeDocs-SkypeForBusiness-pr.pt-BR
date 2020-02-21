---
title: 'Lync Server 2013: local do usuário'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User's location
ms:assetid: ce57941d-086b-448e-8ada-c7d636a2a1c9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994073(v=OCS.15)
ms:contentKeyID: 51803984
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d2e0454b5f8fc891aa878623575ee3850050ba28
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42212995"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="users-location-in-lync-server-2013"></a>Local do usuário no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-03-09_

O roteamento baseado em local aproveita as mesmas regiões de rede, sites e sub-redes, conforme definido no Lync Server usado pelo E9-1-1, CAC e bypass de mídia para aplicar restrições de roteamento de chamadas para evitar o bypass de chamada PSTN. O local de um usuário é determinado pela sub-rede IP dos pontos de extremidade do Lync do usuário estão conectados. Cada sub-rede IP é associada a um site de rede, que é agregado às regiões de rede definidas pelo administrador. O roteamento baseado em local é aplicado com base no site de rede do usuário.

Regras de roteamento com base no local são aplicadas por site de rede, significando que um determinado conjunto de regras será aplicado a todos os pontos de extremidade habilitados para roteamento baseado em local localizado dentro do mesmo local de rede. Os administradores podem aplicar o roteamento baseado em local a sites de rede que o exijam.

As políticas de roteamento de voz podem ser definidas por site de rede para definir um gateway PSTN específico que deve ser usado por todos os usuários localizados no site de rede para chamar números de telefone PSTN. Essas políticas de roteamento de voz terão precedência sobre o roteamento definido pela política de voz do usuário quando o usuário estiver localizado em um site de rede habilitado para o roteamento baseado em local e impedirá o roteamento de chamadas por meio de outros gateways PSTN habilitados para Roteamento baseado em local. Quando um usuário do Lync coloca uma chamada PSTN, a política de voz do usuário determina se o usuário pode ser autorizado a fazer a chamada. Se a política de voz do usuário permitir que o usuário faça a chamada, o roteamento baseado em local determinará o gateway PSTN de saída da chamada. O roteamento baseado em local faz essa determinação com base no local do usuário.

Um local de usuário pode ser categorizado das seguintes maneiras:

  - O usuário está localizado em um site de rede conhecido habilitado para roteamento baseado em local e seu número (discagem direta interna) termina em um gateway PSTN colocado no mesmo local de rede (ou seja, Office). O roteamento de chamadas de saída será através da política de roteamento de voz do local de rede no qual o usuário está localizado. As chamadas PSTN de entrada para o usuário são roteadas para pontos de extremidade localizados no mesmo local de rede que o gateway PSTN.

  - O usuário está localizado em um site de rede conhecido que é diferente do local de rede onde o gateway PSTN está localizado. (ou seja, o usuário viajau para outro escritório corporativo). O roteamento de chamadas de saída usará a política de roteamento de voz do local de rede no qual o usuário está localizado. As chamadas PSTN de entrada para o usuário não serão encaminhadas para pontos de extremidade localizados em diferentes sites do que o gateway PSTN para impedir o bypass de chamada PSTN.

  - Quando um usuário está localizado em um site de rede que é desconhecido para a implantação do Lync Server, o roteamento de chamadas de saída será baseado na política de voz atribuída ao usuário para gateways PSTN não ligados a restrições de roteamento com base no local. As chamadas PSTN de entrada não serão encaminhadas para pontos de extremidade localizados em sites de rede desconhecidos para impedir o bypass de chamadas PSTN.

<div>

## <a name="see-also"></a>Confira também


[Orientação para roteamento baseado em local no Lync Server 2013](lync-server-2013-guidance-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

