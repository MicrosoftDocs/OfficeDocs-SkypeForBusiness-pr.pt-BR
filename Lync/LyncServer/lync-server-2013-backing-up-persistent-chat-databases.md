---
title: 'Lync Server 2013: fazendo backup de bancos de dados de chat persistente'
description: 'Lync Server 2013: fazendo backup de bancos de dados de chat persistente.'
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
ms.openlocfilehash: 9885eaf0065f5b558922c056fb1f669a5b821460
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563287"
---
# <a name="backing-up-persistent-chat-databases-in-lync-server-2013"></a><span data-ttu-id="cb01c-103">Fazendo backup de bancos de dados de chat persistente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cb01c-103">Backing up Persistent Chat databases in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cb01c-104">_**Última modificação do tópico:** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="cb01c-104">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="cb01c-105">O conteúdo de sala de chat persistente é armazenado no banco de dados de chat persistente (MGC. MDF).</span><span class="sxs-lookup"><span data-stu-id="cb01c-105">Persistent Chat room content is stored in the Persistent Chat database (Mgc.mdf).</span></span> <span data-ttu-id="cb01c-106">Estes são dados críticos para os negócios que devem ser copiados regularmente.</span><span class="sxs-lookup"><span data-stu-id="cb01c-106">This is business-critical data that should be backed up regularly.</span></span> <span data-ttu-id="cb01c-107">Além do conteúdo da sala de chat, o banco de dados de chat persistente também armazena informações sobre as entidades (como usuários e grupos de usuários) e as funções e o acesso que eles têm para salas de chat e salas de chat.</span><span class="sxs-lookup"><span data-stu-id="cb01c-107">In addition to the chat room content, the Persistent Chat database also stores information about the principals (such as users and user groups), and the roles and access that they have to chat rooms and chat room.</span></span>

<span data-ttu-id="cb01c-108">Há duas maneiras de fazer backup de dados de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="cb01c-108">There are two ways of backing up Persistent Chat data.</span></span>

  - <span data-ttu-id="cb01c-109">Backup do SQL Server</span><span class="sxs-lookup"><span data-stu-id="cb01c-109">SQL Server Backup</span></span>

  - <span data-ttu-id="cb01c-110">O `Export-CsPersistentChatData` cmdlet, que exporta os dados de chat persistente como um arquivo</span><span class="sxs-lookup"><span data-stu-id="cb01c-110">The `Export-CsPersistentChatData` cmdlet, which exports Persistent Chat data as a file</span></span>

<span data-ttu-id="cb01c-111">Os dados criados usando o backup do SQL Server exigem um espaço de disco significativamente maior, possivelmente 20 vezes mais, do que aqueles criados por `Export-CsPersistentChatData` , mas o backup do SQL Server é mais provável de ser um procedimento que os administradores estão familiarizados com.</span><span class="sxs-lookup"><span data-stu-id="cb01c-111">Data that is created by using SQL Server backup requires significantly more disk space—possibly 20 times more—than that created by `Export-CsPersistentChatData`, but SQL Server backup is more likely to be a procedure that administrators are familiar with.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

