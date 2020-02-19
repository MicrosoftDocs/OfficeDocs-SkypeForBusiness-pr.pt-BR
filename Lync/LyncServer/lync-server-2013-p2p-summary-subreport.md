---
title: 'Lync Server 2013: sub-relatório de resumo P2P'
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
ms.openlocfilehash: ffa28f05ae8059244f53575c01f02551cbaffc95
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140034"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="p2p-summary-subreport-in-lync-server-2013"></a><span data-ttu-id="e8aac-102">Sub-relatório de resumo P2P no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e8aac-102">P2P Summary Subreport in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e8aac-103">_**Última modificação do tópico:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="e8aac-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="e8aac-104">O sub-relatório de resumo P2P fornece uma visão geral das sessões de comunicação ponto a ponto que falharam.</span><span class="sxs-lookup"><span data-stu-id="e8aac-104">The P2P Summary Subreport provides an overall view of your failed peer-to-peer communication sessions.</span></span>

<div>

## <a name="filters"></a><span data-ttu-id="e8aac-105">Filtros</span><span class="sxs-lookup"><span data-stu-id="e8aac-105">Filters</span></span>

<span data-ttu-id="e8aac-106">Os filtros fornecem uma maneira de retornar um conjunto de dados mais direcionado ou de exibir os dados retornados de maneiras diferentes.</span><span class="sxs-lookup"><span data-stu-id="e8aac-106">Filters provide a way for you to return a more finely targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="e8aac-107">A tabela a seguir lista os filtros que você pode usar com o sub-relatório de resumo P2P.</span><span class="sxs-lookup"><span data-stu-id="e8aac-107">The following table lists the filters that you can use with the P2P Summary Subreport.</span></span>

### <a name="p2p-summary-subreport-filters"></a><span data-ttu-id="e8aac-108">Filtros de subrelatório de resumo P2P</span><span class="sxs-lookup"><span data-stu-id="e8aac-108">P2P Summary Subreport Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e8aac-109">Nome</span><span class="sxs-lookup"><span data-stu-id="e8aac-109">Name</span></span></th>
<th><span data-ttu-id="e8aac-110">Descrição</span><span class="sxs-lookup"><span data-stu-id="e8aac-110">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e8aac-111"><strong>De</strong></span><span class="sxs-lookup"><span data-stu-id="e8aac-111"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="e8aac-p102">Data e hora de início para o intervalo de tempo. Para ver os dados por hora, digite a data e hora de início no seguinte formato:</span><span class="sxs-lookup"><span data-stu-id="e8aac-p102">Start date and time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="e8aac-114">7/7/2012 13:00 horas</span><span class="sxs-lookup"><span data-stu-id="e8aac-114">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="e8aac-p103">Se você não inserir uma hora inicial, o relatório começa automaticamente as 12:00 AM no dia especificado. Para exibir os dados por dia, insira apenas a data:</span><span class="sxs-lookup"><span data-stu-id="e8aac-p103">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="e8aac-117">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="e8aac-117">7/7/2012</span></span></p>
<p><span data-ttu-id="e8aac-118">Para exibir por semana ou mês, insira uma data que está dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):</span><span class="sxs-lookup"><span data-stu-id="e8aac-118">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="e8aac-119">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="e8aac-119">7/3/2012</span></span></p>
<p><span data-ttu-id="e8aac-120">As semanas são sempre de domingo a sábado.</span><span class="sxs-lookup"><span data-stu-id="e8aac-120">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8aac-121"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="e8aac-121"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="e8aac-p104">Data e hora de término para o dia intervalo de tempo. Para ver os dados por hora, digite a data e a hora de término no seguinte formato:</span><span class="sxs-lookup"><span data-stu-id="e8aac-p104">End date and time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="e8aac-124">07/07/2012 13:00</span><span class="sxs-lookup"><span data-stu-id="e8aac-124">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="e8aac-p105">Se você não inserir uma hora final, o relatório termina automaticamente as 12:00 AM no dia especificado. Para exibir os dados por dia, insira apenas a data:</span><span class="sxs-lookup"><span data-stu-id="e8aac-p105">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="e8aac-127">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="e8aac-127">7/7/2012</span></span></p>
<p><span data-ttu-id="e8aac-128">Para exibir por semana ou mês, insira uma data que está dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):</span><span class="sxs-lookup"><span data-stu-id="e8aac-128">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="e8aac-129">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="e8aac-129">7/3/2012</span></span></p>
<p><span data-ttu-id="e8aac-130">As semanas sempre correm do domingo até sábado.</span><span class="sxs-lookup"><span data-stu-id="e8aac-130">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8aac-131"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="e8aac-131"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="e8aac-p106">FQDN do pool do Registrador ou Servidor de Borda. É possível selecionar um pool individual ou clicar em <strong>[Todos]</strong> para exibir os dados de todos os pools. Esta lista suspensa é preenchida automaticamente para você com base nos registros do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="e8aac-p106">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="e8aac-135">Métricas</span><span class="sxs-lookup"><span data-stu-id="e8aac-135">Metrics</span></span>

