---
title: Remover um Servidor Front-End de um pool
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Remove a Front End Server from a pool
ms:assetid: 767225c9-7c0b-4d54-a407-d77134ba2abe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688095(v=OCS.15)
ms:contentKeyID: 49733694
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b798674173d14c2bd3f5638f6049c3a723786f91
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844157"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-a-front-end-server-from-a-pool"></a>Remover um Servidor Front-End de um pool

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-04_

O servidor front-end do Microsoft Lync Server 2010 Enterprise Edition não pode existir como um computador autônomo. Ele deve ser definido como um pool de front-end, mesmo se houver apenas um único computador no pool.

Este tópico orienta você pelo processo de remoção de um servidor front-end individual de um pool de front-end existente. Se o servidor front-end for o último servidor do pool ou se você estiver removendo o pool completamente, consulte [remover o pool de front-end ou o servidor Standard Edition](remove-front-end-pool-or-standard-edition-server.md). Não é necessário remover os servidores front-end individuais antes de remover o pool de front-ends. Ao remover o pool, você remove cada servidor front-end.

<div>

## <a name="to-remove-a-front-end-server-from-a-pool"></a>Para remover um servidor front-end de um pool

1.  Abra o servidor front-end do Lync Server 2013, abra o construtor de topologias.

2.  Navegue até o nó do Lync Server 2010.

3.  Expanda Pools de **front-end do Enterprise Edition**, expanda o pool de front-ends com o servidor front-end que você deseja remover, clique com o botão direito do mouse no servidor front-end que você deseja remover e clique em **excluir**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

