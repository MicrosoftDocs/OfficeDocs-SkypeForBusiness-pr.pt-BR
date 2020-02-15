---
title: Remover um servidor front-end de um pool
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Remove a Front End Server from a pool
ms:assetid: 767225c9-7c0b-4d54-a407-d77134ba2abe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688095(v=OCS.15)
ms:contentKeyID: 49733694
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e3f8e2b2e395058d58d201177d2da08672a8d03f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035827"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-a-front-end-server-from-a-pool"></a>Remover um servidor front-end de um pool

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-04_

O servidor front-end do Microsoft Lync Server 2010 Enterprise Edition não pode existir como um computador autônomo. Ele deve ser definido como um pool de front-ends, mesmo se houver apenas um único computador no pool.

Este tópico orienta você durante o processo de remoção de um servidor front-end individual de um pool de front-ends existente. Se o servidor front-end for o último servidor do pool ou se você estiver removendo o pool completamente, consulte [Remove front end pool ou Standard Edition Server](remove-front-end-pool-or-standard-edition-server.md). Não é necessário remover os servidores front-end individuais antes de remover o pool de front-ends. Ao remover o pool, você remove cada servidor de front-end.

<div>

## <a name="to-remove-a-front-end-server-from-a-pool"></a>Para remover um servidor Front-End de um pool

1.  Abra o servidor front-end do Lync Server 2013, abra o construtor de topologias.

2.  Navegue até o nó do Lync Server 2010.

3.  Expanda **pools de front-ends Enterprise Edition**, expanda o pool de front-ends com o servidor front-end que você deseja remover, clique com o botão direito do mouse no servidor front-end que você deseja remover e clique em **excluir**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

