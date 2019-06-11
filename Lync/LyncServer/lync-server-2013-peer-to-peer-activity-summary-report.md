---
title: 'Lync Server 2013: relatório de Resumo de atividade ponto a ponto'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Peer-to-Peer Activity Summary Report
ms:assetid: e829a21e-9dfa-46ba-9b5b-077c175d6586
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615041(v=OCS.15)
ms:contentKeyID: 48185884
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 62bdd1203db471de770ed56cf6377d7a3c651649
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825384"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="peer-to-peer-activity-summary-report-in-lync-server-2013"></a><span data-ttu-id="c72dc-102">Relatório de Resumo de atividade ponto a ponto no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c72dc-102">Peer-to-Peer Activity Summary Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c72dc-103">_**Tópico da última modificação:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="c72dc-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="c72dc-104">O Relatório de Resumo de Atividades Ponto a Ponto fornece uma visão geral de suas sessões de comunicação ponto a ponto.</span><span class="sxs-lookup"><span data-stu-id="c72dc-104">The Peer-to-Peer Activity Summary Report provides an overall view of your peer-to-peer communication sessions.</span></span> <span data-ttu-id="c72dc-105">Uma sessão ponto a ponto geralmente envolve apenas dois usuários e não requer o uso dos serviços de conferência do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c72dc-105">A peer-to-peer session typically involves just two users, and does not require the use of the Lync Server conferencing services.</span></span> <span data-ttu-id="c72dc-106">Por comparação, uma conferência geralmente envolve mais de dois usuários e requer o uso de serviços de conferência do Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c72dc-106">By comparison, a conference typically involves more than two users and requires the use of Microsoft Lync Server 2013 conferencing services.</span></span> <span data-ttu-id="c72dc-107">As atividades de conferência são relatadas no Relatório de Resumo de Conferências.</span><span class="sxs-lookup"><span data-stu-id="c72dc-107">Conference activity is reported on the Conference Summary Report.</span></span>

<span data-ttu-id="c72dc-108">O Relatório de Resumo de Atividades Ponto a Ponto ajuda você a responder perguntas como as seguintes:</span><span class="sxs-lookup"><span data-stu-id="c72dc-108">The Peer-to-Peer Activity Summary Report helps you answer questions like the following:</span></span>

  - <span data-ttu-id="c72dc-109">Quantas mensagens instantâneas ponto a ponto meus usuários enviam em um dia normal?</span><span class="sxs-lookup"><span data-stu-id="c72dc-109">How many peer-to-peer instant messages do my users send on a typical day?</span></span>

  - <span data-ttu-id="c72dc-110">Algum dos meus usuários realmente aproveita os recursos de compartilhamento de aplicativos e transferência de arquivos do Lync Server?</span><span class="sxs-lookup"><span data-stu-id="c72dc-110">Are any of my users actually taking advantage of the Lync Server application sharing and file transfer capabilities?</span></span>

  - <span data-ttu-id="c72dc-p102">Os usuários têm reclamado que a rede parece devagar em certos horários do dia. Quantos minutos são dedicados às sessões de áudio e vídeo durante esses períodos?</span><span class="sxs-lookup"><span data-stu-id="c72dc-p102">Users have been complaining that the network seems slow at certain times of the day. How many minutes are devoted to peer-to-peer audio and video sessions during those time periods?</span></span>

<div>

## <a name="accessing-the-peer-to-peer-activity-summary-report"></a><span data-ttu-id="c72dc-113">Acessando o Relatório de Resumo de Atividades Ponto a Ponto</span><span class="sxs-lookup"><span data-stu-id="c72dc-113">Accessing the Peer-to-Peer Activity Summary Report</span></span>

