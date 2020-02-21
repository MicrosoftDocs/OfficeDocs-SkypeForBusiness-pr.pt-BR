---
title: 'Lync Server 2013: relatório de distribuição de falhas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failure Distribution Report
ms:assetid: 365c7beb-24d4-40f5-92e7-4978b9688916
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558635(v=OCS.15)
ms:contentKeyID: 48183849
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c1531b7b103e3df6f2d165a4fd6fcd3abf100132
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42179618"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="failure-distribution-report-in-lync-server-2013"></a><span data-ttu-id="c472f-102">Relatório de distribuição de falhas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c472f-102">Failure Distribution Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c472f-103">_**Última modificação do tópico:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="c472f-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="c472f-104">O Relatório de Distribuição de Falhas classifica sessões com falha nas seguintes categorias:</span><span class="sxs-lookup"><span data-stu-id="c472f-104">The Failure Distribution Report ranks failed sessions in the following categories:</span></span>

  - <span data-ttu-id="c472f-105">Principais motivos diagnósticos</span><span class="sxs-lookup"><span data-stu-id="c472f-105">Top diagnostic reasons</span></span>

  - <span data-ttu-id="c472f-106">Principais modalidades</span><span class="sxs-lookup"><span data-stu-id="c472f-106">Top modalities</span></span>

  - <span data-ttu-id="c472f-107">Principais pools</span><span class="sxs-lookup"><span data-stu-id="c472f-107">Top pools</span></span>

  - <span data-ttu-id="c472f-108">Principais fontes</span><span class="sxs-lookup"><span data-stu-id="c472f-108">Top sources</span></span>

  - <span data-ttu-id="c472f-109">Principais componentes</span><span class="sxs-lookup"><span data-stu-id="c472f-109">Top components</span></span>

  - <span data-ttu-id="c472f-110">Principais usuários de origem</span><span class="sxs-lookup"><span data-stu-id="c472f-110">Top from users</span></span>

  - <span data-ttu-id="c472f-111">Principais usuários de destino</span><span class="sxs-lookup"><span data-stu-id="c472f-111">Top to users</span></span>

  - <span data-ttu-id="c472f-112">Principal usuário de origem</span><span class="sxs-lookup"><span data-stu-id="c472f-112">Top from user agents</span></span>

<span data-ttu-id="c472f-p101">É possível usar essas categorias para determinar exatamente onde está ocorrendo um problema e, em alguns casos, porque o problema está ocorrendo. Por exemplo, suponha que você tenha registrado 242 sessões de áudio/vídeo com falha durante um determinado dia. Se você observar o Relatório de Distribuição de Falhas, ele poderá mostrar que 237 das sessões com falha ocorreram no pool de Dublin. Isso fornece um ótimo ponto inicial para rastrear e diagnosticar as causas por trás dessas falhas. Se você clicar no pool de Dublin na categoria **Principais pools**, você verá um Relatório de Distribuição de Falhas exclusivo desse pool. Será possível então começar a analisar por que o pool de Dublin enfrentou tantas dificuldades.</span><span class="sxs-lookup"><span data-stu-id="c472f-p101">You can use these categories to determine exactly where a problem is occurring and, in some cases, why the problem is occurring. For example, suppose you recorded 242 failed audio/video sessions during a given day. If you look at the Failure Distribution Report, it might show that 237 of those failed sessions took place in your Dublin pool. That gives you a good place to start when it comes to tracking down and diagnosing the causes behind those failures. If you click on the Dublin pool under the **Top pools** category, you will see a Failure Distribution Report just for that pool. You can then begin analyzing why the Dublin pool was experiencing so many difficulties.</span></span>

<div>

## <a name="viewing-the-failure-distribution-report"></a><span data-ttu-id="c472f-119">Exibindo o Relatório de Distribuição de Falhas</span><span class="sxs-lookup"><span data-stu-id="c472f-119">Viewing the Failure Distribution Report</span></span>

