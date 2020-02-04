---
title: 'Lync Server 2013: tblFileToken'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblFileToken
ms:assetid: 49e7dd79-1607-443c-818a-88c160e4ed06
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558646(v=OCS.15)
ms:contentKeyID: 48184073
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b469b79e680c202654024d1ac20a55b9929e4b10
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764177"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblfiletoken-in-lync-server-2013"></a><span data-ttu-id="1d613-102">tblFileToken no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1d613-102">tblFileToken in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1d613-103">_**Tópico da última modificação:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="1d613-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="1d613-104">tblFileToken contém tokens temporários para fins de transferência de arquivo.</span><span class="sxs-lookup"><span data-stu-id="1d613-104">tblFileToken contains temporary tokens for file transfer purposes.</span></span>

### <a name="columns"></a><span data-ttu-id="1d613-105">Colunas</span><span class="sxs-lookup"><span data-stu-id="1d613-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1d613-106">Coluna</span><span class="sxs-lookup"><span data-stu-id="1d613-106">Column</span></span></th>
<th><span data-ttu-id="1d613-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="1d613-107">Type</span></span></th>
<th><span data-ttu-id="1d613-108">Descrição</span><span class="sxs-lookup"><span data-stu-id="1d613-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1d613-109">Filetoken</span><span class="sxs-lookup"><span data-stu-id="1d613-109">fileToken</span></span></p></td>
<td><p><span data-ttu-id="1d613-110">nvarchar (50), NOT NULL</span><span class="sxs-lookup"><span data-stu-id="1d613-110">nvarchar (50), not null</span></span></p></td>
<td><p><span data-ttu-id="1d613-111">Token exclusivo (a GUID).</span><span class="sxs-lookup"><span data-stu-id="1d613-111">Unique token (a GUID).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d613-112">fileTokenUserID</span><span class="sxs-lookup"><span data-stu-id="1d613-112">fileTokenUserID</span></span></p></td>
<td><p><span data-ttu-id="1d613-113">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="1d613-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="1d613-114">ID da entidade de segurança que está transferindo o arquivo.</span><span class="sxs-lookup"><span data-stu-id="1d613-114">ID of the principal that is transferring the file.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d613-115">fileTokenChannelID</span><span class="sxs-lookup"><span data-stu-id="1d613-115">fileTokenChannelID</span></span></p></td>
<td><p><span data-ttu-id="1d613-116">GUID, não nulo</span><span class="sxs-lookup"><span data-stu-id="1d613-116">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="1d613-117">GUID do nó da sala de chat.</span><span class="sxs-lookup"><span data-stu-id="1d613-117">GUID of the chat room node.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d613-118">fileTokenExpireDate</span><span class="sxs-lookup"><span data-stu-id="1d613-118">fileTokenExpireDate</span></span></p></td>
<td><p><span data-ttu-id="1d613-119">DateTime, não nulo</span><span class="sxs-lookup"><span data-stu-id="1d613-119">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="1d613-120">Tempo de expiração.</span><span class="sxs-lookup"><span data-stu-id="1d613-120">Expiration time.</span></span> <span data-ttu-id="1d613-121">(Os tokens expiram após 30 minutos, a menos que sejam fixados (consulte as descrições a seguir nesta coluna).</span><span class="sxs-lookup"><span data-stu-id="1d613-121">(Tokens expire after 30 minutes, unless pinned (see the following descriptions in this column).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d613-122">fileTokenComplianceFileUrl</span><span class="sxs-lookup"><span data-stu-id="1d613-122">fileTokenComplianceFileUrl</span></span></p></td>
<td><p><span data-ttu-id="1d613-123">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="1d613-123">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1d613-124">URL do arquivo transferido (para uso do serviço de conformidade).</span><span class="sxs-lookup"><span data-stu-id="1d613-124">URL of the transferred file (for Compliance service use).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d613-125">fileTokenComplianceThumbnailUrl</span><span class="sxs-lookup"><span data-stu-id="1d613-125">fileTokenComplianceThumbnailUrl</span></span></p></td>
<td><p><span data-ttu-id="1d613-126">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="1d613-126">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1d613-127">URL da miniatura do arquivo transferido (para uso do serviço de conformidade).</span><span class="sxs-lookup"><span data-stu-id="1d613-127">URL of the thumbnail for the transferred file (for Compliance service use).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d613-128">fileTokenComplianceTime</span><span class="sxs-lookup"><span data-stu-id="1d613-128">fileTokenComplianceTime</span></span></p></td>
<td><p><span data-ttu-id="1d613-129">datetime2</span><span class="sxs-lookup"><span data-stu-id="1d613-129">datetime2</span></span></p></td>
<td><p><span data-ttu-id="1d613-130">Carimbo de data/hora para a operação de transferência de arquivo real (para uso do serviço de conformidade).</span><span class="sxs-lookup"><span data-stu-id="1d613-130">Timestamp for the actual file transfer operation (for Compliance service use).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d613-131">fileTokenComplianceIsUpload</span><span class="sxs-lookup"><span data-stu-id="1d613-131">fileTokenComplianceIsUpload</span></span></p></td>
<td><p><span data-ttu-id="1d613-132">bit</span><span class="sxs-lookup"><span data-stu-id="1d613-132">bit</span></span></p></td>
<td><p><span data-ttu-id="1d613-133">Verdadeiro se for carregado; Falso se baixar (para uso do serviço de conformidade).</span><span class="sxs-lookup"><span data-stu-id="1d613-133">True if upload; False if download (for Compliance service use).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d613-134">fileTokenCompliancePinned</span><span class="sxs-lookup"><span data-stu-id="1d613-134">fileTokenCompliancePinned</span></span></p></td>
<td><p><span data-ttu-id="1d613-135">bit, e não nulo</span><span class="sxs-lookup"><span data-stu-id="1d613-135">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="1d613-136">Verdadeiro se o token estiver fixado.</span><span class="sxs-lookup"><span data-stu-id="1d613-136">True if token is pinned.</span></span> <span data-ttu-id="1d613-137">Ele é usado para manter o token na tabela até que o serviço de conformidade tenha a chance de recuperar os campos relevantes dele.</span><span class="sxs-lookup"><span data-stu-id="1d613-137">It’s used to keep the token in the table until Compliance service has a chance to retrieve the relevant fields from it.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="1d613-138">As</span><span class="sxs-lookup"><span data-stu-id="1d613-138">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1d613-139">Coluna</span><span class="sxs-lookup"><span data-stu-id="1d613-139">Column</span></span></th>
<th><span data-ttu-id="1d613-140">Descrição</span><span class="sxs-lookup"><span data-stu-id="1d613-140">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1d613-141">Filetoken</span><span class="sxs-lookup"><span data-stu-id="1d613-141">fileToken</span></span></p></td>
<td><p><span data-ttu-id="1d613-142">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="1d613-142">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d613-143">fileTokenChannelID</span><span class="sxs-lookup"><span data-stu-id="1d613-143">fileTokenChannelID</span></span></p></td>
<td><p><span data-ttu-id="1d613-144">Chave estrangeira com Lookup na tabela tblNode. nodeGuid.</span><span class="sxs-lookup"><span data-stu-id="1d613-144">Foreign key with lookup in tblNode.nodeGuid table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

