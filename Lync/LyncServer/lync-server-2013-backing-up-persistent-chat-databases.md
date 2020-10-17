---
title: 'Lync Server 2013: fazendo backup de bancos de dados de chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backing up Persistent Chat databases
ms:assetid: b99ebdc0-a025-44d7-9d74-37a7365f330d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945646(v=OCS.15)
ms:contentKeyID: 51541507
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5eec65c22465ee5a2198e7f7147db2d0d014cc2b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48523138"
---
# <a name="backing-up-persistent-chat-databases-in-lync-server-2013"></a>Fazendo backup de bancos de dados de chat persistente no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-17_

O conteúdo de sala de chat persistente é armazenado no banco de dados de chat persistente (MGC. MDF). Estes são dados críticos para os negócios que devem ser copiados regularmente. Além do conteúdo da sala de chat, o banco de dados de chat persistente também armazena informações sobre as entidades (como usuários e grupos de usuários) e as funções e o acesso que eles têm para salas de chat e salas de chat.

Há duas maneiras de fazer backup de dados de chat persistente.

  - Backup do SQL Server

  - O `Export-CsPersistentChatData` cmdlet, que exporta os dados de chat persistente como um arquivo

Os dados criados usando o backup do SQL Server exigem um espaço de disco significativamente maior, possivelmente 20 vezes mais, do que aqueles criados por `Export-CsPersistentChatData` , mas o backup do SQL Server é mais provável de ser um procedimento que os administradores estão familiarizados com.

</div>

<span> </span>

</div>

</div>

</div>

