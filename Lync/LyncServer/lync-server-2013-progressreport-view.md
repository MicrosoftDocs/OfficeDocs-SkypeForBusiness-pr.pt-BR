---
title: 'Lync Server 2013: modo de exibição ProgressReport'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: ProgressReport view
ms:assetid: b49f3fc7-0e2f-498f-8505-aaaf54e435f9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721857(v=OCS.15)
ms:contentKeyID: 49733790
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 423d99211a89ef328bc62aca89a9b65141e128ce
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823592"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="progressreport-view-in-lync-server-2013"></a><span data-ttu-id="fe47e-102">Exibição ProgressReport no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fe47e-102">ProgressReport view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fe47e-103">_**Tópico da última modificação:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="fe47e-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="fe47e-104">A exibição ProgressReport armazena informações sobre sessões concluídas.</span><span class="sxs-lookup"><span data-stu-id="fe47e-104">The ProgressReport view stores information about completed sessions.</span></span> <span data-ttu-id="fe47e-105">Os relatórios de progresso serão escritos apenas para chamadas e sessões que o Lync Server 2013 determina que podem ser úteis para fins de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="fe47e-105">Progress reports will be written only for calls and sessions that Lync Server 2013 determines might be useful for diagnostic purposes.</span></span> <span data-ttu-id="fe47e-106">Este modo de exibição foi apresentado no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fe47e-106">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="fe47e-107">Os campos ErrorTime, ErrorReportSeq e ProgressReportSeq não se referem necessariamente a erros, mas a mensagens que indicam o status de chamadas ou mensagens.</span><span class="sxs-lookup"><span data-stu-id="fe47e-107">The ErrorTime, ErrorReportSeq and ProgressReportSeq fields don’t necessarily refer to errors but to messages that indicate the status of calls or messages.</span></span>



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fe47e-108">Coluna</span><span class="sxs-lookup"><span data-stu-id="fe47e-108">Column</span></span></th>
<th><span data-ttu-id="fe47e-109">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="fe47e-109">Data Type</span></span></th>
<th><span data-ttu-id="fe47e-110">Detalhes</span><span class="sxs-lookup"><span data-stu-id="fe47e-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fe47e-111"><strong>ErrorTime</strong></span><span class="sxs-lookup"><span data-stu-id="fe47e-111"><strong>ErrorTime</strong></span></span></p></td>
<td><p><span data-ttu-id="fe47e-112">datetime</span><span class="sxs-lookup"><span data-stu-id="fe47e-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="fe47e-113">Ocorreu um erro de hora.</span><span class="sxs-lookup"><span data-stu-id="fe47e-113">Time of error occurred.</span></span> <span data-ttu-id="fe47e-114">Usado em conjunto com ErrorReportSeq para identificar um erro exclusivamente.</span><span class="sxs-lookup"><span data-stu-id="fe47e-114">Used in conjunction with ErrorReportSeq to uniquely identify an error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe47e-115"><strong>ErrorReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="fe47e-115"><strong>ErrorReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="fe47e-116">int</span><span class="sxs-lookup"><span data-stu-id="fe47e-116">int</span></span></p></td>
<td><p><span data-ttu-id="fe47e-117">Número de identificação para identificar o erro.</span><span class="sxs-lookup"><span data-stu-id="fe47e-117">ID number to identify the error.</span></span> <span data-ttu-id="fe47e-118">Usado em conjunto com ErrorTime para identificar um erro com exclusividade.</span><span class="sxs-lookup"><span data-stu-id="fe47e-118">Used in conjunction with ErrorTime to uniquely identify an error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe47e-119"><strong>ProgressReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="fe47e-119"><strong>ProgressReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="fe47e-120">int</span><span class="sxs-lookup"><span data-stu-id="fe47e-120">int</span></span></p></td>
<td><p><span data-ttu-id="fe47e-121">ID para identificar o relatório de progresso.</span><span class="sxs-lookup"><span data-stu-id="fe47e-121">ID to identify the progress report.</span></span> <span data-ttu-id="fe47e-122">Usado para distinguir relatórios de progresso do mesmo relatório de erro.</span><span class="sxs-lookup"><span data-stu-id="fe47e-122">Used to distinguish progress reports of the same error report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe47e-123"><strong>MsDiagId</strong></span><span class="sxs-lookup"><span data-stu-id="fe47e-123"><strong>MsDiagId</strong></span></span></p></td>
<td><p><span data-ttu-id="fe47e-124">int</span><span class="sxs-lookup"><span data-stu-id="fe47e-124">int</span></span></p></td>
<td><p><span data-ttu-id="fe47e-125">ID de diagnóstico do relatório de erros.</span><span class="sxs-lookup"><span data-stu-id="fe47e-125">Diagnostic ID for the error report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe47e-126"><strong>Origem</strong></span><span class="sxs-lookup"><span data-stu-id="fe47e-126"><strong>Source</strong></span></span></p></td>
<td><p><span data-ttu-id="fe47e-127">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="fe47e-127">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fe47e-128">Nome do servidor que originou o erro (se o relatório foi enviado a partir de um componente de servidor).</span><span class="sxs-lookup"><span data-stu-id="fe47e-128">Name of server that originated the error (if report was sent from a server component).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe47e-129"><strong>Aplicativo</strong></span><span class="sxs-lookup"><span data-stu-id="fe47e-129"><strong>Application</strong></span></span></p></td>
<td><p><span data-ttu-id="fe47e-130">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="fe47e-130">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fe47e-131">Nome do aplicativo que originou o erro (se o relatório foi enviado a partir de um componente de servidor).</span><span class="sxs-lookup"><span data-stu-id="fe47e-131">Name of application that originated the error (if report was sent from a server component).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe47e-132"><strong>Telemetria</strong></span><span class="sxs-lookup"><span data-stu-id="fe47e-132"><strong>TelemetryId</strong></span></span></p></td>
<td><p><span data-ttu-id="fe47e-133">identificador</span><span class="sxs-lookup"><span data-stu-id="fe47e-133">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="fe47e-134">Identificador exclusivo que correlaciona as informações de tempo de junção para os diferentes componentes envolvidos em uma conferência.</span><span class="sxs-lookup"><span data-stu-id="fe47e-134">Unique identifier correlating join time information for the different components involved in a conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe47e-135"><strong>SessionSetupTime</strong></span><span class="sxs-lookup"><span data-stu-id="fe47e-135"><strong>SessionSetupTime</strong></span></span></p></td>
<td><p><span data-ttu-id="fe47e-136">int</span><span class="sxs-lookup"><span data-stu-id="fe47e-136">int</span></span></p></td>
<td><p><span data-ttu-id="fe47e-137">Tempo (em milissegundos) necessário para um componente específico entrar em uma conferência.</span><span class="sxs-lookup"><span data-stu-id="fe47e-137">Time (in milliseconds) required for a specific component to join a conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe47e-138"><strong>MsDiagHeader</strong></span><span class="sxs-lookup"><span data-stu-id="fe47e-138"><strong>MsDiagHeader</strong></span></span></p></td>
<td><p><span data-ttu-id="fe47e-139">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="fe47e-139">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="fe47e-140">Informações adicionais sobre o erro.</span><span class="sxs-lookup"><span data-stu-id="fe47e-140">Additional error information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

