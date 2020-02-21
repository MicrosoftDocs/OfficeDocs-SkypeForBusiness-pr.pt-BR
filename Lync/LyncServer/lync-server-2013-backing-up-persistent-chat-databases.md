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
ms.openlocfilehash: 218c011d2acc970028bfd0be529d89542d684758
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42206087"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="backing-up-persistent-chat-databases-in-lync-server-2013"></a>Fazendo backup de bancos de dados de chat persistente no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-17_

O conteúdo de sala de chat persistente é armazenado no banco de dados de chat persistente (MGC. MDF). Estes são dados críticos para os negócios que devem ser copiados regularmente. Além do conteúdo da sala de chat, o banco de dados de chat persistente também armazena informações sobre as entidades (como usuários e grupos de usuários) e as funções e o acesso que eles têm para salas de chat e salas de chat.

Há duas maneiras de fazer backup de dados de chat persistente.

  - Backup do SQL Server

  - O `Export-CsPersistentChatData` cmdlet, que exporta os dados de chat persistente como um arquivo

Os dados criados usando o backup do SQL Server exigem um espaço de disco significativamente maior, possivelmente 20 vezes mais, do que `Export-CsPersistentChatData`aqueles criados por, mas o backup do SQL Server é mais provável de ser um procedimento que os administradores estão familiarizados com.

</div>

<span> </span>

</div>

</div>

</div>

