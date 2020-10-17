---
title: 'Lync Server 2013: sub-relatório de resumo P2P'
description: 'Lync Server 2013: sub-relatório de resumo P2P.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: P2P Summary Subreport
ms:assetid: fc36185a-3cc5-4167-8c93-8a755fa75ac7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205416(v=OCS.15)
ms:contentKeyID: 48185950
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eda51e76c4ed7b62535a2a2e4ab52982aa6381f3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557377"
---
# <a name="p2p-summary-subreport-in-lync-server-2013"></a><span data-ttu-id="9e380-103">Sub-relatório de resumo P2P no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9e380-103">P2P Summary Subreport in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9e380-104">_**Última modificação do tópico:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="9e380-104">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="9e380-105">O sub-relatório de resumo P2P fornece uma visão geral das sessões de comunicação ponto a ponto que falharam.</span><span class="sxs-lookup"><span data-stu-id="9e380-105">The P2P Summary Subreport provides an overall view of your failed peer-to-peer communication sessions.</span></span>

<div>

## <a name="filters"></a><span data-ttu-id="9e380-106">Filtros</span><span class="sxs-lookup"><span data-stu-id="9e380-106">Filters</span></span>

<span data-ttu-id="9e380-107">Os filtros fornecem uma maneira de retornar um conjunto de dados mais direcionado ou de exibir os dados retornados de maneiras diferentes.</span><span class="sxs-lookup"><span data-stu-id="9e380-107">Filters provide a way for you to return a more finely targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="9e380-108">A tabela a seguir lista os filtros que você pode usar com o sub-relatório de resumo P2P.</span><span class="sxs-lookup"><span data-stu-id="9e380-108">The following table lists the filters that you can use with the P2P Summary Subreport.</span></span>

### <a name="p2p-summary-subreport-filters"></a><span data-ttu-id="9e380-109">Filtros de subrelatório de resumo P2P</span><span class="sxs-lookup"><span data-stu-id="9e380-109">P2P Summary Subreport Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9e380-110">Nome</span><span class="sxs-lookup"><span data-stu-id="9e380-110">Name</span></span></th>
<th><span data-ttu-id="9e380-111">Descrição</span><span class="sxs-lookup"><span data-stu-id="9e380-111">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9e380-112"><strong>De</strong></span><span class="sxs-lookup"><span data-stu-id="9e380-112"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="9e380-p102">Data e hora de início para o intervalo de tempo. Para ver os dados por hora, digite a data e hora de início no seguinte formato:</span><span class="sxs-lookup"><span data-stu-id="9e380-p102">Start date and time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="9e380-115">07/07/2012 13:00</span><span class="sxs-lookup"><span data-stu-id="9e380-115">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="9e380-p103">Se você não inserir uma hora inicial, o relatório começa automaticamente as 12:00 AM no dia especificado. Para exibir os dados por dia, insira apenas a data:</span><span class="sxs-lookup"><span data-stu-id="9e380-p103">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="9e380-118">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="9e380-118">7/7/2012</span></span></p>
<p><span data-ttu-id="9e380-119">Para exibir por semana ou mês, insira uma data que está dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):</span><span class="sxs-lookup"><span data-stu-id="9e380-119">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="9e380-120">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="9e380-120">7/3/2012</span></span></p>
<p><span data-ttu-id="9e380-121">As semanas são sempre de domingo a sábado.</span><span class="sxs-lookup"><span data-stu-id="9e380-121">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9e380-122"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="9e380-122"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="9e380-p104">Data e hora de término para o dia intervalo de tempo. Para ver os dados por hora, digite a data e a hora de término no seguinte formato:</span><span class="sxs-lookup"><span data-stu-id="9e380-p104">End date and time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="9e380-125">07/07/2012 13:00</span><span class="sxs-lookup"><span data-stu-id="9e380-125">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="9e380-p105">Se você não inserir uma hora final, o relatório termina automaticamente as 12:00 AM no dia especificado. Para exibir os dados por dia, insira apenas a data:</span><span class="sxs-lookup"><span data-stu-id="9e380-p105">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="9e380-128">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="9e380-128">7/7/2012</span></span></p>
<p><span data-ttu-id="9e380-129">Para exibir por semana ou mês, insira uma data que está dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):</span><span class="sxs-lookup"><span data-stu-id="9e380-129">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="9e380-130">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="9e380-130">7/3/2012</span></span></p>
<p><span data-ttu-id="9e380-131">As semanas sempre correm do domingo até sábado.</span><span class="sxs-lookup"><span data-stu-id="9e380-131">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9e380-132"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="9e380-132"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="9e380-p106">FQDN do pool do Registrador ou Servidor de Borda. É possível selecionar um pool individual ou clicar em <strong>[Todos]</strong> para exibir os dados de todos os pools. Esta lista suspensa é preenchida automaticamente para você com base nos registros do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="9e380-p106">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="9e380-136">Métrica</span><span class="sxs-lookup"><span data-stu-id="9e380-136">Metrics</span></span>

