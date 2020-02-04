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
ms.openlocfilehash: a0fc42a3151b5863885fdb3853ea529503e18a6b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731541"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tbllastchatid-in-lync-server-2013"></a><span data-ttu-id="37a79-102">tblLastChatId no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="37a79-102">tblLastChatId in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="37a79-103">_**Tópico da última modificação:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="37a79-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="37a79-104">tblLastChatId contém a última ID de chat que foi gerada (e usada na tabela tblChat) para cada usuário.</span><span class="sxs-lookup"><span data-stu-id="37a79-104">tblLastChatId contains the last chat ID that was generated (and used in the tblChat table) for each user.</span></span>

### <a name="columns"></a><span data-ttu-id="37a79-105">Colunas</span><span class="sxs-lookup"><span data-stu-id="37a79-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="37a79-106">Coluna</span><span class="sxs-lookup"><span data-stu-id="37a79-106">Column</span></span></th>
<th><span data-ttu-id="37a79-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="37a79-107">Type</span></span></th>
<th><span data-ttu-id="37a79-108">Descrição</span><span class="sxs-lookup"><span data-stu-id="37a79-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="37a79-109">NodeId</span><span class="sxs-lookup"><span data-stu-id="37a79-109">nodeID</span></span></p></td>
<td><p><span data-ttu-id="37a79-110">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="37a79-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="37a79-111">ID do nó (somente sala de chat-tipo).</span><span class="sxs-lookup"><span data-stu-id="37a79-111">Node ID (chat room-type only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37a79-112">lastChatID</span><span class="sxs-lookup"><span data-stu-id="37a79-112">lastChatID</span></span></p></td>
<td><p><span data-ttu-id="37a79-113">bigint, e não nulo</span><span class="sxs-lookup"><span data-stu-id="37a79-113">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="37a79-114">ID do Chat usado pela última vez.</span><span class="sxs-lookup"><span data-stu-id="37a79-114">Last used chat ID.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="37a79-115">As</span><span class="sxs-lookup"><span data-stu-id="37a79-115">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="37a79-116">Coluna</span><span class="sxs-lookup"><span data-stu-id="37a79-116">Column</span></span></th>
<th><span data-ttu-id="37a79-117">Descrição</span><span class="sxs-lookup"><span data-stu-id="37a79-117">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="37a79-118">&lt;NodeId, lastChatID&gt;</span><span class="sxs-lookup"><span data-stu-id="37a79-118">&lt;nodeID, lastChatID&gt;</span></span></p></td>
<td><p><span data-ttu-id="37a79-119">Chave primária (apenas NodeId é suficiente para processamento).</span><span class="sxs-lookup"><span data-stu-id="37a79-119">Primary key (just nodeID is sufficient for processing).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37a79-120">NodeId</span><span class="sxs-lookup"><span data-stu-id="37a79-120">nodeID</span></span></p></td>
<td><p><span data-ttu-id="37a79-121">Chave estrangeira com Lookup na tabela tblNode. NodeId.</span><span class="sxs-lookup"><span data-stu-id="37a79-121">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="37a79-122">Confira também</span><span class="sxs-lookup"><span data-stu-id="37a79-122">See Also</span></span>


[<span data-ttu-id="37a79-123">tblChat no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="37a79-123">tblChat in Lync Server 2013</span></span>](lync-server-2013-tblchat.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

