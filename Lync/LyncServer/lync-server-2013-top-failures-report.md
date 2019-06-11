---
title: 'Lync Server 2013: relatório de falhas principais'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Top Failures Report
ms:assetid: 438942e2-580a-4b67-9d42-f116111fb26a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558640(v=OCS.15)
ms:contentKeyID: 48184021
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 094f5034951e20d48b05c8772698ae2983492509
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844599"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="top-failures-report-in-lync-server-2013"></a><span data-ttu-id="68e0d-102">Relatório de falhas principais no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68e0d-102">Top Failures Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="68e0d-103">_**Tópico da última modificação:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="68e0d-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="68e0d-p101">O Relatório de Falhas Principais apresenta uma noção das falhas mais frequentemente relatadas e suas tendências ao longo do tempo. As falhas são baseadas em uma combinação das seguintes métricas:</span><span class="sxs-lookup"><span data-stu-id="68e0d-p101">The Top Failures Report provides a look at the most-commonly reported failures and their trends over time. Failures are based on a combination of the following two metrics:</span></span>

  - <span data-ttu-id="68e0d-p102">**ID de Diagnóstico**. Identificador único (na forma de um cabeçalho ms-diagnostics) que é anexado a uma mensagem SIP. As IDs de Diagnóstico fornecem informações úteis na solução de problemas relacionados a chamadas.</span><span class="sxs-lookup"><span data-stu-id="68e0d-p102">**Diagnostic ID**. Unique identifier (in the form of an ms-diagnostics header) that is attached to a SIP message. Diagnostic IDs provide information useful in troubleshooting call-related problems.</span></span>

  - <span data-ttu-id="68e0d-109">**Código de resposta**.</span><span class="sxs-lookup"><span data-stu-id="68e0d-109">**Response code**.</span></span> <span data-ttu-id="68e0d-110">Os códigos de resposta são utilizados nas sessões de comunicação SIP para responder solicitações SIP.</span><span class="sxs-lookup"><span data-stu-id="68e0d-110">Response codes are used in SIP communication sessions to respond to SIP requests.</span></span> <span data-ttu-id="68e0d-111">Por exemplo, suponha que Ken envie a solicitação INVITE a Pilar Ackerman (isto é, suponha que Ken Myer ligue para Pilar Ackerman).</span><span class="sxs-lookup"><span data-stu-id="68e0d-111">For example, suppose Ken sends the INVITE request to Pilar Ackerman (that is, suppose Ken Myer calls Pilar Ackerman).</span></span> <span data-ttu-id="68e0d-112">Se Pilar responder, o telefone enviará o código de resposta 200 (OK), permitindo que o telefone de Ken saiba que Pilar atendeu.</span><span class="sxs-lookup"><span data-stu-id="68e0d-112">If Pilar answers, her phone will send the response code 200 (OK), letting Ken's phone know that Pilar has answered.</span></span> <span data-ttu-id="68e0d-113">O relatório de falhas principais inclui apenas códigos de resposta que foram enviados em resposta a uma falha de chamada; O Lync Server não mantém o controle de todos os códigos de resposta emitidos durante o curso de uma chamada.</span><span class="sxs-lookup"><span data-stu-id="68e0d-113">The Top Failures Report only includes response codes that were sent in response to a call failure; Lync Server does not keep track of all the response codes issued during the course of a call.</span></span>

<span data-ttu-id="68e0d-114">A informação é relatada não apenas para o número total de sessões quando uma falha ocorre, mas também para o número total de usuários que foram impactados pela falha.</span><span class="sxs-lookup"><span data-stu-id="68e0d-114">Information is reported not only for the total number of sessions where a failure occurred but also for the total number of users who were impacted by the failure.</span></span>

<div>

## <a name="accessing-the-top-failures-report"></a><span data-ttu-id="68e0d-115">Acessando o Relatório de Falhas Principais</span><span class="sxs-lookup"><span data-stu-id="68e0d-115">Accessing the Top Failures Report</span></span>

