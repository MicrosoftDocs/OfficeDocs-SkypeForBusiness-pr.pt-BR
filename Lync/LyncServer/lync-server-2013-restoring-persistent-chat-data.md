---
title: 'Lync Server 2013: restaurando dados de chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring Persistent Chat data
ms:assetid: c251a7fa-50da-434b-b39a-17f5978ce736
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945649(v=OCS.15)
ms:contentKeyID: 51541516
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3c905ee22ed237e908fc72e551f973b6f20fa8f2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144657"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="restoring-persistent-chat-data-in-lync-server-2013"></a>Restaurando dados de chat persistente no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-18_

O conteúdo de sala de chat persistente é armazenado no banco de dados de chat persistente (MGC. MDF). Estes são dados críticos para os negócios que devem ser copiados regularmente. Além do conteúdo da sala de chat, as entidades de segurança (como usuários e grupos) e as funções e o acesso de salas de chat e o conteúdo da sala de chat, também são armazenados no banco de dados de chat persistente.

O modo de restauração dos dados de chat persistente depende do método usado para fazer o backup.

  - Se você usou procedimentos de backup do SQL Server, deverá usar os procedimentos de restauração do SQL Server.

  - Se você usou o cmdlet **Export-CsPersistentChatData** para fazer o backup de dados de chat persistente, deverá usar o cmdlet **Import-CsPersistentChatData** para restaurar os dados.

</div>

<span> </span>

</div>

</div>

</div>

