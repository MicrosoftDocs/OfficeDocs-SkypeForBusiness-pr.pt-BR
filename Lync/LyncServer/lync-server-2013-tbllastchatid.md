---
title: 'Lync Server 2013: tblLastChatId'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblLastChatId
ms:assetid: 17a4ffbe-cca9-4ec5-ae46-38a15274889a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558616(v=OCS.15)
ms:contentKeyID: 48183513
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1def19b45f09a81c1bd5a1504151bfb919f6c4f7
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42208087"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tbllastchatid-in-lync-server-2013"></a><span data-ttu-id="e3e39-102">tblLastChatId no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e3e39-102">tblLastChatId in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e3e39-103">_**Última modificação do tópico:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="e3e39-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="e3e39-104">tblLastChatId inclui a última ID de chat que foi gerada (e usada na tabela tblChat) para cada usuário.</span><span class="sxs-lookup"><span data-stu-id="e3e39-104">tblLastChatId contains the last chat ID that was generated (and used in the tblChat table) for each user.</span></span>

### <a name="columns"></a><span data-ttu-id="e3e39-105">Colunas</span><span class="sxs-lookup"><span data-stu-id="e3e39-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e3e39-106">Coluna</span><span class="sxs-lookup"><span data-stu-id="e3e39-106">Column</span></span></th>
<th><span data-ttu-id="e3e39-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="e3e39-107">Type</span></span></th>
<th><span data-ttu-id="e3e39-108">Descrição</span><span class="sxs-lookup"><span data-stu-id="e3e39-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e3e39-109">nodeID</span><span class="sxs-lookup"><span data-stu-id="e3e39-109">nodeID</span></span></p></td>
<td><p><span data-ttu-id="e3e39-110">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="e3e39-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="e3e39-111">ID de nó (apenas para tipo de sala de chat).</span><span class="sxs-lookup"><span data-stu-id="e3e39-111">Node ID (chat room-type only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3e39-112">lastChatID</span><span class="sxs-lookup"><span data-stu-id="e3e39-112">lastChatID</span></span></p></td>
<td><p><span data-ttu-id="e3e39-113">bigint, não nulo</span><span class="sxs-lookup"><span data-stu-id="e3e39-113">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="e3e39-114">Último ID de chat usado.</span><span class="sxs-lookup"><span data-stu-id="e3e39-114">Last used chat ID.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="e3e39-115">Chaves</span><span class="sxs-lookup"><span data-stu-id="e3e39-115">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e3e39-116">Coluna</span><span class="sxs-lookup"><span data-stu-id="e3e39-116">Column</span></span></th>
<th><span data-ttu-id="e3e39-117">Descrição</span><span class="sxs-lookup"><span data-stu-id="e3e39-117">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e3e39-118">&lt;NodeId, lastChatID&gt;</span><span class="sxs-lookup"><span data-stu-id="e3e39-118">&lt;nodeID, lastChatID&gt;</span></span></p></td>
<td><p><span data-ttu-id="e3e39-119">Chave primária (apenas o nodeID é suficiente para o processamento).</span><span class="sxs-lookup"><span data-stu-id="e3e39-119">Primary key (just nodeID is sufficient for processing).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3e39-120">nodeID</span><span class="sxs-lookup"><span data-stu-id="e3e39-120">nodeID</span></span></p></td>
<td><p><span data-ttu-id="e3e39-121">Chave estrangeira com pesquisa na tabela tblNode.nodeID.</span><span class="sxs-lookup"><span data-stu-id="e3e39-121">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="e3e39-122">Confira também</span><span class="sxs-lookup"><span data-stu-id="e3e39-122">See Also</span></span>


[<span data-ttu-id="e3e39-123">tblChat no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e3e39-123">tblChat in Lync Server 2013</span></span>](lync-server-2013-tblchat.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

