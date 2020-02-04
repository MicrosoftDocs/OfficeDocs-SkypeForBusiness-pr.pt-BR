---
title: 'Lync Server 2013: relatório de distribuição de falha'
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
ms.openlocfilehash: 5250b03aef3fb77de2cbeefa4688a150c9b4a302
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765169"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failure-distribution-report-in-lync-server-2013"></a><span data-ttu-id="fef3c-102">Relatório de distribuição de falha no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fef3c-102">Failure Distribution Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fef3c-103">_**Tópico da última modificação:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="fef3c-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="fef3c-104">O Relatório de Distribuição de Falhas classifica sessões com falha nas seguintes categorias:</span><span class="sxs-lookup"><span data-stu-id="fef3c-104">The Failure Distribution Report ranks failed sessions in the following categories:</span></span>

  - <span data-ttu-id="fef3c-105">Principais motivos diagnósticos</span><span class="sxs-lookup"><span data-stu-id="fef3c-105">Top diagnostic reasons</span></span>

  - <span data-ttu-id="fef3c-106">Principais modalidades</span><span class="sxs-lookup"><span data-stu-id="fef3c-106">Top modalities</span></span>

  - <span data-ttu-id="fef3c-107">Principais pools</span><span class="sxs-lookup"><span data-stu-id="fef3c-107">Top pools</span></span>

  - <span data-ttu-id="fef3c-108">Principais fontes</span><span class="sxs-lookup"><span data-stu-id="fef3c-108">Top sources</span></span>

  - <span data-ttu-id="fef3c-109">Principais componentes</span><span class="sxs-lookup"><span data-stu-id="fef3c-109">Top components</span></span>

  - <span data-ttu-id="fef3c-110">Principais usuários "De"</span><span class="sxs-lookup"><span data-stu-id="fef3c-110">Top from users</span></span>

  - <span data-ttu-id="fef3c-111">Principais usuários "Para"</span><span class="sxs-lookup"><span data-stu-id="fef3c-111">Top to users</span></span>

  - <span data-ttu-id="fef3c-112">Principais agentes do usuário "De"</span><span class="sxs-lookup"><span data-stu-id="fef3c-112">Top from user agents</span></span>

<span data-ttu-id="fef3c-p101">É possível usar essas categorias para determinar exatamente onde está ocorrendo um problema e, em alguns casos, porque o problema está ocorrendo. Por exemplo, suponha que você tenha registrado 242 sessões de áudio/vídeo com falha durante um determinado dia. Se você observar o Relatório de Distribuição de Falhas, ele poderá mostrar que 237 das sessões com falha ocorreram no pool de Dublin. Isso fornece um ótimo ponto inicial para rastrear e diagnosticar as causas por trás dessas falhas. Se você clicar no pool de Dublin na categoria **Principais pools**, você verá um Relatório de Distribuição de Falhas exclusivo desse pool. Será possível então começar a analisar por que o pool de Dublin enfrentou tantas dificuldades.</span><span class="sxs-lookup"><span data-stu-id="fef3c-p101">You can use these categories to determine exactly where a problem is occurring and, in some cases, why the problem is occurring. For example, suppose you recorded 242 failed audio/video sessions during a given day. If you look at the Failure Distribution Report, it might show that 237 of those failed sessions took place in your Dublin pool. That gives you a good place to start when it comes to tracking down and diagnosing the causes behind those failures. If you click on the Dublin pool under the **Top pools** category, you will see a Failure Distribution Report just for that pool. You can then begin analyzing why the Dublin pool was experiencing so many difficulties.</span></span>

<div>

## <a name="viewing-the-failure-distribution-report"></a><span data-ttu-id="fef3c-119">Exibindo o Relatório de Distribuição de Falhas</span><span class="sxs-lookup"><span data-stu-id="fef3c-119">Viewing the Failure Distribution Report</span></span>

