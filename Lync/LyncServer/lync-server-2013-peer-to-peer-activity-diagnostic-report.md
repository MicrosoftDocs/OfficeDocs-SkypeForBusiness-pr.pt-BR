---
title: 'Lync Server 2013: relatório de diagnóstico de atividade ponto a ponto'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Peer-to-Peer Activity Diagnostic Report
ms:assetid: 025e8ab4-2e64-4a6b-8f52-caf756a5cac3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558602(v=OCS.15)
ms:contentKeyID: 48183242
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f435a4b0ff0ec42e8898260c3ada528963bbebb1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825405"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="peer-to-peer-activity-diagnostic-report-in-lync-server-2013"></a><span data-ttu-id="f4823-102">Relatório de diagnóstico de atividade ponto a ponto no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f4823-102">Peer-to-Peer Activity Diagnostic Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f4823-103">_**Tópico da última modificação:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="f4823-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="f4823-104">O Relatório de Diagnóstico de Atividades Ponto a Ponto fornece informações sobre o sucesso e falha de suas sessões de comunicação ponto a ponto.</span><span class="sxs-lookup"><span data-stu-id="f4823-104">The Peer-to-Peer Activity Diagnostic Report provides information about the success and failure of your peer-to-peer communication sessions.</span></span> <span data-ttu-id="f4823-105">Observe que o Microsoft Lync Server 2013 distingue entre os diferentes tipos de falha:</span><span class="sxs-lookup"><span data-stu-id="f4823-105">Note that Microsoft Lync Server 2013 distinguishes between different kinds of failure:</span></span>

  - <span data-ttu-id="f4823-106">**Falha esperada**.</span><span class="sxs-lookup"><span data-stu-id="f4823-106">**Expected failure**.</span></span> <span data-ttu-id="f4823-107">Uma falha esperada é normalmente uma falha somente no sentido mais técnico.</span><span class="sxs-lookup"><span data-stu-id="f4823-107">An expected failure is typically a failure only in the most technical sense.</span></span> <span data-ttu-id="f4823-108">Por exemplo, vamos supor que você ligue para alguém, mas ele ou ela esteja fora do escritório e não possa atender ao telefone.</span><span class="sxs-lookup"><span data-stu-id="f4823-108">For example, suppose you call someone, but he or she is away from the office and is unable to answer the phone.</span></span> <span data-ttu-id="f4823-109">Como a chamada não foi atendida, ela é considerada tecnicamente uma falha.</span><span class="sxs-lookup"><span data-stu-id="f4823-109">Because the call was not answered, the call is technically considered a failure.</span></span> <span data-ttu-id="f4823-110">Por outro lado, isso era uma falha esperada: o Microsoft Lync Server 2013 não espera que você atenda ao telefone se não estiver disponível para atender ao telefone.</span><span class="sxs-lookup"><span data-stu-id="f4823-110">On the other hand, this was an expected failure: Microsoft Lync Server 2013 does not expect you to answer the phone if you're not available to answer the phone.</span></span> <span data-ttu-id="f4823-111">Da mesma maneira, uma falha esperada ocorrerá se você tentar enviar uma mensagem instantânea a um usuário que esteja offline, ou conectado apenas a um telefone que não suporta mensagem instantânea.</span><span class="sxs-lookup"><span data-stu-id="f4823-111">Likewise, an expected failure will occur if you attempt to send an instant message to a user who is offline, or is logged on only to a phone that does not support instant messaging.</span></span>

  - <span data-ttu-id="f4823-112">**Falha inesperada**.</span><span class="sxs-lookup"><span data-stu-id="f4823-112">**Unexpected failure**.</span></span> <span data-ttu-id="f4823-113">Um erro inesperado é exatamente o que o nome sugere: um erro que, baseado nas circunstâncias, você não espera.</span><span class="sxs-lookup"><span data-stu-id="f4823-113">An unexpected error is exactly what the name implies: an error that, based on the circumstances, you would not expect to occur.</span></span> <span data-ttu-id="f4823-114">Por exemplo, suponha que você ligue para alguém e essa pessoa está disponível para atender a chamada; no entanto, quando o Lync Server 2013 tenta encaminhar sua chamada para o correio de voz, a chamada falha porque a conectividade com a Unificação de mensagens do Exchange foi perdida.</span><span class="sxs-lookup"><span data-stu-id="f4823-114">For example, suppose you call someone and that person is available to answer the call; however, when Lync Server 2013 tries to route your call to voicemail the call fails because connectivity to Exchange Unified Messaging has been lost.</span></span> <span data-ttu-id="f4823-115">Isso é um erro inesperado: você espera que as chamadas sejam sempre roteadas para o correio de voz.</span><span class="sxs-lookup"><span data-stu-id="f4823-115">That's an unexpected error: you would expect that calls could always be routed to voicemail.</span></span> <span data-ttu-id="f4823-116">Como regra geral, falhas inesperadas são verdadeiras falhas: elas são problemas que provavelmente não podem ser corrigidos por meio da educação do usuário ou por medidas parecidas.</span><span class="sxs-lookup"><span data-stu-id="f4823-116">As a general rule, unexpected failures are true failures: they are problems that likely cannot be remedied through user education or similar measures.</span></span>

