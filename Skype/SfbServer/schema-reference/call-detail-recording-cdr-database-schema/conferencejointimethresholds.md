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
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30895814"
---
# <a name="conferencejointimethresholds-table-in-skype-for-business-server-2015"></a><span data-ttu-id="24fdb-104">Tabela ConferenceJoinTimeThresholds no Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="24fdb-104">ConferenceJoinTimeThresholds table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="24fdb-105">A tabela ConferenceJoinTimeThresholds contém os limites de classificação utilizados pelo relatório de resumo de tempo de ingresso de conferência.</span><span class="sxs-lookup"><span data-stu-id="24fdb-105">The ConferenceJoinTimeThresholds table contains the classification boundaries used by the Conference Join Time Summary Report.</span></span> <span data-ttu-id="24fdb-106">O relatório de resumo de tempo de ingresso de conferência resume o tempo necessário para os usuários ingressem em uma conferência; com êxito Esses valores de tempo são relatados como uma média e em uma das seguintes categorias:</span><span class="sxs-lookup"><span data-stu-id="24fdb-106">The Conference Join Time Summary Report summarizes the amount time required for users to successfully join a conference; these time values are reported both as an average and in one of the following categories:</span></span>
  
- <span data-ttu-id="24fdb-107">Menos de 2 segundos.</span><span class="sxs-lookup"><span data-stu-id="24fdb-107">Less than 2 seconds.</span></span>
    
- <span data-ttu-id="24fdb-108">Entre 2 e 5 segundos.</span><span class="sxs-lookup"><span data-stu-id="24fdb-108">Between 2 second and 5 seconds.</span></span>
    
- <span data-ttu-id="24fdb-109">Entre 5 e 10 segundos.</span><span class="sxs-lookup"><span data-stu-id="24fdb-109">Between 5 seconds and 10 seconds.</span></span>
    
- <span data-ttu-id="24fdb-110">Mais de 10 segundos.</span><span class="sxs-lookup"><span data-stu-id="24fdb-110">More than 10 seconds.</span></span>
    
<span data-ttu-id="24fdb-111">A tabela ConferenceJoinTimeThresholds contém os valores de classificação de 2 segundos, 5 segundos e 10 segundos.</span><span class="sxs-lookup"><span data-stu-id="24fdb-111">The ConferenceJoinTimeThresholds table contains the classification values 2 seconds, 5 seconds, and 10 seconds.</span></span>
  
<span data-ttu-id="24fdb-112">Esta tabela foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="24fdb-112">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="24fdb-113">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="24fdb-113">**Column**</span></span>|<span data-ttu-id="24fdb-114">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="24fdb-114">**Data Type**</span></span>|<span data-ttu-id="24fdb-115">**Chave/índice**</span><span class="sxs-lookup"><span data-stu-id="24fdb-115">**Key/Index**</span></span>|<span data-ttu-id="24fdb-116">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="24fdb-116">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="24fdb-117">**ThresholdId**</span><span class="sxs-lookup"><span data-stu-id="24fdb-117">**ThresholdId**</span></span> <br/> |<span data-ttu-id="24fdb-118">int</span><span class="sxs-lookup"><span data-stu-id="24fdb-118">int</span></span>  <br/> |<span data-ttu-id="24fdb-119">Primária</span><span class="sxs-lookup"><span data-stu-id="24fdb-119">Primary</span></span>  <br/> |<span data-ttu-id="24fdb-120">Identificador exclusivo para a classificação.</span><span class="sxs-lookup"><span data-stu-id="24fdb-120">Unique identifier for the classification.</span></span>  <br/> |
|<span data-ttu-id="24fdb-121">**ThresholdValue**</span><span class="sxs-lookup"><span data-stu-id="24fdb-121">**ThresholdValue**</span></span> <br/> |<span data-ttu-id="24fdb-122">int</span><span class="sxs-lookup"><span data-stu-id="24fdb-122">int</span></span>  <br/> || <span data-ttu-id="24fdb-123">Limite superior para a classificação.</span><span class="sxs-lookup"><span data-stu-id="24fdb-123">Upper limit for the classification.</span></span> <span data-ttu-id="24fdb-124">Os valores permitidos são:</span><span class="sxs-lookup"><span data-stu-id="24fdb-124">Allowed values are:</span></span> <br/>  <span data-ttu-id="24fdb-125">2</span><span class="sxs-lookup"><span data-stu-id="24fdb-125">2</span></span> <br/>  <span data-ttu-id="24fdb-126">5</span><span class="sxs-lookup"><span data-stu-id="24fdb-126">5</span></span> <br/>  <span data-ttu-id="24fdb-127">10</span><span class="sxs-lookup"><span data-stu-id="24fdb-127">10</span></span> <br/> |
   

