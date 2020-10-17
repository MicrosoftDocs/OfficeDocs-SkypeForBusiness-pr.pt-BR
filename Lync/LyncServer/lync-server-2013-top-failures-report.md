---
title: 'Lync Server 2013: relatório de falhas principais'
description: 'Lync Server 2013: relatório de falhas principais.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Top Failures Report
ms:assetid: 438942e2-580a-4b67-9d42-f116111fb26a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558640(v=OCS.15)
ms:contentKeyID: 48184021
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 768c9a99916dece9eb76877b0cd65b057697ff95
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561267"
---
# <a name="top-failures-report-in-lync-server-2013"></a><span data-ttu-id="fd3bd-103">Relatório de falhas principais no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fd3bd-103">Top Failures Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fd3bd-104">_**Última modificação do tópico:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="fd3bd-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="fd3bd-p101">O Relatório de Falhas Principais apresenta uma noção das falhas mais frequentemente relatadas e suas tendências ao longo do tempo. As falhas são baseadas em uma combinação das duas seguintes métricas:</span><span class="sxs-lookup"><span data-stu-id="fd3bd-p101">The Top Failures Report provides a look at the most-commonly reported failures and their trends over time. Failures are based on a combination of the following two metrics:</span></span>

  - <span data-ttu-id="fd3bd-p102">**ID de Diagnóstico**. Identificador único (na forma de um cabeçalho ms-diagnostics) que é anexado a uma mensagem SIP. As IDs de Diagnóstico fornecem informações úteis na solução de problemas relacionados a chamadas.</span><span class="sxs-lookup"><span data-stu-id="fd3bd-p102">**Diagnostic ID**. Unique identifier (in the form of an ms-diagnostics header) that is attached to a SIP message. Diagnostic IDs provide information useful in troubleshooting call-related problems.</span></span>

  - <span data-ttu-id="fd3bd-110">**Código de resposta**.</span><span class="sxs-lookup"><span data-stu-id="fd3bd-110">**Response code**.</span></span> <span data-ttu-id="fd3bd-111">Os códigos de resposta são utilizados nas sessões de comunicação SIP para responder solicitações SIP.</span><span class="sxs-lookup"><span data-stu-id="fd3bd-111">Response codes are used in SIP communication sessions to respond to SIP requests.</span></span> <span data-ttu-id="fd3bd-112">Por exemplo, suponha que Ken envie a solicitação INVITE a Pilar Ackerman (isto é, suponha que Ken Myer ligue para Pilar Ackerman).</span><span class="sxs-lookup"><span data-stu-id="fd3bd-112">For example, suppose Ken sends the INVITE request to Pilar Ackerman (that is, suppose Ken Myer calls Pilar Ackerman).</span></span> <span data-ttu-id="fd3bd-113">Se Pilar responder, o telefone enviará o código de resposta 200 (OK), permitindo que o telefone de Ken saiba que Pilar atendeu.</span><span class="sxs-lookup"><span data-stu-id="fd3bd-113">If Pilar answers, her phone will send the response code 200 (OK), letting Ken's phone know that Pilar has answered.</span></span> <span data-ttu-id="fd3bd-114">O relatório de falhas principais inclui apenas os códigos de resposta que foram enviados em resposta a uma falha de chamada; O Lync Server não mantém o controle de todos os códigos de resposta emitidos durante o curso de uma chamada.</span><span class="sxs-lookup"><span data-stu-id="fd3bd-114">The Top Failures Report only includes response codes that were sent in response to a call failure; Lync Server does not keep track of all the response codes issued during the course of a call.</span></span>

<span data-ttu-id="fd3bd-115">A informação é relatada não apenas para o número total de sessões quando uma falha ocorre, mas também para o número total de usuários que foram impactados pela falha.</span><span class="sxs-lookup"><span data-stu-id="fd3bd-115">Information is reported not only for the total number of sessions where a failure occurred but also for the total number of users who were impacted by the failure.</span></span>

<div>

## <a name="accessing-the-top-failures-report"></a><span data-ttu-id="fd3bd-116">Acessando o Relatório de Falhas Principais</span><span class="sxs-lookup"><span data-stu-id="fd3bd-116">Accessing the Top Failures Report</span></span>

