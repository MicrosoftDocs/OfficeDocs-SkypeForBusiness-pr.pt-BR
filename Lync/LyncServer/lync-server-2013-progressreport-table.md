---
title: 'Lync Server 2013: tabela ProgressReport'
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
ms.openlocfilehash: c92adf48a09f83c3c3dec18f91e4aadc3a3cbd39
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48513228"
---
# <a name="progressreport-table-in-lync-server-2013"></a><span data-ttu-id="a394f-102">Tabela ProgressReport no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a394f-102">ProgressReport table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a394f-103">_**Última modificação do tópico:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="a394f-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="a394f-104">Relatórios de andamento são baseados nos dados carregados pelo cliente no banco de dados após a conclusão de uma chamada ou sessão.</span><span class="sxs-lookup"><span data-stu-id="a394f-104">Progress reports are based on data uploaded by the client to the database after a call or session is completed.</span></span> <span data-ttu-id="a394f-105">Os relatórios de progresso será gravados somente para chamadas e sessões que o Lync Server 2013 determina como úteis para diagnósticos.</span><span class="sxs-lookup"><span data-stu-id="a394f-105">Progress reports will be written only for calls and sessions that Lync Server 2013 determines might be useful for diagnostic purposes.</span></span>

<span data-ttu-id="a394f-106">Os campos ErrorTime, ErrorReportSeq e ProgressReportSeq não se referem necessariamente aos erros, mas a mensagens que indicam o status das chamadas ou mensagens.</span><span class="sxs-lookup"><span data-stu-id="a394f-106">The ErrorTime, ErrorReportSeq and ProgressReportSeq fields don’t necessarily refer to errors but to messages that indicate the status of calls or messages.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a394f-107">Coluna</span><span class="sxs-lookup"><span data-stu-id="a394f-107">Column</span></span></th>
<th><span data-ttu-id="a394f-108">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="a394f-108">Data Type</span></span></th>
<th><span data-ttu-id="a394f-109">Chave/índice</span><span class="sxs-lookup"><span data-stu-id="a394f-109">Key/Index</span></span></th>
<th><span data-ttu-id="a394f-110">Detalhes</span><span class="sxs-lookup"><span data-stu-id="a394f-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a394f-111"><strong>ErrorTime</strong></span><span class="sxs-lookup"><span data-stu-id="a394f-111"><strong>ErrorTime</strong></span></span></p></td>
<td><p><span data-ttu-id="a394f-112">datetime</span><span class="sxs-lookup"><span data-stu-id="a394f-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="a394f-113">Primário, externo</span><span class="sxs-lookup"><span data-stu-id="a394f-113">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="a394f-114">Data e hora do relatório de erros de andamento.</span><span class="sxs-lookup"><span data-stu-id="a394f-114">Date and time of the progress error report that contains this progress report.</span></span> <span data-ttu-id="a394f-115">Consulte a <a href="lync-server-2013-errorreport-table.md">tabela errorreport no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="a394f-115">See the <a href="lync-server-2013-errorreport-table.md">ErrorReport table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a394f-116"><strong>ErrorID</strong></span><span class="sxs-lookup"><span data-stu-id="a394f-116"><strong>ErrorId</strong></span></span></p></td>
<td><p><span data-ttu-id="a394f-117">int</span><span class="sxs-lookup"><span data-stu-id="a394f-117">int</span></span></p></td>
<td><p><span data-ttu-id="a394f-118">Primário, externo</span><span class="sxs-lookup"><span data-stu-id="a394f-118">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="a394f-119">Número de ID usado junto com o ErrorTime, ProgressReportSeq para identificar exclusivamente um relatório de andamento.</span><span class="sxs-lookup"><span data-stu-id="a394f-119">ID number used in conjunction with ErrorTime, ProgressReportSeq to uniquely identify a progress report.</span></span> <span data-ttu-id="a394f-120">Consulte a <a href="lync-server-2013-errorreport-table.md">tabela errorreport no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="a394f-120">See the <a href="lync-server-2013-errorreport-table.md">ErrorReport table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a394f-121"><strong>ErrorReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="a394f-121"><strong>ErrorReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="a394f-122">int</span><span class="sxs-lookup"><span data-stu-id="a394f-122">int</span></span></p></td>
<td><p><span data-ttu-id="a394f-123">Primário, externo</span><span class="sxs-lookup"><span data-stu-id="a394f-123">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="a394f-124">Número de ID que identifica o relatório de erros.</span><span class="sxs-lookup"><span data-stu-id="a394f-124">ID number that identifies the error report.</span></span> <span data-ttu-id="a394f-125">O ErrorReporSeq é usado em conjunto com o ErrorTime para identificar exclusivamente um relatório de erros.</span><span class="sxs-lookup"><span data-stu-id="a394f-125">ErrorReporSeq is used in conjunction with ErrorTime to uniquely identify an error report.</span></span> <span data-ttu-id="a394f-126">Consulte a <a href="lync-server-2013-errorreport-table.md">tabela errorreport no Lync Server 2013</a> para obter mais informações</span><span class="sxs-lookup"><span data-stu-id="a394f-126">See the <a href="lync-server-2013-errorreport-table.md">ErrorReport table in Lync Server 2013</a> for more information</span></span></p>
<p><span data-ttu-id="a394f-127">Este campo foi introduzido no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a394f-127">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a394f-128"><strong>ProgressReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="a394f-128"><strong>ProgressReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="a394f-129">int</span><span class="sxs-lookup"><span data-stu-id="a394f-129">int</span></span></p></td>
<td><p><span data-ttu-id="a394f-130">Primário</span><span class="sxs-lookup"><span data-stu-id="a394f-130">Primary</span></span></p></td>
<td><p><span data-ttu-id="a394f-p105">Número de ID para identificar o relatório de andamento. Usado junto com ErrorTime e ErrorReportSeq para identificar exclusivamente um relatório de andamento.</span><span class="sxs-lookup"><span data-stu-id="a394f-p105">ID number to identify the progress report. Used in conjunction with ErrorTime and ErrorReportSeq to uniquely identify a progress report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a394f-133"><strong>MsDiagId</strong></span><span class="sxs-lookup"><span data-stu-id="a394f-133"><strong>MsDiagId</strong></span></span></p></td>
<td><p><span data-ttu-id="a394f-134">int</span><span class="sxs-lookup"><span data-stu-id="a394f-134">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a394f-135">ID do diagnóstico do relatório de andamento.</span><span class="sxs-lookup"><span data-stu-id="a394f-135">Diagnostic ID of the progress report.</span></span></p>
<p><span data-ttu-id="a394f-136">Este campo foi introduzido no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a394f-136">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a394f-137"><strong>SourceId</strong></span><span class="sxs-lookup"><span data-stu-id="a394f-137"><strong>SourceId</strong></span></span></p></td>
<td><p><span data-ttu-id="a394f-138">int</span><span class="sxs-lookup"><span data-stu-id="a394f-138">int</span></span></p></td>
<td><p><span data-ttu-id="a394f-139">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="a394f-139">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a394f-140">Servidor que enviou o relatório de erros (se o relatório foi enviado de um componente do servidor), Consulte a Servers Table para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="a394f-140">Server that sent the error report (if the report was sent from a server component).</span></span> <span data-ttu-id="a394f-141">Consulte a <a href="lync-server-2013-servers-table.md">tabela de servidores no Lync Server 2013</a> para obter mais informações. Este campo foi introduzido no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a394f-141">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a394f-142"><strong>ApplicationId</strong></span><span class="sxs-lookup"><span data-stu-id="a394f-142"><strong>ApplicationId</strong></span></span></p></td>
<td><p><span data-ttu-id="a394f-143">int</span><span class="sxs-lookup"><span data-stu-id="a394f-143">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a394f-p107">O processo do Lync Server do qual o relatório trata. Consulte a Application Table para obter mais informações</span><span class="sxs-lookup"><span data-stu-id="a394f-p107">The Lync Server process that the report is about. See the Application Table for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a394f-146"><strong>Ver os detalhes</strong></span><span class="sxs-lookup"><span data-stu-id="a394f-146"><strong>Detail</strong></span></span></p></td>
<td><p><span data-ttu-id="a394f-147">imagem</span><span class="sxs-lookup"><span data-stu-id="a394f-147">image</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a394f-148">Detalhes do relatório de andamento armazenados em formato binário para economizar espaço. Esses dados podem ser convertidos em formato de texto usando essa sintaxe:</span><span class="sxs-lookup"><span data-stu-id="a394f-148">Progress report details, stored in binary format to save space.This data can be converted to text format using this syntax:</span></span></p>
<p><span data-ttu-id="a394f-149">cast(cast(Detail as varbinary(max)) as varchar(max))</span><span class="sxs-lookup"><span data-stu-id="a394f-149">cast(cast(Detail as varbinary(max)) as varchar(max))</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a394f-150"><strong>Telemetria</strong></span><span class="sxs-lookup"><span data-stu-id="a394f-150"><strong>TelemetryId</strong></span></span></p></td>
<td><p><span data-ttu-id="a394f-151">Identificador</span><span class="sxs-lookup"><span data-stu-id="a394f-151">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a394f-152">Identificador exclusivo que correlaciona as informações da hora de ingresso com os diferentes componentes envolvidos em uma conferência.</span><span class="sxs-lookup"><span data-stu-id="a394f-152">Unique identifier that correlates join time information for the different components involved in a conference.</span></span></p>
<p><span data-ttu-id="a394f-153">Este campo foi introduzido no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a394f-153">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a394f-154"><strong>SessionSetupTime</strong></span><span class="sxs-lookup"><span data-stu-id="a394f-154"><strong>SessionSetupTime</strong></span></span></p></td>
<td><p><span data-ttu-id="a394f-155">int</span><span class="sxs-lookup"><span data-stu-id="a394f-155">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a394f-156">Tempo (em milissegundos) para que um componente específico ingresse em uma conferência.</span><span class="sxs-lookup"><span data-stu-id="a394f-156">Time (in milliseconds) for a specific component to join a conference.</span></span></p>
<p><span data-ttu-id="a394f-157">Este campo foi introduzido no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a394f-157">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

