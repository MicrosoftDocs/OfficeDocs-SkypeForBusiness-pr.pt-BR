---
title: 'Lync Server 2013: excluindo uma sala de chat ou categoria'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting a chat room or category
ms:assetid: adccb869-0015-4eba-ac73-718bac7843b5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215881(v=OCS.15)
ms:contentKeyID: 48706009
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b0d849ce195b663b6f633a5b50aab32a547dd487
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42202497"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deleting-a-chat-room-or-category-in-lync-server-2013"></a>Excluindo uma sala de chat ou categoria no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-11-01_

As salas de chat persistentes podem ser excluídas. Se houver uma sala de chat que não esteja mais sendo usada, você poderá desabilitá-la. Para obter detalhes, consulte [desabilitar ou habilitar uma sala de chat no Lync Server 2013](lync-server-2013-disabling-or-enabling-a-chat-room.md).

Um administrador de chat persistente pode consultar salas de bate-papo desabilitadas e pode limpar e excluir periodicamente as salas de chat, usando o cmdlet do Windows PowerShell, **Remove-CsPersistentChatRoom**.

As categorias podem ser excluídas. No entanto, para excluir uma categoria, você deve primeiro excluir todas as salas de bate-papo ou mover as salas de chat para uma nova categoria, deixando uma categoria vazia para exclusão. O servidor de chat persistente não permite que você exclua uma categoria que contenha salas de chat. Para obter detalhes, consulte [movendo uma sala de chat de uma categoria para outra no Lync Server 2013](lync-server-2013-moving-a-chat-room-from-one-category-to-another.md).

Para obter detalhes sobre como excluir categorias vazias usando a interface de linha de comando do Windows PowerShell, consulte "gerenciamento de sala" em [Configurando servidor de chat persistente usando cmdlets do Windows PowerShell](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).

Para obter detalhes sobre salas e categorias de chat, consulte [Configure Rooms in Lync Server 2013](lync-server-2013-configure-rooms.md) e [Configure Categories in Lync Server 2013](lync-server-2013-configure-categories.md) na documentação de implantação.

</div>

<span> </span>

</div>

</div>

</div>

