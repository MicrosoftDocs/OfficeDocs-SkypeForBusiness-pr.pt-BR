---
title: 'Lync Server 2013: modo de exibição ProgressReport'
description: 'Lync Server 2013: modo de exibição ProgressReport.'
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
ms.openlocfilehash: b95086012f254499644e778e43cafdf70ffc8f9c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579787"
---
# <a name="progressreport-view-in-lync-server-2013"></a><span data-ttu-id="1cd35-103">Exibição ProgressReport no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1cd35-103">ProgressReport view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1cd35-104">_**Última modificação do tópico:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="1cd35-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="1cd35-105">A exibição ProgressReport armazena informações sobre sessões concluídas.</span><span class="sxs-lookup"><span data-stu-id="1cd35-105">The ProgressReport view stores information about completed sessions.</span></span> <span data-ttu-id="1cd35-106">Os relatórios de progresso será gravados somente para chamadas e sessões que o Lync Server 2013 determina como úteis para diagnósticos.</span><span class="sxs-lookup"><span data-stu-id="1cd35-106">Progress reports will be written only for calls and sessions that Lync Server 2013 determines might be useful for diagnostic purposes.</span></span> <span data-ttu-id="1cd35-107">Este modo de exibição foi introduzido no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1cd35-107">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1cd35-108">Os campos ErrorTime, ErrorReportSeq e ProgressReportSeq não se referem necessariamente aos erros, mas a mensagens que indicam o status das chamadas ou mensagens.</span><span class="sxs-lookup"><span data-stu-id="1cd35-108">The ErrorTime, ErrorReportSeq and ProgressReportSeq fields don’t necessarily refer to errors but to messages that indicate the status of calls or messages.</span></span>



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1cd35-109">Coluna</span><span class="sxs-lookup"><span data-stu-id="1cd35-109">Column</span></span></th>
<th><span data-ttu-id="1cd35-110">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="1cd35-110">Data Type</span></span></th>
<th><span data-ttu-id="1cd35-111">Detalhes</span><span class="sxs-lookup"><span data-stu-id="1cd35-111">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1cd35-112"><strong>ErrorTime</strong></span><span class="sxs-lookup"><span data-stu-id="1cd35-112"><strong>ErrorTime</strong></span></span></p></td>
<td><p><span data-ttu-id="1cd35-113">datetime</span><span class="sxs-lookup"><span data-stu-id="1cd35-113">datetime</span></span></p></td>
<td><p><span data-ttu-id="1cd35-p102">Hora do erro. Usada com o ErrorReportSeq para identificar um erro.</span><span class="sxs-lookup"><span data-stu-id="1cd35-p102">Time of error occurred. Used in conjunction with ErrorReportSeq to uniquely identify an error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1cd35-116"><strong>ErrorReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="1cd35-116"><strong>ErrorReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="1cd35-117">int</span><span class="sxs-lookup"><span data-stu-id="1cd35-117">int</span></span></p></td>
<td><p><span data-ttu-id="1cd35-p103">Um número de ID para identificar o erro. Usado com ErrorTime para identificar um erro.</span><span class="sxs-lookup"><span data-stu-id="1cd35-p103">ID number to identify the error. Used in conjunction with ErrorTime to uniquely identify an error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1cd35-120"><strong>ProgressReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="1cd35-120"><strong>ProgressReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="1cd35-121">int</span><span class="sxs-lookup"><span data-stu-id="1cd35-121">int</span></span></p></td>
<td><p><span data-ttu-id="1cd35-122">ID para identificar o relatórios de progresso.</span><span class="sxs-lookup"><span data-stu-id="1cd35-122">ID to identify the progress report.</span></span> <span data-ttu-id="1cd35-123">Usado para distinguir relatórios de progresso do mesmo relatório de erro.</span><span class="sxs-lookup"><span data-stu-id="1cd35-123">Used to distinguish progress reports of the same error report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1cd35-124"><strong>MsDiagId</strong></span><span class="sxs-lookup"><span data-stu-id="1cd35-124"><strong>MsDiagId</strong></span></span></p></td>
<td><p><span data-ttu-id="1cd35-125">int</span><span class="sxs-lookup"><span data-stu-id="1cd35-125">int</span></span></p></td>
<td><p><span data-ttu-id="1cd35-126">ID de diagnóstico do relatório de erro.</span><span class="sxs-lookup"><span data-stu-id="1cd35-126">Diagnostic ID for the error report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1cd35-127"><strong>Fonte</strong></span><span class="sxs-lookup"><span data-stu-id="1cd35-127"><strong>Source</strong></span></span></p></td>
<td><p><span data-ttu-id="1cd35-128">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="1cd35-128">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1cd35-129">Nome do servidor que originou o erro (se o relatório foi enviado de um componente do servidor).</span><span class="sxs-lookup"><span data-stu-id="1cd35-129">Name of server that originated the error (if report was sent from a server component).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1cd35-130"><strong>Aplicação</strong></span><span class="sxs-lookup"><span data-stu-id="1cd35-130"><strong>Application</strong></span></span></p></td>
<td><p><span data-ttu-id="1cd35-131">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="1cd35-131">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1cd35-132">Nome de um aplicativo que originou o erro (se o relatório foi enviado de um componente do servidor).</span><span class="sxs-lookup"><span data-stu-id="1cd35-132">Name of application that originated the error (if report was sent from a server component).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1cd35-133"><strong>Telemetria</strong></span><span class="sxs-lookup"><span data-stu-id="1cd35-133"><strong>TelemetryId</strong></span></span></p></td>
<td><p><span data-ttu-id="1cd35-134">identificador</span><span class="sxs-lookup"><span data-stu-id="1cd35-134">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="1cd35-135">Identificador exclusivo correlacionando as informações da hora de ingresso dos diferentes componentes envolvidos em uma conferência.</span><span class="sxs-lookup"><span data-stu-id="1cd35-135">Unique identifier correlating join time information for the different components involved in a conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1cd35-136"><strong>SessionSetupTime</strong></span><span class="sxs-lookup"><span data-stu-id="1cd35-136"><strong>SessionSetupTime</strong></span></span></p></td>
<td><p><span data-ttu-id="1cd35-137">int</span><span class="sxs-lookup"><span data-stu-id="1cd35-137">int</span></span></p></td>
<td><p><span data-ttu-id="1cd35-138">Tempo (em milissegundos) necessário para que um componentes específico ingresse em uma conferência.</span><span class="sxs-lookup"><span data-stu-id="1cd35-138">Time (in milliseconds) required for a specific component to join a conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1cd35-139"><strong>MsDiagHeader</strong></span><span class="sxs-lookup"><span data-stu-id="1cd35-139"><strong>MsDiagHeader</strong></span></span></p></td>
<td><p><span data-ttu-id="1cd35-140">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="1cd35-140">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="1cd35-141">Informações de erro adicionais.</span><span class="sxs-lookup"><span data-stu-id="1cd35-141">Additional error information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

