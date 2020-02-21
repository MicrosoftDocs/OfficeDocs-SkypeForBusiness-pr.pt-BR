---
title: 'Lync Server 2013: sub-relatório de Resumo de conferências'
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
ms.openlocfilehash: e8cc92efe91b1618cd6d0f4f9cdaaf6cdf09730d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213217"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="conference-summary-subreport-in-lync-server-2013"></a><span data-ttu-id="dfb5f-102">Sub-relatório de Resumo de conferências no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dfb5f-102">Conference Summary Subreport in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dfb5f-103">_**Última modificação do tópico:** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="dfb5f-103">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="dfb5f-p101">O Subrelatório de Resumo da Conferência oferece uma visão geral das sessões de conferência em falha. Estas sessões em falha são detalhadas pelo tipo de sessão: Sessão de foco e sessões MCU.</span><span class="sxs-lookup"><span data-stu-id="dfb5f-p101">The Conference Summary Subreport provides an overall view of failed conference sessions. These failed sessions are further broken down by session type: Focus sessions and MCU sessions.</span></span>

<div>

## <a name="filters"></a><span data-ttu-id="dfb5f-106">Filtros</span><span class="sxs-lookup"><span data-stu-id="dfb5f-106">Filters</span></span>

<span data-ttu-id="dfb5f-p102">Os filtros oferecem uma forma de retornar um conjunto de dados mais detalhado ou para exibir os dados retornados de formas diferentes. A tabela a seguir lista os filtros que você pode usar com o Subrelatório de Resumo da Conferência.</span><span class="sxs-lookup"><span data-stu-id="dfb5f-p102">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. The following table lists the filters that you can use with the Conference Summary Subreport.</span></span>

### <a name="conference-summary-subreport-filters"></a><span data-ttu-id="dfb5f-109">Filtros do Subrelatório de Resumo da Conferência</span><span class="sxs-lookup"><span data-stu-id="dfb5f-109">Conference Summary Subreport Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dfb5f-110">Nome</span><span class="sxs-lookup"><span data-stu-id="dfb5f-110">Name</span></span></th>
<th><span data-ttu-id="dfb5f-111">Descrição</span><span class="sxs-lookup"><span data-stu-id="dfb5f-111">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dfb5f-112"><strong>De</strong></span><span class="sxs-lookup"><span data-stu-id="dfb5f-112"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="dfb5f-p103">Data/hora inicial para o intervalo de tempo. Para exibir os dados por hora, insira a data e hora inicial como a seguir:</span><span class="sxs-lookup"><span data-stu-id="dfb5f-p103">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="dfb5f-115">7/7/2012 13:00 horas</span><span class="sxs-lookup"><span data-stu-id="dfb5f-115">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="dfb5f-p104">Se você não inserir uma hora inicial, o relatório começa automaticamente as 12:00 AM no dia especificado. Para exibir os dados por dia, insira apenas a data:</span><span class="sxs-lookup"><span data-stu-id="dfb5f-p104">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="dfb5f-118">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="dfb5f-118">7/7/2012</span></span></p>
<p><span data-ttu-id="dfb5f-119">Para exibir por semana ou mês, insira uma data que está dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):</span><span class="sxs-lookup"><span data-stu-id="dfb5f-119">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="dfb5f-120">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="dfb5f-120">7/3/2012</span></span></p>
<p><span data-ttu-id="dfb5f-121">As semanas são sempre de domingo a sábado.</span><span class="sxs-lookup"><span data-stu-id="dfb5f-121">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dfb5f-122"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="dfb5f-122"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="dfb5f-p105">Data/hora final para o intervalo de tempo. Para exibir os dados por hora, insira a data e hora final como a seguir:</span><span class="sxs-lookup"><span data-stu-id="dfb5f-p105">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="dfb5f-125">7/7/2012 13:00 horas</span><span class="sxs-lookup"><span data-stu-id="dfb5f-125">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="dfb5f-p106">Se você não inserir uma hora final, o relatório termina automaticamente as 12:00 AM no dia especificado. Para exibir os dados por dia, insira apenas a data:</span><span class="sxs-lookup"><span data-stu-id="dfb5f-p106">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="dfb5f-128">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="dfb5f-128">7/7/2012</span></span></p>
<p><span data-ttu-id="dfb5f-129">Para exibir por semana ou mês, insira uma data que está dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):</span><span class="sxs-lookup"><span data-stu-id="dfb5f-129">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="dfb5f-130">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="dfb5f-130">7/3/2012</span></span></p>
<p><span data-ttu-id="dfb5f-131">As semanas sempre correm do domingo até sábado.</span><span class="sxs-lookup"><span data-stu-id="dfb5f-131">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dfb5f-132"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="dfb5f-132"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="dfb5f-p107">FQDN do pool do Registrador ou Servidor de Borda. É possível selecionar um pool individual ou clicar em <strong>[Todos]</strong> para exibir os dados de todos os pools. Esta lista suspensa é preenchida automaticamente para você com base nos registros do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="dfb5f-p107">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="dfb5f-136">Métricas</span><span class="sxs-lookup"><span data-stu-id="dfb5f-136">Metrics</span></span>

<span data-ttu-id="dfb5f-137">A tabela a seguir lista as informações fornecidas no Subrelatório de Resumo de Conferência.</span><span class="sxs-lookup"><span data-stu-id="dfb5f-137">The following table lists the information provided in the Conference Summary Subreport.</span></span>

