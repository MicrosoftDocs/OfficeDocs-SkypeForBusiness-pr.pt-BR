---
title: 'Lync Server 2013: relatório de desempenho do servidor'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Server Performance Report
ms:assetid: 942bb39a-1790-498e-9d99-8f6ce2d155c3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615018(v=OCS.15)
ms:contentKeyID: 48184879
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 05c1e366c797eb0c626d00744ef6f0088d28e465
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42143979"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="server-performance-report-in-lync-server-2013"></a><span data-ttu-id="24a3c-102">Relatório de desempenho do servidor no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="24a3c-102">Server Performance Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="24a3c-103">_**Última modificação do tópico:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="24a3c-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="24a3c-104">O relatório de desempenho do servidor fornece uma lista de servidores do Microsoft Lync Server 2013 que experimentaram a maior porcentagem de chamadas ruins.</span><span class="sxs-lookup"><span data-stu-id="24a3c-104">The Server Performance Report provides a list of Microsoft Lync Server 2013 servers that have experienced the highest-percentage of poor calls.</span></span> <span data-ttu-id="24a3c-105">O relatório divide os servidores por tipo, relatando estatísticas separadas para os seguintes tipos:</span><span class="sxs-lookup"><span data-stu-id="24a3c-105">The report breaks down servers by server type, reporting separate statistics for the following types:</span></span>

  - <span data-ttu-id="24a3c-106">Servidor de Mediação</span><span class="sxs-lookup"><span data-stu-id="24a3c-106">Mediation Server</span></span>

  - <span data-ttu-id="24a3c-107">Servidor de Conferência A/V</span><span class="sxs-lookup"><span data-stu-id="24a3c-107">A/V Conferencing Server</span></span>

  - <span data-ttu-id="24a3c-108">Servidor de borda A/V</span><span class="sxs-lookup"><span data-stu-id="24a3c-108">A/V Edge Server</span></span>

  - <span data-ttu-id="24a3c-109">Gateway (Servidor de Mediação)</span><span class="sxs-lookup"><span data-stu-id="24a3c-109">Gateway (Mediation Server)</span></span>

  - <span data-ttu-id="24a3c-110">Gateway (desvio de Servidor de Mediação)</span><span class="sxs-lookup"><span data-stu-id="24a3c-110">Gateway (Mediation Server bypass)</span></span>

  - <span data-ttu-id="24a3c-111">Vídeo (incluindo métricas de vídeo para Servidores de Conferência A/V e Servidores de Borda A/V)</span><span class="sxs-lookup"><span data-stu-id="24a3c-111">Video (including video metrics for A/V Conferencing servers and A/V Edge servers)</span></span>

  - <span data-ttu-id="24a3c-112">Compartilhamento de aplicativos (incluindo métricas de compartilhamento de aplicativos para Servidores de Conferência A/V e Servidores de Borda A/V)</span><span class="sxs-lookup"><span data-stu-id="24a3c-112">Application Sharing (including application sharing metrics for A/V Conferencing servers and A/V Edge servers)</span></span>

<span data-ttu-id="24a3c-p102">É importante observar a classificação mostrada neste relatório como classificação relativa. Por exemplo, suponha que seu servidor com pior desempenho tenha uma chamada ruim entre suas 1.000 chamadas efetuadas. Isso é uma porcentagem de 0,1% que é mais que aceitável. No entanto, se esse for seu servidor com pior desempenho (isto é, se todos os seus outros servidores tiverem uma porcentagem de chamada ruim mais baixa que 0,1%), então esse servidor aparecerá mesmo assim no Relatório de desempenho do servidor.</span><span class="sxs-lookup"><span data-stu-id="24a3c-p102">It’s important to note that the ranking shown in this report as relative rankings. For example, suppose your worst-performing server had one poor call among its 1,000 placed calls. That's a more-than-acceptable percentage of .1%. However, if that's the worst-performing server you have (that is, if all your other servers have a poor call percentage even lower than .1%), then that server will still appear on the Server Performance Report.</span></span>

<div>

## <a name="accessing-the-server-performance-report"></a><span data-ttu-id="24a3c-117">Como avaliar o Relatório de desempenho do servidor</span><span class="sxs-lookup"><span data-stu-id="24a3c-117">Accessing the Server Performance Report</span></span>

