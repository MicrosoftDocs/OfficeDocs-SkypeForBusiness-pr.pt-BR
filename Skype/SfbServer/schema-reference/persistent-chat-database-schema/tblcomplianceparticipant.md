---
title: tblComplianceParticipant
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5d7e0dea-74f7-46d1-badf-b94abc8f066d
description: tblComplianceParticipant contém os participantes atuais por canal e por servidor.
ms.openlocfilehash: a3d18c4a78af2892a837e1105a435a3ce46ea14b
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30881413"
---
# <a name="tblcomplianceparticipant"></a><span data-ttu-id="1b2de-103">tblComplianceParticipant</span><span class="sxs-lookup"><span data-stu-id="1b2de-103">tblComplianceParticipant</span></span>
 
<span data-ttu-id="1b2de-104">tblComplianceParticipant contém os participantes atuais por canal e por servidor.</span><span class="sxs-lookup"><span data-stu-id="1b2de-104">tblComplianceParticipant contains the current participants per channel and per server.</span></span>
  
<span data-ttu-id="1b2de-105">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="1b2de-105">**Columns**</span></span>

|<span data-ttu-id="1b2de-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="1b2de-106">**Column**</span></span>|<span data-ttu-id="1b2de-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="1b2de-107">**Type**</span></span>|<span data-ttu-id="1b2de-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="1b2de-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="1b2de-109">channelUri</span><span class="sxs-lookup"><span data-stu-id="1b2de-109">channelUri</span></span>  <br/> |<span data-ttu-id="1b2de-110">nvarchar (255), não nulo</span><span class="sxs-lookup"><span data-stu-id="1b2de-110">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="1b2de-111">Identificador de recurso uniforme do canal (URI).</span><span class="sxs-lookup"><span data-stu-id="1b2de-111">Channel Uniform Resource Identifier (URI).</span></span>  <br/> |
|<span data-ttu-id="1b2de-112">userId</span><span class="sxs-lookup"><span data-stu-id="1b2de-112">userId</span></span>  <br/> |<span data-ttu-id="1b2de-113">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="1b2de-113">int, not null</span></span>  <br/> |<span data-ttu-id="1b2de-114">ID da entidade do participante (correspondente à tabela Tblprincipal).</span><span class="sxs-lookup"><span data-stu-id="1b2de-114">Principal ID of the participant (corresponding to tblPrincipal.prinID table).</span></span>  <br/> |
|<span data-ttu-id="1b2de-115">joinedAt</span><span class="sxs-lookup"><span data-stu-id="1b2de-115">joinedAt</span></span>  <br/> |<span data-ttu-id="1b2de-116">bigint, não nulo</span><span class="sxs-lookup"><span data-stu-id="1b2de-116">bigint, not null</span></span>  <br/> |<span data-ttu-id="1b2de-117">Carimbo de hora de ingresso no evento.</span><span class="sxs-lookup"><span data-stu-id="1b2de-117">Time stamp of the joining event.</span></span>  <br/> |
|<span data-ttu-id="1b2de-118">partedAt</span><span class="sxs-lookup"><span data-stu-id="1b2de-118">partedAt</span></span>  <br/> |<span data-ttu-id="1b2de-119">bigint</span><span class="sxs-lookup"><span data-stu-id="1b2de-119">bigint</span></span>  <br/> |<span data-ttu-id="1b2de-120">Nulo se participante ainda está vinculada.</span><span class="sxs-lookup"><span data-stu-id="1b2de-120">Null if participant is still joined.</span></span> <span data-ttu-id="1b2de-121">O carimbo de hora do canal deixando evento se não nulo.</span><span class="sxs-lookup"><span data-stu-id="1b2de-121">The time stamp of the channel leaving event if not null.</span></span>  <br/> <span data-ttu-id="1b2de-122">Essas entradas são eventualmente removidas quando todos os conversores processam o evento.</span><span class="sxs-lookup"><span data-stu-id="1b2de-122">These entries are eventually removed when all translators process the event.</span></span>  <br/> |
|<span data-ttu-id="1b2de-123">userUri</span><span class="sxs-lookup"><span data-stu-id="1b2de-123">userUri</span></span>  <br/> |<span data-ttu-id="1b2de-124">nvarchar (255), não nulo</span><span class="sxs-lookup"><span data-stu-id="1b2de-124">nvarchar(255), not null</span></span>  <br/> |<span data-ttu-id="1b2de-125">URI do usuário.</span><span class="sxs-lookup"><span data-stu-id="1b2de-125">User URI.</span></span>  <br/> |
|<span data-ttu-id="1b2de-126">serverID</span><span class="sxs-lookup"><span data-stu-id="1b2de-126">serverID</span></span>  <br/> |<span data-ttu-id="1b2de-127">int</span><span class="sxs-lookup"><span data-stu-id="1b2de-127">int</span></span>  <br/> |<span data-ttu-id="1b2de-128">Identidade do servidor (como em Tblserveridentity tabela).</span><span class="sxs-lookup"><span data-stu-id="1b2de-128">Server identity (as in tblServerIdentity.serverID table).</span></span>  <br/> |
|<span data-ttu-id="1b2de-129">sessionId</span><span class="sxs-lookup"><span data-stu-id="1b2de-129">sessionId</span></span>  <br/> |<span data-ttu-id="1b2de-130">bigint</span><span class="sxs-lookup"><span data-stu-id="1b2de-130">bigint</span></span>  <br/> |<span data-ttu-id="1b2de-131">Sessão de servidor.</span><span class="sxs-lookup"><span data-stu-id="1b2de-131">Server session.</span></span> <span data-ttu-id="1b2de-132">Este é um número aleatório gerado sempre que um serviço de bate-papo é iniciado.</span><span class="sxs-lookup"><span data-stu-id="1b2de-132">This is a random number generated each time a Chat service starts.</span></span> <span data-ttu-id="1b2de-133">Ele é usado para diferenciar sessões com o objetivo de identificar participantes órfãos.</span><span class="sxs-lookup"><span data-stu-id="1b2de-133">It is used to differentiate sessions for the purpose of identifying orphaned participants.</span></span>  <br/> |
   
<span data-ttu-id="1b2de-134">**Chave**</span><span class="sxs-lookup"><span data-stu-id="1b2de-134">**Key**</span></span>

|<span data-ttu-id="1b2de-135">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="1b2de-135">**Column**</span></span>|<span data-ttu-id="1b2de-136">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="1b2de-136">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1b2de-137">\<channelUri, userId, joinedAt\></span><span class="sxs-lookup"><span data-stu-id="1b2de-137">\<channelUri, userId, joinedAt\></span></span>  <br/> |<span data-ttu-id="1b2de-138">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="1b2de-138">Primary key.</span></span>  <br/> |
   

