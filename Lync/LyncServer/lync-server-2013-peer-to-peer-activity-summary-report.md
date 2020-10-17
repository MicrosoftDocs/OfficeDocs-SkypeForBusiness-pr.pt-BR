---
title: 'Lync Server 2013: relatório de Resumo de atividades ponto a ponto'
description: 'Lync Server 2013: relatório de Resumo de atividades ponto a ponto.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Peer-to-Peer Activity Summary Report
ms:assetid: e829a21e-9dfa-46ba-9b5b-077c175d6586
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615041(v=OCS.15)
ms:contentKeyID: 48185884
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2f081f542a5063ed83be470d3e991c58e458b487
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557297"
---
# <a name="peer-to-peer-activity-summary-report-in-lync-server-2013"></a><span data-ttu-id="d99d7-103">Relatório de Resumo de atividades ponto a ponto no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d99d7-103">Peer-to-Peer Activity Summary Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d99d7-104">_**Última modificação do tópico:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="d99d7-104">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="d99d7-105">O Relatório de Resumo de Atividades Ponto a Ponto fornece uma visão geral de suas sessões de comunicação ponto a ponto.</span><span class="sxs-lookup"><span data-stu-id="d99d7-105">The Peer-to-Peer Activity Summary Report provides an overall view of your peer-to-peer communication sessions.</span></span> <span data-ttu-id="d99d7-106">Uma sessão ponto a ponto geralmente envolve apenas dois usuários e não requer o uso dos serviços de conferência do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d99d7-106">A peer-to-peer session typically involves just two users, and does not require the use of the Lync Server conferencing services.</span></span> <span data-ttu-id="d99d7-107">Por comparação, uma conferência geralmente envolve mais de dois usuários e requer o uso de serviços de conferência do Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d99d7-107">By comparison, a conference typically involves more than two users and requires the use of Microsoft Lync Server 2013 conferencing services.</span></span> <span data-ttu-id="d99d7-108">Atividades de conferência são relatadas no Relatório de Resumo de Conferência.</span><span class="sxs-lookup"><span data-stu-id="d99d7-108">Conference activity is reported on the Conference Summary Report.</span></span>

<span data-ttu-id="d99d7-109">O Relatório de Resumo de Atividade Ponto a Ponto ajuda você a responder perguntas como as seguintes:</span><span class="sxs-lookup"><span data-stu-id="d99d7-109">The Peer-to-Peer Activity Summary Report helps you answer questions like the following:</span></span>

  - <span data-ttu-id="d99d7-110">Quantas mensagens instantâneas ponto a ponto meus usuários enviam em um dia normal?</span><span class="sxs-lookup"><span data-stu-id="d99d7-110">How many peer-to-peer instant messages do my users send on a typical day?</span></span>

  - <span data-ttu-id="d99d7-111">Algum de meus usuários realmente aproveita as vantagens do compartilhamento de aplicativos do Lync Server e dos recursos de transferência de arquivos?</span><span class="sxs-lookup"><span data-stu-id="d99d7-111">Are any of my users actually taking advantage of the Lync Server application sharing and file transfer capabilities?</span></span>

  - <span data-ttu-id="d99d7-p102">Usuários tem reclamado que a rede parece devagar em certos horários do dia. Quantos minutos são devotados para sessões de áudio e video durante estes períodos de tempo?</span><span class="sxs-lookup"><span data-stu-id="d99d7-p102">Users have been complaining that the network seems slow at certain times of the day. How many minutes are devoted to peer-to-peer audio and video sessions during those time periods?</span></span>

<div>

## <a name="accessing-the-peer-to-peer-activity-summary-report"></a><span data-ttu-id="d99d7-114">Acessando o Relatório de Resumo de Atividade Ponto a Ponto</span><span class="sxs-lookup"><span data-stu-id="d99d7-114">Accessing the Peer-to-Peer Activity Summary Report</span></span>

