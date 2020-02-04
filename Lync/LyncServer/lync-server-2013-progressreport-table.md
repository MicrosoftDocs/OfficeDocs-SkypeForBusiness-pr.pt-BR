---
title: 'Lync Server 2013: Tabela ProgressReport'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ProgressReport table
ms:assetid: 38e5f060-5e9b-4185-87b2-7ef61c4bb75f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425864(v=OCS.15)
ms:contentKeyID: 48183847
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2e1cb7c8e764097af96981220ee74d481b379341
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724811"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="progressreport-table-in-lync-server-2013"></a><span data-ttu-id="d0de1-102">Tabela ProgressReport no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d0de1-102">ProgressReport table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d0de1-103">_**Tópico da última modificação:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="d0de1-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="d0de1-104">Os relatórios de progresso são baseados em dados carregados pelo cliente para o banco de dados após a conclusão de uma chamada ou sessão.</span><span class="sxs-lookup"><span data-stu-id="d0de1-104">Progress reports are based on data uploaded by the client to the database after a call or session is completed.</span></span> <span data-ttu-id="d0de1-105">Os relatórios de progresso serão escritos apenas para chamadas e sessões que o Lync Server 2013 determina que podem ser úteis para fins de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="d0de1-105">Progress reports will be written only for calls and sessions that Lync Server 2013 determines might be useful for diagnostic purposes.</span></span>

