---
title: Exibição ProgressReport
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
ms.assetid: b49f3fc7-0e2f-498f-8505-aaaf54e435f9
description: A exibição ProgressReport armazena informações sobre sessões concluídas. Os relatórios de progresso será gravados somente para chamadas e sessões que o Lync Server 2013 determina como úteis para diagnósticos. Esta exibição foi introduzida no Microsoft Lync Server 2013.
ms.openlocfilehash: 6cc8295e73463fff9d4913efbf9d4844f9316149
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823181"
---
# <a name="progressreport-view"></a><span data-ttu-id="c1899-105">Exibição ProgressReport</span><span class="sxs-lookup"><span data-stu-id="c1899-105">ProgressReport view</span></span>
 
<span data-ttu-id="c1899-106">A exibição ProgressReport armazena informações sobre sessões concluídas.</span><span class="sxs-lookup"><span data-stu-id="c1899-106">The ProgressReport view stores information about completed sessions.</span></span> <span data-ttu-id="c1899-107">Os relatórios de progresso será gravados somente para chamadas e sessões que o Lync Server 2013 determina como úteis para diagnósticos.</span><span class="sxs-lookup"><span data-stu-id="c1899-107">Progress reports will be written only for calls and sessions that Lync Server 2013 determines might be useful for diagnostic purposes.</span></span> <span data-ttu-id="c1899-108">Esta exibição foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c1899-108">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c1899-109">Os campos ErrorTime, ErrorReportSeq e ProgressReportSeq não se referem necessariamente a erros, mas a mensagens que indicam o status de chamadas ou mensagens.</span><span class="sxs-lookup"><span data-stu-id="c1899-109">The ErrorTime, ErrorReportSeq and ProgressReportSeq fields don't necessarily refer to errors but to messages that indicate the status of calls or messages.</span></span> 
  
|<span data-ttu-id="c1899-110">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="c1899-110">**Column**</span></span>|<span data-ttu-id="c1899-111">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="c1899-111">**Data Type**</span></span>|<span data-ttu-id="c1899-112">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="c1899-112">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c1899-113">**ErrorTime**</span><span class="sxs-lookup"><span data-stu-id="c1899-113">**ErrorTime**</span></span> <br/> |<span data-ttu-id="c1899-114">datetime</span><span class="sxs-lookup"><span data-stu-id="c1899-114">datetime</span></span>  <br/> |<span data-ttu-id="c1899-p103">Hora do erro. Usada com o ErrorReportSeq para identificar um erro.</span><span class="sxs-lookup"><span data-stu-id="c1899-p103">Time of error occurred. Used in conjunction with ErrorReportSeq to uniquely identify an error.</span></span>  <br/> |
|<span data-ttu-id="c1899-117">**ErrorReportSeq**</span><span class="sxs-lookup"><span data-stu-id="c1899-117">**ErrorReportSeq**</span></span> <br/> |<span data-ttu-id="c1899-118">int</span><span class="sxs-lookup"><span data-stu-id="c1899-118">int</span></span>  <br/> |<span data-ttu-id="c1899-p104">Um número de ID para identificar o erro. Usado com ErrorTime para identificar um erro.</span><span class="sxs-lookup"><span data-stu-id="c1899-p104">ID number to identify the error. Used in conjunction with ErrorTime to uniquely identify an error.</span></span>  <br/> |
|<span data-ttu-id="c1899-121">**ProgressReportSeq**</span><span class="sxs-lookup"><span data-stu-id="c1899-121">**ProgressReportSeq**</span></span> <br/> |<span data-ttu-id="c1899-122">int</span><span class="sxs-lookup"><span data-stu-id="c1899-122">int</span></span>  <br/> |<span data-ttu-id="c1899-123">ID para identificar o relatórios de progresso.</span><span class="sxs-lookup"><span data-stu-id="c1899-123">ID to identify the progress report.</span></span> <span data-ttu-id="c1899-124">Usado para distinguir relatórios de progresso do mesmo relatório de erro.</span><span class="sxs-lookup"><span data-stu-id="c1899-124">Used to distinguish progress reports of the same error report.</span></span>  <br/> |
|<span data-ttu-id="c1899-125">**MsDiagId**</span><span class="sxs-lookup"><span data-stu-id="c1899-125">**MsDiagId**</span></span> <br/> |<span data-ttu-id="c1899-126">int</span><span class="sxs-lookup"><span data-stu-id="c1899-126">int</span></span>  <br/> |<span data-ttu-id="c1899-127">ID de diagnóstico do relatório de erro.</span><span class="sxs-lookup"><span data-stu-id="c1899-127">Diagnostic ID for the error report.</span></span>  <br/> |
|<span data-ttu-id="c1899-128">**Fonte**</span><span class="sxs-lookup"><span data-stu-id="c1899-128">**Source**</span></span> <br/> |<span data-ttu-id="c1899-129">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="c1899-129">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="c1899-130">Nome do servidor que originou o erro (se o relatório foi enviado de um componente do servidor).</span><span class="sxs-lookup"><span data-stu-id="c1899-130">Name of server that originated the error (if report was sent from a server component).</span></span>  <br/> |
|<span data-ttu-id="c1899-131">**Aplicativo**</span><span class="sxs-lookup"><span data-stu-id="c1899-131">**Application**</span></span> <br/> |<span data-ttu-id="c1899-132">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="c1899-132">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="c1899-133">Nome de um aplicativo que originou o erro (se o relatório foi enviado de um componente do servidor).</span><span class="sxs-lookup"><span data-stu-id="c1899-133">Name of application that originated the error (if report was sent from a server component).</span></span>  <br/> |
|<span data-ttu-id="c1899-134">**TelemetryId**</span><span class="sxs-lookup"><span data-stu-id="c1899-134">**TelemetryId**</span></span> <br/> |<span data-ttu-id="c1899-135">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="c1899-135">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="c1899-136">Identificador exclusivo correlacionando as informações da hora de ingresso dos diferentes componentes envolvidos em uma conferência.</span><span class="sxs-lookup"><span data-stu-id="c1899-136">Unique identifier correlating join time information for the different components involved in a conference.</span></span>  <br/> |
|<span data-ttu-id="c1899-137">**SessionSetupTime**</span><span class="sxs-lookup"><span data-stu-id="c1899-137">**SessionSetupTime**</span></span> <br/> |<span data-ttu-id="c1899-138">int</span><span class="sxs-lookup"><span data-stu-id="c1899-138">int</span></span>  <br/> |<span data-ttu-id="c1899-139">Tempo (em milissegundos) necessário para que um componentes específico ingresse em uma conferência.</span><span class="sxs-lookup"><span data-stu-id="c1899-139">Time (in milliseconds) required for a specific component to join a conference.</span></span>  <br/> |
|<span data-ttu-id="c1899-140">**MsDiagHeader**</span><span class="sxs-lookup"><span data-stu-id="c1899-140">**MsDiagHeader**</span></span> <br/> |<span data-ttu-id="c1899-141">varchar(max)</span><span class="sxs-lookup"><span data-stu-id="c1899-141">varchar(max)</span></span>  <br/> |<span data-ttu-id="c1899-142">Informações de erro adicionais.</span><span class="sxs-lookup"><span data-stu-id="c1899-142">Additional error information.</span></span>  <br/> |
   