<span data-ttu-id="d99d7-115">O Relatório de Resumo de Atividade Ponto a Ponto é acessado a partir da página inicial de Relatórios de Monitoramento.</span><span class="sxs-lookup"><span data-stu-id="d99d7-115">You access the Peer-to-Peer Activity Summary Report from the Monitoring Reports home page.</span></span> <span data-ttu-id="d99d7-116">Abra o [relatório de mensagens instantâneas ponto a ponto no Lync Server 2013](lync-server-2013-peer-to-peer-im-report.md) clicando em uma das seguintes métricas:</span><span class="sxs-lookup"><span data-stu-id="d99d7-116">You open the [Peer-to-Peer IM Report in Lync Server 2013](lync-server-2013-peer-to-peer-im-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="d99d7-117">Total de sessões de mensagens instantâneas ponto a ponto</span><span class="sxs-lookup"><span data-stu-id="d99d7-117">Total peer-to-peer IM sessions</span></span>

  - <span data-ttu-id="d99d7-118">Total de mensagens instantâneas ponto a ponto</span><span class="sxs-lookup"><span data-stu-id="d99d7-118">Total peer-to-peer IM messages</span></span>

<span data-ttu-id="d99d7-119">De modo parecido, você pode abrir o Relatório de Vídeo e Voz Ponto a Ponto clicando em qualquer uma destas métricas:</span><span class="sxs-lookup"><span data-stu-id="d99d7-119">Likewise, you can open the Peer-to-Peer Voice and Video Report by clicking any of these metrics:</span></span>

  - <span data-ttu-id="d99d7-120">Total de sessões de áudio ponto a ponto</span><span class="sxs-lookup"><span data-stu-id="d99d7-120">Total peer-to-peer audio sessions</span></span>

  - <span data-ttu-id="d99d7-121">Total de minutos de sessão de áudio ponto a ponto</span><span class="sxs-lookup"><span data-stu-id="d99d7-121">Total peer-to-peer audio session minutes</span></span>

  - <span data-ttu-id="d99d7-122">Total de sessões de áudio ponto a ponto</span><span class="sxs-lookup"><span data-stu-id="d99d7-122">Total peer-to-peer audio sessions</span></span>

  - <span data-ttu-id="d99d7-123">Total de minutos de sessão de áudio ponto a ponto</span><span class="sxs-lookup"><span data-stu-id="d99d7-123">Total peer-to-peer audio session minutes</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-peer-to-peer-activity-summary-report"></a><span data-ttu-id="d99d7-124">Fazendo o Melhor Uso do Relatório de Resumo de Atividade Ponto a Ponto</span><span class="sxs-lookup"><span data-stu-id="d99d7-124">Making the Best Use of the Peer-to-Peer Activity Summary Report</span></span>

<span data-ttu-id="d99d7-p104">Ao final do Relatório de Resumo de Atividade Ponto a Ponto, você encontrará os totais para métricas tais como Total de sessões de mensagens instantâneas ponto a ponto e Total de mensagens instantâneas ponto a ponto. Isso oferece um resumo rápido das informações detalhadas encontradas no corpo do relatório.</span><span class="sxs-lookup"><span data-stu-id="d99d7-p104">At the bottom of the Peer-to-Peer Activity Summary Report you'll find totals for metrics such as Total peer-to-peer IM sessions and Total peer-to-peer IM messages. This provides a quick summary of the detailed information found in the body of the report.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="d99d7-127">Filtros</span><span class="sxs-lookup"><span data-stu-id="d99d7-127">Filters</span></span>

<span data-ttu-id="d99d7-p105">Os filtros fornecem uma maneira de retornar um conjunto de dados mais direcionado ou de exibir os dados retornados de maneiras diferentes. Por exemplo, o Relatório de Resumos de Atividades Ponto a Ponto permite que você escolha como os dados devem ser agrupados. Nesse caso, atividades agrupadas por hora, dia, semana ou mês.</span><span class="sxs-lookup"><span data-stu-id="d99d7-p105">Filters provide a way for you to return a more finely targeted set of data or to view the returned data in different ways. For example, the Peer-to-Peer Activity Summary Report enables you to choose how data should be grouped. In this case, activity grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="d99d7-131">A tabela a seguir lista os filtros que podem ser usados com o Relatório de Resumos de Atividades Ponta a Ponta.</span><span class="sxs-lookup"><span data-stu-id="d99d7-131">The following table lists the filters that you can use with the Peer-to-Peer Activity Summary Report.</span></span>

### <a name="peer-to-peer-activity-summary-report-filters"></a><span data-ttu-id="d99d7-132">Filtros do Relatório de Resumos de Atividades Ponto a Ponto</span><span class="sxs-lookup"><span data-stu-id="d99d7-132">Peer-to-Peer Activity Summary Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d99d7-133">Nome</span><span class="sxs-lookup"><span data-stu-id="d99d7-133">Name</span></span></th>
<th><span data-ttu-id="d99d7-134">Descrição</span><span class="sxs-lookup"><span data-stu-id="d99d7-134">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d99d7-135"><strong>De</strong></span><span class="sxs-lookup"><span data-stu-id="d99d7-135"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="d99d7-p106">Data e hora de início para o intervalo de tempo. Para exibir os dados por horas, digite a data e a hora de início da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="d99d7-p106">Start date and time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="d99d7-138">17/07/2012 13:00</span><span class="sxs-lookup"><span data-stu-id="d99d7-138">7/17/12012 1:00 PM</span></span></p>
<p><span data-ttu-id="d99d7-p107">Se você não digitar um horário de início, o relatório começará automaticamente às 12:00 AM no dia especificado. Para exibir os dados por dia, digite apenas a data:</span><span class="sxs-lookup"><span data-stu-id="d99d7-p107">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="d99d7-141">7/17/12012</span><span class="sxs-lookup"><span data-stu-id="d99d7-141">7/17/12012</span></span></p>
<p><span data-ttu-id="d99d7-142">Para exibir por semana ou por mês, insira uma data cai em qualquer lugar dentro da semana ou mês que você deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):</span><span class="sxs-lookup"><span data-stu-id="d99d7-142">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="d99d7-143">7/13/2012</span><span class="sxs-lookup"><span data-stu-id="d99d7-143">7/13/2012</span></span></p>
<p><span data-ttu-id="d99d7-144">As semanas sempre correm do domingo até sábado.</span><span class="sxs-lookup"><span data-stu-id="d99d7-144">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d99d7-145"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="d99d7-145"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="d99d7-p108">Data e hora final para o intervalo de tempo. Para exibir os dados por hora, insira a data e hora final como a seguir:</span><span class="sxs-lookup"><span data-stu-id="d99d7-p108">End date and time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="d99d7-148">17/07/2012 13:00</span><span class="sxs-lookup"><span data-stu-id="d99d7-148">7/17/12012 1:00 PM</span></span></p>
<p><span data-ttu-id="d99d7-p109">Se você não digitar um horário de término, o relatório terminará automaticamente às 12:00 AM no dia especificado. Para exibir os dados por dia, digite apenas a data:</span><span class="sxs-lookup"><span data-stu-id="d99d7-p109">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="d99d7-151">7/17/12012</span><span class="sxs-lookup"><span data-stu-id="d99d7-151">7/17/12012</span></span></p>
<p><span data-ttu-id="d99d7-152">Para exibir por semana ou por mês, insira uma data cai em qualquer lugar dentro da semana ou mês que você deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):</span><span class="sxs-lookup"><span data-stu-id="d99d7-152">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="d99d7-153">7/13/2012</span><span class="sxs-lookup"><span data-stu-id="d99d7-153">7/13/2012</span></span></p>
<p><span data-ttu-id="d99d7-154">As semanas sempre correm do domingo até sábado.</span><span class="sxs-lookup"><span data-stu-id="d99d7-154">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d99d7-155"><strong>Intervalo</strong></span><span class="sxs-lookup"><span data-stu-id="d99d7-155"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="d99d7-p110">Intervalo de tempo. Selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="d99d7-p110">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="d99d7-158">Por hora (é possível exibir no máximo 25 horas)</span><span class="sxs-lookup"><span data-stu-id="d99d7-158">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="d99d7-159">Diariamente (é possível exibir no máximo 31 dias)</span><span class="sxs-lookup"><span data-stu-id="d99d7-159">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="d99d7-160">Semanalmente (é possível exibir no máximo 12 semanas)</span><span class="sxs-lookup"><span data-stu-id="d99d7-160">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="d99d7-161">Mensalmente (é possível exibir no máximo 12 meses)</span><span class="sxs-lookup"><span data-stu-id="d99d7-161">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="d99d7-p111">Se as datas de início e término excederem o número máximo de valores permitidos para o intervalo selecionado, somente o número máximo de valores (a partir da data de início) será exibido. Por exemplo, se você selecionar o intervalo Diariamente com a data de início 17/07/2012 e uma data de término de 28/02/12, os dados serão exibidos para os dias 07/08/2012 12:00 AM até 07/09/2012 12:00 AM (ou seja, um total de 31 dias de dados).</span><span class="sxs-lookup"><span data-stu-id="d99d7-p111">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed. For example, if you select the Daily interval with a start date of 7/17/12012 and an end date of 2/28/2012, data is displayed for the days 8/7/12012 12:00 AM to 9/7/12012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="d99d7-164">Métrica</span><span class="sxs-lookup"><span data-stu-id="d99d7-164">Metrics</span></span>

