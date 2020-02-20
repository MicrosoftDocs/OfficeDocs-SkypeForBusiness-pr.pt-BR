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

# <a name="restoring-persistent-chat-data-in-lync-server-2013"></a><span data-ttu-id="402a3-102">Restaurando dados de chat persistente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="402a3-102">Restoring Persistent Chat data in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="402a3-103">_**Última modificação do tópico:** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="402a3-103">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="402a3-104">O conteúdo de sala de chat persistente é armazenado no banco de dados de chat persistente (MGC. MDF).</span><span class="sxs-lookup"><span data-stu-id="402a3-104">Persistent Chat room content is stored in the Persistent Chat database (mgc.mdf).</span></span> <span data-ttu-id="402a3-105">Estes são dados críticos para os negócios que devem ser copiados regularmente.</span><span class="sxs-lookup"><span data-stu-id="402a3-105">This is business-critical data that should be backed up regularly.</span></span> <span data-ttu-id="402a3-106">Além do conteúdo da sala de chat, as entidades de segurança (como usuários e grupos) e as funções e o acesso de salas de chat e o conteúdo da sala de chat, também são armazenados no banco de dados de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="402a3-106">In addition to the chat room content, principals (such as users and groups) and the roles and access that they have to chat rooms and chat room content, is also stored in the Persistent Chat database.</span></span>

<span data-ttu-id="402a3-107">O modo de restauração dos dados de chat persistente depende do método usado para fazer o backup.</span><span class="sxs-lookup"><span data-stu-id="402a3-107">How you restore your Persistent Chat data depends on the method that you used to back it up.</span></span>

  - <span data-ttu-id="402a3-108">Se você usou procedimentos de backup do SQL Server, deverá usar os procedimentos de restauração do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="402a3-108">If you used SQL Server backup procedures, you must use SQL Server restore procedures.</span></span>

  - <span data-ttu-id="402a3-109">Se você usou o cmdlet **Export-CsPersistentChatData** para fazer o backup de dados de chat persistente, deverá usar o cmdlet **Import-CsPersistentChatData** para restaurar os dados.</span><span class="sxs-lookup"><span data-stu-id="402a3-109">If you used the **Export-CsPersistentChatData** cmdlet to back up Persistent Chat data, then you must use the **Import-CsPersistentChatData** cmdlet to restore the data.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

