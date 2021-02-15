---
title: Exibição de mídia
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
ms.assetid: 1a7b2e59-082e-4188-98ae-48ae9bd3494a
description: A exibição de mídia armazena informações sobre um tipo de mídia usado em uma sessão ponto a ponto. Uma sessão será representada por vários registros na tabela caso mais de um tipo de mídia seja usado. Essa exibição foi introduzida no Microsoft Lync Server 2013.
ms.openlocfilehash: 77c22246056a28cdb41a007ac0d7e2617fa00ad9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831781"
---
# <a name="media-view"></a><span data-ttu-id="d5cae-105">Exibição de mídia</span><span class="sxs-lookup"><span data-stu-id="d5cae-105">Media view</span></span>
 
<span data-ttu-id="d5cae-106">A exibição de mídia armazena informações sobre um tipo de mídia usado em uma sessão ponto a ponto.</span><span class="sxs-lookup"><span data-stu-id="d5cae-106">The Media view stores information about one media type used in a peer-to-peer session.</span></span> <span data-ttu-id="d5cae-107">Uma sessão será representada por vários registros na tabela caso mais de um tipo de mídia seja usado.</span><span class="sxs-lookup"><span data-stu-id="d5cae-107">One session would be represented by multiple records in the table, if more than one media type is used.</span></span> <span data-ttu-id="d5cae-108">Essa exibição foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d5cae-108">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d5cae-p103">A exibição de mídia não deve ser usada para calcular a duração de mídia para uma sessão. Essa exibição contém os detalhes de sinalização da troca de mídia em uma sessão. A troca de mídia é feita pela solicitação INVITE, e o StartTime indica o horário em que o INVITE foi enviado. O horário de convite não significa, necessariamente, o horário de início da mídia, pois a mídia só começa depois que a sessão tenha sido aceita.</span><span class="sxs-lookup"><span data-stu-id="d5cae-p103">The Media view should not be used to calculate the media duration for a session. This view contains the signaling details of media exchange in a session. Media exchange is done by the INVITE request, and StartTime indicates the time that the INVITE was sent out. The invite time does not necessarily mean the media start time, because media starts only after the session is accepted.</span></span> 
  
<span data-ttu-id="d5cae-112">O visualizador de mídia contém todas as colunas no [exibição SessionDetails,](sessiondetails-0.md) além das listadas abaixo.</span><span class="sxs-lookup"><span data-stu-id="d5cae-112">The Media view contains all of the columns in the [SessionDetails view](sessiondetails-0.md) in addition the ones listed below.</span></span>
  
|<span data-ttu-id="d5cae-113">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="d5cae-113">**Column**</span></span>|<span data-ttu-id="d5cae-114">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="d5cae-114">**Data Type**</span></span>|<span data-ttu-id="d5cae-115">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="d5cae-115">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d5cae-116">**Mídia**</span><span class="sxs-lookup"><span data-stu-id="d5cae-116">**Media**</span></span> <br/> |<span data-ttu-id="d5cae-117">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="d5cae-117">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="d5cae-118">Tipo de mídia.</span><span class="sxs-lookup"><span data-stu-id="d5cae-118">Media type.</span></span> <span data-ttu-id="d5cae-119">Consulte a [tabela MediaList](medialist.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="d5cae-119">See the [MediaList table](medialist.md) for more information.</span></span> <br/> |
|<span data-ttu-id="d5cae-120">**MediaStartTime**</span><span class="sxs-lookup"><span data-stu-id="d5cae-120">**MediaStartTime**</span></span> <br/> |<span data-ttu-id="d5cae-121">datetime</span><span class="sxs-lookup"><span data-stu-id="d5cae-121">datetime</span></span>  <br/> |<span data-ttu-id="d5cae-122">Horário em que a solicitação de mídia foi enviada.</span><span class="sxs-lookup"><span data-stu-id="d5cae-122">Time that a media request was sent out.</span></span>  <br/> |
|<span data-ttu-id="d5cae-123">**MediaEndTime**</span><span class="sxs-lookup"><span data-stu-id="d5cae-123">**MediaEndTime**</span></span> <br/> |<span data-ttu-id="d5cae-124">datetime</span><span class="sxs-lookup"><span data-stu-id="d5cae-124">datetime</span></span>  <br/> |<span data-ttu-id="d5cae-125">Horário de término da sessão.</span><span class="sxs-lookup"><span data-stu-id="d5cae-125">End time of the session.</span></span>  <br/> |
   