<span data-ttu-id="d99d7-165">A tabela a seguir lista as informações fornecidas no Relatório de Resumos de Atividades Ponto a Ponto.</span><span class="sxs-lookup"><span data-stu-id="d99d7-165">The following table lists the information provided in the Peer-to-Peer Activity Summary Report.</span></span>

### <a name="peer-to-peer-activity-summary-report-metrics"></a><span data-ttu-id="d99d7-166">Métricas do Relatório de Resumos de Atividades Ponto a Ponto</span><span class="sxs-lookup"><span data-stu-id="d99d7-166">Peer-to-Peer Activity Summary Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d99d7-167">Nome</span><span class="sxs-lookup"><span data-stu-id="d99d7-167">Name</span></span></th>
<th><span data-ttu-id="d99d7-168">É possível classificar este item?</span><span class="sxs-lookup"><span data-stu-id="d99d7-168">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="d99d7-169">Descrição</span><span class="sxs-lookup"><span data-stu-id="d99d7-169">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d99d7-170"><strong>A cada hora</strong></span><span class="sxs-lookup"><span data-stu-id="d99d7-170"><strong>Hourly</strong></span></span></p>
<p><span data-ttu-id="d99d7-171"><strong>Diariamente</strong></span><span class="sxs-lookup"><span data-stu-id="d99d7-171"><strong>Daily</strong></span></span></p>
<p><span data-ttu-id="d99d7-172"><strong>Semanalmente</strong></span><span class="sxs-lookup"><span data-stu-id="d99d7-172"><strong>Weekly</strong></span></span></p>
<p><span data-ttu-id="d99d7-173"><strong>Mensal</strong></span><span class="sxs-lookup"><span data-stu-id="d99d7-173"><strong>Monthly</strong></span></span></p></td>
<td><p><span data-ttu-id="d99d7-174">Não</span><span class="sxs-lookup"><span data-stu-id="d99d7-174">No</span></span></p></td>
<td><p><span data-ttu-id="d99d7-p112">Indica o intervalo de tempo selecionado na barra de ferramentas do filtro. Quando aplicável, é possível clicar em um determinado intervalo de tempo para exibir informações detalhadas desse intervalo. Por exemplo, se você estiver usando o intervalo Diário e clicar em 17/07/2012, você verá uma divisão por hora da atividade de registro do usuário para essa data.</span><span class="sxs-lookup"><span data-stu-id="d99d7-p112">Indicates the time interval that you selected on the filter toolbar. Where applicable, you can click a given time interval to view detailed information for that interval. For example, if you are using the Daily interval and you click 7/17/12012, you see an hourly breakdown of user registration activity for that date.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d99d7-178"><strong>Total de sessões ponto a ponto </strong></span><span class="sxs-lookup"><span data-stu-id="d99d7-178"><strong>Total peer-to-peer sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="d99d7-179">Não</span><span class="sxs-lookup"><span data-stu-id="d99d7-179">No</span></span></p></td>
<td><p><span data-ttu-id="d99d7-180">Número total de sessões ponto a ponto conduzidas, independentemente do tipo de sessão.</span><span class="sxs-lookup"><span data-stu-id="d99d7-180">Total number of peer-to-peer sessions conducted, regardless of session type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d99d7-181"><strong>Total de sessões de mensagens instantâneas ponto a ponto </strong></span><span class="sxs-lookup"><span data-stu-id="d99d7-181"><strong>Total peer-to-peer IM sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="d99d7-182">Não</span><span class="sxs-lookup"><span data-stu-id="d99d7-182">No</span></span></p></td>
<td><p><span data-ttu-id="d99d7-p113">Número total de sessões de mensagens instantâneas (IM) ponto a ponto. Quando você clica nesse item, o relatório mostra o Relatório de Mensagens Instantâneas Ponto a Ponto para o período selecionado.</span><span class="sxs-lookup"><span data-stu-id="d99d7-p113">Total number of peer-to-peer instant messaging (IM) sessions. When you click this item, the report shows you the Peer-to-Peer IM Report for the selected time period.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d99d7-185"><strong>Total de mensagens instantâneas ponto a ponto </strong></span><span class="sxs-lookup"><span data-stu-id="d99d7-185"><strong>Total peer-to-peer IM messages</strong></span></span></p></td>
<td><p><span data-ttu-id="d99d7-186">Não</span><span class="sxs-lookup"><span data-stu-id="d99d7-186">No</span></span></p></td>
<td><p><span data-ttu-id="d99d7-p114">Número total de mensagens instantâneas enviadas em sessões ponto a ponto. Quando você clica nesse item, o relatório mostra o Relatório de Mensagens Instantâneas Ponto a Ponto para o período selecionado.</span><span class="sxs-lookup"><span data-stu-id="d99d7-p114">Total number of instant messages sent in peer-to-peer sessions. When you click this item, the report shows you the Peer-to-Peer IM Report for the selected time period.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d99d7-189"><strong>Total de sessões de áudio ponto a ponto </strong></span><span class="sxs-lookup"><span data-stu-id="d99d7-189"><strong>Total peer-to-peer audio sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="d99d7-190">Não</span><span class="sxs-lookup"><span data-stu-id="d99d7-190">No</span></span></p></td>
<td><p><span data-ttu-id="d99d7-p115">Número total de chamadas de áudio ponto a ponto. Quando você clica nesse campo, o relatório mostra o Relatório de de Voz e Vídeo Ponto a Ponto para o período selecionado.</span><span class="sxs-lookup"><span data-stu-id="d99d7-p115">Total number of peer-to-peer audio calls. When you click this field, the report shows you the Peer-to-Peer Voice and Video Report for the selected time period.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d99d7-193"><strong>Total de minutos de sessão de áudio ponto a ponto</strong></span><span class="sxs-lookup"><span data-stu-id="d99d7-193"><strong>Total peer-to-peer audio session minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="d99d7-194">Não</span><span class="sxs-lookup"><span data-stu-id="d99d7-194">No</span></span></p></td>
<td><p><span data-ttu-id="d99d7-195">Tempo total gasto em sessões de áudio ponto a ponto.</span><span class="sxs-lookup"><span data-stu-id="d99d7-195">Total amount of time spent in peer-to-peer audio sessions.</span></span> <span data-ttu-id="d99d7-196">Quando você clica nesse item, o relatório mostra o relatório de vídeo e voz ponto a ponto para o período de tempo selecionado.</span><span class="sxs-lookup"><span data-stu-id="d99d7-196">When you click this item, the report shows you the Peer-to-Peer Voice and Video Report for the selected time period.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d99d7-197"><strong>Média de minutos de sessão de áudio ponto a ponto</strong></span><span class="sxs-lookup"><span data-stu-id="d99d7-197"><strong>Average peer-to-peer audio session minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="d99d7-198">Não</span><span class="sxs-lookup"><span data-stu-id="d99d7-198">No</span></span></p></td>
<td><p><span data-ttu-id="d99d7-p117">Tempo médio gasto em sessões de áudio ponto a ponto. Calculado dividindo o tempo de sessão de áudio total pelo número total de sessões de áudio.</span><span class="sxs-lookup"><span data-stu-id="d99d7-p117">Average amount of time spent in peer-to-peer audio sessions. Calculated by dividing the total audio session time by the total number of audio sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d99d7-201"><strong>Total de sessões de vídeo ponto a ponto </strong></span><span class="sxs-lookup"><span data-stu-id="d99d7-201"><strong>Total peer-to-peer video sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="d99d7-202">Não</span><span class="sxs-lookup"><span data-stu-id="d99d7-202">No</span></span></p></td>
<td><p><span data-ttu-id="d99d7-p118">Número total de chamadas de vídeo ponto a ponto. Observe que as sessões de vídeo também são contadas como sessões de áudio: cada sessão de vídeo é contada como uma sessão de vídeo e uma sessão de áudio. Quando você clica nesse item, o relatório mostra o relatório de vídeo e voz ponto a ponto para o período de tempo selecionado.</span><span class="sxs-lookup"><span data-stu-id="d99d7-p118">Total number of peer-to-peer video calls. Note that video sessions are also counted as audio sessions: each video session is counted as one video session and one audio session. When you click this item, the report shows you the Peer-to-Peer Voice and Video Report for the selected time period.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d99d7-206"><strong>Total de minutos de sessão de vídeo ponto a ponto</strong></span><span class="sxs-lookup"><span data-stu-id="d99d7-206"><strong>Total peer-to-peer video session minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="d99d7-207">Não</span><span class="sxs-lookup"><span data-stu-id="d99d7-207">No</span></span></p></td>
<td><p><span data-ttu-id="d99d7-p119">Tempo total gasto em sessões de vídeo ponto a ponto. Quando você clica nesse item, o relatório mostra o relatório de vídeo e voz ponto a ponto para o período de tempo selecionado.</span><span class="sxs-lookup"><span data-stu-id="d99d7-p119">Total amount of time spent in peer-to-peer video sessions. When you click this item, the report shows you the Peer-to-Peer Voice and Video Report for the selected time period.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d99d7-210"><strong>Média de minutos de sessão de vídeo ponto a ponto</strong></span><span class="sxs-lookup"><span data-stu-id="d99d7-210"><strong>Average peer-to-peer video session minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="d99d7-211">Não</span><span class="sxs-lookup"><span data-stu-id="d99d7-211">No</span></span></p></td>
<td><p><span data-ttu-id="d99d7-p120">Tempo médio gasto em sessões de vídeo ponto a ponto. Calculado dividindo o tempo de sessão de vídeo total pelo número total de sessões de áudio.</span><span class="sxs-lookup"><span data-stu-id="d99d7-p120">Average amount of time spent in peer-to-peer video sessions. Calculated by dividing the total video session time by the total number of video sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d99d7-214"><strong>Total de sessões de transferência de arquivo ponto a ponto</strong></span><span class="sxs-lookup"><span data-stu-id="d99d7-214"><strong>Total peer-to-peer file transfer sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="d99d7-215">Não</span><span class="sxs-lookup"><span data-stu-id="d99d7-215">No</span></span></p></td>
<td><p><span data-ttu-id="d99d7-216">Número total de sessões ponto a ponto que incluem transferências de arquivo.</span><span class="sxs-lookup"><span data-stu-id="d99d7-216">Total number of peer-to-peer sessions that included file transfers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d99d7-217"><strong>Total de sessões de compartilhamento de arquivo ponto a ponto</strong></span><span class="sxs-lookup"><span data-stu-id="d99d7-217"><strong>Total peer-to-peer application sharing sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="d99d7-218">Não</span><span class="sxs-lookup"><span data-stu-id="d99d7-218">No</span></span></p></td>
<td><p><span data-ttu-id="d99d7-219">Número total de sessões ponto a ponto que incluem compartilhamento de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="d99d7-219">Total number of peer-to-peer sessions that included application sharing.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

