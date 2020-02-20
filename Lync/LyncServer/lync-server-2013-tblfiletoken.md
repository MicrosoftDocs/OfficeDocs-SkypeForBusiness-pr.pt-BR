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
ms.openlocfilehash: 9e3d80b1a326140a94b840c212fc8577a73e468f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142087"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblfiletoken-in-lync-server-2013"></a><span data-ttu-id="61e57-102">tblFileToken no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="61e57-102">tblFileToken in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="61e57-103">_**Última modificação do tópico:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="61e57-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="61e57-104">tblFileToken inclui tokens temporários para fins de transferência de arquivos.</span><span class="sxs-lookup"><span data-stu-id="61e57-104">tblFileToken contains temporary tokens for file transfer purposes.</span></span>

### <a name="columns"></a><span data-ttu-id="61e57-105">Colunas</span><span class="sxs-lookup"><span data-stu-id="61e57-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="61e57-106">Coluna</span><span class="sxs-lookup"><span data-stu-id="61e57-106">Column</span></span></th>
<th><span data-ttu-id="61e57-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="61e57-107">Type</span></span></th>
<th><span data-ttu-id="61e57-108">Descrição</span><span class="sxs-lookup"><span data-stu-id="61e57-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="61e57-109">token de</span><span class="sxs-lookup"><span data-stu-id="61e57-109">fileToken</span></span></p></td>
<td><p><span data-ttu-id="61e57-110">nvarchar (50), not null</span><span class="sxs-lookup"><span data-stu-id="61e57-110">nvarchar (50), not null</span></span></p></td>
<td><p><span data-ttu-id="61e57-111">Token exclusivo (uma GUID).</span><span class="sxs-lookup"><span data-stu-id="61e57-111">Unique token (a GUID).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61e57-112">fileTokenUserID</span><span class="sxs-lookup"><span data-stu-id="61e57-112">fileTokenUserID</span></span></p></td>
<td><p><span data-ttu-id="61e57-113">int, not null</span><span class="sxs-lookup"><span data-stu-id="61e57-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="61e57-114">ID da entidade de segurança que está transferindo o arquivo.</span><span class="sxs-lookup"><span data-stu-id="61e57-114">ID of the principal that is transferring the file.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61e57-115">fileTokenChannelID</span><span class="sxs-lookup"><span data-stu-id="61e57-115">fileTokenChannelID</span></span></p></td>
<td><p><span data-ttu-id="61e57-116">GUID, não vazio</span><span class="sxs-lookup"><span data-stu-id="61e57-116">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="61e57-117">GUID do nó da sala de chat.</span><span class="sxs-lookup"><span data-stu-id="61e57-117">GUID of the chat room node.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61e57-118">fileTokenExpireDate</span><span class="sxs-lookup"><span data-stu-id="61e57-118">fileTokenExpireDate</span></span></p></td>
<td><p><span data-ttu-id="61e57-119">datetime, not null</span><span class="sxs-lookup"><span data-stu-id="61e57-119">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="61e57-p101">Tempo de expiração. (Tokens expiram após 30 minutos, a menos que fixado (consultar as descrições a seguir nesta coluna).</span><span class="sxs-lookup"><span data-stu-id="61e57-p101">Expiration time. (Tokens expire after 30 minutes, unless pinned (see the following descriptions in this column).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61e57-122">fileTokenComplianceFileUrl</span><span class="sxs-lookup"><span data-stu-id="61e57-122">fileTokenComplianceFileUrl</span></span></p></td>
<td><p><span data-ttu-id="61e57-123">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="61e57-123">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="61e57-124">URL do arquivo transferido (para uso do serviço de Conformidade).</span><span class="sxs-lookup"><span data-stu-id="61e57-124">URL of the transferred file (for Compliance service use).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61e57-125">fileTokenComplianceThumbnailUrl</span><span class="sxs-lookup"><span data-stu-id="61e57-125">fileTokenComplianceThumbnailUrl</span></span></p></td>
<td><p><span data-ttu-id="61e57-126">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="61e57-126">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="61e57-127">URL da miniatura para o arquivo transferido (para uso do serviço de Conformidade).</span><span class="sxs-lookup"><span data-stu-id="61e57-127">URL of the thumbnail for the transferred file (for Compliance service use).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61e57-128">fileTokenComplianceTime</span><span class="sxs-lookup"><span data-stu-id="61e57-128">fileTokenComplianceTime</span></span></p></td>
<td><p><span data-ttu-id="61e57-129">datetime2</span><span class="sxs-lookup"><span data-stu-id="61e57-129">datetime2</span></span></p></td>
<td><p><span data-ttu-id="61e57-130">Carimbo de data e hora para a operação de transferência de arquivo atual (para uso do serviço de Conformidade).</span><span class="sxs-lookup"><span data-stu-id="61e57-130">Timestamp for the actual file transfer operation (for Compliance service use).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61e57-131">fileTokenComplianceIsUpload</span><span class="sxs-lookup"><span data-stu-id="61e57-131">fileTokenComplianceIsUpload</span></span></p></td>
<td><p><span data-ttu-id="61e57-132">bits</span><span class="sxs-lookup"><span data-stu-id="61e57-132">bit</span></span></p></td>
<td><p><span data-ttu-id="61e57-133">Verdadeiro em caso de upload; Falso se download (para uso do serviço de Conformidade).</span><span class="sxs-lookup"><span data-stu-id="61e57-133">True if upload; False if download (for Compliance service use).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61e57-134">fileTokenCompliancePinned</span><span class="sxs-lookup"><span data-stu-id="61e57-134">fileTokenCompliancePinned</span></span></p></td>
<td><p><span data-ttu-id="61e57-135">bit, não vazio</span><span class="sxs-lookup"><span data-stu-id="61e57-135">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="61e57-p102">Verdadeiro se fixado. É utilizado para manter o token na tabela até que o serviço de Conformidade tenha uma chance de recuperar os campos dele.</span><span class="sxs-lookup"><span data-stu-id="61e57-p102">True if token is pinned. It’s used to keep the token in the table until Compliance service has a chance to retrieve the relevant fields from it.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="61e57-138">Chaves</span><span class="sxs-lookup"><span data-stu-id="61e57-138">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="61e57-139">Coluna</span><span class="sxs-lookup"><span data-stu-id="61e57-139">Column</span></span></th>
<th><span data-ttu-id="61e57-140">Descrição</span><span class="sxs-lookup"><span data-stu-id="61e57-140">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="61e57-141">token de</span><span class="sxs-lookup"><span data-stu-id="61e57-141">fileToken</span></span></p></td>
<td><p><span data-ttu-id="61e57-142">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="61e57-142">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61e57-143">fileTokenChannelID</span><span class="sxs-lookup"><span data-stu-id="61e57-143">fileTokenChannelID</span></span></p></td>
<td><p><span data-ttu-id="61e57-144">Chave estrangeira com pesquisa na tabela tblNode.nodeGuid.</span><span class="sxs-lookup"><span data-stu-id="61e57-144">Foreign key with lookup in tblNode.nodeGuid table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

