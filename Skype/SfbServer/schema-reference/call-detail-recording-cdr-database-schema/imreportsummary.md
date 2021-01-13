---
title: Tabela IMReportSummary no Skype for Business Server 2015
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
ms.assetid: 27ff9453-53f2-4fae-b637-70a086c9df96
description: O IMReportSummaryTable oferece um relatório geral sobre as sessões de mensagem instantânea mantidas em uma organização. Esta tabela foi introduzida no Microsoft Lync Server 2013.
ms.openlocfilehash: 6a80918376440c13d60e059744d88c09c2705853
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821521"
---
# <a name="imreportsummary-table-in-skype-for-business-server-2015"></a><span data-ttu-id="cdd5f-104">Tabela IMReportSummary no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="cdd5f-104">IMReportSummary table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="cdd5f-105">O IMReportSummaryTable oferece um relatório geral sobre as sessões de mensagem instantânea mantidas em uma organização.</span><span class="sxs-lookup"><span data-stu-id="cdd5f-105">The IMReportSummaryTable provides an overall report on the instant messaging sessions held in an organization.</span></span> <span data-ttu-id="cdd5f-106">Esta tabela foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cdd5f-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="cdd5f-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="cdd5f-107">**Column**</span></span>|<span data-ttu-id="cdd5f-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="cdd5f-108">**Data Type**</span></span>|<span data-ttu-id="cdd5f-109">**Chave/Índice**</span><span class="sxs-lookup"><span data-stu-id="cdd5f-109">**Key/Index**</span></span>|<span data-ttu-id="cdd5f-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="cdd5f-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="cdd5f-111">**StartTime**</span><span class="sxs-lookup"><span data-stu-id="cdd5f-111">**StartTime**</span></span> <br/> |<span data-ttu-id="cdd5f-112">datetime</span><span class="sxs-lookup"><span data-stu-id="cdd5f-112">datetime</span></span>  <br/> |<span data-ttu-id="cdd5f-113">Primário</span><span class="sxs-lookup"><span data-stu-id="cdd5f-113">Primary</span></span>  <br/> |<span data-ttu-id="cdd5f-114">Data e hora que a sessão de mensagem instantânea começou.</span><span class="sxs-lookup"><span data-stu-id="cdd5f-114">Date and time that the instant messaging session began.</span></span>  <br/> |
|<span data-ttu-id="cdd5f-115">**TimePeriod**</span><span class="sxs-lookup"><span data-stu-id="cdd5f-115">**TimePeriod**</span></span> <br/> |<span data-ttu-id="cdd5f-116">char(1)</span><span class="sxs-lookup"><span data-stu-id="cdd5f-116">char(1)</span></span>  <br/> |<span data-ttu-id="cdd5f-117">Primário</span><span class="sxs-lookup"><span data-stu-id="cdd5f-117">Primary</span></span>  <br/> ||
|<span data-ttu-id="cdd5f-118">**PoolFQDN**</span><span class="sxs-lookup"><span data-stu-id="cdd5f-118">**PoolFQDN**</span></span> <br/> |<span data-ttu-id="cdd5f-119">nvarchar(257)</span><span class="sxs-lookup"><span data-stu-id="cdd5f-119">nvarchar(257)</span></span>  <br/> |<span data-ttu-id="cdd5f-120">Primário</span><span class="sxs-lookup"><span data-stu-id="cdd5f-120">Primary</span></span>  <br/> |<span data-ttu-id="cdd5f-121">Nome de domínio totalmente qualificado do pool hospedando a sessão.</span><span class="sxs-lookup"><span data-stu-id="cdd5f-121">Fully qualified domain name of the pool hosting the session.</span></span>  <br/> |
|<span data-ttu-id="cdd5f-122">**AuthType**</span><span class="sxs-lookup"><span data-stu-id="cdd5f-122">**AuthType**</span></span> <br/> |<span data-ttu-id="cdd5f-123">int</span><span class="sxs-lookup"><span data-stu-id="cdd5f-123">int</span></span>  <br/> |<span data-ttu-id="cdd5f-124">Primário</span><span class="sxs-lookup"><span data-stu-id="cdd5f-124">Primary</span></span>  <br/> |<span data-ttu-id="cdd5f-125">Prioridade (por exemplo, urgente ou não urgente) da chamada.</span><span class="sxs-lookup"><span data-stu-id="cdd5f-125">Priority (for example, urgent or non-urgent) of the call.</span></span> <span data-ttu-id="cdd5f-126">As informações de prioridade são armazenadas [na tabela CallPriorities no Skype for Business Server 2015.](callpriorities.md)</span><span class="sxs-lookup"><span data-stu-id="cdd5f-126">Priority information is stored in the [CallPriorities table in Skype for Business Server 2015](callpriorities.md).</span></span>  <br/> |
|<span data-ttu-id="cdd5f-127">**SessionCount**</span><span class="sxs-lookup"><span data-stu-id="cdd5f-127">**SessionCount**</span></span> <br/> |<span data-ttu-id="cdd5f-128">bigint</span><span class="sxs-lookup"><span data-stu-id="cdd5f-128">bigint</span></span>  <br/> |||
|<span data-ttu-id="cdd5f-129">**MsgCount**</span><span class="sxs-lookup"><span data-stu-id="cdd5f-129">**MsgCount**</span></span> <br/> |<span data-ttu-id="cdd5f-130">bigint</span><span class="sxs-lookup"><span data-stu-id="cdd5f-130">bigint</span></span>  <br/> ||<span data-ttu-id="cdd5f-131">Número total de mensagens instantâneas trocadas durante a sessão.</span><span class="sxs-lookup"><span data-stu-id="cdd5f-131">Total number of instant messages exchanged during the session.</span></span>  <br/> |
   

