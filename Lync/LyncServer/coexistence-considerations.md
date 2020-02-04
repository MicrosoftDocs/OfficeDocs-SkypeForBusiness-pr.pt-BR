---
title: Considerações de coexistência
ms.reviewer: ''
ms.author: kenwith
author: kenwith
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
ms.openlocfilehash: e53c57b90a85024ed5375129ce23c6ff0060edc4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727971"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="coexistence-considerations"></a>Considerações de coexistência

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-06_

Após a migração, apenas um servidor do Lync 2013, o pool do servidor de chat persistente existirá, e você poderá encerrar sua implantação herdada.

Antes de a migração ser concluída e antes de você ter desativado a implantação do servidor de chat de grupo atual completamente, você pode ter qualquer uma das seguintes implantações:

  - Lync Server 2013, pool de servidor de chat persistente, que deve ser hospedado em um pool do Lync Server 2013.

  - Lync Server 2010, pool de chat em grupo, que deve ser hospedado em um pool do Lync Server 2010.

  - Pool de chat do grupo do Office Communications Server 2007 R2, que deve ser hospedado em um pool do Office Communications Server 2007 R2.

Essas implantações podem existir lado a lado. No entanto, as categorias, salas e suplementos em uma implantação não interagem com as da implantação que o acompanha.

Usando a configuração manual, um cliente herdado (cliente de chat em grupo) pode se conectar a um pool por vez para o Office Communications Server 2007 R2, o Lync Server 2010, o chat em grupo ou o Lync Server 2013.

O Lync 2013 (cliente) só pode interagir com o servidor de chat do Lync 2013, o pool persistente do servidor de chat, não com pools de servidores de chat em grupo herdado. Para usar o chat persistente em um Lync 2013 (cliente), o usuário deve ser hospedado no Lync 2013 e habilitado pela política.

</div>

<span> </span>

</div>

</div>

</div>

