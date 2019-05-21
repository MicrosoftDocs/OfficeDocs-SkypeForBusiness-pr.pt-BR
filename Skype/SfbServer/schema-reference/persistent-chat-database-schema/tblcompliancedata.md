---
title: tblComplianceData
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 05b28f9b-4aba-4b69-ba8d-2ceeb6cbfaac
description: tblComplianceData contém os eventos de conformidade que ainda não foram processados pelo adaptador de conformidade.
ms.openlocfilehash: b505b3e05fb2aebba98804f5b7ad6a1d4d2da53e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295507"
---
# <a name="tblcompliancedata"></a><span data-ttu-id="79550-103">tblComplianceData</span><span class="sxs-lookup"><span data-stu-id="79550-103">tblComplianceData</span></span>
 
<span data-ttu-id="79550-104">tblComplianceData contém os eventos de conformidade que ainda não foram processados pelo adaptador de conformidade.</span><span class="sxs-lookup"><span data-stu-id="79550-104">tblComplianceData contains the compliance events that have not been processed by the compliance adapter yet.</span></span>
  
<span data-ttu-id="79550-105">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="79550-105">**Columns**</span></span>

|<span data-ttu-id="79550-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="79550-106">**Column**</span></span>|<span data-ttu-id="79550-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="79550-107">**Type**</span></span>|<span data-ttu-id="79550-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="79550-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="79550-109">cmplEventID</span><span class="sxs-lookup"><span data-stu-id="79550-109">cmplEventID</span></span>  <br/> |<span data-ttu-id="79550-110">bigint, e não nulo</span><span class="sxs-lookup"><span data-stu-id="79550-110">bigint, not null</span></span>  <br/> |<span data-ttu-id="79550-111">ID do evento.</span><span class="sxs-lookup"><span data-stu-id="79550-111">Event ID.</span></span>  <br/> |
|<span data-ttu-id="79550-112">entryDate</span><span class="sxs-lookup"><span data-stu-id="79550-112">entryDate</span></span>  <br/> |<span data-ttu-id="79550-113">smalldatetime, não nulo</span><span class="sxs-lookup"><span data-stu-id="79550-113">smalldatetime, not null</span></span>  <br/> |<span data-ttu-id="79550-114">Tempo de inserção (pode estar muito no futuro para cmplType = 9 porque a entrada é apenas um espaço reservado nesse caso).</span><span class="sxs-lookup"><span data-stu-id="79550-114">Time of insertion (may be far in the future for cmplType=9 because the entry is just a placeholder in that case).</span></span>  <br/> |
|<span data-ttu-id="79550-115">cmplType</span><span class="sxs-lookup"><span data-stu-id="79550-115">cmplType</span></span>  <br/> |<span data-ttu-id="79550-116">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="79550-116">int, not null</span></span>  <br/> | <span data-ttu-id="79550-117">Tipo de evento de conformidade:</span><span class="sxs-lookup"><span data-stu-id="79550-117">Type of compliance event:</span></span> <br/>  <span data-ttu-id="79550-118">1: chat</span><span class="sxs-lookup"><span data-stu-id="79550-118">1: Chat</span></span> <br/>  <span data-ttu-id="79550-119">2: backchat</span><span class="sxs-lookup"><span data-stu-id="79550-119">2: Backchat</span></span> <br/>  <span data-ttu-id="79550-120">3: download de arquivo</span><span class="sxs-lookup"><span data-stu-id="79550-120">3: File download</span></span> <br/>  <span data-ttu-id="79550-121">4: carregamento de arquivo</span><span class="sxs-lookup"><span data-stu-id="79550-121">4: File upload</span></span> <br/>  <span data-ttu-id="79550-122">9: transferência de arquivo provisório</span><span class="sxs-lookup"><span data-stu-id="79550-122">9: Provisional file transfer</span></span> <br/>  <span data-ttu-id="79550-123">10: exclusão de chat (com replace)</span><span class="sxs-lookup"><span data-stu-id="79550-123">10: Chat deletion (with replace)</span></span> <br/>  <span data-ttu-id="79550-124">11: limpeza de chat</span><span class="sxs-lookup"><span data-stu-id="79550-124">11: Chat purging</span></span> <br/> |
|<span data-ttu-id="79550-125">cmplTime</span><span class="sxs-lookup"><span data-stu-id="79550-125">cmplTime</span></span>  <br/> |<span data-ttu-id="79550-126">bigint, e não nulo</span><span class="sxs-lookup"><span data-stu-id="79550-126">bigint, not null</span></span>  <br/> |<span data-ttu-id="79550-127">Carimbo de data/hora do evento.</span><span class="sxs-lookup"><span data-stu-id="79550-127">Time stamp for the event.</span></span>  <br/> |
|<span data-ttu-id="79550-128">cmplChannelUri</span><span class="sxs-lookup"><span data-stu-id="79550-128">cmplChannelUri</span></span>  <br/> |<span data-ttu-id="79550-129">nvarchar (255), NOT NULL</span><span class="sxs-lookup"><span data-stu-id="79550-129">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="79550-130">URI (Uniform Resource Identifier) do canal.</span><span class="sxs-lookup"><span data-stu-id="79550-130">Channel Uniform Resource Identifier (URI).</span></span>  <br/> |
|<span data-ttu-id="79550-131">cmplChatID</span><span class="sxs-lookup"><span data-stu-id="79550-131">cmplChatID</span></span>  <br/> |<span data-ttu-id="79550-132">bigint</span><span class="sxs-lookup"><span data-stu-id="79550-132">bigint</span></span>  <br/> |<span data-ttu-id="79550-133">ID de chat (correspondente à tabela tblChat. chatid).</span><span class="sxs-lookup"><span data-stu-id="79550-133">Chat ID (corresponding to tblChat.chatId table).</span></span>  <br/> |
|<span data-ttu-id="79550-134">cmplUserID</span><span class="sxs-lookup"><span data-stu-id="79550-134">cmplUserID</span></span>  <br/> |<span data-ttu-id="79550-135">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="79550-135">int, not null</span></span>  <br/> |<span data-ttu-id="79550-136">ID da entidade de segurança do pôster (correspondente à tabela tblPrincipal. retoid).</span><span class="sxs-lookup"><span data-stu-id="79550-136">Principal ID of the poster (corresponding to tblPrincipal.prinID table).</span></span>  <br/> |
|<span data-ttu-id="79550-137">cmplUserUri</span><span class="sxs-lookup"><span data-stu-id="79550-137">cmplUserUri</span></span>  <br/> |<span data-ttu-id="79550-138">nvarchar (255), NOT NULL</span><span class="sxs-lookup"><span data-stu-id="79550-138">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="79550-139">URI de usuário.</span><span class="sxs-lookup"><span data-stu-id="79550-139">User URI.</span></span>  <br/> |
|<span data-ttu-id="79550-140">cmplMessage</span><span class="sxs-lookup"><span data-stu-id="79550-140">cmplMessage</span></span>  <br/> |<span data-ttu-id="79550-141">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="79550-141">nvarchar (max)</span></span>  <br/> |<span data-ttu-id="79550-142">Mensagem (a codificação depende do cmplType).</span><span class="sxs-lookup"><span data-stu-id="79550-142">Message (encoding depends on cmplType).</span></span>  <br/> |
   
<span data-ttu-id="79550-143">**Chave**</span><span class="sxs-lookup"><span data-stu-id="79550-143">**Key**</span></span>

|<span data-ttu-id="79550-144">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="79550-144">**Column**</span></span>|<span data-ttu-id="79550-145">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="79550-145">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="79550-146">cmplEventID</span><span class="sxs-lookup"><span data-stu-id="79550-146">cmplEventID</span></span>  <br/> |<span data-ttu-id="79550-147">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="79550-147">Primary key.</span></span>  <br/> |
   

