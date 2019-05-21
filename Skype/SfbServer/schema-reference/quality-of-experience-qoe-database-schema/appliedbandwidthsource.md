---
title: Tabela AppliedBandwidthSource
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 24fb3caf-19b3-4c0a-90d7-ca5d53de32ad
description: A tabela AppliedBandwidthSource é uma tabela de suporte. Cada registro representa uma fonte.
ms.openlocfilehash: 6d40701b74dd5e7312a504127675eed686de7321
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295108"
---
# <a name="appliedbandwidthsource-table"></a><span data-ttu-id="11cc6-104">Tabela AppliedBandwidthSource</span><span class="sxs-lookup"><span data-stu-id="11cc6-104">AppliedBandwidthSource table</span></span>
 
<span data-ttu-id="11cc6-105">A tabela AppliedBandwidthSource é uma tabela de suporte.</span><span class="sxs-lookup"><span data-stu-id="11cc6-105">The AppliedBandwidthSource table is a supporting table.</span></span> <span data-ttu-id="11cc6-106">Cada registro representa uma fonte.</span><span class="sxs-lookup"><span data-stu-id="11cc6-106">Each record represents one source.</span></span>
  
|<span data-ttu-id="11cc6-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="11cc6-107">**Column**</span></span>|<span data-ttu-id="11cc6-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="11cc6-108">**Data Type**</span></span>|<span data-ttu-id="11cc6-109">**Chave/índice**</span><span class="sxs-lookup"><span data-stu-id="11cc6-109">**Key/Index**</span></span>|<span data-ttu-id="11cc6-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="11cc6-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="11cc6-111">**AppliedBandwidthSourceKey**</span><span class="sxs-lookup"><span data-stu-id="11cc6-111">**AppliedBandwidthSourceKey**</span></span> <br/> |<span data-ttu-id="11cc6-112">int</span><span class="sxs-lookup"><span data-stu-id="11cc6-112">int</span></span>  <br/> |<span data-ttu-id="11cc6-113">Primária</span><span class="sxs-lookup"><span data-stu-id="11cc6-113">Primary</span></span>  <br/> |<span data-ttu-id="11cc6-114">Número exclusivo que identifica a fonte.</span><span class="sxs-lookup"><span data-stu-id="11cc6-114">Unique number identifying the source.</span></span>  <br/> |
|<span data-ttu-id="11cc6-115">**AppliedBandwidthSource**</span><span class="sxs-lookup"><span data-stu-id="11cc6-115">**AppliedBandwidthSource**</span></span> <br/> |<span data-ttu-id="11cc6-116">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="11cc6-116">varchar(256)</span></span>  <br/> |<span data-ttu-id="11cc6-117">Exclusividade</span><span class="sxs-lookup"><span data-stu-id="11cc6-117">Unique</span></span>  <br/> |<span data-ttu-id="11cc6-118">Essa é a origem do limite de largura de banda que está sendo imposto.</span><span class="sxs-lookup"><span data-stu-id="11cc6-118">This is the source of the bandwidth cap being imposed.</span></span> <span data-ttu-id="11cc6-119">Ele descreve para onde o limite de largura de banda é proveniente (por exemplo, "servidor de políticas", "Ativar servidor" ou "modalidade").</span><span class="sxs-lookup"><span data-stu-id="11cc6-119">It describes where the bandwidth limit is coming from (for example, "Policy Server", "TURN Server", or "Modality").</span></span>  <br/> |
   

