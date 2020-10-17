---
title: 'Lync Server 2013: tblComplianceParticipant'
description: 'Lync Server 2013: tblComplianceParticipant.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblComplianceParticipant
ms:assetid: 5d7e0dea-74f7-46d1-badf-b94abc8f066d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558655(v=OCS.15)
ms:contentKeyID: 48184262
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c1385b0a635f003a72de93f10f72642314ad7ebd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569067"
---
# <a name="tblcomplianceparticipant-in-lync-server-2013"></a><span data-ttu-id="52179-103">tblComplianceParticipant no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="52179-103">tblComplianceParticipant in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="52179-104">_**Última modificação do tópico:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="52179-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="52179-105">tblComplianceParticipant contém os participantes atuais por canal e por servidor.</span><span class="sxs-lookup"><span data-stu-id="52179-105">tblComplianceParticipant contains the current participants per channel and per server.</span></span>

### <a name="columns"></a><span data-ttu-id="52179-106">Colunas</span><span class="sxs-lookup"><span data-stu-id="52179-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="52179-107">Coluna</span><span class="sxs-lookup"><span data-stu-id="52179-107">Column</span></span></th>
<th><span data-ttu-id="52179-108">Tipo</span><span class="sxs-lookup"><span data-stu-id="52179-108">Type</span></span></th>
<th><span data-ttu-id="52179-109">Descrição</span><span class="sxs-lookup"><span data-stu-id="52179-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="52179-110">channelUri</span><span class="sxs-lookup"><span data-stu-id="52179-110">channelUri</span></span></p></td>
<td><p><span data-ttu-id="52179-111">nvarchar (255), não nulo</span><span class="sxs-lookup"><span data-stu-id="52179-111">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="52179-112">Identificador de Recurso Uniforme do Canal (URI).</span><span class="sxs-lookup"><span data-stu-id="52179-112">Channel Uniform Resource Identifier (URI).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52179-113">userId</span><span class="sxs-lookup"><span data-stu-id="52179-113">userId</span></span></p></td>
<td><p><span data-ttu-id="52179-114">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="52179-114">int, not null</span></span></p></td>
<td><p><span data-ttu-id="52179-115">ID da entidade do participante (correspondente à tabela tblPrincipal.prinID).</span><span class="sxs-lookup"><span data-stu-id="52179-115">Principal ID of the participant (corresponding to tblPrincipal.prinID table).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52179-116">joinedAt</span><span class="sxs-lookup"><span data-stu-id="52179-116">joinedAt</span></span></p></td>
<td><p><span data-ttu-id="52179-117">bigint, não nulo</span><span class="sxs-lookup"><span data-stu-id="52179-117">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="52179-118">Carimbo de data e hora de ingresso no evento.</span><span class="sxs-lookup"><span data-stu-id="52179-118">Time stamp of the joining event.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52179-119">partedAt</span><span class="sxs-lookup"><span data-stu-id="52179-119">partedAt</span></span></p></td>
<td><p><span data-ttu-id="52179-120">bigint</span><span class="sxs-lookup"><span data-stu-id="52179-120">bigint</span></span></p></td>
<td><p><span data-ttu-id="52179-p101">Nulo se o participante ainda estiver ingressado. O carimbo de data e hora de quando o canal deixa o evento se não for nulo.</span><span class="sxs-lookup"><span data-stu-id="52179-p101">Null if participant is still joined. The time stamp of the channel leaving event if not null.</span></span></p>
<p><span data-ttu-id="52179-123">Essas entradas são eventualmente removidas quando todos os conversores processam o evento.</span><span class="sxs-lookup"><span data-stu-id="52179-123">These entries are eventually removed when all translators process the event.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52179-124">userUri</span><span class="sxs-lookup"><span data-stu-id="52179-124">userUri</span></span></p></td>
<td><p><span data-ttu-id="52179-125">nvarchar (255), não nulo</span><span class="sxs-lookup"><span data-stu-id="52179-125">nvarchar(255), not null</span></span></p></td>
<td><p><span data-ttu-id="52179-126">URI do Usuário.</span><span class="sxs-lookup"><span data-stu-id="52179-126">User URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52179-127">serverID</span><span class="sxs-lookup"><span data-stu-id="52179-127">serverID</span></span></p></td>
<td><p><span data-ttu-id="52179-128">int</span><span class="sxs-lookup"><span data-stu-id="52179-128">int</span></span></p></td>
<td><p><span data-ttu-id="52179-129">Identidade do servidor (como na tabela tblServerIdentity.serverID).</span><span class="sxs-lookup"><span data-stu-id="52179-129">Server identity (as in tblServerIdentity.serverID table).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52179-130">Identificação_da_sessão</span><span class="sxs-lookup"><span data-stu-id="52179-130">sessionId</span></span></p></td>
<td><p><span data-ttu-id="52179-131">bigint</span><span class="sxs-lookup"><span data-stu-id="52179-131">bigint</span></span></p></td>
<td><p><span data-ttu-id="52179-p102">Sessão do servidor. Este é um número aleatório gerado sempre que um serviço de chat é iniciado. Ele é usado para diferenciar as sessões a fim de identificar os participantes órfãos.</span><span class="sxs-lookup"><span data-stu-id="52179-p102">Server session. This is a random number generated each time a Chat service starts. It is used to differentiate sessions for the purpose of identifying orphaned participants.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="52179-135">Chave</span><span class="sxs-lookup"><span data-stu-id="52179-135">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="52179-136">Coluna</span><span class="sxs-lookup"><span data-stu-id="52179-136">Column</span></span></th>
<th><span data-ttu-id="52179-137">Descrição</span><span class="sxs-lookup"><span data-stu-id="52179-137">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="52179-138">&lt;channelUri, userId, joinedAt&gt;</span><span class="sxs-lookup"><span data-stu-id="52179-138">&lt;channelUri, userId, joinedAt&gt;</span></span></p></td>
<td><p><span data-ttu-id="52179-139">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="52179-139">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

