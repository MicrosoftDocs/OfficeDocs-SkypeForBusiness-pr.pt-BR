---
title: 'Lync Server 2013: Configurando os computadores do Lync Server que serão monitorados'
description: 'Lync Server 2013: Configurando os computadores do Lync Server que serão monitorados.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the Lync Server computers that will be monitored
ms:assetid: 9f1b2b91-d5af-42ad-a27d-b0815f762ad8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205118(v=OCS.15)
ms:contentKeyID: 48184927
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 742bd8a67eb42472e598c45619514e9407cb29cf
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556827"
---
# <a name="configuring-the-lync-server-computers-that-will-be-monitored-in-lync-server-2013"></a>Configurando os computadores do Lync Server que serão monitorados no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-20_

Como o Lync Server 2013 não usa o processo de descoberta central usado no Microsoft Lync Server 2010, cada computador do Lync Server 2013 que você deseja monitorar deve ser capaz de relatar automaticamente sua existência ao servidor de gerenciamento. Para que isso seja possível, é necessário instalar os arquivos do agente Operations Manager em cada computador a ser monitorado. Após os arquivos do agente serem instalados, será necessário configurar o computador para agir como um proxy do System Center. Observe que esses procedimentos devem ser executados depois que você instalou e configurou o Lync Server nesses computadores.

</div>

<span> </span>

</div>

</div>

</div>

