---
title: 'Lync Server 2013: relatório de tendências de qualidade de mídia do servidor'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Server Media Quality Trend Report
ms:assetid: 8a51fd13-1487-4632-b5ec-f7ae2abe8ed4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205071(v=OCS.15)
ms:contentKeyID: 48184760
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0c36add301665c2e6b689bd1343cc09efeec5b3e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049363"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="server-media-quality-trend-report-in-lync-server-2013"></a><span data-ttu-id="5c017-102">Relatório de tendências de qualidade de mídia do servidor no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5c017-102">Server Media Quality Trend Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5c017-103">_**Última modificação do tópico:** 2012-11-12_</span><span class="sxs-lookup"><span data-stu-id="5c017-103">_**Topic Last Modified:** 2012-11-12_</span></span>

<span data-ttu-id="5c017-p101">O relatório de tendências de qualidade de mídia do servidor é uma forma gráfica de comparar até cinco servidores em relação a métricas de qualidade de experiência, como volume da chamada, percentagem de chamadas ruins, perda de pacotes e tremulação. Ele facilita determinadas tarefas como identificar servidores com desempenho ruim, subutilizados e superutilizados.</span><span class="sxs-lookup"><span data-stu-id="5c017-p101">The Server Media Quality Trend Report provides a way for you to graphically compare up to 5 servers on Quality of Experience metrics such as call volume, poor call percentage, packet loss, and jitter. This makes it easier to do such things as identify servers that are performing poorly, identify servers that are underutilized, or identify servers that are being overused.</span></span>

<div>

## <a name="accessing-the-server-media-quality-trend-report"></a><span data-ttu-id="5c017-106">Acessando o relatório de tendências de qualidade de mídia do servidor</span><span class="sxs-lookup"><span data-stu-id="5c017-106">Accessing the Server Media Quality Trend Report</span></span>

