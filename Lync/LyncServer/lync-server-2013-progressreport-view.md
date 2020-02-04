---
title: 'Lync Server 2013: modo de exibição ProgressReport'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ProgressReport view
ms:assetid: b49f3fc7-0e2f-498f-8505-aaaf54e435f9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721857(v=OCS.15)
ms:contentKeyID: 49733790
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4fa8d73981490503b26b77b79be6f42aab77703e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747235"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="progressreport-view-in-lync-server-2013"></a><span data-ttu-id="88c8a-102">Exibição ProgressReport no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="88c8a-102">ProgressReport view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="88c8a-103">_**Tópico da última modificação:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="88c8a-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="88c8a-104">A exibição ProgressReport armazena informações sobre sessões concluídas.</span><span class="sxs-lookup"><span data-stu-id="88c8a-104">The ProgressReport view stores information about completed sessions.</span></span> <span data-ttu-id="88c8a-105">Os relatórios de progresso serão escritos apenas para chamadas e sessões que o Lync Server 2013 determina que podem ser úteis para fins de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="88c8a-105">Progress reports will be written only for calls and sessions that Lync Server 2013 determines might be useful for diagnostic purposes.</span></span> <span data-ttu-id="88c8a-106">Este modo de exibição foi apresentado no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="88c8a-106">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="88c8a-107">Os campos ErrorTime, ErrorReportSeq e ProgressReportSeq não se referem necessariamente a erros, mas a mensagens que indicam o status de chamadas ou mensagens.</span><span class="sxs-lookup"><span data-stu-id="88c8a-107">The ErrorTime, ErrorReportSeq and ProgressReportSeq fields don’t necessarily refer to errors but to messages that indicate the status of calls or messages.</span></span>



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="88c8a-108">Coluna</span><span class="sxs-lookup"><span data-stu-id="88c8a-108">Column</span></span></th>
<th><span data-ttu-id="88c8a-109">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="88c8a-109">Data Type</span></span></th>
<th><span data-ttu-id="88c8a-110">Detalhes</span><span class="sxs-lookup"><span data-stu-id="88c8a-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="88c8a-111"><strong>ErrorTime</strong></span><span class="sxs-lookup"><span data-stu-id="88c8a-111"><strong>ErrorTime</strong></span></span></p></td>
<td><p><span data-ttu-id="88c8a-112">datetime</span><span class="sxs-lookup"><span data-stu-id="88c8a-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="88c8a-113">Ocorreu um erro de hora.</span><span class="sxs-lookup"><span data-stu-id="88c8a-113">Time of error occurred.</span></span> <span data-ttu-id="88c8a-114">Usado em conjunto com ErrorReportSeq para identificar um erro exclusivamente.</span><span class="sxs-lookup"><span data-stu-id="88c8a-114">Used in conjunction with ErrorReportSeq to uniquely identify an error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88c8a-115"><strong>ErrorReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="88c8a-115"><strong>ErrorReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="88c8a-116">int</span><span class="sxs-lookup"><span data-stu-id="88c8a-116">int</span></span></p></td>
<td><p><span data-ttu-id="88c8a-117">Número de identificação para identificar o erro.</span><span class="sxs-lookup"><span data-stu-id="88c8a-117">ID number to identify the error.</span></span> <span data-ttu-id="88c8a-118">Usado em conjunto com ErrorTime para identificar um erro com exclusividade.</span><span class="sxs-lookup"><span data-stu-id="88c8a-118">Used in conjunction with ErrorTime to uniquely identify an error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88c8a-119"><strong>ProgressReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="88c8a-119"><strong>ProgressReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="88c8a-120">int</span><span class="sxs-lookup"><span data-stu-id="88c8a-120">int</span></span></p></td>
<td><p><span data-ttu-id="88c8a-121">ID para identificar o relatório de progresso.</span><span class="sxs-lookup"><span data-stu-id="88c8a-121">ID to identify the progress report.</span></span> <span data-ttu-id="88c8a-122">Usado para distinguir relatórios de progresso do mesmo relatório de erro.</span><span class="sxs-lookup"><span data-stu-id="88c8a-122">Used to distinguish progress reports of the same error report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88c8a-123"><strong>MsDiagId</strong></span><span class="sxs-lookup"><span data-stu-id="88c8a-123"><strong>MsDiagId</strong></span></span></p></td>
<td><p><span data-ttu-id="88c8a-124">int</span><span class="sxs-lookup"><span data-stu-id="88c8a-124">int</span></span></p></td>
<td><p><span data-ttu-id="88c8a-125">ID de diagnóstico do relatório de erros.</span><span class="sxs-lookup"><span data-stu-id="88c8a-125">Diagnostic ID for the error report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88c8a-126"><strong>Origem</strong></span><span class="sxs-lookup"><span data-stu-id="88c8a-126"><strong>Source</strong></span></span></p></td>
<td><p><span data-ttu-id="88c8a-127">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="88c8a-127">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="88c8a-128">Nome do servidor que originou o erro (se o relatório foi enviado a partir de um componente de servidor).</span><span class="sxs-lookup"><span data-stu-id="88c8a-128">Name of server that originated the error (if report was sent from a server component).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88c8a-129"><strong>Aplicativo</strong></span><span class="sxs-lookup"><span data-stu-id="88c8a-129"><strong>Application</strong></span></span></p></td>
<td><p><span data-ttu-id="88c8a-130">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="88c8a-130">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="88c8a-131">Nome do aplicativo que originou o erro (se o relatório foi enviado a partir de um componente de servidor).</span><span class="sxs-lookup"><span data-stu-id="88c8a-131">Name of application that originated the error (if report was sent from a server component).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88c8a-132"><strong>Telemetria</strong></span><span class="sxs-lookup"><span data-stu-id="88c8a-132"><strong>TelemetryId</strong></span></span></p></td>
<td><p><span data-ttu-id="88c8a-133">identificador</span><span class="sxs-lookup"><span data-stu-id="88c8a-133">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="88c8a-134">Identificador exclusivo que correlaciona as informações de tempo de junção para os diferentes componentes envolvidos em uma conferência.</span><span class="sxs-lookup"><span data-stu-id="88c8a-134">Unique identifier correlating join time information for the different components involved in a conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88c8a-135"><strong>SessionSetupTime</strong></span><span class="sxs-lookup"><span data-stu-id="88c8a-135"><strong>SessionSetupTime</strong></span></span></p></td>
<td><p><span data-ttu-id="88c8a-136">int</span><span class="sxs-lookup"><span data-stu-id="88c8a-136">int</span></span></p></td>
<td><p><span data-ttu-id="88c8a-137">Tempo (em milissegundos) necessário para um componente específico entrar em uma conferência.</span><span class="sxs-lookup"><span data-stu-id="88c8a-137">Time (in milliseconds) required for a specific component to join a conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88c8a-138"><strong>MsDiagHeader</strong></span><span class="sxs-lookup"><span data-stu-id="88c8a-138"><strong>MsDiagHeader</strong></span></span></p></td>
<td><p><span data-ttu-id="88c8a-139">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="88c8a-139">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="88c8a-140">Informações adicionais sobre o erro.</span><span class="sxs-lookup"><span data-stu-id="88c8a-140">Additional error information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

