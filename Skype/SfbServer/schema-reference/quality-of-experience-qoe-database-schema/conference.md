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
localization_priority: Normal
ms.assetid: 2a2c327c-4719-42dc-a3bb-6dbc0864d9af
description: A tabela de conferências é uma tabela de suporte. Cada registro representa uma reunião ou sessão ponto a ponto.
ms.openlocfilehash: 61e9667d235ed9ab8f3696f55e676bfc60ab69e3
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295010"
---
# <a name="conference-table"></a><span data-ttu-id="27563-104">Tabela Conference</span><span class="sxs-lookup"><span data-stu-id="27563-104">Conference table</span></span>
 
<span data-ttu-id="27563-105">A tabela de conferências é uma tabela de suporte.</span><span class="sxs-lookup"><span data-stu-id="27563-105">The Conference table is a supporting table.</span></span> <span data-ttu-id="27563-106">Cada registro representa uma reunião ou sessão ponto a ponto.</span><span class="sxs-lookup"><span data-stu-id="27563-106">Each record represents one conference or peer-to-peer session.</span></span>
  
|<span data-ttu-id="27563-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="27563-107">**Column**</span></span>|<span data-ttu-id="27563-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="27563-108">**Data Type**</span></span>|<span data-ttu-id="27563-109">**Chave/índice**</span><span class="sxs-lookup"><span data-stu-id="27563-109">**Key/Index**</span></span>|<span data-ttu-id="27563-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="27563-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="27563-111">**ConferenceKey**</span><span class="sxs-lookup"><span data-stu-id="27563-111">**ConferenceKey**</span></span> <br/> |<span data-ttu-id="27563-112">int</span><span class="sxs-lookup"><span data-stu-id="27563-112">int</span></span>  <br/> |<span data-ttu-id="27563-113">Primária</span><span class="sxs-lookup"><span data-stu-id="27563-113">Primary</span></span>  <br/> |<span data-ttu-id="27563-114">Número exclusivo que identifica esse registro de conferência.</span><span class="sxs-lookup"><span data-stu-id="27563-114">Unique number identifying this conference record.</span></span>  <br/> |
|<span data-ttu-id="27563-115">**ConfURI**</span><span class="sxs-lookup"><span data-stu-id="27563-115">**ConfURI**</span></span> <br/> |<span data-ttu-id="27563-116">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="27563-116">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="27563-117">exclusividade</span><span class="sxs-lookup"><span data-stu-id="27563-117">unique</span></span>  <br/> |<span data-ttu-id="27563-118">URL da conferência se for uma conferência ou caixa de diálogo se for uma sessão ponto a ponto.</span><span class="sxs-lookup"><span data-stu-id="27563-118">Conference URI if this is a conference, or DialogID if this is a peer-to-peer session.</span></span>  <br/> |
|<span data-ttu-id="27563-119">**Prova**</span><span class="sxs-lookup"><span data-stu-id="27563-119">**Checksum**</span></span> <br/> |<span data-ttu-id="27563-120">int</span><span class="sxs-lookup"><span data-stu-id="27563-120">int</span></span>  <br/> |<span data-ttu-id="27563-121">dedo</span><span class="sxs-lookup"><span data-stu-id="27563-121">index</span></span>  <br/> |<span data-ttu-id="27563-122">Checksum do URI da conferência.</span><span class="sxs-lookup"><span data-stu-id="27563-122">Checksum of the conference URI.</span></span> <span data-ttu-id="27563-123">Isso é usado internamente.</span><span class="sxs-lookup"><span data-stu-id="27563-123">This is used internally.</span></span>  <br/> |
|<span data-ttu-id="27563-124">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="27563-124">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="27563-125">datetime</span><span class="sxs-lookup"><span data-stu-id="27563-125">datetime</span></span>  <br/> ||<span data-ttu-id="27563-126">Somente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="27563-126">For internal use only.</span></span>  <br/> |
   