<span data-ttu-id="f4823-p104">Observe que talvez as métricas Sucesso, Falha esperada e Falha inesperada não acrescentem à métrica Total de sessões. Por exemplo, na ilustração anterior, temos os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="f4823-p104">Note that the Success, Expected failure, and Unexpected failure metrics might not add up to the Total sessions metric. For example, in the preceding illustration, we have the following values:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f4823-119">Êxitos</span><span class="sxs-lookup"><span data-stu-id="f4823-119">Successes</span></span></th>
<th><span data-ttu-id="f4823-120">Falhas esperadas</span><span class="sxs-lookup"><span data-stu-id="f4823-120">Expected failures</span></span></th>
<th><span data-ttu-id="f4823-121">Falhas inesperadas</span><span class="sxs-lookup"><span data-stu-id="f4823-121">Unexpected failures</span></span></th>
<th><span data-ttu-id="f4823-122">Total de sessões</span><span class="sxs-lookup"><span data-stu-id="f4823-122">Total sessions</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f4823-123">2024</span><span class="sxs-lookup"><span data-stu-id="f4823-123">2024</span></span></p></td>
<td><p><span data-ttu-id="f4823-124">469</span><span class="sxs-lookup"><span data-stu-id="f4823-124">469</span></span></p></td>
<td><p><span data-ttu-id="f4823-125">16</span><span class="sxs-lookup"><span data-stu-id="f4823-125">16</span></span></p></td>
<td><p><span data-ttu-id="f4823-126">2521</span><span class="sxs-lookup"><span data-stu-id="f4823-126">2521</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="f4823-127">Se você adicionar 2024 + 469 + 16 terá um total de 2.509 sessões, ainda assim a coluna Total de sessões mostrará um total de 2.521 sessões.</span><span class="sxs-lookup"><span data-stu-id="f4823-127">If you add 2024 + 469 + 16 you get a total of 2,509 sessions, yet the Total sessions column shows a total of 2,521 sessions.</span></span> <span data-ttu-id="f4823-128">As 12 sessões que "faltam" são sessões que o sistema não pode categorizar como bem-sucedida ou sem sucesso.</span><span class="sxs-lookup"><span data-stu-id="f4823-128">The "missing" 12 sessions are sessions that the system was unable to categorize as successful or unsuccessful.</span></span> <span data-ttu-id="f4823-129">Isso, às vezes, é o caso quando um produto de terceiros introduz um novo código de diagnóstico que não é familiar ao Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f4823-129">That will sometimes be the case when a third-party product introduces a new diagnostic code that is unfamiliar to Lync Server.</span></span> <span data-ttu-id="f4823-130">Quando isso acontece, as chamadas feitas usando esse produto, e o relatório desse código de diagnóstico, não podem sempre ser categorizados como Sucesso, Falha esperada ou Falha inesperada.</span><span class="sxs-lookup"><span data-stu-id="f4823-130">When that happens, calls made using that product, and reporting that diagnostic code, cannot always be categorized as being a Success, an Expected failure, or an Unexpected failure.</span></span>

