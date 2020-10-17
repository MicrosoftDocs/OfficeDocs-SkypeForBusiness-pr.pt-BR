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
ms.openlocfilehash: b184d863ff9d0404fbc05b90a88f7c203499262a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48523818"
---
# <a name="tbllastchatid-in-lync-server-2013"></a><span data-ttu-id="686e7-102">tblLastChatId no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="686e7-102">tblLastChatId in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="686e7-103">_**Última modificação do tópico:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="686e7-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="686e7-104">tblLastChatId inclui a última ID de chat que foi gerada (e usada na tabela tblChat) para cada usuário.</span><span class="sxs-lookup"><span data-stu-id="686e7-104">tblLastChatId contains the last chat ID that was generated (and used in the tblChat table) for each user.</span></span>

### <a name="columns"></a><span data-ttu-id="686e7-105">Colunas</span><span class="sxs-lookup"><span data-stu-id="686e7-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="686e7-106">Coluna</span><span class="sxs-lookup"><span data-stu-id="686e7-106">Column</span></span></th>
<th><span data-ttu-id="686e7-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="686e7-107">Type</span></span></th>
<th><span data-ttu-id="686e7-108">Descrição</span><span class="sxs-lookup"><span data-stu-id="686e7-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="686e7-109">nodeID</span><span class="sxs-lookup"><span data-stu-id="686e7-109">nodeID</span></span></p></td>
<td><p><span data-ttu-id="686e7-110">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="686e7-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="686e7-111">ID de nó (apenas para tipo de sala de chat).</span><span class="sxs-lookup"><span data-stu-id="686e7-111">Node ID (chat room-type only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="686e7-112">lastChatID</span><span class="sxs-lookup"><span data-stu-id="686e7-112">lastChatID</span></span></p></td>
<td><p><span data-ttu-id="686e7-113">bigint, não nulo</span><span class="sxs-lookup"><span data-stu-id="686e7-113">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="686e7-114">Último ID de chat usado.</span><span class="sxs-lookup"><span data-stu-id="686e7-114">Last used chat ID.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="686e7-115">Chaves</span><span class="sxs-lookup"><span data-stu-id="686e7-115">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="686e7-116">Coluna</span><span class="sxs-lookup"><span data-stu-id="686e7-116">Column</span></span></th>
<th><span data-ttu-id="686e7-117">Descrição</span><span class="sxs-lookup"><span data-stu-id="686e7-117">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="686e7-118">&lt;NodeId, lastChatID&gt;</span><span class="sxs-lookup"><span data-stu-id="686e7-118">&lt;nodeID, lastChatID&gt;</span></span></p></td>
<td><p><span data-ttu-id="686e7-119">Chave primária (apenas o nodeID é suficiente para o processamento).</span><span class="sxs-lookup"><span data-stu-id="686e7-119">Primary key (just nodeID is sufficient for processing).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="686e7-120">nodeID</span><span class="sxs-lookup"><span data-stu-id="686e7-120">nodeID</span></span></p></td>
<td><p><span data-ttu-id="686e7-121">Chave estrangeira com pesquisa na tabela tblNode.nodeID.</span><span class="sxs-lookup"><span data-stu-id="686e7-121">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="686e7-122">Confira também</span><span class="sxs-lookup"><span data-stu-id="686e7-122">See Also</span></span>


[<span data-ttu-id="686e7-123">tblChat no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="686e7-123">tblChat in Lync Server 2013</span></span>](lync-server-2013-tblchat.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

