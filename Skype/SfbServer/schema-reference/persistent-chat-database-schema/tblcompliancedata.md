---
title: tblComplianceData
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 05b28f9b-4aba-4b69-ba8d-2ceeb6cbfaac
description: a tabela Compliancedata inclui eventos de conformidade que ainda não foram processados pelo adaptador de conformidade.
ms.openlocfilehash: 88319da90c1f3e03b6ca3e441259972f51d0bcf9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929928"
---
# <a name="tblcompliancedata"></a><span data-ttu-id="27eb4-103">tblComplianceData</span><span class="sxs-lookup"><span data-stu-id="27eb4-103">tblComplianceData</span></span>
 
<span data-ttu-id="27eb4-104">a tabela Compliancedata inclui eventos de conformidade que ainda não foram processados pelo adaptador de conformidade.</span><span class="sxs-lookup"><span data-stu-id="27eb4-104">tblComplianceData contains the compliance events that have not been processed by the compliance adapter yet.</span></span>
  
<span data-ttu-id="27eb4-105">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="27eb4-105">**Columns**</span></span>

|<span data-ttu-id="27eb4-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="27eb4-106">**Column**</span></span>|<span data-ttu-id="27eb4-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="27eb4-107">**Type**</span></span>|<span data-ttu-id="27eb4-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="27eb4-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="27eb4-109">cmplEventID</span><span class="sxs-lookup"><span data-stu-id="27eb4-109">cmplEventID</span></span>  <br/> |<span data-ttu-id="27eb4-110">bigint, não nulo</span><span class="sxs-lookup"><span data-stu-id="27eb4-110">bigint, not null</span></span>  <br/> |<span data-ttu-id="27eb4-111">ID do evento.</span><span class="sxs-lookup"><span data-stu-id="27eb4-111">Event ID.</span></span>  <br/> |
|<span data-ttu-id="27eb4-112">entryDate</span><span class="sxs-lookup"><span data-stu-id="27eb4-112">entryDate</span></span>  <br/> |<span data-ttu-id="27eb4-113">smalldatetime, não nulo</span><span class="sxs-lookup"><span data-stu-id="27eb4-113">smalldatetime, not null</span></span>  <br/> |<span data-ttu-id="27eb4-114">Hora de inserção (pode está longe no futuro para cmplType = 9, pois a entrada é apenas um espaço reservado neste caso).</span><span class="sxs-lookup"><span data-stu-id="27eb4-114">Time of insertion (may be far in the future for cmplType=9 because the entry is just a placeholder in that case).</span></span>  <br/> |
|<span data-ttu-id="27eb4-115">cmplType</span><span class="sxs-lookup"><span data-stu-id="27eb4-115">cmplType</span></span>  <br/> |<span data-ttu-id="27eb4-116">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="27eb4-116">int, not null</span></span>  <br/> | <span data-ttu-id="27eb4-117">Tipo de evento de conformidade:</span><span class="sxs-lookup"><span data-stu-id="27eb4-117">Type of compliance event:</span></span> <br/>  <span data-ttu-id="27eb4-118">1: chat</span><span class="sxs-lookup"><span data-stu-id="27eb4-118">1: Chat</span></span> <br/>  <span data-ttu-id="27eb4-119">2: Chat persistente</span><span class="sxs-lookup"><span data-stu-id="27eb4-119">2: Backchat</span></span> <br/>  <span data-ttu-id="27eb4-120">3: download de arquivo</span><span class="sxs-lookup"><span data-stu-id="27eb4-120">3: File download</span></span> <br/>  <span data-ttu-id="27eb4-121">4: carregamento de arquivo</span><span class="sxs-lookup"><span data-stu-id="27eb4-121">4: File upload</span></span> <br/>  <span data-ttu-id="27eb4-122">9: transferência de arquivo provisional</span><span class="sxs-lookup"><span data-stu-id="27eb4-122">9: Provisional file transfer</span></span> <br/>  <span data-ttu-id="27eb4-123">10: exclusão (com substituição) de chat</span><span class="sxs-lookup"><span data-stu-id="27eb4-123">10: Chat deletion (with replace)</span></span> <br/>  <span data-ttu-id="27eb4-124">11: limpeza de chat</span><span class="sxs-lookup"><span data-stu-id="27eb4-124">11: Chat purging</span></span> <br/> |
|<span data-ttu-id="27eb4-125">cmplTime</span><span class="sxs-lookup"><span data-stu-id="27eb4-125">cmplTime</span></span>  <br/> |<span data-ttu-id="27eb4-126">bigint, não nulo</span><span class="sxs-lookup"><span data-stu-id="27eb4-126">bigint, not null</span></span>  <br/> |<span data-ttu-id="27eb4-127">Carimbo de hora para o evento.</span><span class="sxs-lookup"><span data-stu-id="27eb4-127">Time stamp for the event.</span></span>  <br/> |
|<span data-ttu-id="27eb4-128">cmplChannelUri</span><span class="sxs-lookup"><span data-stu-id="27eb4-128">cmplChannelUri</span></span>  <br/> |<span data-ttu-id="27eb4-129">nvarchar (255), não nulo</span><span class="sxs-lookup"><span data-stu-id="27eb4-129">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="27eb4-130">Identificador de recurso uniforme do canal (URI).</span><span class="sxs-lookup"><span data-stu-id="27eb4-130">Channel Uniform Resource Identifier (URI).</span></span>  <br/> |
|<span data-ttu-id="27eb4-131">cmplChatID</span><span class="sxs-lookup"><span data-stu-id="27eb4-131">cmplChatID</span></span>  <br/> |<span data-ttu-id="27eb4-132">bigint</span><span class="sxs-lookup"><span data-stu-id="27eb4-132">bigint</span></span>  <br/> |<span data-ttu-id="27eb4-133">Bate-papo ID (correspondendo à tabela de Chatid).</span><span class="sxs-lookup"><span data-stu-id="27eb4-133">Chat ID (corresponding to tblChat.chatId table).</span></span>  <br/> |
|<span data-ttu-id="27eb4-134">cmplUserID</span><span class="sxs-lookup"><span data-stu-id="27eb4-134">cmplUserID</span></span>  <br/> |<span data-ttu-id="27eb4-135">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="27eb4-135">int, not null</span></span>  <br/> |<span data-ttu-id="27eb4-136">ID principal do pôster (correspondendo à tabela Tblprincipal).</span><span class="sxs-lookup"><span data-stu-id="27eb4-136">Principal ID of the poster (corresponding to tblPrincipal.prinID table).</span></span>  <br/> |
|<span data-ttu-id="27eb4-137">cmplUserUri</span><span class="sxs-lookup"><span data-stu-id="27eb4-137">cmplUserUri</span></span>  <br/> |<span data-ttu-id="27eb4-138">nvarchar (255), não nulo</span><span class="sxs-lookup"><span data-stu-id="27eb4-138">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="27eb4-139">URI do usuário.</span><span class="sxs-lookup"><span data-stu-id="27eb4-139">User URI.</span></span>  <br/> |
|<span data-ttu-id="27eb4-140">cmplMessage</span><span class="sxs-lookup"><span data-stu-id="27eb4-140">cmplMessage</span></span>  <br/> |<span data-ttu-id="27eb4-141">nvarchar (máx.)</span><span class="sxs-lookup"><span data-stu-id="27eb4-141">nvarchar (max)</span></span>  <br/> |<span data-ttu-id="27eb4-142">Mensagem (codificação depende de cmplType).</span><span class="sxs-lookup"><span data-stu-id="27eb4-142">Message (encoding depends on cmplType).</span></span>  <br/> |
   
<span data-ttu-id="27eb4-143">**Chave**</span><span class="sxs-lookup"><span data-stu-id="27eb4-143">**Key**</span></span>

|<span data-ttu-id="27eb4-144">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="27eb4-144">**Column**</span></span>|<span data-ttu-id="27eb4-145">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="27eb4-145">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="27eb4-146">cmplEventID</span><span class="sxs-lookup"><span data-stu-id="27eb4-146">cmplEventID</span></span>  <br/> |<span data-ttu-id="27eb4-147">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="27eb4-147">Primary key.</span></span>  <br/> |
   