<span data-ttu-id="c72dc-114">O Relatório de Resumo de Atividades Ponto a Ponto é acessado na página inicial de Relatórios de Monitoramento.</span><span class="sxs-lookup"><span data-stu-id="c72dc-114">You access the Peer-to-Peer Activity Summary Report from the Monitoring Reports home page.</span></span> <span data-ttu-id="c72dc-115">Você abre o [relatório de im ponto a ponto no Lync Server 2013](lync-server-2013-peer-to-peer-im-report.md) clicando em uma das seguintes métricas:</span><span class="sxs-lookup"><span data-stu-id="c72dc-115">You open the [Peer-to-Peer IM Report in Lync Server 2013](lync-server-2013-peer-to-peer-im-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="c72dc-116">Total de sessões de mensagens instantâneas ponto a ponto</span><span class="sxs-lookup"><span data-stu-id="c72dc-116">Total peer-to-peer IM sessions</span></span>

  - <span data-ttu-id="c72dc-117">Total de mensagens instantâneas ponto a ponto</span><span class="sxs-lookup"><span data-stu-id="c72dc-117">Total peer-to-peer IM messages</span></span>

<span data-ttu-id="c72dc-118">Da mesma forma, você pode abrir o Relatório de Vídeo e Voz Ponto a Ponto clicando em qualquer uma destas métricas:</span><span class="sxs-lookup"><span data-stu-id="c72dc-118">Likewise, you can open the Peer-to-Peer Voice and Video Report by clicking any of these metrics:</span></span>

  - <span data-ttu-id="c72dc-119">Total de sessões de áudio ponto a ponto</span><span class="sxs-lookup"><span data-stu-id="c72dc-119">Total peer-to-peer audio sessions</span></span>

  - <span data-ttu-id="c72dc-120">Total de minutos de sessão de áudio ponto a ponto</span><span class="sxs-lookup"><span data-stu-id="c72dc-120">Total peer-to-peer audio session minutes</span></span>

  - <span data-ttu-id="c72dc-121">Total de sessões de áudio ponto a ponto</span><span class="sxs-lookup"><span data-stu-id="c72dc-121">Total peer-to-peer audio sessions</span></span>

  - <span data-ttu-id="c72dc-122">Total de minutos de sessão de áudio ponto a ponto</span><span class="sxs-lookup"><span data-stu-id="c72dc-122">Total peer-to-peer audio session minutes</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-peer-to-peer-activity-summary-report"></a><span data-ttu-id="c72dc-123">Como usar o Relatório de Resumo de Atividades Ponto a Ponto da melhor maneira possível</span><span class="sxs-lookup"><span data-stu-id="c72dc-123">Making the Best Use of the Peer-to-Peer Activity Summary Report</span></span>

<span data-ttu-id="c72dc-p104">No final do Relatório de Resumo de Atividades Ponto a Ponto, você encontrará os totais de métricas como Total de sessões de mensagens instantâneas ponto a ponto e Total de mensagens instantâneas ponto a ponto. Isso oferece um resumo rápido das informações detalhadas encontradas no corpo do relatório.</span><span class="sxs-lookup"><span data-stu-id="c72dc-p104">At the bottom of the Peer-to-Peer Activity Summary Report you'll find totals for metrics such as Total peer-to-peer IM sessions and Total peer-to-peer IM messages. This provides a quick summary of the detailed information found in the body of the report.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="c72dc-126">Filtros</span><span class="sxs-lookup"><span data-stu-id="c72dc-126">Filters</span></span>

<span data-ttu-id="c72dc-p105">Os filtros fornecem uma maneira de retornar um conjunto de dados mais direcionado ou de exibir os dados retornados de maneiras diferentes. Por exemplo, o Relatório de Resumo de Atividades Ponto a Ponto permite que você escolha como os dados devem ser agrupados. Nesse caso, atividades agrupadas por hora, dia, semana ou mês.</span><span class="sxs-lookup"><span data-stu-id="c72dc-p105">Filters provide a way for you to return a more finely targeted set of data or to view the returned data in different ways. For example, the Peer-to-Peer Activity Summary Report enables you to choose how data should be grouped. In this case, activity grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="c72dc-130">A tabela a seguir lista os filtros que podem ser usados com o Relatório de Resumo de Atividades Ponto a Ponto.</span><span class="sxs-lookup"><span data-stu-id="c72dc-130">The following table lists the filters that you can use with the Peer-to-Peer Activity Summary Report.</span></span>

### <a name="peer-to-peer-activity-summary-report-filters"></a><span data-ttu-id="c72dc-131">Filtros do Relatório de Resumo de Atividades Ponto a Ponto</span><span class="sxs-lookup"><span data-stu-id="c72dc-131">Peer-to-Peer Activity Summary Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c72dc-132">Nome</span><span class="sxs-lookup"><span data-stu-id="c72dc-132">Name</span></span></th>
<th><span data-ttu-id="c72dc-133">Descrição</span><span class="sxs-lookup"><span data-stu-id="c72dc-133">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c72dc-134"><strong>De</strong></span><span class="sxs-lookup"><span data-stu-id="c72dc-134"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="c72dc-p106">Data e hora de início do intervalo de tempo. Para ver os dados por hora, insira a data e hora de início desta forma:</span><span class="sxs-lookup"><span data-stu-id="c72dc-p106">Start date and time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="c72dc-137">7/17/12012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="c72dc-137">7/17/12012 1:00 PM</span></span></p>
<p><span data-ttu-id="c72dc-p107">Se você não inserir a hora de início, o relatório começará automaticamente à meia-noite do dia especificado. Para ver os dados por dia, insira somente a data:</span><span class="sxs-lookup"><span data-stu-id="c72dc-p107">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="c72dc-140">7/17/12012</span><span class="sxs-lookup"><span data-stu-id="c72dc-140">7/17/12012</span></span></p>
<p><span data-ttu-id="c72dc-141">Para exibir por semana ou mês, insira uma data dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):</span><span class="sxs-lookup"><span data-stu-id="c72dc-141">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="c72dc-142">7/13/2012</span><span class="sxs-lookup"><span data-stu-id="c72dc-142">7/13/2012</span></span></p>
<p><span data-ttu-id="c72dc-143">As semanas sempre vão de domingo a sábado.</span><span class="sxs-lookup"><span data-stu-id="c72dc-143">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c72dc-144"><strong>Até</strong></span><span class="sxs-lookup"><span data-stu-id="c72dc-144"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="c72dc-p108">Data e hora final para o intervalo de tempo. Para exibir os dados por hora, insira a data e hora final como a seguir:</span><span class="sxs-lookup"><span data-stu-id="c72dc-p108">End date and time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="c72dc-147">7/17/12012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="c72dc-147">7/17/12012 1:00 PM</span></span></p>
<p><span data-ttu-id="c72dc-p109">Se você não inserir a hora final, o relatório terminará automaticamente à meia-noite do dia especificado. Para ver os dados por dia, insira somente a data:</span><span class="sxs-lookup"><span data-stu-id="c72dc-p109">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="c72dc-150">7/17/12012</span><span class="sxs-lookup"><span data-stu-id="c72dc-150">7/17/12012</span></span></p>
<p><span data-ttu-id="c72dc-151">Para exibir por semana ou mês, insira uma data dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):</span><span class="sxs-lookup"><span data-stu-id="c72dc-151">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="c72dc-152">7/13/2012</span><span class="sxs-lookup"><span data-stu-id="c72dc-152">7/13/2012</span></span></p>
<p><span data-ttu-id="c72dc-153">As semanas sempre vão de domingo a sábado.</span><span class="sxs-lookup"><span data-stu-id="c72dc-153">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c72dc-154"><strong>Intervalo</strong></span><span class="sxs-lookup"><span data-stu-id="c72dc-154"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="c72dc-p110">Intervalo de tempo. Selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="c72dc-p110">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="c72dc-157">Por hora (é possível exibir no máximo 25 horas)</span><span class="sxs-lookup"><span data-stu-id="c72dc-157">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="c72dc-158">Diariamente (é possível exibir no máximo 31 dias)</span><span class="sxs-lookup"><span data-stu-id="c72dc-158">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="c72dc-159">Semanalmente (é possível exibir no máximo 12 semanas)</span><span class="sxs-lookup"><span data-stu-id="c72dc-159">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="c72dc-160">Mensalmente (é possível exibir no máximo 12 meses)</span><span class="sxs-lookup"><span data-stu-id="c72dc-160">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="c72dc-161">Se as datas de início e término excederem o número máximo de valores permitidos para o intervalo selecionado, somente o número máximo de valores (a partir da data de início) será exibido.</span><span class="sxs-lookup"><span data-stu-id="c72dc-161">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed.</span></span> <span data-ttu-id="c72dc-162">Por exemplo, se você selecionar o intervalo diário com uma data de início de 7/17/12012 e uma data de término de 2/28/2012, os dados serão exibidos para os dias 8/7/12012 12:00 AM a 9/7/12012 12:00 AM (ou seja, um total de 31 dias da importância dos dados).</span><span class="sxs-lookup"><span data-stu-id="c72dc-162">For example, if you select the Daily interval with a start date of 7/17/12012 and an end date of 2/28/2012, data is displayed for the days 8/7/12012 12:00 AM to 9/7/12012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="c72dc-163">Métricas</span><span class="sxs-lookup"><span data-stu-id="c72dc-163">Metrics</span></span>