<span data-ttu-id="e8aac-136">A tabela a seguir lista as informações fornecidas no subrelatório de resumo P2P.</span><span class="sxs-lookup"><span data-stu-id="e8aac-136">The following table lists the information provided in the P2P Summary Subreport.</span></span>

### <a name="p2p-summary-subreport-metrics"></a><span data-ttu-id="e8aac-137">Métricas de subrelatório de resumo P2P</span><span class="sxs-lookup"><span data-stu-id="e8aac-137">P2P Summary Subreport Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e8aac-138">Nome</span><span class="sxs-lookup"><span data-stu-id="e8aac-138">Name</span></span></th>
<th><span data-ttu-id="e8aac-139">É possível classificar este item?</span><span class="sxs-lookup"><span data-stu-id="e8aac-139">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="e8aac-140">Descrição</span><span class="sxs-lookup"><span data-stu-id="e8aac-140">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e8aac-141"><strong>Sessões totais</strong></span><span class="sxs-lookup"><span data-stu-id="e8aac-141"><strong>Total sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="e8aac-142">Não</span><span class="sxs-lookup"><span data-stu-id="e8aac-142">No</span></span></p></td>
<td><p><span data-ttu-id="e8aac-143">Número total de sessões, incluindo sessões bem-sucedidas, com falha (tanto falhas esperadas quanto inesperadas) e sessões não categorizadas.</span><span class="sxs-lookup"><span data-stu-id="e8aac-143">Total number of sessions, including successful sessions, failed sessions (both expected failures and unexpected failures), and uncategorized sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8aac-144"><strong>Taxa de falha</strong></span><span class="sxs-lookup"><span data-stu-id="e8aac-144"><strong>Failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="e8aac-145">Não</span><span class="sxs-lookup"><span data-stu-id="e8aac-145">No</span></span></p></td>
<td><p><span data-ttu-id="e8aac-146">Percentual de sessões ponto a ponto que falharam.</span><span class="sxs-lookup"><span data-stu-id="e8aac-146">Percentage of peer-to-peer sessions that failed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8aac-147"><strong>Sessões por modalidade</strong></span><span class="sxs-lookup"><span data-stu-id="e8aac-147"><strong>Sessions by Modality</strong></span></span></p></td>
<td><p><span data-ttu-id="e8aac-148">Não</span><span class="sxs-lookup"><span data-stu-id="e8aac-148">No</span></span></p></td>
<td><p><span data-ttu-id="e8aac-149">Número total de sessões agrupadas por modalidade (por exemplo, mensagens instantâneas).</span><span class="sxs-lookup"><span data-stu-id="e8aac-149">Total number of sessions grouped by modality (for example, instant messaging).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8aac-150"><strong>Taxa de falha por modalidade</strong></span><span class="sxs-lookup"><span data-stu-id="e8aac-150"><strong>Failure rate by modality</strong></span></span></p></td>
<td><p><span data-ttu-id="e8aac-151">Não</span><span class="sxs-lookup"><span data-stu-id="e8aac-151">No</span></span></p></td>
<td><p><span data-ttu-id="e8aac-152">Número total de sessões com falha agrupadas por modalidade (por exemplo, mensagens instantâneas).</span><span class="sxs-lookup"><span data-stu-id="e8aac-152">Total number of failed sessions grouped by modality (for example, instant messaging).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

