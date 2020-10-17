---
title: 'Lync Server 2013: sub-relatório de Resumo de conferências'
description: 'Lync Server 2013: sub-relatório de Resumo de conferências.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conference Summary Subreport
ms:assetid: 2fc1d2bf-34f5-4093-a6e2-250ec1f1b004
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204779(v=OCS.15)
ms:contentKeyID: 48183742
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0612ce1adb8a6b0fdea5e3bf70b88346f7c08044
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550687"
---
# <a name="conference-summary-subreport-in-lync-server-2013"></a><span data-ttu-id="79632-103">Sub-relatório de Resumo de conferências no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="79632-103">Conference Summary Subreport in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="79632-104">_**Última modificação do tópico:** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="79632-104">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="79632-p101">O Subrelatório de Resumo da Conferência oferece uma visão geral das sessões de conferência em falha. Estas sessões em falha são detalhadas pelo tipo de sessão: Sessão de foco e sessões MCU.</span><span class="sxs-lookup"><span data-stu-id="79632-p101">The Conference Summary Subreport provides an overall view of failed conference sessions. These failed sessions are further broken down by session type: Focus sessions and MCU sessions.</span></span>

<div>

## <a name="filters"></a><span data-ttu-id="79632-107">Filtros</span><span class="sxs-lookup"><span data-stu-id="79632-107">Filters</span></span>

<span data-ttu-id="79632-p102">Os filtros oferecem uma forma de retornar um conjunto de dados mais detalhado ou para exibir os dados retornados de formas diferentes. A tabela a seguir lista os filtros que você pode usar com o Subrelatório de Resumo da Conferência.</span><span class="sxs-lookup"><span data-stu-id="79632-p102">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. The following table lists the filters that you can use with the Conference Summary Subreport.</span></span>

### <a name="conference-summary-subreport-filters"></a><span data-ttu-id="79632-110">Filtros do Subrelatório de Resumo da Conferência</span><span class="sxs-lookup"><span data-stu-id="79632-110">Conference Summary Subreport Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="79632-111">Nome</span><span class="sxs-lookup"><span data-stu-id="79632-111">Name</span></span></th>
<th><span data-ttu-id="79632-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="79632-112">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="79632-113"><strong>De</strong></span><span class="sxs-lookup"><span data-stu-id="79632-113"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="79632-p103">Data/hora inicial para o intervalo de tempo. Para exibir os dados por hora, insira a data e hora inicial como a seguir:</span><span class="sxs-lookup"><span data-stu-id="79632-p103">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="79632-116">7/7/2012 13:00 horas</span><span class="sxs-lookup"><span data-stu-id="79632-116">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="79632-p104">Se você não inserir uma hora inicial, o relatório começa automaticamente as 12:00 AM no dia especificado. Para exibir os dados por dia, insira apenas a data:</span><span class="sxs-lookup"><span data-stu-id="79632-p104">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="79632-119">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="79632-119">7/7/2012</span></span></p>
<p><span data-ttu-id="79632-120">Para exibir por semana ou mês, insira uma data que está dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):</span><span class="sxs-lookup"><span data-stu-id="79632-120">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="79632-121">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="79632-121">7/3/2012</span></span></p>
<p><span data-ttu-id="79632-122">As semanas são sempre de domingo a sábado.</span><span class="sxs-lookup"><span data-stu-id="79632-122">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="79632-123"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="79632-123"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="79632-p105">Data/hora final para o intervalo de tempo. Para exibir os dados por hora, insira a data e hora final como a seguir:</span><span class="sxs-lookup"><span data-stu-id="79632-p105">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="79632-126">7/7/2012 13:00 horas</span><span class="sxs-lookup"><span data-stu-id="79632-126">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="79632-p106">Se você não inserir uma hora final, o relatório termina automaticamente as 12:00 AM no dia especificado. Para exibir os dados por dia, insira apenas a data:</span><span class="sxs-lookup"><span data-stu-id="79632-p106">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="79632-129">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="79632-129">7/7/2012</span></span></p>
<p><span data-ttu-id="79632-130">Para exibir por semana ou mês, insira uma data que está dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):</span><span class="sxs-lookup"><span data-stu-id="79632-130">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="79632-131">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="79632-131">7/3/2012</span></span></p>
<p><span data-ttu-id="79632-132">As semanas sempre correm do domingo até sábado.</span><span class="sxs-lookup"><span data-stu-id="79632-132">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="79632-133"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="79632-133"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="79632-p107">FQDN do pool do Registrador ou Servidor de Borda. É possível selecionar um pool individual ou clicar em <strong>[Todos]</strong> para exibir os dados de todos os pools. Esta lista suspensa é preenchida automaticamente para você com base nos registros do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="79632-p107">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="79632-137">Métrica</span><span class="sxs-lookup"><span data-stu-id="79632-137">Metrics</span></span>

<span data-ttu-id="79632-138">A tabela a seguir lista as informações fornecidas no Subrelatório de Resumo de Conferência.</span><span class="sxs-lookup"><span data-stu-id="79632-138">The following table lists the information provided in the Conference Summary Subreport.</span></span>

