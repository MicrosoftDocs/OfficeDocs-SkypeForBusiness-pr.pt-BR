---
title: Considerações de coexistência
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Coexistence considerations
ms:assetid: 9d1a3c0f-492a-4e37-bc2f-63509e328785
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205131(v=OCS.15)
ms:contentKeyID: 48184990
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cdad93eaf8debbc616099c1454d5e39438a63474
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48499668"
---
# <a name="coexistence-considerations"></a>Considerações de coexistência

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-06_

Após a migração, somente um pool do servidor de chat persistente do Lync Server 2013, existirá, e você poderá encerrar sua implantação herdada.

Antes que a migração seja concluída e antes de você tenha descomissionado completamente sua implantação do servidor de chat de grupo atual, você pode ter qualquer uma das seguintes implantações:

  - Lync Server 2013, pool de servidor de chat persistente, que deve ser hospedado em um pool do Lync Server 2013.

  - Lync Server 2010, pool de chat de grupo, que deve ser hospedado em um pool do Lync Server 2010.

  - Pool de chat do grupo do Office Communications Server 2007 R2, que deve estar hospedado em um pool do Office Communications Server 2007 R2.

Essas implantações podem coexistir. No entanto, as categorias, salas e complementos em uma implantação não interagem com aquelas na implantação acompanhante.

Usando a configuração manual, um cliente herdado (cliente de chat de grupo) pode se conectar a um pool por vez para o Office Communications Server 2007 R2, o Lync Server 2010, o chat de grupo ou o Lync Server 2013.

O Lync 2013 (cliente) pode interagir somente com o pool do servidor de chat persistente do Lync Server 2013, não com pools do servidor de chat de grupo herdado. Para usar o chat persistente em um Lync 2013 (cliente), o usuário deve estar hospedado no Lync 2013 e habilitado por política.

</div>

<span> </span>

</div>

</div>

</div>

