---
title: Tabela ConferenceJoinTimeThresholds no Skype for Business Server 2015
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
ms.assetid: 3944d724-bdd8-4d1c-a2af-933ee8141529
description: 'A tabela ConferenceJoinTimeThresholds contém os limites de classificação usados pelo relatório de Resumo de tempo de ingresso em conferência. O relatório de Resumo de tempo de ingresso em conferência resume o tempo necessário para que os usuários ingressem com êxito em uma conferência; esses valores de tempo são relatados como uma média e em uma das seguintes categorias:'
ms.openlocfilehash: 1874a94448be5957079b1c53944bc127df761e5e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815389"
---
# <a name="conferencejointimethresholds-table-in-skype-for-business-server-2015"></a><span data-ttu-id="19be5-104">Tabela ConferenceJoinTimeThresholds no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="19be5-104">ConferenceJoinTimeThresholds table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="19be5-105">A tabela ConferenceJoinTimeThresholds contém os limites de classificação usados pelo relatório de Resumo de tempo de ingresso em conferência.</span><span class="sxs-lookup"><span data-stu-id="19be5-105">The ConferenceJoinTimeThresholds table contains the classification boundaries used by the Conference Join Time Summary Report.</span></span> <span data-ttu-id="19be5-106">O relatório de Resumo de tempo de ingresso em conferência resume o tempo necessário para que os usuários ingressem com êxito em uma conferência; esses valores de tempo são relatados como uma média e em uma das seguintes categorias:</span><span class="sxs-lookup"><span data-stu-id="19be5-106">The Conference Join Time Summary Report summarizes the amount time required for users to successfully join a conference; these time values are reported both as an average and in one of the following categories:</span></span>
  
- <span data-ttu-id="19be5-107">Menos de 2 segundos.</span><span class="sxs-lookup"><span data-stu-id="19be5-107">Less than 2 seconds.</span></span>
    
- <span data-ttu-id="19be5-108">Entre 2 e 5 segundos.</span><span class="sxs-lookup"><span data-stu-id="19be5-108">Between 2 second and 5 seconds.</span></span>
    
- <span data-ttu-id="19be5-109">Entre 5 segundos e 10 segundos.</span><span class="sxs-lookup"><span data-stu-id="19be5-109">Between 5 seconds and 10 seconds.</span></span>
    
- <span data-ttu-id="19be5-110">Mais de 10 segundos.</span><span class="sxs-lookup"><span data-stu-id="19be5-110">More than 10 seconds.</span></span>
    
<span data-ttu-id="19be5-111">A tabela ConferenceJoinTimeThresholds contém os valores de classificação 2 segundos, 5 segundos e 10 segundos.</span><span class="sxs-lookup"><span data-stu-id="19be5-111">The ConferenceJoinTimeThresholds table contains the classification values 2 seconds, 5 seconds, and 10 seconds.</span></span>
  
<span data-ttu-id="19be5-112">Esta tabela foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="19be5-112">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="19be5-113">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="19be5-113">**Column**</span></span>|<span data-ttu-id="19be5-114">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="19be5-114">**Data Type**</span></span>|<span data-ttu-id="19be5-115">**Chave/índice**</span><span class="sxs-lookup"><span data-stu-id="19be5-115">**Key/Index**</span></span>|<span data-ttu-id="19be5-116">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="19be5-116">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="19be5-117">**Thresholdid**</span><span class="sxs-lookup"><span data-stu-id="19be5-117">**ThresholdId**</span></span> <br/> |<span data-ttu-id="19be5-118">int</span><span class="sxs-lookup"><span data-stu-id="19be5-118">int</span></span>  <br/> |<span data-ttu-id="19be5-119">Primária</span><span class="sxs-lookup"><span data-stu-id="19be5-119">Primary</span></span>  <br/> |<span data-ttu-id="19be5-120">Identificador exclusivo da classificação.</span><span class="sxs-lookup"><span data-stu-id="19be5-120">Unique identifier for the classification.</span></span>  <br/> |
|<span data-ttu-id="19be5-121">**ThresholdValue**</span><span class="sxs-lookup"><span data-stu-id="19be5-121">**ThresholdValue**</span></span> <br/> |<span data-ttu-id="19be5-122">int</span><span class="sxs-lookup"><span data-stu-id="19be5-122">int</span></span>  <br/> || <span data-ttu-id="19be5-123">Limite superior da classificação.</span><span class="sxs-lookup"><span data-stu-id="19be5-123">Upper limit for the classification.</span></span> <span data-ttu-id="19be5-124">Os valores permitidos são:</span><span class="sxs-lookup"><span data-stu-id="19be5-124">Allowed values are:</span></span> <br/>  <span data-ttu-id="19be5-125">2</span><span class="sxs-lookup"><span data-stu-id="19be5-125">2</span></span> <br/>  <span data-ttu-id="19be5-126">5</span><span class="sxs-lookup"><span data-stu-id="19be5-126">5</span></span> <br/>  <span data-ttu-id="19be5-127">254</span><span class="sxs-lookup"><span data-stu-id="19be5-127">10</span></span> <br/> |
   

