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
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212948"
---
# <a name="tblcomplianceparticipant"></a><span data-ttu-id="3c24b-103">tblComplianceParticipant</span><span class="sxs-lookup"><span data-stu-id="3c24b-103">tblComplianceParticipant</span></span>
 
<span data-ttu-id="3c24b-104">tblComplianceParticipant contém os participantes atuais por canal e por servidor.</span><span class="sxs-lookup"><span data-stu-id="3c24b-104">tblComplianceParticipant contains the current participants per channel and per server.</span></span>
  
<span data-ttu-id="3c24b-105">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="3c24b-105">**Columns**</span></span>

|<span data-ttu-id="3c24b-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="3c24b-106">**Column**</span></span>|<span data-ttu-id="3c24b-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="3c24b-107">**Type**</span></span>|<span data-ttu-id="3c24b-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="3c24b-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="3c24b-109">channelUri</span><span class="sxs-lookup"><span data-stu-id="3c24b-109">channelUri</span></span>  <br/> |<span data-ttu-id="3c24b-110">nvarchar (255), não nulo</span><span class="sxs-lookup"><span data-stu-id="3c24b-110">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="3c24b-111">Identificador de recurso uniforme do canal (URI).</span><span class="sxs-lookup"><span data-stu-id="3c24b-111">Channel Uniform Resource Identifier (URI).</span></span>  <br/> |
|<span data-ttu-id="3c24b-112">userId</span><span class="sxs-lookup"><span data-stu-id="3c24b-112">userId</span></span>  <br/> |<span data-ttu-id="3c24b-113">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="3c24b-113">int, not null</span></span>  <br/> |<span data-ttu-id="3c24b-114">ID da entidade do participante (correspondente à tabela Tblprincipal).</span><span class="sxs-lookup"><span data-stu-id="3c24b-114">Principal ID of the participant (corresponding to tblPrincipal.prinID table).</span></span>  <br/> |
|<span data-ttu-id="3c24b-115">joinedAt</span><span class="sxs-lookup"><span data-stu-id="3c24b-115">joinedAt</span></span>  <br/> |<span data-ttu-id="3c24b-116">bigint, não nulo</span><span class="sxs-lookup"><span data-stu-id="3c24b-116">bigint, not null</span></span>  <br/> |<span data-ttu-id="3c24b-117">Carimbo de hora de ingresso no evento.</span><span class="sxs-lookup"><span data-stu-id="3c24b-117">Time stamp of the joining event.</span></span>  <br/> |
|<span data-ttu-id="3c24b-118">partedAt</span><span class="sxs-lookup"><span data-stu-id="3c24b-118">partedAt</span></span>  <br/> |<span data-ttu-id="3c24b-119">bigint</span><span class="sxs-lookup"><span data-stu-id="3c24b-119">bigint</span></span>  <br/> |<span data-ttu-id="3c24b-120">Nulo se participante ainda está vinculada.</span><span class="sxs-lookup"><span data-stu-id="3c24b-120">Null if participant is still joined.</span></span> <span data-ttu-id="3c24b-121">O carimbo de hora do canal deixando evento se não nulo.</span><span class="sxs-lookup"><span data-stu-id="3c24b-121">The time stamp of the channel leaving event if not null.</span></span>  <br/> <span data-ttu-id="3c24b-122">Essas entradas são eventualmente removidas quando todos os conversores processam o evento.</span><span class="sxs-lookup"><span data-stu-id="3c24b-122">These entries are eventually removed when all translators process the event.</span></span>  <br/> |
|<span data-ttu-id="3c24b-123">userUri</span><span class="sxs-lookup"><span data-stu-id="3c24b-123">userUri</span></span>  <br/> |<span data-ttu-id="3c24b-124">nvarchar (255), não nulo</span><span class="sxs-lookup"><span data-stu-id="3c24b-124">nvarchar(255), not null</span></span>  <br/> |<span data-ttu-id="3c24b-125">URI do usuário.</span><span class="sxs-lookup"><span data-stu-id="3c24b-125">User URI.</span></span>  <br/> |
|<span data-ttu-id="3c24b-126">serverID</span><span class="sxs-lookup"><span data-stu-id="3c24b-126">serverID</span></span>  <br/> |<span data-ttu-id="3c24b-127">int</span><span class="sxs-lookup"><span data-stu-id="3c24b-127">int</span></span>  <br/> |<span data-ttu-id="3c24b-128">Identidade do servidor (como em Tblserveridentity tabela).</span><span class="sxs-lookup"><span data-stu-id="3c24b-128">Server identity (as in tblServerIdentity.serverID table).</span></span>  <br/> |
|<span data-ttu-id="3c24b-129">sessionId</span><span class="sxs-lookup"><span data-stu-id="3c24b-129">sessionId</span></span>  <br/> |<span data-ttu-id="3c24b-130">bigint</span><span class="sxs-lookup"><span data-stu-id="3c24b-130">bigint</span></span>  <br/> |<span data-ttu-id="3c24b-131">Sessão de servidor.</span><span class="sxs-lookup"><span data-stu-id="3c24b-131">Server session.</span></span> <span data-ttu-id="3c24b-132">Este é um número aleatório gerado sempre que um serviço de bate-papo é iniciado.</span><span class="sxs-lookup"><span data-stu-id="3c24b-132">This is a random number generated each time a Chat service starts.</span></span> <span data-ttu-id="3c24b-133">Ele é usado para diferenciar sessões com o objetivo de identificar participantes órfãos.</span><span class="sxs-lookup"><span data-stu-id="3c24b-133">It is used to differentiate sessions for the purpose of identifying orphaned participants.</span></span>  <br/> |
   
<span data-ttu-id="3c24b-134">**Chave**</span><span class="sxs-lookup"><span data-stu-id="3c24b-134">**Key**</span></span>

|<span data-ttu-id="3c24b-135">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="3c24b-135">**Column**</span></span>|<span data-ttu-id="3c24b-136">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="3c24b-136">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="3c24b-137">\<channelUri, userId, joinedAt\></span><span class="sxs-lookup"><span data-stu-id="3c24b-137">\<channelUri, userId, joinedAt\></span></span>  <br/> |<span data-ttu-id="3c24b-138">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="3c24b-138">Primary key.</span></span>  <br/> |
   

