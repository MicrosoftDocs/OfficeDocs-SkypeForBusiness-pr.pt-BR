---
title: Tabela Conference
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 2a2c327c-4719-42dc-a3bb-6dbc0864d9af
description: A tabela de conferências é uma tabela de suporte. Cada registro representa uma reunião ou sessão ponto a ponto.
ms.openlocfilehash: 95e08861adaca2e76144f35037626e7b03afd962
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41810299"
---
# <a name="conference-table"></a><span data-ttu-id="b3bbc-104">Tabela Conference</span><span class="sxs-lookup"><span data-stu-id="b3bbc-104">Conference table</span></span>
 
<span data-ttu-id="b3bbc-105">A tabela de conferências é uma tabela de suporte.</span><span class="sxs-lookup"><span data-stu-id="b3bbc-105">The Conference table is a supporting table.</span></span> <span data-ttu-id="b3bbc-106">Cada registro representa uma reunião ou sessão ponto a ponto.</span><span class="sxs-lookup"><span data-stu-id="b3bbc-106">Each record represents one conference or peer-to-peer session.</span></span>
  
|<span data-ttu-id="b3bbc-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="b3bbc-107">**Column**</span></span>|<span data-ttu-id="b3bbc-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="b3bbc-108">**Data Type**</span></span>|<span data-ttu-id="b3bbc-109">**Chave/índice**</span><span class="sxs-lookup"><span data-stu-id="b3bbc-109">**Key/Index**</span></span>|<span data-ttu-id="b3bbc-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="b3bbc-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="b3bbc-111">**ConferenceKey**</span><span class="sxs-lookup"><span data-stu-id="b3bbc-111">**ConferenceKey**</span></span> <br/> |<span data-ttu-id="b3bbc-112">int</span><span class="sxs-lookup"><span data-stu-id="b3bbc-112">int</span></span>  <br/> |<span data-ttu-id="b3bbc-113">Primária</span><span class="sxs-lookup"><span data-stu-id="b3bbc-113">Primary</span></span>  <br/> |<span data-ttu-id="b3bbc-114">Número exclusivo que identifica esse registro de conferência.</span><span class="sxs-lookup"><span data-stu-id="b3bbc-114">Unique number identifying this conference record.</span></span>  <br/> |
|<span data-ttu-id="b3bbc-115">**ConfURI**</span><span class="sxs-lookup"><span data-stu-id="b3bbc-115">**ConfURI**</span></span> <br/> |<span data-ttu-id="b3bbc-116">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="b3bbc-116">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="b3bbc-117">exclusividade</span><span class="sxs-lookup"><span data-stu-id="b3bbc-117">unique</span></span>  <br/> |<span data-ttu-id="b3bbc-118">URL da conferência se for uma conferência ou caixa de diálogo se for uma sessão ponto a ponto.</span><span class="sxs-lookup"><span data-stu-id="b3bbc-118">Conference URI if this is a conference, or DialogID if this is a peer-to-peer session.</span></span>  <br/> |
|<span data-ttu-id="b3bbc-119">**Prova**</span><span class="sxs-lookup"><span data-stu-id="b3bbc-119">**Checksum**</span></span> <br/> |<span data-ttu-id="b3bbc-120">int</span><span class="sxs-lookup"><span data-stu-id="b3bbc-120">int</span></span>  <br/> |<span data-ttu-id="b3bbc-121">dedo</span><span class="sxs-lookup"><span data-stu-id="b3bbc-121">index</span></span>  <br/> |<span data-ttu-id="b3bbc-122">Checksum do URI da conferência.</span><span class="sxs-lookup"><span data-stu-id="b3bbc-122">Checksum of the conference URI.</span></span> <span data-ttu-id="b3bbc-123">Isso é usado internamente.</span><span class="sxs-lookup"><span data-stu-id="b3bbc-123">This is used internally.</span></span>  <br/> |
|<span data-ttu-id="b3bbc-124">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="b3bbc-124">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="b3bbc-125">datetime</span><span class="sxs-lookup"><span data-stu-id="b3bbc-125">datetime</span></span>  <br/> ||<span data-ttu-id="b3bbc-126">Somente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="b3bbc-126">For internal use only.</span></span>  <br/> |
   