<span data-ttu-id="fd3bd-117">O Relatório de Falhas Principais é acessado a partir da página Relatórios de Monitoramento.</span><span class="sxs-lookup"><span data-stu-id="fd3bd-117">The Top Failures Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="fd3bd-118">Clicar na métrica sessões relatadas levará você para o [relatório de distribuição de falhas no Lync Server 2013](lync-server-2013-failure-distribution-report.md).</span><span class="sxs-lookup"><span data-stu-id="fd3bd-118">Clicking the Reported sessions metric will take you to the [Failure Distribution Report in Lync Server 2013](lync-server-2013-failure-distribution-report.md).</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-top-failures-report"></a><span data-ttu-id="fd3bd-119">Fazendo o melhor uso do Relatório de Falhas Principais</span><span class="sxs-lookup"><span data-stu-id="fd3bd-119">Making the Best Use of the Top Failures Report</span></span>

<span data-ttu-id="fd3bd-p105">O Relatório de Falhas Principais é incomum quanto a uma coisa: ele permite a filtragem de até 5 IDs de diagnóstico de uma vez. (Normalmente, você só pode filtrar um item, como o endereço SIP de usuário, por vez.) Para filtrar várias IDs de diagnóstico, apenas insira cada ID na caixa de ID de Diagnóstico, separando as IDs com vírgula. (Se você quiser, pode deixar um espaço em branco após cada vírgula.) Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="fd3bd-p105">The Top Failures Report is unusual in one regard: it allows you to filter on as many as 5 diagnostic IDs at once. (Typically you can only filter on one item – such as one user SIP address – at a time.) To filter on multiple diagnostic IDs, simply enter each ID in the Diagnostic IDs box, separating the IDs by using commas. (If you want to, you can leave a blank space after each comma.) For example:</span></span>

<span data-ttu-id="fd3bd-123">1011, 2412, 1033, 52116, 1008</span><span class="sxs-lookup"><span data-stu-id="fd3bd-123">1011, 2412, 1033, 52116, 1008</span></span>

<span data-ttu-id="fd3bd-124">Faça isso e apenas chamadas que falharam e foram reportadas pelo menos em uma dessas cinco IDs de diagnóstico serão exibidas.</span><span class="sxs-lookup"><span data-stu-id="fd3bd-124">Do that, and only failed calls that reported at least one of those five diagnostic IDs will be displayed.</span></span>

<span data-ttu-id="fd3bd-p106">Se você manter o mouse sob Código de Resposta, você verá uma dica que diz o que um Código de Resposta em questão significa. Por exemplo, se você manter o mouse sobre o Código de Resposta 486, você verá esta mensagem:</span><span class="sxs-lookup"><span data-stu-id="fd3bd-p106">If you hold your mouse over a Response code you'll see a tooltip that tells you what the Response code in question means. For example, if you hold the mouse over the Response code 486 you'll see this message:</span></span>

<span data-ttu-id="fd3bd-127">Ocupado.</span><span class="sxs-lookup"><span data-stu-id="fd3bd-127">Busy Here.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="fd3bd-128">Filtros</span><span class="sxs-lookup"><span data-stu-id="fd3bd-128">Filters</span></span>

<span data-ttu-id="fd3bd-p107">Os filtros fornecem uma maneira de retornar um conjunto de dados mais direcionado ou para exibir os dados retornados de diferentes maneiras. Por exemplo, o Relatório de Falhas Principais permite filtrar os dados retornados com base, por exemplo, no tipo de atividade (sessão ponto a ponto ou sessão de conferência), ou no código de resposta SIP que acompanhava a sessão com falha. Você também pode escolher como os dados devem ser agrupados. Nesse caso, os usos são agrupados por hora, dia, semana ou mês.</span><span class="sxs-lookup"><span data-stu-id="fd3bd-p107">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Top Failures Report enables you to filter the returned data based on such things as the activity type (peer-to-peer session or conferencing session) or by the SIP response code that accompanied the failed session. You can also choose how data should be grouped. In this case, usages are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="fd3bd-133">A tabela a seguir lista os filtros que você pode usar com o Relatório de Falhas Principais.</span><span class="sxs-lookup"><span data-stu-id="fd3bd-133">The following table lists the filters that you can use with the Top Failures Report.</span></span>

