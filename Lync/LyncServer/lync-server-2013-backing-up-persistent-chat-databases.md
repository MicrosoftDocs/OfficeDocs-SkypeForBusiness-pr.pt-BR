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
ms.openlocfilehash: f186552b9e0d5c78d0f40416cd92e41d5705e93a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740611"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backing-up-persistent-chat-databases-in-lync-server-2013"></a><span data-ttu-id="00186-102">Fazer backup de bancos de dados de chat persistentes no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="00186-102">Backing up Persistent Chat databases in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="00186-103">_**Tópico da última modificação:** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="00186-103">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="00186-104">Conteúdo da sala de chat persistente é armazenado no banco de dados de chat persistente (MGC. MDF).</span><span class="sxs-lookup"><span data-stu-id="00186-104">Persistent Chat room content is stored in the Persistent Chat database (Mgc.mdf).</span></span> <span data-ttu-id="00186-105">Esses dados são essenciais para os negócios, cujo backup deve ser feito regularmente.</span><span class="sxs-lookup"><span data-stu-id="00186-105">This is business-critical data that should be backed up regularly.</span></span> <span data-ttu-id="00186-106">Além do conteúdo da sala de chat, o banco de dados de chat persistente também armazena informações sobre as entidades de segurança (como usuários e grupos de usuários) e as funções e o acesso de chat a salas de chat e salas de chat.</span><span class="sxs-lookup"><span data-stu-id="00186-106">In addition to the chat room content, the Persistent Chat database also stores information about the principals (such as users and user groups), and the roles and access that they have to chat rooms and chat room.</span></span>

<span data-ttu-id="00186-107">Há duas maneiras de fazer backup de dados de chat persistentes.</span><span class="sxs-lookup"><span data-stu-id="00186-107">There are two ways of backing up Persistent Chat data.</span></span>

  - <span data-ttu-id="00186-108">Backup do SQL Server</span><span class="sxs-lookup"><span data-stu-id="00186-108">SQL Server Backup</span></span>

  - <span data-ttu-id="00186-109">O `Export-CsPersistentChatData` cmdlet, que exporta dados de chat persistentes como um arquivo</span><span class="sxs-lookup"><span data-stu-id="00186-109">The `Export-CsPersistentChatData` cmdlet, which exports Persistent Chat data as a file</span></span>

<span data-ttu-id="00186-110">Os dados que são criados usando o backup do SQL Server exigem um espaço de disco significativamente maior, possivelmente 20 vezes mais, `Export-CsPersistentChatData`do que o criado por, mas o backup do SQL Server tem mais probabilidade de ser um procedimento com o qual os administradores estão familiarizados.</span><span class="sxs-lookup"><span data-stu-id="00186-110">Data that is created by using SQL Server backup requires significantly more disk space—possibly 20 times more—than that created by `Export-CsPersistentChatData`, but SQL Server backup is more likely to be a procedure that administrators are familiar with.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

