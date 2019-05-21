---
title: Tabela IMReportSummary no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 27ff9453-53f2-4fae-b637-70a086c9df96
description: O IMReportSummaryTable fornece um relatório geral sobre as sessões de mensagens instantâneas contidas em uma organização. Esta tabela foi introduzida no Microsoft Lync Server 2013.
ms.openlocfilehash: 647b8dc3e48e56d126a65f524de90954b7aeca8f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296123"
---
# <a name="imreportsummary-table-in-skype-for-business-server-2015"></a><span data-ttu-id="cd70a-104">Tabela IMReportSummary no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="cd70a-104">IMReportSummary table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="cd70a-105">O IMReportSummaryTable fornece um relatório geral sobre as sessões de mensagens instantâneas contidas em uma organização.</span><span class="sxs-lookup"><span data-stu-id="cd70a-105">The IMReportSummaryTable provides an overall report on the instant messaging sessions held in an organization.</span></span> <span data-ttu-id="cd70a-106">Esta tabela foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cd70a-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="cd70a-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="cd70a-107">**Column**</span></span>|<span data-ttu-id="cd70a-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="cd70a-108">**Data Type**</span></span>|<span data-ttu-id="cd70a-109">**Chave/índice**</span><span class="sxs-lookup"><span data-stu-id="cd70a-109">**Key/Index**</span></span>|<span data-ttu-id="cd70a-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="cd70a-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="cd70a-111">**StartTime **</span><span class="sxs-lookup"><span data-stu-id="cd70a-111">**StartTime**</span></span> <br/> |<span data-ttu-id="cd70a-112">datetime</span><span class="sxs-lookup"><span data-stu-id="cd70a-112">datetime</span></span>  <br/> |<span data-ttu-id="cd70a-113">Primária</span><span class="sxs-lookup"><span data-stu-id="cd70a-113">Primary</span></span>  <br/> |<span data-ttu-id="cd70a-114">Data e hora de início da sessão de mensagens instantâneas.</span><span class="sxs-lookup"><span data-stu-id="cd70a-114">Date and time that the instant messaging session began.</span></span>  <br/> |
|<span data-ttu-id="cd70a-115">**Período de tempo**</span><span class="sxs-lookup"><span data-stu-id="cd70a-115">**TimePeriod**</span></span> <br/> |<span data-ttu-id="cd70a-116">caractere (1)</span><span class="sxs-lookup"><span data-stu-id="cd70a-116">char(1)</span></span>  <br/> |<span data-ttu-id="cd70a-117">Primária</span><span class="sxs-lookup"><span data-stu-id="cd70a-117">Primary</span></span>  <br/> ||
|<span data-ttu-id="cd70a-118">**PoolFQDN**</span><span class="sxs-lookup"><span data-stu-id="cd70a-118">**PoolFQDN**</span></span> <br/> |<span data-ttu-id="cd70a-119">nvarchar (257)</span><span class="sxs-lookup"><span data-stu-id="cd70a-119">nvarchar(257)</span></span>  <br/> |<span data-ttu-id="cd70a-120">Primária</span><span class="sxs-lookup"><span data-stu-id="cd70a-120">Primary</span></span>  <br/> |<span data-ttu-id="cd70a-121">Nome de domínio totalmente qualificado do pool que hospeda a sessão.</span><span class="sxs-lookup"><span data-stu-id="cd70a-121">Fully qualified domain name of the pool hosting the session.</span></span>  <br/> |
|<span data-ttu-id="cd70a-122">**AuthType**</span><span class="sxs-lookup"><span data-stu-id="cd70a-122">**AuthType**</span></span> <br/> |<span data-ttu-id="cd70a-123">int</span><span class="sxs-lookup"><span data-stu-id="cd70a-123">int</span></span>  <br/> |<span data-ttu-id="cd70a-124">Primária</span><span class="sxs-lookup"><span data-stu-id="cd70a-124">Primary</span></span>  <br/> |<span data-ttu-id="cd70a-125">Prioridade (por exemplo, urgente ou não urgente) da chamada.</span><span class="sxs-lookup"><span data-stu-id="cd70a-125">Priority (for example, urgent or non-urgent) of the call.</span></span> <span data-ttu-id="cd70a-126">As informações de prioridade são armazenadas na [tabela CallPriorities no Skype for Business Server 2015](callpriorities.md).</span><span class="sxs-lookup"><span data-stu-id="cd70a-126">Priority information is stored in the [CallPriorities table in Skype for Business Server 2015](callpriorities.md).</span></span>  <br/> |
|<span data-ttu-id="cd70a-127">**SessionCount**</span><span class="sxs-lookup"><span data-stu-id="cd70a-127">**SessionCount**</span></span> <br/> |<span data-ttu-id="cd70a-128">bigint</span><span class="sxs-lookup"><span data-stu-id="cd70a-128">bigint</span></span>  <br/> |||
|<span data-ttu-id="cd70a-129">**MsgCount**</span><span class="sxs-lookup"><span data-stu-id="cd70a-129">**MsgCount**</span></span> <br/> |<span data-ttu-id="cd70a-130">bigint</span><span class="sxs-lookup"><span data-stu-id="cd70a-130">bigint</span></span>  <br/> ||<span data-ttu-id="cd70a-131">Número total de mensagens instantâneas trocadas durante a sessão.</span><span class="sxs-lookup"><span data-stu-id="cd70a-131">Total number of instant messages exchanged during the session.</span></span>  <br/> |
   

