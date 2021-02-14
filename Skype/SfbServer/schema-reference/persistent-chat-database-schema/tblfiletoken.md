---
title: tblFileToken
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 49e7dd79-1607-443c-818a-88c160e4ed06
description: tblFileToken inclui tokens temporários para fins de transferência de arquivos.
ms.openlocfilehash: 75d3d4df3affe3d12f94499efdb4337ade11af27
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816011"
---
# <a name="tblfiletoken"></a><span data-ttu-id="73af3-103">tblFileToken</span><span class="sxs-lookup"><span data-stu-id="73af3-103">tblFileToken</span></span>
 
<span data-ttu-id="73af3-104">tblFileToken inclui tokens temporários para fins de transferência de arquivos.</span><span class="sxs-lookup"><span data-stu-id="73af3-104">tblFileToken contains temporary tokens for file transfer purposes.</span></span>
  
<span data-ttu-id="73af3-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="73af3-105">**Columns**</span></span>

|<span data-ttu-id="73af3-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="73af3-106">**Column**</span></span>|<span data-ttu-id="73af3-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="73af3-107">**Type**</span></span>|<span data-ttu-id="73af3-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="73af3-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="73af3-109">fileToken</span><span class="sxs-lookup"><span data-stu-id="73af3-109">fileToken</span></span>  <br/> |<span data-ttu-id="73af3-110">nvarchar (50), not null</span><span class="sxs-lookup"><span data-stu-id="73af3-110">nvarchar (50), not null</span></span>  <br/> |<span data-ttu-id="73af3-111">Token exclusivo (uma GUID).</span><span class="sxs-lookup"><span data-stu-id="73af3-111">Unique token (a GUID).</span></span>  <br/> |
|<span data-ttu-id="73af3-112">fileTokenUserID</span><span class="sxs-lookup"><span data-stu-id="73af3-112">fileTokenUserID</span></span>  <br/> |<span data-ttu-id="73af3-113">int, not null</span><span class="sxs-lookup"><span data-stu-id="73af3-113">int, not null</span></span>  <br/> |<span data-ttu-id="73af3-114">ID da entidade de segurança que está transferindo o arquivo.</span><span class="sxs-lookup"><span data-stu-id="73af3-114">ID of the principal that is transferring the file.</span></span>  <br/> |
|<span data-ttu-id="73af3-115">fileTokenChannelID</span><span class="sxs-lookup"><span data-stu-id="73af3-115">fileTokenChannelID</span></span>  <br/> |<span data-ttu-id="73af3-116">GUID, não vazio</span><span class="sxs-lookup"><span data-stu-id="73af3-116">GUID, not null</span></span>  <br/> |<span data-ttu-id="73af3-117">GUID do nó da sala de chat.</span><span class="sxs-lookup"><span data-stu-id="73af3-117">GUID of the chat room node.</span></span>  <br/> |
|<span data-ttu-id="73af3-118">fileTokenExpireDate</span><span class="sxs-lookup"><span data-stu-id="73af3-118">fileTokenExpireDate</span></span>  <br/> |<span data-ttu-id="73af3-119">datetime, not null</span><span class="sxs-lookup"><span data-stu-id="73af3-119">datetime, not null</span></span>  <br/> |<span data-ttu-id="73af3-p101">Tempo de expiração. (Tokens expiram após 30 minutos, a menos que fixado (consultar as descrições a seguir nesta coluna).</span><span class="sxs-lookup"><span data-stu-id="73af3-p101">Expiration time. (Tokens expire after 30 minutes, unless pinned (see the following descriptions in this column).</span></span>  <br/> |
|<span data-ttu-id="73af3-122">fileTokenComplianceFileUrl</span><span class="sxs-lookup"><span data-stu-id="73af3-122">fileTokenComplianceFileUrl</span></span>  <br/> |<span data-ttu-id="73af3-123">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="73af3-123">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="73af3-124">URL do arquivo transferido (para uso do serviço de Conformidade).</span><span class="sxs-lookup"><span data-stu-id="73af3-124">URL of the transferred file (for Compliance service use).</span></span>  <br/> |
|<span data-ttu-id="73af3-125">fileTokenComplianceThumbnailUrl</span><span class="sxs-lookup"><span data-stu-id="73af3-125">fileTokenComplianceThumbnailUrl</span></span>  <br/> |<span data-ttu-id="73af3-126">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="73af3-126">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="73af3-127">URL da miniatura para o arquivo transferido (para uso do serviço de Conformidade).</span><span class="sxs-lookup"><span data-stu-id="73af3-127">URL of the thumbnail for the transferred file (for Compliance service use).</span></span>  <br/> |
|<span data-ttu-id="73af3-128">fileTokenComplianceTime</span><span class="sxs-lookup"><span data-stu-id="73af3-128">fileTokenComplianceTime</span></span>  <br/> |<span data-ttu-id="73af3-129">datetime2</span><span class="sxs-lookup"><span data-stu-id="73af3-129">datetime2</span></span>  <br/> |<span data-ttu-id="73af3-130">Carimbo de data e hora para a operação de transferência de arquivo atual (para uso do serviço de Conformidade).</span><span class="sxs-lookup"><span data-stu-id="73af3-130">Timestamp for the actual file transfer operation (for Compliance service use).</span></span>  <br/> |
|<span data-ttu-id="73af3-131">fileTokenComplianceIsUpload</span><span class="sxs-lookup"><span data-stu-id="73af3-131">fileTokenComplianceIsUpload</span></span>  <br/> |<span data-ttu-id="73af3-132">bit</span><span class="sxs-lookup"><span data-stu-id="73af3-132">bit</span></span>  <br/> |<span data-ttu-id="73af3-133">Verdadeiro em caso de upload; Falso se download (para uso do serviço de Conformidade).</span><span class="sxs-lookup"><span data-stu-id="73af3-133">True if upload; False if download (for Compliance service use).</span></span>  <br/> |
|<span data-ttu-id="73af3-134">fileTokenCompliancePinned</span><span class="sxs-lookup"><span data-stu-id="73af3-134">fileTokenCompliancePinned</span></span>  <br/> |<span data-ttu-id="73af3-135">bit, não vazio</span><span class="sxs-lookup"><span data-stu-id="73af3-135">bit, not null</span></span>  <br/> |<span data-ttu-id="73af3-136">Verdadeiro se fixado.</span><span class="sxs-lookup"><span data-stu-id="73af3-136">True if token is pinned.</span></span> <span data-ttu-id="73af3-137">Ele é usado para manter o token na tabela até que o serviço de Conformidade tenha a chance de recuperar os campos relevantes dele.</span><span class="sxs-lookup"><span data-stu-id="73af3-137">It's used to keep the token in the table until Compliance service has a chance to retrieve the relevant fields from it.</span></span>  <br/> |
   
<span data-ttu-id="73af3-138">**Teclas**</span><span class="sxs-lookup"><span data-stu-id="73af3-138">**Keys**</span></span>

|<span data-ttu-id="73af3-139">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="73af3-139">**Column**</span></span>|<span data-ttu-id="73af3-140">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="73af3-140">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="73af3-141">fileToken</span><span class="sxs-lookup"><span data-stu-id="73af3-141">fileToken</span></span>  <br/> |<span data-ttu-id="73af3-142">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="73af3-142">Primary key.</span></span>  <br/> |
|<span data-ttu-id="73af3-143">fileTokenChannelID</span><span class="sxs-lookup"><span data-stu-id="73af3-143">fileTokenChannelID</span></span>  <br/> |<span data-ttu-id="73af3-144">Chave estrangeira com pesquisa na tabela tblNode.nodeGuid.</span><span class="sxs-lookup"><span data-stu-id="73af3-144">Foreign key with lookup in tblNode.nodeGuid table.</span></span>  <br/> |
   

