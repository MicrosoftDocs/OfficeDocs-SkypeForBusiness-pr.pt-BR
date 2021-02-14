---
title: tblComplianceData
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
ms.assetid: 05b28f9b-4aba-4b69-ba8d-2ceeb6cbfaac
description: A tabela ComplianceData inclui eventos de conformidade que ainda não foram processados pelo adaptador de conformidade
ms.openlocfilehash: e4ceda662b2f601660c144319a4231cebeea39ad
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809851"
---
# <a name="tblcompliancedata"></a><span data-ttu-id="7f3b9-103">tblComplianceData</span><span class="sxs-lookup"><span data-stu-id="7f3b9-103">tblComplianceData</span></span>
 
<span data-ttu-id="7f3b9-104">A tabela ComplianceData inclui eventos de conformidade que ainda não foram processados pelo adaptador de conformidade</span><span class="sxs-lookup"><span data-stu-id="7f3b9-104">tblComplianceData contains the compliance events that have not been processed by the compliance adapter yet.</span></span>
  
<span data-ttu-id="7f3b9-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="7f3b9-105">**Columns**</span></span>

|<span data-ttu-id="7f3b9-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="7f3b9-106">**Column**</span></span>|<span data-ttu-id="7f3b9-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="7f3b9-107">**Type**</span></span>|<span data-ttu-id="7f3b9-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="7f3b9-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="7f3b9-109">cmplEventID</span><span class="sxs-lookup"><span data-stu-id="7f3b9-109">cmplEventID</span></span>  <br/> |<span data-ttu-id="7f3b9-110">bigint, não nulo</span><span class="sxs-lookup"><span data-stu-id="7f3b9-110">bigint, not null</span></span>  <br/> |<span data-ttu-id="7f3b9-111">ID do evento.</span><span class="sxs-lookup"><span data-stu-id="7f3b9-111">Event ID.</span></span>  <br/> |
|<span data-ttu-id="7f3b9-112">entryDate</span><span class="sxs-lookup"><span data-stu-id="7f3b9-112">entryDate</span></span>  <br/> |<span data-ttu-id="7f3b9-113">smalldatetime, não nulo</span><span class="sxs-lookup"><span data-stu-id="7f3b9-113">smalldatetime, not null</span></span>  <br/> |<span data-ttu-id="7f3b9-114">Hora de inserção (pode está longe no futuro para cmplType=9, pois a entrada é apenas um espaço reservado neste caso).</span><span class="sxs-lookup"><span data-stu-id="7f3b9-114">Time of insertion (may be far in the future for cmplType=9 because the entry is just a placeholder in that case).</span></span>  <br/> |
|<span data-ttu-id="7f3b9-115">cmplType</span><span class="sxs-lookup"><span data-stu-id="7f3b9-115">cmplType</span></span>  <br/> |<span data-ttu-id="7f3b9-116">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="7f3b9-116">int, not null</span></span>  <br/> | <span data-ttu-id="7f3b9-117">Tipo de evento de conformidade:</span><span class="sxs-lookup"><span data-stu-id="7f3b9-117">Type of compliance event:</span></span> <br/>  <span data-ttu-id="7f3b9-118">1: Chat</span><span class="sxs-lookup"><span data-stu-id="7f3b9-118">1: Chat</span></span> <br/>  <span data-ttu-id="7f3b9-119">2: Backchat</span><span class="sxs-lookup"><span data-stu-id="7f3b9-119">2: Backchat</span></span> <br/>  <span data-ttu-id="7f3b9-120">3: Download de arquivo</span><span class="sxs-lookup"><span data-stu-id="7f3b9-120">3: File download</span></span> <br/>  <span data-ttu-id="7f3b9-121">4: Carregamento de arquivo</span><span class="sxs-lookup"><span data-stu-id="7f3b9-121">4: File upload</span></span> <br/>  <span data-ttu-id="7f3b9-122">9: Transferência de arquivo provisional</span><span class="sxs-lookup"><span data-stu-id="7f3b9-122">9: Provisional file transfer</span></span> <br/>  <span data-ttu-id="7f3b9-123">10: Exclusão de chat (com substituição)</span><span class="sxs-lookup"><span data-stu-id="7f3b9-123">10: Chat deletion (with replace)</span></span> <br/>  <span data-ttu-id="7f3b9-124">11: Limpeza de chat</span><span class="sxs-lookup"><span data-stu-id="7f3b9-124">11: Chat purging</span></span> <br/> |
|<span data-ttu-id="7f3b9-125">cmplTime</span><span class="sxs-lookup"><span data-stu-id="7f3b9-125">cmplTime</span></span>  <br/> |<span data-ttu-id="7f3b9-126">bigint, não nulo</span><span class="sxs-lookup"><span data-stu-id="7f3b9-126">bigint, not null</span></span>  <br/> |<span data-ttu-id="7f3b9-127">Carimbo de data/hora para o evento.</span><span class="sxs-lookup"><span data-stu-id="7f3b9-127">Time stamp for the event.</span></span>  <br/> |
|<span data-ttu-id="7f3b9-128">cmplChannelUri</span><span class="sxs-lookup"><span data-stu-id="7f3b9-128">cmplChannelUri</span></span>  <br/> |<span data-ttu-id="7f3b9-129">nvarchar (255), não nulo</span><span class="sxs-lookup"><span data-stu-id="7f3b9-129">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="7f3b9-130">Canal do Identificador de Recurso Uniforme (URI).</span><span class="sxs-lookup"><span data-stu-id="7f3b9-130">Channel Uniform Resource Identifier (URI).</span></span>  <br/> |
|<span data-ttu-id="7f3b9-131">cmplChatID</span><span class="sxs-lookup"><span data-stu-id="7f3b9-131">cmplChatID</span></span>  <br/> |<span data-ttu-id="7f3b9-132">bigint</span><span class="sxs-lookup"><span data-stu-id="7f3b9-132">bigint</span></span>  <br/> |<span data-ttu-id="7f3b9-133">ID do chat (correspondendo à tabela do Chat.chatId).</span><span class="sxs-lookup"><span data-stu-id="7f3b9-133">Chat ID (corresponding to tblChat.chatId table).</span></span>  <br/> |
|<span data-ttu-id="7f3b9-134">cmplUserID</span><span class="sxs-lookup"><span data-stu-id="7f3b9-134">cmplUserID</span></span>  <br/> |<span data-ttu-id="7f3b9-135">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="7f3b9-135">int, not null</span></span>  <br/> |<span data-ttu-id="7f3b9-136">ID principal do pôster (correspondendo à tabela do Principal.prinID).</span><span class="sxs-lookup"><span data-stu-id="7f3b9-136">Principal ID of the poster (corresponding to tblPrincipal.prinID table).</span></span>  <br/> |
|<span data-ttu-id="7f3b9-137">cmplUserUri</span><span class="sxs-lookup"><span data-stu-id="7f3b9-137">cmplUserUri</span></span>  <br/> |<span data-ttu-id="7f3b9-138">nvarchar (255), não nulo</span><span class="sxs-lookup"><span data-stu-id="7f3b9-138">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="7f3b9-139">URI do usuário.</span><span class="sxs-lookup"><span data-stu-id="7f3b9-139">User URI.</span></span>  <br/> |
|<span data-ttu-id="7f3b9-140">cmplMessage</span><span class="sxs-lookup"><span data-stu-id="7f3b9-140">cmplMessage</span></span>  <br/> |<span data-ttu-id="7f3b9-141">nvarchar (máx)</span><span class="sxs-lookup"><span data-stu-id="7f3b9-141">nvarchar (max)</span></span>  <br/> |<span data-ttu-id="7f3b9-142">Mensagem (codificação depende de cmplType).</span><span class="sxs-lookup"><span data-stu-id="7f3b9-142">Message (encoding depends on cmplType).</span></span>  <br/> |
   
<span data-ttu-id="7f3b9-143">**Chave**</span><span class="sxs-lookup"><span data-stu-id="7f3b9-143">**Key**</span></span>

|<span data-ttu-id="7f3b9-144">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="7f3b9-144">**Column**</span></span>|<span data-ttu-id="7f3b9-145">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="7f3b9-145">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="7f3b9-146">cmplEventID</span><span class="sxs-lookup"><span data-stu-id="7f3b9-146">cmplEventID</span></span>  <br/> |<span data-ttu-id="7f3b9-147">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="7f3b9-147">Primary key.</span></span>  <br/> |
   

