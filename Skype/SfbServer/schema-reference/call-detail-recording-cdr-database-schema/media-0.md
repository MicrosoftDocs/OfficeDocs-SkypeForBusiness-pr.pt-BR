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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 1a7b2e59-082e-4188-98ae-48ae9bd3494a
description: O modo de exibição mídia armazena informações sobre um tipo de mídia usado em uma sessão ponto a ponto. Uma sessão seria representada por vários registros na tabela, se mais de um tipo de mídia for usado. Este modo de exibição foi apresentado no Microsoft Lync Server 2013.
ms.openlocfilehash: 26ef344b5fade02168fb8737fe00049e44e24892
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815049"
---
# <a name="media-view"></a><span data-ttu-id="038ea-105">Modo de exibição de mídia</span><span class="sxs-lookup"><span data-stu-id="038ea-105">Media view</span></span>
 
<span data-ttu-id="038ea-106">O modo de exibição mídia armazena informações sobre um tipo de mídia usado em uma sessão ponto a ponto.</span><span class="sxs-lookup"><span data-stu-id="038ea-106">The Media view stores information about one media type used in a peer-to-peer session.</span></span> <span data-ttu-id="038ea-107">Uma sessão seria representada por vários registros na tabela, se mais de um tipo de mídia for usado.</span><span class="sxs-lookup"><span data-stu-id="038ea-107">One session would be represented by multiple records in the table, if more than one media type is used.</span></span> <span data-ttu-id="038ea-108">Este modo de exibição foi apresentado no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="038ea-108">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="038ea-109">O modo de exibição de mídia não deve ser usado para calcular a duração da mídia de uma sessão.</span><span class="sxs-lookup"><span data-stu-id="038ea-109">The Media view should not be used to calculate the media duration for a session.</span></span> <span data-ttu-id="038ea-110">Este modo de exibição contém os detalhes de sinalização da troca de mídia em uma sessão.</span><span class="sxs-lookup"><span data-stu-id="038ea-110">This view contains the signaling details of media exchange in a session.</span></span> <span data-ttu-id="038ea-111">A troca de mídia é feita pela solicitação de convite e StartTime indica a hora em que o convite foi enviado. O tempo de convite não significa necessariamente a hora de início da mídia porque a mídia só inicia após a aceitação da sessão.</span><span class="sxs-lookup"><span data-stu-id="038ea-111">Media exchange is done by the INVITE request, and StartTime indicates the time that the INVITE was sent out. The invite time does not necessarily mean the media start time, because media starts only after the session is accepted.</span></span> 
  
<span data-ttu-id="038ea-112">O modo de exibição de mídia contém todas as colunas na [exibição SessionDetails](sessiondetails-0.md) além daquelas listadas abaixo.</span><span class="sxs-lookup"><span data-stu-id="038ea-112">The Media view contains all of the columns in the [SessionDetails view](sessiondetails-0.md) in addition the ones listed below.</span></span>
  
|<span data-ttu-id="038ea-113">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="038ea-113">**Column**</span></span>|<span data-ttu-id="038ea-114">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="038ea-114">**Data Type**</span></span>|<span data-ttu-id="038ea-115">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="038ea-115">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="038ea-116">**Media**</span><span class="sxs-lookup"><span data-stu-id="038ea-116">**Media**</span></span> <br/> |<span data-ttu-id="038ea-117">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="038ea-117">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="038ea-118">Tipo de mídia.</span><span class="sxs-lookup"><span data-stu-id="038ea-118">Media type.</span></span> <span data-ttu-id="038ea-119">Consulte a [tabela medialist](medialist.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="038ea-119">See the [MediaList table](medialist.md) for more information.</span></span> <br/> |
|<span data-ttu-id="038ea-120">**MediaStartTime**</span><span class="sxs-lookup"><span data-stu-id="038ea-120">**MediaStartTime**</span></span> <br/> |<span data-ttu-id="038ea-121">datetime</span><span class="sxs-lookup"><span data-stu-id="038ea-121">datetime</span></span>  <br/> |<span data-ttu-id="038ea-122">Tempo em que uma solicitação de mídia foi enviada.</span><span class="sxs-lookup"><span data-stu-id="038ea-122">Time that a media request was sent out.</span></span>  <br/> |
|<span data-ttu-id="038ea-123">**MediaEndTime**</span><span class="sxs-lookup"><span data-stu-id="038ea-123">**MediaEndTime**</span></span> <br/> |<span data-ttu-id="038ea-124">datetime</span><span class="sxs-lookup"><span data-stu-id="038ea-124">datetime</span></span>  <br/> |<span data-ttu-id="038ea-125">Hora de término da sessão.</span><span class="sxs-lookup"><span data-stu-id="038ea-125">End time of the session.</span></span>  <br/> |
   

