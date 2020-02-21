---
title: Relações de registrador de backup do Lync Server 2013
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
ms.openlocfilehash: 9ac47dcda07d7c0ca368cc572ccfafe2c6c95b2f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42181364"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="backup-registrar-relationships-in-lync-server-2013"></a>Relações de registradores de backup no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-06-28_

Além de oferecer capacidade para recuperação de desastre, dois pools pareados servem como backup de Registrars. No Lync Server 2013, as relações de registrador de backup entre os pools front-end são sempre 1:1 e recíprocos. Isso significa que se P1 for backup de P2, P2 deve ser o backup de P1 e nenhum pode ser backup de outro pool Front End. Essa é uma alteração do Lync Server 2010, em que as relações de backup do pool de front-ends podem ser muitos para um.

Embora as relações de backup entre dois pools de front-ends devam ser 1:1 e symmetric, cada pool de front-ends ainda pode ser o registrador de backup para qualquer número de aparelhos de filial persistente, assim como no Lync Server 2010.

Observe que o Lync Server 2013 não estende o suporte à recuperação de desastres para usuários hospedados em um aparelho de filial persistente. Se um pool de front-ends que serve como backup para um aparelho de filial persistente falhar, os usuários conectados ao aparelho de filial persistente se enquadram no modo de resiliência, mesmo depois que os usuários hospedados no pool de front-ends têm failover para o pool de front-ends de backup.

</div>

<span> </span>

</div>

</div>

</div>

