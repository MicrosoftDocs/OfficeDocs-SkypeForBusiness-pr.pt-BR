---
title: 'Lync Server 2013: relatório de Resumo de qualidade de mídia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Media Quality Summary Report
ms:assetid: 8bd59ad6-3087-49c8-b692-5573fe2ffcd8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615012(v=OCS.15)
ms:contentKeyID: 48184776
ms.date: 06/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 89a5046ba15534d40c81e1e3b8a4f310873a9e1b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045103"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="media-quality-summary-report-in-lync-server-2013"></a><span data-ttu-id="2ca29-102">Relatório de Resumo de qualidade de mídia no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2ca29-102">Media Quality Summary Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2ca29-103">_**Última modificação do tópico:** 2016-06-29_</span><span class="sxs-lookup"><span data-stu-id="2ca29-103">_**Topic Last Modified:** 2016-06-29_</span></span>

<span data-ttu-id="2ca29-104">O Relatório de resumo de qualidade de mídia é talvez a melhor maneira de analisar a qualidade das chamadas em sua organização: este relatório fornece métricas de chamada para Qualidade de Serviço (QoS) divididas nas seguintes categorias:</span><span class="sxs-lookup"><span data-stu-id="2ca29-104">The Media Quality Summary Report is perhaps your best bet for analyzing call quality in your organization: this report provides detailed Quality of Experience (QoE) call metrics broken down into the following categories:</span></span>

  - <span data-ttu-id="2ca29-105">Chamadas ponto a ponto de UC (como uma chamada do Microsoft Lync 2013 para o Microsoft Lync 2013)</span><span class="sxs-lookup"><span data-stu-id="2ca29-105">UC Peer to Peer Calls (such as a Microsoft Lync 2013 to Microsoft Lync 2013 call)</span></span>

  - <span data-ttu-id="2ca29-106">Sessões de Conferência de UC</span><span class="sxs-lookup"><span data-stu-id="2ca29-106">UC Conference Sessions</span></span>

  - <span data-ttu-id="2ca29-107">Sessões de Conferência PSTN</span><span class="sxs-lookup"><span data-stu-id="2ca29-107">PSTN Conference Sessions</span></span>

  - <span data-ttu-id="2ca29-108">Chamadas PSTN: Desvio de Mídia</span><span class="sxs-lookup"><span data-stu-id="2ca29-108">PSTN Calls: Media Bypass</span></span>

  - <span data-ttu-id="2ca29-109">Chamadas PSTN (Não Ignorar): Trecho de UC</span><span class="sxs-lookup"><span data-stu-id="2ca29-109">PSTN Calls (Non-Bypass): UC Leg</span></span>

  - <span data-ttu-id="2ca29-110">Chamadas PSTN (Não Ignorar): Trecho de Gateway</span><span class="sxs-lookup"><span data-stu-id="2ca29-110">PSTN Calls (Non-Bypass): Gateway Leg</span></span>

  - <span data-ttu-id="2ca29-111">Outros Tipos de Chamada</span><span class="sxs-lookup"><span data-stu-id="2ca29-111">Other Call Types</span></span>

<span data-ttu-id="2ca29-112">Ao abrir pela primeira vez o relatório, você verá informações resumidas para cada uma das categorias.</span><span class="sxs-lookup"><span data-stu-id="2ca29-112">When you first open the report, you see summary information for each of these categories.</span></span> <span data-ttu-id="2ca29-113">Sem sair do relatório, você pode expandir cada categoria para examinar subcategorias como chamadas feitas do Office Communicator 2007 R2 para o Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="2ca29-113">Without leaving the report, you can expand each category to look at subcategories such as calls made from Office Communicator 2007 R2 to Lync 2013.</span></span> <span data-ttu-id="2ca29-114">Por sua vez, você pode ver os detalhes de cada chamada feita dentro dessa subcategoria.</span><span class="sxs-lookup"><span data-stu-id="2ca29-114">In turn, you can then drill down into these subcategories to see details about each call made within that subcategory.</span></span>

<span data-ttu-id="2ca29-115">No Microsoft Lync Server 2013, o relatório de Resumo de qualidade de mídia divide ainda mais os dados em três tipos de chamadas: chamadas de áudio, chamadas de vídeo e chamadas de compartilhamento de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="2ca29-115">In Microsoft Lync Server 2013 the Media Quality Summary Report further breaks the data down into three call types: audio calls, video calls, and application sharing calls.</span></span> <span data-ttu-id="2ca29-116">Cada tipo de chamada tem sua própria seção no relatório, e seu próprio conjunto de métricas de chamadas.</span><span class="sxs-lookup"><span data-stu-id="2ca29-116">Each call type has its own section in the report, and its own custom set of call metrics.</span></span>

<span data-ttu-id="2ca29-117">O Relatório de resumo de qualidade de mídia também permite aplicar filtros que permitem comparar a qualidade de chamada de chamadas com fio em relação a chamadas sem fio, chamadas internas x chamadas externas e chamadas VPN x chamadas não VPN.</span><span class="sxs-lookup"><span data-stu-id="2ca29-117">The Media Quality Summary Report also allows you to apply filters that enable you to compare the call quality of wired calls vs. wireless calls, internal calls vs. external calls, and VPN calls vs. non-VPN calls.</span></span>

<div>

## <a name="accessing-the-media-quality-summary-report"></a><span data-ttu-id="2ca29-118">Como acessar o Relatório de resumo de qualidade de mídia</span><span class="sxs-lookup"><span data-stu-id="2ca29-118">Accessing the Media Quality Summary Report</span></span>

