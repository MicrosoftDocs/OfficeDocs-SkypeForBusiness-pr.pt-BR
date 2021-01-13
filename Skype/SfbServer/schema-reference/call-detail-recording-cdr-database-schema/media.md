---
title: Tabela De mídia
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
ms.assetid: 1e1b427f-59b5-4564-bde5-1002a80439ee
description: Cada registro representa um tipo de mídia usado em uma sessão ponto a ponto. Uma sessão será representada por vários registros na tabela se mais de um tipo de mídia for usado.
ms.openlocfilehash: ce5b5a2b312307e608367279e4e871ed03063860
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49800101"
---
# <a name="media-table"></a><span data-ttu-id="b2a52-104">Tabela De mídia</span><span class="sxs-lookup"><span data-stu-id="b2a52-104">Media table</span></span>
 
<span data-ttu-id="b2a52-p102">Cada registro representa um tipo de mídia usado em uma sessão ponto a ponto. Uma sessão será representada por vários registros na tabela se mais de um tipo de mídia for usado.</span><span class="sxs-lookup"><span data-stu-id="b2a52-p102">Each record represents one media type used in a peer-to-peer session. One session would be represented by multiple records in the table, if more than one media type is used.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b2a52-p103">A tabela de Mídia não deve ser usada para calcular a duração da mídia de uma sessão. Esta tabela contém os detalhes de sinalização da troca de mídia em uma sessão. A troca de mídia é realizada pela solicitação INVITE e StartTime indica a hora que INVITE foi enviado. O horário do convite não necessariamente significa a hora inicial da mídia, porque a mídia começa apenas após o participante aceitar a sessão. O EndTime geralmente significa a hora final desta sessão.</span><span class="sxs-lookup"><span data-stu-id="b2a52-p103">The Media table should not be used to calculate the media duration for a session. This table contains the signaling details of media exchange in a session. Media exchange is done by the INVITE request, and StartTime indicates the time that the INVITE was sent out. The invite time does not necessarily mean the media start time, because media starts only after the sessionee accepts the session. The EndTime usually means the end time of this session.</span></span> 
  
|<span data-ttu-id="b2a52-111">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="b2a52-111">**Column**</span></span>|<span data-ttu-id="b2a52-112">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="b2a52-112">**Data Type**</span></span>|<span data-ttu-id="b2a52-113">**Chave/Índice**</span><span class="sxs-lookup"><span data-stu-id="b2a52-113">**Key/Index**</span></span>|<span data-ttu-id="b2a52-114">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="b2a52-114">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="b2a52-115">**SessionIdTime**</span><span class="sxs-lookup"><span data-stu-id="b2a52-115">**SessionIdTime**</span></span> <br/> |<span data-ttu-id="b2a52-116">datetime</span><span class="sxs-lookup"><span data-stu-id="b2a52-116">datetime</span></span>  <br/> |<span data-ttu-id="b2a52-117">Primário, Estrangeiro</span><span class="sxs-lookup"><span data-stu-id="b2a52-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="b2a52-118">Tempo da solicitação de sessão.</span><span class="sxs-lookup"><span data-stu-id="b2a52-118">Time of session request.</span></span> <span data-ttu-id="b2a52-119">Usado em conjunto com **SessionIdSeq** para identificar exclusivamente uma sessão.</span><span class="sxs-lookup"><span data-stu-id="b2a52-119">Used in conjunction with **SessionIdSeq** to uniquely identify a session.</span></span> <span data-ttu-id="b2a52-120">Consulte a [tabela Dialogs no Skype for Business Server 2015](dialogs.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="b2a52-120">See the [Dialogs table in Skype for Business Server 2015](dialogs.md) for more information.</span></span> <br/> |
|<span data-ttu-id="b2a52-121">**SessionIdSeq**</span><span class="sxs-lookup"><span data-stu-id="b2a52-121">**SessionIdSeq**</span></span> <br/> |<span data-ttu-id="b2a52-122">int</span><span class="sxs-lookup"><span data-stu-id="b2a52-122">int</span></span>  <br/> |<span data-ttu-id="b2a52-123">Primário, Estrangeiro</span><span class="sxs-lookup"><span data-stu-id="b2a52-123">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="b2a52-124">O número de ID para identificar a sessão.</span><span class="sxs-lookup"><span data-stu-id="b2a52-124">ID number to identify the session.</span></span> <span data-ttu-id="b2a52-125">Usado em conjunto com **SessionIdTime** para identificar exclusivamente uma sessão.</span><span class="sxs-lookup"><span data-stu-id="b2a52-125">Used in conjunction with **SessionIdTime** to uniquely identify a session.</span></span> <span data-ttu-id="b2a52-126">Consulte a [tabela Dialogs no Skype for Business Server 2015](dialogs.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="b2a52-126">See the [Dialogs table in Skype for Business Server 2015](dialogs.md) for more information.</span></span> <br/> |
|<span data-ttu-id="b2a52-127">**MediaId**</span><span class="sxs-lookup"><span data-stu-id="b2a52-127">**MediaId**</span></span> <br/> |<span data-ttu-id="b2a52-128">tinyint</span><span class="sxs-lookup"><span data-stu-id="b2a52-128">tinyint</span></span>  <br/> |<span data-ttu-id="b2a52-129">Primária, Estrangeira</span><span class="sxs-lookup"><span data-stu-id="b2a52-129">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="b2a52-130">Número exclusivo identificando este tipo de mídia.</span><span class="sxs-lookup"><span data-stu-id="b2a52-130">Unique number identifying this media type.</span></span> <span data-ttu-id="b2a52-131">Consulte a [tabela MediaList para](medialist.md) obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="b2a52-131">See the [MediaList table](medialist.md) for more information.</span></span> <br/> |
|<span data-ttu-id="b2a52-132">**StartTime**</span><span class="sxs-lookup"><span data-stu-id="b2a52-132">**StartTime**</span></span> <br/> |<span data-ttu-id="b2a52-133">datetime</span><span class="sxs-lookup"><span data-stu-id="b2a52-133">datetime</span></span>  <br/> |<span data-ttu-id="b2a52-134">Primário</span><span class="sxs-lookup"><span data-stu-id="b2a52-134">Primary</span></span>  <br/> |<span data-ttu-id="b2a52-p107">Este é o horário em que a solicitação de mídia foi enviada, não o horário de início de mídia real. O **StartTime** inclui a hora de configuração da sessão.</span><span class="sxs-lookup"><span data-stu-id="b2a52-p107">This is the time that a media request was sent out, not the real media start time. **StartTime** includes the session setup time. </span></span><br/> |
|<span data-ttu-id="b2a52-137">**EndTime**</span><span class="sxs-lookup"><span data-stu-id="b2a52-137">**EndTime**</span></span> <br/> |<span data-ttu-id="b2a52-138">datetime</span><span class="sxs-lookup"><span data-stu-id="b2a52-138">datetime</span></span>  <br/> ||<span data-ttu-id="b2a52-139">Este é o horário de término da sessão.</span><span class="sxs-lookup"><span data-stu-id="b2a52-139">This is the end time of the session.</span></span>  <br/> |
   

