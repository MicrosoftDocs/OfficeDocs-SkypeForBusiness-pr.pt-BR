---
title: 'Lync Server 2013: fazendo backup de bancos de dados de chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Backing up Persistent Chat databases
ms:assetid: b99ebdc0-a025-44d7-9d74-37a7365f330d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945646(v=OCS.15)
ms:contentKeyID: 51541507
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c8ffb99effcf0a42bbddefd7151aa40a8d691d9c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836891"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backing-up-persistent-chat-databases-in-lync-server-2013"></a>Fazer backup de bancos de dados de chat persistentes no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-17_

Conteúdo da sala de chat persistente é armazenado no banco de dados de chat persistente (MGC. MDF). Esses dados são essenciais para os negócios, cujo backup deve ser feito regularmente. Além do conteúdo da sala de chat, o banco de dados de chat persistente também armazena informações sobre as entidades de segurança (como usuários e grupos de usuários) e as funções e o acesso de chat a salas de chat e salas de chat.

Há duas maneiras de fazer backup de dados de chat persistentes.

  - Backup do SQL Server

  - O `Export-CsPersistentChatData` cmdlet, que exporta dados de chat persistentes como um arquivo

Os dados que são criados usando o backup do SQL Server exigem um espaço de disco significativamente maior, possivelmente 20 vezes mais, `Export-CsPersistentChatData`do que o criado por, mas o backup do SQL Server tem mais probabilidade de ser um procedimento com o qual os administradores estão familiarizados.

</div>

<span> </span>

</div>

</div>

</div>

