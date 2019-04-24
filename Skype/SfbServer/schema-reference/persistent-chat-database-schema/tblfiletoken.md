---
title: tblFileToken
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 49e7dd79-1607-443c-818a-88c160e4ed06
description: tblFileToken inclui tokens temporários para fins de transferência de arquivo.
ms.openlocfilehash: 46553a4b8752e2a95691dc2042a2632845166fc7
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212597"
---
# <a name="tblfiletoken"></a><span data-ttu-id="cef31-103">tblFileToken</span><span class="sxs-lookup"><span data-stu-id="cef31-103">tblFileToken</span></span>
 
<span data-ttu-id="cef31-104">tblFileToken inclui tokens temporários para fins de transferência de arquivo.</span><span class="sxs-lookup"><span data-stu-id="cef31-104">tblFileToken contains temporary tokens for file transfer purposes.</span></span>
  
<span data-ttu-id="cef31-105">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="cef31-105">**Columns**</span></span>

|<span data-ttu-id="cef31-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="cef31-106">**Column**</span></span>|<span data-ttu-id="cef31-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="cef31-107">**Type**</span></span>|<span data-ttu-id="cef31-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="cef31-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="cef31-109">fileToken</span><span class="sxs-lookup"><span data-stu-id="cef31-109">fileToken</span></span>  <br/> |<span data-ttu-id="cef31-110">nvarchar (50), não nulo</span><span class="sxs-lookup"><span data-stu-id="cef31-110">nvarchar (50), not null</span></span>  <br/> |<span data-ttu-id="cef31-111">Token exclusivo (GUID).</span><span class="sxs-lookup"><span data-stu-id="cef31-111">Unique token (a GUID).</span></span>  <br/> |
|<span data-ttu-id="cef31-112">fileTokenUserID</span><span class="sxs-lookup"><span data-stu-id="cef31-112">fileTokenUserID</span></span>  <br/> |<span data-ttu-id="cef31-113">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="cef31-113">int, not null</span></span>  <br/> |<span data-ttu-id="cef31-114">ID da entidade que está transferindo o arquivo.</span><span class="sxs-lookup"><span data-stu-id="cef31-114">ID of the principal that is transferring the file.</span></span>  <br/> |
|<span data-ttu-id="cef31-115">fileTokenChannelID</span><span class="sxs-lookup"><span data-stu-id="cef31-115">fileTokenChannelID</span></span>  <br/> |<span data-ttu-id="cef31-116">GUID, não nulo</span><span class="sxs-lookup"><span data-stu-id="cef31-116">GUID, not null</span></span>  <br/> |<span data-ttu-id="cef31-117">GUID do nó de sala de chat.</span><span class="sxs-lookup"><span data-stu-id="cef31-117">GUID of the chat room node.</span></span>  <br/> |
|<span data-ttu-id="cef31-118">fileTokenExpireDate</span><span class="sxs-lookup"><span data-stu-id="cef31-118">fileTokenExpireDate</span></span>  <br/> |<span data-ttu-id="cef31-119">DateTime, não nulo</span><span class="sxs-lookup"><span data-stu-id="cef31-119">datetime, not null</span></span>  <br/> |<span data-ttu-id="cef31-120">Tempo de expiração.</span><span class="sxs-lookup"><span data-stu-id="cef31-120">Expiration time.</span></span> <span data-ttu-id="cef31-121">(Tokens expiram após 30 minutos, a menos que fixados (consulte as seguintes descrições nessa coluna).</span><span class="sxs-lookup"><span data-stu-id="cef31-121">(Tokens expire after 30 minutes, unless pinned (see the following descriptions in this column).</span></span>  <br/> |
|<span data-ttu-id="cef31-122">fileTokenComplianceFileUrl</span><span class="sxs-lookup"><span data-stu-id="cef31-122">fileTokenComplianceFileUrl</span></span>  <br/> |<span data-ttu-id="cef31-123">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="cef31-123">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="cef31-124">URL do arquivo transferido (para uso do serviço de conformidade).</span><span class="sxs-lookup"><span data-stu-id="cef31-124">URL of the transferred file (for Compliance service use).</span></span>  <br/> |
|<span data-ttu-id="cef31-125">fileTokenComplianceThumbnailUrl</span><span class="sxs-lookup"><span data-stu-id="cef31-125">fileTokenComplianceThumbnailUrl</span></span>  <br/> |<span data-ttu-id="cef31-126">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="cef31-126">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="cef31-127">URL da miniatura para o arquivo transferido (para uso do serviço de conformidade).</span><span class="sxs-lookup"><span data-stu-id="cef31-127">URL of the thumbnail for the transferred file (for Compliance service use).</span></span>  <br/> |
|<span data-ttu-id="cef31-128">fileTokenComplianceTime</span><span class="sxs-lookup"><span data-stu-id="cef31-128">fileTokenComplianceTime</span></span>  <br/> |<span data-ttu-id="cef31-129">datetime2</span><span class="sxs-lookup"><span data-stu-id="cef31-129">datetime2</span></span>  <br/> |<span data-ttu-id="cef31-130">Carimbo de hora para a operação de transferência de arquivo real (para uso do serviço de conformidade).</span><span class="sxs-lookup"><span data-stu-id="cef31-130">Timestamp for the actual file transfer operation (for Compliance service use).</span></span>  <br/> |
|<span data-ttu-id="cef31-131">fileTokenComplianceIsUpload</span><span class="sxs-lookup"><span data-stu-id="cef31-131">fileTokenComplianceIsUpload</span></span>  <br/> |<span data-ttu-id="cef31-132">bit</span><span class="sxs-lookup"><span data-stu-id="cef31-132">bit</span></span>  <br/> |<span data-ttu-id="cef31-133">True se carregar; False se download (para uso do serviço de conformidade).</span><span class="sxs-lookup"><span data-stu-id="cef31-133">True if upload; False if download (for Compliance service use).</span></span>  <br/> |
|<span data-ttu-id="cef31-134">fileTokenCompliancePinned</span><span class="sxs-lookup"><span data-stu-id="cef31-134">fileTokenCompliancePinned</span></span>  <br/> |<span data-ttu-id="cef31-135">bit, não nulo</span><span class="sxs-lookup"><span data-stu-id="cef31-135">bit, not null</span></span>  <br/> |<span data-ttu-id="cef31-136">True se o token é fixado.</span><span class="sxs-lookup"><span data-stu-id="cef31-136">True if token is pinned.</span></span> <span data-ttu-id="cef31-137">Ele é usado para manter o token na tabela até que tenha o serviço de conformidade a oportunidade de se recuperar os campos relevantes a partir dele.</span><span class="sxs-lookup"><span data-stu-id="cef31-137">It's used to keep the token in the table until Compliance service has a chance to retrieve the relevant fields from it.</span></span>  <br/> |
   
<span data-ttu-id="cef31-138">**Chaves**</span><span class="sxs-lookup"><span data-stu-id="cef31-138">**Keys**</span></span>

|<span data-ttu-id="cef31-139">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="cef31-139">**Column**</span></span>|<span data-ttu-id="cef31-140">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="cef31-140">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="cef31-141">fileToken</span><span class="sxs-lookup"><span data-stu-id="cef31-141">fileToken</span></span>  <br/> |<span data-ttu-id="cef31-142">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="cef31-142">Primary key.</span></span>  <br/> |
|<span data-ttu-id="cef31-143">fileTokenChannelID</span><span class="sxs-lookup"><span data-stu-id="cef31-143">fileTokenChannelID</span></span>  <br/> |<span data-ttu-id="cef31-144">Chave estrangeira com pesquisa na tabela Nodeguid.</span><span class="sxs-lookup"><span data-stu-id="cef31-144">Foreign key with lookup in tblNode.nodeGuid table.</span></span>  <br/> |
   