<span data-ttu-id="c472f-120">É possível acessar o Relatório de Distribuição de Falhas a partir de qualquer um dos seguintes relatórios clicando nas medidas **Volume de falhas esperado** ou **Volume de falhas não esperado**:</span><span class="sxs-lookup"><span data-stu-id="c472f-120">You can access the Failure Distribution Report from any of the following reports by clicking either the **Expected failure volume** or the **Unexpected failure volume** metric:</span></span>

  - [<span data-ttu-id="c472f-121">Relatório de falhas principais no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c472f-121">Top Failures Report in Lync Server 2013</span></span>](lync-server-2013-top-failures-report.md)

  - [<span data-ttu-id="c472f-122">Relatório de diagnóstico de conferência no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c472f-122">Conference Diagnostic Report in Lync Server 2013</span></span>](lync-server-2013-conference-diagnostic-report.md)

  - [<span data-ttu-id="c472f-123">Relatório de diagnóstico de atividade ponto a ponto no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c472f-123">Peer-to-Peer Activity Diagnostic Report in Lync Server 2013</span></span>](lync-server-2013-peer-to-peer-activity-diagnostic-report.md)

<span data-ttu-id="c472f-124">No relatório de distribuição de falhas, você pode clicar em qualquer uma das métricas a seguir para exibir o [relatório de lista de falhas no Lync Server 2013](lync-server-2013-failure-list-report.md):</span><span class="sxs-lookup"><span data-stu-id="c472f-124">From the Failure Distribution Report, you can click any of the following metrics to view the [Failure List Report in Lync Server 2013](lync-server-2013-failure-list-report.md):</span></span>

  - <span data-ttu-id="c472f-125">Principais motivos diagnósticos (sessões)</span><span class="sxs-lookup"><span data-stu-id="c472f-125">Top diagnostic reasons (sessions)</span></span>

  - <span data-ttu-id="c472f-126">Principais modalidades (sessões)</span><span class="sxs-lookup"><span data-stu-id="c472f-126">Top modalities (sessions)</span></span>

  - <span data-ttu-id="c472f-127">Principais pools (sessões)</span><span class="sxs-lookup"><span data-stu-id="c472f-127">Top pools (sessions)</span></span>

  - <span data-ttu-id="c472f-128">Principais fontes (sessões)</span><span class="sxs-lookup"><span data-stu-id="c472f-128">Top sources (sessions)</span></span>

  - <span data-ttu-id="c472f-129">Principais componentes (sessões)</span><span class="sxs-lookup"><span data-stu-id="c472f-129">Top components (sessions)</span></span>

  - <span data-ttu-id="c472f-130">Principais usuários de origem (sessões)</span><span class="sxs-lookup"><span data-stu-id="c472f-130">Top from users (sessions)</span></span>

  - <span data-ttu-id="c472f-131">Principais usuários de destino (sessões)</span><span class="sxs-lookup"><span data-stu-id="c472f-131">Top to users (sessions)</span></span>

  - <span data-ttu-id="c472f-132">Principais agentes de usuários de origem (sessões)</span><span class="sxs-lookup"><span data-stu-id="c472f-132">Top from user agents (sessions)</span></span>

</div>

<div>

## <a name="using-the-failure-distribution-report"></a><span data-ttu-id="c472f-133">Usando o Relatório de Distribuição de Falhas</span><span class="sxs-lookup"><span data-stu-id="c472f-133">Using the Failure Distribution Report</span></span>

<span data-ttu-id="c472f-p102">Dependendo do tamanho de seu monitor e da resolução da tela, é possível que alguns dos dados apresentados no Relatório de Distribuição de Falhas sejam truncados que exibidos na tela. Por exemplo, um agente de usuário com o nome "UCCAPI/4.0.7400.0 OC/4.0.7400.0 (Microsoft Lync 2013)" poderá aparecer apenas parcialmente na tela:</span><span class="sxs-lookup"><span data-stu-id="c472f-p102">Depending on your monitor size and screen resolution, it's possible that some of the data shown in the Failure Distribution Report might be truncated when you view it onscreen. This is especially true for metrics such as user agents, which can have very long labels. For example, a user agent with a name like "UCCAPI/4.0.7400.0 OC/4.0.7400.0 (Microsoft Lync 2013)" might only partially appear onscreen:</span></span>

<span data-ttu-id="c472f-137">UCCAPI/4.0.7400.0 OC/4.0.7400.0 (Microsoft Ly...</span><span class="sxs-lookup"><span data-stu-id="c472f-137">UCCAPI/4.0.7400.0 OC/4.0.7400.0 (Microsoft Ly...</span></span>

<span data-ttu-id="c472f-138">Felizmente, é possível ver o nome completo mantendo o mouse sobre o valor truncado.</span><span class="sxs-lookup"><span data-stu-id="c472f-138">Fortunately, you can see the entire label simply by holding your mouse over the truncated value.</span></span>

<span data-ttu-id="c472f-p103">Um medida interessante que pode ser filtrada usando o Relatório de Distribuição de Falhas é o ID do diagnóstico. Se vir o mesmo ID do diagnóstico surgir em outros relatórios, será possível filtrar esse ID no Relatório de Distribuição de Falhas e obter uma visão bastante detalhada de exatamente onde e com que frequência esse ID foi reportado durante uma sessão com falha.</span><span class="sxs-lookup"><span data-stu-id="c472f-p103">One interesting metric that you can filter on by using the Failure Distribution Report is Diagnostic ID. If you see the same Diagnostic ID cropping up in other reports you can filter on that ID in the Failure Distribution Report and get a very detailed look at exactly where, and how often, that ID has been reported during a failed session.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="c472f-141">Filtros</span><span class="sxs-lookup"><span data-stu-id="c472f-141">Filters</span></span>

<span data-ttu-id="c472f-p104">O filtro é uma maneira de retornar um conjunto de dados mais refinado e direcionado, ou ver os dados retornados de maneiras diferentes. Por exemplo, o Relatório de Falha na Distribuição permite filtrar itens como tipo de atividade (sessão ponto a ponto ou de conferência) ou pelo ID diagnóstico que acompanha cada sessão com falha.</span><span class="sxs-lookup"><span data-stu-id="c472f-p104">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Failed Distribution Report enables you to filter on such things as the activity type (peer-to-peer session or conferencing session) or by the diagnostic ID that accompanied each failed session.</span></span>

<span data-ttu-id="c472f-144">A tabela a seguir lista os filtros que você pode usar com o Relatório de Falha na Distribuição.</span><span class="sxs-lookup"><span data-stu-id="c472f-144">The following table lists the filters that you can use with the Failure Distribution Report.</span></span>

### <a name="failure-distribution-report-filters"></a><span data-ttu-id="c472f-145">Filtros do Relatório de Falha na Distribuição.</span><span class="sxs-lookup"><span data-stu-id="c472f-145">Failure Distribution Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c472f-146">Nome</span><span class="sxs-lookup"><span data-stu-id="c472f-146">Name</span></span></th>
<th><span data-ttu-id="c472f-147">Descrição</span><span class="sxs-lookup"><span data-stu-id="c472f-147">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c472f-148"><strong>De</strong></span><span class="sxs-lookup"><span data-stu-id="c472f-148"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="c472f-p105">Data/hora inicial para o intervalo de tempo. Para exibir os dados por hora, insira a data e hora inicial como a seguir:</span><span class="sxs-lookup"><span data-stu-id="c472f-p105">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="c472f-151">7/7/2012 13:00 horas</span><span class="sxs-lookup"><span data-stu-id="c472f-151">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="c472f-p106">Se você não inserir uma hora inicial, o relatório começa automaticamente as 12:00 AM no dia especificado. Para exibir os dados por dia, insira apenas a data:</span><span class="sxs-lookup"><span data-stu-id="c472f-p106">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="c472f-154">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="c472f-154">7/7/2012</span></span></p>
<p><span data-ttu-id="c472f-155">Para exibir por semana ou mês, insira uma data que está dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):</span><span class="sxs-lookup"><span data-stu-id="c472f-155">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="c472f-156">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="c472f-156">7/3/2012</span></span></p>
<p><span data-ttu-id="c472f-157">As semanas são sempre de domingo a sábado.</span><span class="sxs-lookup"><span data-stu-id="c472f-157">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c472f-158"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="c472f-158"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="c472f-p107">Data/hora final para o intervalo de tempo. Para exibir os dados por hora, insira a data e hora final como a seguir:</span><span class="sxs-lookup"><span data-stu-id="c472f-p107">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="c472f-161">7/7/2012 13:00 horas</span><span class="sxs-lookup"><span data-stu-id="c472f-161">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="c472f-p108">Se você não inserir uma hora final, o relatório termina automaticamente as 12:00 AM no dia especificado. Para exibir os dados por dia, insira apenas a data:</span><span class="sxs-lookup"><span data-stu-id="c472f-p108">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="c472f-164">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="c472f-164">7/7/2012</span></span></p>
<p><span data-ttu-id="c472f-165">Para exibir por semana ou mês, insira uma data que está dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):</span><span class="sxs-lookup"><span data-stu-id="c472f-165">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="c472f-166">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="c472f-166">7/3/2012</span></span></p>
<p><span data-ttu-id="c472f-167">As semanas sempre correm do domingo até sábado.</span><span class="sxs-lookup"><span data-stu-id="c472f-167">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c472f-168"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="c472f-168"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="c472f-p109">FQDN (Nome de domínio totalmente qualificado) do pool de Registradores ou Servidor de Borda. Você pode selecionar um pool individual ou clicar em <strong>[Tudo]</strong> para ver os dados de todos os pools. Essa lista suspensa é automaticamente preenchida para você com base nos registros no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="c472f-p109">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c472f-172"><strong>Tipo de atividade</strong></span><span class="sxs-lookup"><span data-stu-id="c472f-172"><strong>Activity type</strong></span></span></p></td>
<td><p><span data-ttu-id="c472f-p110">Tipo de atividade para filtrar. Selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="c472f-p110">Type of activity to filter on. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="c472f-175">Todos os</span><span class="sxs-lookup"><span data-stu-id="c472f-175">[All]</span></span></p></li>
<li><p><span data-ttu-id="c472f-176">Ponto a ponto</span><span class="sxs-lookup"><span data-stu-id="c472f-176">Peer-to-peer</span></span></p></li>
<li><p><span data-ttu-id="c472f-177">Conferência</span><span class="sxs-lookup"><span data-stu-id="c472f-177">Conference</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c472f-178"><strong>Categoria da sessão</strong></span><span class="sxs-lookup"><span data-stu-id="c472f-178"><strong>Session category</strong></span></span></p></td>
<td><p><span data-ttu-id="c472f-p111">Indica se a atividade em questão teve sucesso ou falhou. Selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="c472f-p111">Indicates whether the activity in question succeeded or failed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="c472f-181">Todos os</span><span class="sxs-lookup"><span data-stu-id="c472f-181">[All]</span></span></p></li>
<li><p><span data-ttu-id="c472f-182">Êxito</span><span class="sxs-lookup"><span data-stu-id="c472f-182">Success</span></span></p></li>
<li><p><span data-ttu-id="c472f-183">Falha esperada</span><span class="sxs-lookup"><span data-stu-id="c472f-183">Expected failure</span></span></p></li>
<li><p><span data-ttu-id="c472f-184">Falha inesperada</span><span class="sxs-lookup"><span data-stu-id="c472f-184">Unexpected failure</span></span></p></li>
</ul>
<p><span data-ttu-id="c472f-185">Uma &quot;falha&quot; esperada é uma falha que deve ocorrer.</span><span class="sxs-lookup"><span data-stu-id="c472f-185">An &quot;expected failure&quot; is a failure that is expected to happen.</span></span> <span data-ttu-id="c472f-186">Por exemplo, se um usuário configurou seu status para Não Perturbe, é previsto que qualquer chamada para ele irá falhar.</span><span class="sxs-lookup"><span data-stu-id="c472f-186">For example, if a user has set his or her status to Do Not Disturb you would expect any call to that user to fail.</span></span> <span data-ttu-id="c472f-187">Uma &quot;falha&quot; inesperada é uma falha que ocorre no que parece ser um sistema saudável de outra forma.</span><span class="sxs-lookup"><span data-stu-id="c472f-187">An &quot;unexpected failure&quot; is a failure that occurs in what would appear to be an otherwise healthy system.</span></span> <span data-ttu-id="c472f-188">Por exemplo, uma chamada não deveria ser terminada se o chamador for colocado em espera.</span><span class="sxs-lookup"><span data-stu-id="c472f-188">For example, a call should not be terminated if the caller is placed on hold.</span></span> <span data-ttu-id="c472f-189">Se isso ocorrer, será sinalizado como uma falha inesperada.</span><span class="sxs-lookup"><span data-stu-id="c472f-189">If that occurs, that would be flagged as an unexpected failure.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c472f-190"><strong>ID diagnóstico</strong></span><span class="sxs-lookup"><span data-stu-id="c472f-190"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="c472f-p113">Identificador exclusivo (na forma de um cabeçalho de diagnóstico-ms) anexado a uma mensagem SIP que fornece informações úteis sobre os erros de solução de problemas. Os cabeçalhos diagnósticos são opcionais (é possível ter sessões SIP que não os incluem), e os IDs diagnósticos são relatados somente para as sessões com algum tipo de problema.</span><span class="sxs-lookup"><span data-stu-id="c472f-p113">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors. Diagnostics headers are optional (it is possible to have SIP sessions that do not include these headers), and diagnostic IDs are reported only for sessions that experienced problems of some kind.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-diagnostic-reasons"></a><span data-ttu-id="c472f-193">Métricas para os principais motivos diagnósticos</span><span class="sxs-lookup"><span data-stu-id="c472f-193">Metrics for Top Diagnostic Reasons</span></span>

<span data-ttu-id="c472f-194">A tabela a seguir lista as informações fornecidas no Relatório de Falha de Distribuição, com base no ID diagnóstico relatado com mais frequência.</span><span class="sxs-lookup"><span data-stu-id="c472f-194">The following table lists the information provided in the Failure Distribution Report based on the most frequently reported diagnostic ID.</span></span>

### <a name="metrics-for-top-diagnostic-reasons"></a><span data-ttu-id="c472f-195">Métricas para os principais motivos diagnósticos</span><span class="sxs-lookup"><span data-stu-id="c472f-195">Metrics for Top Diagnostic Reasons</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c472f-196">Nome</span><span class="sxs-lookup"><span data-stu-id="c472f-196">Name</span></span></th>
<th><span data-ttu-id="c472f-197">É possível classificar este item?</span><span class="sxs-lookup"><span data-stu-id="c472f-197">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="c472f-198">Descrição</span><span class="sxs-lookup"><span data-stu-id="c472f-198">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c472f-199"><strong>Rank</strong></span><span class="sxs-lookup"><span data-stu-id="c472f-199"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="c472f-200">Não</span><span class="sxs-lookup"><span data-stu-id="c472f-200">No</span></span></p></td>
<td><p><span data-ttu-id="c472f-p114">Classificação relativa das sessões com falha, com base no ID diagnóstico, que é um identificador exclusivo (na forma de um cabeçalho de diagnóstico-ms) anexado a uma mensagem SIP que fornece informações úteis sobre os erros de solução de problemas.</span><span class="sxs-lookup"><span data-stu-id="c472f-p114">Relative ranking of failed sessions based on diagnostic IDs. The diagnostic ID is a unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c472f-203"><strong>Principais motivos diagnósticos</strong></span><span class="sxs-lookup"><span data-stu-id="c472f-203"><strong>Top diagnostic reasons</strong></span></span></p></td>
<td><p><span data-ttu-id="c472f-204">Não</span><span class="sxs-lookup"><span data-stu-id="c472f-204">No</span></span></p></td>
<td><p><span data-ttu-id="c472f-205">ID diagnóstico gerado em uma sessão.</span><span class="sxs-lookup"><span data-stu-id="c472f-205">Diagnostic ID generated in a session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c472f-206"><strong>Sessões</strong></span><span class="sxs-lookup"><span data-stu-id="c472f-206"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="c472f-207">Não</span><span class="sxs-lookup"><span data-stu-id="c472f-207">No</span></span></p></td>
<td><p><span data-ttu-id="c472f-208">Número total de sessões com falha em que ID diagnóstico especificado foi gerado.</span><span class="sxs-lookup"><span data-stu-id="c472f-208">Total number of failed sessions where the specified diagnostic ID was generated.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-modalities"></a><span data-ttu-id="c472f-209">Métricas para as principais modalidades</span><span class="sxs-lookup"><span data-stu-id="c472f-209">Metrics for Top Modalities</span></span>

<span data-ttu-id="c472f-210">A tabela a seguir lista as informações fornecidas no Relatório de Falha de Distribuição, com base nas modalidades de sessão que apresentaram mais falhas.</span><span class="sxs-lookup"><span data-stu-id="c472f-210">The following table lists the information provided in the Failure Distribution Report based on the session modalities that experienced the most failures.</span></span>

### <a name="metrics-for-top-modalities"></a><span data-ttu-id="c472f-211">Métricas para as principais modalidades</span><span class="sxs-lookup"><span data-stu-id="c472f-211">Metrics for Top Modalities</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c472f-212">Nome</span><span class="sxs-lookup"><span data-stu-id="c472f-212">Name</span></span></th>
<th><span data-ttu-id="c472f-213">É possível classificar este item?</span><span class="sxs-lookup"><span data-stu-id="c472f-213">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="c472f-214">Descrição</span><span class="sxs-lookup"><span data-stu-id="c472f-214">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c472f-215"><strong>Rank</strong></span><span class="sxs-lookup"><span data-stu-id="c472f-215"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="c472f-216">Não</span><span class="sxs-lookup"><span data-stu-id="c472f-216">No</span></span></p></td>
<td><p><span data-ttu-id="c472f-217">Classificação relativa com base na sessão com falha baseada no tipo de sessão (por exemplo, conferência de áudio/vídeo ou sessão de transferência de arquivo ponto a ponto).</span><span class="sxs-lookup"><span data-stu-id="c472f-217">Relative ranking based of failed session based on session type (for example, an audio/video conference or a peer-to-peer file transfer session).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c472f-218"><strong>Principais modalidades</strong></span><span class="sxs-lookup"><span data-stu-id="c472f-218"><strong>Top modalities</strong></span></span></p></td>
<td><p><span data-ttu-id="c472f-219">Não</span><span class="sxs-lookup"><span data-stu-id="c472f-219">No</span></span></p></td>
<td><p><span data-ttu-id="c472f-220">Tipo de sessão.</span><span class="sxs-lookup"><span data-stu-id="c472f-220">Session type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c472f-221"><strong>Sessões</strong></span><span class="sxs-lookup"><span data-stu-id="c472f-221"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="c472f-222">Não</span><span class="sxs-lookup"><span data-stu-id="c472f-222">No</span></span></p></td>
<td><p><span data-ttu-id="c472f-223">Número total de sessões com falha envolvendo a modalidade especificada.</span><span class="sxs-lookup"><span data-stu-id="c472f-223">Total number of failed sessions involving the specified modality.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-pools"></a><span data-ttu-id="c472f-224">Métricas para os principais pools</span><span class="sxs-lookup"><span data-stu-id="c472f-224">Metrics for Top Pools</span></span>

<span data-ttu-id="c472f-225">A tabela a seguir lista as informações fornecidas no Relatório de Falha de Distribuição, com base nos pools que apresentaram mais falhas.</span><span class="sxs-lookup"><span data-stu-id="c472f-225">The following table lists the information provided in the Failure Distribution Report based on the pools that experienced the most failures.</span></span>

### <a name="metrics-for-top-pools"></a><span data-ttu-id="c472f-226">Métricas para os principais pools</span><span class="sxs-lookup"><span data-stu-id="c472f-226">Metrics for Top Pools</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c472f-227">Nome</span><span class="sxs-lookup"><span data-stu-id="c472f-227">Name</span></span></th>
<th><span data-ttu-id="c472f-228">É possível classificar este item?</span><span class="sxs-lookup"><span data-stu-id="c472f-228">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="c472f-229">Descrição</span><span class="sxs-lookup"><span data-stu-id="c472f-229">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c472f-230"><strong>Rank</strong></span><span class="sxs-lookup"><span data-stu-id="c472f-230"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="c472f-231">Não</span><span class="sxs-lookup"><span data-stu-id="c472f-231">No</span></span></p></td>
<td><p><span data-ttu-id="c472f-232">Classificação relativa de sessões com falha com base no pool de registradores ou no servidor de borda onde a sessão foi conduzida.</span><span class="sxs-lookup"><span data-stu-id="c472f-232">Relative ranking of failed sessions based on the Registrar pool or Edge Server where the session was conducted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c472f-233"><strong>Principais pools</strong></span><span class="sxs-lookup"><span data-stu-id="c472f-233"><strong>Top pools</strong></span></span></p></td>
<td><p><span data-ttu-id="c472f-234">Não</span><span class="sxs-lookup"><span data-stu-id="c472f-234">No</span></span></p></td>
<td><p><span data-ttu-id="c472f-235">Nome do pool de registradores ou servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="c472f-235">Name of the Registrar pool or Edge Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c472f-236"><strong>Sessões</strong></span><span class="sxs-lookup"><span data-stu-id="c472f-236"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="c472f-237">Não</span><span class="sxs-lookup"><span data-stu-id="c472f-237">No</span></span></p></td>
<td><p><span data-ttu-id="c472f-238">Número total de sessões com falha por pool de registradores ou servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="c472f-238">Total number of failed sessions per Registrar pool or Edge Server.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-sources"></a><span data-ttu-id="c472f-239">Métricas para as principais fontes</span><span class="sxs-lookup"><span data-stu-id="c472f-239">Metrics for Top Sources</span></span>

<span data-ttu-id="c472f-240">A tabela a seguir lista as informações fornecidas no Relatório de Falha de Distribuição, com base nos computadores que apresentaram mais falhas.</span><span class="sxs-lookup"><span data-stu-id="c472f-240">The following table lists the information provided in the Failure Distribution Report based on the computers that experienced the most failures.</span></span>

### <a name="metrics-for-top-sources"></a><span data-ttu-id="c472f-241">Métricas para as principais fontes</span><span class="sxs-lookup"><span data-stu-id="c472f-241">Metrics for Top Sources</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c472f-242">Nome</span><span class="sxs-lookup"><span data-stu-id="c472f-242">Name</span></span></th>
<th><span data-ttu-id="c472f-243">É possível classificar este item?</span><span class="sxs-lookup"><span data-stu-id="c472f-243">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="c472f-244">Descrição</span><span class="sxs-lookup"><span data-stu-id="c472f-244">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c472f-245"><strong>Rank</strong></span><span class="sxs-lookup"><span data-stu-id="c472f-245"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="c472f-246">Não</span><span class="sxs-lookup"><span data-stu-id="c472f-246">No</span></span></p></td>
<td><p><span data-ttu-id="c472f-247">Classificação relativa das sessões com falha por computador.</span><span class="sxs-lookup"><span data-stu-id="c472f-247">Relative ranking failed sessions per computer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c472f-248"><strong>Principais fontes</strong></span><span class="sxs-lookup"><span data-stu-id="c472f-248"><strong>Top sources</strong></span></span></p></td>
<td><p><span data-ttu-id="c472f-249">Não</span><span class="sxs-lookup"><span data-stu-id="c472f-249">No</span></span></p></td>
<td><p><span data-ttu-id="c472f-250">Nome do computador envolvido na sessão com falha.</span><span class="sxs-lookup"><span data-stu-id="c472f-250">Name of the computer involved in the failed session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c472f-251"><strong>Sessões</strong></span><span class="sxs-lookup"><span data-stu-id="c472f-251"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="c472f-252">Não</span><span class="sxs-lookup"><span data-stu-id="c472f-252">No</span></span></p></td>
<td><p><span data-ttu-id="c472f-253">Número total de sessões com falha por computador.</span><span class="sxs-lookup"><span data-stu-id="c472f-253">Total number of failed sessions per computer.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-components"></a><span data-ttu-id="c472f-254">Métricas para os principais componentes</span><span class="sxs-lookup"><span data-stu-id="c472f-254">Metrics for Top Components</span></span>

<span data-ttu-id="c472f-255">A tabela a seguir lista as informações fornecidas no relatório de falha de distribuição, com base nos componentes do Microsoft Lync Server 2010 que apresentaram mais falhas.</span><span class="sxs-lookup"><span data-stu-id="c472f-255">The following table lists the information provided in the Failure Distribution Report based on the Microsoft Lync Server 2010 components that experienced the most failures.</span></span>

### <a name="metrics-for-top-components"></a><span data-ttu-id="c472f-256">Métricas para os principais componentes</span><span class="sxs-lookup"><span data-stu-id="c472f-256">Metrics for Top Components</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c472f-257">Nome</span><span class="sxs-lookup"><span data-stu-id="c472f-257">Name</span></span></th>
<th><span data-ttu-id="c472f-258">É possível classificar este item?</span><span class="sxs-lookup"><span data-stu-id="c472f-258">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="c472f-259">Descrição</span><span class="sxs-lookup"><span data-stu-id="c472f-259">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c472f-260"><strong>Rank</strong></span><span class="sxs-lookup"><span data-stu-id="c472f-260"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="c472f-261">Não</span><span class="sxs-lookup"><span data-stu-id="c472f-261">No</span></span></p></td>
<td><p><span data-ttu-id="c472f-262">Classificação relativa de sessões com falha com base no componente do Lync Server 2010 (por exemplo, ExumRouting, GroupChat ou MediationServer).</span><span class="sxs-lookup"><span data-stu-id="c472f-262">Relative ranking of failed sessions based on Lync Server 2010 component (for example, ExumRouting, GroupChat, or MediationServer).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c472f-263"><strong>Principais componentes</strong></span><span class="sxs-lookup"><span data-stu-id="c472f-263"><strong>Top components</strong></span></span></p></td>
<td><p><span data-ttu-id="c472f-264">Não</span><span class="sxs-lookup"><span data-stu-id="c472f-264">No</span></span></p></td>
<td><p><span data-ttu-id="c472f-265">Nome do componente envolvido na sessão com falha.</span><span class="sxs-lookup"><span data-stu-id="c472f-265">Name of the component involved in the failed session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c472f-266"><strong>Sessões</strong></span><span class="sxs-lookup"><span data-stu-id="c472f-266"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="c472f-267">Não</span><span class="sxs-lookup"><span data-stu-id="c472f-267">No</span></span></p></td>
<td><p><span data-ttu-id="c472f-268">Número total de sessões com falha por componente.</span><span class="sxs-lookup"><span data-stu-id="c472f-268">Total number of failed sessions per component.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-from-users"></a><span data-ttu-id="c472f-269">Métricas para os principais usuários "De"</span><span class="sxs-lookup"><span data-stu-id="c472f-269">Metrics for Top From Users</span></span>

<span data-ttu-id="c472f-270">A tabela a seguir lista as informações fornecidas no Relatório de Falha de Distribuição, com base nos usuários que apresentaram mais falhas quando tentaram chamar alguém (conhecidos como usuários "De").</span><span class="sxs-lookup"><span data-stu-id="c472f-270">The following table lists the information provided in the Failure Distribution Report based on users who experienced the most failures when they tried to call someone else (known as "From" users).</span></span>

### <a name="metrics-for-top-from-users"></a><span data-ttu-id="c472f-271">Métricas para os principais usuários "Para"</span><span class="sxs-lookup"><span data-stu-id="c472f-271">Metrics for Top From Users</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c472f-272">Nome</span><span class="sxs-lookup"><span data-stu-id="c472f-272">Name</span></span></th>
<th><span data-ttu-id="c472f-273">É possível classificar este item?</span><span class="sxs-lookup"><span data-stu-id="c472f-273">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="c472f-274">Descrição</span><span class="sxs-lookup"><span data-stu-id="c472f-274">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c472f-275"><strong>Rank</strong></span><span class="sxs-lookup"><span data-stu-id="c472f-275"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="c472f-276">Não</span><span class="sxs-lookup"><span data-stu-id="c472f-276">No</span></span></p></td>
<td><p><span data-ttu-id="c472f-277">Classificação relativa das sessões com falha, com base no usuário convidado a entrar na sessão.</span><span class="sxs-lookup"><span data-stu-id="c472f-277">Relative ranking of failed sessions based on the user who was invited to join the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c472f-278"><strong>Principais usuários "Para"</strong></span><span class="sxs-lookup"><span data-stu-id="c472f-278"><strong>Top from users</strong></span></span></p></td>
<td><p><span data-ttu-id="c472f-279">Não</span><span class="sxs-lookup"><span data-stu-id="c472f-279">No</span></span></p></td>
<td><p><span data-ttu-id="c472f-280">Endereço SIP do usuário convidado para entrar na sessão.</span><span class="sxs-lookup"><span data-stu-id="c472f-280">SIP address of the user invited to join the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c472f-281"><strong>Sessões</strong></span><span class="sxs-lookup"><span data-stu-id="c472f-281"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="c472f-282">Não</span><span class="sxs-lookup"><span data-stu-id="c472f-282">No</span></span></p></td>
<td><p><span data-ttu-id="c472f-283">Número total de sessões com falha por usuário.</span><span class="sxs-lookup"><span data-stu-id="c472f-283">Total number of failed sessions per user.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-to-users"></a><span data-ttu-id="c472f-284">Métricas para os principais usuários</span><span class="sxs-lookup"><span data-stu-id="c472f-284">Metrics for Top To Users</span></span>

<span data-ttu-id="c472f-285">A tabela a seguir lista as informações fornecidas no Relatório de Falha de Distribuição, com base nos usuários que apresentaram mais falhas quando o outro usuário tentou chamá-los (conhecidos como usuários "Para").</span><span class="sxs-lookup"><span data-stu-id="c472f-285">The following table lists the information provided in the Failure Distribution Report based on the users who experienced the most failures when another user tried to call them (known as "To" users).</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c472f-286">Nome</span><span class="sxs-lookup"><span data-stu-id="c472f-286">Name</span></span></th>
<th><span data-ttu-id="c472f-287">É possível classificar este item?</span><span class="sxs-lookup"><span data-stu-id="c472f-287">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="c472f-288">Descrição</span><span class="sxs-lookup"><span data-stu-id="c472f-288">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c472f-289"><strong>Rank</strong></span><span class="sxs-lookup"><span data-stu-id="c472f-289"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="c472f-290">Não</span><span class="sxs-lookup"><span data-stu-id="c472f-290">No</span></span></p></td>
<td><p><span data-ttu-id="c472f-291">Classificação relativa das sessões com falha, com base no usuário que iniciou a sessão.</span><span class="sxs-lookup"><span data-stu-id="c472f-291">Relative ranking of failed sessions based on the user who initiated the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c472f-292"><strong>Principais usuários "Para"</strong></span><span class="sxs-lookup"><span data-stu-id="c472f-292"><strong>Top to users</strong></span></span></p></td>
<td><p><span data-ttu-id="c472f-293">Não</span><span class="sxs-lookup"><span data-stu-id="c472f-293">No</span></span></p></td>
<td><p><span data-ttu-id="c472f-294">Endereço SIP do usuário que iniciou a sessão.</span><span class="sxs-lookup"><span data-stu-id="c472f-294">SIP address of the user who initiated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c472f-295"><strong>Sessões</strong></span><span class="sxs-lookup"><span data-stu-id="c472f-295"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="c472f-296">Não</span><span class="sxs-lookup"><span data-stu-id="c472f-296">No</span></span></p></td>
<td><p><span data-ttu-id="c472f-297">Número total de sessões com falha por usuário.</span><span class="sxs-lookup"><span data-stu-id="c472f-297">Total number of failed sessions per user.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-user-agents"></a><span data-ttu-id="c472f-298">Métricas para os principais agentes do usuário</span><span class="sxs-lookup"><span data-stu-id="c472f-298">Metrics for Top User Agents</span></span>

<span data-ttu-id="c472f-299">A tabela a seguir lista as informações fornecidas no Relatório de Falha de Distribuição, com base no software de ponto de extremidade que apresentou mais falhas.</span><span class="sxs-lookup"><span data-stu-id="c472f-299">The following table lists the information provided in the Failure Distribution Report based on the endpoint software that experienced the most failures.</span></span>

### <a name="metrics-for-top-user-agents"></a><span data-ttu-id="c472f-300">Métricas para os principais agentes do usuário</span><span class="sxs-lookup"><span data-stu-id="c472f-300">Metrics for Top User Agents</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c472f-301">Nome</span><span class="sxs-lookup"><span data-stu-id="c472f-301">Name</span></span></th>
<th><span data-ttu-id="c472f-302">É possível classificar este item?</span><span class="sxs-lookup"><span data-stu-id="c472f-302">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="c472f-303">Descrição</span><span class="sxs-lookup"><span data-stu-id="c472f-303">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c472f-304"><strong>Rank</strong></span><span class="sxs-lookup"><span data-stu-id="c472f-304"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="c472f-305">Não</span><span class="sxs-lookup"><span data-stu-id="c472f-305">No</span></span></p></td>
<td><p><span data-ttu-id="c472f-p115">Classificação relativa de sessões com falha, com base no agente do usuário (software) envolvido na sessão. Por exemplo: RTCC/4.0.0.0 Inbound Routing/4.0.0.0.</span><span class="sxs-lookup"><span data-stu-id="c472f-p115">Relative ranking of failed sessions based on the user agent (software) involved in the session. For example: RTCC/4.0.0.0 Inbound Routing/4.0.0.0.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c472f-308"><strong>Principais agentes do usuário</strong></span><span class="sxs-lookup"><span data-stu-id="c472f-308"><strong>Top user agents</strong></span></span></p></td>
<td><p><span data-ttu-id="c472f-309">Não</span><span class="sxs-lookup"><span data-stu-id="c472f-309">No</span></span></p></td>
<td><p><span data-ttu-id="c472f-310">Nome do agente do usuário envolvido na sessão com falha.</span><span class="sxs-lookup"><span data-stu-id="c472f-310">Name of the user agent involved in the failed session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c472f-311"><strong>Sessões</strong></span><span class="sxs-lookup"><span data-stu-id="c472f-311"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="c472f-312">Não</span><span class="sxs-lookup"><span data-stu-id="c472f-312">No</span></span></p></td>
<td><p><span data-ttu-id="c472f-313">Número total de sessões com falha por agente do usuário.</span><span class="sxs-lookup"><span data-stu-id="c472f-313">Total number of failed sessions per user agent.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