<span data-ttu-id="68e0d-116">O Relatório de Falhas Principais é acessado a partir da home page Relatórios de Monitoramento.</span><span class="sxs-lookup"><span data-stu-id="68e0d-116">The Top Failures Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="68e0d-117">Clicar na métrica de sessões informadas levará você ao [relatório de distribuição de falha no Lync Server 2013](lync-server-2013-failure-distribution-report.md).</span><span class="sxs-lookup"><span data-stu-id="68e0d-117">Clicking the Reported sessions metric will take you to the [Failure Distribution Report in Lync Server 2013](lync-server-2013-failure-distribution-report.md).</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-top-failures-report"></a><span data-ttu-id="68e0d-118">Fazendo o melhor uso do Relatório de Falhas Principais</span><span class="sxs-lookup"><span data-stu-id="68e0d-118">Making the Best Use of the Top Failures Report</span></span>

<span data-ttu-id="68e0d-p105">O Relatório de Falhas Principais é incomum quanto a uma coisa: ele permite a filtragem de até 5 IDs de diagnóstico de uma vez. (Normalmente, você só pode filtrar um item, como o endereço SIP de usuário, por vez.) Para filtrar várias IDs de diagnóstico, basta inserir cada ID na caixa de ID de Diagnóstico, separando as IDs com vírgula. (Se você quiser, pode deixar um espaço em branco após cada vírgula.) Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="68e0d-p105">The Top Failures Report is unusual in one regard: it allows you to filter on as many as 5 diagnostic IDs at once. (Typically you can only filter on one item – such as one user SIP address – at a time.) To filter on multiple diagnostic IDs, simply enter each ID in the Diagnostic IDs box, separating the IDs by using commas. (If you want to, you can leave a blank space after each comma.) For example:</span></span>

<span data-ttu-id="68e0d-122">1011, 2412, 1033, 52116, 1008</span><span class="sxs-lookup"><span data-stu-id="68e0d-122">1011, 2412, 1033, 52116, 1008</span></span>

<span data-ttu-id="68e0d-123">Faça isso e apenas chamadas que falharam e foram reportadas pelo menos em uma dessas cinco IDs de diagnóstico serão exibidas.</span><span class="sxs-lookup"><span data-stu-id="68e0d-123">Do that, and only failed calls that reported at least one of those five diagnostic IDs will be displayed.</span></span>

<span data-ttu-id="68e0d-p106">Ao passar o mouse sobre um Código de Resposta, você verá uma dica que diz o que um Código de Resposta em questão significa. Por exemplo, se você passar o mouse sobre o Código de Resposta 486, verá esta mensagem:</span><span class="sxs-lookup"><span data-stu-id="68e0d-p106">If you hold your mouse over a Response code you'll see a tooltip that tells you what the Response code in question means. For example, if you hold the mouse over the Response code 486 you'll see this message:</span></span>

<span data-ttu-id="68e0d-126">Ocupado.</span><span class="sxs-lookup"><span data-stu-id="68e0d-126">Busy Here.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="68e0d-127">Filtros</span><span class="sxs-lookup"><span data-stu-id="68e0d-127">Filters</span></span>

<span data-ttu-id="68e0d-p107">Os filtros fornecem uma maneira de retornar um conjunto de dados mais direcionado ou exibir os dados retornados de diferentes maneiras. Por exemplo, o Relatório de Falhas Principais permite filtrar os dados retornados com base, por exemplo, no tipo de atividade (sessão ponto a ponto ou sessão de conferência), ou com base no código de resposta SIP que acompanhava a sessão com falha. Você também pode escolher como os dados devem ser agrupados. Nesse caso, os usos são agrupados por hora, dia, semana ou mês.</span><span class="sxs-lookup"><span data-stu-id="68e0d-p107">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Top Failures Report enables you to filter the returned data based on such things as the activity type (peer-to-peer session or conferencing session) or by the SIP response code that accompanied the failed session. You can also choose how data should be grouped. In this case, usages are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="68e0d-132">A tabela a seguir lista os filtros que você pode usar com o Relatório de Falhas Principais.</span><span class="sxs-lookup"><span data-stu-id="68e0d-132">The following table lists the filters that you can use with the Top Failures Report.</span></span>