<span data-ttu-id="fef3c-120">É possível acessar o Relatório de Distribuição de Falhas a partir de qualquer um dos seguintes relatórios clicando nas medidas **Volume de falhas esperado** ou **Volume de falhas não esperado**:</span><span class="sxs-lookup"><span data-stu-id="fef3c-120">You can access the Failure Distribution Report from any of the following reports by clicking either the **Expected failure volume** or the **Unexpected failure volume** metric:</span></span>

  - [<span data-ttu-id="fef3c-121">Relatório de falhas principais no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fef3c-121">Top Failures Report in Lync Server 2013</span></span>](lync-server-2013-top-failures-report.md)

  - [<span data-ttu-id="fef3c-122">Relatório de diagnóstico de conferência no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fef3c-122">Conference Diagnostic Report in Lync Server 2013</span></span>](lync-server-2013-conference-diagnostic-report.md)

  - [<span data-ttu-id="fef3c-123">Relatório de diagnóstico de atividade ponto a ponto no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fef3c-123">Peer-to-Peer Activity Diagnostic Report in Lync Server 2013</span></span>](lync-server-2013-peer-to-peer-activity-diagnostic-report.md)

<span data-ttu-id="fef3c-124">No relatório de distribuição de falha, você pode clicar em qualquer uma das seguintes métricas para exibir o [relatório de lista de falhas no Lync Server 2013](lync-server-2013-failure-list-report.md):</span><span class="sxs-lookup"><span data-stu-id="fef3c-124">From the Failure Distribution Report, you can click any of the following metrics to view the [Failure List Report in Lync Server 2013](lync-server-2013-failure-list-report.md):</span></span>

  - <span data-ttu-id="fef3c-125">Principais motivos diagnósticos (sessões)</span><span class="sxs-lookup"><span data-stu-id="fef3c-125">Top diagnostic reasons (sessions)</span></span>

  - <span data-ttu-id="fef3c-126">Principais modalidades (sessões)</span><span class="sxs-lookup"><span data-stu-id="fef3c-126">Top modalities (sessions)</span></span>

  - <span data-ttu-id="fef3c-127">Principais pools (sessões)</span><span class="sxs-lookup"><span data-stu-id="fef3c-127">Top pools (sessions)</span></span>

  - <span data-ttu-id="fef3c-128">Principais fontes (sessões)</span><span class="sxs-lookup"><span data-stu-id="fef3c-128">Top sources (sessions)</span></span>

  - <span data-ttu-id="fef3c-129">Principais componentes (sessões)</span><span class="sxs-lookup"><span data-stu-id="fef3c-129">Top components (sessions)</span></span>

  - <span data-ttu-id="fef3c-130">Principais usuários "De" (sessões)</span><span class="sxs-lookup"><span data-stu-id="fef3c-130">Top from users (sessions)</span></span>

  - <span data-ttu-id="fef3c-131">Principais usuários "Para" (sessões)</span><span class="sxs-lookup"><span data-stu-id="fef3c-131">Top to users (sessions)</span></span>

  - <span data-ttu-id="fef3c-132">Principais agentes do usuários "De" (sessões)</span><span class="sxs-lookup"><span data-stu-id="fef3c-132">Top from user agents (sessions)</span></span>

</div>

<div>

## <a name="using-the-failure-distribution-report"></a><span data-ttu-id="fef3c-133">Usando o Relatório de Distribuição de Falhas</span><span class="sxs-lookup"><span data-stu-id="fef3c-133">Using the Failure Distribution Report</span></span>

<span data-ttu-id="fef3c-p102">Dependendo do tamanho de seu monitor e da resolução da tela, é possível que alguns dos dados apresentados no Relatório de Distribuição de Falhas sejam truncados que exibidos na tela. Por exemplo, um agente de usuário com o nome "UCCAPI/4.0.7400.0 OC/4.0.7400.0 (Microsoft Lync 2013)" poderá aparecer apenas parcialmente na tela:</span><span class="sxs-lookup"><span data-stu-id="fef3c-p102">Depending on your monitor size and screen resolution, it's possible that some of the data shown in the Failure Distribution Report might be truncated when you view it onscreen. This is especially true for metrics such as user agents, which can have very long labels. For example, a user agent with a name like "UCCAPI/4.0.7400.0 OC/4.0.7400.0 (Microsoft Lync 2013)" might only partially appear onscreen:</span></span>

<span data-ttu-id="fef3c-137">UCCAPI/4.0.7400.0 OC/4.0.7400.0 (Microsoft Ly...</span><span class="sxs-lookup"><span data-stu-id="fef3c-137">UCCAPI/4.0.7400.0 OC/4.0.7400.0 (Microsoft Ly...</span></span>

<span data-ttu-id="fef3c-138">Felizmente, é possível ver o nome completo mantendo o mouse sobre o valor truncado.</span><span class="sxs-lookup"><span data-stu-id="fef3c-138">Fortunately, you can see the entire label simply by holding your mouse over the truncated value.</span></span>

<span data-ttu-id="fef3c-p103">Um medida interessante que pode ser filtrada usando o Relatório de Distribuição de Falhas é o ID do diagnóstico. Se vir o mesmo ID do diagnóstico surgir em outros relatórios, será possível filtrar esse ID no Relatório de Distribuição de Falhas e obter uma visão bastante detalhada de exatamente onde e com que frequência esse ID foi reportado durante uma sessão com falha.</span><span class="sxs-lookup"><span data-stu-id="fef3c-p103">One interesting metric that you can filter on by using the Failure Distribution Report is Diagnostic ID. If you see the same Diagnostic ID cropping up in other reports you can filter on that ID in the Failure Distribution Report and get a very detailed look at exactly where, and how often, that ID has been reported during a failed session.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="fef3c-141">Filtros</span><span class="sxs-lookup"><span data-stu-id="fef3c-141">Filters</span></span>

<span data-ttu-id="fef3c-p104">O filtro é uma maneira de retornar um conjunto de dados mais refinado e direcionado, ou ver os dados retornados de maneiras diferentes. Por exemplo, o Relatório de Falha na Distribuição permite filtrar itens como tipo de atividade (sessão ponto a ponto ou de conferência) ou pelo ID diagnóstico que acompanha cada sessão com falha.</span><span class="sxs-lookup"><span data-stu-id="fef3c-p104">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Failed Distribution Report enables you to filter on such things as the activity type (peer-to-peer session or conferencing session) or by the diagnostic ID that accompanied each failed session.</span></span>

<span data-ttu-id="fef3c-144">A tabela a seguir lista os filtros que você pode usar com o Relatório de Falha na Distribuição.</span><span class="sxs-lookup"><span data-stu-id="fef3c-144">The following table lists the filters that you can use with the Failure Distribution Report.</span></span>

### <a name="failure-distribution-report-filters"></a><span data-ttu-id="fef3c-145">Filtros do Relatório de Falha na Distribuição</span><span class="sxs-lookup"><span data-stu-id="fef3c-145">Failure Distribution Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fef3c-146">Nome</span><span class="sxs-lookup"><span data-stu-id="fef3c-146">Name</span></span></th>
<th><span data-ttu-id="fef3c-147">Descrição</span><span class="sxs-lookup"><span data-stu-id="fef3c-147">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fef3c-148"><strong>De</strong></span><span class="sxs-lookup"><span data-stu-id="fef3c-148"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="fef3c-p105">Data/hora de início para o intervalo de tempo. Para ver os dados por horas, insira a data e hora de início conforme segue:</span><span class="sxs-lookup"><span data-stu-id="fef3c-p105">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="fef3c-151">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="fef3c-151">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="fef3c-p106">Se você não inserir a hora de início, o relatório começará automaticamente à meia-noite do dia especificado. Para ver os dados por dia, insira somente a data:</span><span class="sxs-lookup"><span data-stu-id="fef3c-p106">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="fef3c-154">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="fef3c-154">7/7/2012</span></span></p>
<p><span data-ttu-id="fef3c-155">Para exibir por semana ou mês, insira uma data dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):</span><span class="sxs-lookup"><span data-stu-id="fef3c-155">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="fef3c-156">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="fef3c-156">7/3/2012</span></span></p>
<p><span data-ttu-id="fef3c-157">As semanas sempre vão de domingo a sábado.</span><span class="sxs-lookup"><span data-stu-id="fef3c-157">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fef3c-158"><strong>Até</strong></span><span class="sxs-lookup"><span data-stu-id="fef3c-158"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="fef3c-p107">Data/hora final de intervalo de tempo. Para ver os dados por horas, insira a data e hora final conforme segue:</span><span class="sxs-lookup"><span data-stu-id="fef3c-p107">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="fef3c-161">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="fef3c-161">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="fef3c-p108">Se você não inserir a hora final, o relatório terminará automaticamente à meia-noite do dia especificado. Para ver os dados por dia, insira somente a data:</span><span class="sxs-lookup"><span data-stu-id="fef3c-p108">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="fef3c-164">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="fef3c-164">7/7/2012</span></span></p>
<p><span data-ttu-id="fef3c-165">Para exibir por semana ou mês, insira uma data dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):</span><span class="sxs-lookup"><span data-stu-id="fef3c-165">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="fef3c-166">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="fef3c-166">7/3/2012</span></span></p>
<p><span data-ttu-id="fef3c-167">As semanas sempre vão de domingo a sábado.</span><span class="sxs-lookup"><span data-stu-id="fef3c-167">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fef3c-168"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="fef3c-168"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="fef3c-p109">FQDN (Nome de domínio totalmente qualificado) do Pool de registradores ou Servidor de Borda. Você pode selecionar um pool individual ou clicar em <strong>[Todos]</strong> para ver os dados de todos os pools. Essa lista suspensa é automaticamente preenchida para você com base nos registros no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="fef3c-p109">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fef3c-172"><strong>Tipo de atividade</strong></span><span class="sxs-lookup"><span data-stu-id="fef3c-172"><strong>Activity type</strong></span></span></p></td>
<td><p><span data-ttu-id="fef3c-p110">Tipo de atividade para filtrar. Selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="fef3c-p110">Type of activity to filter on. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="fef3c-175">[Todos]</span><span class="sxs-lookup"><span data-stu-id="fef3c-175">[All]</span></span></p></li>
<li><p><span data-ttu-id="fef3c-176">Ponto a ponto</span><span class="sxs-lookup"><span data-stu-id="fef3c-176">Peer-to-peer</span></span></p></li>
<li><p><span data-ttu-id="fef3c-177">Conferência</span><span class="sxs-lookup"><span data-stu-id="fef3c-177">Conference</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fef3c-178"><strong>Categoria da sessão</strong></span><span class="sxs-lookup"><span data-stu-id="fef3c-178"><strong>Session category</strong></span></span></p></td>
<td><p><span data-ttu-id="fef3c-p111">Indica se a atividade em questão teve sucesso ou falhou. Selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="fef3c-p111">Indicates whether the activity in question succeeded or failed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="fef3c-181">[Todos]</span><span class="sxs-lookup"><span data-stu-id="fef3c-181">[All]</span></span></p></li>
<li><p><span data-ttu-id="fef3c-182">Sucesso</span><span class="sxs-lookup"><span data-stu-id="fef3c-182">Success</span></span></p></li>
<li><p><span data-ttu-id="fef3c-183">Falha esperada</span><span class="sxs-lookup"><span data-stu-id="fef3c-183">Expected failure</span></span></p></li>
<li><p><span data-ttu-id="fef3c-184">Falha inesperada</span><span class="sxs-lookup"><span data-stu-id="fef3c-184">Unexpected failure</span></span></p></li>
</ul>
<p><span data-ttu-id="fef3c-185">Uma &quot;falha&quot; esperada é uma falha que espera acontecer.</span><span class="sxs-lookup"><span data-stu-id="fef3c-185">An &quot;expected failure&quot; is a failure that is expected to happen.</span></span> <span data-ttu-id="fef3c-186">Por exemplo, se um usuário tiver definido seu status como Não perturbe, é esperado que qualquer chamada para esse usuário falhe.</span><span class="sxs-lookup"><span data-stu-id="fef3c-186">For example, if a user has set his or her status to Do Not Disturb you would expect any call to that user to fail.</span></span> <span data-ttu-id="fef3c-187">Uma &quot;falha&quot; inesperada é uma falha que ocorre em que parece ser um sistema de outra forma saudável.</span><span class="sxs-lookup"><span data-stu-id="fef3c-187">An &quot;unexpected failure&quot; is a failure that occurs in what would appear to be an otherwise healthy system.</span></span> <span data-ttu-id="fef3c-188">Por exemplo, uma chamada não deve ser encerrada se o chamador for colocado em espera.</span><span class="sxs-lookup"><span data-stu-id="fef3c-188">For example, a call should not be terminated if the caller is placed on hold.</span></span> <span data-ttu-id="fef3c-189">Se isso ocorrer, isso seria sinalizado como uma falha inesperada.</span><span class="sxs-lookup"><span data-stu-id="fef3c-189">If that occurs, that would be flagged as an unexpected failure.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fef3c-190"><strong>ID do Diagnóstico</strong></span><span class="sxs-lookup"><span data-stu-id="fef3c-190"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="fef3c-p113">Identificador exclusivo (na forma de um cabeçalho de diagnóstico-ms) anexado a uma mensagem SIP que fornece informações úteis sobre os erros de solução de problemas. Os cabeçalhos diagnósticos são opcionais (é possível ter sessões SIP que não os incluem), e os IDs diagnósticos são relatados somente para as sessões com algum tipo de problema.</span><span class="sxs-lookup"><span data-stu-id="fef3c-p113">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors. Diagnostics headers are optional (it is possible to have SIP sessions that do not include these headers), and diagnostic IDs are reported only for sessions that experienced problems of some kind.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-diagnostic-reasons"></a><span data-ttu-id="fef3c-193">Métricas para os principais motivos diagnósticos</span><span class="sxs-lookup"><span data-stu-id="fef3c-193">Metrics for Top Diagnostic Reasons</span></span>

<span data-ttu-id="fef3c-194">A tabela a seguir lista as informações fornecidas no Relatório de Falha de Distribuição, com base no ID diagnóstico relatado com mais frequência.</span><span class="sxs-lookup"><span data-stu-id="fef3c-194">The following table lists the information provided in the Failure Distribution Report based on the most frequently reported diagnostic ID.</span></span>

### <a name="metrics-for-top-diagnostic-reasons"></a><span data-ttu-id="fef3c-195">Métricas para os principais motivos diagnósticos</span><span class="sxs-lookup"><span data-stu-id="fef3c-195">Metrics for Top Diagnostic Reasons</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fef3c-196">Nome</span><span class="sxs-lookup"><span data-stu-id="fef3c-196">Name</span></span></th>
<th><span data-ttu-id="fef3c-197">Você pode classificar este item?</span><span class="sxs-lookup"><span data-stu-id="fef3c-197">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="fef3c-198">Descrição</span><span class="sxs-lookup"><span data-stu-id="fef3c-198">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fef3c-199"><strong>Classificação</strong></span><span class="sxs-lookup"><span data-stu-id="fef3c-199"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="fef3c-200">Não</span><span class="sxs-lookup"><span data-stu-id="fef3c-200">No</span></span></p></td>
<td><p><span data-ttu-id="fef3c-p114">Classificação relativa das sessões com falha, com base no ID diagnóstico, que é um identificador exclusivo (na forma de um cabeçalho de diagnóstico-ms) anexado a uma mensagem SIP que fornece informações úteis sobre os erros de solução de problemas.</span><span class="sxs-lookup"><span data-stu-id="fef3c-p114">Relative ranking of failed sessions based on diagnostic IDs. The diagnostic ID is a unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fef3c-203"><strong>Principais motivos diagnósticos</strong></span><span class="sxs-lookup"><span data-stu-id="fef3c-203"><strong>Top diagnostic reasons</strong></span></span></p></td>
<td><p><span data-ttu-id="fef3c-204">Não</span><span class="sxs-lookup"><span data-stu-id="fef3c-204">No</span></span></p></td>
<td><p><span data-ttu-id="fef3c-205">ID diagnóstico gerado em uma sessão.</span><span class="sxs-lookup"><span data-stu-id="fef3c-205">Diagnostic ID generated in a session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fef3c-206"><strong>Sessões</strong></span><span class="sxs-lookup"><span data-stu-id="fef3c-206"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="fef3c-207">Não</span><span class="sxs-lookup"><span data-stu-id="fef3c-207">No</span></span></p></td>
<td><p><span data-ttu-id="fef3c-208">Número total de sessões com falha em que ID diagnóstico especificado foi gerado.</span><span class="sxs-lookup"><span data-stu-id="fef3c-208">Total number of failed sessions where the specified diagnostic ID was generated.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-modalities"></a><span data-ttu-id="fef3c-209">Métricas para as principais modalidades</span><span class="sxs-lookup"><span data-stu-id="fef3c-209">Metrics for Top Modalities</span></span>

<span data-ttu-id="fef3c-210">A tabela a seguir lista as informações fornecidas no Relatório de Falha de Distribuição, com base nas modalidades de sessão que apresentaram mais falhas.</span><span class="sxs-lookup"><span data-stu-id="fef3c-210">The following table lists the information provided in the Failure Distribution Report based on the session modalities that experienced the most failures.</span></span>

### <a name="metrics-for-top-modalities"></a><span data-ttu-id="fef3c-211">Métricas para as principais modalidades</span><span class="sxs-lookup"><span data-stu-id="fef3c-211">Metrics for Top Modalities</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fef3c-212">Nome</span><span class="sxs-lookup"><span data-stu-id="fef3c-212">Name</span></span></th>
<th><span data-ttu-id="fef3c-213">Você pode classificar este item?</span><span class="sxs-lookup"><span data-stu-id="fef3c-213">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="fef3c-214">Descrição</span><span class="sxs-lookup"><span data-stu-id="fef3c-214">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fef3c-215"><strong>Classificação</strong></span><span class="sxs-lookup"><span data-stu-id="fef3c-215"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="fef3c-216">Não</span><span class="sxs-lookup"><span data-stu-id="fef3c-216">No</span></span></p></td>
<td><p><span data-ttu-id="fef3c-217">Classificação relativa com base na sessão com falha baseada no tipo de sessão (por exemplo, conferência de áudio/vídeo ou sessão de transferência de arquivo ponto a ponto).</span><span class="sxs-lookup"><span data-stu-id="fef3c-217">Relative ranking based of failed session based on session type (for example, an audio/video conference or a peer-to-peer file transfer session).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fef3c-218"><strong>Principais modalidades</strong></span><span class="sxs-lookup"><span data-stu-id="fef3c-218"><strong>Top modalities</strong></span></span></p></td>
<td><p><span data-ttu-id="fef3c-219">Não</span><span class="sxs-lookup"><span data-stu-id="fef3c-219">No</span></span></p></td>
<td><p><span data-ttu-id="fef3c-220">Tipo de sessão.</span><span class="sxs-lookup"><span data-stu-id="fef3c-220">Session type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fef3c-221"><strong>Sessões</strong></span><span class="sxs-lookup"><span data-stu-id="fef3c-221"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="fef3c-222">Não</span><span class="sxs-lookup"><span data-stu-id="fef3c-222">No</span></span></p></td>
<td><p><span data-ttu-id="fef3c-223">Número total de sessões com falha envolvendo a modalidade especificada.</span><span class="sxs-lookup"><span data-stu-id="fef3c-223">Total number of failed sessions involving the specified modality.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-pools"></a><span data-ttu-id="fef3c-224">Métricas para os principais pools</span><span class="sxs-lookup"><span data-stu-id="fef3c-224">Metrics for Top Pools</span></span>

<span data-ttu-id="fef3c-225">A tabela a seguir lista as informações fornecidas no Relatório de Falha de Distribuição, com base nos pools que apresentaram mais falhas.</span><span class="sxs-lookup"><span data-stu-id="fef3c-225">The following table lists the information provided in the Failure Distribution Report based on the pools that experienced the most failures.</span></span>

### <a name="metrics-for-top-pools"></a><span data-ttu-id="fef3c-226">Métricas para os principais pools</span><span class="sxs-lookup"><span data-stu-id="fef3c-226">Metrics for Top Pools</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fef3c-227">Nome</span><span class="sxs-lookup"><span data-stu-id="fef3c-227">Name</span></span></th>
<th><span data-ttu-id="fef3c-228">Você pode classificar este item?</span><span class="sxs-lookup"><span data-stu-id="fef3c-228">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="fef3c-229">Descrição</span><span class="sxs-lookup"><span data-stu-id="fef3c-229">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fef3c-230"><strong>Classificação</strong></span><span class="sxs-lookup"><span data-stu-id="fef3c-230"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="fef3c-231">Não</span><span class="sxs-lookup"><span data-stu-id="fef3c-231">No</span></span></p></td>
<td><p><span data-ttu-id="fef3c-232">Classificação relativa de sessões com falha com base no pool de registradores ou no servidor de borda em que a sessão foi conduzida.</span><span class="sxs-lookup"><span data-stu-id="fef3c-232">Relative ranking of failed sessions based on the Registrar pool or Edge Server where the session was conducted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fef3c-233"><strong>Principais pools</strong></span><span class="sxs-lookup"><span data-stu-id="fef3c-233"><strong>Top pools</strong></span></span></p></td>
<td><p><span data-ttu-id="fef3c-234">Não</span><span class="sxs-lookup"><span data-stu-id="fef3c-234">No</span></span></p></td>
<td><p><span data-ttu-id="fef3c-235">Nome do pool de registradores ou servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="fef3c-235">Name of the Registrar pool or Edge Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fef3c-236"><strong>Sessões</strong></span><span class="sxs-lookup"><span data-stu-id="fef3c-236"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="fef3c-237">Não</span><span class="sxs-lookup"><span data-stu-id="fef3c-237">No</span></span></p></td>
<td><p><span data-ttu-id="fef3c-238">Número total de sessões com falha por pool de registradores ou servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="fef3c-238">Total number of failed sessions per Registrar pool or Edge Server.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-sources"></a><span data-ttu-id="fef3c-239">Métricas para as principais fontes</span><span class="sxs-lookup"><span data-stu-id="fef3c-239">Metrics for Top Sources</span></span>

<span data-ttu-id="fef3c-240">A tabela a seguir lista as informações fornecidas no Relatório de Falha de Distribuição, com base nos computadores que apresentaram mais falhas.</span><span class="sxs-lookup"><span data-stu-id="fef3c-240">The following table lists the information provided in the Failure Distribution Report based on the computers that experienced the most failures.</span></span>

### <a name="metrics-for-top-sources"></a><span data-ttu-id="fef3c-241">Métricas para as principais fontes</span><span class="sxs-lookup"><span data-stu-id="fef3c-241">Metrics for Top Sources</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fef3c-242">Nome</span><span class="sxs-lookup"><span data-stu-id="fef3c-242">Name</span></span></th>
<th><span data-ttu-id="fef3c-243">Você pode classificar este item?</span><span class="sxs-lookup"><span data-stu-id="fef3c-243">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="fef3c-244">Descrição</span><span class="sxs-lookup"><span data-stu-id="fef3c-244">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fef3c-245"><strong>Classificação</strong></span><span class="sxs-lookup"><span data-stu-id="fef3c-245"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="fef3c-246">Não</span><span class="sxs-lookup"><span data-stu-id="fef3c-246">No</span></span></p></td>
<td><p><span data-ttu-id="fef3c-247">Classificação relativa das sessões com falha por computador.</span><span class="sxs-lookup"><span data-stu-id="fef3c-247">Relative ranking failed sessions per computer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fef3c-248"><strong>Principais fontes</strong></span><span class="sxs-lookup"><span data-stu-id="fef3c-248"><strong>Top sources</strong></span></span></p></td>
<td><p><span data-ttu-id="fef3c-249">Não</span><span class="sxs-lookup"><span data-stu-id="fef3c-249">No</span></span></p></td>
<td><p><span data-ttu-id="fef3c-250">Nome do computador envolvido na sessão com falha.</span><span class="sxs-lookup"><span data-stu-id="fef3c-250">Name of the computer involved in the failed session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fef3c-251"><strong>Sessões</strong></span><span class="sxs-lookup"><span data-stu-id="fef3c-251"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="fef3c-252">Não</span><span class="sxs-lookup"><span data-stu-id="fef3c-252">No</span></span></p></td>
<td><p><span data-ttu-id="fef3c-253">Número total de sessões com falha por computador.</span><span class="sxs-lookup"><span data-stu-id="fef3c-253">Total number of failed sessions per computer.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-components"></a><span data-ttu-id="fef3c-254">Métricas para os principais componentes</span><span class="sxs-lookup"><span data-stu-id="fef3c-254">Metrics for Top Components</span></span>

<span data-ttu-id="fef3c-255">A tabela a seguir lista as informações fornecidas no relatório de distribuição de falha com base nos componentes do Microsoft Lync Server 2010 que tiveram mais falhas.</span><span class="sxs-lookup"><span data-stu-id="fef3c-255">The following table lists the information provided in the Failure Distribution Report based on the Microsoft Lync Server 2010 components that experienced the most failures.</span></span>

### <a name="metrics-for-top-components"></a><span data-ttu-id="fef3c-256">Métricas para os principais componentes</span><span class="sxs-lookup"><span data-stu-id="fef3c-256">Metrics for Top Components</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fef3c-257">Nome</span><span class="sxs-lookup"><span data-stu-id="fef3c-257">Name</span></span></th>
<th><span data-ttu-id="fef3c-258">Você pode classificar este item?</span><span class="sxs-lookup"><span data-stu-id="fef3c-258">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="fef3c-259">Descrição</span><span class="sxs-lookup"><span data-stu-id="fef3c-259">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fef3c-260"><strong>Classificação</strong></span><span class="sxs-lookup"><span data-stu-id="fef3c-260"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="fef3c-261">Não</span><span class="sxs-lookup"><span data-stu-id="fef3c-261">No</span></span></p></td>
<td><p><span data-ttu-id="fef3c-262">Classificação relativa de sessões com falha com base no componente do Lync Server 2010 (por exemplo, ExumRouting, GroupChat ou MediationServer).</span><span class="sxs-lookup"><span data-stu-id="fef3c-262">Relative ranking of failed sessions based on Lync Server 2010 component (for example, ExumRouting, GroupChat, or MediationServer).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fef3c-263"><strong>Principais componentes</strong></span><span class="sxs-lookup"><span data-stu-id="fef3c-263"><strong>Top components</strong></span></span></p></td>
<td><p><span data-ttu-id="fef3c-264">Não</span><span class="sxs-lookup"><span data-stu-id="fef3c-264">No</span></span></p></td>
<td><p><span data-ttu-id="fef3c-265">Nome do componente envolvido na sessão com falha.</span><span class="sxs-lookup"><span data-stu-id="fef3c-265">Name of the component involved in the failed session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fef3c-266"><strong>Sessões</strong></span><span class="sxs-lookup"><span data-stu-id="fef3c-266"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="fef3c-267">Não</span><span class="sxs-lookup"><span data-stu-id="fef3c-267">No</span></span></p></td>
<td><p><span data-ttu-id="fef3c-268">Número total de sessões com falha por componente.</span><span class="sxs-lookup"><span data-stu-id="fef3c-268">Total number of failed sessions per component.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-from-users"></a><span data-ttu-id="fef3c-269">Métricas para os principais usuários "Para"</span><span class="sxs-lookup"><span data-stu-id="fef3c-269">Metrics for Top From Users</span></span>

<span data-ttu-id="fef3c-270">A tabela a seguir lista as informações fornecidas no Relatório de Falha de Distribuição, com base nos usuários que apresentaram mais falhas quando tentaram chamar alguém (conhecidos como usuários "De").</span><span class="sxs-lookup"><span data-stu-id="fef3c-270">The following table lists the information provided in the Failure Distribution Report based on users who experienced the most failures when they tried to call someone else (known as "From" users).</span></span>

### <a name="metrics-for-top-from-users"></a><span data-ttu-id="fef3c-271">Métricas para os principais usuários "Para"</span><span class="sxs-lookup"><span data-stu-id="fef3c-271">Metrics for Top From Users</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fef3c-272">Nome</span><span class="sxs-lookup"><span data-stu-id="fef3c-272">Name</span></span></th>
<th><span data-ttu-id="fef3c-273">Você pode classificar este item?</span><span class="sxs-lookup"><span data-stu-id="fef3c-273">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="fef3c-274">Descrição</span><span class="sxs-lookup"><span data-stu-id="fef3c-274">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fef3c-275"><strong>Classificação</strong></span><span class="sxs-lookup"><span data-stu-id="fef3c-275"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="fef3c-276">Não</span><span class="sxs-lookup"><span data-stu-id="fef3c-276">No</span></span></p></td>
<td><p><span data-ttu-id="fef3c-277">Classificação relativa das sessões com falha, com base no usuário convidado a entrar na sessão.</span><span class="sxs-lookup"><span data-stu-id="fef3c-277">Relative ranking of failed sessions based on the user who was invited to join the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fef3c-278"><strong>Principais usuários "De"</strong></span><span class="sxs-lookup"><span data-stu-id="fef3c-278"><strong>Top from users</strong></span></span></p></td>
<td><p><span data-ttu-id="fef3c-279">Não</span><span class="sxs-lookup"><span data-stu-id="fef3c-279">No</span></span></p></td>
<td><p><span data-ttu-id="fef3c-280">Endereço SIP do usuário convidado para entrar na sessão.</span><span class="sxs-lookup"><span data-stu-id="fef3c-280">SIP address of the user invited to join the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fef3c-281"><strong>Sessões</strong></span><span class="sxs-lookup"><span data-stu-id="fef3c-281"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="fef3c-282">Não</span><span class="sxs-lookup"><span data-stu-id="fef3c-282">No</span></span></p></td>
<td><p><span data-ttu-id="fef3c-283">Número total de sessões com falha por usuário.</span><span class="sxs-lookup"><span data-stu-id="fef3c-283">Total number of failed sessions per user.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-to-users"></a><span data-ttu-id="fef3c-284">Métricas para os principais usuários</span><span class="sxs-lookup"><span data-stu-id="fef3c-284">Metrics for Top To Users</span></span>

<span data-ttu-id="fef3c-285">A tabela a seguir lista as informações fornecidas no Relatório de Falha de Distribuição, com base nos usuários que apresentaram mais falhas quando o outro usuário tentou chamá-los (conhecidos como usuários "Para").</span><span class="sxs-lookup"><span data-stu-id="fef3c-285">The following table lists the information provided in the Failure Distribution Report based on the users who experienced the most failures when another user tried to call them (known as "To" users).</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fef3c-286">Nome</span><span class="sxs-lookup"><span data-stu-id="fef3c-286">Name</span></span></th>
<th><span data-ttu-id="fef3c-287">Você pode classificar este item?</span><span class="sxs-lookup"><span data-stu-id="fef3c-287">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="fef3c-288">Descrição</span><span class="sxs-lookup"><span data-stu-id="fef3c-288">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fef3c-289"><strong>Classificação</strong></span><span class="sxs-lookup"><span data-stu-id="fef3c-289"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="fef3c-290">Não</span><span class="sxs-lookup"><span data-stu-id="fef3c-290">No</span></span></p></td>
<td><p><span data-ttu-id="fef3c-291">Classificação relativa das sessões com falha, com base no usuário que iniciou a sessão.</span><span class="sxs-lookup"><span data-stu-id="fef3c-291">Relative ranking of failed sessions based on the user who initiated the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fef3c-292"><strong>Principais usuários "Para"</strong></span><span class="sxs-lookup"><span data-stu-id="fef3c-292"><strong>Top to users</strong></span></span></p></td>
<td><p><span data-ttu-id="fef3c-293">Não</span><span class="sxs-lookup"><span data-stu-id="fef3c-293">No</span></span></p></td>
<td><p><span data-ttu-id="fef3c-294">Endereço SIP do usuário que iniciou a sessão.</span><span class="sxs-lookup"><span data-stu-id="fef3c-294">SIP address of the user who initiated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fef3c-295"><strong>Sessões</strong></span><span class="sxs-lookup"><span data-stu-id="fef3c-295"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="fef3c-296">Não</span><span class="sxs-lookup"><span data-stu-id="fef3c-296">No</span></span></p></td>
<td><p><span data-ttu-id="fef3c-297">Número total de sessões com falha por usuário.</span><span class="sxs-lookup"><span data-stu-id="fef3c-297">Total number of failed sessions per user.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-user-agents"></a><span data-ttu-id="fef3c-298">Métricas para os principais agentes do usuário</span><span class="sxs-lookup"><span data-stu-id="fef3c-298">Metrics for Top User Agents</span></span>

<span data-ttu-id="fef3c-299">A tabela a seguir lista as informações fornecidas no Relatório de Falha de Distribuição, com base no software de ponto de extremidade que apresentou mais falhas.</span><span class="sxs-lookup"><span data-stu-id="fef3c-299">The following table lists the information provided in the Failure Distribution Report based on the endpoint software that experienced the most failures.</span></span>

### <a name="metrics-for-top-user-agents"></a><span data-ttu-id="fef3c-300">Métricas para os principais agentes do usuário</span><span class="sxs-lookup"><span data-stu-id="fef3c-300">Metrics for Top User Agents</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fef3c-301">Nome</span><span class="sxs-lookup"><span data-stu-id="fef3c-301">Name</span></span></th>
<th><span data-ttu-id="fef3c-302">Você pode classificar este item?</span><span class="sxs-lookup"><span data-stu-id="fef3c-302">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="fef3c-303">Descrição</span><span class="sxs-lookup"><span data-stu-id="fef3c-303">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fef3c-304"><strong>Classificação</strong></span><span class="sxs-lookup"><span data-stu-id="fef3c-304"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="fef3c-305">Não</span><span class="sxs-lookup"><span data-stu-id="fef3c-305">No</span></span></p></td>
<td><p><span data-ttu-id="fef3c-p115">Classificação relativa de sessões com falha, com base no agente do usuário (software) envolvido na sessão. Por exemplo: RTCC/4.0.0.0 Inbound Routing/4.0.0.0.</span><span class="sxs-lookup"><span data-stu-id="fef3c-p115">Relative ranking of failed sessions based on the user agent (software) involved in the session. For example: RTCC/4.0.0.0 Inbound Routing/4.0.0.0.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fef3c-308"><strong>Principais agentes do usuário</strong></span><span class="sxs-lookup"><span data-stu-id="fef3c-308"><strong>Top user agents</strong></span></span></p></td>
<td><p><span data-ttu-id="fef3c-309">Não</span><span class="sxs-lookup"><span data-stu-id="fef3c-309">No</span></span></p></td>
<td><p><span data-ttu-id="fef3c-310">Nome do agente do usuário envolvido na sessão com falha.</span><span class="sxs-lookup"><span data-stu-id="fef3c-310">Name of the user agent involved in the failed session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fef3c-311"><strong>Sessões</strong></span><span class="sxs-lookup"><span data-stu-id="fef3c-311"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="fef3c-312">Não</span><span class="sxs-lookup"><span data-stu-id="fef3c-312">No</span></span></p></td>
<td><p><span data-ttu-id="fef3c-313">Número total de sessões com falha por agente do usuário.</span><span class="sxs-lookup"><span data-stu-id="fef3c-313">Total number of failed sessions per user agent.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

