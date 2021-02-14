---
title: tblComplianceParticipant
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
ms.assetid: 5d7e0dea-74f7-46d1-badf-b94abc8f066d
description: tblComplianceParticipant contém os participantes atuais por canal e por servidor.
ms.openlocfilehash: c6aae3c1e7b13456708034512c6b68d67d6d1f92
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809741"
---
# <a name="tblcomplianceparticipant"></a><span data-ttu-id="2a2aa-103">tblComplianceParticipant</span><span class="sxs-lookup"><span data-stu-id="2a2aa-103">tblComplianceParticipant</span></span>
 
<span data-ttu-id="2a2aa-104">tblComplianceParticipant contém os participantes atuais por canal e por servidor.</span><span class="sxs-lookup"><span data-stu-id="2a2aa-104">tblComplianceParticipant contains the current participants per channel and per server.</span></span>
  
<span data-ttu-id="2a2aa-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="2a2aa-105">**Columns**</span></span>

|<span data-ttu-id="2a2aa-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="2a2aa-106">**Column**</span></span>|<span data-ttu-id="2a2aa-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="2a2aa-107">**Type**</span></span>|<span data-ttu-id="2a2aa-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="2a2aa-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="2a2aa-109">channelUri</span><span class="sxs-lookup"><span data-stu-id="2a2aa-109">channelUri</span></span>  <br/> |<span data-ttu-id="2a2aa-110">nvarchar (255), não nulo</span><span class="sxs-lookup"><span data-stu-id="2a2aa-110">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="2a2aa-111">Identificador de Recurso Uniforme do Canal (URI).</span><span class="sxs-lookup"><span data-stu-id="2a2aa-111">Channel Uniform Resource Identifier (URI).</span></span>  <br/> |
|<span data-ttu-id="2a2aa-112">userId</span><span class="sxs-lookup"><span data-stu-id="2a2aa-112">userId</span></span>  <br/> |<span data-ttu-id="2a2aa-113">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="2a2aa-113">int, not null</span></span>  <br/> |<span data-ttu-id="2a2aa-114">ID da entidade do participante (correspondente à tabela tblPrincipal.prinID).</span><span class="sxs-lookup"><span data-stu-id="2a2aa-114">Principal ID of the participant (corresponding to tblPrincipal.prinID table).</span></span>  <br/> |
|<span data-ttu-id="2a2aa-115">joinedAt</span><span class="sxs-lookup"><span data-stu-id="2a2aa-115">joinedAt</span></span>  <br/> |<span data-ttu-id="2a2aa-116">bigint, não nulo</span><span class="sxs-lookup"><span data-stu-id="2a2aa-116">bigint, not null</span></span>  <br/> |<span data-ttu-id="2a2aa-117">Carimbo de data e hora de ingresso no evento.</span><span class="sxs-lookup"><span data-stu-id="2a2aa-117">Time stamp of the joining event.</span></span>  <br/> |
|<span data-ttu-id="2a2aa-118">partedAt</span><span class="sxs-lookup"><span data-stu-id="2a2aa-118">partedAt</span></span>  <br/> |<span data-ttu-id="2a2aa-119">bigint</span><span class="sxs-lookup"><span data-stu-id="2a2aa-119">bigint</span></span>  <br/> |<span data-ttu-id="2a2aa-p101">Nulo se o participante ainda estiver ingressado. O carimbo de data e hora de quando o canal deixa o evento se não for nulo.</span><span class="sxs-lookup"><span data-stu-id="2a2aa-p101">Null if participant is still joined. The time stamp of the channel leaving event if not null.</span></span>  <br/> <span data-ttu-id="2a2aa-122">Essas entradas são eventualmente removidas quando todos os conversores processam o evento.</span><span class="sxs-lookup"><span data-stu-id="2a2aa-122">These entries are eventually removed when all translators process the event.</span></span>  <br/> |
|<span data-ttu-id="2a2aa-123">userUri</span><span class="sxs-lookup"><span data-stu-id="2a2aa-123">userUri</span></span>  <br/> |<span data-ttu-id="2a2aa-124">nvarchar (255), não nulo</span><span class="sxs-lookup"><span data-stu-id="2a2aa-124">nvarchar(255), not null</span></span>  <br/> |<span data-ttu-id="2a2aa-125">URI do Usuário.</span><span class="sxs-lookup"><span data-stu-id="2a2aa-125">User URI.</span></span>  <br/> |
|<span data-ttu-id="2a2aa-126">serverID</span><span class="sxs-lookup"><span data-stu-id="2a2aa-126">serverID</span></span>  <br/> |<span data-ttu-id="2a2aa-127">int</span><span class="sxs-lookup"><span data-stu-id="2a2aa-127">int</span></span>  <br/> |<span data-ttu-id="2a2aa-128">Identidade do servidor (como na tabela tblServerIdentity.serverID).</span><span class="sxs-lookup"><span data-stu-id="2a2aa-128">Server identity (as in tblServerIdentity.serverID table).</span></span>  <br/> |
|<span data-ttu-id="2a2aa-129">sessionId</span><span class="sxs-lookup"><span data-stu-id="2a2aa-129">sessionId</span></span>  <br/> |<span data-ttu-id="2a2aa-130">bigint</span><span class="sxs-lookup"><span data-stu-id="2a2aa-130">bigint</span></span>  <br/> |<span data-ttu-id="2a2aa-p102">Sessão do servidor. Este é um número aleatório gerado sempre que um serviço de chat é iniciado. Ele é usado para diferenciar as sessões a fim de identificar os participantes órfãos.</span><span class="sxs-lookup"><span data-stu-id="2a2aa-p102">Server session. This is a random number generated each time a Chat service starts. It is used to differentiate sessions for the purpose of identifying orphaned participants.</span></span>  <br/> |
   
<span data-ttu-id="2a2aa-134">**Chave**</span><span class="sxs-lookup"><span data-stu-id="2a2aa-134">**Key**</span></span>

|<span data-ttu-id="2a2aa-135">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="2a2aa-135">**Column**</span></span>|<span data-ttu-id="2a2aa-136">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="2a2aa-136">**Description**</span></span>|
|:-----|:-----|
|\<channelUri, userId, joinedAt\>  <br/> |<span data-ttu-id="2a2aa-137">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="2a2aa-137">Primary key.</span></span>  <br/> |
   