<div>

## <a name="accessing-the-peer-to-peer-activity-diagnostic-report"></a><span data-ttu-id="f4823-131">Acessando o Relatório de Diagnóstico de Atividades Ponto a Ponto</span><span class="sxs-lookup"><span data-stu-id="f4823-131">Accessing the Peer-to-Peer Activity Diagnostic Report</span></span>

<span data-ttu-id="f4823-132">O Relatório de Diagnóstico de Atividades Ponto a Ponto é acessado a partir da home page dos Relatórios de monitoramento.</span><span class="sxs-lookup"><span data-stu-id="f4823-132">The Peer-to-Peer Diagnostic Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="f4823-133">Você pode acessar o [relatório de distribuição de falha no Lync Server 2013](lync-server-2013-failure-distribution-report.md) clicando em uma das seguintes métricas:</span><span class="sxs-lookup"><span data-stu-id="f4823-133">You can access the [Failure Distribution Report in Lync Server 2013](lync-server-2013-failure-distribution-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="f4823-134">Volume de falhas inesperadas</span><span class="sxs-lookup"><span data-stu-id="f4823-134">Unexpected failure volume</span></span>

  - <span data-ttu-id="f4823-135">Volume de falhas esperadas</span><span class="sxs-lookup"><span data-stu-id="f4823-135">Expected failure volume</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-peer-to-peer-activity-diagnostic-report"></a><span data-ttu-id="f4823-136">Fazendo o melhor uso do Relatório de Diagnóstico de Atividades Ponto a Ponto</span><span class="sxs-lookup"><span data-stu-id="f4823-136">Making the Best Use of the Peer-to-Peer Activity Diagnostic Report</span></span>

<span data-ttu-id="f4823-p107">Há diversas maneiras de usar filtrar o Relatório de Diagnóstico de Atividades Ponto a Ponto, mas, por padrão, essas opções de filtragem ficam ocultas. Para exibir as opções de filtragem disponíveis, clique no botão Mostrar/Ocultar Parâmetros no canto superior direito da janela de relatório. Depois de fazer isso, as opções de filtragem ficarão disponíveis para uso.</span><span class="sxs-lookup"><span data-stu-id="f4823-p107">There are a number of ways you can filter the Peer-to-Peer Activity Diagnostic Report but, by default, those filtering options are hidden from view. To view the filtering options available to you, click the Show/Hide Parameters button in the upper right-hand corner of the report window. Once you do that the filtering options will be available for use.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="f4823-140">Filtros</span><span class="sxs-lookup"><span data-stu-id="f4823-140">Filters</span></span>

<span data-ttu-id="f4823-p108">Filtros oferecem uma maneira de você retornar um conjunto de dados mais preciso ou visualizar os dados retornados de maneiras diferentes. Por exemplo, o Relatório de Diagnóstico de Atividade Ponto-a-Ponto permite que você filtre tais coisas como a modalidade de sessão (por exemplo, mensagens instantâneas, transferência de arquivos ou compartilhamento de arquivos). Você pode escolher também como os dados devem ser agrupados. Neste caso, as chamadas são agrupadas por hora, dia, semana ou mês.</span><span class="sxs-lookup"><span data-stu-id="f4823-p108">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Peer-to-Peer Activity Diagnostic Report enables you to filter on such things as the session modality (for example, instant messaging, file transfer, or application sharing). You can also choose how data should be grouped. In this case, calls are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="f4823-145">A tabela a seguir lista os filtros que você pode utilizar com o Relatório de Diagnóstico de Atividade Ponto-a-Ponto.</span><span class="sxs-lookup"><span data-stu-id="f4823-145">The following table lists the filters that you can use with the Peer-to-Peer Activity Diagnostic Report.</span></span>

### <a name="peer-to-peer-activity-diagnostic-report-filters"></a><span data-ttu-id="f4823-146">Filtros de Relatório de Diagnóstico de Atividade Ponto-a-Ponto</span><span class="sxs-lookup"><span data-stu-id="f4823-146">Peer-to-Peer Activity Diagnostic Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f4823-147">Nome</span><span class="sxs-lookup"><span data-stu-id="f4823-147">Name</span></span></th>
<th><span data-ttu-id="f4823-148">Descrição</span><span class="sxs-lookup"><span data-stu-id="f4823-148">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f4823-149"><strong>De</strong></span><span class="sxs-lookup"><span data-stu-id="f4823-149"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="f4823-p109">Data/hora de início para o intervalo de tempo. Para ver os dados por horas, insira a data e hora de início conforme segue:</span><span class="sxs-lookup"><span data-stu-id="f4823-p109">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="f4823-152">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="f4823-152">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="f4823-p110">Se você não inserir a hora de início, o relatório começará automaticamente à meia-noite do dia especificado. Para ver os dados por dia, insira somente a data:</span><span class="sxs-lookup"><span data-stu-id="f4823-p110">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="f4823-155">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="f4823-155">7/7/2012</span></span></p>
<p><span data-ttu-id="f4823-156">Para exibir por semana ou mês, insira uma data dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):</span><span class="sxs-lookup"><span data-stu-id="f4823-156">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="f4823-157">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="f4823-157">7/3/2012</span></span></p>
<p><span data-ttu-id="f4823-158">As semanas sempre vão de domingo a sábado.</span><span class="sxs-lookup"><span data-stu-id="f4823-158">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4823-159"><strong>Até</strong></span><span class="sxs-lookup"><span data-stu-id="f4823-159"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="f4823-p111">Data/hora final de intervalo de tempo. Para ver os dados por horas, insira a data e hora final conforme segue:</span><span class="sxs-lookup"><span data-stu-id="f4823-p111">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="f4823-162">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="f4823-162">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="f4823-p112">Se você não inserir a hora final, o relatório terminará automaticamente à meia-noite do dia especificado. Para ver os dados por dia, insira somente a data:</span><span class="sxs-lookup"><span data-stu-id="f4823-p112">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="f4823-165">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="f4823-165">7/7/2012</span></span></p>
<p><span data-ttu-id="f4823-166">Para exibir por semana ou mês, insira uma data dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):</span><span class="sxs-lookup"><span data-stu-id="f4823-166">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="f4823-167">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="f4823-167">7/3/2012</span></span></p>
<p><span data-ttu-id="f4823-168">As semanas sempre vão de domingo a sábado.</span><span class="sxs-lookup"><span data-stu-id="f4823-168">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4823-169"><strong>Intervalo</strong></span><span class="sxs-lookup"><span data-stu-id="f4823-169"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="f4823-p113">Intervalo de tempo. Selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="f4823-p113">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="f4823-172">Por hora (é possível exibir no máximo 25 horas)</span><span class="sxs-lookup"><span data-stu-id="f4823-172">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="f4823-173">Diariamente (é possível exibir no máximo 31 dias)</span><span class="sxs-lookup"><span data-stu-id="f4823-173">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="f4823-174">Semanalmente (é possível exibir no máximo 12 semanas)</span><span class="sxs-lookup"><span data-stu-id="f4823-174">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="f4823-175">Mensalmente (é possível exibir no máximo 12 meses)</span><span class="sxs-lookup"><span data-stu-id="f4823-175">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="f4823-176">Se as datas de início e término excederem o número máximo de valores permitidos para o intervalo selecionado, somente o número máximo de valores (a partir da data de início) será exibido.</span><span class="sxs-lookup"><span data-stu-id="f4823-176">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed.</span></span> <span data-ttu-id="f4823-177">Por exemplo, se você selecionar o intervalo diário com uma data de início de 7/7/2012 e uma data de término de 2/28/2012, os dados serão exibidos para os dias 8/7/2012 12:00 AM a 9/7/2012 12:00 AM (ou seja, um total de 31 dias da importância dos dados).</span><span class="sxs-lookup"><span data-stu-id="f4823-177">For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4823-178"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="f4823-178"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="f4823-p115">FQDN (Nome de domínio totalmente qualificado) do pool de Registradores ou Servidor de Borda. Você pode selecionar um pool individual ou clicar em <strong>[Tudo]</strong> para ver os dados de todos os pools. Essa lista suspensa é automaticamente preenchida para você com base nos registros no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="f4823-p115">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4823-182"><strong>Modalidade</strong></span><span class="sxs-lookup"><span data-stu-id="f4823-182"><strong>Modality</strong></span></span></p></td>
<td><p><span data-ttu-id="f4823-p116">Indica o tipo de atividade de comunicação que ocorreu. Selecione um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="f4823-p116">Indicates the type of communication activity that took place. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="f4823-185">[Todos]</span><span class="sxs-lookup"><span data-stu-id="f4823-185">[All]</span></span></p></li>
<li><p><span data-ttu-id="f4823-186">Mensagens instantâneas</span><span class="sxs-lookup"><span data-stu-id="f4823-186">Instant messaging</span></span></p></li>
<li><p><span data-ttu-id="f4823-187">Transferência de arquivos</span><span class="sxs-lookup"><span data-stu-id="f4823-187">File transfer</span></span></p></li>
<li><p><span data-ttu-id="f4823-188">Compartilhamento de aplicativos</span><span class="sxs-lookup"><span data-stu-id="f4823-188">Application sharing</span></span></p></li>
<li><p><span data-ttu-id="f4823-189">Áudio</span><span class="sxs-lookup"><span data-stu-id="f4823-189">Audio</span></span></p></li>
<li><p><span data-ttu-id="f4823-190">Vídeo</span><span class="sxs-lookup"><span data-stu-id="f4823-190">Video</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-per-modality"></a><span data-ttu-id="f4823-191">Medidas (por modalidade)</span><span class="sxs-lookup"><span data-stu-id="f4823-191">Metrics (per modality)</span></span>