<span data-ttu-id="24a3c-118">O Relatório de desempenho do servidor é acessado a partir da página inicial dos Relatórios de Monitoramento.</span><span class="sxs-lookup"><span data-stu-id="24a3c-118">The Server Performance Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="24a3c-119">Você pode fazer uma busca detalhada no [relatório de lista de chamadas no Lync Server 2013](lync-server-2013-call-list-report.md) clicando em uma das seguintes métricas:</span><span class="sxs-lookup"><span data-stu-id="24a3c-119">You can drill down to the [Call List Report in Lync Server 2013](lync-server-2013-call-list-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="24a3c-120">Volume da chamada</span><span class="sxs-lookup"><span data-stu-id="24a3c-120">Call volume</span></span>

  - <span data-ttu-id="24a3c-121">Porcentagem de chamada inválida</span><span class="sxs-lookup"><span data-stu-id="24a3c-121">Poor call percentage</span></span>

<span data-ttu-id="24a3c-122">Além disso, você ver os detalhes do Relatório de Tendência de Qualidade de Mídia do Servidor clicando na seguinte métrica:</span><span class="sxs-lookup"><span data-stu-id="24a3c-122">In addition, you can drill down to the Server Media Quality Trend Report by clicking the following metric:</span></span>

  - <span data-ttu-id="24a3c-123">Trend</span><span class="sxs-lookup"><span data-stu-id="24a3c-123">Trend</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-server-performance-report"></a><span data-ttu-id="24a3c-124">Como usar melhor o Relatório de desempenho do servidor</span><span class="sxs-lookup"><span data-stu-id="24a3c-124">Making the Best Use of the Server Performance Report</span></span>

<span data-ttu-id="24a3c-p104">O Relatório de desempenho do servidor fornece várias maneiras de filtrar dados; por exemplo, você pode filtrar por tipo de rede (chamadas feitas de uma chamada cabeada x chamadas de uma conexão sem fio) e tipo de acesso (chamadas feitas de dentro do firewall x chamadas feitas de fora do firewall). Ao exibir o relatório de desempenho do servidor, é uma boa ideia usar esses filtros. Por exemplo, suponha que você tem um Servidor de Mediação que tenha uma porcentagem de chamadas ruins igual a 3,24%. Se você observar apenas as chamadas sem fio, o mesmo servidor teria uma porcentagem de chamadas ruins próxima de 20%. Isso significa que o servidor tem dificuldades com chamadas sem fio, um problema que é obscurecido parcialmente porque o servidor não tem problemas em lidar com chamadas com fio.</span><span class="sxs-lookup"><span data-stu-id="24a3c-p104">The Server Performance Report provides a number of ways to filter data; for example, you can filter on network type (calls made from a wired connection vs. calls made from a wireless connection) and access type (calls made from inside the firewall vs. calls made from outside the firewall). It's a good idea when viewing the server performance report to make use of these filters. For example, suppose you have a Mediation Server that has a poor call percentage of 3.24%. If you look solely at wireless calls, that same server might have a poor call percentage approaching 20%. That means that the server was having difficulty with wireless calls, a problem that is partially obscured because the server was not having problems with wired calls.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="24a3c-130">Filtros</span><span class="sxs-lookup"><span data-stu-id="24a3c-130">Filters</span></span>

<span data-ttu-id="24a3c-p105">Filtros fornecem uma forma de retornar um conjunto de dados mais focado ou exibir os dados retornados de diferentes formas. Por exemplo o Relatório de Desempenho do Servidor permite fazer coisas como filtrar os dados retornados por tipo de servidor ou por tipo de rede (ou seja, com ou sem fio). Você também pode escolher como os dados serão agrupados. Neste caso, os dados são agrupados por hora, dia, semana ou mês.</span><span class="sxs-lookup"><span data-stu-id="24a3c-p105">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Server Performance Report enables you to do such things as filter the returned data by server type or by network type (that is, wired or wireless). You can also choose how data should be grouped. In this case, data is grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="24a3c-135">A tabela a seguir lista os filtros que podem ser usados com o Relatório de Desempenho do Servidor.</span><span class="sxs-lookup"><span data-stu-id="24a3c-135">The following table lists the filters that you can use with the Server Performance Report.</span></span>

### <a name="server-performance-report-filters"></a><span data-ttu-id="24a3c-136">Filtros do Relatório de Desempenho do Servidor</span><span class="sxs-lookup"><span data-stu-id="24a3c-136">Server Performance Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="24a3c-137">Nome</span><span class="sxs-lookup"><span data-stu-id="24a3c-137">Name</span></span></th>
<th><span data-ttu-id="24a3c-138">Descrição</span><span class="sxs-lookup"><span data-stu-id="24a3c-138">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="24a3c-139"><strong>De</strong></span><span class="sxs-lookup"><span data-stu-id="24a3c-139"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="24a3c-p106">Data/hora inicial para o intervalo de tempo. Para exibir os dados por hora, insira a data e hora inicial como a seguir:</span><span class="sxs-lookup"><span data-stu-id="24a3c-p106">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="24a3c-142">7/7/2012 13:00 horas</span><span class="sxs-lookup"><span data-stu-id="24a3c-142">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="24a3c-p107">Se você não inserir uma hora inicial, o relatório começa automaticamente as 12:00 AM no dia especificado. Para exibir os dados por dia, insira apenas a data:</span><span class="sxs-lookup"><span data-stu-id="24a3c-p107">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="24a3c-145">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="24a3c-145">7/7/2012</span></span></p>
<p><span data-ttu-id="24a3c-146">Para exibir por semana ou mês, insira uma data que está dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):</span><span class="sxs-lookup"><span data-stu-id="24a3c-146">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="24a3c-147">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="24a3c-147">7/3/2012</span></span></p>
<p><span data-ttu-id="24a3c-148">As semanas são sempre de domingo a sábado.</span><span class="sxs-lookup"><span data-stu-id="24a3c-148">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24a3c-149"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="24a3c-149"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="24a3c-p108">Data/hora final para o intervalo de tempo. Para exibir os dados por hora, insira a data e hora final como a seguir:</span><span class="sxs-lookup"><span data-stu-id="24a3c-p108">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="24a3c-152">7/7/2012 13:00 horas</span><span class="sxs-lookup"><span data-stu-id="24a3c-152">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="24a3c-p109">Se você não inserir uma hora final, o relatório termina automaticamente as 12:00 AM no dia especificado. Para exibir os dados por dia, insira apenas a data:</span><span class="sxs-lookup"><span data-stu-id="24a3c-p109">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="24a3c-155">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="24a3c-155">7/7/2012</span></span></p>
<p><span data-ttu-id="24a3c-156">Para exibir por semana ou mês, insira uma data que está dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):</span><span class="sxs-lookup"><span data-stu-id="24a3c-156">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="24a3c-157">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="24a3c-157">7/3/2012</span></span></p>
<p><span data-ttu-id="24a3c-158">As semanas sempre vão de domingo a sábado.</span><span class="sxs-lookup"><span data-stu-id="24a3c-158">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24a3c-159"><strong>Tipo de Servidor</strong></span><span class="sxs-lookup"><span data-stu-id="24a3c-159"><strong>Server type</strong></span></span></p></td>
<td><p><span data-ttu-id="24a3c-p110">Indica o tipo de servidor cujo desempenho deve ser reportado. Selecione um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="24a3c-p110">Indicates the type of server whose performance should be reported. Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="24a3c-162">Todos os</span><span class="sxs-lookup"><span data-stu-id="24a3c-162">[All]</span></span></p></li>
<li><p><span data-ttu-id="24a3c-163">Servidor de Mediação</span><span class="sxs-lookup"><span data-stu-id="24a3c-163">Mediation Server</span></span></p></li>
<li><p><span data-ttu-id="24a3c-164">Servidor de Conferência A/V</span><span class="sxs-lookup"><span data-stu-id="24a3c-164">A/V Conferencing Server</span></span></p></li>
<li><p><span data-ttu-id="24a3c-165">Servidor de Borda A/V</span><span class="sxs-lookup"><span data-stu-id="24a3c-165">A/V Edge Server</span></span></p></li>
</ol></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24a3c-166"><strong>N Primeiros</strong></span><span class="sxs-lookup"><span data-stu-id="24a3c-166"><strong>Top N</strong></span></span></p></td>
<td><p><span data-ttu-id="24a3c-p111">Indica o número de servidores (com base no percentual de chamadas ruins) a serem exibidos em cada categoria. Por exemplo, se você selecionar <strong>5</strong>, os cinco servidores com pior desempenho são exibidos. Selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="24a3c-p111">Indicates the number of servers (based on their poor call percentage) to be displayed in each category. For example, if you select <strong>5</strong> then the five poorest-performing servers are displayed. Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="24a3c-170">Todos os</span><span class="sxs-lookup"><span data-stu-id="24a3c-170">[All]</span></span></p></li>
<li><p><span data-ttu-id="24a3c-171">0,5</span><span class="sxs-lookup"><span data-stu-id="24a3c-171">5</span></span></p></li>
<li><p><span data-ttu-id="24a3c-172">10 </span><span class="sxs-lookup"><span data-stu-id="24a3c-172">10</span></span></p></li>
</ol></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24a3c-173"><strong>Tipo de acesso</strong></span><span class="sxs-lookup"><span data-stu-id="24a3c-173"><strong>Access type</strong></span></span></p></td>
<td><p><span data-ttu-id="24a3c-p112">Indica se um cliente estava conectado na rede interna ou na rede externa quando a chamada foi realizada. Selecione um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="24a3c-p112">Indicates whether the client was logged on to the internal network or the external network when the call was placed. Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="24a3c-176">Todos os</span><span class="sxs-lookup"><span data-stu-id="24a3c-176">[All]</span></span></p></li>
<li><p><span data-ttu-id="24a3c-177">Interna</span><span class="sxs-lookup"><span data-stu-id="24a3c-177">Internal</span></span></p></li>
<li><p><span data-ttu-id="24a3c-178">Externa</span><span class="sxs-lookup"><span data-stu-id="24a3c-178">External</span></span></p></li>
</ol></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24a3c-179"><strong>Tipo de rede</strong></span><span class="sxs-lookup"><span data-stu-id="24a3c-179"><strong>Network type</strong></span></span></p></td>
<td><p><span data-ttu-id="24a3c-p113">Indica o tipo de rede que o cliente estava conectado quando a chamada foi realizada. Selecione um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="24a3c-p113">Indicates the type of network the client was connected to when the call was placed. Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="24a3c-182">Todos os</span><span class="sxs-lookup"><span data-stu-id="24a3c-182">[All]</span></span></p></li>
<li><p><span data-ttu-id="24a3c-183">Com fio</span><span class="sxs-lookup"><span data-stu-id="24a3c-183">Wired</span></span></p></li>
<li><p><span data-ttu-id="24a3c-184">Conexão</span><span class="sxs-lookup"><span data-stu-id="24a3c-184">Wireless</span></span></p></li>
</ol></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24a3c-185"><strong>VPN</strong></span><span class="sxs-lookup"><span data-stu-id="24a3c-185"><strong>VPN</strong></span></span></p></td>
<td><p><span data-ttu-id="24a3c-p114">Indica se um cliente externo estava usando uma conexão de rede privada virtual (VPN) quando a chamada foi realizada. Selecione um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="24a3c-p114">Indicates whether an external client was using a virtual private network (VPN) connection when the call was placed. Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="24a3c-188">Todos os</span><span class="sxs-lookup"><span data-stu-id="24a3c-188">[All]</span></span></p></li>
<li><p><span data-ttu-id="24a3c-189">VPN</span><span class="sxs-lookup"><span data-stu-id="24a3c-189">VPN</span></span></p></li>
<li><p><span data-ttu-id="24a3c-190">Não VPN</span><span class="sxs-lookup"><span data-stu-id="24a3c-190">Non-VPN</span></span></p></li>
</ol></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="24a3c-191">Métricas</span><span class="sxs-lookup"><span data-stu-id="24a3c-191">Metrics</span></span>

