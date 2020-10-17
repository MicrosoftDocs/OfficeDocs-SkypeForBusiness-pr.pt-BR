---
title: 'Lync Server 2013: novo recurso de tronco'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New trunk feature
ms:assetid: 9b398bc8-2760-4218-b1a4-89b9694b1171
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688152(v=OCS.15)
ms:contentKeyID: 49733755
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0feda45fd6c035209783d173da3a85dec3876e50
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48505278"
---
# <a name="new-trunk-feature-in-lync-server-2013"></a>Novo recurso de tronco no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-21_

No Microsoft Lync Server 2013, vários troncos entre um servidor de mediação e um gateway podem ser definidos. O Microsoft Lync Server 2010 é permitido apenas para um único tronco entre um servidor de mediação e um gateway PSTN. Esse recurso oferece a flexibilidade para definir troncos adicionais. Um tronco é uma associação lógica entre um FQDN do servidor de mediação e uma porta de escuta e um FQDN de gateway PSTN e uma porta de escuta. Esse novo recurso permite uma definição de tronco fácil para resiliência (onde vários servidores de mediação podem ser usados para rotear chamadas para o mesmo gateway PSTN) para a interoperabilidade de PBX, onde vários troncos com políticas associadas diferentes podem ser usados entre o IP-PBX e um servidor de mediação e as configurações de tronco SIP, onde os servidores de mediação em diferentes sites têm troncos SIP para a portadora referenciada pelo mesmo FQDN da operadora.

<div>

## <a name="see-also"></a>Confira também


[Novos recursos do Enterprise Voice no Lync Server 2013](lync-server-2013-new-enterprise-voice-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