<span data-ttu-id="c72dc-164">A tabela a seguir lista as informações fornecidas no Relatório de Resumo de Atividades Ponto a Ponto.</span><span class="sxs-lookup"><span data-stu-id="c72dc-164">The following table lists the information provided in the Peer-to-Peer Activity Summary Report.</span></span>

### <a name="peer-to-peer-activity-summary-report-metrics"></a><span data-ttu-id="c72dc-165">Métricas do Relatório de Resumo de Atividades Ponto a Ponto</span><span class="sxs-lookup"><span data-stu-id="c72dc-165">Peer-to-Peer Activity Summary Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c72dc-166">Nome</span><span class="sxs-lookup"><span data-stu-id="c72dc-166">Name</span></span></th>
<th><span data-ttu-id="c72dc-167">Você pode classificar este item?</span><span class="sxs-lookup"><span data-stu-id="c72dc-167">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="c72dc-168">Descrição</span><span class="sxs-lookup"><span data-stu-id="c72dc-168">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c72dc-169"><strong>Por hora</strong></span><span class="sxs-lookup"><span data-stu-id="c72dc-169"><strong>Hourly</strong></span></span></p>
<p><span data-ttu-id="c72dc-170"><strong>Diário</strong></span><span class="sxs-lookup"><span data-stu-id="c72dc-170"><strong>Daily</strong></span></span></p>
<p><span data-ttu-id="c72dc-171"><strong>Semanal</strong></span><span class="sxs-lookup"><span data-stu-id="c72dc-171"><strong>Weekly</strong></span></span></p>
<p><span data-ttu-id="c72dc-172"><strong>Mensal</strong></span><span class="sxs-lookup"><span data-stu-id="c72dc-172"><strong>Monthly</strong></span></span></p></td>
<td><p><span data-ttu-id="c72dc-173">Não</span><span class="sxs-lookup"><span data-stu-id="c72dc-173">No</span></span></p></td>
<td><p><span data-ttu-id="c72dc-174">Indica o intervalo de tempo selecionado na barra de ferramentas de filtro.</span><span class="sxs-lookup"><span data-stu-id="c72dc-174">Indicates the time interval that you selected on the filter toolbar.</span></span> <span data-ttu-id="c72dc-175">Quando aplicável, é possível clicar em determinado intervalo de tempo para exibir informações detalhadas sobre ele.</span><span class="sxs-lookup"><span data-stu-id="c72dc-175">Where applicable, you can click a given time interval to view detailed information for that interval.</span></span> <span data-ttu-id="c72dc-176">Por exemplo, se você estiver usando o intervalo diário e clicar em 7/17/12012, verá um detalhamento por hora da atividade de registro do usuário para essa data.</span><span class="sxs-lookup"><span data-stu-id="c72dc-176">For example, if you are using the Daily interval and you click 7/17/12012, you see an hourly breakdown of user registration activity for that date.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c72dc-177"><strong>Total de sessões ponto a ponto</strong></span><span class="sxs-lookup"><span data-stu-id="c72dc-177"><strong>Total peer-to-peer sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="c72dc-178">Não</span><span class="sxs-lookup"><span data-stu-id="c72dc-178">No</span></span></p></td>
<td><p><span data-ttu-id="c72dc-179">Número total de sessões ponto a ponto conduzidas, independentemente do tipo de sessão.</span><span class="sxs-lookup"><span data-stu-id="c72dc-179">Total number of peer-to-peer sessions conducted, regardless of session type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c72dc-180"><strong>Total de sessões de mensagens instantâneas ponto a ponto</strong></span><span class="sxs-lookup"><span data-stu-id="c72dc-180"><strong>Total peer-to-peer IM sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="c72dc-181">Não</span><span class="sxs-lookup"><span data-stu-id="c72dc-181">No</span></span></p></td>
<td><p><span data-ttu-id="c72dc-p113">Número total de sessões de mensagens instantâneas (IM) ponto a ponto. Quando você clica nesse item, o relatório mostra o Relatório de Mensagens Instantâneas Ponto a Ponto para o período selecionado.</span><span class="sxs-lookup"><span data-stu-id="c72dc-p113">Total number of peer-to-peer instant messaging (IM) sessions. When you click this item, the report shows you the Peer-to-Peer IM Report for the selected time period.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c72dc-184"><strong>Total de mensagens instantâneas ponto a ponto</strong></span><span class="sxs-lookup"><span data-stu-id="c72dc-184"><strong>Total peer-to-peer IM messages</strong></span></span></p></td>
<td><p><span data-ttu-id="c72dc-185">Não</span><span class="sxs-lookup"><span data-stu-id="c72dc-185">No</span></span></p></td>
<td><p><span data-ttu-id="c72dc-p114">Número total de mensagens instantâneas enviadas em sessões ponto a ponto. Quando você clica nesse item, o relatório mostra o Relatório de Mensagens Instantâneas Ponto a Ponto para o período selecionado.</span><span class="sxs-lookup"><span data-stu-id="c72dc-p114">Total number of instant messages sent in peer-to-peer sessions. When you click this item, the report shows you the Peer-to-Peer IM Report for the selected time period.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c72dc-188"><strong>Total de sessões de áudio ponto a ponto</strong></span><span class="sxs-lookup"><span data-stu-id="c72dc-188"><strong>Total peer-to-peer audio sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="c72dc-189">Não</span><span class="sxs-lookup"><span data-stu-id="c72dc-189">No</span></span></p></td>
<td><p><span data-ttu-id="c72dc-p115">Número total de chamadas de áudio ponto a ponto. Quando você clica nesse campo, o relatório mostra o Relatório de Voz e Vídeo Ponto a Ponto para o período selecionado.</span><span class="sxs-lookup"><span data-stu-id="c72dc-p115">Total number of peer-to-peer audio calls. When you click this field, the report shows you the Peer-to-Peer Voice and Video Report for the selected time period.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c72dc-192"><strong>Total de minutos de sessão de áudio ponto a ponto</strong></span><span class="sxs-lookup"><span data-stu-id="c72dc-192"><strong>Total peer-to-peer audio session minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="c72dc-193">Não</span><span class="sxs-lookup"><span data-stu-id="c72dc-193">No</span></span></p></td>
<td><p><span data-ttu-id="c72dc-194">Tempo total gasto em sessões de áudio ponto a ponto.</span><span class="sxs-lookup"><span data-stu-id="c72dc-194">Total amount of time spent in peer-to-peer audio sessions.</span></span> <span data-ttu-id="c72dc-195">Quando você clica nesse item, o relatório mostra o Relatório de Vídeo e Voz Ponto a Ponto do período selecionado.</span><span class="sxs-lookup"><span data-stu-id="c72dc-195">When you click this item, the report shows you the Peer-to-Peer Voice and Video Report for the selected time period.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c72dc-196"><strong>Média de minutos de sessão de áudio ponto a ponto</strong></span><span class="sxs-lookup"><span data-stu-id="c72dc-196"><strong>Average peer-to-peer audio session minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="c72dc-197">Não</span><span class="sxs-lookup"><span data-stu-id="c72dc-197">No</span></span></p></td>
<td><p><span data-ttu-id="c72dc-p117">Tempo médio gasto em sessões de áudio ponto a ponto. Calculado dividindo o tempo total de sessão de áudio pelo número total de sessões de áudio.</span><span class="sxs-lookup"><span data-stu-id="c72dc-p117">Average amount of time spent in peer-to-peer audio sessions. Calculated by dividing the total audio session time by the total number of audio sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c72dc-200"><strong>Total de sessões de vídeo ponto a ponto</strong></span><span class="sxs-lookup"><span data-stu-id="c72dc-200"><strong>Total peer-to-peer video sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="c72dc-201">Não</span><span class="sxs-lookup"><span data-stu-id="c72dc-201">No</span></span></p></td>
<td><p><span data-ttu-id="c72dc-p118">Número total de chamadas de vídeo ponto a ponto. Observe que as sessões de vídeo também contam como sessões de áudio: cada sessão de vídeo conta como uma sessão de vídeo e uma sessão de áudio. Quando você clica nesse item, o relatório mostra o Relatório de Vídeo e Voz Ponto a Ponto do período selecionado.</span><span class="sxs-lookup"><span data-stu-id="c72dc-p118">Total number of peer-to-peer video calls. Note that video sessions are also counted as audio sessions: each video session is counted as one video session and one audio session. When you click this item, the report shows you the Peer-to-Peer Voice and Video Report for the selected time period.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c72dc-205"><strong>Total de minutos de sessão de vídeo ponto a ponto</strong></span><span class="sxs-lookup"><span data-stu-id="c72dc-205"><strong>Total peer-to-peer video session minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="c72dc-206">Não</span><span class="sxs-lookup"><span data-stu-id="c72dc-206">No</span></span></p></td>
<td><p><span data-ttu-id="c72dc-p119">Tempo total gasto em sessões de vídeo ponto a ponto. Quando você clica nesse item, o relatório mostra o Relatório de Vídeo e Voz Ponto a Ponto do período selecionado.</span><span class="sxs-lookup"><span data-stu-id="c72dc-p119">Total amount of time spent in peer-to-peer video sessions. When you click this item, the report shows you the Peer-to-Peer Voice and Video Report for the selected time period.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c72dc-209"><strong>Média de minutos de sessão de vídeo ponto a ponto</strong></span><span class="sxs-lookup"><span data-stu-id="c72dc-209"><strong>Average peer-to-peer video session minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="c72dc-210">Não</span><span class="sxs-lookup"><span data-stu-id="c72dc-210">No</span></span></p></td>
<td><p><span data-ttu-id="c72dc-p120">Tempo médio gasto em sessões de vídeo ponto a ponto. Calculado dividindo o tempo total de sessão de vídeo pelo número total de sessões de áudio.</span><span class="sxs-lookup"><span data-stu-id="c72dc-p120">Average amount of time spent in peer-to-peer video sessions. Calculated by dividing the total video session time by the total number of video sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c72dc-213"><strong>Total de sessões de transferência de arquivo ponto a ponto</strong></span><span class="sxs-lookup"><span data-stu-id="c72dc-213"><strong>Total peer-to-peer file transfer sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="c72dc-214">Não</span><span class="sxs-lookup"><span data-stu-id="c72dc-214">No</span></span></p></td>
<td><p><span data-ttu-id="c72dc-215">Número total de sessões ponto a ponto que incluem transferências de arquivo.</span><span class="sxs-lookup"><span data-stu-id="c72dc-215">Total number of peer-to-peer sessions that included file transfers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c72dc-216"><strong>Total de sessões de compartilhamento de arquivo ponto a ponto</strong></span><span class="sxs-lookup"><span data-stu-id="c72dc-216"><strong>Total peer-to-peer application sharing sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="c72dc-217">Não</span><span class="sxs-lookup"><span data-stu-id="c72dc-217">No</span></span></p></td>
<td><p><span data-ttu-id="c72dc-218">Número total de sessões ponto a ponto que incluem compartilhamento de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="c72dc-218">Total number of peer-to-peer sessions that included application sharing.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