<span data-ttu-id="d0de1-106">Os campos ErrorTime, ErrorReportSeq e ProgressReportSeq não se referem necessariamente a erros, mas a mensagens que indicam o status de chamadas ou mensagens.</span><span class="sxs-lookup"><span data-stu-id="d0de1-106">The ErrorTime, ErrorReportSeq and ProgressReportSeq fields don’t necessarily refer to errors but to messages that indicate the status of calls or messages.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d0de1-107">Coluna</span><span class="sxs-lookup"><span data-stu-id="d0de1-107">Column</span></span></th>
<th><span data-ttu-id="d0de1-108">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="d0de1-108">Data Type</span></span></th>
<th><span data-ttu-id="d0de1-109">Chave/índice</span><span class="sxs-lookup"><span data-stu-id="d0de1-109">Key/Index</span></span></th>
<th><span data-ttu-id="d0de1-110">Detalhes</span><span class="sxs-lookup"><span data-stu-id="d0de1-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d0de1-111"><strong>ErrorTime</strong></span><span class="sxs-lookup"><span data-stu-id="d0de1-111"><strong>ErrorTime</strong></span></span></p></td>
<td><p><span data-ttu-id="d0de1-112">datetime</span><span class="sxs-lookup"><span data-stu-id="d0de1-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="d0de1-113">Primário, estrangeiro</span><span class="sxs-lookup"><span data-stu-id="d0de1-113">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="d0de1-114">Data e hora do relatório de erro de progresso que contém este relatório de progresso.</span><span class="sxs-lookup"><span data-stu-id="d0de1-114">Date and time of the progress error report that contains this progress report.</span></span> <span data-ttu-id="d0de1-115">Consulte a <a href="lync-server-2013-errorreport-table.md">tabela errorreport no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="d0de1-115">See the <a href="lync-server-2013-errorreport-table.md">ErrorReport table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0de1-116"><strong>ErrorID</strong></span><span class="sxs-lookup"><span data-stu-id="d0de1-116"><strong>ErrorId</strong></span></span></p></td>
<td><p><span data-ttu-id="d0de1-117">int</span><span class="sxs-lookup"><span data-stu-id="d0de1-117">int</span></span></p></td>
<td><p><span data-ttu-id="d0de1-118">Primário, estrangeiro</span><span class="sxs-lookup"><span data-stu-id="d0de1-118">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="d0de1-119">Número de identificação usado em conjunto com ErrorTime, ProgressReportSeq para identificar exclusivamente um relatório de progresso.</span><span class="sxs-lookup"><span data-stu-id="d0de1-119">ID number used in conjunction with ErrorTime, ProgressReportSeq to uniquely identify a progress report.</span></span> <span data-ttu-id="d0de1-120">Consulte a <a href="lync-server-2013-errorreport-table.md">tabela errorreport no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="d0de1-120">See the <a href="lync-server-2013-errorreport-table.md">ErrorReport table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0de1-121"><strong>ErrorReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="d0de1-121"><strong>ErrorReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="d0de1-122">int</span><span class="sxs-lookup"><span data-stu-id="d0de1-122">int</span></span></p></td>
<td><p><span data-ttu-id="d0de1-123">Primário, estrangeiro</span><span class="sxs-lookup"><span data-stu-id="d0de1-123">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="d0de1-124">Número de identificação que identifica o relatório de erros.</span><span class="sxs-lookup"><span data-stu-id="d0de1-124">ID number that identifies the error report.</span></span> <span data-ttu-id="d0de1-125">ErrorReporSeq é usado em conjunto com ErrorTime para identificar com exclusividade um relatório de erro.</span><span class="sxs-lookup"><span data-stu-id="d0de1-125">ErrorReporSeq is used in conjunction with ErrorTime to uniquely identify an error report.</span></span> <span data-ttu-id="d0de1-126">Consulte a <a href="lync-server-2013-errorreport-table.md">tabela errorreport no Lync Server 2013</a> para obter mais informações</span><span class="sxs-lookup"><span data-stu-id="d0de1-126">See the <a href="lync-server-2013-errorreport-table.md">ErrorReport table in Lync Server 2013</a> for more information</span></span></p>
<p><span data-ttu-id="d0de1-127">Este campo foi apresentado no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d0de1-127">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0de1-128"><strong>ProgressReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="d0de1-128"><strong>ProgressReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="d0de1-129">int</span><span class="sxs-lookup"><span data-stu-id="d0de1-129">int</span></span></p></td>
<td><p><span data-ttu-id="d0de1-130">Primária</span><span class="sxs-lookup"><span data-stu-id="d0de1-130">Primary</span></span></p></td>
<td><p><span data-ttu-id="d0de1-131">Número de identificação para identificar o relatório de progresso.</span><span class="sxs-lookup"><span data-stu-id="d0de1-131">ID number to identify the progress report.</span></span> <span data-ttu-id="d0de1-132">Usado em conjunto com ErrorTime e ErrorReportSeq para identificar com exclusividade um relatório de progresso.</span><span class="sxs-lookup"><span data-stu-id="d0de1-132">Used in conjunction with ErrorTime and ErrorReportSeq to uniquely identify a progress report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0de1-133"><strong>MsDiagId</strong></span><span class="sxs-lookup"><span data-stu-id="d0de1-133"><strong>MsDiagId</strong></span></span></p></td>
<td><p><span data-ttu-id="d0de1-134">int</span><span class="sxs-lookup"><span data-stu-id="d0de1-134">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d0de1-135">ID de diagnóstico do relatório de progresso.</span><span class="sxs-lookup"><span data-stu-id="d0de1-135">Diagnostic ID of the progress report.</span></span></p>
<p><span data-ttu-id="d0de1-136">Este campo foi apresentado no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d0de1-136">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0de1-137"><strong>SourceID</strong></span><span class="sxs-lookup"><span data-stu-id="d0de1-137"><strong>SourceId</strong></span></span></p></td>
<td><p><span data-ttu-id="d0de1-138">int</span><span class="sxs-lookup"><span data-stu-id="d0de1-138">int</span></span></p></td>
<td><p><span data-ttu-id="d0de1-139">Exterior</span><span class="sxs-lookup"><span data-stu-id="d0de1-139">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d0de1-140">Servidor que enviou o relatório de erro (se o relatório foi enviado de um componente de servidor).</span><span class="sxs-lookup"><span data-stu-id="d0de1-140">Server that sent the error report (if the report was sent from a server component).</span></span> <span data-ttu-id="d0de1-141">Consulte a <a href="lync-server-2013-servers-table.md">tabela servidores no Lync Server 2013</a> para obter mais informações. Este campo foi apresentado no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d0de1-141">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0de1-142"><strong>ApplicationId</strong></span><span class="sxs-lookup"><span data-stu-id="d0de1-142"><strong>ApplicationId</strong></span></span></p></td>
<td><p><span data-ttu-id="d0de1-143">int</span><span class="sxs-lookup"><span data-stu-id="d0de1-143">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d0de1-144">O processo do Lync Server no qual o relatório se encontra.</span><span class="sxs-lookup"><span data-stu-id="d0de1-144">The Lync Server process that the report is about.</span></span> <span data-ttu-id="d0de1-145">Consulte a tabela de aplicativos para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="d0de1-145">See the Application Table for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0de1-146"><strong>Detalhe</strong></span><span class="sxs-lookup"><span data-stu-id="d0de1-146"><strong>Detail</strong></span></span></p></td>
<td><p><span data-ttu-id="d0de1-147">imagem</span><span class="sxs-lookup"><span data-stu-id="d0de1-147">image</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d0de1-148">Detalhes do relatório de progresso armazenados em formato binário para economizar espaço. Esses dados podem ser convertidos em um formato de texto usando esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="d0de1-148">Progress report details, stored in binary format to save space.This data can be converted to text format using this syntax:</span></span></p>
<p><span data-ttu-id="d0de1-149">Cast (Cast (detalhes como varbinary (max)) as varchar (max))</span><span class="sxs-lookup"><span data-stu-id="d0de1-149">cast(cast(Detail as varbinary(max)) as varchar(max))</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0de1-150"><strong>Telemetria</strong></span><span class="sxs-lookup"><span data-stu-id="d0de1-150"><strong>TelemetryId</strong></span></span></p></td>
<td><p><span data-ttu-id="d0de1-151">Identificador</span><span class="sxs-lookup"><span data-stu-id="d0de1-151">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d0de1-152">Identificador exclusivo que correlaciona as informações de tempo de junção para os diferentes componentes envolvidos em uma conferência.</span><span class="sxs-lookup"><span data-stu-id="d0de1-152">Unique identifier that correlates join time information for the different components involved in a conference.</span></span></p>
<p><span data-ttu-id="d0de1-153">Este campo foi apresentado no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d0de1-153">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0de1-154"><strong>SessionSetupTime</strong></span><span class="sxs-lookup"><span data-stu-id="d0de1-154"><strong>SessionSetupTime</strong></span></span></p></td>
<td><p><span data-ttu-id="d0de1-155">int</span><span class="sxs-lookup"><span data-stu-id="d0de1-155">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d0de1-156">Tempo (em milissegundos) para um componente específico para ingressar em uma conferência.</span><span class="sxs-lookup"><span data-stu-id="d0de1-156">Time (in milliseconds) for a specific component to join a conference.</span></span></p>
<p><span data-ttu-id="d0de1-157">Este campo foi apresentado no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d0de1-157">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

