---
title: 'Lync Server 2013: tblComplianceParticipant'
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
ms.openlocfilehash: 38d4a47f3778e2343685a993378d97cc37c827a2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42207217"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblcomplianceparticipant-in-lync-server-2013"></a><span data-ttu-id="675cd-102">tblComplianceParticipant no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="675cd-102">tblComplianceParticipant in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="675cd-103">_**Última modificação do tópico:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="675cd-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="675cd-104">tblComplianceParticipant contém os participantes atuais por canal e por servidor.</span><span class="sxs-lookup"><span data-stu-id="675cd-104">tblComplianceParticipant contains the current participants per channel and per server.</span></span>

### <a name="columns"></a><span data-ttu-id="675cd-105">Colunas</span><span class="sxs-lookup"><span data-stu-id="675cd-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="675cd-106">Coluna</span><span class="sxs-lookup"><span data-stu-id="675cd-106">Column</span></span></th>
<th><span data-ttu-id="675cd-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="675cd-107">Type</span></span></th>
<th><span data-ttu-id="675cd-108">Descrição</span><span class="sxs-lookup"><span data-stu-id="675cd-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="675cd-109">channelUri</span><span class="sxs-lookup"><span data-stu-id="675cd-109">channelUri</span></span></p></td>
<td><p><span data-ttu-id="675cd-110">nvarchar (255), não nulo</span><span class="sxs-lookup"><span data-stu-id="675cd-110">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="675cd-111">Identificador de Recurso Uniforme do Canal (URI).</span><span class="sxs-lookup"><span data-stu-id="675cd-111">Channel Uniform Resource Identifier (URI).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="675cd-112">userId</span><span class="sxs-lookup"><span data-stu-id="675cd-112">userId</span></span></p></td>
<td><p><span data-ttu-id="675cd-113">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="675cd-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="675cd-114">ID da entidade do participante (correspondente à tabela tblPrincipal.prinID).</span><span class="sxs-lookup"><span data-stu-id="675cd-114">Principal ID of the participant (corresponding to tblPrincipal.prinID table).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="675cd-115">joinedAt</span><span class="sxs-lookup"><span data-stu-id="675cd-115">joinedAt</span></span></p></td>
<td><p><span data-ttu-id="675cd-116">bigint, não nulo</span><span class="sxs-lookup"><span data-stu-id="675cd-116">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="675cd-117">Carimbo de data e hora de ingresso no evento.</span><span class="sxs-lookup"><span data-stu-id="675cd-117">Time stamp of the joining event.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="675cd-118">partedAt</span><span class="sxs-lookup"><span data-stu-id="675cd-118">partedAt</span></span></p></td>
<td><p><span data-ttu-id="675cd-119">bigint</span><span class="sxs-lookup"><span data-stu-id="675cd-119">bigint</span></span></p></td>
<td><p><span data-ttu-id="675cd-p101">Nulo se o participante ainda estiver ingressado. O carimbo de data e hora de quando o canal deixa o evento se não for nulo.</span><span class="sxs-lookup"><span data-stu-id="675cd-p101">Null if participant is still joined. The time stamp of the channel leaving event if not null.</span></span></p>
<p><span data-ttu-id="675cd-122">Essas entradas são eventualmente removidas quando todos os conversores processam o evento.</span><span class="sxs-lookup"><span data-stu-id="675cd-122">These entries are eventually removed when all translators process the event.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="675cd-123">userUri</span><span class="sxs-lookup"><span data-stu-id="675cd-123">userUri</span></span></p></td>
<td><p><span data-ttu-id="675cd-124">nvarchar (255), não nulo</span><span class="sxs-lookup"><span data-stu-id="675cd-124">nvarchar(255), not null</span></span></p></td>
<td><p><span data-ttu-id="675cd-125">URI do Usuário.</span><span class="sxs-lookup"><span data-stu-id="675cd-125">User URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="675cd-126">serverID</span><span class="sxs-lookup"><span data-stu-id="675cd-126">serverID</span></span></p></td>
<td><p><span data-ttu-id="675cd-127">int</span><span class="sxs-lookup"><span data-stu-id="675cd-127">int</span></span></p></td>
<td><p><span data-ttu-id="675cd-128">Identidade do servidor (como na tabela tblServerIdentity.serverID).</span><span class="sxs-lookup"><span data-stu-id="675cd-128">Server identity (as in tblServerIdentity.serverID table).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="675cd-129">Identificação_da_sessão</span><span class="sxs-lookup"><span data-stu-id="675cd-129">sessionId</span></span></p></td>
<td><p><span data-ttu-id="675cd-130">bigint</span><span class="sxs-lookup"><span data-stu-id="675cd-130">bigint</span></span></p></td>
<td><p><span data-ttu-id="675cd-p102">Sessão do servidor. Este é um número aleatório gerado sempre que um serviço de chat é iniciado. Ele é usado para diferenciar as sessões a fim de identificar os participantes órfãos.</span><span class="sxs-lookup"><span data-stu-id="675cd-p102">Server session. This is a random number generated each time a Chat service starts. It is used to differentiate sessions for the purpose of identifying orphaned participants.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="675cd-134">Chave</span><span class="sxs-lookup"><span data-stu-id="675cd-134">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="675cd-135">Coluna</span><span class="sxs-lookup"><span data-stu-id="675cd-135">Column</span></span></th>
<th><span data-ttu-id="675cd-136">Descrição</span><span class="sxs-lookup"><span data-stu-id="675cd-136">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="675cd-137">&lt;channelUri, userId, joinedAt&gt;</span><span class="sxs-lookup"><span data-stu-id="675cd-137">&lt;channelUri, userId, joinedAt&gt;</span></span></p></td>
<td><p><span data-ttu-id="675cd-138">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="675cd-138">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

