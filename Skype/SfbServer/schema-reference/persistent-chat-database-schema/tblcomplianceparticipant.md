---
title: tblComplianceParticipant
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5d7e0dea-74f7-46d1-badf-b94abc8f066d
description: tblComplianceParticipant contém os participantes atuais por canal e por servidor.
ms.openlocfilehash: bf6913d8bcc11db1589169c4479cec4a0238825d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295458"
---
# <a name="tblcomplianceparticipant"></a><span data-ttu-id="4a06f-103">tblComplianceParticipant</span><span class="sxs-lookup"><span data-stu-id="4a06f-103">tblComplianceParticipant</span></span>
 
<span data-ttu-id="4a06f-104">tblComplianceParticipant contém os participantes atuais por canal e por servidor.</span><span class="sxs-lookup"><span data-stu-id="4a06f-104">tblComplianceParticipant contains the current participants per channel and per server.</span></span>
  
<span data-ttu-id="4a06f-105">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="4a06f-105">**Columns**</span></span>

|<span data-ttu-id="4a06f-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="4a06f-106">**Column**</span></span>|<span data-ttu-id="4a06f-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="4a06f-107">**Type**</span></span>|<span data-ttu-id="4a06f-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="4a06f-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="4a06f-109">channelUri</span><span class="sxs-lookup"><span data-stu-id="4a06f-109">channelUri</span></span>  <br/> |<span data-ttu-id="4a06f-110">nvarchar (255), NOT NULL</span><span class="sxs-lookup"><span data-stu-id="4a06f-110">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="4a06f-111">URI (Uniform Resource Identifier) do canal.</span><span class="sxs-lookup"><span data-stu-id="4a06f-111">Channel Uniform Resource Identifier (URI).</span></span>  <br/> |
|<span data-ttu-id="4a06f-112">ID</span><span class="sxs-lookup"><span data-stu-id="4a06f-112">userId</span></span>  <br/> |<span data-ttu-id="4a06f-113">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="4a06f-113">int, not null</span></span>  <br/> |<span data-ttu-id="4a06f-114">ID da entidade de segurança do participante (correspondente à tabela tblPrincipal. retoid).</span><span class="sxs-lookup"><span data-stu-id="4a06f-114">Principal ID of the participant (corresponding to tblPrincipal.prinID table).</span></span>  <br/> |
|<span data-ttu-id="4a06f-115">joinedAt</span><span class="sxs-lookup"><span data-stu-id="4a06f-115">joinedAt</span></span>  <br/> |<span data-ttu-id="4a06f-116">bigint, e não nulo</span><span class="sxs-lookup"><span data-stu-id="4a06f-116">bigint, not null</span></span>  <br/> |<span data-ttu-id="4a06f-117">Carimbo de data/hora do evento de associação.</span><span class="sxs-lookup"><span data-stu-id="4a06f-117">Time stamp of the joining event.</span></span>  <br/> |
|<span data-ttu-id="4a06f-118">partedAt</span><span class="sxs-lookup"><span data-stu-id="4a06f-118">partedAt</span></span>  <br/> |<span data-ttu-id="4a06f-119">bigint</span><span class="sxs-lookup"><span data-stu-id="4a06f-119">bigint</span></span>  <br/> |<span data-ttu-id="4a06f-120">NULL se o participante ainda estiver associado.</span><span class="sxs-lookup"><span data-stu-id="4a06f-120">Null if participant is still joined.</span></span> <span data-ttu-id="4a06f-121">O carimbo de data/hora do evento de persaiar de canal, se não for nulo.</span><span class="sxs-lookup"><span data-stu-id="4a06f-121">The time stamp of the channel leaving event if not null.</span></span>  <br/> <span data-ttu-id="4a06f-122">Essas entradas são eventualmente removidas quando todos os tradutores processam o evento.</span><span class="sxs-lookup"><span data-stu-id="4a06f-122">These entries are eventually removed when all translators process the event.</span></span>  <br/> |
|<span data-ttu-id="4a06f-123">userUri</span><span class="sxs-lookup"><span data-stu-id="4a06f-123">userUri</span></span>  <br/> |<span data-ttu-id="4a06f-124">nvarchar (255), NOT NULL</span><span class="sxs-lookup"><span data-stu-id="4a06f-124">nvarchar(255), not null</span></span>  <br/> |<span data-ttu-id="4a06f-125">URI de usuário.</span><span class="sxs-lookup"><span data-stu-id="4a06f-125">User URI.</span></span>  <br/> |
|<span data-ttu-id="4a06f-126">serverID</span><span class="sxs-lookup"><span data-stu-id="4a06f-126">serverID</span></span>  <br/> |<span data-ttu-id="4a06f-127">int</span><span class="sxs-lookup"><span data-stu-id="4a06f-127">int</span></span>  <br/> |<span data-ttu-id="4a06f-128">Identidade do servidor (como na tabela tblServerIdentity. ServerId).</span><span class="sxs-lookup"><span data-stu-id="4a06f-128">Server identity (as in tblServerIdentity.serverID table).</span></span>  <br/> |
|<span data-ttu-id="4a06f-129">Identificação</span><span class="sxs-lookup"><span data-stu-id="4a06f-129">sessionId</span></span>  <br/> |<span data-ttu-id="4a06f-130">bigint</span><span class="sxs-lookup"><span data-stu-id="4a06f-130">bigint</span></span>  <br/> |<span data-ttu-id="4a06f-131">Sessão do servidor.</span><span class="sxs-lookup"><span data-stu-id="4a06f-131">Server session.</span></span> <span data-ttu-id="4a06f-132">Esse é um número aleatório gerado cada vez que um serviço de chat é iniciado.</span><span class="sxs-lookup"><span data-stu-id="4a06f-132">This is a random number generated each time a Chat service starts.</span></span> <span data-ttu-id="4a06f-133">Ele é usado para diferenciar sessões para fins de identificação de participantes órfãos.</span><span class="sxs-lookup"><span data-stu-id="4a06f-133">It is used to differentiate sessions for the purpose of identifying orphaned participants.</span></span>  <br/> |
   
<span data-ttu-id="4a06f-134">**Chave**</span><span class="sxs-lookup"><span data-stu-id="4a06f-134">**Key**</span></span>

|<span data-ttu-id="4a06f-135">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="4a06f-135">**Column**</span></span>|<span data-ttu-id="4a06f-136">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="4a06f-136">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="4a06f-137">\<channelUri, userId, joinedAt\></span><span class="sxs-lookup"><span data-stu-id="4a06f-137">\<channelUri, userId, joinedAt\></span></span>  <br/> |<span data-ttu-id="4a06f-138">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="4a06f-138">Primary key.</span></span>  <br/> |
   