### <a name="top-failures-report-filters"></a><span data-ttu-id="68e0d-133">Filtros de Relatório de Falhas Principais</span><span class="sxs-lookup"><span data-stu-id="68e0d-133">Top Failures Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="68e0d-134">Nome</span><span class="sxs-lookup"><span data-stu-id="68e0d-134">Name</span></span></th>
<th><span data-ttu-id="68e0d-135">Descrição</span><span class="sxs-lookup"><span data-stu-id="68e0d-135">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="68e0d-136"><strong>De</strong></span><span class="sxs-lookup"><span data-stu-id="68e0d-136"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="68e0d-p108">Data/hora de início para o intervalo de tempo. Para ver os dados por horas, insira a data e hora de início conforme segue:</span><span class="sxs-lookup"><span data-stu-id="68e0d-p108">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="68e0d-139">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="68e0d-139">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="68e0d-p109">Se você não inserir a hora de início, o relatório começará automaticamente à meia-noite do dia especificado. Para ver os dados por dia, insira somente a data:</span><span class="sxs-lookup"><span data-stu-id="68e0d-p109">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="68e0d-142">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="68e0d-142">7/7/2012</span></span></p>
<p><span data-ttu-id="68e0d-143">Para exibir por semana ou mês, insira uma data dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):</span><span class="sxs-lookup"><span data-stu-id="68e0d-143">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="68e0d-144">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="68e0d-144">7/3/2012</span></span></p>
<p><span data-ttu-id="68e0d-145">As semanas sempre vão de domingo a sábado.</span><span class="sxs-lookup"><span data-stu-id="68e0d-145">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68e0d-146"><strong>Até</strong></span><span class="sxs-lookup"><span data-stu-id="68e0d-146"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="68e0d-p110">Data/hora final de intervalo de tempo. Para ver os dados por horas, insira a data e hora final conforme segue:</span><span class="sxs-lookup"><span data-stu-id="68e0d-p110">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="68e0d-149">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="68e0d-149">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="68e0d-p111">Se você não inserir a hora final, o relatório terminará automaticamente à meia-noite do dia especificado. Para ver os dados por dia, insira somente a data:</span><span class="sxs-lookup"><span data-stu-id="68e0d-p111">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="68e0d-152">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="68e0d-152">7/7/2012</span></span></p>
<p><span data-ttu-id="68e0d-153">Para exibir por semana ou mês, insira uma data dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):</span><span class="sxs-lookup"><span data-stu-id="68e0d-153">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="68e0d-154">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="68e0d-154">7/3/2012</span></span></p>
<p><span data-ttu-id="68e0d-155">As semanas sempre vão de domingo a sábado.</span><span class="sxs-lookup"><span data-stu-id="68e0d-155">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68e0d-156"><strong>Tipo de atividade</strong></span><span class="sxs-lookup"><span data-stu-id="68e0d-156"><strong>Activity type</strong></span></span></p></td>
<td><p><span data-ttu-id="68e0d-p112">Tipo de atividade. Selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="68e0d-p112">Type of activity. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="68e0d-159">[Todos]</span><span class="sxs-lookup"><span data-stu-id="68e0d-159">[All]</span></span></p></li>
<li><p><span data-ttu-id="68e0d-160">Ponto a ponto</span><span class="sxs-lookup"><span data-stu-id="68e0d-160">Peer-to-peer</span></span></p></li>
<li><p><span data-ttu-id="68e0d-161">Conferência</span><span class="sxs-lookup"><span data-stu-id="68e0d-161">Conference</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68e0d-162"><strong>Modalidade</strong></span><span class="sxs-lookup"><span data-stu-id="68e0d-162"><strong>Modality</strong></span></span></p></td>
<td><p><span data-ttu-id="68e0d-163">Neste momento, a única opção disponível é <strong>[Todos]</strong>.</span><span class="sxs-lookup"><span data-stu-id="68e0d-163">At this time the only option available is <strong>[All]</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68e0d-164"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="68e0d-164"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="68e0d-p113">O FQDN (nome de domínio totalmente qualificado) do pool Registrador Avançado ou Servidor de Borda. Você pode selecionar um pool individual ou clicar em <strong>[Todos]</strong> para ver os dados de todos os pools. Essa lista suspensa é preenchida automaticamente com base nos registros no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="68e0d-p113">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68e0d-168"><strong>Categoria</strong></span><span class="sxs-lookup"><span data-stu-id="68e0d-168"><strong>Category</strong></span></span></p></td>
<td><p><span data-ttu-id="68e0d-p114">Tipo de falha ocorrido. Selecione um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="68e0d-p114">Type of failure experienced. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="68e0d-171">Falha inesperada e esperada</span><span class="sxs-lookup"><span data-stu-id="68e0d-171">Both expected and unexpected failure</span></span></p></li>
<li><p><span data-ttu-id="68e0d-172">Falha inesperada</span><span class="sxs-lookup"><span data-stu-id="68e0d-172">Unexpected failure</span></span></p></li>
</ul>
<p><span data-ttu-id="68e0d-173">Uma &quot;falha&quot; esperada é uma falha que espera acontecer.</span><span class="sxs-lookup"><span data-stu-id="68e0d-173">An &quot;expected failure&quot; is a failure that is expected to happen.</span></span> <span data-ttu-id="68e0d-174">Por exemplo, se um usuário tiver definido seu status como Não perturbe, é esperado que qualquer chamada para esse usuário falhe.</span><span class="sxs-lookup"><span data-stu-id="68e0d-174">For example, if a user has set his or her status to Do Not Disturb you would expect any call to that user to fail.</span></span> <span data-ttu-id="68e0d-175">Uma &quot;falha&quot; inesperada é uma falha que ocorre em que parece ser um sistema de outra forma saudável.</span><span class="sxs-lookup"><span data-stu-id="68e0d-175">An &quot;unexpected failure&quot; is a failure that occurs in what would appear to be an otherwise healthy system.</span></span> <span data-ttu-id="68e0d-176">Por exemplo, uma chamada não deve ser encerrada se o chamador for colocado em espera.</span><span class="sxs-lookup"><span data-stu-id="68e0d-176">For example, a call should not be terminated if the caller is placed on hold.</span></span> <span data-ttu-id="68e0d-177">Se isso ocorrer, a situação será sinalizada como falha inesperada.</span><span class="sxs-lookup"><span data-stu-id="68e0d-177">If that occurs, that would be flagged as an unexpected failure.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68e0d-178"><strong>Código de resposta</strong></span><span class="sxs-lookup"><span data-stu-id="68e0d-178"><strong>Response code</strong></span></span></p></td>
<td><p><span data-ttu-id="68e0d-p116">O código de resposta enviado quando a conferência falhou. Digite o código de resposta inteiro. Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="68e0d-p116">SIP response code sent when the conference failed. Enter the entire response code For example:</span></span></p>
<p><span data-ttu-id="68e0d-181">400</span><span class="sxs-lookup"><span data-stu-id="68e0d-181">400</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68e0d-182"><strong>ID do Diagnóstico</strong></span><span class="sxs-lookup"><span data-stu-id="68e0d-182"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="68e0d-p117">Identificador exclusivo (na forma de um cabeçalho ms-diagnostics) anexado a uma mensagem SIP que fornece informações úteis para resolução de erros. Os cabeçalhos de diagnóstico são opcionais (é possível ter sessões SIP que não os incluem), e as IDs de diagnóstico são relatadas somente em sessões com algum tipo de problema.</span><span class="sxs-lookup"><span data-stu-id="68e0d-p117">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors. Diagnostics headers are optional (it is possible to have SIP sessions that do not include these headers), and diagnostic IDs are reported only for sessions that experienced problems of some kind.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="68e0d-185">Métricas</span><span class="sxs-lookup"><span data-stu-id="68e0d-185">Metrics</span></span>