### <a name="top-failures-report-filters"></a><span data-ttu-id="fd3bd-134">Filtros de Relatório de Falhas Principais</span><span class="sxs-lookup"><span data-stu-id="fd3bd-134">Top Failures Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fd3bd-135">Nome</span><span class="sxs-lookup"><span data-stu-id="fd3bd-135">Name</span></span></th>
<th><span data-ttu-id="fd3bd-136">Descrição</span><span class="sxs-lookup"><span data-stu-id="fd3bd-136">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fd3bd-137"><strong>De</strong></span><span class="sxs-lookup"><span data-stu-id="fd3bd-137"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="fd3bd-p108">Data/hora inicial para o intervalo de tempo. Para exibir os dados por hora, insira a data e hora inicial como a seguir:</span><span class="sxs-lookup"><span data-stu-id="fd3bd-p108">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="fd3bd-140">7/7/2012 13:00 horas</span><span class="sxs-lookup"><span data-stu-id="fd3bd-140">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="fd3bd-p109">Se você não inserir uma hora inicial, o relatório começa automaticamente as 12:00 AM no dia especificado. Para exibir os dados por dia, insira apenas a data:</span><span class="sxs-lookup"><span data-stu-id="fd3bd-p109">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="fd3bd-143">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="fd3bd-143">7/7/2012</span></span></p>
<p><span data-ttu-id="fd3bd-144">Para exibir por semana ou mês, insira uma data que está dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):</span><span class="sxs-lookup"><span data-stu-id="fd3bd-144">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="fd3bd-145">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="fd3bd-145">7/3/2012</span></span></p>
<p><span data-ttu-id="fd3bd-146">As semanas são sempre de domingo a sábado.</span><span class="sxs-lookup"><span data-stu-id="fd3bd-146">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd3bd-147"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="fd3bd-147"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="fd3bd-p110">Data/hora final para o intervalo de tempo. Para exibir os dados por hora, insira a data e hora final como a seguir:</span><span class="sxs-lookup"><span data-stu-id="fd3bd-p110">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="fd3bd-150">7/7/2012 13:00 horas</span><span class="sxs-lookup"><span data-stu-id="fd3bd-150">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="fd3bd-p111">Se você não inserir uma hora final, o relatório termina automaticamente as 12:00 AM no dia especificado. Para exibir os dados por dia, insira apenas a data:</span><span class="sxs-lookup"><span data-stu-id="fd3bd-p111">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="fd3bd-153">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="fd3bd-153">7/7/2012</span></span></p>
<p><span data-ttu-id="fd3bd-154">Para exibir por semana ou mês, insira uma data que está dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):</span><span class="sxs-lookup"><span data-stu-id="fd3bd-154">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="fd3bd-155">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="fd3bd-155">7/3/2012</span></span></p>
<p><span data-ttu-id="fd3bd-156">As semanas são contadas de domingo até sábado.</span><span class="sxs-lookup"><span data-stu-id="fd3bd-156">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd3bd-157"><strong>Tipo de atividade</strong></span><span class="sxs-lookup"><span data-stu-id="fd3bd-157"><strong>Activity type</strong></span></span></p></td>
<td><p><span data-ttu-id="fd3bd-p112">Tipo de atividade. Selecione um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="fd3bd-p112">Type of activity. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="fd3bd-160">Todos os</span><span class="sxs-lookup"><span data-stu-id="fd3bd-160">[All]</span></span></p></li>
<li><p><span data-ttu-id="fd3bd-161">Ponto a ponto</span><span class="sxs-lookup"><span data-stu-id="fd3bd-161">Peer-to-peer</span></span></p></li>
<li><p><span data-ttu-id="fd3bd-162">Conferência</span><span class="sxs-lookup"><span data-stu-id="fd3bd-162">Conference</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd3bd-163"><strong>Modalidade</strong></span><span class="sxs-lookup"><span data-stu-id="fd3bd-163"><strong>Modality</strong></span></span></p></td>
<td><p><span data-ttu-id="fd3bd-164">Neste momento, a única opção disponível é <strong>[Todos]</strong>.</span><span class="sxs-lookup"><span data-stu-id="fd3bd-164">At this time the only option available is <strong>[All]</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd3bd-165"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="fd3bd-165"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="fd3bd-p113">FQDN (nome de domínio totalmente qualificado do pool de Registrador ou Servidor de Borda. Você pode selecionar um pool individual ou clicar em <strong>[Todos]</strong> para exibir dados de todos os pools. Esta lista suspensa é preenchida automaticamente com base nos registros contidos no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="fd3bd-p113">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd3bd-169"><strong>Categoria</strong></span><span class="sxs-lookup"><span data-stu-id="fd3bd-169"><strong>Category</strong></span></span></p></td>
<td><p><span data-ttu-id="fd3bd-p114">Tipo de falha ocorrido. Selecione um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="fd3bd-p114">Type of failure experienced. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="fd3bd-172">Falha inesperada e esperada</span><span class="sxs-lookup"><span data-stu-id="fd3bd-172">Both expected and unexpected failure</span></span></p></li>
<li><p><span data-ttu-id="fd3bd-173">Falha inesperada</span><span class="sxs-lookup"><span data-stu-id="fd3bd-173">Unexpected failure</span></span></p></li>
</ul>
<p><span data-ttu-id="fd3bd-174">Uma &quot; falha esperada &quot; é uma falha que deve ocorrer.</span><span class="sxs-lookup"><span data-stu-id="fd3bd-174">An &quot;expected failure&quot; is a failure that is expected to happen.</span></span> <span data-ttu-id="fd3bd-175">Por exemplo, se um usuário configurou seu status para Não Perturbe, é previsto que qualquer chamada para ele irá falhar.</span><span class="sxs-lookup"><span data-stu-id="fd3bd-175">For example, if a user has set his or her status to Do Not Disturb you would expect any call to that user to fail.</span></span> <span data-ttu-id="fd3bd-176">Uma &quot; falha inesperada &quot; é uma falha que ocorre no que parece ser um sistema saudável de outra forma.</span><span class="sxs-lookup"><span data-stu-id="fd3bd-176">An &quot;unexpected failure&quot; is a failure that occurs in what would appear to be an otherwise healthy system.</span></span> <span data-ttu-id="fd3bd-177">Por exemplo, uma chamada não deveria ser terminada se o chamador for colocado em espera.</span><span class="sxs-lookup"><span data-stu-id="fd3bd-177">For example, a call should not be terminated if the caller is placed on hold.</span></span> <span data-ttu-id="fd3bd-178">Se isso ocorrer, será sinalizado como uma falha inesperada.</span><span class="sxs-lookup"><span data-stu-id="fd3bd-178">If that occurs, that would be flagged as an unexpected failure.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd3bd-179"><strong>Código de resposta</strong></span><span class="sxs-lookup"><span data-stu-id="fd3bd-179"><strong>Response code</strong></span></span></p></td>
<td><p><span data-ttu-id="fd3bd-p116">O código de resposta enviado quando a conferência falhou. Digite o código de resposta inteiro. Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="fd3bd-p116">SIP response code sent when the conference failed. Enter the entire response code For example:</span></span></p>
<p><span data-ttu-id="fd3bd-182">400</span><span class="sxs-lookup"><span data-stu-id="fd3bd-182">400</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd3bd-183"><strong>ID do Diagnóstico</strong></span><span class="sxs-lookup"><span data-stu-id="fd3bd-183"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="fd3bd-p117">Identificador exclusivo (na forma de um cabeçalho ms-diagnostics) anexado a uma mensagem SIP que geralmente fornece informações úteis para solucionar problemas de erros. Cabeçalhos de diagnóstico são opcionais (é possível ter sessões SIP que não incluem esses cabeçalhos) e IDs de diagnóstico serão relatadas somente para as sessões que apresentaram problemas de algum tipo.</span><span class="sxs-lookup"><span data-stu-id="fd3bd-p117">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors. Diagnostics headers are optional (it is possible to have SIP sessions that do not include these headers), and diagnostic IDs are reported only for sessions that experienced problems of some kind.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="fd3bd-186">Métrica</span><span class="sxs-lookup"><span data-stu-id="fd3bd-186">Metrics</span></span>

