---
title: 'Lync Server 2013: tblFileToken'
description: 'Lync Server 2013: tblFileToken.'
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
ms.openlocfilehash: 9c0a0465bd769cff5c23c00a98f79e2346232175
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547627"
---
# <a name="tblfiletoken-in-lync-server-2013"></a><span data-ttu-id="5ac2f-103">tblFileToken no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5ac2f-103">tblFileToken in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5ac2f-104">_**Última modificação do tópico:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="5ac2f-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="5ac2f-105">tblFileToken inclui tokens temporários para fins de transferência de arquivos.</span><span class="sxs-lookup"><span data-stu-id="5ac2f-105">tblFileToken contains temporary tokens for file transfer purposes.</span></span>

### <a name="columns"></a><span data-ttu-id="5ac2f-106">Colunas</span><span class="sxs-lookup"><span data-stu-id="5ac2f-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5ac2f-107">Coluna</span><span class="sxs-lookup"><span data-stu-id="5ac2f-107">Column</span></span></th>
<th><span data-ttu-id="5ac2f-108">Tipo</span><span class="sxs-lookup"><span data-stu-id="5ac2f-108">Type</span></span></th>
<th><span data-ttu-id="5ac2f-109">Descrição</span><span class="sxs-lookup"><span data-stu-id="5ac2f-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5ac2f-110">token de</span><span class="sxs-lookup"><span data-stu-id="5ac2f-110">fileToken</span></span></p></td>
<td><p><span data-ttu-id="5ac2f-111">nvarchar (50), not null</span><span class="sxs-lookup"><span data-stu-id="5ac2f-111">nvarchar (50), not null</span></span></p></td>
<td><p><span data-ttu-id="5ac2f-112">Token exclusivo (uma GUID).</span><span class="sxs-lookup"><span data-stu-id="5ac2f-112">Unique token (a GUID).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5ac2f-113">fileTokenUserID</span><span class="sxs-lookup"><span data-stu-id="5ac2f-113">fileTokenUserID</span></span></p></td>
<td><p><span data-ttu-id="5ac2f-114">int, not null</span><span class="sxs-lookup"><span data-stu-id="5ac2f-114">int, not null</span></span></p></td>
<td><p><span data-ttu-id="5ac2f-115">ID da entidade de segurança que está transferindo o arquivo.</span><span class="sxs-lookup"><span data-stu-id="5ac2f-115">ID of the principal that is transferring the file.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5ac2f-116">fileTokenChannelID</span><span class="sxs-lookup"><span data-stu-id="5ac2f-116">fileTokenChannelID</span></span></p></td>
<td><p><span data-ttu-id="5ac2f-117">GUID, não vazio</span><span class="sxs-lookup"><span data-stu-id="5ac2f-117">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="5ac2f-118">GUID do nó da sala de chat.</span><span class="sxs-lookup"><span data-stu-id="5ac2f-118">GUID of the chat room node.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5ac2f-119">fileTokenExpireDate</span><span class="sxs-lookup"><span data-stu-id="5ac2f-119">fileTokenExpireDate</span></span></p></td>
<td><p><span data-ttu-id="5ac2f-120">datetime, not null</span><span class="sxs-lookup"><span data-stu-id="5ac2f-120">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="5ac2f-p101">Tempo de expiração. (Tokens expiram após 30 minutos, a menos que fixado (consultar as descrições a seguir nesta coluna).</span><span class="sxs-lookup"><span data-stu-id="5ac2f-p101">Expiration time. (Tokens expire after 30 minutes, unless pinned (see the following descriptions in this column).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5ac2f-123">fileTokenComplianceFileUrl</span><span class="sxs-lookup"><span data-stu-id="5ac2f-123">fileTokenComplianceFileUrl</span></span></p></td>
<td><p><span data-ttu-id="5ac2f-124">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="5ac2f-124">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5ac2f-125">URL do arquivo transferido (para uso do serviço de Conformidade).</span><span class="sxs-lookup"><span data-stu-id="5ac2f-125">URL of the transferred file (for Compliance service use).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5ac2f-126">fileTokenComplianceThumbnailUrl</span><span class="sxs-lookup"><span data-stu-id="5ac2f-126">fileTokenComplianceThumbnailUrl</span></span></p></td>
<td><p><span data-ttu-id="5ac2f-127">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="5ac2f-127">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5ac2f-128">URL da miniatura para o arquivo transferido (para uso do serviço de Conformidade).</span><span class="sxs-lookup"><span data-stu-id="5ac2f-128">URL of the thumbnail for the transferred file (for Compliance service use).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5ac2f-129">fileTokenComplianceTime</span><span class="sxs-lookup"><span data-stu-id="5ac2f-129">fileTokenComplianceTime</span></span></p></td>
<td><p><span data-ttu-id="5ac2f-130">datetime2</span><span class="sxs-lookup"><span data-stu-id="5ac2f-130">datetime2</span></span></p></td>
<td><p><span data-ttu-id="5ac2f-131">Carimbo de data e hora para a operação de transferência de arquivo atual (para uso do serviço de Conformidade).</span><span class="sxs-lookup"><span data-stu-id="5ac2f-131">Timestamp for the actual file transfer operation (for Compliance service use).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5ac2f-132">fileTokenComplianceIsUpload</span><span class="sxs-lookup"><span data-stu-id="5ac2f-132">fileTokenComplianceIsUpload</span></span></p></td>
<td><p><span data-ttu-id="5ac2f-133">bits</span><span class="sxs-lookup"><span data-stu-id="5ac2f-133">bit</span></span></p></td>
<td><p><span data-ttu-id="5ac2f-134">Verdadeiro em caso de upload; Falso se download (para uso do serviço de Conformidade).</span><span class="sxs-lookup"><span data-stu-id="5ac2f-134">True if upload; False if download (for Compliance service use).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5ac2f-135">fileTokenCompliancePinned</span><span class="sxs-lookup"><span data-stu-id="5ac2f-135">fileTokenCompliancePinned</span></span></p></td>
<td><p><span data-ttu-id="5ac2f-136">bit, não vazio</span><span class="sxs-lookup"><span data-stu-id="5ac2f-136">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="5ac2f-p102">Verdadeiro se fixado. É utilizado para manter o token na tabela até que o serviço de Conformidade tenha uma chance de recuperar os campos dele.</span><span class="sxs-lookup"><span data-stu-id="5ac2f-p102">True if token is pinned. It’s used to keep the token in the table until Compliance service has a chance to retrieve the relevant fields from it.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="5ac2f-139">Chaves</span><span class="sxs-lookup"><span data-stu-id="5ac2f-139">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5ac2f-140">Coluna</span><span class="sxs-lookup"><span data-stu-id="5ac2f-140">Column</span></span></th>
<th><span data-ttu-id="5ac2f-141">Descrição</span><span class="sxs-lookup"><span data-stu-id="5ac2f-141">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5ac2f-142">token de</span><span class="sxs-lookup"><span data-stu-id="5ac2f-142">fileToken</span></span></p></td>
<td><p><span data-ttu-id="5ac2f-143">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="5ac2f-143">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5ac2f-144">fileTokenChannelID</span><span class="sxs-lookup"><span data-stu-id="5ac2f-144">fileTokenChannelID</span></span></p></td>
<td><p><span data-ttu-id="5ac2f-145">Chave estrangeira com pesquisa na tabela tblNode.nodeGuid.</span><span class="sxs-lookup"><span data-stu-id="5ac2f-145">Foreign key with lookup in tblNode.nodeGuid table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