<span data-ttu-id="68e0d-186">A tabela a seguir lista as informações fornecidas no Relatório de Falhas Principais.</span><span class="sxs-lookup"><span data-stu-id="68e0d-186">The following table lists the information provided in the Top Failures Report.</span></span>

### <a name="top-failures-report-metrics"></a><span data-ttu-id="68e0d-187">Métricas do Relatório de Falhas Principais</span><span class="sxs-lookup"><span data-stu-id="68e0d-187">Top Failures Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="68e0d-188">Nome</span><span class="sxs-lookup"><span data-stu-id="68e0d-188">Name</span></span></th>
<th><span data-ttu-id="68e0d-189">Você pode classificar este item?</span><span class="sxs-lookup"><span data-stu-id="68e0d-189">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="68e0d-190">Descrição</span><span class="sxs-lookup"><span data-stu-id="68e0d-190">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="68e0d-191"><strong>Classificação</strong></span><span class="sxs-lookup"><span data-stu-id="68e0d-191"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="68e0d-192">Sim</span><span class="sxs-lookup"><span data-stu-id="68e0d-192">Yes</span></span></p></td>
<td><p><span data-ttu-id="68e0d-193">Classificação relativa com base no número de sessões relatadas.</span><span class="sxs-lookup"><span data-stu-id="68e0d-193">Relative rank based on the number of reported sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68e0d-194"><strong>Sessões relatadas</strong></span><span class="sxs-lookup"><span data-stu-id="68e0d-194"><strong>Reported sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="68e0d-195">Sim</span><span class="sxs-lookup"><span data-stu-id="68e0d-195">Yes</span></span></p></td>
<td><p><span data-ttu-id="68e0d-196">Número total de sessões com falha com base na ID de diagnóstico e no código de resposta SIP.</span><span class="sxs-lookup"><span data-stu-id="68e0d-196">Total number of failed sessions based on diagnostic ID and SIP response code.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68e0d-197"><strong>Usuários afetados</strong></span><span class="sxs-lookup"><span data-stu-id="68e0d-197"><strong>Users impacted</strong></span></span></p></td>
<td><p><span data-ttu-id="68e0d-198">Sim</span><span class="sxs-lookup"><span data-stu-id="68e0d-198">Yes</span></span></p></td>
<td><p><span data-ttu-id="68e0d-199">Número total de usuários afetados pela sessão com falha.</span><span class="sxs-lookup"><span data-stu-id="68e0d-199">Total number of users affected by the failed session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68e0d-200"><strong>Informações da falha</strong></span><span class="sxs-lookup"><span data-stu-id="68e0d-200"><strong>Failure information</strong></span></span></p></td>
<td><p><span data-ttu-id="68e0d-201">Não</span><span class="sxs-lookup"><span data-stu-id="68e0d-201">No</span></span></p></td>
<td><p><span data-ttu-id="68e0d-202">Informações detalhadas sobre a falha, incluindo a ID de diagnóstico, o código de resposta SIP e a descrição do motivo da falha na sessão.</span><span class="sxs-lookup"><span data-stu-id="68e0d-202">Detailed information about the failure, including diagnostic ID, SIP response code, and description of why the session failed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68e0d-203"><strong>Tendência no passado</strong></span><span class="sxs-lookup"><span data-stu-id="68e0d-203"><strong>Trend in the past</strong></span></span></p></td>
<td><p><span data-ttu-id="68e0d-204">Não</span><span class="sxs-lookup"><span data-stu-id="68e0d-204">No</span></span></p></td>
<td><p><span data-ttu-id="68e0d-205">Representa graficamente as sessões com falha ao longo do tempo.</span><span class="sxs-lookup"><span data-stu-id="68e0d-205">Graphs failed sessions over time.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

