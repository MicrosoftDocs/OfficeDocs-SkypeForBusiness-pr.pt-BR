---
title: 'Lync Server 2013: movendo uma sala de chat de uma categoria para outra'
description: 'Lync Server 2013: movendo uma sala de chat de uma categoria para outra.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Moving a chat room from one category to another
ms:assetid: 7e93b8f6-5a18-4476-a432-3918e01bcfa6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215877(v=OCS.15)
ms:contentKeyID: 48706004
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4066732a90a94414b55d6a567fde0d496e4faf13
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48541989"
---
# <a name="moving-a-chat-room-from-one-category-to-another-in-lync-server-2013"></a>Mover uma sala de chat de uma categoria para outra no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-11-01_

Recomendamos que você não altere a categoria de uma sala de chat persistente após a criação da sala de chat. Contudo, se a o gerente da sala tiver privilégios de **Criador** em outra categoria, ele pode mover a sala de uma categoria a outra. A sala não é excluída e recriada. É uma mudança de associação no banco de dados.

Muda a categoria de uma sala de chat deve ser feito raramente. Uma categoria determina o membro permitido para a sala de chat, por isso, quando uma sala de chat muda de categoria, todas as listas de controle de acesso ao sistema (SACLs) não mais suportados pela nova categoria são purgadas. Por exemplo, se um usuário for membro da sala e não mais um **AllowedMember** na nova categoria, a filiação da sala será modificada e o usuário será removido da sala.

Para obter detalhes sobre como mover uma sala de chat usando a interface de linha de comando do Windows PowerShell, consulte "gerenciamento de sala" em [Configurando servidor de chat persistente usando cmdlets do Windows PowerShell](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).

Para obter detalhes sobre como configurar salas de chat, consulte [Configure Rooms in Lync Server 2013](lync-server-2013-configure-rooms.md) na documentação de implantação.

</div>

<span> </span>

</div>

</div>

</div>