<span data-ttu-id="5c017-107">O relatório de tendências de qualidade de mídia do servidor pode ser acessado por um destes relatórios:</span><span class="sxs-lookup"><span data-stu-id="5c017-107">The Server Media Quality Trend Report can be accessed from either one of the following report:</span></span>

  - <span data-ttu-id="5c017-108">[Relatório de desempenho do servidor no Lync Server 2013](lync-server-2013-server-performance-report.md) (clicando na métrica de tendência)</span><span class="sxs-lookup"><span data-stu-id="5c017-108">[Server Performance Report in Lync Server 2013](lync-server-2013-server-performance-report.md) (by clicking the Trend metric)</span></span>

  - <span data-ttu-id="5c017-109">[Relatório detalhado de chamadas no Lync Server 2013](lync-server-2013-call-detail-report.md) (clicando na métrica de servidor de borda a/V.</span><span class="sxs-lookup"><span data-stu-id="5c017-109">[Call Detail Report in Lync Server 2013](lync-server-2013-call-detail-report.md) (by clicking the A/V edge server metric.</span></span> <span data-ttu-id="5c017-110">Se o chamador ou o receptor for um servidor, você também pode acessar o relatório de tendências de mídia de qualidade do servidor clicando no nome do ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="5c017-110">If the caller or callee is a server, you can also reach the Server Quality Media Trend Report by clicking the endpoint name.)</span></span>

</div>

<div>

## <a name="making-the-best-use-of-server-media-quality-trend-report"></a><span data-ttu-id="5c017-111">Aproveitando ao máximo o relatório de tendências de qualidade de mídia do servidor</span><span class="sxs-lookup"><span data-stu-id="5c017-111">Making the Best Use of Server Media Quality Trend Report</span></span>

<span data-ttu-id="5c017-112">Ao clicar na métrica de tendência no [relatório de desempenho do servidor no Lync Server 2013](lync-server-2013-server-performance-report.md) para um servidor específico, o relatório de tendências de qualidade de mídia do servidor será aberto.</span><span class="sxs-lookup"><span data-stu-id="5c017-112">When you click the Trend metric on the [Server Performance Report in Lync Server 2013](lync-server-2013-server-performance-report.md) for a specific server, the Server Media Quality Trend Report will open.</span></span> <span data-ttu-id="5c017-113">No entanto, você verá uma instância em branco do relatório; o servidor selecionado no Relatório de desempenho do servidor não será exibido na tela.</span><span class="sxs-lookup"><span data-stu-id="5c017-113">However, you will see only a blank instance of that report; the server you selected on the Server Performance Report will not be displayed onscreen.</span></span> <span data-ttu-id="5c017-114">Será necessário selecionar o servidor em questão no menu suspenso "Servidores".</span><span class="sxs-lookup"><span data-stu-id="5c017-114">Instead, you will need to select that server from the Servers dropdown.</span></span> <span data-ttu-id="5c017-115">O menu suspenso "Servidores" apresenta também a opção "Seleciontar tudo".</span><span class="sxs-lookup"><span data-stu-id="5c017-115">Note, too that the Servers dropdown includes a Select All option.</span></span> <span data-ttu-id="5c017-116">Essa opção não funcionará caso haja mais de cinco servidores; o relatório de tendências de qualidade de mídia do servidor só pode exibir dados para, no máximo, cinco servidores por vez.</span><span class="sxs-lookup"><span data-stu-id="5c017-116">This option will not work if you have more than 5 servers; the Server Media Quality Trend Report can only display data for a maximum of 5 servers at a time.</span></span>

<span data-ttu-id="5c017-117">Nos gráficos exibidos pelo relatório de tendências de qualidade de mídia do servidor, os pontos com o rótulo volume de chamadas e a porcentagem de chamadas ruins são hotlinks; clicar em um ponto no gráfico abrirá uma instância do [relatório de lista de chamadas no Lync Server 2013](lync-server-2013-call-list-report.md) , mostrando o total de chamadas (ou chamadas ruins) para o período de tempo especificado.</span><span class="sxs-lookup"><span data-stu-id="5c017-117">On the graphs displayed by the Server Media Quality Trend Report, the points labeled Call Volume and Poor Call Percentage are hotlinks; clicking a point on the graph will open an instance of the [Call List Report in Lync Server 2013](lync-server-2013-call-list-report.md) showing the total calls (or poor calls) for the specified time period.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="5c017-118">Filtros</span><span class="sxs-lookup"><span data-stu-id="5c017-118">Filters</span></span>

<span data-ttu-id="5c017-p104">Os filtros são uma forma de obter dados mais direcionados ou visualizar os dados obtidos de diferentes maneiras. A tabela a seguir relaciona os filtros que podem ser usados no relatório de tendências de qualidade de mídia do servidor.</span><span class="sxs-lookup"><span data-stu-id="5c017-p104">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. The following table lists the filters that you can use with the Server Media Quality Trend Report.</span></span>

### <a name="server-media-quality-trend-report-filters"></a><span data-ttu-id="5c017-121">Filtros do relatório de tendências de qualidade de mídia do servidor</span><span class="sxs-lookup"><span data-stu-id="5c017-121">Server Media Quality Trend Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5c017-122">Nome</span><span class="sxs-lookup"><span data-stu-id="5c017-122">Name</span></span></th>
<th><span data-ttu-id="5c017-123">Descrição</span><span class="sxs-lookup"><span data-stu-id="5c017-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5c017-124"><strong>De</strong></span><span class="sxs-lookup"><span data-stu-id="5c017-124"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="5c017-p105">Data/hora inicial para o intervalo de tempo. Para exibir os dados por hora, insira a data e hora inicial como a seguir:</span><span class="sxs-lookup"><span data-stu-id="5c017-p105">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="5c017-127">7/7/2012 13:00 horas</span><span class="sxs-lookup"><span data-stu-id="5c017-127">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="5c017-p106">Se você não inserir uma hora inicial, o relatório começa automaticamente as 12:00 AM no dia especificado. Para exibir os dados por dia, insira apenas a data:</span><span class="sxs-lookup"><span data-stu-id="5c017-p106">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="5c017-130">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="5c017-130">7/7/2012</span></span></p>
<p><span data-ttu-id="5c017-131">Para exibir por semana ou mês, insira uma data que está dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):</span><span class="sxs-lookup"><span data-stu-id="5c017-131">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="5c017-132">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="5c017-132">7/3/2012</span></span></p>
<p><span data-ttu-id="5c017-133">As semanas sempre são de Domingo a Sábado.</span><span class="sxs-lookup"><span data-stu-id="5c017-133">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5c017-134"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="5c017-134"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="5c017-p107">Data/hora final para o intervalo de tempo. Para exibir os dados por hora, insira a data e hora final como a seguir:</span><span class="sxs-lookup"><span data-stu-id="5c017-p107">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="5c017-137">7/7/2012 13:00 horas</span><span class="sxs-lookup"><span data-stu-id="5c017-137">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="5c017-p108">Se você não inserir uma hora final, o relatório termina automaticamente as 12:00 AM no dia especificado. Para exibir os dados por dia, insira apenas a data:</span><span class="sxs-lookup"><span data-stu-id="5c017-p108">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="5c017-140">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="5c017-140">7/7/2012</span></span></p>
<p><span data-ttu-id="5c017-141">Para exibir por semana ou mês, insira uma data que está dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):</span><span class="sxs-lookup"><span data-stu-id="5c017-141">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="5c017-142">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="5c017-142">7/3/2012</span></span></p>
<p><span data-ttu-id="5c017-143">As semanas são sempre de domingo a sábado.</span><span class="sxs-lookup"><span data-stu-id="5c017-143">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5c017-144"><strong>Intervalo</strong></span><span class="sxs-lookup"><span data-stu-id="5c017-144"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="5c017-p109">Intervalo de tempo. Selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="5c017-p109">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="5c017-147">Por hora (é possível exibir no máximo 25 horas)</span><span class="sxs-lookup"><span data-stu-id="5c017-147">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="5c017-148">Diariamente (é possível exibir no máximo 31 dias)</span><span class="sxs-lookup"><span data-stu-id="5c017-148">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="5c017-149">Semanal (podem ser exibidas, no máximo, 12 semanas)</span><span class="sxs-lookup"><span data-stu-id="5c017-149">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="5c017-p110">Se as datas de início e término ultrapassarem a quantidade máxima permitida para o intervalo selecionado, apenas o máximo de valores (a contar da data de início) será exibido. Por exemplo, se você selecionar o intervalo "Diário" com data de início em 7/7/2012 e data de término em 28/9/2012, os dados são exibidos das 12:00 AM do dia 7/8/2012 a 12:00 AM do dia 7/9/2012 (ou seja, um tota de 31 dias de dados).</span><span class="sxs-lookup"><span data-stu-id="5c017-p110">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed. For example, if you select the Daily interval with a start date of 8/7/2012 and an end date of 9/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5c017-152"><strong>Tipo de servidor</strong></span><span class="sxs-lookup"><span data-stu-id="5c017-152"><strong>Server type</strong></span></span></p></td>
<td><p><span data-ttu-id="5c017-p111">Tipo de servidor envolvido na chamada. Os valores permitidos são</span><span class="sxs-lookup"><span data-stu-id="5c017-p111">Type of server involved in the call. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="5c017-155">Servidor de mediação</span><span class="sxs-lookup"><span data-stu-id="5c017-155">Mediation Server</span></span></p></li>
<li><p><span data-ttu-id="5c017-156">Servidor de Conferência A/V</span><span class="sxs-lookup"><span data-stu-id="5c017-156">A/V Conferencing Server</span></span></p></li>
<li><p><span data-ttu-id="5c017-157">Servidor de Borda A/V</span><span class="sxs-lookup"><span data-stu-id="5c017-157">A/V Edge Server</span></span></p></li>
<li><p><span data-ttu-id="5c017-158">Gateway (servidor de mediação)</span><span class="sxs-lookup"><span data-stu-id="5c017-158">Gateway (Mediation Server)</span></span></p></li>
<li><p><span data-ttu-id="5c017-159">Gateway (Bypass do servidor de mediação)</span><span class="sxs-lookup"><span data-stu-id="5c017-159">Gateway (Mediation Server Bypass)</span></span></p></li>
<li><p><span data-ttu-id="5c017-160">Servidor de conferência AS</span><span class="sxs-lookup"><span data-stu-id="5c017-160">AS Conferencing Server</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5c017-161"><strong>Servidores</strong></span><span class="sxs-lookup"><span data-stu-id="5c017-161"><strong>Servers</strong></span></span></p></td>
<td><p><span data-ttu-id="5c017-p112">Nome do servidor envolvidona sessão; essa lista suspensa é preenchida automaticamente com base no valor do filtro de tipo de arquivo. É possível selecionar até cinco servidores diferentes ao compilar o relatório.</span><span class="sxs-lookup"><span data-stu-id="5c017-p112">Name of the server involved in the session; this dropdown list is automatically populated for you based on the value of the Server type filter. You can select up to 5 different servers when compiling a report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5c017-164"><strong>Tipo de acesso</strong></span><span class="sxs-lookup"><span data-stu-id="5c017-164"><strong>Access type</strong></span></span></p></td>
<td><p><span data-ttu-id="5c017-p113">Indica se o participante fez logon a partir da rede interna ou de uma rede externa. Os valores permitidos são:</span><span class="sxs-lookup"><span data-stu-id="5c017-p113">Indicates whether the participant was logged on to the internal network or from the external network. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="5c017-167">Todos os</span><span class="sxs-lookup"><span data-stu-id="5c017-167">[All]</span></span></p></li>
<li><p><span data-ttu-id="5c017-168">Interna</span><span class="sxs-lookup"><span data-stu-id="5c017-168">Internal</span></span></p></li>
<li><p><span data-ttu-id="5c017-169">Externa</span><span class="sxs-lookup"><span data-stu-id="5c017-169">External</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5c017-170"><strong>Tipo de rede</strong></span><span class="sxs-lookup"><span data-stu-id="5c017-170"><strong>Network type</strong></span></span></p></td>
<td><p><span data-ttu-id="5c017-p114">Indicao tipo de rede ao qual o participante estava conectado. Osvalores permitidos são:</span><span class="sxs-lookup"><span data-stu-id="5c017-p114">Indicates the type of network the participant was connected to. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="5c017-173">Todos os</span><span class="sxs-lookup"><span data-stu-id="5c017-173">[All]</span></span></p></li>
<li><p><span data-ttu-id="5c017-174">Com fio</span><span class="sxs-lookup"><span data-stu-id="5c017-174">Wired</span></span></p></li>
<li><p><span data-ttu-id="5c017-175">Conexão</span><span class="sxs-lookup"><span data-stu-id="5c017-175">Wireless</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5c017-176"><strong>VPN</strong></span><span class="sxs-lookup"><span data-stu-id="5c017-176"><strong>VPN</strong></span></span></p></td>
<td><p><span data-ttu-id="5c017-p115">Indica se o participante externos estava usando conexão VPN durante a sessão. Os valores permitidos são:</span><span class="sxs-lookup"><span data-stu-id="5c017-p115">Indicates whether an external participant was using a virtual private network (VPN) connection during the session. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="5c017-179">Todos os</span><span class="sxs-lookup"><span data-stu-id="5c017-179">[All]</span></span></p></li>
<li><p><span data-ttu-id="5c017-180">VPN</span><span class="sxs-lookup"><span data-stu-id="5c017-180">VPN</span></span></p></li>
<li><p><span data-ttu-id="5c017-181">Não VPN</span><span class="sxs-lookup"><span data-stu-id="5c017-181">Non-VPN</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="5c017-182">Métricas</span><span class="sxs-lookup"><span data-stu-id="5c017-182">Metrics</span></span>

