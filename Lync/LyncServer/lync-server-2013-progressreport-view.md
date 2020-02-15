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
ms.openlocfilehash: 916fb459e71460249b47719ab4a4c07f8d082e4d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049613"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="progressreport-view-in-lync-server-2013"></a><span data-ttu-id="942db-102">Exibição ProgressReport no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="942db-102">ProgressReport view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="942db-103">_**Última modificação do tópico:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="942db-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="942db-104">A exibição ProgressReport armazena informações sobre sessões concluídas.</span><span class="sxs-lookup"><span data-stu-id="942db-104">The ProgressReport view stores information about completed sessions.</span></span> <span data-ttu-id="942db-105">Os relatórios de progresso será gravados somente para chamadas e sessões que o Lync Server 2013 determina como úteis para diagnósticos.</span><span class="sxs-lookup"><span data-stu-id="942db-105">Progress reports will be written only for calls and sessions that Lync Server 2013 determines might be useful for diagnostic purposes.</span></span> <span data-ttu-id="942db-106">Este modo de exibição foi introduzido no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="942db-106">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="942db-107">Os campos ErrorTime, ErrorReportSeq e ProgressReportSeq não se referem necessariamente aos erros, mas a mensagens que indicam o status das chamadas ou mensagens.</span><span class="sxs-lookup"><span data-stu-id="942db-107">The ErrorTime, ErrorReportSeq and ProgressReportSeq fields don’t necessarily refer to errors but to messages that indicate the status of calls or messages.</span></span>



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="942db-108">Coluna</span><span class="sxs-lookup"><span data-stu-id="942db-108">Column</span></span></th>
<th><span data-ttu-id="942db-109">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="942db-109">Data Type</span></span></th>
<th><span data-ttu-id="942db-110">Detalhes</span><span class="sxs-lookup"><span data-stu-id="942db-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="942db-111"><strong>ErrorTime</strong></span><span class="sxs-lookup"><span data-stu-id="942db-111"><strong>ErrorTime</strong></span></span></p></td>
<td><p><span data-ttu-id="942db-112">datetime</span><span class="sxs-lookup"><span data-stu-id="942db-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="942db-p102">Hora do erro. Usada com o ErrorReportSeq para identificar um erro.</span><span class="sxs-lookup"><span data-stu-id="942db-p102">Time of error occurred. Used in conjunction with ErrorReportSeq to uniquely identify an error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="942db-115"><strong>ErrorReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="942db-115"><strong>ErrorReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="942db-116">int</span><span class="sxs-lookup"><span data-stu-id="942db-116">int</span></span></p></td>
<td><p><span data-ttu-id="942db-p103">Um número de ID para identificar o erro. Usado com ErrorTime para identificar um erro.</span><span class="sxs-lookup"><span data-stu-id="942db-p103">ID number to identify the error. Used in conjunction with ErrorTime to uniquely identify an error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="942db-119"><strong>ProgressReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="942db-119"><strong>ProgressReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="942db-120">int</span><span class="sxs-lookup"><span data-stu-id="942db-120">int</span></span></p></td>
<td><p><span data-ttu-id="942db-121">ID para identificar o relatórios de progresso.</span><span class="sxs-lookup"><span data-stu-id="942db-121">ID to identify the progress report.</span></span> <span data-ttu-id="942db-122">Usado para distinguir relatórios de progresso do mesmo relatório de erro.</span><span class="sxs-lookup"><span data-stu-id="942db-122">Used to distinguish progress reports of the same error report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="942db-123"><strong>MsDiagId</strong></span><span class="sxs-lookup"><span data-stu-id="942db-123"><strong>MsDiagId</strong></span></span></p></td>
<td><p><span data-ttu-id="942db-124">int</span><span class="sxs-lookup"><span data-stu-id="942db-124">int</span></span></p></td>
<td><p><span data-ttu-id="942db-125">ID de diagnóstico do relatório de erro.</span><span class="sxs-lookup"><span data-stu-id="942db-125">Diagnostic ID for the error report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="942db-126"><strong>Fonte</strong></span><span class="sxs-lookup"><span data-stu-id="942db-126"><strong>Source</strong></span></span></p></td>
<td><p><span data-ttu-id="942db-127">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="942db-127">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="942db-128">Nome do servidor que originou o erro (se o relatório foi enviado de um componente do servidor).</span><span class="sxs-lookup"><span data-stu-id="942db-128">Name of server that originated the error (if report was sent from a server component).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="942db-129"><strong>Application</strong></span><span class="sxs-lookup"><span data-stu-id="942db-129"><strong>Application</strong></span></span></p></td>
<td><p><span data-ttu-id="942db-130">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="942db-130">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="942db-131">Nome de um aplicativo que originou o erro (se o relatório foi enviado de um componente do servidor).</span><span class="sxs-lookup"><span data-stu-id="942db-131">Name of application that originated the error (if report was sent from a server component).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="942db-132"><strong>Telemetria</strong></span><span class="sxs-lookup"><span data-stu-id="942db-132"><strong>TelemetryId</strong></span></span></p></td>
<td><p><span data-ttu-id="942db-133">identificador</span><span class="sxs-lookup"><span data-stu-id="942db-133">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="942db-134">Identificador exclusivo correlacionando as informações da hora de ingresso dos diferentes componentes envolvidos em uma conferência.</span><span class="sxs-lookup"><span data-stu-id="942db-134">Unique identifier correlating join time information for the different components involved in a conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="942db-135"><strong>SessionSetupTime</strong></span><span class="sxs-lookup"><span data-stu-id="942db-135"><strong>SessionSetupTime</strong></span></span></p></td>
<td><p><span data-ttu-id="942db-136">int</span><span class="sxs-lookup"><span data-stu-id="942db-136">int</span></span></p></td>
<td><p><span data-ttu-id="942db-137">Tempo (em milissegundos) necessário para que um componentes específico ingresse em uma conferência.</span><span class="sxs-lookup"><span data-stu-id="942db-137">Time (in milliseconds) required for a specific component to join a conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="942db-138"><strong>MsDiagHeader</strong></span><span class="sxs-lookup"><span data-stu-id="942db-138"><strong>MsDiagHeader</strong></span></span></p></td>
<td><p><span data-ttu-id="942db-139">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="942db-139">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="942db-140">Informações de erro adicionais.</span><span class="sxs-lookup"><span data-stu-id="942db-140">Additional error information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

