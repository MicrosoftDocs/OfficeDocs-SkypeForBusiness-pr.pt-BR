---
title: 'Lync Server 2013: tblLastChatId'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblLastChatId
ms:assetid: 17a4ffbe-cca9-4ec5-ae46-38a15274889a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558616(v=OCS.15)
ms:contentKeyID: 48183513
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bddc89952b544a71c469538cf11f65658e19e38d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844812"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tbllastchatid-in-lync-server-2013"></a><span data-ttu-id="634e5-102">tblLastChatId no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="634e5-102">tblLastChatId in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="634e5-103">_**Tópico da última modificação:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="634e5-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="634e5-104">tblLastChatId contém a última ID de chat que foi gerada (e usada na tabela tblChat) para cada usuário.</span><span class="sxs-lookup"><span data-stu-id="634e5-104">tblLastChatId contains the last chat ID that was generated (and used in the tblChat table) for each user.</span></span>

### <a name="columns"></a><span data-ttu-id="634e5-105">Colunas</span><span class="sxs-lookup"><span data-stu-id="634e5-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="634e5-106">Coluna</span><span class="sxs-lookup"><span data-stu-id="634e5-106">Column</span></span></th>
<th><span data-ttu-id="634e5-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="634e5-107">Type</span></span></th>
<th><span data-ttu-id="634e5-108">Descrição</span><span class="sxs-lookup"><span data-stu-id="634e5-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="634e5-109">NodeId</span><span class="sxs-lookup"><span data-stu-id="634e5-109">nodeID</span></span></p></td>
<td><p><span data-ttu-id="634e5-110">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="634e5-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="634e5-111">ID do nó (somente sala de chat-tipo).</span><span class="sxs-lookup"><span data-stu-id="634e5-111">Node ID (chat room-type only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="634e5-112">lastChatID</span><span class="sxs-lookup"><span data-stu-id="634e5-112">lastChatID</span></span></p></td>
<td><p><span data-ttu-id="634e5-113">bigint, e não nulo</span><span class="sxs-lookup"><span data-stu-id="634e5-113">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="634e5-114">ID do Chat usado pela última vez.</span><span class="sxs-lookup"><span data-stu-id="634e5-114">Last used chat ID.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="634e5-115">As</span><span class="sxs-lookup"><span data-stu-id="634e5-115">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="634e5-116">Coluna</span><span class="sxs-lookup"><span data-stu-id="634e5-116">Column</span></span></th>
<th><span data-ttu-id="634e5-117">Descrição</span><span class="sxs-lookup"><span data-stu-id="634e5-117">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="634e5-118">&lt;NodeId, lastChatID&gt;</span><span class="sxs-lookup"><span data-stu-id="634e5-118">&lt;nodeID, lastChatID&gt;</span></span></p></td>
<td><p><span data-ttu-id="634e5-119">Chave primária (apenas NodeId é suficiente para processamento).</span><span class="sxs-lookup"><span data-stu-id="634e5-119">Primary key (just nodeID is sufficient for processing).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="634e5-120">NodeId</span><span class="sxs-lookup"><span data-stu-id="634e5-120">nodeID</span></span></p></td>
<td><p><span data-ttu-id="634e5-121">Chave estrangeira com Lookup na tabela tblNode. NodeId.</span><span class="sxs-lookup"><span data-stu-id="634e5-121">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="634e5-122">Confira também</span><span class="sxs-lookup"><span data-stu-id="634e5-122">See Also</span></span>


[<span data-ttu-id="634e5-123">tblChat no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="634e5-123">tblChat in Lync Server 2013</span></span>](lync-server-2013-tblchat.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

