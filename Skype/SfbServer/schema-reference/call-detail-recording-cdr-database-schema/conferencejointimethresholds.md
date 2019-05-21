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
localization_priority: Normal
ms.assetid: 3944d724-bdd8-4d1c-a2af-933ee8141529
description: 'A tabela ConferenceJoinTimeThresholds contém os limites de classificação usados pelo relatório de Resumo de tempo de ingresso em conferência. O relatório de Resumo de tempo de ingresso em conferência resume o tempo necessário para que os usuários ingressem com êxito em uma conferência; esses valores de tempo são relatados como uma média e em uma das seguintes categorias:'
ms.openlocfilehash: 4b2f27b6ab826ff95c1478cf54e8a21c148b1d3c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296494"
---
# <a name="conferencejointimethresholds-table-in-skype-for-business-server-2015"></a><span data-ttu-id="9913a-104">Tabela ConferenceJoinTimeThresholds no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="9913a-104">ConferenceJoinTimeThresholds table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="9913a-105">A tabela ConferenceJoinTimeThresholds contém os limites de classificação usados pelo relatório de Resumo de tempo de ingresso em conferência.</span><span class="sxs-lookup"><span data-stu-id="9913a-105">The ConferenceJoinTimeThresholds table contains the classification boundaries used by the Conference Join Time Summary Report.</span></span> <span data-ttu-id="9913a-106">O relatório de Resumo de tempo de ingresso em conferência resume o tempo necessário para que os usuários ingressem com êxito em uma conferência; esses valores de tempo são relatados como uma média e em uma das seguintes categorias:</span><span class="sxs-lookup"><span data-stu-id="9913a-106">The Conference Join Time Summary Report summarizes the amount time required for users to successfully join a conference; these time values are reported both as an average and in one of the following categories:</span></span>
  
- <span data-ttu-id="9913a-107">Menos de 2 segundos.</span><span class="sxs-lookup"><span data-stu-id="9913a-107">Less than 2 seconds.</span></span>
    
- <span data-ttu-id="9913a-108">Entre 2 e 5 segundos.</span><span class="sxs-lookup"><span data-stu-id="9913a-108">Between 2 second and 5 seconds.</span></span>
    
- <span data-ttu-id="9913a-109">Entre 5 segundos e 10 segundos.</span><span class="sxs-lookup"><span data-stu-id="9913a-109">Between 5 seconds and 10 seconds.</span></span>
    
- <span data-ttu-id="9913a-110">Mais de 10 segundos.</span><span class="sxs-lookup"><span data-stu-id="9913a-110">More than 10 seconds.</span></span>
    
<span data-ttu-id="9913a-111">A tabela ConferenceJoinTimeThresholds contém os valores de classificação 2 segundos, 5 segundos e 10 segundos.</span><span class="sxs-lookup"><span data-stu-id="9913a-111">The ConferenceJoinTimeThresholds table contains the classification values 2 seconds, 5 seconds, and 10 seconds.</span></span>
  
<span data-ttu-id="9913a-112">Esta tabela foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9913a-112">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="9913a-113">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="9913a-113">**Column**</span></span>|<span data-ttu-id="9913a-114">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="9913a-114">**Data Type**</span></span>|<span data-ttu-id="9913a-115">**Chave/índice**</span><span class="sxs-lookup"><span data-stu-id="9913a-115">**Key/Index**</span></span>|<span data-ttu-id="9913a-116">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="9913a-116">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="9913a-117">**Thresholdid**</span><span class="sxs-lookup"><span data-stu-id="9913a-117">**ThresholdId**</span></span> <br/> |<span data-ttu-id="9913a-118">int</span><span class="sxs-lookup"><span data-stu-id="9913a-118">int</span></span>  <br/> |<span data-ttu-id="9913a-119">Primária</span><span class="sxs-lookup"><span data-stu-id="9913a-119">Primary</span></span>  <br/> |<span data-ttu-id="9913a-120">Identificador exclusivo da classificação.</span><span class="sxs-lookup"><span data-stu-id="9913a-120">Unique identifier for the classification.</span></span>  <br/> |
|<span data-ttu-id="9913a-121">**ThresholdValue**</span><span class="sxs-lookup"><span data-stu-id="9913a-121">**ThresholdValue**</span></span> <br/> |<span data-ttu-id="9913a-122">int</span><span class="sxs-lookup"><span data-stu-id="9913a-122">int</span></span>  <br/> || <span data-ttu-id="9913a-123">Limite superior da classificação.</span><span class="sxs-lookup"><span data-stu-id="9913a-123">Upper limit for the classification.</span></span> <span data-ttu-id="9913a-124">Os valores permitidos são:</span><span class="sxs-lookup"><span data-stu-id="9913a-124">Allowed values are:</span></span> <br/>  <span data-ttu-id="9913a-125">2</span><span class="sxs-lookup"><span data-stu-id="9913a-125">2</span></span> <br/>  <span data-ttu-id="9913a-126">5</span><span class="sxs-lookup"><span data-stu-id="9913a-126">5</span></span> <br/>  <span data-ttu-id="9913a-127">254</span><span class="sxs-lookup"><span data-stu-id="9913a-127">10</span></span> <br/> |
   