<span data-ttu-id="2ca29-119">O Relatório de resumo de qualidade de mídia é acessado a partir da página inicial dos Relatórios de Monitoramento.</span><span class="sxs-lookup"><span data-stu-id="2ca29-119">The Media Quality Summary Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="2ca29-120">Você pode fazer uma busca detalhada no [relatório de lista de chamadas no Lync Server 2013](lync-server-2013-call-list-report.md) clicando em uma das seguintes métricas:</span><span class="sxs-lookup"><span data-stu-id="2ca29-120">You can drill down to the [Call List Report in Lync Server 2013](lync-server-2013-call-list-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="2ca29-121">Volume da chamada</span><span class="sxs-lookup"><span data-stu-id="2ca29-121">Call volume</span></span>

  - <span data-ttu-id="2ca29-122">Porcentagem de chamada inválida</span><span class="sxs-lookup"><span data-stu-id="2ca29-122">Poor call percentage</span></span>

<span data-ttu-id="2ca29-123">Além disso, você pode acessar o Relatório de distribuição de métricas de qualidade de mídia clicando em uma das seguintes métricas de chamada de áudio:</span><span class="sxs-lookup"><span data-stu-id="2ca29-123">In addition, you can access the Media Quality Metrics Distribution Report by clicking any of the following audio call metrics:</span></span>

  - <span data-ttu-id="2ca29-124">Viagem de ida e volta (ms)</span><span class="sxs-lookup"><span data-stu-id="2ca29-124">Round trip (ms)</span></span>

  - <span data-ttu-id="2ca29-125">Degradação (MOS)</span><span class="sxs-lookup"><span data-stu-id="2ca29-125">Degradation (MOS)</span></span>

  - <span data-ttu-id="2ca29-126">Perda de pacote</span><span class="sxs-lookup"><span data-stu-id="2ca29-126">Packet loss</span></span>

  - <span data-ttu-id="2ca29-127">Tremulação (ms)</span><span class="sxs-lookup"><span data-stu-id="2ca29-127">Jitter (ms)</span></span>

  - <span data-ttu-id="2ca29-128">Taxa de correção oculta</span><span class="sxs-lookup"><span data-stu-id="2ca29-128">Healer concealed ratio</span></span>

  - <span data-ttu-id="2ca29-129">Taxa de correção estendida</span><span class="sxs-lookup"><span data-stu-id="2ca29-129">Healer stretched ratio</span></span>

  - <span data-ttu-id="2ca29-130">Taxa de correção compactada</span><span class="sxs-lookup"><span data-stu-id="2ca29-130">Healer compressed ratio</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="2ca29-131">Filtros</span><span class="sxs-lookup"><span data-stu-id="2ca29-131">Filters</span></span>

<span data-ttu-id="2ca29-p104">Filtros fornecem uma forma de retornar um conjunto de dados mais focado ou exibir os dados retornados de diferentes formas. Por exemplo, o Relatório de Resumo de Qualidade de Mídia permite filtrar os dados retornados por informações como tipo de acesso (ou seja, acesso interno vs. acesso externo) ou por conexão de rede com fio/sem fio. Você também pode escolher como os dados serão agrupados. Neste caso, as chamadas são agrupadas por hora, dia, semana ou mês.</span><span class="sxs-lookup"><span data-stu-id="2ca29-p104">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Media Quality Summary Report enables you to filter the returned data by such things as access type (that is, interval access vs. external access) or by wired/wireless network connection. You can also choose how data should be grouped. In this case, calls are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="2ca29-136">A tabela a seguir lista os filtros que podem ser usados com o Relatório de Resumo de Qualidade de Mídia.</span><span class="sxs-lookup"><span data-stu-id="2ca29-136">The following table lists the filters that you can use with the Media Quality Summary Report.</span></span>

### <a name="media-quality-summary-report-filters"></a><span data-ttu-id="2ca29-137">Filtros do Relatório de Resumo de Qualidade de Mídia</span><span class="sxs-lookup"><span data-stu-id="2ca29-137">Media Quality Summary Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2ca29-138">Nome</span><span class="sxs-lookup"><span data-stu-id="2ca29-138">Name</span></span></th>
<th><span data-ttu-id="2ca29-139">Descrição</span><span class="sxs-lookup"><span data-stu-id="2ca29-139">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2ca29-140"><strong>De</strong></span><span class="sxs-lookup"><span data-stu-id="2ca29-140"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="2ca29-p105">Data/hora inicial para o intervalo de tempo. Para exibir os dados por hora, insira a data e hora inicial como a seguir:</span><span class="sxs-lookup"><span data-stu-id="2ca29-p105">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="2ca29-143">7/7/2012 13:00 horas</span><span class="sxs-lookup"><span data-stu-id="2ca29-143">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="2ca29-p106">Se você não inserir uma hora inicial, o relatório começa automaticamente as 12:00 AM no dia especificado. Para exibir os dados por dia, insira apenas a data:</span><span class="sxs-lookup"><span data-stu-id="2ca29-p106">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="2ca29-146">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="2ca29-146">7/7/2012</span></span></p>
<p><span data-ttu-id="2ca29-147">Para exibir por semana ou mês, insira uma data que está dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):</span><span class="sxs-lookup"><span data-stu-id="2ca29-147">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="2ca29-148">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="2ca29-148">7/3/2012</span></span></p>
<p><span data-ttu-id="2ca29-149">As semanas são sempre de domingo a sábado.</span><span class="sxs-lookup"><span data-stu-id="2ca29-149">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ca29-150"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="2ca29-150"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="2ca29-p107">Data/hora final para o intervalo de tempo. Para exibir os dados por hora, insira a data e hora final como a seguir:</span><span class="sxs-lookup"><span data-stu-id="2ca29-p107">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="2ca29-153">7/7/2012 13:00 horas</span><span class="sxs-lookup"><span data-stu-id="2ca29-153">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="2ca29-p108">Se você não inserir uma hora final, o relatório termina automaticamente as 12:00 AM no dia especificado. Para exibir os dados por dia, insira apenas a data:</span><span class="sxs-lookup"><span data-stu-id="2ca29-p108">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="2ca29-156">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="2ca29-156">7/7/2012</span></span></p>
<p><span data-ttu-id="2ca29-157">Para exibir por semana ou mês, insira uma data que está dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):</span><span class="sxs-lookup"><span data-stu-id="2ca29-157">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="2ca29-158">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="2ca29-158">7/3/2012</span></span></p>
<p><span data-ttu-id="2ca29-159">As semanas sempre vão de domingo a sábado.</span><span class="sxs-lookup"><span data-stu-id="2ca29-159">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2ca29-160"><strong>Tipo de acesso</strong></span><span class="sxs-lookup"><span data-stu-id="2ca29-160"><strong>Access type</strong></span></span></p></td>
<td><p><span data-ttu-id="2ca29-p109">Indica se um cliente estava conectado na rede interna ou na rede externa quando a chamada foi realizada. Selecione um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="2ca29-p109">Indicates whether the client was logged on to the internal network or the external network when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="2ca29-163">Todos os</span><span class="sxs-lookup"><span data-stu-id="2ca29-163">[All]</span></span></p></li>
<li><p><span data-ttu-id="2ca29-164">Interna</span><span class="sxs-lookup"><span data-stu-id="2ca29-164">Internal</span></span></p></li>
<li><p><span data-ttu-id="2ca29-165">Externa</span><span class="sxs-lookup"><span data-stu-id="2ca29-165">External</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ca29-166"><strong>Tipo de rede</strong></span><span class="sxs-lookup"><span data-stu-id="2ca29-166"><strong>Network type</strong></span></span></p></td>
<td><p><span data-ttu-id="2ca29-p110">Indica o tipo de rede que o cliente estava conectado quando a chamada foi realizada. Selecione um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="2ca29-p110">Indicates the type of network the client was connected to when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="2ca29-169">Todos os</span><span class="sxs-lookup"><span data-stu-id="2ca29-169">[All]</span></span></p></li>
<li><p><span data-ttu-id="2ca29-170">Com fio</span><span class="sxs-lookup"><span data-stu-id="2ca29-170">Wired</span></span></p></li>
<li><p><span data-ttu-id="2ca29-171">Conexão</span><span class="sxs-lookup"><span data-stu-id="2ca29-171">Wireless</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2ca29-172"><strong>VPN</strong></span><span class="sxs-lookup"><span data-stu-id="2ca29-172"><strong>VPN</strong></span></span></p></td>
<td><p><span data-ttu-id="2ca29-p111">Indica se um cliente externo estava usando uma conexão de rede privada virtual (VPN) quando a chamada foi realizada. Selecione um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="2ca29-p111">Indicates whether an external client was using a virtual private network (VPN) connection when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="2ca29-175">Todos os</span><span class="sxs-lookup"><span data-stu-id="2ca29-175">[All]</span></span></p></li>
<li><p><span data-ttu-id="2ca29-176">VPN</span><span class="sxs-lookup"><span data-stu-id="2ca29-176">VPN</span></span></p></li>
<li><p><span data-ttu-id="2ca29-177">Não VPN</span><span class="sxs-lookup"><span data-stu-id="2ca29-177">Non-VPN</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="2ca29-178">Métricas</span><span class="sxs-lookup"><span data-stu-id="2ca29-178">Metrics</span></span>

