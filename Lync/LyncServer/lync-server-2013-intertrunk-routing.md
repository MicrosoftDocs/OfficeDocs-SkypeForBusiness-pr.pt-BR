---
title: 'Lync Server 2013: Roteamento entre troncos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Intertrunk routing
ms:assetid: d3a33b4a-8bf4-4a8c-a371-8ef79e740780
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205272(v=OCS.15)
ms:contentKeyID: 48185442
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3c1b66ea04ed72bab6d33114f52fa9fe96364b48
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34828955"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="intertrunk-routing-in-lync-server-2013"></a>Roteamento entre troncos no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-20_

O Lync Server 2013 pode interconectar um IP-PBX a um gateway PSTN (rede telefônica pública comutada) para que as chamadas de um telefone PBX possam ser roteadas para a PSTN, e chamadas PSTN de entrada possam ser roteadas para um telefone PBX (central privada de intercâmbio). Da mesma forma, o Lync Server 2013 pode interconectar dois ou mais sistemas de PBX IP para que as chamadas possam ser feitas e recebidas entre telefones PBX dos diferentes sistemas de IP-PBX.

Este recurso de roteamento de intertronco pode ser configurado usando o cmdlet do Shell de gerenciamento do Lync Server, **set-CsTrunkConfiguration**, com o novo parâmetro PstnUsages. Esse parâmetro especifica o conjunto de registros de uso PSTN a ser usado. Um tronco usa esse uso de PSTN para determinar uma rota e para direcionar todas as chamadas de entrada de acordo.

    Set-CsTrunkConfiguration -Identity <TrunkId> -PstnUsages @{add="<UsageString>"}

O diagrama a seguir ilustra o Lync Server 2013 fornecendo interconectividade entre um gateway PSTN e um IP-PBX.

**Roteamento entre troncos entre gateway e PBX IP**

O ![servidor do Lync conectando o diagrama PSTN gateway/IP-PBX] O (images/JJ721940.cc3858ca-2ee3-4d51-8a51-db078366b50b(OCS.15).jpg "servidor do Lync conectando o diagrama PSTN gateway/IP-PBX")

O diagrama a seguir ilustra o Lync Server 2013 interconectando dois sistemas de PBX IP.

**Roteamento entre troncos entre dois PBXs de IP**

![Diagrama de sistemas IP-pax de interconexão do Lync Server] (images/JJ721940.6ba18ec9-df70-498a-9cf7-7fc41e5ec432(OCS.15).jpg "Diagrama de sistemas IP-pax de interconexão do Lync Server")

</div>

<span> </span>

</div>

</div>

</div>