<span data-ttu-id="9e380-137">A tabela a seguir lista as informações fornecidas no subrelatório de resumo P2P.</span><span class="sxs-lookup"><span data-stu-id="9e380-137">The following table lists the information provided in the P2P Summary Subreport.</span></span>

### <a name="p2p-summary-subreport-metrics"></a><span data-ttu-id="9e380-138">Métricas de subrelatório de resumo P2P</span><span class="sxs-lookup"><span data-stu-id="9e380-138">P2P Summary Subreport Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9e380-139">Nome</span><span class="sxs-lookup"><span data-stu-id="9e380-139">Name</span></span></th>
<th><span data-ttu-id="9e380-140">É possível classificar este item?</span><span class="sxs-lookup"><span data-stu-id="9e380-140">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="9e380-141">Descrição</span><span class="sxs-lookup"><span data-stu-id="9e380-141">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9e380-142"><strong>Sessões totais</strong></span><span class="sxs-lookup"><span data-stu-id="9e380-142"><strong>Total sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="9e380-143">Não</span><span class="sxs-lookup"><span data-stu-id="9e380-143">No</span></span></p></td>
<td><p><span data-ttu-id="9e380-144">Número total de sessões, incluindo sessões bem-sucedidas, com falha (tanto falhas esperadas quanto inesperadas) e sessões não categorizadas.</span><span class="sxs-lookup"><span data-stu-id="9e380-144">Total number of sessions, including successful sessions, failed sessions (both expected failures and unexpected failures), and uncategorized sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9e380-145"><strong>Taxa de falha</strong></span><span class="sxs-lookup"><span data-stu-id="9e380-145"><strong>Failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="9e380-146">Não</span><span class="sxs-lookup"><span data-stu-id="9e380-146">No</span></span></p></td>
<td><p><span data-ttu-id="9e380-147">Percentual de sessões ponto a ponto que falharam.</span><span class="sxs-lookup"><span data-stu-id="9e380-147">Percentage of peer-to-peer sessions that failed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9e380-148"><strong>Sessões por modalidade</strong></span><span class="sxs-lookup"><span data-stu-id="9e380-148"><strong>Sessions by Modality</strong></span></span></p></td>
<td><p><span data-ttu-id="9e380-149">Não</span><span class="sxs-lookup"><span data-stu-id="9e380-149">No</span></span></p></td>
<td><p><span data-ttu-id="9e380-150">Número total de sessões agrupadas por modalidade (por exemplo, mensagens instantâneas).</span><span class="sxs-lookup"><span data-stu-id="9e380-150">Total number of sessions grouped by modality (for example, instant messaging).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9e380-151"><strong>Taxa de falha por modalidade</strong></span><span class="sxs-lookup"><span data-stu-id="9e380-151"><strong>Failure rate by modality</strong></span></span></p></td>
<td><p><span data-ttu-id="9e380-152">Não</span><span class="sxs-lookup"><span data-stu-id="9e380-152">No</span></span></p></td>
<td><p><span data-ttu-id="9e380-153">Número total de sessões com falha agrupadas por modalidade (por exemplo, mensagens instantâneas).</span><span class="sxs-lookup"><span data-stu-id="9e380-153">Total number of failed sessions grouped by modality (for example, instant messaging).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

