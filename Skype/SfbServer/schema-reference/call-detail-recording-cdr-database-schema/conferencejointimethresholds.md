---
title: Tabela ConferenceJoinTimeThresholds no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3944d724-bdd8-4d1c-a2af-933ee8141529
description: 'A tabela ConferenceJoinTimeThresholds contém os limites de classificação usados pelo Relatório de Resumo de Tempo de Participação em Conferência. Este relatório resume o período necessário para que os usuários participem com êxito de uma conferência; esses valores de tempo são reportados como média e em uma das seguintes categorias:'
ms.openlocfilehash: dfa7293307376b5fb5c86cec6f7504d363b005f5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813301"
---
# <a name="conferencejointimethresholds-table-in-skype-for-business-server-2015"></a><span data-ttu-id="aa202-104">Tabela ConferenceJoinTimeThresholds no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="aa202-104">ConferenceJoinTimeThresholds table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="aa202-p102">A tabela ConferenceJoinTimeThresholds contém os limites de classificação usados pelo Relatório de Resumo de Tempo de Participação em Conferência. Este relatório resume o período necessário para que os usuários participem com êxito de uma conferência; esses valores de tempo são reportados como média e em uma das seguintes categorias:</span><span class="sxs-lookup"><span data-stu-id="aa202-p102">The ConferenceJoinTimeThresholds table contains the classification boundaries used by the Conference Join Time Summary Report. The Conference Join Time Summary Report summarizes the amount time required for users to successfully join a conference; these time values are reported both as an average and in one of the following categories:</span></span>
  
- <span data-ttu-id="aa202-107">Menos de 2 segundos.</span><span class="sxs-lookup"><span data-stu-id="aa202-107">Less than 2 seconds.</span></span>
    
- <span data-ttu-id="aa202-108">Entre 2 e 5 segundos.</span><span class="sxs-lookup"><span data-stu-id="aa202-108">Between 2 second and 5 seconds.</span></span>
    
- <span data-ttu-id="aa202-109">Entre 5 e 10 segundos.</span><span class="sxs-lookup"><span data-stu-id="aa202-109">Between 5 seconds and 10 seconds.</span></span>
    
- <span data-ttu-id="aa202-110">Mais de 10 segundos</span><span class="sxs-lookup"><span data-stu-id="aa202-110">More than 10 seconds.</span></span>
    
<span data-ttu-id="aa202-111">A tabela ConferenceJoinTimeThresholds contém os valores de classificação de 2 segundos, 5 segundos e 10 segundos.</span><span class="sxs-lookup"><span data-stu-id="aa202-111">The ConferenceJoinTimeThresholds table contains the classification values 2 seconds, 5 seconds, and 10 seconds.</span></span>
  
<span data-ttu-id="aa202-112">Esta tabela foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="aa202-112">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="aa202-113">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="aa202-113">**Column**</span></span>|<span data-ttu-id="aa202-114">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="aa202-114">**Data Type**</span></span>|<span data-ttu-id="aa202-115">**Chave/Índice**</span><span class="sxs-lookup"><span data-stu-id="aa202-115">**Key/Index**</span></span>|<span data-ttu-id="aa202-116">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="aa202-116">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="aa202-117">**ThresholdId**</span><span class="sxs-lookup"><span data-stu-id="aa202-117">**ThresholdId**</span></span> <br/> |<span data-ttu-id="aa202-118">int</span><span class="sxs-lookup"><span data-stu-id="aa202-118">int</span></span>  <br/> |<span data-ttu-id="aa202-119">Primário</span><span class="sxs-lookup"><span data-stu-id="aa202-119">Primary</span></span>  <br/> |<span data-ttu-id="aa202-120">Identificador exclusivo da classificação.</span><span class="sxs-lookup"><span data-stu-id="aa202-120">Unique identifier for the classification.</span></span>  <br/> |
|<span data-ttu-id="aa202-121">**ThresholdValue**</span><span class="sxs-lookup"><span data-stu-id="aa202-121">**ThresholdValue**</span></span> <br/> |<span data-ttu-id="aa202-122">int</span><span class="sxs-lookup"><span data-stu-id="aa202-122">int</span></span>  <br/> || <span data-ttu-id="aa202-p103">Limite superior da classificação. Os valores permitidos são:</span><span class="sxs-lookup"><span data-stu-id="aa202-p103">Upper limit for the classification. Allowed values are:</span></span> <br/>  <span data-ttu-id="aa202-125">2 </span><span class="sxs-lookup"><span data-stu-id="aa202-125">2</span></span> <br/>  <span data-ttu-id="aa202-126">5 </span><span class="sxs-lookup"><span data-stu-id="aa202-126">5</span></span> <br/>  <span data-ttu-id="aa202-127">10 </span><span class="sxs-lookup"><span data-stu-id="aa202-127">10</span></span> <br/> |
   

