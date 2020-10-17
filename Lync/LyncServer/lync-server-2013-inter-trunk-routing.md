---
title: 'Lync Server 2013: roteamento entre troncos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Inter-trunk routing
ms:assetid: f687a548-1f2e-48ed-9745-a13dc1f3698f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721940(v=OCS.15)
ms:contentKeyID: 49733877
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: de302ec9bfbf81ea1d5c43ec568f2a0c0f6c19bf
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48498488"
---
# <a name="inter-trunk-routing-in-lync-server-2013"></a>Roteamento entre troncos no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-08_

O Lync Server 2013 fornece gerenciamento de sessão básica através do suporte de roteamento entre troncos. Esse novo recurso permite que o Lync Server forneça funcionalidades de controle de chamada para sistemas de telefonia downstream. O roteamento entre troncos pode interconectar um IP-PBX a um gateway de rede de telefone pública comutada (PSTN) de forma que as chamadas de um telefone de central privada de comutação telefônica (PBX) possam ser encaminhadas para o PSTN, e as chamas PSTN de entrada possam ser encaminhadas para um telefone PBX. Da mesma forma, o Lync Server pode interconectar dois ou mais sistemas IP-PBX para que as chamadas possam ser colocadas e recebidas entre os telefones PBX dos diferentes sistemas IP-PBX.

A figura a seguir ilustra o Lync Server 2013 fornecendo interconectividade entre um gateway PSTN e um IP-PBX.

![O diagrama de gateway PSTN/IP-PBX de conexão do Lync Server](images/JJ721940.cc3858ca-2ee3-4d51-8a51-db078366b50b(OCS.15).jpg "O diagrama de gateway PSTN/IP-PBX de conexão do Lync Server")

A próxima figura ilustra o Lync Server 2013 conectando dois sistemas IP-PBX.

![Diagrama de sistemas IP-PAX de interconexão do Lync Server](images/JJ721940.6ba18ec9-df70-498a-9cf7-7fc41e5ec432(OCS.15).jpg "Diagrama de sistemas IP-PAX de interconexão do Lync Server")

</div>

<span> </span>

</div>

</div>

</div>

