---
title: 'Lync Server 2013: relatório de distribuição de falhas'
description: 'Lync Server 2013: relatório de distribuição de falhas.'
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
ms.openlocfilehash: f5a87f779f87d6b7002fa108f1969c33739eed9b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564727"
---
# <a name="failure-distribution-report-in-lync-server-2013"></a><span data-ttu-id="1eabc-103">Relatório de distribuição de falhas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1eabc-103">Failure Distribution Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1eabc-104">_**Última modificação do tópico:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="1eabc-104">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="1eabc-105">O Relatório de Distribuição de Falhas classifica sessões com falha nas seguintes categorias:</span><span class="sxs-lookup"><span data-stu-id="1eabc-105">The Failure Distribution Report ranks failed sessions in the following categories:</span></span>

  - <span data-ttu-id="1eabc-106">Principais motivos diagnósticos</span><span class="sxs-lookup"><span data-stu-id="1eabc-106">Top diagnostic reasons</span></span>

  - <span data-ttu-id="1eabc-107">Principais modalidades</span><span class="sxs-lookup"><span data-stu-id="1eabc-107">Top modalities</span></span>

  - <span data-ttu-id="1eabc-108">Principais pools</span><span class="sxs-lookup"><span data-stu-id="1eabc-108">Top pools</span></span>

  - <span data-ttu-id="1eabc-109">Principais fontes</span><span class="sxs-lookup"><span data-stu-id="1eabc-109">Top sources</span></span>

  - <span data-ttu-id="1eabc-110">Principais componentes</span><span class="sxs-lookup"><span data-stu-id="1eabc-110">Top components</span></span>

  - <span data-ttu-id="1eabc-111">Principais usuários de origem</span><span class="sxs-lookup"><span data-stu-id="1eabc-111">Top from users</span></span>

  - <span data-ttu-id="1eabc-112">Principais usuários de destino</span><span class="sxs-lookup"><span data-stu-id="1eabc-112">Top to users</span></span>

  - <span data-ttu-id="1eabc-113">Principal usuário de origem</span><span class="sxs-lookup"><span data-stu-id="1eabc-113">Top from user agents</span></span>

<span data-ttu-id="1eabc-p101">É possível usar essas categorias para determinar exatamente onde está ocorrendo um problema e, em alguns casos, porque o problema está ocorrendo. Por exemplo, suponha que você tenha registrado 242 sessões de áudio/vídeo com falha durante um determinado dia. Se você observar o Relatório de Distribuição de Falhas, ele poderá mostrar que 237 das sessões com falha ocorreram no pool de Dublin. Isso fornece um ótimo ponto inicial para rastrear e diagnosticar as causas por trás dessas falhas. Se você clicar no pool de Dublin na categoria **Principais pools**, você verá um Relatório de Distribuição de Falhas exclusivo desse pool. Será possível então começar a analisar por que o pool de Dublin enfrentou tantas dificuldades.</span><span class="sxs-lookup"><span data-stu-id="1eabc-p101">You can use these categories to determine exactly where a problem is occurring and, in some cases, why the problem is occurring. For example, suppose you recorded 242 failed audio/video sessions during a given day. If you look at the Failure Distribution Report, it might show that 237 of those failed sessions took place in your Dublin pool. That gives you a good place to start when it comes to tracking down and diagnosing the causes behind those failures. If you click on the Dublin pool under the **Top pools** category, you will see a Failure Distribution Report just for that pool. You can then begin analyzing why the Dublin pool was experiencing so many difficulties.</span></span>

<div>

## <a name="viewing-the-failure-distribution-report"></a><span data-ttu-id="1eabc-120">Exibindo o Relatório de Distribuição de Falhas</span><span class="sxs-lookup"><span data-stu-id="1eabc-120">Viewing the Failure Distribution Report</span></span>

