---
title: Tabela AppliedBandwidthSource
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
ms.assetid: 24fb3caf-19b3-4c0a-90d7-ca5d53de32ad
description: A tabela AppliedBandwidthSource é uma tabela de suporte. Cada registro representa uma origem.
ms.openlocfilehash: bf7e1be3b98bcd56fea16dbd7aa7171b056a7f3c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831401"
---
# <a name="appliedbandwidthsource-table"></a><span data-ttu-id="5fa55-104">Tabela AppliedBandwidthSource</span><span class="sxs-lookup"><span data-stu-id="5fa55-104">AppliedBandwidthSource table</span></span>
 
<span data-ttu-id="5fa55-p102">A tabela AppliedBandwidthSource é uma tabela de suporte. Cada registro representa uma origem.</span><span class="sxs-lookup"><span data-stu-id="5fa55-p102">The AppliedBandwidthSource table is a supporting table. Each record represents one source.</span></span>
  
|<span data-ttu-id="5fa55-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="5fa55-107">**Column**</span></span>|<span data-ttu-id="5fa55-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="5fa55-108">**Data Type**</span></span>|<span data-ttu-id="5fa55-109">**Chave/Índice**</span><span class="sxs-lookup"><span data-stu-id="5fa55-109">**Key/Index**</span></span>|<span data-ttu-id="5fa55-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="5fa55-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="5fa55-111">**AppliedBandwidthSourceKey**</span><span class="sxs-lookup"><span data-stu-id="5fa55-111">**AppliedBandwidthSourceKey**</span></span> <br/> |<span data-ttu-id="5fa55-112">int</span><span class="sxs-lookup"><span data-stu-id="5fa55-112">int</span></span>  <br/> |<span data-ttu-id="5fa55-113">Primário</span><span class="sxs-lookup"><span data-stu-id="5fa55-113">Primary</span></span>  <br/> |<span data-ttu-id="5fa55-114">Número exclusivo que identifica a origem.</span><span class="sxs-lookup"><span data-stu-id="5fa55-114">Unique number identifying the source.</span></span>  <br/> |
|<span data-ttu-id="5fa55-115">**AppliedBandwidthSource**</span><span class="sxs-lookup"><span data-stu-id="5fa55-115">**AppliedBandwidthSource**</span></span> <br/> |<span data-ttu-id="5fa55-116">varchar(256)</span><span class="sxs-lookup"><span data-stu-id="5fa55-116">varchar(256)</span></span>  <br/> |<span data-ttu-id="5fa55-117">Exclusivo</span><span class="sxs-lookup"><span data-stu-id="5fa55-117">Unique</span></span>  <br/> |<span data-ttu-id="5fa55-118">Essa é a origem do cap de largura de banda que está sendo imposto.</span><span class="sxs-lookup"><span data-stu-id="5fa55-118">This is the source of the bandwidth cap being imposed.</span></span> <span data-ttu-id="5fa55-119">Ele descreve de onde vem o limite de largura de banda (por exemplo, "Servidor de Políticas", "Servidor TURN" ou "Modalidade").</span><span class="sxs-lookup"><span data-stu-id="5fa55-119">It describes where the bandwidth limit is coming from (for example, "Policy Server", "TURN Server", or "Modality").</span></span>  <br/> |
   

