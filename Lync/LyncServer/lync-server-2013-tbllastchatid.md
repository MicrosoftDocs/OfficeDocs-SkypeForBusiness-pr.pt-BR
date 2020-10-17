---
title: 'Lync Server 2013: tblLastChatId'
description: 'Lync Server 2013: tblLastChatId.'
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
ms.openlocfilehash: 69e80a735e70c8a03441038f5e58eb93e0af1f82
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547597"
---
# <a name="tbllastchatid-in-lync-server-2013"></a><span data-ttu-id="cda4a-103">tblLastChatId no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cda4a-103">tblLastChatId in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cda4a-104">_**Última modificação do tópico:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="cda4a-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="cda4a-105">tblLastChatId inclui a última ID de chat que foi gerada (e usada na tabela tblChat) para cada usuário.</span><span class="sxs-lookup"><span data-stu-id="cda4a-105">tblLastChatId contains the last chat ID that was generated (and used in the tblChat table) for each user.</span></span>

### <a name="columns"></a><span data-ttu-id="cda4a-106">Colunas</span><span class="sxs-lookup"><span data-stu-id="cda4a-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cda4a-107">Coluna</span><span class="sxs-lookup"><span data-stu-id="cda4a-107">Column</span></span></th>
<th><span data-ttu-id="cda4a-108">Tipo</span><span class="sxs-lookup"><span data-stu-id="cda4a-108">Type</span></span></th>
<th><span data-ttu-id="cda4a-109">Descrição</span><span class="sxs-lookup"><span data-stu-id="cda4a-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cda4a-110">nodeID</span><span class="sxs-lookup"><span data-stu-id="cda4a-110">nodeID</span></span></p></td>
<td><p><span data-ttu-id="cda4a-111">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="cda4a-111">int, not null</span></span></p></td>
<td><p><span data-ttu-id="cda4a-112">ID de nó (apenas para tipo de sala de chat).</span><span class="sxs-lookup"><span data-stu-id="cda4a-112">Node ID (chat room-type only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cda4a-113">lastChatID</span><span class="sxs-lookup"><span data-stu-id="cda4a-113">lastChatID</span></span></p></td>
<td><p><span data-ttu-id="cda4a-114">bigint, não nulo</span><span class="sxs-lookup"><span data-stu-id="cda4a-114">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="cda4a-115">Último ID de chat usado.</span><span class="sxs-lookup"><span data-stu-id="cda4a-115">Last used chat ID.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="cda4a-116">Chaves</span><span class="sxs-lookup"><span data-stu-id="cda4a-116">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cda4a-117">Coluna</span><span class="sxs-lookup"><span data-stu-id="cda4a-117">Column</span></span></th>
<th><span data-ttu-id="cda4a-118">Descrição</span><span class="sxs-lookup"><span data-stu-id="cda4a-118">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cda4a-119">&lt;NodeId, lastChatID&gt;</span><span class="sxs-lookup"><span data-stu-id="cda4a-119">&lt;nodeID, lastChatID&gt;</span></span></p></td>
<td><p><span data-ttu-id="cda4a-120">Chave primária (apenas o nodeID é suficiente para o processamento).</span><span class="sxs-lookup"><span data-stu-id="cda4a-120">Primary key (just nodeID is sufficient for processing).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cda4a-121">nodeID</span><span class="sxs-lookup"><span data-stu-id="cda4a-121">nodeID</span></span></p></td>
<td><p><span data-ttu-id="cda4a-122">Chave estrangeira com pesquisa na tabela tblNode.nodeID.</span><span class="sxs-lookup"><span data-stu-id="cda4a-122">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="cda4a-123">Confira também</span><span class="sxs-lookup"><span data-stu-id="cda4a-123">See Also</span></span>


[<span data-ttu-id="cda4a-124">tblChat no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cda4a-124">tblChat in Lync Server 2013</span></span>](lync-server-2013-tblchat.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