### <a name="conference-summary-subreport-metrics"></a><span data-ttu-id="79632-139">Métricas do Subrelatório de Resumo da Conferência</span><span class="sxs-lookup"><span data-stu-id="79632-139">Conference Summary Subreport Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="79632-140">Nome</span><span class="sxs-lookup"><span data-stu-id="79632-140">Name</span></span></th>
<th><span data-ttu-id="79632-141">É possível classificar este item?</span><span class="sxs-lookup"><span data-stu-id="79632-141">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="79632-142">Descrição</span><span class="sxs-lookup"><span data-stu-id="79632-142">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="79632-143"><strong>Total de conferências</strong></span><span class="sxs-lookup"><span data-stu-id="79632-143"><strong>Total conferences</strong></span></span></p></td>
<td><p><span data-ttu-id="79632-144">Não</span><span class="sxs-lookup"><span data-stu-id="79632-144">No</span></span></p></td>
<td><p><span data-ttu-id="79632-145">Número total de conferências realizadas.</span><span class="sxs-lookup"><span data-stu-id="79632-145">Total number of conferences held.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="79632-146"><strong>Total de sessões de conferência</strong></span><span class="sxs-lookup"><span data-stu-id="79632-146"><strong>Total conference sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="79632-147">Não</span><span class="sxs-lookup"><span data-stu-id="79632-147">No</span></span></p></td>
<td><p><span data-ttu-id="79632-p108">Número total de sessões de conferência. Uma única conferência pode ter várias sessões; por exemplo, uma conferência pode incluir uma sessão Foco e uma sessão MCU.</span><span class="sxs-lookup"><span data-stu-id="79632-p108">Total number of conference sessions. A single conference can have multiple sessions; for example, a conference might include both a Focus session and an MCU session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="79632-150"><strong>Taxa de falha de sessão geral</strong></span><span class="sxs-lookup"><span data-stu-id="79632-150"><strong>Overall session failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="79632-151">Não</span><span class="sxs-lookup"><span data-stu-id="79632-151">No</span></span></p></td>
<td><p><span data-ttu-id="79632-152">Porcentagem de todas as conferências que falharam.</span><span class="sxs-lookup"><span data-stu-id="79632-152">Percentage of all conferences that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="79632-153"><strong>Sessões de foco</strong></span><span class="sxs-lookup"><span data-stu-id="79632-153"><strong>Focus sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="79632-154">Não</span><span class="sxs-lookup"><span data-stu-id="79632-154">No</span></span></p></td>
<td><p><span data-ttu-id="79632-155">Número total de sessões de Foco.</span><span class="sxs-lookup"><span data-stu-id="79632-155">Total number of Focus sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="79632-156"><strong>Taxa de falha do foco</strong></span><span class="sxs-lookup"><span data-stu-id="79632-156"><strong>Focus failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="79632-157">Não</span><span class="sxs-lookup"><span data-stu-id="79632-157">No</span></span></p></td>
<td><p><span data-ttu-id="79632-158">Porcentagem das sessões de Foco que falharam.</span><span class="sxs-lookup"><span data-stu-id="79632-158">Percentage of Focus sessions that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="79632-159">Sessões MCU</span><span class="sxs-lookup"><span data-stu-id="79632-159">MCU sessions</span></span></p></td>
<td><p><span data-ttu-id="79632-160">Não</span><span class="sxs-lookup"><span data-stu-id="79632-160">No</span></span></p></td>
<td><p><span data-ttu-id="79632-161">Número total de sessões MCU.</span><span class="sxs-lookup"><span data-stu-id="79632-161">Total number of MCU sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="79632-162"><strong>Taxa de falha MCU</strong></span><span class="sxs-lookup"><span data-stu-id="79632-162"><strong>MCU failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="79632-163">Não</span><span class="sxs-lookup"><span data-stu-id="79632-163">No</span></span></p></td>
<td><p><span data-ttu-id="79632-164">Porcentagem de sessões MCU que falharam.</span><span class="sxs-lookup"><span data-stu-id="79632-164">Percentage of MCU sessions that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="79632-165"><strong>Sessões MCU por modalidade</strong></span><span class="sxs-lookup"><span data-stu-id="79632-165"><strong>MCU sessions by modality</strong></span></span></p></td>
<td><p><span data-ttu-id="79632-166">Não</span><span class="sxs-lookup"><span data-stu-id="79632-166">No</span></span></p></td>
<td><p><span data-ttu-id="79632-167">Número total de sessões MCU, agrupado por modalidade (por exemplo, conferência IM).</span><span class="sxs-lookup"><span data-stu-id="79632-167">Total number of MCU sessions, grouped by modality (for example, IM conferencing).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="79632-168"><strong>Taxa de falha por modalidade</strong></span><span class="sxs-lookup"><span data-stu-id="79632-168"><strong>Failure rate by modality</strong></span></span></p></td>
<td><p><span data-ttu-id="79632-169">Não</span><span class="sxs-lookup"><span data-stu-id="79632-169">No</span></span></p></td>
<td><p><span data-ttu-id="79632-170">Porcentagem de sessões MCU que falharam, agrupadas por modalidade (por exemplo, conferência de IM).</span><span class="sxs-lookup"><span data-stu-id="79632-170">Percentage of MCU sessions that failed, grouped by modality (for example, IM conferencing).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

