---
title: Modo de exibição de mídia
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1a7b2e59-082e-4188-98ae-48ae9bd3494a
description: O modo de exibição mídia armazena informações sobre um tipo de mídia usado em uma sessão ponto a ponto. Uma sessão seria representada por vários registros na tabela, se mais de um tipo de mídia for usado. Este modo de exibição foi apresentado no Microsoft Lync Server 2013.
ms.openlocfilehash: 044a31381d4e1e48c465f7ee6de89acab10ab54e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295997"
---
# <a name="media-view"></a><span data-ttu-id="b0c82-105">Modo de exibição de mídia</span><span class="sxs-lookup"><span data-stu-id="b0c82-105">Media view</span></span>
 
<span data-ttu-id="b0c82-106">O modo de exibição mídia armazena informações sobre um tipo de mídia usado em uma sessão ponto a ponto.</span><span class="sxs-lookup"><span data-stu-id="b0c82-106">The Media view stores information about one media type used in a peer-to-peer session.</span></span> <span data-ttu-id="b0c82-107">Uma sessão seria representada por vários registros na tabela, se mais de um tipo de mídia for usado.</span><span class="sxs-lookup"><span data-stu-id="b0c82-107">One session would be represented by multiple records in the table, if more than one media type is used.</span></span> <span data-ttu-id="b0c82-108">Este modo de exibição foi apresentado no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b0c82-108">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b0c82-109">O modo de exibição de mídia não deve ser usado para calcular a duração da mídia de uma sessão.</span><span class="sxs-lookup"><span data-stu-id="b0c82-109">The Media view should not be used to calculate the media duration for a session.</span></span> <span data-ttu-id="b0c82-110">Este modo de exibição contém os detalhes de sinalização da troca de mídia em uma sessão.</span><span class="sxs-lookup"><span data-stu-id="b0c82-110">This view contains the signaling details of media exchange in a session.</span></span> <span data-ttu-id="b0c82-111">A troca de mídia é feita pela solicitação de convite e StartTime indica a hora em que o convite foi enviado. O tempo de convite não significa necessariamente a hora de início da mídia porque a mídia só inicia após a aceitação da sessão.</span><span class="sxs-lookup"><span data-stu-id="b0c82-111">Media exchange is done by the INVITE request, and StartTime indicates the time that the INVITE was sent out. The invite time does not necessarily mean the media start time, because media starts only after the session is accepted.</span></span> 
  
<span data-ttu-id="b0c82-112">O modo de exibição de mídia contém todas as colunas na [exibição SessionDetails](sessiondetails-0.md) além daquelas listadas abaixo.</span><span class="sxs-lookup"><span data-stu-id="b0c82-112">The Media view contains all of the columns in the [SessionDetails view](sessiondetails-0.md) in addition the ones listed below.</span></span>
  
|<span data-ttu-id="b0c82-113">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="b0c82-113">**Column**</span></span>|<span data-ttu-id="b0c82-114">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="b0c82-114">**Data Type**</span></span>|<span data-ttu-id="b0c82-115">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="b0c82-115">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b0c82-116">**Media**</span><span class="sxs-lookup"><span data-stu-id="b0c82-116">**Media**</span></span> <br/> |<span data-ttu-id="b0c82-117">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="b0c82-117">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="b0c82-118">Tipo de mídia.</span><span class="sxs-lookup"><span data-stu-id="b0c82-118">Media type.</span></span> <span data-ttu-id="b0c82-119">Consulte a [tabela medialist](medialist.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="b0c82-119">See the [MediaList table](medialist.md) for more information.</span></span> <br/> |
|<span data-ttu-id="b0c82-120">**MediaStartTime**</span><span class="sxs-lookup"><span data-stu-id="b0c82-120">**MediaStartTime**</span></span> <br/> |<span data-ttu-id="b0c82-121">datetime</span><span class="sxs-lookup"><span data-stu-id="b0c82-121">datetime</span></span>  <br/> |<span data-ttu-id="b0c82-122">Tempo em que uma solicitação de mídia foi enviada.</span><span class="sxs-lookup"><span data-stu-id="b0c82-122">Time that a media request was sent out.</span></span>  <br/> |
|<span data-ttu-id="b0c82-123">**MediaEndTime**</span><span class="sxs-lookup"><span data-stu-id="b0c82-123">**MediaEndTime**</span></span> <br/> |<span data-ttu-id="b0c82-124">datetime</span><span class="sxs-lookup"><span data-stu-id="b0c82-124">datetime</span></span>  <br/> |<span data-ttu-id="b0c82-125">Hora de término da sessão.</span><span class="sxs-lookup"><span data-stu-id="b0c82-125">End time of the session.</span></span>  <br/> |
   

