---
title: 'Lync Server 2013: tblComplianceData'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblComplianceData
ms:assetid: 05b28f9b-4aba-4b69-ba8d-2ceeb6cbfaac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558606(v=OCS.15)
ms:contentKeyID: 48183308
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dc2858ede3d1d3ccd1cc9af44c564fcac3424f35
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142157"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblcompliancedata-in-lync-server-2013"></a><span data-ttu-id="1531d-102">tblComplianceData no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1531d-102">tblComplianceData in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1531d-103">_**Última modificação do tópico:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="1531d-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="1531d-104">A tabela ComplianceData inclui eventos de conformidade que ainda não foram processados pelo adaptador de conformidade</span><span class="sxs-lookup"><span data-stu-id="1531d-104">tblComplianceData contains the compliance events that have not been processed by the compliance adapter yet.</span></span>

### <a name="columns"></a><span data-ttu-id="1531d-105">Colunas</span><span class="sxs-lookup"><span data-stu-id="1531d-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1531d-106">Coluna</span><span class="sxs-lookup"><span data-stu-id="1531d-106">Column</span></span></th>
<th><span data-ttu-id="1531d-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="1531d-107">Type</span></span></th>
<th><span data-ttu-id="1531d-108">Descrição</span><span class="sxs-lookup"><span data-stu-id="1531d-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1531d-109">cmplEventID</span><span class="sxs-lookup"><span data-stu-id="1531d-109">cmplEventID</span></span></p></td>
<td><p><span data-ttu-id="1531d-110">bigint, não nulo</span><span class="sxs-lookup"><span data-stu-id="1531d-110">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="1531d-111">ID do evento.</span><span class="sxs-lookup"><span data-stu-id="1531d-111">Event ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1531d-112">entryDate</span><span class="sxs-lookup"><span data-stu-id="1531d-112">entryDate</span></span></p></td>
<td><p><span data-ttu-id="1531d-113">smalldatetime, não nulo</span><span class="sxs-lookup"><span data-stu-id="1531d-113">smalldatetime, not null</span></span></p></td>
<td><p><span data-ttu-id="1531d-114">Hora de inserção (pode está longe no futuro para cmplType=9, pois a entrada é apenas um espaço reservado neste caso).</span><span class="sxs-lookup"><span data-stu-id="1531d-114">Time of insertion (may be far in the future for cmplType=9 because the entry is just a placeholder in that case).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1531d-115">cmplType</span><span class="sxs-lookup"><span data-stu-id="1531d-115">cmplType</span></span></p></td>
<td><p><span data-ttu-id="1531d-116">int, not null</span><span class="sxs-lookup"><span data-stu-id="1531d-116">int, not null</span></span></p></td>
<td><p><span data-ttu-id="1531d-117">Tipo de evento de conformidade:</span><span class="sxs-lookup"><span data-stu-id="1531d-117">Type of compliance event:</span></span></p>
<ul>
<li><p><span data-ttu-id="1531d-118">1: Chat</span><span class="sxs-lookup"><span data-stu-id="1531d-118">1: Chat</span></span></p></li>
<li><p><span data-ttu-id="1531d-119">2: Backchat</span><span class="sxs-lookup"><span data-stu-id="1531d-119">2: Backchat</span></span></p></li>
<li><p><span data-ttu-id="1531d-120">3: Download de arquivo</span><span class="sxs-lookup"><span data-stu-id="1531d-120">3: File download</span></span></p></li>
<li><p><span data-ttu-id="1531d-121">4: Carregamento de arquivo</span><span class="sxs-lookup"><span data-stu-id="1531d-121">4: File upload</span></span></p></li>
<li><p><span data-ttu-id="1531d-122">9: Transferência de arquivo provisional</span><span class="sxs-lookup"><span data-stu-id="1531d-122">9: Provisional file transfer</span></span></p></li>
<li><p><span data-ttu-id="1531d-123">10: Exclusão de chat (com substituição)</span><span class="sxs-lookup"><span data-stu-id="1531d-123">10: Chat deletion (with replace)</span></span></p></li>
<li><p><span data-ttu-id="1531d-124">11: Limpeza de chat</span><span class="sxs-lookup"><span data-stu-id="1531d-124">11: Chat purging</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1531d-125">cmplTime</span><span class="sxs-lookup"><span data-stu-id="1531d-125">cmplTime</span></span></p></td>
<td><p><span data-ttu-id="1531d-126">bigint, não nulo</span><span class="sxs-lookup"><span data-stu-id="1531d-126">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="1531d-127">Carimbo de data/hora para o evento.</span><span class="sxs-lookup"><span data-stu-id="1531d-127">Time stamp for the event.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1531d-128">cmplChannelUri</span><span class="sxs-lookup"><span data-stu-id="1531d-128">cmplChannelUri</span></span></p></td>
<td><p><span data-ttu-id="1531d-129">nvarchar (255), não nulo</span><span class="sxs-lookup"><span data-stu-id="1531d-129">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="1531d-130">Canal do Identificador de Recurso Uniforme (URI).</span><span class="sxs-lookup"><span data-stu-id="1531d-130">Channel Uniform Resource Identifier (URI).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1531d-131">cmplChatID</span><span class="sxs-lookup"><span data-stu-id="1531d-131">cmplChatID</span></span></p></td>
<td><p><span data-ttu-id="1531d-132">bigint</span><span class="sxs-lookup"><span data-stu-id="1531d-132">bigint</span></span></p></td>
<td><p><span data-ttu-id="1531d-133">ID do chat (correspondendo à tabela do Chat.chatId).</span><span class="sxs-lookup"><span data-stu-id="1531d-133">Chat ID (corresponding to tblChat.chatId table).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1531d-134">cmplUserID</span><span class="sxs-lookup"><span data-stu-id="1531d-134">cmplUserID</span></span></p></td>
<td><p><span data-ttu-id="1531d-135">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="1531d-135">int, not null</span></span></p></td>
<td><p><span data-ttu-id="1531d-136">ID principal do pôster (correspondendo à tabela do Principal.prinID).</span><span class="sxs-lookup"><span data-stu-id="1531d-136">Principal ID of the poster (corresponding to tblPrincipal.prinID table).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1531d-137">cmplUserUri</span><span class="sxs-lookup"><span data-stu-id="1531d-137">cmplUserUri</span></span></p></td>
<td><p><span data-ttu-id="1531d-138">nvarchar (255), não nulo</span><span class="sxs-lookup"><span data-stu-id="1531d-138">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="1531d-139">URI do usuário.</span><span class="sxs-lookup"><span data-stu-id="1531d-139">User URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1531d-140">cmplMessage</span><span class="sxs-lookup"><span data-stu-id="1531d-140">cmplMessage</span></span></p></td>
<td><p><span data-ttu-id="1531d-141">nvarchar (máx)</span><span class="sxs-lookup"><span data-stu-id="1531d-141">nvarchar (max)</span></span></p></td>
<td><p><span data-ttu-id="1531d-142">Mensagem (codificação depende de cmplType).</span><span class="sxs-lookup"><span data-stu-id="1531d-142">Message (encoding depends on cmplType).</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="1531d-143">Chave</span><span class="sxs-lookup"><span data-stu-id="1531d-143">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1531d-144">Coluna</span><span class="sxs-lookup"><span data-stu-id="1531d-144">Column</span></span></th>
<th><span data-ttu-id="1531d-145">Descrição</span><span class="sxs-lookup"><span data-stu-id="1531d-145">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1531d-146">cmplEventID</span><span class="sxs-lookup"><span data-stu-id="1531d-146">cmplEventID</span></span></p></td>
<td><p><span data-ttu-id="1531d-147">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="1531d-147">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

