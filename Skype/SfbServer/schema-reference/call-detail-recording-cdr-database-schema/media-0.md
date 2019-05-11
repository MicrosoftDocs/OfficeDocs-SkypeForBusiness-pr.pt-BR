---
title: Modo de exibição de mídia
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1a7b2e59-082e-4188-98ae-48ae9bd3494a
description: O modo de exibição de mídia armazena informações sobre um tipo de mídia usado em uma sessão ponto a ponto. Uma sessão seria representada por vários registros na tabela, se mais de um tipo de mídia é usado. Este modo de exibição foi introduzido no Microsoft Lync Server 2013.
ms.openlocfilehash: 83caf609efae4e97961e7c62c3a1ed6c6004e8e8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930690"
---
# <a name="media-view"></a><span data-ttu-id="62acb-105">Modo de exibição de mídia</span><span class="sxs-lookup"><span data-stu-id="62acb-105">Media view</span></span>
 
<span data-ttu-id="62acb-106">O modo de exibição de mídia armazena informações sobre um tipo de mídia usado em uma sessão ponto a ponto.</span><span class="sxs-lookup"><span data-stu-id="62acb-106">The Media view stores information about one media type used in a peer-to-peer session.</span></span> <span data-ttu-id="62acb-107">Uma sessão seria representada por vários registros na tabela, se mais de um tipo de mídia é usado.</span><span class="sxs-lookup"><span data-stu-id="62acb-107">One session would be represented by multiple records in the table, if more than one media type is used.</span></span> <span data-ttu-id="62acb-108">Este modo de exibição foi introduzido no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="62acb-108">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="62acb-109">O modo de exibição de mídia não deve ser usado para calcular a duração de mídia para uma sessão.</span><span class="sxs-lookup"><span data-stu-id="62acb-109">The Media view should not be used to calculate the media duration for a session.</span></span> <span data-ttu-id="62acb-110">Este modo de exibição contém os detalhes de sinalização de troca de mídia em uma sessão.</span><span class="sxs-lookup"><span data-stu-id="62acb-110">This view contains the signaling details of media exchange in a session.</span></span> <span data-ttu-id="62acb-111">Troca de mídia é feita com a solicitação de convite e StartTime indica a hora em que o convite foi enviado. O tempo de convidar não necessariamente que a mídia Iniciar tempo, porque a mídia inicia somente depois que a sessão é aceito.</span><span class="sxs-lookup"><span data-stu-id="62acb-111">Media exchange is done by the INVITE request, and StartTime indicates the time that the INVITE was sent out. The invite time does not necessarily mean the media start time, because media starts only after the session is accepted.</span></span> 
  
<span data-ttu-id="62acb-112">O modo de exibição de mídia contém todas as colunas no [SessionDetails view](sessiondetails-0.md) além das listadas abaixo.</span><span class="sxs-lookup"><span data-stu-id="62acb-112">The Media view contains all of the columns in the [SessionDetails view](sessiondetails-0.md) in addition the ones listed below.</span></span>
  
|<span data-ttu-id="62acb-113">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="62acb-113">**Column**</span></span>|<span data-ttu-id="62acb-114">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="62acb-114">**Data Type**</span></span>|<span data-ttu-id="62acb-115">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="62acb-115">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="62acb-116">**Media**</span><span class="sxs-lookup"><span data-stu-id="62acb-116">**Media**</span></span> <br/> |<span data-ttu-id="62acb-117">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="62acb-117">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="62acb-118">Tipo de mídia.</span><span class="sxs-lookup"><span data-stu-id="62acb-118">Media type.</span></span> <span data-ttu-id="62acb-119">Consulte a [tabela MediaList](medialist.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="62acb-119">See the [MediaList table](medialist.md) for more information.</span></span> <br/> |
|<span data-ttu-id="62acb-120">**MediaStartTime**</span><span class="sxs-lookup"><span data-stu-id="62acb-120">**MediaStartTime**</span></span> <br/> |<span data-ttu-id="62acb-121">datetime</span><span class="sxs-lookup"><span data-stu-id="62acb-121">datetime</span></span>  <br/> |<span data-ttu-id="62acb-122">Hora em que a solicitação de mídia foi enviada.</span><span class="sxs-lookup"><span data-stu-id="62acb-122">Time that a media request was sent out.</span></span>  <br/> |
|<span data-ttu-id="62acb-123">**MediaEndTime**</span><span class="sxs-lookup"><span data-stu-id="62acb-123">**MediaEndTime**</span></span> <br/> |<span data-ttu-id="62acb-124">datetime</span><span class="sxs-lookup"><span data-stu-id="62acb-124">datetime</span></span>  <br/> |<span data-ttu-id="62acb-125">Hora de término da sessão.</span><span class="sxs-lookup"><span data-stu-id="62acb-125">End time of the session.</span></span>  <br/> |
   