<span data-ttu-id="5c017-183">A tabela a seguir lista as informações fornecidas no relatório de tendências de qualidade de mídia do servidor.</span><span class="sxs-lookup"><span data-stu-id="5c017-183">The following table lists the information provided in the Server Media Quality Trend Report.</span></span>

### <a name="server-media-quality-trend-report-metrics"></a><span data-ttu-id="5c017-184">Métricas do relatório de tendências de qualidade de mídia do servidor</span><span class="sxs-lookup"><span data-stu-id="5c017-184">Server Media Quality Trend Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5c017-185">Nome</span><span class="sxs-lookup"><span data-stu-id="5c017-185">Name</span></span></th>
<th><span data-ttu-id="5c017-186">É possível classificar este item?</span><span class="sxs-lookup"><span data-stu-id="5c017-186">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="5c017-187">Descrição</span><span class="sxs-lookup"><span data-stu-id="5c017-187">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5c017-188"><strong>Volume da chamada</strong></span><span class="sxs-lookup"><span data-stu-id="5c017-188"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="5c017-189">Não</span><span class="sxs-lookup"><span data-stu-id="5c017-189">No</span></span></p></td>
<td><p><span data-ttu-id="5c017-190">Número total de chamadas.</span><span class="sxs-lookup"><span data-stu-id="5c017-190">Total number of calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5c017-191"><strong>Degradação (MOS)</strong></span><span class="sxs-lookup"><span data-stu-id="5c017-191"><strong>Degradation (MOS)</strong></span></span></p></td>
<td><p><span data-ttu-id="5c017-192">Não</span><span class="sxs-lookup"><span data-stu-id="5c017-192">No</span></span></p></td>
<td><p><span data-ttu-id="5c017-193">Valor médio de uma degradação da marca de opção (média) em uma chamada.</span><span class="sxs-lookup"><span data-stu-id="5c017-193">Average amount of MOS (mean option score) degradation experienced during a call.</span></span> <span data-ttu-id="5c017-194">Os valores de degradação podem variar de um baixo de 0,0 para um alto de 5,0; um valor de 0,5 ou menos representa degradação aceitável.</span><span class="sxs-lookup"><span data-stu-id="5c017-194">Degradation values can range from a low of 0.0 to a high of 5.0; a value of 0.5 or less represents acceptable degradation.</span></span> <span data-ttu-id="5c017-195">Historicamente, pontuações de opções médias foram calculadas com usuários classificando a qualidade de uma chamada em uma escala de 1 a 5.</span><span class="sxs-lookup"><span data-stu-id="5c017-195">Historically, mean options scores were calculated by having users rate the quality of a call on a scale of 1-to-5.</span></span> <span data-ttu-id="5c017-196">O Lync Server usa um conjunto de algoritmos para prever como os usuários classificaram uma chamada.</span><span class="sxs-lookup"><span data-stu-id="5c017-196">Lync Server uses a set of algorithms to predict how users would have rated a call.</span></span></p>
<p><span data-ttu-id="5c017-p117">Os valores de degradação altos podem ser causados por congestão, falta de largura de banda, congestionamento ou interferência sem fio ou um servidor de mídia ou ponto de extremidade sobrecarregado. A alta degradação resulta em perda ou distorção de áudio.</span><span class="sxs-lookup"><span data-stu-id="5c017-p117">High degradation values can be caused by congestion; lack of bandwidth; wireless congestion or interference, or an overloaded media server or endpoint. High degradation results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5c017-199"><strong>Percentual de chamadas ruins</strong></span><span class="sxs-lookup"><span data-stu-id="5c017-199"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="5c017-200">Não</span><span class="sxs-lookup"><span data-stu-id="5c017-200">No</span></span></p></td>
<td><p><span data-ttu-id="5c017-p118">O número total de chamadas classificadas como ruins. Uma chamada ruim é qualquer chamada em que no mínimo uma das métricas medidas excedeu o valor permitido (por exemplo, uma chamada com tremulação excessiva).</span><span class="sxs-lookup"><span data-stu-id="5c017-p118">The total number of calls classified as poor. A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5c017-203"><strong>Viagem de ida e volta (ms)</strong></span><span class="sxs-lookup"><span data-stu-id="5c017-203"><strong>Round trip (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="5c017-204">Não</span><span class="sxs-lookup"><span data-stu-id="5c017-204">No</span></span></p></td>
<td><p><span data-ttu-id="5c017-p119">Quantidade média de tempo (em milésimos de seguntos) exigida para que um pacote (protocolo de transporte em tempo real) viaje até outra extremidade e retorne. Tempos de viagem de ida e volta de 200 milésimos de segundo ou menos são considerados de qualidade aceitável.</span><span class="sxs-lookup"><span data-stu-id="5c017-p119">Average amount of time (in milliseconds) required for a Real-Time Transport Protocol packet to travel to one endpoint and then back. Round-trip times of 200 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="5c017-p120">Viagens de ida e volta com altos valores podem ser resultado do roteamento de chamadas internacionais, configurações incorretas de roteamento ou servidor de mídia sobrecarregado. Viagens de ida e volta com altos valores resultam em dificuldades para conversas de áudio bidirecionais e em tempo real.</span><span class="sxs-lookup"><span data-stu-id="5c017-p120">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5c017-209"><strong>Perda de pacote </strong></span><span class="sxs-lookup"><span data-stu-id="5c017-209"><strong>Packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="5c017-210">Não</span><span class="sxs-lookup"><span data-stu-id="5c017-210">No</span></span></p></td>
<td><p><span data-ttu-id="5c017-p121">Taxa média de perda de pacotes de Protocolo de Transporte em Tempo Real (RTP). (A perda de pacotes ocorre quando pacotes RTP, um protocolo usado para transmitir áudio e vídeo pela internet, falha ao tentar alcançar seu destino). Altas taxas de perda geralmente são causadas por congestionamento, insuficiência da largura de banda, congestionamento ou interferência na rede sem fio ou um servidor de mídia sobrecarregado. A perda de pacotes normalmente resulta em distorção ou perda de áudio.</span><span class="sxs-lookup"><span data-stu-id="5c017-p121">Average rate of Real-Time Transport Protocol (RTP) packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5c017-214"><strong>Tremulação (ms)</strong></span><span class="sxs-lookup"><span data-stu-id="5c017-214"><strong>Jitter (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="5c017-215">Não</span><span class="sxs-lookup"><span data-stu-id="5c017-215">No</span></span></p></td>
<td><p><span data-ttu-id="5c017-216">Tremulação média detectada entre chegadas de pacote RTP.</span><span class="sxs-lookup"><span data-stu-id="5c017-216">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="5c017-217">(Tremulação é uma medida do &quot;tremula&quot; de uma chamada.) Os valores de variação alta geralmente são causados por congestionamento ou por um servidor de mídia sobrecarregado e resultam em um áudio distorcido ou perdido.</span><span class="sxs-lookup"><span data-stu-id="5c017-217">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5c017-218"><strong>Taxa de correção oculta</strong></span><span class="sxs-lookup"><span data-stu-id="5c017-218"><strong>Healer concealed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="5c017-219">Não</span><span class="sxs-lookup"><span data-stu-id="5c017-219">No</span></span></p></td>
<td><p><span data-ttu-id="5c017-p123">Taxa média de amostras de áudio ocultas para o número total de amostras. (Uma amostra de áudio oculta é uma técnica usada para suavizar a transição abrupta que normalmente seria causada por pacotes de rede descartados.) Valores altos indicam níveis consideráveis de perda de ocultação aplicada causada por perda de pacote ou tremulação e resulta na perda ou distorção de áudio.</span><span class="sxs-lookup"><span data-stu-id="5c017-p123">Average ratio of concealed audio samples to the total to the total number of samples. (A concealed audio sample is a technique used to smooth out the abrupt transition that would usually be caused by dropped network packets.) High values indicate significant levels of loss concealment applied caused by packet loss or jitter, and results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5c017-222"><strong>Taxa de correção estendida</strong></span><span class="sxs-lookup"><span data-stu-id="5c017-222"><strong>Healer stretched ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="5c017-223">Não</span><span class="sxs-lookup"><span data-stu-id="5c017-223">No</span></span></p></td>
<td><p><span data-ttu-id="5c017-p124">Taxa média de amostras de áudio estendidas para o número total de amostras. (Áudio estendido é o áudio que foi expandido a fim de ajudar a manter a qualidade da chamada quando um pacote de rede descartado é detectado.) Valores altos indicam níveis significativos de extensão de amostra causada por tremulação e resultam em um som robótico ou distorcido.</span><span class="sxs-lookup"><span data-stu-id="5c017-p124">Average ratio of stretched audio samples to the total to the total number of samples. (Stretched audio is audio that has been expanded to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample stretching caused by jitter, and result in audio sounding robotic or distorted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5c017-226"><strong>Taxa de correção compactada</strong></span><span class="sxs-lookup"><span data-stu-id="5c017-226"><strong>Healer compressed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="5c017-227">Não</span><span class="sxs-lookup"><span data-stu-id="5c017-227">No</span></span></p></td>
<td><p><span data-ttu-id="5c017-p125">Taxa média de amostras de áudio compactadas para o número total de amostras. (Áudio compactado é o áudio que foi compactado para ajudar a manter a qualidade da chamada quando um pacote de rede descartado é detectado.) Valores altos podem indicar níveis consideráveis de compactação de amostra causada por tremulação e resultam em um som acelerado ou distorcido.</span><span class="sxs-lookup"><span data-stu-id="5c017-p125">Average ratio of compressed audio samples to the total number of samples. (Compressed audio is audio that has been compressed to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample compression caused by jitter, and result in audio sounding accelerated or distorted.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