<span data-ttu-id="24a3c-192">A tabela a seguir lista as informações fornecidas no Relatório de Desempenho do Servidor.</span><span class="sxs-lookup"><span data-stu-id="24a3c-192">The following table lists the information provided in the Server Performance Report.</span></span>

### <a name="server-performance-report-metrics-audio-call-summary"></a><span data-ttu-id="24a3c-193">Métricas do Relatório de Desempenho do Servidor: Resumo da chamada de áudio</span><span class="sxs-lookup"><span data-stu-id="24a3c-193">Server Performance Report Metrics: Audio Call Summary</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="24a3c-194">Nome</span><span class="sxs-lookup"><span data-stu-id="24a3c-194">Name</span></span></th>
<th><span data-ttu-id="24a3c-195">É possível classificar por</span><span class="sxs-lookup"><span data-stu-id="24a3c-195">Can Sort On</span></span></th>
<th><span data-ttu-id="24a3c-196">Descrição</span><span class="sxs-lookup"><span data-stu-id="24a3c-196">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="24a3c-197"><strong>Servidor</strong></span><span class="sxs-lookup"><span data-stu-id="24a3c-197"><strong>Server</strong></span></span></p></td>
<td><p><span data-ttu-id="24a3c-198">Não</span><span class="sxs-lookup"><span data-stu-id="24a3c-198">No</span></span></p></td>
<td><p><span data-ttu-id="24a3c-199">Nome/endereço IP do servidor.</span><span class="sxs-lookup"><span data-stu-id="24a3c-199">Name/IP address of the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24a3c-200"><strong>Volume de chamadas</strong></span><span class="sxs-lookup"><span data-stu-id="24a3c-200"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="24a3c-201">Não</span><span class="sxs-lookup"><span data-stu-id="24a3c-201">No</span></span></p></td>
<td><p><span data-ttu-id="24a3c-202">Número total de chamadas realizadas.</span><span class="sxs-lookup"><span data-stu-id="24a3c-202">Total number of calls made.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24a3c-203"><strong>Percentual de chamadas ruins</strong></span><span class="sxs-lookup"><span data-stu-id="24a3c-203"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="24a3c-204">Não</span><span class="sxs-lookup"><span data-stu-id="24a3c-204">No</span></span></p></td>
<td><p><span data-ttu-id="24a3c-p115">Número total de chamadas classificadas como ruins. Uma chamada ruim é qualquer chamada em que no mínimo uma das métricas medidas excedeu o valor permitido (por exemplo, uma chamada com tremulação excessiva).</span><span class="sxs-lookup"><span data-stu-id="24a3c-p115">Total number of calls classified as poor. A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24a3c-207"><strong>Viagem de ida e volta (ms)</strong></span><span class="sxs-lookup"><span data-stu-id="24a3c-207"><strong>Round trip (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="24a3c-208">Sim</span><span class="sxs-lookup"><span data-stu-id="24a3c-208">Yes</span></span></p></td>
<td><p><span data-ttu-id="24a3c-p116">Quantidade média (em milissegundos) necessária para um pacote de protocolo de transporte em tempo real (RTP) viajar para outro ponto de extremidade e voltar. Tempos de resposta de 100 milissegundos ou menos são considerados de qualidade aceitável.</span><span class="sxs-lookup"><span data-stu-id="24a3c-p116">Average amount of (in milliseconds) required for a real-time transport protocol (RTP) packet to travel to another endpoint and then back. Round-trip times of 100 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="24a3c-p117">Altos valores de tempo de resposta podem ser causados por roteamento de chamadas internacionais, configuração incorreta de um roteamento ou um servidor de mídia sobrecarregado. Tempos de resposta altos resultam em dificuldades para conversas de áudio bidirecionais e em tempo real.</span><span class="sxs-lookup"><span data-stu-id="24a3c-p117">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24a3c-213"><strong>Degradação (MOS)</strong></span><span class="sxs-lookup"><span data-stu-id="24a3c-213"><strong>Degradation (MOS)</strong></span></span></p></td>
<td><p><span data-ttu-id="24a3c-214">Sim</span><span class="sxs-lookup"><span data-stu-id="24a3c-214">Yes</span></span></p></td>
<td><p><span data-ttu-id="24a3c-215">Quantidade média da degradação MOS enfrentada durante uma chamada.</span><span class="sxs-lookup"><span data-stu-id="24a3c-215">Average amount of mean opinion score (MOS) degradation experienced during a call.</span></span> <span data-ttu-id="24a3c-216">Os valores de degradação variam de um baixo de 0,0 a um alto de 5,0.</span><span class="sxs-lookup"><span data-stu-id="24a3c-216">Degradation values can range from a low of 0.0 to a high of 5.0.</span></span> <span data-ttu-id="24a3c-217">Um valor de 0,5 ou menos representa degradação aceitável.</span><span class="sxs-lookup"><span data-stu-id="24a3c-217">A value of 0.5 or less represents acceptable degradation.</span></span> <span data-ttu-id="24a3c-218">Historicamente, pontuações de opções médias foram calculadas com usuários classificando a qualidade de uma chamada em uma escala de 1 a 5.</span><span class="sxs-lookup"><span data-stu-id="24a3c-218">Historically, mean options scores were calculated by having users rate the quality of a call on a scale of 1-to-5.</span></span> <span data-ttu-id="24a3c-219">No Lync Server, o Monitoring Server usa um conjunto de algoritmos para prever como os usuários teriam classificado uma chamada.</span><span class="sxs-lookup"><span data-stu-id="24a3c-219">In Lync Server, the Monitoring Server uses a set of algorithms to predict how users would have rated a call.</span></span></p>
<p><span data-ttu-id="24a3c-p119">Os valores de degradação altos podem ser causados por congestão, falta de largura de banda, congestionamento ou interferência sem fio ou um servidor de mídia ou ponto de extremidade sobrecarregado. A alta degradação resulta em perda ou distorção de áudio.</span><span class="sxs-lookup"><span data-stu-id="24a3c-p119">High degradation values can be caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server or endpoint. High degradation results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24a3c-222"><strong>Perda de pacote </strong></span><span class="sxs-lookup"><span data-stu-id="24a3c-222"><strong>Packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="24a3c-223">Sim</span><span class="sxs-lookup"><span data-stu-id="24a3c-223">Yes</span></span></p></td>
<td><p><span data-ttu-id="24a3c-p120">Taxa média de perda de pacotes de protocolo de transporte em tempo real (RTP) (a perda de pacotes ocorre quando pacotes RTP, um protocolo usado para transmitir áudio e vídeo pela internet, falha ao tentar alcançar seu destino). Altas taxas de perda geralmente são causadas por congestionamento, insuficiência da largura de banda, congestionamento ou interferência na rede sem fio ou um servidor de mídia sobrecarregado. A perda de pacotes normalmente resulta em distorção ou perda de áudio.</span><span class="sxs-lookup"><span data-stu-id="24a3c-p120">Average rate of real-time transport protocol (RTP) packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24a3c-227"><strong>Tremulação (ms)</strong></span><span class="sxs-lookup"><span data-stu-id="24a3c-227"><strong>Jitter (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="24a3c-228">Sim</span><span class="sxs-lookup"><span data-stu-id="24a3c-228">Yes</span></span></p></td>
<td><p><span data-ttu-id="24a3c-229">Tremulação média detectada entre chegadas de pacote RTP.</span><span class="sxs-lookup"><span data-stu-id="24a3c-229">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="24a3c-230">(Tremulação é uma medida do &quot;tremula&quot; de uma chamada.) Os valores de variação alta geralmente são causados por congestionamento ou por um servidor de mídia sobrecarregado e resultam em um áudio distorcido ou perdido.</span><span class="sxs-lookup"><span data-stu-id="24a3c-230">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24a3c-231"><strong>Taxa de correção oculta</strong></span><span class="sxs-lookup"><span data-stu-id="24a3c-231"><strong>Healer concealed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="24a3c-232">Sim</span><span class="sxs-lookup"><span data-stu-id="24a3c-232">Yes</span></span></p></td>
<td><p><span data-ttu-id="24a3c-p122">Taxa média de amostras de áudio ocultas para o número total de amostras. (Uma amostra de áudio oculta é uma técnica usada para suavizar a transição abrupta que normalmente seria causada por pacotes de rede descartados.) Valores altos indicam níveis consideráveis de perda de ocultação aplicada causada por perda de pacote ou tremulação e resulta na perda ou distorção de áudio.</span><span class="sxs-lookup"><span data-stu-id="24a3c-p122">Average ratio of concealed audio samples to the total to the total number of samples. (A concealed audio sample is a technique used to smooth out the abrupt transition that would usually be caused by dropped network packets.) High values indicate significant levels of loss concealment applied caused by packet loss or jitter, and results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24a3c-235"><strong>Taxa de correção estendida</strong></span><span class="sxs-lookup"><span data-stu-id="24a3c-235"><strong>Healer stretched ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="24a3c-236">Sim</span><span class="sxs-lookup"><span data-stu-id="24a3c-236">Yes</span></span></p></td>
<td><p><span data-ttu-id="24a3c-p123">Taxa média de amostras de áudio estendidas para o número total de amostras. (Áudio estendido é o áudio que foi expandido a fim de ajudar a manter a qualidade da chamada quando um pacote de rede descartado é detectado.) Valores altos indicam níveis significativos de extensão de amostra causada por tremulação e resultam em um som robótico ou distorcido.</span><span class="sxs-lookup"><span data-stu-id="24a3c-p123">Average ratio of stretched audio samples to the total to the total number of samples. (Stretched audio is audio that has been expanded to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample stretching caused by jitter, and result in audio sounding robotic or distorted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24a3c-239"><strong>Taxa de correção compactada</strong></span><span class="sxs-lookup"><span data-stu-id="24a3c-239"><strong>Healer compressed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="24a3c-240">Sim</span><span class="sxs-lookup"><span data-stu-id="24a3c-240">Yes</span></span></p></td>
<td><p><span data-ttu-id="24a3c-p124">Taxa média de amostras de áudio compactadas para o número total de amostras (áudio compactado é o áudio que foi comprimido para ajudar a manter a qualidade da chamada quando um pacote de rede ignorado foi detectado). Altos valores indicam níveis significativos de compressão de amostras causados por tremulação, o que resulta em áudio acelerado ou distorcido.</span><span class="sxs-lookup"><span data-stu-id="24a3c-p124">Average ratio of compressed audio samples to the total number of samples. (Compressed audio is audio that has been compressed to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample compression caused by jitter, and result in audio sounding accelerated or distorted.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="server-performance-report-metrics-video-call-summary"></a><span data-ttu-id="24a3c-243">Métricas do Relatório de Desempenho do Servidor: Resumo da chamada de vídeo</span><span class="sxs-lookup"><span data-stu-id="24a3c-243">Server Performance Report Metrics: Video Call Summary</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="24a3c-244">Nome</span><span class="sxs-lookup"><span data-stu-id="24a3c-244">Name</span></span></th>
<th><span data-ttu-id="24a3c-245">É possível classificar este item?</span><span class="sxs-lookup"><span data-stu-id="24a3c-245">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="24a3c-246">Descrição</span><span class="sxs-lookup"><span data-stu-id="24a3c-246">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="24a3c-247"><strong>Tipo de Chamada/Tipo de Ponto de Extremidade</strong></span><span class="sxs-lookup"><span data-stu-id="24a3c-247"><strong>Call type/Endpoint type</strong></span></span></p></td>
<td><p><span data-ttu-id="24a3c-248">Não</span><span class="sxs-lookup"><span data-stu-id="24a3c-248">No</span></span></p></td>
<td><p><span data-ttu-id="24a3c-p125">Ao clicar neste item, o relatório mostra informações detalhadas sobre chamadas baseadas no tipo escolhido. Tipos de chamada incluem:</span><span class="sxs-lookup"><span data-stu-id="24a3c-p125">When you click this item, the report shows detailed information about calls based on that type. Call types include:</span></span></p>
<ul>
<li><p><span data-ttu-id="24a3c-251">Chamadas Ponto a Ponto de UC</span><span class="sxs-lookup"><span data-stu-id="24a3c-251">UC Peer-to-Peer Calls</span></span></p></li>
<li><p><span data-ttu-id="24a3c-252">Sessões de Conferência de UC</span><span class="sxs-lookup"><span data-stu-id="24a3c-252">UC Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="24a3c-253">Sessões de Conferência PSTN</span><span class="sxs-lookup"><span data-stu-id="24a3c-253">PSTN Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="24a3c-254">Chamadas PSTN: Desvio de Mídia</span><span class="sxs-lookup"><span data-stu-id="24a3c-254">PSTN Calls: Media Bypass</span></span></p></li>
<li><p><span data-ttu-id="24a3c-255">Chamadas PSTN (Não Ignorar): Trecho de UC</span><span class="sxs-lookup"><span data-stu-id="24a3c-255">PSTN Calls (Non-Bypass): UC Leg</span></span></p></li>
<li><p><span data-ttu-id="24a3c-256">Chamadas PSTN (Não Ignorar): Trecho de Gateway</span><span class="sxs-lookup"><span data-stu-id="24a3c-256">PSTN Calls (Non-Bypass): Gateway Leg</span></span></p></li>
<li><p><span data-ttu-id="24a3c-257">Outros Tipos de Chamada</span><span class="sxs-lookup"><span data-stu-id="24a3c-257">Other Call Types</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24a3c-258"><strong>Volume da chamada</strong></span><span class="sxs-lookup"><span data-stu-id="24a3c-258"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="24a3c-259">Não</span><span class="sxs-lookup"><span data-stu-id="24a3c-259">No</span></span></p></td>
<td><p><span data-ttu-id="24a3c-260">Número total de chamadas por tipo de chamada.</span><span class="sxs-lookup"><span data-stu-id="24a3c-260">Total number of calls per call type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24a3c-261"><strong>Percentual de chamadas ruins</strong></span><span class="sxs-lookup"><span data-stu-id="24a3c-261"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="24a3c-262">Não</span><span class="sxs-lookup"><span data-stu-id="24a3c-262">No</span></span></p></td>
<td><p><span data-ttu-id="24a3c-p126">Número total de chamadas classificadas como ruins. Uma chamada ruim é qualquer chamada em que no mínimo uma das métricas medidas excedeu o valor permitido (por exemplo, uma chamada com tremulação excessiva).</span><span class="sxs-lookup"><span data-stu-id="24a3c-p126">Total number of calls classified as poor. A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24a3c-265"><strong>Volume de chamadas (chamadas sem fio)</strong></span><span class="sxs-lookup"><span data-stu-id="24a3c-265"><strong>Call volume (wireless call)</strong></span></span></p></td>
<td><p><span data-ttu-id="24a3c-266">Não</span><span class="sxs-lookup"><span data-stu-id="24a3c-266">No</span></span></p></td>
<td><p><span data-ttu-id="24a3c-267">Número total de chamadas que usaram uma conexão sem fio.</span><span class="sxs-lookup"><span data-stu-id="24a3c-267">Total number of calls that used a wireless connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24a3c-268"><strong>Volume de chamadas (chamadas VPN)</strong></span><span class="sxs-lookup"><span data-stu-id="24a3c-268"><strong>Call volume (VPN call)</strong></span></span></p></td>
<td><p><span data-ttu-id="24a3c-269">Não</span><span class="sxs-lookup"><span data-stu-id="24a3c-269">No</span></span></p></td>
<td><p><span data-ttu-id="24a3c-270">Número total de chamadas que usaram uma conexão VPN.</span><span class="sxs-lookup"><span data-stu-id="24a3c-270">Total number of calls that used a VPN connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24a3c-271"><strong>Volume de chamadas (chamadas externas)</strong></span><span class="sxs-lookup"><span data-stu-id="24a3c-271"><strong>Call volume (external call)</strong></span></span></p></td>
<td><p><span data-ttu-id="24a3c-272">Não</span><span class="sxs-lookup"><span data-stu-id="24a3c-272">No</span></span></p></td>
<td><p><span data-ttu-id="24a3c-273">Número de chamadas que usaram uma conexão externa (ou seja, uma conexão fora da rede interna).</span><span class="sxs-lookup"><span data-stu-id="24a3c-273">Number of calls that used an external connection (that is, a connection outside the internal network).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24a3c-274"><strong>Taxa de bits média (Kbits/s)</strong></span><span class="sxs-lookup"><span data-stu-id="24a3c-274"><strong>Avg bit-rate (Kbits/s)</strong></span></span></p></td>
<td><p><span data-ttu-id="24a3c-275">Não</span><span class="sxs-lookup"><span data-stu-id="24a3c-275">No</span></span></p></td>
<td><p><span data-ttu-id="24a3c-276">Taxa de bits média (em quilobytes por segundo).</span><span class="sxs-lookup"><span data-stu-id="24a3c-276">Average video bit rate (in kilobits per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24a3c-277"><strong>% de taxa de bits baixa</strong></span><span class="sxs-lookup"><span data-stu-id="24a3c-277"><strong>Low bit-rate %</strong></span></span></p></td>
<td><p><span data-ttu-id="24a3c-278">Não</span><span class="sxs-lookup"><span data-stu-id="24a3c-278">No</span></span></p></td>
<td><p><span data-ttu-id="24a3c-279">Porcentagem da chamada onde a taxa de bits foi baixa.</span><span class="sxs-lookup"><span data-stu-id="24a3c-279">Percentage of the call where the bit rate was low.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24a3c-280"><strong>Perda de pacote de saída</strong></span><span class="sxs-lookup"><span data-stu-id="24a3c-280"><strong>Outbound packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="24a3c-281">Não</span><span class="sxs-lookup"><span data-stu-id="24a3c-281">No</span></span></p></td>
<td><p><span data-ttu-id="24a3c-p127">Perda de pacotes do Protocolo de transporte em tempo real (RTP) para pacotes enviados. (A perda de pacotes ocorre quando pacotes RTP, um protocolo usado para transmitir áudio e vídeo pela internet, falha ao tentar alcançar seu destino). Altas taxas de perda geralmente são causadas por congestionamento, insuficiência da largura de banda, congestionamento ou interferência na rede sem fio ou um servidor de mídia sobrecarregado. A perda de pacotes normalmente resulta em distorção ou perda de áudio.</span><span class="sxs-lookup"><span data-stu-id="24a3c-p127">Real-Time Transport Protocol (RTP) packet loss for outbound packets. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24a3c-285"><strong>% de quadros congelados</strong></span><span class="sxs-lookup"><span data-stu-id="24a3c-285"><strong>Frozen frame %</strong></span></span></p></td>
<td><p><span data-ttu-id="24a3c-286">Não</span><span class="sxs-lookup"><span data-stu-id="24a3c-286">No</span></span></p></td>
<td><p><span data-ttu-id="24a3c-p128">Porcentagem de quadros "congelados". Em um quadro congelado, o vídeo não avança enquanto a parte de áudio da chamada prossegue.</span><span class="sxs-lookup"><span data-stu-id="24a3c-p128">Percentage of “frozen” frames. In a frozen frame, the video stops advancing while the audio portion of the call continues.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24a3c-289"><strong>Taxa de quadros média de saída</strong></span><span class="sxs-lookup"><span data-stu-id="24a3c-289"><strong>Outbound avg frame rate</strong></span></span></p></td>
<td><p><span data-ttu-id="24a3c-290">Não</span><span class="sxs-lookup"><span data-stu-id="24a3c-290">No</span></span></p></td>
<td><p><span data-ttu-id="24a3c-291">Taxa de quadros média para transmissões de saída durante a chamada.</span><span class="sxs-lookup"><span data-stu-id="24a3c-291">Average frame rate for outbound transmissions during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24a3c-292"><strong>Taxa de quadros média de entrada</strong></span><span class="sxs-lookup"><span data-stu-id="24a3c-292"><strong>Inbound avg frame rate</strong></span></span></p></td>
<td><p><span data-ttu-id="24a3c-293">Não</span><span class="sxs-lookup"><span data-stu-id="24a3c-293">No</span></span></p></td>
<td><p><span data-ttu-id="24a3c-294">Taxa de quadros média para transmissões de entrada durante a chamada.</span><span class="sxs-lookup"><span data-stu-id="24a3c-294">Average frame rate for incoming transmissions during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24a3c-295"><strong>% de taxa de quadros baixa de entrada</strong></span><span class="sxs-lookup"><span data-stu-id="24a3c-295"><strong>Inbound low frame rate %</strong></span></span></p></td>
<td><p><span data-ttu-id="24a3c-296">Não</span><span class="sxs-lookup"><span data-stu-id="24a3c-296">No</span></span></p></td>
<td><p><span data-ttu-id="24a3c-297">Porcentagem da chamada onde a taxa de bits foi baixa para vídeo de entrada.</span><span class="sxs-lookup"><span data-stu-id="24a3c-297">Percentage of the call where the bit rate for incoming video was low.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24a3c-298"><strong>% de integridade do cliente</strong></span><span class="sxs-lookup"><span data-stu-id="24a3c-298"><strong>Client health %</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="24a3c-299">Indica o estado relativo do dispositivo do cliente durante a chamada.</span><span class="sxs-lookup"><span data-stu-id="24a3c-299">Indicates the relative health of the client device during the call.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="server-performance-report-metrics-application-sharing-call-summary"></a><span data-ttu-id="24a3c-300">Métricas do Relatório de Desempenho do Servidor: Resumo da chamada de compartilhamento de aplicativo</span><span class="sxs-lookup"><span data-stu-id="24a3c-300">Server Performance Report Metrics: Application Sharing Call Summary</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="24a3c-301">Nome</span><span class="sxs-lookup"><span data-stu-id="24a3c-301">Name</span></span></th>
<th><span data-ttu-id="24a3c-302">É possível classificar este item?</span><span class="sxs-lookup"><span data-stu-id="24a3c-302">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="24a3c-303">Descrição</span><span class="sxs-lookup"><span data-stu-id="24a3c-303">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="24a3c-304"><strong>Tipo de Chamada/Tipo de Ponto de Extremidade</strong></span><span class="sxs-lookup"><span data-stu-id="24a3c-304"><strong>Call type/Endpoint type</strong></span></span></p></td>
<td><p><span data-ttu-id="24a3c-305">Não</span><span class="sxs-lookup"><span data-stu-id="24a3c-305">No</span></span></p></td>
<td><p><span data-ttu-id="24a3c-p129">Ao clicar neste item, o relatório mostra informações detalhadas sobre chamadas baseadas no tipo escolhido. Tipos de chamada incluem:</span><span class="sxs-lookup"><span data-stu-id="24a3c-p129">When you click this item, the report shows detailed information about calls based on that type. Call types include:</span></span></p>
<ul>
<li><p><span data-ttu-id="24a3c-308">Chamadas Ponto a Ponto de UC</span><span class="sxs-lookup"><span data-stu-id="24a3c-308">UC Peer-to-Peer Calls</span></span></p></li>
<li><p><span data-ttu-id="24a3c-309">Sessões de Conferência de UC</span><span class="sxs-lookup"><span data-stu-id="24a3c-309">UC Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="24a3c-310">Sessões de Conferência PSTN</span><span class="sxs-lookup"><span data-stu-id="24a3c-310">PSTN Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="24a3c-311">Chamadas PSTN: Desvio de Mídia</span><span class="sxs-lookup"><span data-stu-id="24a3c-311">PSTN Calls: Media Bypass</span></span></p></li>
<li><p><span data-ttu-id="24a3c-312">Chamadas PSTN (Não Ignorar): Trecho de UC</span><span class="sxs-lookup"><span data-stu-id="24a3c-312">PSTN Calls (Non-Bypass): UC Leg</span></span></p></li>
<li><p><span data-ttu-id="24a3c-313">Chamadas PSTN (Não Ignorar): Trecho de Gateway</span><span class="sxs-lookup"><span data-stu-id="24a3c-313">PSTN Calls (Non-Bypass): Gateway Leg</span></span></p></li>
<li><p><span data-ttu-id="24a3c-314">Outros Tipos de Chamada</span><span class="sxs-lookup"><span data-stu-id="24a3c-314">Other Call Types</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24a3c-315"><strong>Volume da chamada</strong></span><span class="sxs-lookup"><span data-stu-id="24a3c-315"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="24a3c-316">Não</span><span class="sxs-lookup"><span data-stu-id="24a3c-316">No</span></span></p></td>
<td><p><span data-ttu-id="24a3c-317">Número total de chamadas por tipo de chamada.</span><span class="sxs-lookup"><span data-stu-id="24a3c-317">Total number of calls per call type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24a3c-318"><strong>Percentual de chamadas ruins</strong></span><span class="sxs-lookup"><span data-stu-id="24a3c-318"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="24a3c-319">Não</span><span class="sxs-lookup"><span data-stu-id="24a3c-319">No</span></span></p></td>
<td><p><span data-ttu-id="24a3c-p130">Número total de chamadas classificadas como ruins. Uma chamada ruim é qualquer chamada em que no mínimo uma das métricas medidas excedeu o valor permitido (por exemplo, uma chamada com tremulação excessiva).</span><span class="sxs-lookup"><span data-stu-id="24a3c-p130">Total number of calls classified as poor. A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24a3c-322"><strong>Volume de chamadas (chamadas sem fio)</strong></span><span class="sxs-lookup"><span data-stu-id="24a3c-322"><strong>Call volume (wireless call)</strong></span></span></p></td>
<td><p><span data-ttu-id="24a3c-323">Não</span><span class="sxs-lookup"><span data-stu-id="24a3c-323">No</span></span></p></td>
<td><p><span data-ttu-id="24a3c-324">Número total de chamadas que usaram uma conexão sem fio.</span><span class="sxs-lookup"><span data-stu-id="24a3c-324">Total number of calls that used a wireless connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24a3c-325"><strong>Volume de chamadas (chamadas VPN)</strong></span><span class="sxs-lookup"><span data-stu-id="24a3c-325"><strong>Call volume (VPN call)</strong></span></span></p></td>
<td><p><span data-ttu-id="24a3c-326">Não</span><span class="sxs-lookup"><span data-stu-id="24a3c-326">No</span></span></p></td>
<td><p><span data-ttu-id="24a3c-327">Número total de chamadas que usaram uma conexão VPN.</span><span class="sxs-lookup"><span data-stu-id="24a3c-327">Total number of calls that used a VPN connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24a3c-328"><strong>Volume de chamadas (chamadas externas)</strong></span><span class="sxs-lookup"><span data-stu-id="24a3c-328"><strong>Call volume (external call)</strong></span></span></p></td>
<td><p><span data-ttu-id="24a3c-329">Não</span><span class="sxs-lookup"><span data-stu-id="24a3c-329">No</span></span></p></td>
<td><p><span data-ttu-id="24a3c-330">Número de chamadas que usaram uma conexão externa (ou seja, uma conexão fora da rede interna).</span><span class="sxs-lookup"><span data-stu-id="24a3c-330">Number of calls that used an external connection (that is, a connection outside the internal network).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24a3c-331"><strong>Tremulação (ms)</strong></span><span class="sxs-lookup"><span data-stu-id="24a3c-331"><strong>Jitter (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="24a3c-332">Não</span><span class="sxs-lookup"><span data-stu-id="24a3c-332">No</span></span></p></td>
<td><p><span data-ttu-id="24a3c-333">Tremulação média detectada entre chegadas de pacote RTP.</span><span class="sxs-lookup"><span data-stu-id="24a3c-333">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="24a3c-334">(Tremulação é uma medida do &quot;tremula&quot; de uma chamada.) Os valores de variação alta geralmente são causados por congestionamento ou por um servidor de mídia sobrecarregado e resultam em um áudio distorcido ou perdido.</span><span class="sxs-lookup"><span data-stu-id="24a3c-334">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24a3c-335"><strong>Unidirecional relativo médio</strong></span><span class="sxs-lookup"><span data-stu-id="24a3c-335"><strong>Avg. relative one way</strong></span></span></p></td>
<td><p><span data-ttu-id="24a3c-336">Não</span><span class="sxs-lookup"><span data-stu-id="24a3c-336">No</span></span></p></td>
<td><p><span data-ttu-id="24a3c-p132">Atraso unidirecional relativo médio entre dois pontos de extremidade de mídia. Esta é uma medida de latência de salto único.</span><span class="sxs-lookup"><span data-stu-id="24a3c-p132">Average relative one-way delay between two media endpoints. This is a single-hop latency measure.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24a3c-339"><strong>Latência média de processamento lado a lado RDP</strong></span><span class="sxs-lookup"><span data-stu-id="24a3c-339"><strong>Avg. RDP tile processing latency</strong></span></span></p></td>
<td><p><span data-ttu-id="24a3c-340">Não</span><span class="sxs-lookup"><span data-stu-id="24a3c-340">No</span></span></p></td>
<td><p><span data-ttu-id="24a3c-p133">A latência média de processamento lado a lado RDP no Servidor de Conferência AS durante a sessão de visualização. Essa métrica não cobre a latência de rede. Uma média alta reflete um atraso maior na experiência de visualização. Um servidor de conferência sobrecarregado pode enfrentar atrasos médios maiores.</span><span class="sxs-lookup"><span data-stu-id="24a3c-p133">The average RDP tile processing latency in the AS Conferencing Server over the duration of the viewing session. This metric does not cover network latency. A high average reflects a longer delay in the viewing experience. An overloaded conferencing server may experience higher average delays.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24a3c-345"><strong>% total de lado a lado estragado</strong></span><span class="sxs-lookup"><span data-stu-id="24a3c-345"><strong>Total spoiled tile %</strong></span></span></p></td>
<td><p><span data-ttu-id="24a3c-346">Não</span><span class="sxs-lookup"><span data-stu-id="24a3c-346">No</span></span></p></td>
<td><p><span data-ttu-id="24a3c-347">A porcentagem total de lado a lado estragados.</span><span class="sxs-lookup"><span data-stu-id="24a3c-347">Total percentage of spoiled RDP tiles.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