<span data-ttu-id="fd3bd-187">A tabela a seguir lista as informações fornecidas no Relatório de Falhas Principais.</span><span class="sxs-lookup"><span data-stu-id="fd3bd-187">The following table lists the information provided in the Top Failures Report.</span></span>

### <a name="top-failures-report-metrics"></a><span data-ttu-id="fd3bd-188">Medição do Relatório de Falhas Principais</span><span class="sxs-lookup"><span data-stu-id="fd3bd-188">Top Failures Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fd3bd-189">Nome</span><span class="sxs-lookup"><span data-stu-id="fd3bd-189">Name</span></span></th>
<th><span data-ttu-id="fd3bd-190">É possível classificar este item?</span><span class="sxs-lookup"><span data-stu-id="fd3bd-190">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="fd3bd-191">Descrição</span><span class="sxs-lookup"><span data-stu-id="fd3bd-191">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fd3bd-192"><strong>Rank</strong></span><span class="sxs-lookup"><span data-stu-id="fd3bd-192"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="fd3bd-193">Sim</span><span class="sxs-lookup"><span data-stu-id="fd3bd-193">Yes</span></span></p></td>
<td><p><span data-ttu-id="fd3bd-194">Classificação relativa com base no número de sessões relatadas.</span><span class="sxs-lookup"><span data-stu-id="fd3bd-194">Relative rank based on the number of reported sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd3bd-195"><strong>Sessões relatadas</strong></span><span class="sxs-lookup"><span data-stu-id="fd3bd-195"><strong>Reported sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="fd3bd-196">Sim</span><span class="sxs-lookup"><span data-stu-id="fd3bd-196">Yes</span></span></p></td>
<td><p><span data-ttu-id="fd3bd-197">Número total de sessões com falha baseadas na ID de diagnóstico e no código de resposta SIP.</span><span class="sxs-lookup"><span data-stu-id="fd3bd-197">Total number of failed sessions based on diagnostic ID and SIP response code.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd3bd-198"><strong>Usuários afetados</strong></span><span class="sxs-lookup"><span data-stu-id="fd3bd-198"><strong>Users impacted</strong></span></span></p></td>
<td><p><span data-ttu-id="fd3bd-199">Sim</span><span class="sxs-lookup"><span data-stu-id="fd3bd-199">Yes</span></span></p></td>
<td><p><span data-ttu-id="fd3bd-200">Número total de usuários afetados pela sessão com falha.</span><span class="sxs-lookup"><span data-stu-id="fd3bd-200">Total number of users affected by the failed session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd3bd-201"><strong>Informações de falha</strong></span><span class="sxs-lookup"><span data-stu-id="fd3bd-201"><strong>Failure information</strong></span></span></p></td>
<td><p><span data-ttu-id="fd3bd-202">Não</span><span class="sxs-lookup"><span data-stu-id="fd3bd-202">No</span></span></p></td>
<td><p><span data-ttu-id="fd3bd-203">Informações detalhadas sobre a falha, incluindo a ID de diagnóstico, o código de resposta SIP e a descrição do motivo da sessão com falha.</span><span class="sxs-lookup"><span data-stu-id="fd3bd-203">Detailed information about the failure, including diagnostic ID, SIP response code, and description of why the session failed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd3bd-204"><strong>Tendência no passado</strong></span><span class="sxs-lookup"><span data-stu-id="fd3bd-204"><strong>Trend in the past</strong></span></span></p></td>
<td><p><span data-ttu-id="fd3bd-205">Não</span><span class="sxs-lookup"><span data-stu-id="fd3bd-205">No</span></span></p></td>
<td><p><span data-ttu-id="fd3bd-206">Representa graficamente as sessões com falha ao longo do tempo.</span><span class="sxs-lookup"><span data-stu-id="fd3bd-206">Graphs failed sessions over time.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

