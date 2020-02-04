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
ms.openlocfilehash: 48516f307a084d30fde06a03548119e0ada34d6a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731500"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblcompliancedata-in-lync-server-2013"></a><span data-ttu-id="4628e-102">tblComplianceData no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4628e-102">tblComplianceData in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4628e-103">_**Tópico da última modificação:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="4628e-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="4628e-104">tblComplianceData contém os eventos de conformidade que ainda não foram processados pelo adaptador de conformidade.</span><span class="sxs-lookup"><span data-stu-id="4628e-104">tblComplianceData contains the compliance events that have not been processed by the compliance adapter yet.</span></span>

### <a name="columns"></a><span data-ttu-id="4628e-105">Colunas</span><span class="sxs-lookup"><span data-stu-id="4628e-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4628e-106">Coluna</span><span class="sxs-lookup"><span data-stu-id="4628e-106">Column</span></span></th>
<th><span data-ttu-id="4628e-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="4628e-107">Type</span></span></th>
<th><span data-ttu-id="4628e-108">Descrição</span><span class="sxs-lookup"><span data-stu-id="4628e-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4628e-109">cmplEventID</span><span class="sxs-lookup"><span data-stu-id="4628e-109">cmplEventID</span></span></p></td>
<td><p><span data-ttu-id="4628e-110">bigint, e não nulo</span><span class="sxs-lookup"><span data-stu-id="4628e-110">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="4628e-111">ID do evento.</span><span class="sxs-lookup"><span data-stu-id="4628e-111">Event ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4628e-112">entryDate</span><span class="sxs-lookup"><span data-stu-id="4628e-112">entryDate</span></span></p></td>
<td><p><span data-ttu-id="4628e-113">smalldatetime, não nulo</span><span class="sxs-lookup"><span data-stu-id="4628e-113">smalldatetime, not null</span></span></p></td>
<td><p><span data-ttu-id="4628e-114">Tempo de inserção (pode estar muito no futuro para cmplType = 9 porque a entrada é apenas um espaço reservado nesse caso).</span><span class="sxs-lookup"><span data-stu-id="4628e-114">Time of insertion (may be far in the future for cmplType=9 because the entry is just a placeholder in that case).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4628e-115">cmplType</span><span class="sxs-lookup"><span data-stu-id="4628e-115">cmplType</span></span></p></td>
<td><p><span data-ttu-id="4628e-116">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="4628e-116">int, not null</span></span></p></td>
<td><p><span data-ttu-id="4628e-117">Tipo de evento de conformidade:</span><span class="sxs-lookup"><span data-stu-id="4628e-117">Type of compliance event:</span></span></p>
<ul>
<li><p><span data-ttu-id="4628e-118">1: chat</span><span class="sxs-lookup"><span data-stu-id="4628e-118">1: Chat</span></span></p></li>
<li><p><span data-ttu-id="4628e-119">2: backchat</span><span class="sxs-lookup"><span data-stu-id="4628e-119">2: Backchat</span></span></p></li>
<li><p><span data-ttu-id="4628e-120">3: download de arquivo</span><span class="sxs-lookup"><span data-stu-id="4628e-120">3: File download</span></span></p></li>
<li><p><span data-ttu-id="4628e-121">4: carregamento de arquivo</span><span class="sxs-lookup"><span data-stu-id="4628e-121">4: File upload</span></span></p></li>
<li><p><span data-ttu-id="4628e-122">9: transferência de arquivo provisório</span><span class="sxs-lookup"><span data-stu-id="4628e-122">9: Provisional file transfer</span></span></p></li>
<li><p><span data-ttu-id="4628e-123">10: exclusão de chat (com replace)</span><span class="sxs-lookup"><span data-stu-id="4628e-123">10: Chat deletion (with replace)</span></span></p></li>
<li><p><span data-ttu-id="4628e-124">11: limpeza de chat</span><span class="sxs-lookup"><span data-stu-id="4628e-124">11: Chat purging</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4628e-125">cmplTime</span><span class="sxs-lookup"><span data-stu-id="4628e-125">cmplTime</span></span></p></td>
<td><p><span data-ttu-id="4628e-126">bigint, e não nulo</span><span class="sxs-lookup"><span data-stu-id="4628e-126">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="4628e-127">Carimbo de data/hora do evento.</span><span class="sxs-lookup"><span data-stu-id="4628e-127">Time stamp for the event.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4628e-128">cmplChannelUri</span><span class="sxs-lookup"><span data-stu-id="4628e-128">cmplChannelUri</span></span></p></td>
<td><p><span data-ttu-id="4628e-129">nvarchar (255), NOT NULL</span><span class="sxs-lookup"><span data-stu-id="4628e-129">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="4628e-130">URI (Uniform Resource Identifier) do canal.</span><span class="sxs-lookup"><span data-stu-id="4628e-130">Channel Uniform Resource Identifier (URI).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4628e-131">cmplChatID</span><span class="sxs-lookup"><span data-stu-id="4628e-131">cmplChatID</span></span></p></td>
<td><p><span data-ttu-id="4628e-132">bigint</span><span class="sxs-lookup"><span data-stu-id="4628e-132">bigint</span></span></p></td>
<td><p><span data-ttu-id="4628e-133">ID de chat (correspondente à tabela tblChat. chatid).</span><span class="sxs-lookup"><span data-stu-id="4628e-133">Chat ID (corresponding to tblChat.chatId table).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4628e-134">cmplUserID</span><span class="sxs-lookup"><span data-stu-id="4628e-134">cmplUserID</span></span></p></td>
<td><p><span data-ttu-id="4628e-135">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="4628e-135">int, not null</span></span></p></td>
<td><p><span data-ttu-id="4628e-136">ID da entidade de segurança do pôster (correspondente à tabela tblPrincipal. retoid).</span><span class="sxs-lookup"><span data-stu-id="4628e-136">Principal ID of the poster (corresponding to tblPrincipal.prinID table).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4628e-137">cmplUserUri</span><span class="sxs-lookup"><span data-stu-id="4628e-137">cmplUserUri</span></span></p></td>
<td><p><span data-ttu-id="4628e-138">nvarchar (255), NOT NULL</span><span class="sxs-lookup"><span data-stu-id="4628e-138">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="4628e-139">URI de usuário.</span><span class="sxs-lookup"><span data-stu-id="4628e-139">User URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4628e-140">cmplMessage</span><span class="sxs-lookup"><span data-stu-id="4628e-140">cmplMessage</span></span></p></td>
<td><p><span data-ttu-id="4628e-141">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="4628e-141">nvarchar (max)</span></span></p></td>
<td><p><span data-ttu-id="4628e-142">Mensagem (a codificação depende do cmplType).</span><span class="sxs-lookup"><span data-stu-id="4628e-142">Message (encoding depends on cmplType).</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="4628e-143">Chave</span><span class="sxs-lookup"><span data-stu-id="4628e-143">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4628e-144">Coluna</span><span class="sxs-lookup"><span data-stu-id="4628e-144">Column</span></span></th>
<th><span data-ttu-id="4628e-145">Descrição</span><span class="sxs-lookup"><span data-stu-id="4628e-145">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4628e-146">cmplEventID</span><span class="sxs-lookup"><span data-stu-id="4628e-146">cmplEventID</span></span></p></td>
<td><p><span data-ttu-id="4628e-147">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="4628e-147">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

