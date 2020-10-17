---
title: 'Lync Server 2013: tblComplianceData'
description: 'Lync Server 2013: tblComplianceData.'
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
ms.openlocfilehash: 3c597d67054303de2753182b37419f68051d3af8
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568097"
---
# <a name="tblcompliancedata-in-lync-server-2013"></a><span data-ttu-id="fee5a-103">tblComplianceData no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fee5a-103">tblComplianceData in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fee5a-104">_**Última modificação do tópico:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="fee5a-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="fee5a-105">A tabela ComplianceData inclui eventos de conformidade que ainda não foram processados pelo adaptador de conformidade</span><span class="sxs-lookup"><span data-stu-id="fee5a-105">tblComplianceData contains the compliance events that have not been processed by the compliance adapter yet.</span></span>

### <a name="columns"></a><span data-ttu-id="fee5a-106">Colunas</span><span class="sxs-lookup"><span data-stu-id="fee5a-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fee5a-107">Coluna</span><span class="sxs-lookup"><span data-stu-id="fee5a-107">Column</span></span></th>
<th><span data-ttu-id="fee5a-108">Tipo</span><span class="sxs-lookup"><span data-stu-id="fee5a-108">Type</span></span></th>
<th><span data-ttu-id="fee5a-109">Descrição</span><span class="sxs-lookup"><span data-stu-id="fee5a-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fee5a-110">cmplEventID</span><span class="sxs-lookup"><span data-stu-id="fee5a-110">cmplEventID</span></span></p></td>
<td><p><span data-ttu-id="fee5a-111">bigint, não nulo</span><span class="sxs-lookup"><span data-stu-id="fee5a-111">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="fee5a-112">ID do evento.</span><span class="sxs-lookup"><span data-stu-id="fee5a-112">Event ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fee5a-113">entryDate</span><span class="sxs-lookup"><span data-stu-id="fee5a-113">entryDate</span></span></p></td>
<td><p><span data-ttu-id="fee5a-114">smalldatetime, não nulo</span><span class="sxs-lookup"><span data-stu-id="fee5a-114">smalldatetime, not null</span></span></p></td>
<td><p><span data-ttu-id="fee5a-115">Hora de inserção (pode está longe no futuro para cmplType=9, pois a entrada é apenas um espaço reservado neste caso).</span><span class="sxs-lookup"><span data-stu-id="fee5a-115">Time of insertion (may be far in the future for cmplType=9 because the entry is just a placeholder in that case).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fee5a-116">cmplType</span><span class="sxs-lookup"><span data-stu-id="fee5a-116">cmplType</span></span></p></td>
<td><p><span data-ttu-id="fee5a-117">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="fee5a-117">int, not null</span></span></p></td>
<td><p><span data-ttu-id="fee5a-118">Tipo de evento de conformidade:</span><span class="sxs-lookup"><span data-stu-id="fee5a-118">Type of compliance event:</span></span></p>
<ul>
<li><p><span data-ttu-id="fee5a-119">1: Chat</span><span class="sxs-lookup"><span data-stu-id="fee5a-119">1: Chat</span></span></p></li>
<li><p><span data-ttu-id="fee5a-120">2: Backchat</span><span class="sxs-lookup"><span data-stu-id="fee5a-120">2: Backchat</span></span></p></li>
<li><p><span data-ttu-id="fee5a-121">3: Download de arquivo</span><span class="sxs-lookup"><span data-stu-id="fee5a-121">3: File download</span></span></p></li>
<li><p><span data-ttu-id="fee5a-122">4: Carregamento de arquivo</span><span class="sxs-lookup"><span data-stu-id="fee5a-122">4: File upload</span></span></p></li>
<li><p><span data-ttu-id="fee5a-123">9: Transferência de arquivo provisional</span><span class="sxs-lookup"><span data-stu-id="fee5a-123">9: Provisional file transfer</span></span></p></li>
<li><p><span data-ttu-id="fee5a-124">10: Exclusão de chat (com substituição)</span><span class="sxs-lookup"><span data-stu-id="fee5a-124">10: Chat deletion (with replace)</span></span></p></li>
<li><p><span data-ttu-id="fee5a-125">11: Limpeza de chat</span><span class="sxs-lookup"><span data-stu-id="fee5a-125">11: Chat purging</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fee5a-126">cmplTime</span><span class="sxs-lookup"><span data-stu-id="fee5a-126">cmplTime</span></span></p></td>
<td><p><span data-ttu-id="fee5a-127">bigint, não nulo</span><span class="sxs-lookup"><span data-stu-id="fee5a-127">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="fee5a-128">Carimbo de data/hora para o evento.</span><span class="sxs-lookup"><span data-stu-id="fee5a-128">Time stamp for the event.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fee5a-129">cmplChannelUri</span><span class="sxs-lookup"><span data-stu-id="fee5a-129">cmplChannelUri</span></span></p></td>
<td><p><span data-ttu-id="fee5a-130">nvarchar (255), não nulo</span><span class="sxs-lookup"><span data-stu-id="fee5a-130">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="fee5a-131">Canal do Identificador de Recurso Uniforme (URI).</span><span class="sxs-lookup"><span data-stu-id="fee5a-131">Channel Uniform Resource Identifier (URI).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fee5a-132">cmplChatID</span><span class="sxs-lookup"><span data-stu-id="fee5a-132">cmplChatID</span></span></p></td>
<td><p><span data-ttu-id="fee5a-133">bigint</span><span class="sxs-lookup"><span data-stu-id="fee5a-133">bigint</span></span></p></td>
<td><p><span data-ttu-id="fee5a-134">ID do chat (correspondendo à tabela do Chat.chatId).</span><span class="sxs-lookup"><span data-stu-id="fee5a-134">Chat ID (corresponding to tblChat.chatId table).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fee5a-135">cmplUserID</span><span class="sxs-lookup"><span data-stu-id="fee5a-135">cmplUserID</span></span></p></td>
<td><p><span data-ttu-id="fee5a-136">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="fee5a-136">int, not null</span></span></p></td>
<td><p><span data-ttu-id="fee5a-137">ID principal do pôster (correspondendo à tabela do Principal.prinID).</span><span class="sxs-lookup"><span data-stu-id="fee5a-137">Principal ID of the poster (corresponding to tblPrincipal.prinID table).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fee5a-138">cmplUserUri</span><span class="sxs-lookup"><span data-stu-id="fee5a-138">cmplUserUri</span></span></p></td>
<td><p><span data-ttu-id="fee5a-139">nvarchar (255), não nulo</span><span class="sxs-lookup"><span data-stu-id="fee5a-139">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="fee5a-140">URI do usuário.</span><span class="sxs-lookup"><span data-stu-id="fee5a-140">User URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fee5a-141">cmplMessage</span><span class="sxs-lookup"><span data-stu-id="fee5a-141">cmplMessage</span></span></p></td>
<td><p><span data-ttu-id="fee5a-142">nvarchar (máx)</span><span class="sxs-lookup"><span data-stu-id="fee5a-142">nvarchar (max)</span></span></p></td>
<td><p><span data-ttu-id="fee5a-143">Mensagem (codificação depende de cmplType).</span><span class="sxs-lookup"><span data-stu-id="fee5a-143">Message (encoding depends on cmplType).</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="fee5a-144">Chave</span><span class="sxs-lookup"><span data-stu-id="fee5a-144">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fee5a-145">Coluna</span><span class="sxs-lookup"><span data-stu-id="fee5a-145">Column</span></span></th>
<th><span data-ttu-id="fee5a-146">Descrição</span><span class="sxs-lookup"><span data-stu-id="fee5a-146">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fee5a-147">cmplEventID</span><span class="sxs-lookup"><span data-stu-id="fee5a-147">cmplEventID</span></span></p></td>
<td><p><span data-ttu-id="fee5a-148">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="fee5a-148">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

