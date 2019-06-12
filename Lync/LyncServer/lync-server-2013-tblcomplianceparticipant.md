---
title: 'Lync Server 2013: tblComplianceParticipant'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblComplianceParticipant
ms:assetid: 5d7e0dea-74f7-46d1-badf-b94abc8f066d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558655(v=OCS.15)
ms:contentKeyID: 48184262
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e98b257552f728d0976df6331673f1f55d0dbdeb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844781"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblcomplianceparticipant-in-lync-server-2013"></a><span data-ttu-id="7abc3-102">tblComplianceParticipant no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7abc3-102">tblComplianceParticipant in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7abc3-103">_**Tópico da última modificação:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="7abc3-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="7abc3-104">tblComplianceParticipant contém os participantes atuais por canal e por servidor.</span><span class="sxs-lookup"><span data-stu-id="7abc3-104">tblComplianceParticipant contains the current participants per channel and per server.</span></span>

### <a name="columns"></a><span data-ttu-id="7abc3-105">Colunas</span><span class="sxs-lookup"><span data-stu-id="7abc3-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7abc3-106">Coluna</span><span class="sxs-lookup"><span data-stu-id="7abc3-106">Column</span></span></th>
<th><span data-ttu-id="7abc3-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="7abc3-107">Type</span></span></th>
<th><span data-ttu-id="7abc3-108">Descrição</span><span class="sxs-lookup"><span data-stu-id="7abc3-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7abc3-109">channelUri</span><span class="sxs-lookup"><span data-stu-id="7abc3-109">channelUri</span></span></p></td>
<td><p><span data-ttu-id="7abc3-110">nvarchar (255), NOT NULL</span><span class="sxs-lookup"><span data-stu-id="7abc3-110">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="7abc3-111">URI (Uniform Resource Identifier) do canal.</span><span class="sxs-lookup"><span data-stu-id="7abc3-111">Channel Uniform Resource Identifier (URI).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7abc3-112">ID</span><span class="sxs-lookup"><span data-stu-id="7abc3-112">userId</span></span></p></td>
<td><p><span data-ttu-id="7abc3-113">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="7abc3-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="7abc3-114">ID da entidade de segurança do participante (correspondente à tabela tblPrincipal. retoid).</span><span class="sxs-lookup"><span data-stu-id="7abc3-114">Principal ID of the participant (corresponding to tblPrincipal.prinID table).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7abc3-115">joinedAt</span><span class="sxs-lookup"><span data-stu-id="7abc3-115">joinedAt</span></span></p></td>
<td><p><span data-ttu-id="7abc3-116">bigint, e não nulo</span><span class="sxs-lookup"><span data-stu-id="7abc3-116">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="7abc3-117">Carimbo de data/hora do evento de associação.</span><span class="sxs-lookup"><span data-stu-id="7abc3-117">Time stamp of the joining event.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7abc3-118">partedAt</span><span class="sxs-lookup"><span data-stu-id="7abc3-118">partedAt</span></span></p></td>
<td><p><span data-ttu-id="7abc3-119">bigint</span><span class="sxs-lookup"><span data-stu-id="7abc3-119">bigint</span></span></p></td>
<td><p><span data-ttu-id="7abc3-120">NULL se o participante ainda estiver associado.</span><span class="sxs-lookup"><span data-stu-id="7abc3-120">Null if participant is still joined.</span></span> <span data-ttu-id="7abc3-121">O carimbo de data/hora do evento de persaiar de canal, se não for nulo.</span><span class="sxs-lookup"><span data-stu-id="7abc3-121">The time stamp of the channel leaving event if not null.</span></span></p>
<p><span data-ttu-id="7abc3-122">Essas entradas são eventualmente removidas quando todos os tradutores processam o evento.</span><span class="sxs-lookup"><span data-stu-id="7abc3-122">These entries are eventually removed when all translators process the event.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7abc3-123">userUri</span><span class="sxs-lookup"><span data-stu-id="7abc3-123">userUri</span></span></p></td>
<td><p><span data-ttu-id="7abc3-124">nvarchar (255), NOT NULL</span><span class="sxs-lookup"><span data-stu-id="7abc3-124">nvarchar(255), not null</span></span></p></td>
<td><p><span data-ttu-id="7abc3-125">URI de usuário.</span><span class="sxs-lookup"><span data-stu-id="7abc3-125">User URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7abc3-126">serverID</span><span class="sxs-lookup"><span data-stu-id="7abc3-126">serverID</span></span></p></td>
<td><p><span data-ttu-id="7abc3-127">int</span><span class="sxs-lookup"><span data-stu-id="7abc3-127">int</span></span></p></td>
<td><p><span data-ttu-id="7abc3-128">Identidade do servidor (como na tabela tblServerIdentity. ServerId).</span><span class="sxs-lookup"><span data-stu-id="7abc3-128">Server identity (as in tblServerIdentity.serverID table).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7abc3-129">Identificação</span><span class="sxs-lookup"><span data-stu-id="7abc3-129">sessionId</span></span></p></td>
<td><p><span data-ttu-id="7abc3-130">bigint</span><span class="sxs-lookup"><span data-stu-id="7abc3-130">bigint</span></span></p></td>
<td><p><span data-ttu-id="7abc3-131">Sessão do servidor.</span><span class="sxs-lookup"><span data-stu-id="7abc3-131">Server session.</span></span> <span data-ttu-id="7abc3-132">Esse é um número aleatório gerado cada vez que um serviço de chat é iniciado.</span><span class="sxs-lookup"><span data-stu-id="7abc3-132">This is a random number generated each time a Chat service starts.</span></span> <span data-ttu-id="7abc3-133">Ele é usado para diferenciar sessões para fins de identificação de participantes órfãos.</span><span class="sxs-lookup"><span data-stu-id="7abc3-133">It is used to differentiate sessions for the purpose of identifying orphaned participants.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="7abc3-134">Chave</span><span class="sxs-lookup"><span data-stu-id="7abc3-134">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7abc3-135">Coluna</span><span class="sxs-lookup"><span data-stu-id="7abc3-135">Column</span></span></th>
<th><span data-ttu-id="7abc3-136">Descrição</span><span class="sxs-lookup"><span data-stu-id="7abc3-136">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7abc3-137">&lt;channelUri, userId, joinedAt&gt;</span><span class="sxs-lookup"><span data-stu-id="7abc3-137">&lt;channelUri, userId, joinedAt&gt;</span></span></p></td>
<td><p><span data-ttu-id="7abc3-138">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="7abc3-138">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

