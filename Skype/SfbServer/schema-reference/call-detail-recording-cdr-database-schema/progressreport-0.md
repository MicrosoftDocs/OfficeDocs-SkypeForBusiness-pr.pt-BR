---
title: Exibição ProgressReport
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
ms.assetid: b49f3fc7-0e2f-498f-8505-aaaf54e435f9
description: A exibição ProgressReport armazena informações sobre sessões concluídas. Os relatórios de progresso serão escritos apenas para chamadas e sessões que o Lync Server 2013 determina que podem ser úteis para fins de diagnóstico. Este modo de exibição foi apresentado no Microsoft Lync Server 2013.
ms.openlocfilehash: c07b9db8ebd9f898ab9d8feb5b07c4723209522c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814979"
---
# <a name="progressreport-view"></a><span data-ttu-id="ae11d-105">Exibição ProgressReport</span><span class="sxs-lookup"><span data-stu-id="ae11d-105">ProgressReport view</span></span>
 
<span data-ttu-id="ae11d-106">A exibição ProgressReport armazena informações sobre sessões concluídas.</span><span class="sxs-lookup"><span data-stu-id="ae11d-106">The ProgressReport view stores information about completed sessions.</span></span> <span data-ttu-id="ae11d-107">Os relatórios de progresso serão escritos apenas para chamadas e sessões que o Lync Server 2013 determina que podem ser úteis para fins de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="ae11d-107">Progress reports will be written only for calls and sessions that Lync Server 2013 determines might be useful for diagnostic purposes.</span></span> <span data-ttu-id="ae11d-108">Este modo de exibição foi apresentado no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ae11d-108">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ae11d-109">Os campos ErrorTime, ErrorReportSeq e ProgressReportSeq não se referem necessariamente a erros, mas a mensagens que indicam o status de chamadas ou mensagens.</span><span class="sxs-lookup"><span data-stu-id="ae11d-109">The ErrorTime, ErrorReportSeq and ProgressReportSeq fields don't necessarily refer to errors but to messages that indicate the status of calls or messages.</span></span> 
  