<span data-ttu-id="2ca29-179">A tabela a seguir lista as informações fornecidas no Relatório de Resumo de Qualidade de Mídia.</span><span class="sxs-lookup"><span data-stu-id="2ca29-179">The following table lists the information provided in the Media Quality Summary Report.</span></span>

### <a name="media-quality-summary-report-metrics-audio-call-summary"></a><span data-ttu-id="2ca29-180">Métricas do Relatório de Resumo de Qualidade de Mídia: Resumo da chamada de áudio</span><span class="sxs-lookup"><span data-stu-id="2ca29-180">Media Quality Summary Report Metrics: Audio Call Summary</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2ca29-181">Nome</span><span class="sxs-lookup"><span data-stu-id="2ca29-181">Name</span></span></th>
<th><span data-ttu-id="2ca29-182">É possível classificar este item?</span><span class="sxs-lookup"><span data-stu-id="2ca29-182">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="2ca29-183">Descrição</span><span class="sxs-lookup"><span data-stu-id="2ca29-183">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2ca29-184"><strong>Tipo de Chamada/Tipo de Ponto de Extremidade</strong></span><span class="sxs-lookup"><span data-stu-id="2ca29-184"><strong>Call type/Endpoint type</strong></span></span></p></td>
<td><p><span data-ttu-id="2ca29-185">Não</span><span class="sxs-lookup"><span data-stu-id="2ca29-185">No</span></span></p></td>
<td><p><span data-ttu-id="2ca29-p112">Ao clicar neste item, o relatório mostra informações detalhadas sobre chamadas baseadas no tipo escolhido. Tipos de chamada incluem:</span><span class="sxs-lookup"><span data-stu-id="2ca29-p112">When you click this item, the report shows detailed information about calls based on that type. Call types include:</span></span></p>
<ul>
<li><p><span data-ttu-id="2ca29-188">Chamadas Ponto a Ponto de UC</span><span class="sxs-lookup"><span data-stu-id="2ca29-188">UC Peer-to-Peer Calls</span></span></p></li>
<li><p><span data-ttu-id="2ca29-189">Sessões de Conferência de UC</span><span class="sxs-lookup"><span data-stu-id="2ca29-189">UC Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="2ca29-190">Sessões de Conferência PSTN</span><span class="sxs-lookup"><span data-stu-id="2ca29-190">PSTN Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="2ca29-191">Chamadas PSTN: Desvio de Mídia</span><span class="sxs-lookup"><span data-stu-id="2ca29-191">PSTN Calls: Media Bypass</span></span></p></li>
<li><p><span data-ttu-id="2ca29-192">Chamadas PSTN (Não Ignorar): Trecho de UC</span><span class="sxs-lookup"><span data-stu-id="2ca29-192">PSTN Calls (Non-Bypass): UC Leg</span></span></p></li>
<li><p><span data-ttu-id="2ca29-193">Chamadas PSTN (Não Ignorar): Trecho de Gateway</span><span class="sxs-lookup"><span data-stu-id="2ca29-193">PSTN Calls (Non-Bypass): Gateway Leg</span></span></p></li>
<li><p><span data-ttu-id="2ca29-194">Outros Tipos de Chamada</span><span class="sxs-lookup"><span data-stu-id="2ca29-194">Other Call Types</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ca29-195"><strong>Volume da chamada</strong></span><span class="sxs-lookup"><span data-stu-id="2ca29-195"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="2ca29-196">Não</span><span class="sxs-lookup"><span data-stu-id="2ca29-196">No</span></span></p></td>
<td><p><span data-ttu-id="2ca29-197">Número total de chamadas por tipo de chamada.</span><span class="sxs-lookup"><span data-stu-id="2ca29-197">Total number of calls per call type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2ca29-198"><strong>Percentual de chamadas ruins</strong></span><span class="sxs-lookup"><span data-stu-id="2ca29-198"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="2ca29-199">Não</span><span class="sxs-lookup"><span data-stu-id="2ca29-199">No</span></span></p></td>
<td><p><span data-ttu-id="2ca29-p113">Número total de chamadas classificadas como ruins. Uma chamada ruim é qualquer chamada em que no mínimo uma das métricas medidas excedeu o valor permitido (por exemplo, uma chamada com tremulação excessiva).</span><span class="sxs-lookup"><span data-stu-id="2ca29-p113">Total number of calls classified as poor. A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ca29-202"><strong>Volume de chamadas (chamadas sem fio)</strong></span><span class="sxs-lookup"><span data-stu-id="2ca29-202"><strong>Call volume (wireless call)</strong></span></span></p></td>
<td><p><span data-ttu-id="2ca29-203">Não</span><span class="sxs-lookup"><span data-stu-id="2ca29-203">No</span></span></p></td>
<td><p><span data-ttu-id="2ca29-204">Número total de chamadas que usaram uma conexão sem fio.</span><span class="sxs-lookup"><span data-stu-id="2ca29-204">Total number of calls that used a wireless connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2ca29-205"><strong>Volume de chamadas (chamadas VPN)</strong></span><span class="sxs-lookup"><span data-stu-id="2ca29-205"><strong>Call volume (VPN call)</strong></span></span></p></td>
<td><p><span data-ttu-id="2ca29-206">Não</span><span class="sxs-lookup"><span data-stu-id="2ca29-206">No</span></span></p></td>
<td><p><span data-ttu-id="2ca29-207">Número total de chamadas que usaram uma conexão VPN.</span><span class="sxs-lookup"><span data-stu-id="2ca29-207">Total number of calls that used a VPN connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ca29-208"><strong>Volume de chamadas (chamadas externas)</strong></span><span class="sxs-lookup"><span data-stu-id="2ca29-208"><strong>Call volume (external call)</strong></span></span></p></td>
<td><p><span data-ttu-id="2ca29-209">Não</span><span class="sxs-lookup"><span data-stu-id="2ca29-209">No</span></span></p></td>
<td><p><span data-ttu-id="2ca29-210">Número de chamadas que usaram uma conexão externa (ou seja, uma conexão fora da rede interna).</span><span class="sxs-lookup"><span data-stu-id="2ca29-210">Number of calls that used an external connection (that is, a connection outside the internal network).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2ca29-211"><strong>Tempo de resposta (ms)</strong></span><span class="sxs-lookup"><span data-stu-id="2ca29-211"><strong>Round trip (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="2ca29-212">Não</span><span class="sxs-lookup"><span data-stu-id="2ca29-212">No</span></span></p></td>
<td><p><span data-ttu-id="2ca29-p114">Quantidade média (em milissegundos) necessária para um pacote de protocolo de transporte em tempo real (RTP) viajar para outro ponto de extremidade e voltar. Tempos de resposta de 100 milissegundos ou menos são considerados de qualidade aceitável.</span><span class="sxs-lookup"><span data-stu-id="2ca29-p114">Average amount of (in milliseconds) required for a real-time transport protocol (RTP) packet to travel to another endpoint and then back. Round-trip times of 100 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="2ca29-p115">Os valores altos de ida e volta pode ser causados por roteamento de chamada internacional, um erro de configuração de roteamento ou um servidor de mídia sobrecarregado. Tempos de ida e volta altos resultam em dificuldades com conversas de áudio em tempo real e bidirecionais.</span><span class="sxs-lookup"><span data-stu-id="2ca29-p115">High round-trip values can be caused by international call routing, a routing misconfiguration, or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ca29-217"><strong>Degradação (MOS)</strong></span><span class="sxs-lookup"><span data-stu-id="2ca29-217"><strong>Degradation (MOS)</strong></span></span></p></td>
<td><p><span data-ttu-id="2ca29-218">Não</span><span class="sxs-lookup"><span data-stu-id="2ca29-218">No</span></span></p></td>
<td><p><span data-ttu-id="2ca29-219">Quantidade média de degradação MOS (pontuação média de opinião) experimentada durante uma chamada.</span><span class="sxs-lookup"><span data-stu-id="2ca29-219">Average amount of mean opinion score (MOS) degradation experienced during a call.</span></span> <span data-ttu-id="2ca29-220">Os valores de degradação variam de um baixo de 0,0 a um alto de 5,0.</span><span class="sxs-lookup"><span data-stu-id="2ca29-220">Degradation values can range from a low of 0.0 to a high of 5.0.</span></span> <span data-ttu-id="2ca29-221">Um valor de 0,5 ou menos representa degradação aceitável.</span><span class="sxs-lookup"><span data-stu-id="2ca29-221">A value of 0.5 or less represents acceptable degradation.</span></span> <span data-ttu-id="2ca29-222">Historicamente, pontuações de opções médias foram calculadas com usuários classificando a qualidade de uma chamada em uma escala de 1 a 5.</span><span class="sxs-lookup"><span data-stu-id="2ca29-222">Historically, mean options scores were calculated by having users rate the quality of a call on a scale of 1-to-5.</span></span> <span data-ttu-id="2ca29-223">No Lync Server, o Lync Server usa um conjunto de algoritmos para prever como os usuários classificaram uma chamada.</span><span class="sxs-lookup"><span data-stu-id="2ca29-223">In Lync Server, Lync Server uses a set of algorithms to predict how users would have rated a call.</span></span></p>
<p><span data-ttu-id="2ca29-p117">Os valores de degradação altos podem ser causados por congestão, falta de largura de banda, congestionamento ou interferência sem fio ou um servidor de mídia ou ponto de extremidade sobrecarregado. A alta degradação resulta em perda ou distorção de áudio.</span><span class="sxs-lookup"><span data-stu-id="2ca29-p117">High degradation values can be caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server or endpoint. High degradation results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2ca29-226"><strong>Perda de pacote </strong></span><span class="sxs-lookup"><span data-stu-id="2ca29-226"><strong>Packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="2ca29-227">Não</span><span class="sxs-lookup"><span data-stu-id="2ca29-227">No</span></span></p></td>
<td><p><span data-ttu-id="2ca29-p118">Taxa média de perda de pacotes RTP (a perda de pacotes acontece quando pacotes RTP, um protocolo usado para transmitir áudio e vídeo pela Internet, falha ao tentar alcançar seu destino). Altas taxas de perda geralmente são causadas por congestionamento, insuficiência da largura de banda, congestionamento ou interferência da rede sem fio ou um servidor de mídia sobrecarregado. A perda de pacotes normalmente resulta em distorção ou perda do áudio.</span><span class="sxs-lookup"><span data-stu-id="2ca29-p118">Average rate of RTP packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ca29-231"><strong>Tremulação (ms)</strong></span><span class="sxs-lookup"><span data-stu-id="2ca29-231"><strong>Jitter (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="2ca29-232">Não</span><span class="sxs-lookup"><span data-stu-id="2ca29-232">No</span></span></p></td>
<td><p><span data-ttu-id="2ca29-233">Tremulação média detectada entre chegadas de pacote RTP.</span><span class="sxs-lookup"><span data-stu-id="2ca29-233">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="2ca29-234">(Tremulação é uma medida do &quot;tremula&quot; de uma chamada.) Os valores de variação alta geralmente são causados por congestionamento ou por um servidor de mídia sobrecarregado e resultam em um áudio distorcido ou perdido.</span><span class="sxs-lookup"><span data-stu-id="2ca29-234">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2ca29-235"><strong>Taxa de correção oculta</strong></span><span class="sxs-lookup"><span data-stu-id="2ca29-235"><strong>Healer concealed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="2ca29-236">Não</span><span class="sxs-lookup"><span data-stu-id="2ca29-236">No</span></span></p></td>
<td><p><span data-ttu-id="2ca29-p120">Taxa média de amostras de áudio ocultas para o número total de amostras. (Uma amostra de áudio oculta é uma técnica usada para suavizar a transição abrupta que normalmente seria causada por pacotes de rede descartados.) Valores altos indicam níveis consideráveis de perda de ocultação aplicada causada por perda de pacote ou tremulação e resulta na perda ou distorção de áudio.</span><span class="sxs-lookup"><span data-stu-id="2ca29-p120">Average ratio of concealed audio samples to the total to the total number of samples. (A concealed audio sample is a technique used to smooth out the abrupt transition that would usually be caused by dropped network packets.) High values indicate significant levels of loss concealment applied caused by packet loss or jitter, and results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ca29-239"><strong>Taxa de correção estendida</strong></span><span class="sxs-lookup"><span data-stu-id="2ca29-239"><strong>Healer stretched ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="2ca29-240">Não</span><span class="sxs-lookup"><span data-stu-id="2ca29-240">No</span></span></p></td>
<td><p><span data-ttu-id="2ca29-p121">Taxa média de amostras de áudio estendidas para o número total de amostras. (Áudio estendido é o áudio que foi expandido a fim de ajudar a manter a qualidade da chamada quando um pacote de rede descartado é detectado.) Valores altos indicam níveis significativos de extensão de amostra causada por tremulação e resultam em um som robótico ou distorcido.</span><span class="sxs-lookup"><span data-stu-id="2ca29-p121">Average ratio of stretched audio samples to the total to the total number of samples. (Stretched audio is audio that has been expanded to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample stretching caused by jitter, and result in audio sounding robotic or distorted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2ca29-243"><strong>Taxa de correção compactada</strong></span><span class="sxs-lookup"><span data-stu-id="2ca29-243"><strong>Healer compressed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="2ca29-244">Não</span><span class="sxs-lookup"><span data-stu-id="2ca29-244">No</span></span></p></td>
<td><p><span data-ttu-id="2ca29-p122">Taxa média de amostras de áudio compactadas para o número total de amostras (áudio compactado é o áudio que foi comprimido para ajudar a manter a qualidade da chamada quando um pacote de rede ignorado foi detectado). Altos valores indicam níveis significativos de compressão de amostras causados por tremulação, o que resulta em áudio acelerado ou distorcido.</span><span class="sxs-lookup"><span data-stu-id="2ca29-p122">Average ratio of compressed audio samples to the total number of samples. (Compressed audio is audio that has been compressed to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample compression caused by jitter, and result in audio sounding accelerated or distorted.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="media-quality-summary-report-metrics-video-call-summary"></a><span data-ttu-id="2ca29-247">Métricas do Relatório de Resumo de Qualidade de Mídia: Resumo da chamada de vídeo</span><span class="sxs-lookup"><span data-stu-id="2ca29-247">Media Quality Summary Report Metrics: Video Call Summary</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2ca29-248">Nome</span><span class="sxs-lookup"><span data-stu-id="2ca29-248">Name</span></span></th>
<th><span data-ttu-id="2ca29-249">É possível classificar este item?</span><span class="sxs-lookup"><span data-stu-id="2ca29-249">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="2ca29-250">Descrição</span><span class="sxs-lookup"><span data-stu-id="2ca29-250">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2ca29-251"><strong>Tipo de Chamada/Tipo de Ponto de Extremidade</strong></span><span class="sxs-lookup"><span data-stu-id="2ca29-251"><strong>Call type/Endpoint type</strong></span></span></p></td>
<td><p><span data-ttu-id="2ca29-252">Não</span><span class="sxs-lookup"><span data-stu-id="2ca29-252">No</span></span></p></td>
<td><p><span data-ttu-id="2ca29-p123">Ao clicar neste item, o relatório mostra informações detalhadas sobre chamadas baseadas no tipo escolhido. Tipos de chamada incluem:</span><span class="sxs-lookup"><span data-stu-id="2ca29-p123">When you click this item, the report shows detailed information about calls based on that type. Call types include:</span></span></p>
<ul>
<li><p><span data-ttu-id="2ca29-255">Chamadas Ponto a Ponto de UC</span><span class="sxs-lookup"><span data-stu-id="2ca29-255">UC Peer-to-Peer Calls</span></span></p></li>
<li><p><span data-ttu-id="2ca29-256">Sessões de Conferência de UC</span><span class="sxs-lookup"><span data-stu-id="2ca29-256">UC Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="2ca29-257">Sessões de Conferência PSTN</span><span class="sxs-lookup"><span data-stu-id="2ca29-257">PSTN Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="2ca29-258">Chamadas PSTN: Desvio de Mídia</span><span class="sxs-lookup"><span data-stu-id="2ca29-258">PSTN Calls: Media Bypass</span></span></p></li>
<li><p><span data-ttu-id="2ca29-259">Chamadas PSTN (Não Ignorar): Trecho de UC</span><span class="sxs-lookup"><span data-stu-id="2ca29-259">PSTN Calls (Non-Bypass): UC Leg</span></span></p></li>
<li><p><span data-ttu-id="2ca29-260">Chamadas PSTN (Não Ignorar): Trecho de Gateway</span><span class="sxs-lookup"><span data-stu-id="2ca29-260">PSTN Calls (Non-Bypass): Gateway Leg</span></span></p></li>
<li><p><span data-ttu-id="2ca29-261">Outros Tipos de Chamada</span><span class="sxs-lookup"><span data-stu-id="2ca29-261">Other Call Types</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ca29-262"><strong>Volume da chamada</strong></span><span class="sxs-lookup"><span data-stu-id="2ca29-262"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="2ca29-263">Não</span><span class="sxs-lookup"><span data-stu-id="2ca29-263">No</span></span></p></td>
<td><p><span data-ttu-id="2ca29-264">Número total de chamadas por tipo de chamada.</span><span class="sxs-lookup"><span data-stu-id="2ca29-264">Total number of calls per call type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2ca29-265"><strong>Percentual de chamadas ruins</strong></span><span class="sxs-lookup"><span data-stu-id="2ca29-265"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="2ca29-266">Não</span><span class="sxs-lookup"><span data-stu-id="2ca29-266">No</span></span></p></td>
<td><p><span data-ttu-id="2ca29-p124">Número total de chamadas classificadas como ruins. Uma chamada ruim é qualquer chamada em que no mínimo uma das métricas medidas excedeu o valor permitido (por exemplo, uma chamada com tremulação excessiva).</span><span class="sxs-lookup"><span data-stu-id="2ca29-p124">Total number of calls classified as poor. A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ca29-269"><strong>Volume de chamadas (chamadas sem fio)</strong></span><span class="sxs-lookup"><span data-stu-id="2ca29-269"><strong>Call volume (wireless call)</strong></span></span></p></td>
<td><p><span data-ttu-id="2ca29-270">Não</span><span class="sxs-lookup"><span data-stu-id="2ca29-270">No</span></span></p></td>
<td><p><span data-ttu-id="2ca29-271">Número total de chamadas que usaram uma conexão sem fio.</span><span class="sxs-lookup"><span data-stu-id="2ca29-271">Total number of calls that used a wireless connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2ca29-272"><strong>Volume de chamadas (chamadas VPN)</strong></span><span class="sxs-lookup"><span data-stu-id="2ca29-272"><strong>Call volume (VPN call)</strong></span></span></p></td>
<td><p><span data-ttu-id="2ca29-273">Não</span><span class="sxs-lookup"><span data-stu-id="2ca29-273">No</span></span></p></td>
<td><p><span data-ttu-id="2ca29-274">Número total de chamadas que usaram uma conexão VPN.</span><span class="sxs-lookup"><span data-stu-id="2ca29-274">Total number of calls that used a VPN connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ca29-275"><strong>Volume de chamadas (chamadas externas)</strong></span><span class="sxs-lookup"><span data-stu-id="2ca29-275"><strong>Call volume (external call)</strong></span></span></p></td>
<td><p><span data-ttu-id="2ca29-276">Não</span><span class="sxs-lookup"><span data-stu-id="2ca29-276">No</span></span></p></td>
<td><p><span data-ttu-id="2ca29-277">Número de chamadas que usaram uma conexão externa (ou seja, uma conexão fora da rede interna).</span><span class="sxs-lookup"><span data-stu-id="2ca29-277">Number of calls that used an external connection (that is, a connection outside the internal network).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2ca29-278"><strong>Taxa de bits média (Kbits/s)</strong></span><span class="sxs-lookup"><span data-stu-id="2ca29-278"><strong>Avg bit-rate (Kbits/s)</strong></span></span></p></td>
<td><p><span data-ttu-id="2ca29-279">Não</span><span class="sxs-lookup"><span data-stu-id="2ca29-279">No</span></span></p></td>
<td><p><span data-ttu-id="2ca29-280">Taxa de bits média (em quilobytes por segundo).</span><span class="sxs-lookup"><span data-stu-id="2ca29-280">Average video bit rate (in kilobits per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ca29-281"><strong>% de taxa de bits baixa</strong></span><span class="sxs-lookup"><span data-stu-id="2ca29-281"><strong>Low bit-rate %</strong></span></span></p></td>
<td><p><span data-ttu-id="2ca29-282">Não</span><span class="sxs-lookup"><span data-stu-id="2ca29-282">No</span></span></p></td>
<td><p><span data-ttu-id="2ca29-283">Porcentagem da chamada onde a taxa de bits foi baixa.</span><span class="sxs-lookup"><span data-stu-id="2ca29-283">Percentage of the call where the bit rate was low.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2ca29-284"><strong>Perda de pacote de saída</strong></span><span class="sxs-lookup"><span data-stu-id="2ca29-284"><strong>Outbound packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="2ca29-285">Não</span><span class="sxs-lookup"><span data-stu-id="2ca29-285">No</span></span></p></td>
<td><p><span data-ttu-id="2ca29-p125">Perda de pacotes do Protocolo de transporte em tempo real (RTP) para pacotes enviados. (A perda de pacotes ocorre quando pacotes RTP, um protocolo usado para transmitir áudio e vídeo pela internet, falha ao tentar alcançar seu destino). Altas taxas de perda geralmente são causadas por congestionamento, insuficiência da largura de banda, congestionamento ou interferência na rede sem fio ou um servidor de mídia sobrecarregado. A perda de pacotes normalmente resulta em distorção ou perda de áudio.</span><span class="sxs-lookup"><span data-stu-id="2ca29-p125">Real-Time Transport Protocol (RTP) packet loss for outbound packets. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ca29-289"><strong>% de quadros congelados</strong></span><span class="sxs-lookup"><span data-stu-id="2ca29-289"><strong>Frozen frame %</strong></span></span></p></td>
<td><p><span data-ttu-id="2ca29-290">Não</span><span class="sxs-lookup"><span data-stu-id="2ca29-290">No</span></span></p></td>
<td><p><span data-ttu-id="2ca29-p126">Porcentagem de quadros "congelados". Em um quadro congelado, o vídeo não avança enquanto a parte de áudio da chamada prossegue.</span><span class="sxs-lookup"><span data-stu-id="2ca29-p126">Percentage of “frozen” frames. In a frozen frame, the video stops advancing while the audio portion of the call continues.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2ca29-293"><strong>Taxa de quadros média de saída</strong></span><span class="sxs-lookup"><span data-stu-id="2ca29-293"><strong>Outbound avg frame rate</strong></span></span></p></td>
<td><p><span data-ttu-id="2ca29-294">Não</span><span class="sxs-lookup"><span data-stu-id="2ca29-294">No</span></span></p></td>
<td><p><span data-ttu-id="2ca29-295">Taxa de quadros média para transmissões de saída durante a chamada.</span><span class="sxs-lookup"><span data-stu-id="2ca29-295">Average frame rate for outbound transmissions during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ca29-296"><strong>Taxa de quadros média de entrada</strong></span><span class="sxs-lookup"><span data-stu-id="2ca29-296"><strong>Inbound avg frame rate</strong></span></span></p></td>
<td><p><span data-ttu-id="2ca29-297">Não</span><span class="sxs-lookup"><span data-stu-id="2ca29-297">No</span></span></p></td>
<td><p><span data-ttu-id="2ca29-298">Taxa de quadros média para transmissões de entrada durante a chamada.</span><span class="sxs-lookup"><span data-stu-id="2ca29-298">Average frame rate for incoming transmissions during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2ca29-299"><strong>% de taxa de quadros baixa de entrada</strong></span><span class="sxs-lookup"><span data-stu-id="2ca29-299"><strong>Inbound low frame rate %</strong></span></span></p></td>
<td><p><span data-ttu-id="2ca29-300">Não</span><span class="sxs-lookup"><span data-stu-id="2ca29-300">No</span></span></p></td>
<td><p><span data-ttu-id="2ca29-301">Porcentagem da chamada onde a taxa de bits foi baixa para vídeo de entrada.</span><span class="sxs-lookup"><span data-stu-id="2ca29-301">Percentage of the call where the bit rate for incoming video was low.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ca29-302"><strong>% de integridade do cliente</strong></span><span class="sxs-lookup"><span data-stu-id="2ca29-302"><strong>Client health %</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2ca29-303">Indica o estado relativo do dispositivo do cliente durante a chamada.</span><span class="sxs-lookup"><span data-stu-id="2ca29-303">Indicates the relative health of the client device during the call.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="media-quality-summary-report-metrics-application-sharing-call-summary"></a><span data-ttu-id="2ca29-304">Métricas do Relatório de resumo de qualidade de mídia: Resumo de chamada de compartilhamento de aplicativos</span><span class="sxs-lookup"><span data-stu-id="2ca29-304">Media Quality Summary Report Metrics: Application Sharing Call Summary</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2ca29-305">Nome</span><span class="sxs-lookup"><span data-stu-id="2ca29-305">Name</span></span></th>
<th><span data-ttu-id="2ca29-306">É possível classificar este item?</span><span class="sxs-lookup"><span data-stu-id="2ca29-306">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="2ca29-307">Descrição</span><span class="sxs-lookup"><span data-stu-id="2ca29-307">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2ca29-308"><strong>Tipo de Chamada/Tipo de Ponto de Extremidade</strong></span><span class="sxs-lookup"><span data-stu-id="2ca29-308"><strong>Call type/Endpoint type</strong></span></span></p></td>
<td><p><span data-ttu-id="2ca29-309">Não</span><span class="sxs-lookup"><span data-stu-id="2ca29-309">No</span></span></p></td>
<td><p><span data-ttu-id="2ca29-p127">Ao clicar neste item, o relatório mostra informações detalhadas sobre chamadas baseadas no tipo escolhido. Tipos de chamada incluem:</span><span class="sxs-lookup"><span data-stu-id="2ca29-p127">When you click this item, the report shows detailed information about calls based on that type. Call types include:</span></span></p>
<ul>
<li><p><span data-ttu-id="2ca29-312">Chamadas Ponto a Ponto de UC</span><span class="sxs-lookup"><span data-stu-id="2ca29-312">UC Peer-to-Peer Calls</span></span></p></li>
<li><p><span data-ttu-id="2ca29-313">Sessões de Conferência de UC</span><span class="sxs-lookup"><span data-stu-id="2ca29-313">UC Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="2ca29-314">Sessões de Conferência PSTN</span><span class="sxs-lookup"><span data-stu-id="2ca29-314">PSTN Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="2ca29-315">Chamadas PSTN: Desvio de Mídia</span><span class="sxs-lookup"><span data-stu-id="2ca29-315">PSTN Calls: Media Bypass</span></span></p></li>
<li><p><span data-ttu-id="2ca29-316">Chamadas PSTN (Não Ignorar): Trecho de UC</span><span class="sxs-lookup"><span data-stu-id="2ca29-316">PSTN Calls (Non-Bypass): UC Leg</span></span></p></li>
<li><p><span data-ttu-id="2ca29-317">Chamadas PSTN (Não Ignorar): Trecho de Gateway</span><span class="sxs-lookup"><span data-stu-id="2ca29-317">PSTN Calls (Non-Bypass): Gateway Leg</span></span></p></li>
<li><p><span data-ttu-id="2ca29-318">Outros Tipos de Chamada</span><span class="sxs-lookup"><span data-stu-id="2ca29-318">Other Call Types</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ca29-319"><strong>Volume da chamada</strong></span><span class="sxs-lookup"><span data-stu-id="2ca29-319"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="2ca29-320">Não</span><span class="sxs-lookup"><span data-stu-id="2ca29-320">No</span></span></p></td>
<td><p><span data-ttu-id="2ca29-321">Número total de chamadas por tipo de chamada.</span><span class="sxs-lookup"><span data-stu-id="2ca29-321">Total number of calls per call type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2ca29-322"><strong>Percentual de chamadas ruins</strong></span><span class="sxs-lookup"><span data-stu-id="2ca29-322"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="2ca29-323">Não</span><span class="sxs-lookup"><span data-stu-id="2ca29-323">No</span></span></p></td>
<td><p><span data-ttu-id="2ca29-p128">Número total de chamadas classificadas como ruins. Uma chamada ruim é qualquer chamada em que no mínimo uma das métricas medidas excedeu o valor permitido (por exemplo, uma chamada com tremulação excessiva).</span><span class="sxs-lookup"><span data-stu-id="2ca29-p128">Total number of calls classified as poor. A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ca29-326"><strong>Volume de chamadas (chamadas sem fio)</strong></span><span class="sxs-lookup"><span data-stu-id="2ca29-326"><strong>Call volume (wireless call)</strong></span></span></p></td>
<td><p><span data-ttu-id="2ca29-327">Não</span><span class="sxs-lookup"><span data-stu-id="2ca29-327">No</span></span></p></td>
<td><p><span data-ttu-id="2ca29-328">Número total de chamadas que usaram uma conexão sem fio.</span><span class="sxs-lookup"><span data-stu-id="2ca29-328">Total number of calls that used a wireless connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2ca29-329"><strong>Volume de chamadas (chamadas VPN)</strong></span><span class="sxs-lookup"><span data-stu-id="2ca29-329"><strong>Call volume (VPN call)</strong></span></span></p></td>
<td><p><span data-ttu-id="2ca29-330">Não</span><span class="sxs-lookup"><span data-stu-id="2ca29-330">No</span></span></p></td>
<td><p><span data-ttu-id="2ca29-331">Número total de chamadas que usaram uma conexão VPN.</span><span class="sxs-lookup"><span data-stu-id="2ca29-331">Total number of calls that used a VPN connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ca29-332"><strong>Volume de chamadas (chamadas externas)</strong></span><span class="sxs-lookup"><span data-stu-id="2ca29-332"><strong>Call volume (external call)</strong></span></span></p></td>
<td><p><span data-ttu-id="2ca29-333">Não</span><span class="sxs-lookup"><span data-stu-id="2ca29-333">No</span></span></p></td>
<td><p><span data-ttu-id="2ca29-334">Número de chamadas que usaram uma conexão externa (ou seja, uma conexão fora da rede interna).</span><span class="sxs-lookup"><span data-stu-id="2ca29-334">Number of calls that used an external connection (that is, a connection outside the internal network).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2ca29-335"><strong>Tremulação (ms)</strong></span><span class="sxs-lookup"><span data-stu-id="2ca29-335"><strong>Jitter (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="2ca29-336">Não</span><span class="sxs-lookup"><span data-stu-id="2ca29-336">No</span></span></p></td>
<td><p><span data-ttu-id="2ca29-337">Tremulação média detectada entre chegadas de pacote RTP.</span><span class="sxs-lookup"><span data-stu-id="2ca29-337">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="2ca29-338">(Tremulação é uma medida do &quot;tremula&quot; de uma chamada.) Os valores de variação alta geralmente são causados por congestionamento ou por um servidor de mídia sobrecarregado e resultam em um áudio distorcido ou perdido.</span><span class="sxs-lookup"><span data-stu-id="2ca29-338">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ca29-339"><strong>Unidirecional relativo médio</strong></span><span class="sxs-lookup"><span data-stu-id="2ca29-339"><strong>Avg. relative one way</strong></span></span></p></td>
<td><p><span data-ttu-id="2ca29-340">Não</span><span class="sxs-lookup"><span data-stu-id="2ca29-340">No</span></span></p></td>
<td><p><span data-ttu-id="2ca29-p130">Atraso unidirecional relativo médio entre dois pontos de extremidade de mídia. Esta é uma medida de latência de salto único.</span><span class="sxs-lookup"><span data-stu-id="2ca29-p130">Average relative one-way delay between two media endpoints. This is a single-hop latency measure.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2ca29-343"><strong>Latência média de processamento lado a lado RDP</strong></span><span class="sxs-lookup"><span data-stu-id="2ca29-343"><strong>Avg. RDP tile processing latency</strong></span></span></p></td>
<td><p><span data-ttu-id="2ca29-344">Não</span><span class="sxs-lookup"><span data-stu-id="2ca29-344">No</span></span></p></td>
<td><p><span data-ttu-id="2ca29-345">A latência média de processamento lado a lado RDP no Servidor de Conferência AS durante a sessão de visualização.</span><span class="sxs-lookup"><span data-stu-id="2ca29-345">The average RDP tile processing latency in the AS Conferencing Server over the duration of the viewing session.</span></span> <span data-ttu-id="2ca29-346">Uma média alta reflete um atraso maior na experiência de visualização e inclui latência de rede.</span><span class="sxs-lookup"><span data-stu-id="2ca29-346">A high average reflects a longer delay in the viewing experience, and includes network latency.</span></span> <span data-ttu-id="2ca29-347">Um servidor de conferência sobrecarregado pode enfrentar atrasos médios maiores.</span><span class="sxs-lookup"><span data-stu-id="2ca29-347">An overloaded conferencing server may experience higher average delays.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ca29-348"><strong>% total de lado a lado estragado</strong></span><span class="sxs-lookup"><span data-stu-id="2ca29-348"><strong>Total spoiled tile %</strong></span></span></p></td>
<td><p><span data-ttu-id="2ca29-349">Não</span><span class="sxs-lookup"><span data-stu-id="2ca29-349">No</span></span></p></td>
<td><p><span data-ttu-id="2ca29-350">A porcentagem total de lado a lado estragados.</span><span class="sxs-lookup"><span data-stu-id="2ca29-350">Total percentage of spoiled RDP tiles.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

