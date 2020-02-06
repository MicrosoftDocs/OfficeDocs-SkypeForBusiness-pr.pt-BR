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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 24fb3caf-19b3-4c0a-90d7-ca5d53de32ad
description: A tabela AppliedBandwidthSource é uma tabela de suporte. Cada registro representa uma fonte.
ms.openlocfilehash: 875f6d105a2fef0bf710e57ec389bee4f2613c66
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41811439"
---
# <a name="appliedbandwidthsource-table"></a><span data-ttu-id="09ee7-104">Tabela AppliedBandwidthSource</span><span class="sxs-lookup"><span data-stu-id="09ee7-104">AppliedBandwidthSource table</span></span>
 
<span data-ttu-id="09ee7-105">A tabela AppliedBandwidthSource é uma tabela de suporte.</span><span class="sxs-lookup"><span data-stu-id="09ee7-105">The AppliedBandwidthSource table is a supporting table.</span></span> <span data-ttu-id="09ee7-106">Cada registro representa uma fonte.</span><span class="sxs-lookup"><span data-stu-id="09ee7-106">Each record represents one source.</span></span>
  
|<span data-ttu-id="09ee7-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="09ee7-107">**Column**</span></span>|<span data-ttu-id="09ee7-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="09ee7-108">**Data Type**</span></span>|<span data-ttu-id="09ee7-109">**Chave/índice**</span><span class="sxs-lookup"><span data-stu-id="09ee7-109">**Key/Index**</span></span>|<span data-ttu-id="09ee7-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="09ee7-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="09ee7-111">**AppliedBandwidthSourceKey**</span><span class="sxs-lookup"><span data-stu-id="09ee7-111">**AppliedBandwidthSourceKey**</span></span> <br/> |<span data-ttu-id="09ee7-112">int</span><span class="sxs-lookup"><span data-stu-id="09ee7-112">int</span></span>  <br/> |<span data-ttu-id="09ee7-113">Primária</span><span class="sxs-lookup"><span data-stu-id="09ee7-113">Primary</span></span>  <br/> |<span data-ttu-id="09ee7-114">Número exclusivo que identifica a fonte.</span><span class="sxs-lookup"><span data-stu-id="09ee7-114">Unique number identifying the source.</span></span>  <br/> |
|<span data-ttu-id="09ee7-115">**AppliedBandwidthSource**</span><span class="sxs-lookup"><span data-stu-id="09ee7-115">**AppliedBandwidthSource**</span></span> <br/> |<span data-ttu-id="09ee7-116">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="09ee7-116">varchar(256)</span></span>  <br/> |<span data-ttu-id="09ee7-117">Exclusividade</span><span class="sxs-lookup"><span data-stu-id="09ee7-117">Unique</span></span>  <br/> |<span data-ttu-id="09ee7-118">Essa é a origem do limite de largura de banda que está sendo imposto.</span><span class="sxs-lookup"><span data-stu-id="09ee7-118">This is the source of the bandwidth cap being imposed.</span></span> <span data-ttu-id="09ee7-119">Ele descreve para onde o limite de largura de banda é proveniente (por exemplo, "servidor de políticas", "Ativar servidor" ou "modalidade").</span><span class="sxs-lookup"><span data-stu-id="09ee7-119">It describes where the bandwidth limit is coming from (for example, "Policy Server", "TURN Server", or "Modality").</span></span>  <br/> |
   

