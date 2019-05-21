---
title: tblFileToken
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 49e7dd79-1607-443c-818a-88c160e4ed06
description: tblFileToken contém tokens temporários para fins de transferência de arquivo.
ms.openlocfilehash: 108c9738657354881324ec720f50a51605530922
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295402"
---
# <a name="tblfiletoken"></a><span data-ttu-id="77de4-103">tblFileToken</span><span class="sxs-lookup"><span data-stu-id="77de4-103">tblFileToken</span></span>
 
<span data-ttu-id="77de4-104">tblFileToken contém tokens temporários para fins de transferência de arquivo.</span><span class="sxs-lookup"><span data-stu-id="77de4-104">tblFileToken contains temporary tokens for file transfer purposes.</span></span>
  
<span data-ttu-id="77de4-105">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="77de4-105">**Columns**</span></span>

|<span data-ttu-id="77de4-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="77de4-106">**Column**</span></span>|<span data-ttu-id="77de4-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="77de4-107">**Type**</span></span>|<span data-ttu-id="77de4-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="77de4-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="77de4-109">Filetoken</span><span class="sxs-lookup"><span data-stu-id="77de4-109">fileToken</span></span>  <br/> |<span data-ttu-id="77de4-110">nvarchar (50), NOT NULL</span><span class="sxs-lookup"><span data-stu-id="77de4-110">nvarchar (50), not null</span></span>  <br/> |<span data-ttu-id="77de4-111">Token exclusivo (a GUID).</span><span class="sxs-lookup"><span data-stu-id="77de4-111">Unique token (a GUID).</span></span>  <br/> |
|<span data-ttu-id="77de4-112">fileTokenUserID</span><span class="sxs-lookup"><span data-stu-id="77de4-112">fileTokenUserID</span></span>  <br/> |<span data-ttu-id="77de4-113">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="77de4-113">int, not null</span></span>  <br/> |<span data-ttu-id="77de4-114">ID da entidade de segurança que está transferindo o arquivo.</span><span class="sxs-lookup"><span data-stu-id="77de4-114">ID of the principal that is transferring the file.</span></span>  <br/> |
|<span data-ttu-id="77de4-115">fileTokenChannelID</span><span class="sxs-lookup"><span data-stu-id="77de4-115">fileTokenChannelID</span></span>  <br/> |<span data-ttu-id="77de4-116">GUID, não nulo</span><span class="sxs-lookup"><span data-stu-id="77de4-116">GUID, not null</span></span>  <br/> |<span data-ttu-id="77de4-117">GUID do nó da sala de chat.</span><span class="sxs-lookup"><span data-stu-id="77de4-117">GUID of the chat room node.</span></span>  <br/> |
|<span data-ttu-id="77de4-118">fileTokenExpireDate</span><span class="sxs-lookup"><span data-stu-id="77de4-118">fileTokenExpireDate</span></span>  <br/> |<span data-ttu-id="77de4-119">DateTime, não nulo</span><span class="sxs-lookup"><span data-stu-id="77de4-119">datetime, not null</span></span>  <br/> |<span data-ttu-id="77de4-120">Tempo de expiração.</span><span class="sxs-lookup"><span data-stu-id="77de4-120">Expiration time.</span></span> <span data-ttu-id="77de4-121">(Os tokens expiram após 30 minutos, a menos que sejam fixados (consulte as descrições a seguir nesta coluna).</span><span class="sxs-lookup"><span data-stu-id="77de4-121">(Tokens expire after 30 minutes, unless pinned (see the following descriptions in this column).</span></span>  <br/> |
|<span data-ttu-id="77de4-122">fileTokenComplianceFileUrl</span><span class="sxs-lookup"><span data-stu-id="77de4-122">fileTokenComplianceFileUrl</span></span>  <br/> |<span data-ttu-id="77de4-123">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="77de4-123">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="77de4-124">URL do arquivo transferido (para uso do serviço de conformidade).</span><span class="sxs-lookup"><span data-stu-id="77de4-124">URL of the transferred file (for Compliance service use).</span></span>  <br/> |
|<span data-ttu-id="77de4-125">fileTokenComplianceThumbnailUrl</span><span class="sxs-lookup"><span data-stu-id="77de4-125">fileTokenComplianceThumbnailUrl</span></span>  <br/> |<span data-ttu-id="77de4-126">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="77de4-126">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="77de4-127">URL da miniatura do arquivo transferido (para uso do serviço de conformidade).</span><span class="sxs-lookup"><span data-stu-id="77de4-127">URL of the thumbnail for the transferred file (for Compliance service use).</span></span>  <br/> |
|<span data-ttu-id="77de4-128">fileTokenComplianceTime</span><span class="sxs-lookup"><span data-stu-id="77de4-128">fileTokenComplianceTime</span></span>  <br/> |<span data-ttu-id="77de4-129">datetime2</span><span class="sxs-lookup"><span data-stu-id="77de4-129">datetime2</span></span>  <br/> |<span data-ttu-id="77de4-130">Carimbo de data/hora para a operação de transferência de arquivo real (para uso do serviço de conformidade).</span><span class="sxs-lookup"><span data-stu-id="77de4-130">Timestamp for the actual file transfer operation (for Compliance service use).</span></span>  <br/> |
|<span data-ttu-id="77de4-131">fileTokenComplianceIsUpload</span><span class="sxs-lookup"><span data-stu-id="77de4-131">fileTokenComplianceIsUpload</span></span>  <br/> |<span data-ttu-id="77de4-132">bit</span><span class="sxs-lookup"><span data-stu-id="77de4-132">bit</span></span>  <br/> |<span data-ttu-id="77de4-133">Verdadeiro se for carregado; Falso se baixar (para uso do serviço de conformidade).</span><span class="sxs-lookup"><span data-stu-id="77de4-133">True if upload; False if download (for Compliance service use).</span></span>  <br/> |
|<span data-ttu-id="77de4-134">fileTokenCompliancePinned</span><span class="sxs-lookup"><span data-stu-id="77de4-134">fileTokenCompliancePinned</span></span>  <br/> |<span data-ttu-id="77de4-135">bit, e não nulo</span><span class="sxs-lookup"><span data-stu-id="77de4-135">bit, not null</span></span>  <br/> |<span data-ttu-id="77de4-136">Verdadeiro se o token estiver fixado.</span><span class="sxs-lookup"><span data-stu-id="77de4-136">True if token is pinned.</span></span> <span data-ttu-id="77de4-137">Ele é usado para manter o token na tabela até que o serviço de conformidade tenha a chance de recuperar os campos relevantes dele.</span><span class="sxs-lookup"><span data-stu-id="77de4-137">It's used to keep the token in the table until Compliance service has a chance to retrieve the relevant fields from it.</span></span>  <br/> |
   
<span data-ttu-id="77de4-138">**As**</span><span class="sxs-lookup"><span data-stu-id="77de4-138">**Keys**</span></span>

|<span data-ttu-id="77de4-139">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="77de4-139">**Column**</span></span>|<span data-ttu-id="77de4-140">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="77de4-140">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="77de4-141">Filetoken</span><span class="sxs-lookup"><span data-stu-id="77de4-141">fileToken</span></span>  <br/> |<span data-ttu-id="77de4-142">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="77de4-142">Primary key.</span></span>  <br/> |
|<span data-ttu-id="77de4-143">fileTokenChannelID</span><span class="sxs-lookup"><span data-stu-id="77de4-143">fileTokenChannelID</span></span>  <br/> |<span data-ttu-id="77de4-144">Chave estrangeira com Lookup na tabela tblNode. nodeGuid.</span><span class="sxs-lookup"><span data-stu-id="77de4-144">Foreign key with lookup in tblNode.nodeGuid table.</span></span>  <br/> |
   