<span data-ttu-id="f4823-192">A tabela a seguir lista as informações oferecidas no Relatório de Diagnóstico de Atividades Ponto-a-Ponto para cada modalidade.</span><span class="sxs-lookup"><span data-stu-id="f4823-192">The following table lists the information provided in the Peer-to-Peer Activity Diagnostic Report for each modality.</span></span>

### <a name="metrics-per-modality"></a><span data-ttu-id="f4823-193">Medidas (por modalidade)</span><span class="sxs-lookup"><span data-stu-id="f4823-193">Metrics (per modality)</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f4823-194">Nome</span><span class="sxs-lookup"><span data-stu-id="f4823-194">Name</span></span></th>
<th><span data-ttu-id="f4823-195">Você pode classificar este item?</span><span class="sxs-lookup"><span data-stu-id="f4823-195">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="f4823-196">Descrição</span><span class="sxs-lookup"><span data-stu-id="f4823-196">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f4823-197"><strong>Volume de sucesso</strong></span><span class="sxs-lookup"><span data-stu-id="f4823-197"><strong>Success volume</strong></span></span></p></td>
<td><p><span data-ttu-id="f4823-198">Não</span><span class="sxs-lookup"><span data-stu-id="f4823-198">No</span></span></p></td>
<td><p><span data-ttu-id="f4823-199">Número total de sessões ponto-a-ponto com êxito.</span><span class="sxs-lookup"><span data-stu-id="f4823-199">Total number of successful peer-to-peer sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4823-200"><strong>Porcentagem de sucesso</strong></span><span class="sxs-lookup"><span data-stu-id="f4823-200"><strong>Success percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="f4823-201">Não</span><span class="sxs-lookup"><span data-stu-id="f4823-201">No</span></span></p></td>
<td><p><span data-ttu-id="f4823-p117">Porcentagem de sessões ponto-a-ponto completas com problemas significativos. Calculado dividindo o Volume de sucesso pelo Total de sessões.</span><span class="sxs-lookup"><span data-stu-id="f4823-p117">Percentage of peer-to-peer sessions that completed with significant problems. Calculated by dividing the Success volume by the Total sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4823-204"><strong>Volume de falhas esperadas</strong></span><span class="sxs-lookup"><span data-stu-id="f4823-204"><strong>Expected failure volume</strong></span></span></p></td>
<td><p><span data-ttu-id="f4823-205">Não</span><span class="sxs-lookup"><span data-stu-id="f4823-205">No</span></span></p></td>
<td><p><span data-ttu-id="f4823-206">Número total de sessões em que &quot;ocorreu uma&quot; falha esperada.</span><span class="sxs-lookup"><span data-stu-id="f4823-206">Total number of sessions where an &quot;expected failure&quot; occurred.</span></span></p>
<p><span data-ttu-id="f4823-p118">Uma falha esperada é quando se sabe que a falha ocorrerá. Por exemplo, se um usuário tiver definido seu status como Não perturbe, é esperado que qualquer chamada para esse usuário falhe.</span><span class="sxs-lookup"><span data-stu-id="f4823-p118">An expected failure is a failure that is expected to happen. For example, if a user has set his or her status to Do Not Disturb you would expect any call to that user to fail.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4823-209"><strong>Percentual de falhas esperadas</strong></span><span class="sxs-lookup"><span data-stu-id="f4823-209"><strong>Expected failure percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="f4823-210">Não</span><span class="sxs-lookup"><span data-stu-id="f4823-210">No</span></span></p></td>
<td><p><span data-ttu-id="f4823-p119">Porcentagem de sessões ponto-a-ponto que tiveram um erro esperado. Calculado dividindo o Volume de falhas esperadas pelo Total de sessões.</span><span class="sxs-lookup"><span data-stu-id="f4823-p119">Percentage of peer-to-peer sessions that experienced an expected error. Calculated by dividing the Expected failure volume by the Total sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4823-213"><strong>Volume de falhas inesperadas</strong></span><span class="sxs-lookup"><span data-stu-id="f4823-213"><strong>Unexpected failure volume</strong></span></span></p></td>
<td><p><span data-ttu-id="f4823-214">Não</span><span class="sxs-lookup"><span data-stu-id="f4823-214">No</span></span></p></td>
<td><p><span data-ttu-id="f4823-215">Número total de sessões em que &quot;ocorreu uma&quot; falha inesperada.</span><span class="sxs-lookup"><span data-stu-id="f4823-215">Total number of sessions where an &quot;unexpected failure&quot; occurred.</span></span></p>
<p><span data-ttu-id="f4823-p120">Uma falha inesperada é uma falha que ocorre no que aparenta ser um sistema íntegro. Por exemplo, uma chamada não deve ser encerrada se o chamador for colocado em espera. Se isso ocorrer, isso seria sinalizado como uma falha inesperada.</span><span class="sxs-lookup"><span data-stu-id="f4823-p120">An unexpected failure is a failure that occurs in what would appear to be an otherwise healthy system. For example, a call should not be terminated if the caller is placed on hold. If that occurs, that would be flagged as an unexpected failure.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4823-219"><strong>Percentual de falhas inesperadas</strong></span><span class="sxs-lookup"><span data-stu-id="f4823-219"><strong>Unexpected failure percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="f4823-220">Não</span><span class="sxs-lookup"><span data-stu-id="f4823-220">No</span></span></p></td>
<td><p><span data-ttu-id="f4823-p121">Porcentagem de sessões ponto-a-ponto nas quais um erro inesperado ocorreu. Calculado dividindo o Volume de falhas inesperadas pelo Total de sessões.</span><span class="sxs-lookup"><span data-stu-id="f4823-p121">Percentage of peer-to-peer sessions that experienced an unexpected error. Calculated by dividing the Unexpected failure volume by the Total sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4823-223"><strong>Total de sessões</strong></span><span class="sxs-lookup"><span data-stu-id="f4823-223"><strong>Total sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="f4823-224">Não</span><span class="sxs-lookup"><span data-stu-id="f4823-224">No</span></span></p></td>
<td><p><span data-ttu-id="f4823-225">Número total de sessões, incluindo sessões bem-sucedidas, com falha (esperada e/ou inesperada) e sessões não categorizadas.</span><span class="sxs-lookup"><span data-stu-id="f4823-225">Total number of sessions, including successful sessions, failed sessions (both expected failures and unexpected failures), and uncategorized sessions.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

