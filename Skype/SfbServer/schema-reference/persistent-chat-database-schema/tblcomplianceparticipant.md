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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 5d7e0dea-74f7-46d1-badf-b94abc8f066d
description: tblComplianceParticipant contém os participantes atuais por canal e por servidor.
ms.openlocfilehash: 8f4b90cd7e8949451c2b6c1b9bc3cfabbab826e9
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814639"
---
# <a name="tblcomplianceparticipant"></a><span data-ttu-id="5c982-103">tblComplianceParticipant</span><span class="sxs-lookup"><span data-stu-id="5c982-103">tblComplianceParticipant</span></span>
 
<span data-ttu-id="5c982-104">tblComplianceParticipant contém os participantes atuais por canal e por servidor.</span><span class="sxs-lookup"><span data-stu-id="5c982-104">tblComplianceParticipant contains the current participants per channel and per server.</span></span>
  
<span data-ttu-id="5c982-105">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="5c982-105">**Columns**</span></span>

|<span data-ttu-id="5c982-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="5c982-106">**Column**</span></span>|<span data-ttu-id="5c982-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="5c982-107">**Type**</span></span>|<span data-ttu-id="5c982-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="5c982-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="5c982-109">channelUri</span><span class="sxs-lookup"><span data-stu-id="5c982-109">channelUri</span></span>  <br/> |<span data-ttu-id="5c982-110">nvarchar (255), NOT NULL</span><span class="sxs-lookup"><span data-stu-id="5c982-110">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="5c982-111">URI (Uniform Resource Identifier) do canal.</span><span class="sxs-lookup"><span data-stu-id="5c982-111">Channel Uniform Resource Identifier (URI).</span></span>  <br/> |
|<span data-ttu-id="5c982-112">ID</span><span class="sxs-lookup"><span data-stu-id="5c982-112">userId</span></span>  <br/> |<span data-ttu-id="5c982-113">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="5c982-113">int, not null</span></span>  <br/> |<span data-ttu-id="5c982-114">ID da entidade de segurança do participante (correspondente à tabela tblPrincipal. retoid).</span><span class="sxs-lookup"><span data-stu-id="5c982-114">Principal ID of the participant (corresponding to tblPrincipal.prinID table).</span></span>  <br/> |
|<span data-ttu-id="5c982-115">joinedAt</span><span class="sxs-lookup"><span data-stu-id="5c982-115">joinedAt</span></span>  <br/> |<span data-ttu-id="5c982-116">bigint, e não nulo</span><span class="sxs-lookup"><span data-stu-id="5c982-116">bigint, not null</span></span>  <br/> |<span data-ttu-id="5c982-117">Carimbo de data/hora do evento de associação.</span><span class="sxs-lookup"><span data-stu-id="5c982-117">Time stamp of the joining event.</span></span>  <br/> |
|<span data-ttu-id="5c982-118">partedAt</span><span class="sxs-lookup"><span data-stu-id="5c982-118">partedAt</span></span>  <br/> |<span data-ttu-id="5c982-119">bigint</span><span class="sxs-lookup"><span data-stu-id="5c982-119">bigint</span></span>  <br/> |<span data-ttu-id="5c982-120">NULL se o participante ainda estiver associado.</span><span class="sxs-lookup"><span data-stu-id="5c982-120">Null if participant is still joined.</span></span> <span data-ttu-id="5c982-121">O carimbo de data/hora do evento de persaiar de canal, se não for nulo.</span><span class="sxs-lookup"><span data-stu-id="5c982-121">The time stamp of the channel leaving event if not null.</span></span>  <br/> <span data-ttu-id="5c982-122">Essas entradas são eventualmente removidas quando todos os tradutores processam o evento.</span><span class="sxs-lookup"><span data-stu-id="5c982-122">These entries are eventually removed when all translators process the event.</span></span>  <br/> |
|<span data-ttu-id="5c982-123">userUri</span><span class="sxs-lookup"><span data-stu-id="5c982-123">userUri</span></span>  <br/> |<span data-ttu-id="5c982-124">nvarchar (255), NOT NULL</span><span class="sxs-lookup"><span data-stu-id="5c982-124">nvarchar(255), not null</span></span>  <br/> |<span data-ttu-id="5c982-125">URI de usuário.</span><span class="sxs-lookup"><span data-stu-id="5c982-125">User URI.</span></span>  <br/> |
|<span data-ttu-id="5c982-126">serverID</span><span class="sxs-lookup"><span data-stu-id="5c982-126">serverID</span></span>  <br/> |<span data-ttu-id="5c982-127">int</span><span class="sxs-lookup"><span data-stu-id="5c982-127">int</span></span>  <br/> |<span data-ttu-id="5c982-128">Identidade do servidor (como na tabela tblServerIdentity. ServerId).</span><span class="sxs-lookup"><span data-stu-id="5c982-128">Server identity (as in tblServerIdentity.serverID table).</span></span>  <br/> |
|<span data-ttu-id="5c982-129">Identificação</span><span class="sxs-lookup"><span data-stu-id="5c982-129">sessionId</span></span>  <br/> |<span data-ttu-id="5c982-130">bigint</span><span class="sxs-lookup"><span data-stu-id="5c982-130">bigint</span></span>  <br/> |<span data-ttu-id="5c982-131">Sessão do servidor.</span><span class="sxs-lookup"><span data-stu-id="5c982-131">Server session.</span></span> <span data-ttu-id="5c982-132">Esse é um número aleatório gerado cada vez que um serviço de chat é iniciado.</span><span class="sxs-lookup"><span data-stu-id="5c982-132">This is a random number generated each time a Chat service starts.</span></span> <span data-ttu-id="5c982-133">Ele é usado para diferenciar sessões para fins de identificação de participantes órfãos.</span><span class="sxs-lookup"><span data-stu-id="5c982-133">It is used to differentiate sessions for the purpose of identifying orphaned participants.</span></span>  <br/> |
   
<span data-ttu-id="5c982-134">**Chave**</span><span class="sxs-lookup"><span data-stu-id="5c982-134">**Key**</span></span>

|<span data-ttu-id="5c982-135">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="5c982-135">**Column**</span></span>|<span data-ttu-id="5c982-136">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="5c982-136">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="5c982-137">\<channelUri, userId, joinedAt\></span><span class="sxs-lookup"><span data-stu-id="5c982-137">\<channelUri, userId, joinedAt\></span></span>  <br/> |<span data-ttu-id="5c982-138">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="5c982-138">Primary key.</span></span>  <br/> |
   

