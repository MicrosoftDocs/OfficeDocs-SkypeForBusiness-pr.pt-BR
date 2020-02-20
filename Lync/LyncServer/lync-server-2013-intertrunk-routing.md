---
title: 'Lync Server 2013: roteamento entre troncos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Intertrunk routing
ms:assetid: d3a33b4a-8bf4-4a8c-a371-8ef79e740780
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205272(v=OCS.15)
ms:contentKeyID: 48185442
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ce206c0f20dc00c6abc1304db8c1f933cbefdbca
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145259"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="intertrunk-routing-in-lync-server-2013"></a>Roteamento entre troncos no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-20_

O Lync Server 2013 pode interconectar um IP-PBX a um gateway PSTN (rede telefônica pública comutada) para que as chamadas de um telefone PBX possam ser roteadas para o PSTN, e as chamadas PSTN de entrada possam ser roteadas para um telefone de PBX (central privada de comutação telefônica). Da mesma forma, o Lync Server 2013 pode interconectar dois ou mais sistemas IP-PBX para que as chamadas possam ser colocadas e recebidas entre os telefones PBX dos diferentes sistemas IP-PBX.

Este recurso de roteamento entre troncos pode ser configurado usando o cmdlet do Shell de gerenciamento do Lync Server, **set-CsTrunkConfiguration**, com o novo parâmetro, PstnUsages. Este parâmetro especifica o conjunto de registros de uso PSTN para utilizar. Um tronco usa este uso PSTN para determinar uma rota e rotear todas as chamadas de entrada da mesma forma.

    Set-CsTrunkConfiguration -Identity <TrunkId> -PstnUsages @{add="<UsageString>"}

O diagrama a seguir ilustra o Lync Server 2013 fornecendo interconectividade entre um gateway PSTN e um IP-PBX.

**Roteamento entre troncos entre o gateway e IP PBX**

![O diagrama de gateway PSTN/IP-PBX de conexão do Lync Server](images/JJ721940.cc3858ca-2ee3-4d51-8a51-db078366b50b(OCS.15).jpg "O diagrama de gateway PSTN/IP-PBX de conexão do Lync Server")

O diagrama a seguir ilustra o Lync Server 2013 interconectando dois sistemas IP-PBX.

**Roteamento entre troncos entre dois IP PBXs**

![Diagrama de sistemas IP-PAX de interconexão do Lync Server](images/JJ721940.6ba18ec9-df70-498a-9cf7-7fc41e5ec432(OCS.15).jpg "Diagrama de sistemas IP-PAX de interconexão do Lync Server")

</div>

<span> </span>

</div>

</div>

</div>

