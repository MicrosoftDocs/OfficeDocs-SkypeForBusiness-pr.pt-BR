---
title: tblComplianceData
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 05b28f9b-4aba-4b69-ba8d-2ceeb6cbfaac
description: a tabela Compliancedata inclui eventos de conformidade que ainda não foram processados pelo adaptador de conformidade.
ms.openlocfilehash: e617f7821fcf026f279f333d45f526a1322509a1
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30885818"
---
# <a name="tblcompliancedata"></a><span data-ttu-id="e5f2d-103">tblComplianceData</span><span class="sxs-lookup"><span data-stu-id="e5f2d-103">tblComplianceData</span></span>
 
<span data-ttu-id="e5f2d-104">a tabela Compliancedata inclui eventos de conformidade que ainda não foram processados pelo adaptador de conformidade.</span><span class="sxs-lookup"><span data-stu-id="e5f2d-104">tblComplianceData contains the compliance events that have not been processed by the compliance adapter yet.</span></span>
  
<span data-ttu-id="e5f2d-105">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="e5f2d-105">**Columns**</span></span>

|<span data-ttu-id="e5f2d-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="e5f2d-106">**Column**</span></span>|<span data-ttu-id="e5f2d-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="e5f2d-107">**Type**</span></span>|<span data-ttu-id="e5f2d-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="e5f2d-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e5f2d-109">cmplEventID</span><span class="sxs-lookup"><span data-stu-id="e5f2d-109">cmplEventID</span></span>  <br/> |<span data-ttu-id="e5f2d-110">bigint, não nulo</span><span class="sxs-lookup"><span data-stu-id="e5f2d-110">bigint, not null</span></span>  <br/> |<span data-ttu-id="e5f2d-111">ID do evento.</span><span class="sxs-lookup"><span data-stu-id="e5f2d-111">Event ID.</span></span>  <br/> |
|<span data-ttu-id="e5f2d-112">entryDate</span><span class="sxs-lookup"><span data-stu-id="e5f2d-112">entryDate</span></span>  <br/> |<span data-ttu-id="e5f2d-113">smalldatetime, não nulo</span><span class="sxs-lookup"><span data-stu-id="e5f2d-113">smalldatetime, not null</span></span>  <br/> |<span data-ttu-id="e5f2d-114">Hora de inserção (pode está longe no futuro para cmplType = 9, pois a entrada é apenas um espaço reservado neste caso).</span><span class="sxs-lookup"><span data-stu-id="e5f2d-114">Time of insertion (may be far in the future for cmplType=9 because the entry is just a placeholder in that case).</span></span>  <br/> |
|<span data-ttu-id="e5f2d-115">cmplType</span><span class="sxs-lookup"><span data-stu-id="e5f2d-115">cmplType</span></span>  <br/> |<span data-ttu-id="e5f2d-116">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="e5f2d-116">int, not null</span></span>  <br/> | <span data-ttu-id="e5f2d-117">Tipo de evento de conformidade:</span><span class="sxs-lookup"><span data-stu-id="e5f2d-117">Type of compliance event:</span></span> <br/>  <span data-ttu-id="e5f2d-118">1: chat</span><span class="sxs-lookup"><span data-stu-id="e5f2d-118">1: Chat</span></span> <br/>  <span data-ttu-id="e5f2d-119">2: Chat persistente</span><span class="sxs-lookup"><span data-stu-id="e5f2d-119">2: Backchat</span></span> <br/>  <span data-ttu-id="e5f2d-120">3: download de arquivo</span><span class="sxs-lookup"><span data-stu-id="e5f2d-120">3: File download</span></span> <br/>  <span data-ttu-id="e5f2d-121">4: carregamento de arquivo</span><span class="sxs-lookup"><span data-stu-id="e5f2d-121">4: File upload</span></span> <br/>  <span data-ttu-id="e5f2d-122">9: transferência de arquivo provisional</span><span class="sxs-lookup"><span data-stu-id="e5f2d-122">9: Provisional file transfer</span></span> <br/>  <span data-ttu-id="e5f2d-123">10: exclusão (com substituição) de chat</span><span class="sxs-lookup"><span data-stu-id="e5f2d-123">10: Chat deletion (with replace)</span></span> <br/>  <span data-ttu-id="e5f2d-124">11: limpeza de chat</span><span class="sxs-lookup"><span data-stu-id="e5f2d-124">11: Chat purging</span></span> <br/> |
|<span data-ttu-id="e5f2d-125">cmplTime</span><span class="sxs-lookup"><span data-stu-id="e5f2d-125">cmplTime</span></span>  <br/> |<span data-ttu-id="e5f2d-126">bigint, não nulo</span><span class="sxs-lookup"><span data-stu-id="e5f2d-126">bigint, not null</span></span>  <br/> |<span data-ttu-id="e5f2d-127">Carimbo de hora para o evento.</span><span class="sxs-lookup"><span data-stu-id="e5f2d-127">Time stamp for the event.</span></span>  <br/> |
|<span data-ttu-id="e5f2d-128">cmplChannelUri</span><span class="sxs-lookup"><span data-stu-id="e5f2d-128">cmplChannelUri</span></span>  <br/> |<span data-ttu-id="e5f2d-129">nvarchar (255), não nulo</span><span class="sxs-lookup"><span data-stu-id="e5f2d-129">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="e5f2d-130">Identificador de recurso uniforme do canal (URI).</span><span class="sxs-lookup"><span data-stu-id="e5f2d-130">Channel Uniform Resource Identifier (URI).</span></span>  <br/> |
|<span data-ttu-id="e5f2d-131">cmplChatID</span><span class="sxs-lookup"><span data-stu-id="e5f2d-131">cmplChatID</span></span>  <br/> |<span data-ttu-id="e5f2d-132">bigint</span><span class="sxs-lookup"><span data-stu-id="e5f2d-132">bigint</span></span>  <br/> |<span data-ttu-id="e5f2d-133">Bate-papo ID (correspondendo à tabela de Chatid).</span><span class="sxs-lookup"><span data-stu-id="e5f2d-133">Chat ID (corresponding to tblChat.chatId table).</span></span>  <br/> |
|<span data-ttu-id="e5f2d-134">cmplUserID</span><span class="sxs-lookup"><span data-stu-id="e5f2d-134">cmplUserID</span></span>  <br/> |<span data-ttu-id="e5f2d-135">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="e5f2d-135">int, not null</span></span>  <br/> |<span data-ttu-id="e5f2d-136">ID principal do pôster (correspondendo à tabela Tblprincipal).</span><span class="sxs-lookup"><span data-stu-id="e5f2d-136">Principal ID of the poster (corresponding to tblPrincipal.prinID table).</span></span>  <br/> |
|<span data-ttu-id="e5f2d-137">cmplUserUri</span><span class="sxs-lookup"><span data-stu-id="e5f2d-137">cmplUserUri</span></span>  <br/> |<span data-ttu-id="e5f2d-138">nvarchar (255), não nulo</span><span class="sxs-lookup"><span data-stu-id="e5f2d-138">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="e5f2d-139">URI do usuário.</span><span class="sxs-lookup"><span data-stu-id="e5f2d-139">User URI.</span></span>  <br/> |
|<span data-ttu-id="e5f2d-140">cmplMessage</span><span class="sxs-lookup"><span data-stu-id="e5f2d-140">cmplMessage</span></span>  <br/> |<span data-ttu-id="e5f2d-141">nvarchar (máx.)</span><span class="sxs-lookup"><span data-stu-id="e5f2d-141">nvarchar (max)</span></span>  <br/> |<span data-ttu-id="e5f2d-142">Mensagem (codificação depende de cmplType).</span><span class="sxs-lookup"><span data-stu-id="e5f2d-142">Message (encoding depends on cmplType).</span></span>  <br/> |
   
<span data-ttu-id="e5f2d-143">**Chave**</span><span class="sxs-lookup"><span data-stu-id="e5f2d-143">**Key**</span></span>

|<span data-ttu-id="e5f2d-144">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="e5f2d-144">**Column**</span></span>|<span data-ttu-id="e5f2d-145">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="e5f2d-145">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e5f2d-146">cmplEventID</span><span class="sxs-lookup"><span data-stu-id="e5f2d-146">cmplEventID</span></span>  <br/> |<span data-ttu-id="e5f2d-147">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="e5f2d-147">Primary key.</span></span>  <br/> |
   

