---
title: 'Lync Server 2013: Relacionamentos de Registradores de backup'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backup Registrar relationships
ms:assetid: 7e078271-84b9-4666-989c-c4507a0cdf4a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205033(v=OCS.15)
ms:contentKeyID: 48184631
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 44111dbdec945e525b1ef54d910e1cf7f3b5a5d0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730341"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backup-registrar-relationships-in-lync-server-2013"></a>Relacionamentos de Registradores de backup no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-06-28_

Além de permitir a recuperação de desastre, dois pools emparelhados atuam como os Registradores de backup entre si. No Lync Server 2013, as relações de registrador de backup entre os pools front-end são sempre 1:1 e recíprocos. Isso significa que, se P1 for o backup para P2, então P2 deve ser o backup do P1, e nenhum deles pode ser o backup de qualquer outro pool de front-end. Isso é uma alteração do Lync Server 2010, no qual as relações de backup de pool de front-end podem ser muitos para um.

Embora as relações de backup entre dois pools de front-end sejam 1:1 e simétrica, cada pool de front-ends ainda pode ser o registrador de backup para qualquer número de aparelhos de ramificação sobreviventes, assim como no Lync Server 2010.

Observe que o Lync Server 2013 não estende o suporte à recuperação de desastres para usuários hospedados em um aparelho de ramificação sobreviventes. Se um pool de front-end que funciona como o backup para um aparelho de ramificação sobreviventes parar, os usuários que entrarem no aparelho de ramificação sobreviventes ficarão em modo de resiliência, mesmo depois que os usuários hospedados no pool de front-ends tiverem failover para o pool de front-ends de backup.

</div>

<span> </span>

</div>

</div>

</div>