### <a name="conference-summary-subreport-metrics"></a><span data-ttu-id="dfb5f-138">Métricas do Subrelatório de Resumo da Conferência</span><span class="sxs-lookup"><span data-stu-id="dfb5f-138">Conference Summary Subreport Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dfb5f-139">Nome</span><span class="sxs-lookup"><span data-stu-id="dfb5f-139">Name</span></span></th>
<th><span data-ttu-id="dfb5f-140">É possível classificar este item?</span><span class="sxs-lookup"><span data-stu-id="dfb5f-140">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="dfb5f-141">Descrição</span><span class="sxs-lookup"><span data-stu-id="dfb5f-141">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dfb5f-142"><strong>Total de conferências</strong></span><span class="sxs-lookup"><span data-stu-id="dfb5f-142"><strong>Total conferences</strong></span></span></p></td>
<td><p><span data-ttu-id="dfb5f-143">Não</span><span class="sxs-lookup"><span data-stu-id="dfb5f-143">No</span></span></p></td>
<td><p><span data-ttu-id="dfb5f-144">Número total de conferências realizadas.</span><span class="sxs-lookup"><span data-stu-id="dfb5f-144">Total number of conferences held.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dfb5f-145"><strong>Total de sessões de conferência</strong></span><span class="sxs-lookup"><span data-stu-id="dfb5f-145"><strong>Total conference sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="dfb5f-146">Não</span><span class="sxs-lookup"><span data-stu-id="dfb5f-146">No</span></span></p></td>
<td><p><span data-ttu-id="dfb5f-p108">Número total de sessões de conferência. Uma única conferência pode ter várias sessões; por exemplo, uma conferência pode incluir uma sessão Foco e uma sessão MCU.</span><span class="sxs-lookup"><span data-stu-id="dfb5f-p108">Total number of conference sessions. A single conference can have multiple sessions; for example, a conference might include both a Focus session and an MCU session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dfb5f-149"><strong>Taxa de falha de sessão geral</strong></span><span class="sxs-lookup"><span data-stu-id="dfb5f-149"><strong>Overall session failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="dfb5f-150">Não</span><span class="sxs-lookup"><span data-stu-id="dfb5f-150">No</span></span></p></td>
<td><p><span data-ttu-id="dfb5f-151">Porcentagem de todas as conferências que falharam.</span><span class="sxs-lookup"><span data-stu-id="dfb5f-151">Percentage of all conferences that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dfb5f-152"><strong>Sessões de foco</strong></span><span class="sxs-lookup"><span data-stu-id="dfb5f-152"><strong>Focus sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="dfb5f-153">Não</span><span class="sxs-lookup"><span data-stu-id="dfb5f-153">No</span></span></p></td>
<td><p><span data-ttu-id="dfb5f-154">Número total de sessões de Foco.</span><span class="sxs-lookup"><span data-stu-id="dfb5f-154">Total number of Focus sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dfb5f-155"><strong>Taxa de falha do foco</strong></span><span class="sxs-lookup"><span data-stu-id="dfb5f-155"><strong>Focus failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="dfb5f-156">Não</span><span class="sxs-lookup"><span data-stu-id="dfb5f-156">No</span></span></p></td>
<td><p><span data-ttu-id="dfb5f-157">Porcentagem das sessões de Foco que falharam.</span><span class="sxs-lookup"><span data-stu-id="dfb5f-157">Percentage of Focus sessions that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dfb5f-158">Sessões MCU</span><span class="sxs-lookup"><span data-stu-id="dfb5f-158">MCU sessions</span></span></p></td>
<td><p><span data-ttu-id="dfb5f-159">Não</span><span class="sxs-lookup"><span data-stu-id="dfb5f-159">No</span></span></p></td>
<td><p><span data-ttu-id="dfb5f-160">Número total de sessões MCU.</span><span class="sxs-lookup"><span data-stu-id="dfb5f-160">Total number of MCU sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dfb5f-161"><strong>Taxa de falha MCU</strong></span><span class="sxs-lookup"><span data-stu-id="dfb5f-161"><strong>MCU failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="dfb5f-162">Não</span><span class="sxs-lookup"><span data-stu-id="dfb5f-162">No</span></span></p></td>
<td><p><span data-ttu-id="dfb5f-163">Porcentagem de sessões MCU que falharam.</span><span class="sxs-lookup"><span data-stu-id="dfb5f-163">Percentage of MCU sessions that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dfb5f-164"><strong>Sessões MCU por modalidade</strong></span><span class="sxs-lookup"><span data-stu-id="dfb5f-164"><strong>MCU sessions by modality</strong></span></span></p></td>
<td><p><span data-ttu-id="dfb5f-165">Não</span><span class="sxs-lookup"><span data-stu-id="dfb5f-165">No</span></span></p></td>
<td><p><span data-ttu-id="dfb5f-166">Número total de sessões MCU, agrupado por modalidade (por exemplo, conferência IM).</span><span class="sxs-lookup"><span data-stu-id="dfb5f-166">Total number of MCU sessions, grouped by modality (for example, IM conferencing).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dfb5f-167"><strong>Taxa de falha por modalidade</strong></span><span class="sxs-lookup"><span data-stu-id="dfb5f-167"><strong>Failure rate by modality</strong></span></span></p></td>
<td><p><span data-ttu-id="dfb5f-168">Não</span><span class="sxs-lookup"><span data-stu-id="dfb5f-168">No</span></span></p></td>
<td><p><span data-ttu-id="dfb5f-169">Porcentagem de sessões MCU que falharam, agrupadas por modalidade (por exemplo, conferência de IM).</span><span class="sxs-lookup"><span data-stu-id="dfb5f-169">Percentage of MCU sessions that failed, grouped by modality (for example, IM conferencing).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