<span data-ttu-id="1eabc-121">É possível acessar o Relatório de Distribuição de Falhas a partir de qualquer um dos seguintes relatórios clicando nas medidas **Volume de falhas esperado** ou **Volume de falhas não esperado**:</span><span class="sxs-lookup"><span data-stu-id="1eabc-121">You can access the Failure Distribution Report from any of the following reports by clicking either the **Expected failure volume** or the **Unexpected failure volume** metric:</span></span>

  - [<span data-ttu-id="1eabc-122">Relatório de falhas principais no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1eabc-122">Top Failures Report in Lync Server 2013</span></span>](lync-server-2013-top-failures-report.md)

  - [<span data-ttu-id="1eabc-123">Relatório de diagnóstico de conferência no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1eabc-123">Conference Diagnostic Report in Lync Server 2013</span></span>](lync-server-2013-conference-diagnostic-report.md)

  - [<span data-ttu-id="1eabc-124">Relatório de diagnóstico de atividade ponto a ponto no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1eabc-124">Peer-to-Peer Activity Diagnostic Report in Lync Server 2013</span></span>](lync-server-2013-peer-to-peer-activity-diagnostic-report.md)

<span data-ttu-id="1eabc-125">No relatório de distribuição de falhas, você pode clicar em qualquer uma das métricas a seguir para exibir o [relatório de lista de falhas no Lync Server 2013](lync-server-2013-failure-list-report.md):</span><span class="sxs-lookup"><span data-stu-id="1eabc-125">From the Failure Distribution Report, you can click any of the following metrics to view the [Failure List Report in Lync Server 2013](lync-server-2013-failure-list-report.md):</span></span>

  - <span data-ttu-id="1eabc-126">Principais motivos diagnósticos (sessões)</span><span class="sxs-lookup"><span data-stu-id="1eabc-126">Top diagnostic reasons (sessions)</span></span>

  - <span data-ttu-id="1eabc-127">Principais modalidades (sessões)</span><span class="sxs-lookup"><span data-stu-id="1eabc-127">Top modalities (sessions)</span></span>

  - <span data-ttu-id="1eabc-128">Principais pools (sessões)</span><span class="sxs-lookup"><span data-stu-id="1eabc-128">Top pools (sessions)</span></span>

  - <span data-ttu-id="1eabc-129">Principais fontes (sessões)</span><span class="sxs-lookup"><span data-stu-id="1eabc-129">Top sources (sessions)</span></span>

  - <span data-ttu-id="1eabc-130">Principais componentes (sessões)</span><span class="sxs-lookup"><span data-stu-id="1eabc-130">Top components (sessions)</span></span>

  - <span data-ttu-id="1eabc-131">Principais usuários de origem (sessões)</span><span class="sxs-lookup"><span data-stu-id="1eabc-131">Top from users (sessions)</span></span>

  - <span data-ttu-id="1eabc-132">Principais usuários de destino (sessões)</span><span class="sxs-lookup"><span data-stu-id="1eabc-132">Top to users (sessions)</span></span>

  - <span data-ttu-id="1eabc-133">Principais agentes de usuários de origem (sessões)</span><span class="sxs-lookup"><span data-stu-id="1eabc-133">Top from user agents (sessions)</span></span>

</div>

<div>

## <a name="using-the-failure-distribution-report"></a><span data-ttu-id="1eabc-134">Usando o Relatório de Distribuição de Falhas</span><span class="sxs-lookup"><span data-stu-id="1eabc-134">Using the Failure Distribution Report</span></span>

<span data-ttu-id="1eabc-p102">Dependendo do tamanho de seu monitor e da resolução da tela, é possível que alguns dos dados apresentados no Relatório de Distribuição de Falhas sejam truncados que exibidos na tela. Por exemplo, um agente de usuário com o nome "UCCAPI/4.0.7400.0 OC/4.0.7400.0 (Microsoft Lync 2013)" poderá aparecer apenas parcialmente na tela:</span><span class="sxs-lookup"><span data-stu-id="1eabc-p102">Depending on your monitor size and screen resolution, it's possible that some of the data shown in the Failure Distribution Report might be truncated when you view it onscreen. This is especially true for metrics such as user agents, which can have very long labels. For example, a user agent with a name like "UCCAPI/4.0.7400.0 OC/4.0.7400.0 (Microsoft Lync 2013)" might only partially appear onscreen:</span></span>

<span data-ttu-id="1eabc-138">UCCAPI/4.0.7400.0 OC/4.0.7400.0 (Microsoft Ly...</span><span class="sxs-lookup"><span data-stu-id="1eabc-138">UCCAPI/4.0.7400.0 OC/4.0.7400.0 (Microsoft Ly...</span></span>

<span data-ttu-id="1eabc-139">Felizmente, é possível ver o nome completo mantendo o mouse sobre o valor truncado.</span><span class="sxs-lookup"><span data-stu-id="1eabc-139">Fortunately, you can see the entire label simply by holding your mouse over the truncated value.</span></span>

<span data-ttu-id="1eabc-p103">Um medida interessante que pode ser filtrada usando o Relatório de Distribuição de Falhas é o ID do diagnóstico. Se vir o mesmo ID do diagnóstico surgir em outros relatórios, será possível filtrar esse ID no Relatório de Distribuição de Falhas e obter uma visão bastante detalhada de exatamente onde e com que frequência esse ID foi reportado durante uma sessão com falha.</span><span class="sxs-lookup"><span data-stu-id="1eabc-p103">One interesting metric that you can filter on by using the Failure Distribution Report is Diagnostic ID. If you see the same Diagnostic ID cropping up in other reports you can filter on that ID in the Failure Distribution Report and get a very detailed look at exactly where, and how often, that ID has been reported during a failed session.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="1eabc-142">Filtros</span><span class="sxs-lookup"><span data-stu-id="1eabc-142">Filters</span></span>

<span data-ttu-id="1eabc-p104">O filtro é uma maneira de retornar um conjunto de dados mais refinado e direcionado, ou ver os dados retornados de maneiras diferentes. Por exemplo, o Relatório de Falha na Distribuição permite filtrar itens como tipo de atividade (sessão ponto a ponto ou de conferência) ou pelo ID diagnóstico que acompanha cada sessão com falha.</span><span class="sxs-lookup"><span data-stu-id="1eabc-p104">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Failed Distribution Report enables you to filter on such things as the activity type (peer-to-peer session or conferencing session) or by the diagnostic ID that accompanied each failed session.</span></span>

<span data-ttu-id="1eabc-145">A tabela a seguir lista os filtros que você pode usar com o Relatório de Falha na Distribuição.</span><span class="sxs-lookup"><span data-stu-id="1eabc-145">The following table lists the filters that you can use with the Failure Distribution Report.</span></span>

### <a name="failure-distribution-report-filters"></a><span data-ttu-id="1eabc-146">Filtros do Relatório de Falha na Distribuição.</span><span class="sxs-lookup"><span data-stu-id="1eabc-146">Failure Distribution Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1eabc-147">Nome</span><span class="sxs-lookup"><span data-stu-id="1eabc-147">Name</span></span></th>
<th><span data-ttu-id="1eabc-148">Descrição</span><span class="sxs-lookup"><span data-stu-id="1eabc-148">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1eabc-149"><strong>De</strong></span><span class="sxs-lookup"><span data-stu-id="1eabc-149"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="1eabc-p105">Data/hora inicial para o intervalo de tempo. Para exibir os dados por hora, insira a data e hora inicial como a seguir:</span><span class="sxs-lookup"><span data-stu-id="1eabc-p105">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="1eabc-152">7/7/2012 13:00 horas</span><span class="sxs-lookup"><span data-stu-id="1eabc-152">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="1eabc-p106">Se você não inserir uma hora inicial, o relatório começa automaticamente as 12:00 AM no dia especificado. Para exibir os dados por dia, insira apenas a data:</span><span class="sxs-lookup"><span data-stu-id="1eabc-p106">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="1eabc-155">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="1eabc-155">7/7/2012</span></span></p>
<p><span data-ttu-id="1eabc-156">Para exibir por semana ou mês, insira uma data que está dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):</span><span class="sxs-lookup"><span data-stu-id="1eabc-156">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="1eabc-157">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="1eabc-157">7/3/2012</span></span></p>
<p><span data-ttu-id="1eabc-158">As semanas são sempre de domingo a sábado.</span><span class="sxs-lookup"><span data-stu-id="1eabc-158">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1eabc-159"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="1eabc-159"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="1eabc-p107">Data/hora final para o intervalo de tempo. Para exibir os dados por hora, insira a data e hora final como a seguir:</span><span class="sxs-lookup"><span data-stu-id="1eabc-p107">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="1eabc-162">7/7/2012 13:00 horas</span><span class="sxs-lookup"><span data-stu-id="1eabc-162">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="1eabc-p108">Se você não inserir uma hora final, o relatório termina automaticamente as 12:00 AM no dia especificado. Para exibir os dados por dia, insira apenas a data:</span><span class="sxs-lookup"><span data-stu-id="1eabc-p108">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="1eabc-165">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="1eabc-165">7/7/2012</span></span></p>
<p><span data-ttu-id="1eabc-166">Para exibir por semana ou mês, insira uma data que está dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):</span><span class="sxs-lookup"><span data-stu-id="1eabc-166">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="1eabc-167">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="1eabc-167">7/3/2012</span></span></p>
<p><span data-ttu-id="1eabc-168">As semanas sempre correm do domingo até sábado.</span><span class="sxs-lookup"><span data-stu-id="1eabc-168">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1eabc-169"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="1eabc-169"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="1eabc-p109">FQDN (Nome de domínio totalmente qualificado) do pool de Registradores ou Servidor de Borda. Você pode selecionar um pool individual ou clicar em <strong>[Tudo]</strong> para ver os dados de todos os pools. Essa lista suspensa é automaticamente preenchida para você com base nos registros no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="1eabc-p109">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1eabc-173"><strong>Tipo de atividade</strong></span><span class="sxs-lookup"><span data-stu-id="1eabc-173"><strong>Activity type</strong></span></span></p></td>
<td><p><span data-ttu-id="1eabc-p110">Tipo de atividade para filtrar. Selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="1eabc-p110">Type of activity to filter on. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="1eabc-176">Todos os</span><span class="sxs-lookup"><span data-stu-id="1eabc-176">[All]</span></span></p></li>
<li><p><span data-ttu-id="1eabc-177">Ponto a ponto</span><span class="sxs-lookup"><span data-stu-id="1eabc-177">Peer-to-peer</span></span></p></li>
<li><p><span data-ttu-id="1eabc-178">Conferência</span><span class="sxs-lookup"><span data-stu-id="1eabc-178">Conference</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1eabc-179"><strong>Categoria da sessão</strong></span><span class="sxs-lookup"><span data-stu-id="1eabc-179"><strong>Session category</strong></span></span></p></td>
<td><p><span data-ttu-id="1eabc-p111">Indica se a atividade em questão teve sucesso ou falhou. Selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="1eabc-p111">Indicates whether the activity in question succeeded or failed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="1eabc-182">Todos os</span><span class="sxs-lookup"><span data-stu-id="1eabc-182">[All]</span></span></p></li>
<li><p><span data-ttu-id="1eabc-183">Sucesso</span><span class="sxs-lookup"><span data-stu-id="1eabc-183">Success</span></span></p></li>
<li><p><span data-ttu-id="1eabc-184">Falha esperada</span><span class="sxs-lookup"><span data-stu-id="1eabc-184">Expected failure</span></span></p></li>
<li><p><span data-ttu-id="1eabc-185">Falha inesperada</span><span class="sxs-lookup"><span data-stu-id="1eabc-185">Unexpected failure</span></span></p></li>
</ul>
<p><span data-ttu-id="1eabc-186">Uma &quot; falha esperada &quot; é uma falha que deve ocorrer.</span><span class="sxs-lookup"><span data-stu-id="1eabc-186">An &quot;expected failure&quot; is a failure that is expected to happen.</span></span> <span data-ttu-id="1eabc-187">Por exemplo, se um usuário configurou seu status para Não Perturbe, é previsto que qualquer chamada para ele irá falhar.</span><span class="sxs-lookup"><span data-stu-id="1eabc-187">For example, if a user has set his or her status to Do Not Disturb you would expect any call to that user to fail.</span></span> <span data-ttu-id="1eabc-188">Uma &quot; falha inesperada &quot; é uma falha que ocorre no que parece ser um sistema saudável de outra forma.</span><span class="sxs-lookup"><span data-stu-id="1eabc-188">An &quot;unexpected failure&quot; is a failure that occurs in what would appear to be an otherwise healthy system.</span></span> <span data-ttu-id="1eabc-189">Por exemplo, uma chamada não deveria ser terminada se o chamador for colocado em espera.</span><span class="sxs-lookup"><span data-stu-id="1eabc-189">For example, a call should not be terminated if the caller is placed on hold.</span></span> <span data-ttu-id="1eabc-190">Se isso ocorrer, será sinalizado como uma falha inesperada.</span><span class="sxs-lookup"><span data-stu-id="1eabc-190">If that occurs, that would be flagged as an unexpected failure.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1eabc-191"><strong>ID diagnóstico</strong></span><span class="sxs-lookup"><span data-stu-id="1eabc-191"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="1eabc-p113">Identificador exclusivo (na forma de um cabeçalho de diagnóstico-ms) anexado a uma mensagem SIP que fornece informações úteis sobre os erros de solução de problemas. Os cabeçalhos diagnósticos são opcionais (é possível ter sessões SIP que não os incluem), e os IDs diagnósticos são relatados somente para as sessões com algum tipo de problema.</span><span class="sxs-lookup"><span data-stu-id="1eabc-p113">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors. Diagnostics headers are optional (it is possible to have SIP sessions that do not include these headers), and diagnostic IDs are reported only for sessions that experienced problems of some kind.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-diagnostic-reasons"></a><span data-ttu-id="1eabc-194">Métricas para os principais motivos diagnósticos</span><span class="sxs-lookup"><span data-stu-id="1eabc-194">Metrics for Top Diagnostic Reasons</span></span>

<span data-ttu-id="1eabc-195">A tabela a seguir lista as informações fornecidas no Relatório de Falha de Distribuição, com base no ID diagnóstico relatado com mais frequência.</span><span class="sxs-lookup"><span data-stu-id="1eabc-195">The following table lists the information provided in the Failure Distribution Report based on the most frequently reported diagnostic ID.</span></span>

### <a name="metrics-for-top-diagnostic-reasons"></a><span data-ttu-id="1eabc-196">Métricas para os principais motivos diagnósticos</span><span class="sxs-lookup"><span data-stu-id="1eabc-196">Metrics for Top Diagnostic Reasons</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1eabc-197">Nome</span><span class="sxs-lookup"><span data-stu-id="1eabc-197">Name</span></span></th>
<th><span data-ttu-id="1eabc-198">É possível classificar este item?</span><span class="sxs-lookup"><span data-stu-id="1eabc-198">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="1eabc-199">Descrição</span><span class="sxs-lookup"><span data-stu-id="1eabc-199">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1eabc-200"><strong>Rank</strong></span><span class="sxs-lookup"><span data-stu-id="1eabc-200"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="1eabc-201">Não</span><span class="sxs-lookup"><span data-stu-id="1eabc-201">No</span></span></p></td>
<td><p><span data-ttu-id="1eabc-p114">Classificação relativa das sessões com falha, com base no ID diagnóstico, que é um identificador exclusivo (na forma de um cabeçalho de diagnóstico-ms) anexado a uma mensagem SIP que fornece informações úteis sobre os erros de solução de problemas.</span><span class="sxs-lookup"><span data-stu-id="1eabc-p114">Relative ranking of failed sessions based on diagnostic IDs. The diagnostic ID is a unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1eabc-204"><strong>Principais motivos diagnósticos</strong></span><span class="sxs-lookup"><span data-stu-id="1eabc-204"><strong>Top diagnostic reasons</strong></span></span></p></td>
<td><p><span data-ttu-id="1eabc-205">Não</span><span class="sxs-lookup"><span data-stu-id="1eabc-205">No</span></span></p></td>
<td><p><span data-ttu-id="1eabc-206">ID diagnóstico gerado em uma sessão.</span><span class="sxs-lookup"><span data-stu-id="1eabc-206">Diagnostic ID generated in a session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1eabc-207"><strong>Sessões</strong></span><span class="sxs-lookup"><span data-stu-id="1eabc-207"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="1eabc-208">Não</span><span class="sxs-lookup"><span data-stu-id="1eabc-208">No</span></span></p></td>
<td><p><span data-ttu-id="1eabc-209">Número total de sessões com falha em que ID diagnóstico especificado foi gerado.</span><span class="sxs-lookup"><span data-stu-id="1eabc-209">Total number of failed sessions where the specified diagnostic ID was generated.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-modalities"></a><span data-ttu-id="1eabc-210">Métricas para as principais modalidades</span><span class="sxs-lookup"><span data-stu-id="1eabc-210">Metrics for Top Modalities</span></span>

<span data-ttu-id="1eabc-211">A tabela a seguir lista as informações fornecidas no Relatório de Falha de Distribuição, com base nas modalidades de sessão que apresentaram mais falhas.</span><span class="sxs-lookup"><span data-stu-id="1eabc-211">The following table lists the information provided in the Failure Distribution Report based on the session modalities that experienced the most failures.</span></span>

### <a name="metrics-for-top-modalities"></a><span data-ttu-id="1eabc-212">Métricas para as principais modalidades</span><span class="sxs-lookup"><span data-stu-id="1eabc-212">Metrics for Top Modalities</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1eabc-213">Nome</span><span class="sxs-lookup"><span data-stu-id="1eabc-213">Name</span></span></th>
<th><span data-ttu-id="1eabc-214">É possível classificar este item?</span><span class="sxs-lookup"><span data-stu-id="1eabc-214">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="1eabc-215">Descrição</span><span class="sxs-lookup"><span data-stu-id="1eabc-215">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1eabc-216"><strong>Rank</strong></span><span class="sxs-lookup"><span data-stu-id="1eabc-216"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="1eabc-217">Não</span><span class="sxs-lookup"><span data-stu-id="1eabc-217">No</span></span></p></td>
<td><p><span data-ttu-id="1eabc-218">Classificação relativa com base na sessão com falha baseada no tipo de sessão (por exemplo, conferência de áudio/vídeo ou sessão de transferência de arquivo ponto a ponto).</span><span class="sxs-lookup"><span data-stu-id="1eabc-218">Relative ranking based of failed session based on session type (for example, an audio/video conference or a peer-to-peer file transfer session).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1eabc-219"><strong>Principais modalidades</strong></span><span class="sxs-lookup"><span data-stu-id="1eabc-219"><strong>Top modalities</strong></span></span></p></td>
<td><p><span data-ttu-id="1eabc-220">Não</span><span class="sxs-lookup"><span data-stu-id="1eabc-220">No</span></span></p></td>
<td><p><span data-ttu-id="1eabc-221">Tipo de sessão.</span><span class="sxs-lookup"><span data-stu-id="1eabc-221">Session type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1eabc-222"><strong>Sessões</strong></span><span class="sxs-lookup"><span data-stu-id="1eabc-222"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="1eabc-223">Não</span><span class="sxs-lookup"><span data-stu-id="1eabc-223">No</span></span></p></td>
<td><p><span data-ttu-id="1eabc-224">Número total de sessões com falha envolvendo a modalidade especificada.</span><span class="sxs-lookup"><span data-stu-id="1eabc-224">Total number of failed sessions involving the specified modality.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-pools"></a><span data-ttu-id="1eabc-225">Métricas para os principais pools</span><span class="sxs-lookup"><span data-stu-id="1eabc-225">Metrics for Top Pools</span></span>

<span data-ttu-id="1eabc-226">A tabela a seguir lista as informações fornecidas no Relatório de Falha de Distribuição, com base nos pools que apresentaram mais falhas.</span><span class="sxs-lookup"><span data-stu-id="1eabc-226">The following table lists the information provided in the Failure Distribution Report based on the pools that experienced the most failures.</span></span>

### <a name="metrics-for-top-pools"></a><span data-ttu-id="1eabc-227">Métricas para os principais pools</span><span class="sxs-lookup"><span data-stu-id="1eabc-227">Metrics for Top Pools</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1eabc-228">Nome</span><span class="sxs-lookup"><span data-stu-id="1eabc-228">Name</span></span></th>
<th><span data-ttu-id="1eabc-229">É possível classificar este item?</span><span class="sxs-lookup"><span data-stu-id="1eabc-229">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="1eabc-230">Descrição</span><span class="sxs-lookup"><span data-stu-id="1eabc-230">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1eabc-231"><strong>Rank</strong></span><span class="sxs-lookup"><span data-stu-id="1eabc-231"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="1eabc-232">Não</span><span class="sxs-lookup"><span data-stu-id="1eabc-232">No</span></span></p></td>
<td><p><span data-ttu-id="1eabc-233">Classificação relativa de sessões com falha com base no pool de registradores ou no servidor de borda onde a sessão foi conduzida.</span><span class="sxs-lookup"><span data-stu-id="1eabc-233">Relative ranking of failed sessions based on the Registrar pool or Edge Server where the session was conducted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1eabc-234"><strong>Principais pools</strong></span><span class="sxs-lookup"><span data-stu-id="1eabc-234"><strong>Top pools</strong></span></span></p></td>
<td><p><span data-ttu-id="1eabc-235">Não</span><span class="sxs-lookup"><span data-stu-id="1eabc-235">No</span></span></p></td>
<td><p><span data-ttu-id="1eabc-236">Nome do pool de registradores ou servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="1eabc-236">Name of the Registrar pool or Edge Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1eabc-237"><strong>Sessões</strong></span><span class="sxs-lookup"><span data-stu-id="1eabc-237"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="1eabc-238">Não</span><span class="sxs-lookup"><span data-stu-id="1eabc-238">No</span></span></p></td>
<td><p><span data-ttu-id="1eabc-239">Número total de sessões com falha por pool de registradores ou servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="1eabc-239">Total number of failed sessions per Registrar pool or Edge Server.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-sources"></a><span data-ttu-id="1eabc-240">Métricas para as principais fontes</span><span class="sxs-lookup"><span data-stu-id="1eabc-240">Metrics for Top Sources</span></span>

<span data-ttu-id="1eabc-241">A tabela a seguir lista as informações fornecidas no Relatório de Falha de Distribuição, com base nos computadores que apresentaram mais falhas.</span><span class="sxs-lookup"><span data-stu-id="1eabc-241">The following table lists the information provided in the Failure Distribution Report based on the computers that experienced the most failures.</span></span>

### <a name="metrics-for-top-sources"></a><span data-ttu-id="1eabc-242">Métricas para as principais fontes</span><span class="sxs-lookup"><span data-stu-id="1eabc-242">Metrics for Top Sources</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1eabc-243">Nome</span><span class="sxs-lookup"><span data-stu-id="1eabc-243">Name</span></span></th>
<th><span data-ttu-id="1eabc-244">É possível classificar este item?</span><span class="sxs-lookup"><span data-stu-id="1eabc-244">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="1eabc-245">Descrição</span><span class="sxs-lookup"><span data-stu-id="1eabc-245">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1eabc-246"><strong>Rank</strong></span><span class="sxs-lookup"><span data-stu-id="1eabc-246"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="1eabc-247">Não</span><span class="sxs-lookup"><span data-stu-id="1eabc-247">No</span></span></p></td>
<td><p><span data-ttu-id="1eabc-248">Classificação relativa das sessões com falha por computador.</span><span class="sxs-lookup"><span data-stu-id="1eabc-248">Relative ranking failed sessions per computer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1eabc-249"><strong>Principais fontes</strong></span><span class="sxs-lookup"><span data-stu-id="1eabc-249"><strong>Top sources</strong></span></span></p></td>
<td><p><span data-ttu-id="1eabc-250">Não</span><span class="sxs-lookup"><span data-stu-id="1eabc-250">No</span></span></p></td>
<td><p><span data-ttu-id="1eabc-251">Nome do computador envolvido na sessão com falha.</span><span class="sxs-lookup"><span data-stu-id="1eabc-251">Name of the computer involved in the failed session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1eabc-252"><strong>Sessões</strong></span><span class="sxs-lookup"><span data-stu-id="1eabc-252"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="1eabc-253">Não</span><span class="sxs-lookup"><span data-stu-id="1eabc-253">No</span></span></p></td>
<td><p><span data-ttu-id="1eabc-254">Número total de sessões com falha por computador.</span><span class="sxs-lookup"><span data-stu-id="1eabc-254">Total number of failed sessions per computer.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-components"></a><span data-ttu-id="1eabc-255">Métricas para os principais componentes</span><span class="sxs-lookup"><span data-stu-id="1eabc-255">Metrics for Top Components</span></span>

<span data-ttu-id="1eabc-256">A tabela a seguir lista as informações fornecidas no relatório de falha de distribuição, com base nos componentes do Microsoft Lync Server 2010 que apresentaram mais falhas.</span><span class="sxs-lookup"><span data-stu-id="1eabc-256">The following table lists the information provided in the Failure Distribution Report based on the Microsoft Lync Server 2010 components that experienced the most failures.</span></span>

### <a name="metrics-for-top-components"></a><span data-ttu-id="1eabc-257">Métricas para os principais componentes</span><span class="sxs-lookup"><span data-stu-id="1eabc-257">Metrics for Top Components</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1eabc-258">Nome</span><span class="sxs-lookup"><span data-stu-id="1eabc-258">Name</span></span></th>
<th><span data-ttu-id="1eabc-259">É possível classificar este item?</span><span class="sxs-lookup"><span data-stu-id="1eabc-259">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="1eabc-260">Descrição</span><span class="sxs-lookup"><span data-stu-id="1eabc-260">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1eabc-261"><strong>Rank</strong></span><span class="sxs-lookup"><span data-stu-id="1eabc-261"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="1eabc-262">Não</span><span class="sxs-lookup"><span data-stu-id="1eabc-262">No</span></span></p></td>
<td><p><span data-ttu-id="1eabc-263">Classificação relativa de sessões com falha com base no componente do Lync Server 2010 (por exemplo, ExumRouting, GroupChat ou MediationServer).</span><span class="sxs-lookup"><span data-stu-id="1eabc-263">Relative ranking of failed sessions based on Lync Server 2010 component (for example, ExumRouting, GroupChat, or MediationServer).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1eabc-264"><strong>Principais componentes</strong></span><span class="sxs-lookup"><span data-stu-id="1eabc-264"><strong>Top components</strong></span></span></p></td>
<td><p><span data-ttu-id="1eabc-265">Não</span><span class="sxs-lookup"><span data-stu-id="1eabc-265">No</span></span></p></td>
<td><p><span data-ttu-id="1eabc-266">Nome do componente envolvido na sessão com falha.</span><span class="sxs-lookup"><span data-stu-id="1eabc-266">Name of the component involved in the failed session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1eabc-267"><strong>Sessões</strong></span><span class="sxs-lookup"><span data-stu-id="1eabc-267"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="1eabc-268">Não</span><span class="sxs-lookup"><span data-stu-id="1eabc-268">No</span></span></p></td>
<td><p><span data-ttu-id="1eabc-269">Número total de sessões com falha por componente.</span><span class="sxs-lookup"><span data-stu-id="1eabc-269">Total number of failed sessions per component.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-from-users"></a><span data-ttu-id="1eabc-270">Métricas para os principais usuários "De"</span><span class="sxs-lookup"><span data-stu-id="1eabc-270">Metrics for Top From Users</span></span>

<span data-ttu-id="1eabc-271">A tabela a seguir lista as informações fornecidas no Relatório de Falha de Distribuição, com base nos usuários que apresentaram mais falhas quando tentaram chamar alguém (conhecidos como usuários "De").</span><span class="sxs-lookup"><span data-stu-id="1eabc-271">The following table lists the information provided in the Failure Distribution Report based on users who experienced the most failures when they tried to call someone else (known as "From" users).</span></span>

### <a name="metrics-for-top-from-users"></a><span data-ttu-id="1eabc-272">Métricas para os principais usuários "Para"</span><span class="sxs-lookup"><span data-stu-id="1eabc-272">Metrics for Top From Users</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1eabc-273">Nome</span><span class="sxs-lookup"><span data-stu-id="1eabc-273">Name</span></span></th>
<th><span data-ttu-id="1eabc-274">É possível classificar este item?</span><span class="sxs-lookup"><span data-stu-id="1eabc-274">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="1eabc-275">Descrição</span><span class="sxs-lookup"><span data-stu-id="1eabc-275">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1eabc-276"><strong>Rank</strong></span><span class="sxs-lookup"><span data-stu-id="1eabc-276"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="1eabc-277">Não</span><span class="sxs-lookup"><span data-stu-id="1eabc-277">No</span></span></p></td>
<td><p><span data-ttu-id="1eabc-278">Classificação relativa das sessões com falha, com base no usuário convidado a entrar na sessão.</span><span class="sxs-lookup"><span data-stu-id="1eabc-278">Relative ranking of failed sessions based on the user who was invited to join the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1eabc-279"><strong>Principais usuários "Para"</strong></span><span class="sxs-lookup"><span data-stu-id="1eabc-279"><strong>Top from users</strong></span></span></p></td>
<td><p><span data-ttu-id="1eabc-280">Não</span><span class="sxs-lookup"><span data-stu-id="1eabc-280">No</span></span></p></td>
<td><p><span data-ttu-id="1eabc-281">Endereço SIP do usuário convidado para entrar na sessão.</span><span class="sxs-lookup"><span data-stu-id="1eabc-281">SIP address of the user invited to join the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1eabc-282"><strong>Sessões</strong></span><span class="sxs-lookup"><span data-stu-id="1eabc-282"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="1eabc-283">Não</span><span class="sxs-lookup"><span data-stu-id="1eabc-283">No</span></span></p></td>
<td><p><span data-ttu-id="1eabc-284">Número total de sessões com falha por usuário.</span><span class="sxs-lookup"><span data-stu-id="1eabc-284">Total number of failed sessions per user.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-to-users"></a><span data-ttu-id="1eabc-285">Métricas para os principais usuários</span><span class="sxs-lookup"><span data-stu-id="1eabc-285">Metrics for Top To Users</span></span>

<span data-ttu-id="1eabc-286">A tabela a seguir lista as informações fornecidas no Relatório de Falha de Distribuição, com base nos usuários que apresentaram mais falhas quando o outro usuário tentou chamá-los (conhecidos como usuários "Para").</span><span class="sxs-lookup"><span data-stu-id="1eabc-286">The following table lists the information provided in the Failure Distribution Report based on the users who experienced the most failures when another user tried to call them (known as "To" users).</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1eabc-287">Nome</span><span class="sxs-lookup"><span data-stu-id="1eabc-287">Name</span></span></th>
<th><span data-ttu-id="1eabc-288">É possível classificar este item?</span><span class="sxs-lookup"><span data-stu-id="1eabc-288">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="1eabc-289">Descrição</span><span class="sxs-lookup"><span data-stu-id="1eabc-289">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1eabc-290"><strong>Rank</strong></span><span class="sxs-lookup"><span data-stu-id="1eabc-290"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="1eabc-291">Não</span><span class="sxs-lookup"><span data-stu-id="1eabc-291">No</span></span></p></td>
<td><p><span data-ttu-id="1eabc-292">Classificação relativa das sessões com falha, com base no usuário que iniciou a sessão.</span><span class="sxs-lookup"><span data-stu-id="1eabc-292">Relative ranking of failed sessions based on the user who initiated the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1eabc-293"><strong>Principais usuários "Para"</strong></span><span class="sxs-lookup"><span data-stu-id="1eabc-293"><strong>Top to users</strong></span></span></p></td>
<td><p><span data-ttu-id="1eabc-294">Não</span><span class="sxs-lookup"><span data-stu-id="1eabc-294">No</span></span></p></td>
<td><p><span data-ttu-id="1eabc-295">Endereço SIP do usuário que iniciou a sessão.</span><span class="sxs-lookup"><span data-stu-id="1eabc-295">SIP address of the user who initiated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1eabc-296"><strong>Sessões</strong></span><span class="sxs-lookup"><span data-stu-id="1eabc-296"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="1eabc-297">Não</span><span class="sxs-lookup"><span data-stu-id="1eabc-297">No</span></span></p></td>
<td><p><span data-ttu-id="1eabc-298">Número total de sessões com falha por usuário.</span><span class="sxs-lookup"><span data-stu-id="1eabc-298">Total number of failed sessions per user.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-user-agents"></a><span data-ttu-id="1eabc-299">Métricas para os principais agentes do usuário</span><span class="sxs-lookup"><span data-stu-id="1eabc-299">Metrics for Top User Agents</span></span>

<span data-ttu-id="1eabc-300">A tabela a seguir lista as informações fornecidas no Relatório de Falha de Distribuição, com base no software de ponto de extremidade que apresentou mais falhas.</span><span class="sxs-lookup"><span data-stu-id="1eabc-300">The following table lists the information provided in the Failure Distribution Report based on the endpoint software that experienced the most failures.</span></span>

### <a name="metrics-for-top-user-agents"></a><span data-ttu-id="1eabc-301">Métricas para os principais agentes do usuário</span><span class="sxs-lookup"><span data-stu-id="1eabc-301">Metrics for Top User Agents</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1eabc-302">Nome</span><span class="sxs-lookup"><span data-stu-id="1eabc-302">Name</span></span></th>
<th><span data-ttu-id="1eabc-303">É possível classificar este item?</span><span class="sxs-lookup"><span data-stu-id="1eabc-303">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="1eabc-304">Descrição</span><span class="sxs-lookup"><span data-stu-id="1eabc-304">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1eabc-305"><strong>Rank</strong></span><span class="sxs-lookup"><span data-stu-id="1eabc-305"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="1eabc-306">Não</span><span class="sxs-lookup"><span data-stu-id="1eabc-306">No</span></span></p></td>
<td><p><span data-ttu-id="1eabc-p115">Classificação relativa de sessões com falha, com base no agente do usuário (software) envolvido na sessão. Por exemplo: RTCC/4.0.0.0 Inbound Routing/4.0.0.0.</span><span class="sxs-lookup"><span data-stu-id="1eabc-p115">Relative ranking of failed sessions based on the user agent (software) involved in the session. For example: RTCC/4.0.0.0 Inbound Routing/4.0.0.0.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1eabc-309"><strong>Principais agentes do usuário</strong></span><span class="sxs-lookup"><span data-stu-id="1eabc-309"><strong>Top user agents</strong></span></span></p></td>
<td><p><span data-ttu-id="1eabc-310">Não</span><span class="sxs-lookup"><span data-stu-id="1eabc-310">No</span></span></p></td>
<td><p><span data-ttu-id="1eabc-311">Nome do agente do usuário envolvido na sessão com falha.</span><span class="sxs-lookup"><span data-stu-id="1eabc-311">Name of the user agent involved in the failed session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1eabc-312"><strong>Sessões</strong></span><span class="sxs-lookup"><span data-stu-id="1eabc-312"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="1eabc-313">Não</span><span class="sxs-lookup"><span data-stu-id="1eabc-313">No</span></span></p></td>
<td><p><span data-ttu-id="1eabc-314">Número total de sessões com falha por agente do usuário.</span><span class="sxs-lookup"><span data-stu-id="1eabc-314">Total number of failed sessions per user agent.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

