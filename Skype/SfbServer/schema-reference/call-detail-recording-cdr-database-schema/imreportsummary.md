---
title: Tabela IMReportSummary no Skype para Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 27ff9453-53f2-4fae-b637-70a086c9df96
description: O IMReportSummaryTable fornece um relatório geral sobre a mantidos em uma organização de sessões de mensagens instantâneas. Esta tabela foi introduzida no Microsoft Lync Server 2013.
ms.openlocfilehash: 3611243e49821e5fae211ce55858cdee555dd383
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33901042"
---
# <a name="imreportsummary-table-in-skype-for-business-server-2015"></a><span data-ttu-id="57b72-104">Tabela IMReportSummary no Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="57b72-104">IMReportSummary table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="57b72-105">O IMReportSummaryTable fornece um relatório geral sobre a mantidos em uma organização de sessões de mensagens instantâneas.</span><span class="sxs-lookup"><span data-stu-id="57b72-105">The IMReportSummaryTable provides an overall report on the instant messaging sessions held in an organization.</span></span> <span data-ttu-id="57b72-106">Esta tabela foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="57b72-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="57b72-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="57b72-107">**Column**</span></span>|<span data-ttu-id="57b72-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="57b72-108">**Data Type**</span></span>|<span data-ttu-id="57b72-109">**Chave/índice**</span><span class="sxs-lookup"><span data-stu-id="57b72-109">**Key/Index**</span></span>|<span data-ttu-id="57b72-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="57b72-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="57b72-111">**StartTime **</span><span class="sxs-lookup"><span data-stu-id="57b72-111">**StartTime**</span></span> <br/> |<span data-ttu-id="57b72-112">datetime</span><span class="sxs-lookup"><span data-stu-id="57b72-112">datetime</span></span>  <br/> |<span data-ttu-id="57b72-113">Primária</span><span class="sxs-lookup"><span data-stu-id="57b72-113">Primary</span></span>  <br/> |<span data-ttu-id="57b72-114">Data e hora em que a sessão de mensagens instantâneas começou.</span><span class="sxs-lookup"><span data-stu-id="57b72-114">Date and time that the instant messaging session began.</span></span>  <br/> |
|<span data-ttu-id="57b72-115">**TimePeriod**</span><span class="sxs-lookup"><span data-stu-id="57b72-115">**TimePeriod**</span></span> <br/> |<span data-ttu-id="57b72-116">char(1)</span><span class="sxs-lookup"><span data-stu-id="57b72-116">char(1)</span></span>  <br/> |<span data-ttu-id="57b72-117">Primária</span><span class="sxs-lookup"><span data-stu-id="57b72-117">Primary</span></span>  <br/> ||
|<span data-ttu-id="57b72-118">**PoolFQDN**</span><span class="sxs-lookup"><span data-stu-id="57b72-118">**PoolFQDN**</span></span> <br/> |<span data-ttu-id="57b72-119">nvarchar(257)</span><span class="sxs-lookup"><span data-stu-id="57b72-119">nvarchar(257)</span></span>  <br/> |<span data-ttu-id="57b72-120">Primária</span><span class="sxs-lookup"><span data-stu-id="57b72-120">Primary</span></span>  <br/> |<span data-ttu-id="57b72-121">Nome de domínio totalmente qualificado do pool hospedando a sessão.</span><span class="sxs-lookup"><span data-stu-id="57b72-121">Fully qualified domain name of the pool hosting the session.</span></span>  <br/> |
|<span data-ttu-id="57b72-122">**Tipo de autenticação**</span><span class="sxs-lookup"><span data-stu-id="57b72-122">**AuthType**</span></span> <br/> |<span data-ttu-id="57b72-123">int</span><span class="sxs-lookup"><span data-stu-id="57b72-123">int</span></span>  <br/> |<span data-ttu-id="57b72-124">Primária</span><span class="sxs-lookup"><span data-stu-id="57b72-124">Primary</span></span>  <br/> |<span data-ttu-id="57b72-125">Prioridade (por exemplo, urgente ou não urgente) da chamada.</span><span class="sxs-lookup"><span data-stu-id="57b72-125">Priority (for example, urgent or non-urgent) of the call.</span></span> <span data-ttu-id="57b72-126">Informações de prioridade são armazenadas na [tabela CallPriorities do Skype para Business Server 2015](callpriorities.md).</span><span class="sxs-lookup"><span data-stu-id="57b72-126">Priority information is stored in the [CallPriorities table in Skype for Business Server 2015](callpriorities.md).</span></span>  <br/> |
|<span data-ttu-id="57b72-127">**SessionCount**</span><span class="sxs-lookup"><span data-stu-id="57b72-127">**SessionCount**</span></span> <br/> |<span data-ttu-id="57b72-128">bigint</span><span class="sxs-lookup"><span data-stu-id="57b72-128">bigint</span></span>  <br/> |||
|<span data-ttu-id="57b72-129">**MsgCount**</span><span class="sxs-lookup"><span data-stu-id="57b72-129">**MsgCount**</span></span> <br/> |<span data-ttu-id="57b72-130">bigint</span><span class="sxs-lookup"><span data-stu-id="57b72-130">bigint</span></span>  <br/> ||<span data-ttu-id="57b72-131">Número total de mensagens instantâneas trocadas durante a sessão.</span><span class="sxs-lookup"><span data-stu-id="57b72-131">Total number of instant messages exchanged during the session.</span></span>  <br/> |
   