|<span data-ttu-id="ae11d-110">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="ae11d-110">**Column**</span></span>|<span data-ttu-id="ae11d-111">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="ae11d-111">**Data Type**</span></span>|<span data-ttu-id="ae11d-112">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="ae11d-112">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ae11d-113">**ErrorTime**</span><span class="sxs-lookup"><span data-stu-id="ae11d-113">**ErrorTime**</span></span> <br/> |<span data-ttu-id="ae11d-114">datetime</span><span class="sxs-lookup"><span data-stu-id="ae11d-114">datetime</span></span>  <br/> |<span data-ttu-id="ae11d-115">Ocorreu um erro de hora.</span><span class="sxs-lookup"><span data-stu-id="ae11d-115">Time of error occurred.</span></span> <span data-ttu-id="ae11d-116">Usado em conjunto com ErrorReportSeq para identificar um erro exclusivamente.</span><span class="sxs-lookup"><span data-stu-id="ae11d-116">Used in conjunction with ErrorReportSeq to uniquely identify an error.</span></span>  <br/> |
|<span data-ttu-id="ae11d-117">**ErrorReportSeq**</span><span class="sxs-lookup"><span data-stu-id="ae11d-117">**ErrorReportSeq**</span></span> <br/> |<span data-ttu-id="ae11d-118">int</span><span class="sxs-lookup"><span data-stu-id="ae11d-118">int</span></span>  <br/> |<span data-ttu-id="ae11d-119">Número de identificação para identificar o erro.</span><span class="sxs-lookup"><span data-stu-id="ae11d-119">ID number to identify the error.</span></span> <span data-ttu-id="ae11d-120">Usado em conjunto com ErrorTime para identificar um erro com exclusividade.</span><span class="sxs-lookup"><span data-stu-id="ae11d-120">Used in conjunction with ErrorTime to uniquely identify an error.</span></span>  <br/> |
|<span data-ttu-id="ae11d-121">**ProgressReportSeq**</span><span class="sxs-lookup"><span data-stu-id="ae11d-121">**ProgressReportSeq**</span></span> <br/> |<span data-ttu-id="ae11d-122">int</span><span class="sxs-lookup"><span data-stu-id="ae11d-122">int</span></span>  <br/> |<span data-ttu-id="ae11d-123">ID para identificar o relatório de progresso.</span><span class="sxs-lookup"><span data-stu-id="ae11d-123">ID to identify the progress report.</span></span> <span data-ttu-id="ae11d-124">Usado para distinguir relatórios de progresso do mesmo relatório de erro.</span><span class="sxs-lookup"><span data-stu-id="ae11d-124">Used to distinguish progress reports of the same error report.</span></span>  <br/> |
|<span data-ttu-id="ae11d-125">**MsDiagId**</span><span class="sxs-lookup"><span data-stu-id="ae11d-125">**MsDiagId**</span></span> <br/> |<span data-ttu-id="ae11d-126">int</span><span class="sxs-lookup"><span data-stu-id="ae11d-126">int</span></span>  <br/> |<span data-ttu-id="ae11d-127">ID de diagnóstico do relatório de erros.</span><span class="sxs-lookup"><span data-stu-id="ae11d-127">Diagnostic ID for the error report.</span></span>  <br/> |
|<span data-ttu-id="ae11d-128">**Origem**</span><span class="sxs-lookup"><span data-stu-id="ae11d-128">**Source**</span></span> <br/> |<span data-ttu-id="ae11d-129">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="ae11d-129">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="ae11d-130">Nome do servidor que originou o erro (se o relatório foi enviado a partir de um componente de servidor).</span><span class="sxs-lookup"><span data-stu-id="ae11d-130">Name of server that originated the error (if report was sent from a server component).</span></span>  <br/> |
|<span data-ttu-id="ae11d-131">**Aplicativo**</span><span class="sxs-lookup"><span data-stu-id="ae11d-131">**Application**</span></span> <br/> |<span data-ttu-id="ae11d-132">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="ae11d-132">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="ae11d-133">Nome do aplicativo que originou o erro (se o relatório foi enviado a partir de um componente de servidor).</span><span class="sxs-lookup"><span data-stu-id="ae11d-133">Name of application that originated the error (if report was sent from a server component).</span></span>  <br/> |
|<span data-ttu-id="ae11d-134">**Telemetria**</span><span class="sxs-lookup"><span data-stu-id="ae11d-134">**TelemetryId**</span></span> <br/> |<span data-ttu-id="ae11d-135">identificador</span><span class="sxs-lookup"><span data-stu-id="ae11d-135">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="ae11d-136">Identificador exclusivo que correlaciona as informações de tempo de junção para os diferentes componentes envolvidos em uma conferência.</span><span class="sxs-lookup"><span data-stu-id="ae11d-136">Unique identifier correlating join time information for the different components involved in a conference.</span></span>  <br/> |
|<span data-ttu-id="ae11d-137">**SessionSetupTime**</span><span class="sxs-lookup"><span data-stu-id="ae11d-137">**SessionSetupTime**</span></span> <br/> |<span data-ttu-id="ae11d-138">int</span><span class="sxs-lookup"><span data-stu-id="ae11d-138">int</span></span>  <br/> |<span data-ttu-id="ae11d-139">Tempo (em milissegundos) necessário para um componente específico entrar em uma conferência.</span><span class="sxs-lookup"><span data-stu-id="ae11d-139">Time (in milliseconds) required for a specific component to join a conference.</span></span>  <br/> |
|<span data-ttu-id="ae11d-140">**MsDiagHeader**</span><span class="sxs-lookup"><span data-stu-id="ae11d-140">**MsDiagHeader**</span></span> <br/> |<span data-ttu-id="ae11d-141">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="ae11d-141">varchar(max)</span></span>  <br/> |<span data-ttu-id="ae11d-142">Informações adicionais sobre o erro.</span><span class="sxs-lookup"><span data-stu-id="ae11d-142">Additional error information.</span></span>  <br/> |
   

