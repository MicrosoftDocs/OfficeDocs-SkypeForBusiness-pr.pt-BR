---
title: Tabela ConferenceJoinTimeThresholds no Skype para Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3944d724-bdd8-4d1c-a2af-933ee8141529
description: 'A tabela ConferenceJoinTimeThresholds contém os limites de classificação utilizados pelo relatório de resumo de tempo de ingresso de conferência. O relatório de resumo de tempo de ingresso de conferência resume o tempo necessário para os usuários ingressem em uma conferência; com êxito Esses valores de tempo são relatados como uma média e em uma das seguintes categorias:'
ms.openlocfilehash: d6fbae0d077719782b3e93c0fe008ee35ce3370e
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213288"
---
# <a name="conferencejointimethresholds-table-in-skype-for-business-server-2015"></a><span data-ttu-id="a9903-104">Tabela ConferenceJoinTimeThresholds no Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="a9903-104">ConferenceJoinTimeThresholds table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="a9903-105">A tabela ConferenceJoinTimeThresholds contém os limites de classificação utilizados pelo relatório de resumo de tempo de ingresso de conferência.</span><span class="sxs-lookup"><span data-stu-id="a9903-105">The ConferenceJoinTimeThresholds table contains the classification boundaries used by the Conference Join Time Summary Report.</span></span> <span data-ttu-id="a9903-106">O relatório de resumo de tempo de ingresso de conferência resume o tempo necessário para os usuários ingressem em uma conferência; com êxito Esses valores de tempo são relatados como uma média e em uma das seguintes categorias:</span><span class="sxs-lookup"><span data-stu-id="a9903-106">The Conference Join Time Summary Report summarizes the amount time required for users to successfully join a conference; these time values are reported both as an average and in one of the following categories:</span></span>
  
- <span data-ttu-id="a9903-107">Menos de 2 segundos.</span><span class="sxs-lookup"><span data-stu-id="a9903-107">Less than 2 seconds.</span></span>
    
- <span data-ttu-id="a9903-108">Entre 2 e 5 segundos.</span><span class="sxs-lookup"><span data-stu-id="a9903-108">Between 2 second and 5 seconds.</span></span>
    
- <span data-ttu-id="a9903-109">Entre 5 e 10 segundos.</span><span class="sxs-lookup"><span data-stu-id="a9903-109">Between 5 seconds and 10 seconds.</span></span>
    
- <span data-ttu-id="a9903-110">Mais de 10 segundos.</span><span class="sxs-lookup"><span data-stu-id="a9903-110">More than 10 seconds.</span></span>
    
<span data-ttu-id="a9903-111">A tabela ConferenceJoinTimeThresholds contém os valores de classificação de 2 segundos, 5 segundos e 10 segundos.</span><span class="sxs-lookup"><span data-stu-id="a9903-111">The ConferenceJoinTimeThresholds table contains the classification values 2 seconds, 5 seconds, and 10 seconds.</span></span>
  
<span data-ttu-id="a9903-112">Esta tabela foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a9903-112">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="a9903-113">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="a9903-113">**Column**</span></span>|<span data-ttu-id="a9903-114">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="a9903-114">**Data Type**</span></span>|<span data-ttu-id="a9903-115">**Chave/índice**</span><span class="sxs-lookup"><span data-stu-id="a9903-115">**Key/Index**</span></span>|<span data-ttu-id="a9903-116">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="a9903-116">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a9903-117">**ThresholdId**</span><span class="sxs-lookup"><span data-stu-id="a9903-117">**ThresholdId**</span></span> <br/> |<span data-ttu-id="a9903-118">int</span><span class="sxs-lookup"><span data-stu-id="a9903-118">int</span></span>  <br/> |<span data-ttu-id="a9903-119">Primária</span><span class="sxs-lookup"><span data-stu-id="a9903-119">Primary</span></span>  <br/> |<span data-ttu-id="a9903-120">Identificador exclusivo para a classificação.</span><span class="sxs-lookup"><span data-stu-id="a9903-120">Unique identifier for the classification.</span></span>  <br/> |
|<span data-ttu-id="a9903-121">**ThresholdValue**</span><span class="sxs-lookup"><span data-stu-id="a9903-121">**ThresholdValue**</span></span> <br/> |<span data-ttu-id="a9903-122">int</span><span class="sxs-lookup"><span data-stu-id="a9903-122">int</span></span>  <br/> || <span data-ttu-id="a9903-123">Limite superior para a classificação.</span><span class="sxs-lookup"><span data-stu-id="a9903-123">Upper limit for the classification.</span></span> <span data-ttu-id="a9903-124">Os valores permitidos são:</span><span class="sxs-lookup"><span data-stu-id="a9903-124">Allowed values are:</span></span> <br/>  <span data-ttu-id="a9903-125">2</span><span class="sxs-lookup"><span data-stu-id="a9903-125">2</span></span> <br/>  <span data-ttu-id="a9903-126">5</span><span class="sxs-lookup"><span data-stu-id="a9903-126">5</span></span> <br/>  <span data-ttu-id="a9903-127">10</span><span class="sxs-lookup"><span data-stu-id="a9903-127">10</span></span> <br/> |
   

