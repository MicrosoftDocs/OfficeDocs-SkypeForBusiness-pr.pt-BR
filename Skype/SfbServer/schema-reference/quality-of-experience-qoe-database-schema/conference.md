---
title: Tabela conference
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 2a2c327c-4719-42dc-a3bb-6dbc0864d9af
description: A tabela de Conferência é uma tabela de suporte. Cada registro representa uma conferência ou sessão ponto a ponto.
ms.openlocfilehash: 3840ad9bb4f9b0ff0aea5068c73d307d5bd0cf5e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802781"
---
# <a name="conference-table"></a><span data-ttu-id="a91de-104">Tabela conference</span><span class="sxs-lookup"><span data-stu-id="a91de-104">Conference table</span></span>
 
<span data-ttu-id="a91de-p102">A tabela de Conferência é uma tabela de suporte. Cada registro representa uma conferência ou sessão ponto a ponto.</span><span class="sxs-lookup"><span data-stu-id="a91de-p102">The Conference table is a supporting table. Each record represents one conference or peer-to-peer session.</span></span>
  
|<span data-ttu-id="a91de-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="a91de-107">**Column**</span></span>|<span data-ttu-id="a91de-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="a91de-108">**Data Type**</span></span>|<span data-ttu-id="a91de-109">**Chave/Índice**</span><span class="sxs-lookup"><span data-stu-id="a91de-109">**Key/Index**</span></span>|<span data-ttu-id="a91de-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="a91de-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a91de-111">**ConferenceKey**</span><span class="sxs-lookup"><span data-stu-id="a91de-111">**ConferenceKey**</span></span> <br/> |<span data-ttu-id="a91de-112">int</span><span class="sxs-lookup"><span data-stu-id="a91de-112">int</span></span>  <br/> |<span data-ttu-id="a91de-113">Primário</span><span class="sxs-lookup"><span data-stu-id="a91de-113">Primary</span></span>  <br/> |<span data-ttu-id="a91de-114">Número exclusivo que identifica o registro desta conferência.</span><span class="sxs-lookup"><span data-stu-id="a91de-114">Unique number identifying this conference record.</span></span>  <br/> |
|<span data-ttu-id="a91de-115">**ConfURI**</span><span class="sxs-lookup"><span data-stu-id="a91de-115">**ConfURI**</span></span> <br/> |<span data-ttu-id="a91de-116">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="a91de-116">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="a91de-117">unique</span><span class="sxs-lookup"><span data-stu-id="a91de-117">unique</span></span>  <br/> |<span data-ttu-id="a91de-118">URI da conferência, se isso for uma conferência, ou DialogID se for uma sessão ponto a ponto.</span><span class="sxs-lookup"><span data-stu-id="a91de-118">Conference URI if this is a conference, or DialogID if this is a peer-to-peer session.</span></span>  <br/> |
|<span data-ttu-id="a91de-119">**Soma de verificação**</span><span class="sxs-lookup"><span data-stu-id="a91de-119">**Checksum**</span></span> <br/> |<span data-ttu-id="a91de-120">int</span><span class="sxs-lookup"><span data-stu-id="a91de-120">int</span></span>  <br/> |<span data-ttu-id="a91de-121">index</span><span class="sxs-lookup"><span data-stu-id="a91de-121">index</span></span>  <br/> |<span data-ttu-id="a91de-p103">Soma de verificação do URI de conferência. Isso é usado internamente.</span><span class="sxs-lookup"><span data-stu-id="a91de-p103">Checksum of the conference URI. This is used internally.</span></span>  <br/> |
|<span data-ttu-id="a91de-124">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="a91de-124">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="a91de-125">datetime</span><span class="sxs-lookup"><span data-stu-id="a91de-125">datetime</span></span>  <br/> ||<span data-ttu-id="a91de-126">Apenas para uso interno.</span><span class="sxs-lookup"><span data-stu-id="a91de-126">For internal use only.</span></span>  <br/> |
   

