---
title: 'Lync Server 2013: relatório de Resumo de qualidade de mídia'
description: 'Lync Server 2013: relatório de Resumo de qualidade de mídia.'
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
ms.openlocfilehash: 2616b7e3cdea9df7b004745a5c407188870903c7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558067"
---
# <a name="media-quality-summary-report-in-lync-server-2013"></a><span data-ttu-id="06bd8-103">Relatório de Resumo de qualidade de mídia no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="06bd8-103">Media Quality Summary Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="06bd8-104">_**Última modificação do tópico:** 2016-06-29_</span><span class="sxs-lookup"><span data-stu-id="06bd8-104">_**Topic Last Modified:** 2016-06-29_</span></span>

<span data-ttu-id="06bd8-105">O Relatório de resumo de qualidade de mídia é talvez a melhor maneira de analisar a qualidade das chamadas em sua organização: este relatório fornece métricas de chamada para Qualidade de Serviço (QoS) divididas nas seguintes categorias:</span><span class="sxs-lookup"><span data-stu-id="06bd8-105">The Media Quality Summary Report is perhaps your best bet for analyzing call quality in your organization: this report provides detailed Quality of Experience (QoE) call metrics broken down into the following categories:</span></span>

  - <span data-ttu-id="06bd8-106">Chamadas ponto a ponto de UC (como uma chamada do Microsoft Lync 2013 para o Microsoft Lync 2013)</span><span class="sxs-lookup"><span data-stu-id="06bd8-106">UC Peer to Peer Calls (such as a Microsoft Lync 2013 to Microsoft Lync 2013 call)</span></span>

  - <span data-ttu-id="06bd8-107">Sessões de Conferência de UC</span><span class="sxs-lookup"><span data-stu-id="06bd8-107">UC Conference Sessions</span></span>

  - <span data-ttu-id="06bd8-108">Sessões de Conferência PSTN</span><span class="sxs-lookup"><span data-stu-id="06bd8-108">PSTN Conference Sessions</span></span>

  - <span data-ttu-id="06bd8-109">Chamadas PSTN: Desvio de Mídia</span><span class="sxs-lookup"><span data-stu-id="06bd8-109">PSTN Calls: Media Bypass</span></span>

  - <span data-ttu-id="06bd8-110">Chamadas PSTN (Não Ignorar): Trecho de UC</span><span class="sxs-lookup"><span data-stu-id="06bd8-110">PSTN Calls (Non-Bypass): UC Leg</span></span>

  - <span data-ttu-id="06bd8-111">Chamadas PSTN (Não Ignorar): Trecho de Gateway</span><span class="sxs-lookup"><span data-stu-id="06bd8-111">PSTN Calls (Non-Bypass): Gateway Leg</span></span>

  - <span data-ttu-id="06bd8-112">Outros Tipos de Chamada</span><span class="sxs-lookup"><span data-stu-id="06bd8-112">Other Call Types</span></span>

<span data-ttu-id="06bd8-113">Ao abrir pela primeira vez o relatório, você verá informações resumidas para cada uma das categorias.</span><span class="sxs-lookup"><span data-stu-id="06bd8-113">When you first open the report, you see summary information for each of these categories.</span></span> <span data-ttu-id="06bd8-114">Sem sair do relatório, você pode expandir cada categoria para examinar subcategorias como chamadas feitas do Office Communicator 2007 R2 para o Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="06bd8-114">Without leaving the report, you can expand each category to look at subcategories such as calls made from Office Communicator 2007 R2 to Lync 2013.</span></span> <span data-ttu-id="06bd8-115">Por sua vez, você pode ver os detalhes de cada chamada feita dentro dessa subcategoria.</span><span class="sxs-lookup"><span data-stu-id="06bd8-115">In turn, you can then drill down into these subcategories to see details about each call made within that subcategory.</span></span>

<span data-ttu-id="06bd8-116">No Microsoft Lync Server 2013, o relatório de Resumo de qualidade de mídia divide ainda mais os dados em três tipos de chamadas: chamadas de áudio, chamadas de vídeo e chamadas de compartilhamento de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="06bd8-116">In Microsoft Lync Server 2013 the Media Quality Summary Report further breaks the data down into three call types: audio calls, video calls, and application sharing calls.</span></span> <span data-ttu-id="06bd8-117">Cada tipo de chamada tem sua própria seção no relatório, e seu próprio conjunto de métricas de chamadas.</span><span class="sxs-lookup"><span data-stu-id="06bd8-117">Each call type has its own section in the report, and its own custom set of call metrics.</span></span>

<span data-ttu-id="06bd8-118">O Relatório de resumo de qualidade de mídia também permite aplicar filtros que permitem comparar a qualidade de chamada de chamadas com fio em relação a chamadas sem fio, chamadas internas x chamadas externas e chamadas VPN x chamadas não VPN.</span><span class="sxs-lookup"><span data-stu-id="06bd8-118">The Media Quality Summary Report also allows you to apply filters that enable you to compare the call quality of wired calls vs. wireless calls, internal calls vs. external calls, and VPN calls vs. non-VPN calls.</span></span>

<div>

## <a name="accessing-the-media-quality-summary-report"></a><span data-ttu-id="06bd8-119">Como acessar o Relatório de resumo de qualidade de mídia</span><span class="sxs-lookup"><span data-stu-id="06bd8-119">Accessing the Media Quality Summary Report</span></span>

<span data-ttu-id="06bd8-120">O Relatório de resumo de qualidade de mídia é acessado a partir da página inicial dos Relatórios de Monitoramento.</span><span class="sxs-lookup"><span data-stu-id="06bd8-120">The Media Quality Summary Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="06bd8-121">Você pode fazer uma busca detalhada no [relatório de lista de chamadas no Lync Server 2013](lync-server-2013-call-list-report.md) clicando em uma das seguintes métricas:</span><span class="sxs-lookup"><span data-stu-id="06bd8-121">You can drill down to the [Call List Report in Lync Server 2013](lync-server-2013-call-list-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="06bd8-122">Volume da chamada</span><span class="sxs-lookup"><span data-stu-id="06bd8-122">Call volume</span></span>

  - <span data-ttu-id="06bd8-123">Percentual de chamadas ruins</span><span class="sxs-lookup"><span data-stu-id="06bd8-123">Poor call percentage</span></span>

<span data-ttu-id="06bd8-124">Além disso, você pode acessar o Relatório de distribuição de métricas de qualidade de mídia clicando em uma das seguintes métricas de chamada de áudio:</span><span class="sxs-lookup"><span data-stu-id="06bd8-124">In addition, you can access the Media Quality Metrics Distribution Report by clicking any of the following audio call metrics:</span></span>

  - <span data-ttu-id="06bd8-125">Viagem de ida e volta (ms)</span><span class="sxs-lookup"><span data-stu-id="06bd8-125">Round trip (ms)</span></span>

  - <span data-ttu-id="06bd8-126">Degradação (MOS)</span><span class="sxs-lookup"><span data-stu-id="06bd8-126">Degradation (MOS)</span></span>

  - <span data-ttu-id="06bd8-127">Perda de pacote</span><span class="sxs-lookup"><span data-stu-id="06bd8-127">Packet loss</span></span>

  - <span data-ttu-id="06bd8-128">Tremulação (ms)</span><span class="sxs-lookup"><span data-stu-id="06bd8-128">Jitter (ms)</span></span>

  - <span data-ttu-id="06bd8-129">Taxa de correção oculta</span><span class="sxs-lookup"><span data-stu-id="06bd8-129">Healer concealed ratio</span></span>

  - <span data-ttu-id="06bd8-130">Taxa de correção estendida</span><span class="sxs-lookup"><span data-stu-id="06bd8-130">Healer stretched ratio</span></span>

  - <span data-ttu-id="06bd8-131">Taxa de correção compactada</span><span class="sxs-lookup"><span data-stu-id="06bd8-131">Healer compressed ratio</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="06bd8-132">Filtros</span><span class="sxs-lookup"><span data-stu-id="06bd8-132">Filters</span></span>

<span data-ttu-id="06bd8-p104">Filtros fornecem uma forma de retornar um conjunto de dados mais focado ou exibir os dados retornados de diferentes formas. Por exemplo, o Relatório de Resumo de Qualidade de Mídia permite filtrar os dados retornados por informações como tipo de acesso (ou seja, acesso interno vs. acesso externo) ou por conexão de rede com fio/sem fio. Você também pode escolher como os dados serão agrupados. Neste caso, as chamadas são agrupadas por hora, dia, semana ou mês.</span><span class="sxs-lookup"><span data-stu-id="06bd8-p104">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Media Quality Summary Report enables you to filter the returned data by such things as access type (that is, interval access vs. external access) or by wired/wireless network connection. You can also choose how data should be grouped. In this case, calls are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="06bd8-137">A tabela a seguir lista os filtros que podem ser usados com o Relatório de Resumo de Qualidade de Mídia.</span><span class="sxs-lookup"><span data-stu-id="06bd8-137">The following table lists the filters that you can use with the Media Quality Summary Report.</span></span>

### <a name="media-quality-summary-report-filters"></a><span data-ttu-id="06bd8-138">Filtros do Relatório de Resumo de Qualidade de Mídia</span><span class="sxs-lookup"><span data-stu-id="06bd8-138">Media Quality Summary Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="06bd8-139">Nome</span><span class="sxs-lookup"><span data-stu-id="06bd8-139">Name</span></span></th>
<th><span data-ttu-id="06bd8-140">Descrição</span><span class="sxs-lookup"><span data-stu-id="06bd8-140">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="06bd8-141"><strong>De</strong></span><span class="sxs-lookup"><span data-stu-id="06bd8-141"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="06bd8-p105">Data/hora inicial para o intervalo de tempo. Para exibir os dados por hora, insira a data e hora inicial como a seguir:</span><span class="sxs-lookup"><span data-stu-id="06bd8-p105">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="06bd8-144">7/7/2012 13:00 horas</span><span class="sxs-lookup"><span data-stu-id="06bd8-144">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="06bd8-p106">Se você não inserir uma hora inicial, o relatório começa automaticamente as 12:00 AM no dia especificado. Para exibir os dados por dia, insira apenas a data:</span><span class="sxs-lookup"><span data-stu-id="06bd8-p106">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="06bd8-147">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="06bd8-147">7/7/2012</span></span></p>
<p><span data-ttu-id="06bd8-148">Para exibir por semana ou mês, insira uma data que está dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):</span><span class="sxs-lookup"><span data-stu-id="06bd8-148">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="06bd8-149">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="06bd8-149">7/3/2012</span></span></p>
<p><span data-ttu-id="06bd8-150">As semanas são sempre de domingo a sábado.</span><span class="sxs-lookup"><span data-stu-id="06bd8-150">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="06bd8-151"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="06bd8-151"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="06bd8-p107">Data/hora final para o intervalo de tempo. Para exibir os dados por hora, insira a data e hora final como a seguir:</span><span class="sxs-lookup"><span data-stu-id="06bd8-p107">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="06bd8-154">7/7/2012 13:00 horas</span><span class="sxs-lookup"><span data-stu-id="06bd8-154">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="06bd8-p108">Se você não inserir uma hora final, o relatório termina automaticamente as 12:00 AM no dia especificado. Para exibir os dados por dia, insira apenas a data:</span><span class="sxs-lookup"><span data-stu-id="06bd8-p108">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="06bd8-157">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="06bd8-157">7/7/2012</span></span></p>
<p><span data-ttu-id="06bd8-158">Para exibir por semana ou mês, insira uma data que está dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):</span><span class="sxs-lookup"><span data-stu-id="06bd8-158">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="06bd8-159">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="06bd8-159">7/3/2012</span></span></p>
<p><span data-ttu-id="06bd8-160">As semanas sempre vão de domingo a sábado.</span><span class="sxs-lookup"><span data-stu-id="06bd8-160">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="06bd8-161"><strong>Tipo de acesso</strong></span><span class="sxs-lookup"><span data-stu-id="06bd8-161"><strong>Access type</strong></span></span></p></td>
<td><p><span data-ttu-id="06bd8-p109">Indica se um cliente estava conectado na rede interna ou na rede externa quando a chamada foi realizada. Selecione um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="06bd8-p109">Indicates whether the client was logged on to the internal network or the external network when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="06bd8-164">Todos os</span><span class="sxs-lookup"><span data-stu-id="06bd8-164">[All]</span></span></p></li>
<li><p><span data-ttu-id="06bd8-165">Interno</span><span class="sxs-lookup"><span data-stu-id="06bd8-165">Internal</span></span></p></li>
<li><p><span data-ttu-id="06bd8-166">Externo</span><span class="sxs-lookup"><span data-stu-id="06bd8-166">External</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="06bd8-167"><strong>Tipo de rede</strong></span><span class="sxs-lookup"><span data-stu-id="06bd8-167"><strong>Network type</strong></span></span></p></td>
<td><p><span data-ttu-id="06bd8-p110">Indica o tipo de rede que o cliente estava conectado quando a chamada foi realizada. Selecione um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="06bd8-p110">Indicates the type of network the client was connected to when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="06bd8-170">Todos os</span><span class="sxs-lookup"><span data-stu-id="06bd8-170">[All]</span></span></p></li>
<li><p><span data-ttu-id="06bd8-171">Com fio</span><span class="sxs-lookup"><span data-stu-id="06bd8-171">Wired</span></span></p></li>
<li><p><span data-ttu-id="06bd8-172">Conexão</span><span class="sxs-lookup"><span data-stu-id="06bd8-172">Wireless</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="06bd8-173"><strong>VPN</strong></span><span class="sxs-lookup"><span data-stu-id="06bd8-173"><strong>VPN</strong></span></span></p></td>
<td><p><span data-ttu-id="06bd8-p111">Indica se um cliente externo estava usando uma conexão de rede privada virtual (VPN) quando a chamada foi realizada. Selecione um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="06bd8-p111">Indicates whether an external client was using a virtual private network (VPN) connection when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="06bd8-176">Todos os</span><span class="sxs-lookup"><span data-stu-id="06bd8-176">[All]</span></span></p></li>
<li><p><span data-ttu-id="06bd8-177">VPN</span><span class="sxs-lookup"><span data-stu-id="06bd8-177">VPN</span></span></p></li>
<li><p><span data-ttu-id="06bd8-178">Não VPN</span><span class="sxs-lookup"><span data-stu-id="06bd8-178">Non-VPN</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="06bd8-179">Métrica</span><span class="sxs-lookup"><span data-stu-id="06bd8-179">Metrics</span></span>

<span data-ttu-id="06bd8-180">A tabela a seguir lista as informações fornecidas no Relatório de Resumo de Qualidade de Mídia.</span><span class="sxs-lookup"><span data-stu-id="06bd8-180">The following table lists the information provided in the Media Quality Summary Report.</span></span>

### <a name="media-quality-summary-report-metrics-audio-call-summary"></a><span data-ttu-id="06bd8-181">Métricas do Relatório de Resumo de Qualidade de Mídia: Resumo da chamada de áudio</span><span class="sxs-lookup"><span data-stu-id="06bd8-181">Media Quality Summary Report Metrics: Audio Call Summary</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="06bd8-182">Nome</span><span class="sxs-lookup"><span data-stu-id="06bd8-182">Name</span></span></th>
<th><span data-ttu-id="06bd8-183">É possível classificar este item?</span><span class="sxs-lookup"><span data-stu-id="06bd8-183">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="06bd8-184">Descrição</span><span class="sxs-lookup"><span data-stu-id="06bd8-184">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="06bd8-185"><strong>Tipo de Chamada/Tipo de Ponto de Extremidade</strong></span><span class="sxs-lookup"><span data-stu-id="06bd8-185"><strong>Call type/Endpoint type</strong></span></span></p></td>
<td><p><span data-ttu-id="06bd8-186">Não</span><span class="sxs-lookup"><span data-stu-id="06bd8-186">No</span></span></p></td>
<td><p><span data-ttu-id="06bd8-p112">Ao clicar neste item, o relatório mostra informações detalhadas sobre chamadas baseadas no tipo escolhido. Tipos de chamada incluem:</span><span class="sxs-lookup"><span data-stu-id="06bd8-p112">When you click this item, the report shows detailed information about calls based on that type. Call types include:</span></span></p>
<ul>
<li><p><span data-ttu-id="06bd8-189">Chamadas Ponto a Ponto de UC</span><span class="sxs-lookup"><span data-stu-id="06bd8-189">UC Peer-to-Peer Calls</span></span></p></li>
<li><p><span data-ttu-id="06bd8-190">Sessões de Conferência de UC</span><span class="sxs-lookup"><span data-stu-id="06bd8-190">UC Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="06bd8-191">Sessões de Conferência PSTN</span><span class="sxs-lookup"><span data-stu-id="06bd8-191">PSTN Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="06bd8-192">Chamadas PSTN: Desvio de Mídia</span><span class="sxs-lookup"><span data-stu-id="06bd8-192">PSTN Calls: Media Bypass</span></span></p></li>
<li><p><span data-ttu-id="06bd8-193">Chamadas PSTN (Não Ignorar): Trecho de UC</span><span class="sxs-lookup"><span data-stu-id="06bd8-193">PSTN Calls (Non-Bypass): UC Leg</span></span></p></li>
<li><p><span data-ttu-id="06bd8-194">Chamadas PSTN (Não Ignorar): Trecho de Gateway</span><span class="sxs-lookup"><span data-stu-id="06bd8-194">PSTN Calls (Non-Bypass): Gateway Leg</span></span></p></li>
<li><p><span data-ttu-id="06bd8-195">Outros Tipos de Chamada</span><span class="sxs-lookup"><span data-stu-id="06bd8-195">Other Call Types</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="06bd8-196"><strong>Volume da chamada</strong></span><span class="sxs-lookup"><span data-stu-id="06bd8-196"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="06bd8-197">Não</span><span class="sxs-lookup"><span data-stu-id="06bd8-197">No</span></span></p></td>
<td><p><span data-ttu-id="06bd8-198">Número total de chamadas por tipo de chamada.</span><span class="sxs-lookup"><span data-stu-id="06bd8-198">Total number of calls per call type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="06bd8-199"><strong>Percentual de chamadas ruins</strong></span><span class="sxs-lookup"><span data-stu-id="06bd8-199"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="06bd8-200">Não</span><span class="sxs-lookup"><span data-stu-id="06bd8-200">No</span></span></p></td>
<td><p><span data-ttu-id="06bd8-p113">Número total de chamadas classificadas como ruins. Uma chamada ruim é qualquer chamada em que no mínimo uma das métricas medidas excedeu o valor permitido (por exemplo, uma chamada com tremulação excessiva).</span><span class="sxs-lookup"><span data-stu-id="06bd8-p113">Total number of calls classified as poor. A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="06bd8-203"><strong>Volume de chamadas (chamadas sem fio)</strong></span><span class="sxs-lookup"><span data-stu-id="06bd8-203"><strong>Call volume (wireless call)</strong></span></span></p></td>
<td><p><span data-ttu-id="06bd8-204">Não</span><span class="sxs-lookup"><span data-stu-id="06bd8-204">No</span></span></p></td>
<td><p><span data-ttu-id="06bd8-205">Número total de chamadas que usaram uma conexão sem fio.</span><span class="sxs-lookup"><span data-stu-id="06bd8-205">Total number of calls that used a wireless connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="06bd8-206"><strong>Volume de chamadas (chamadas VPN)</strong></span><span class="sxs-lookup"><span data-stu-id="06bd8-206"><strong>Call volume (VPN call)</strong></span></span></p></td>
<td><p><span data-ttu-id="06bd8-207">Não</span><span class="sxs-lookup"><span data-stu-id="06bd8-207">No</span></span></p></td>
<td><p><span data-ttu-id="06bd8-208">Número total de chamadas que usaram uma conexão VPN.</span><span class="sxs-lookup"><span data-stu-id="06bd8-208">Total number of calls that used a VPN connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="06bd8-209"><strong>Volume de chamadas (chamadas externas)</strong></span><span class="sxs-lookup"><span data-stu-id="06bd8-209"><strong>Call volume (external call)</strong></span></span></p></td>
<td><p><span data-ttu-id="06bd8-210">Não</span><span class="sxs-lookup"><span data-stu-id="06bd8-210">No</span></span></p></td>
<td><p><span data-ttu-id="06bd8-211">Número de chamadas que usaram uma conexão externa (ou seja, uma conexão fora da rede interna).</span><span class="sxs-lookup"><span data-stu-id="06bd8-211">Number of calls that used an external connection (that is, a connection outside the internal network).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="06bd8-212"><strong>Tempo de resposta (ms)</strong></span><span class="sxs-lookup"><span data-stu-id="06bd8-212"><strong>Round trip (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="06bd8-213">Não</span><span class="sxs-lookup"><span data-stu-id="06bd8-213">No</span></span></p></td>
<td><p><span data-ttu-id="06bd8-p114">Quantidade média (em milissegundos) necessária para um pacote de protocolo de transporte em tempo real (RTP) viajar para outro ponto de extremidade e voltar. Tempos de resposta de 100 milissegundos ou menos são considerados de qualidade aceitável.</span><span class="sxs-lookup"><span data-stu-id="06bd8-p114">Average amount of (in milliseconds) required for a real-time transport protocol (RTP) packet to travel to another endpoint and then back. Round-trip times of 100 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="06bd8-p115">Os valores altos de ida e volta pode ser causados por roteamento de chamada internacional, um erro de configuração de roteamento ou um servidor de mídia sobrecarregado. Tempos de ida e volta altos resultam em dificuldades com conversas de áudio em tempo real e bidirecionais.</span><span class="sxs-lookup"><span data-stu-id="06bd8-p115">High round-trip values can be caused by international call routing, a routing misconfiguration, or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="06bd8-218"><strong>Degradação (MOS)</strong></span><span class="sxs-lookup"><span data-stu-id="06bd8-218"><strong>Degradation (MOS)</strong></span></span></p></td>
<td><p><span data-ttu-id="06bd8-219">Não</span><span class="sxs-lookup"><span data-stu-id="06bd8-219">No</span></span></p></td>
<td><p><span data-ttu-id="06bd8-220">Quantidade média de degradação MOS (pontuação média de opinião) experimentada durante uma chamada.</span><span class="sxs-lookup"><span data-stu-id="06bd8-220">Average amount of mean opinion score (MOS) degradation experienced during a call.</span></span> <span data-ttu-id="06bd8-221">Os valores de degradação variam de um baixo de 0,0 a um alto de 5,0.</span><span class="sxs-lookup"><span data-stu-id="06bd8-221">Degradation values can range from a low of 0.0 to a high of 5.0.</span></span> <span data-ttu-id="06bd8-222">Um valor de 0,5 ou menos representa degradação aceitável.</span><span class="sxs-lookup"><span data-stu-id="06bd8-222">A value of 0.5 or less represents acceptable degradation.</span></span> <span data-ttu-id="06bd8-223">Historicamente, pontuações de opções médias foram calculadas com usuários classificando a qualidade de uma chamada em uma escala de 1 a 5.</span><span class="sxs-lookup"><span data-stu-id="06bd8-223">Historically, mean options scores were calculated by having users rate the quality of a call on a scale of 1-to-5.</span></span> <span data-ttu-id="06bd8-224">No Lync Server, o Lync Server usa um conjunto de algoritmos para prever como os usuários classificaram uma chamada.</span><span class="sxs-lookup"><span data-stu-id="06bd8-224">In Lync Server, Lync Server uses a set of algorithms to predict how users would have rated a call.</span></span></p>
<p><span data-ttu-id="06bd8-p117">Os valores de degradação altos podem ser causados por congestão, falta de largura de banda, congestionamento ou interferência sem fio ou um servidor de mídia ou ponto de extremidade sobrecarregado. A alta degradação resulta em perda ou distorção de áudio.</span><span class="sxs-lookup"><span data-stu-id="06bd8-p117">High degradation values can be caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server or endpoint. High degradation results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="06bd8-227"><strong>Perda de pacote </strong></span><span class="sxs-lookup"><span data-stu-id="06bd8-227"><strong>Packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="06bd8-228">Não</span><span class="sxs-lookup"><span data-stu-id="06bd8-228">No</span></span></p></td>
<td><p><span data-ttu-id="06bd8-p118">Taxa média de perda de pacotes RTP (a perda de pacotes acontece quando pacotes RTP, um protocolo usado para transmitir áudio e vídeo pela Internet, falha ao tentar alcançar seu destino). Altas taxas de perda geralmente são causadas por congestionamento, insuficiência da largura de banda, congestionamento ou interferência da rede sem fio ou um servidor de mídia sobrecarregado. A perda de pacotes normalmente resulta em distorção ou perda do áudio.</span><span class="sxs-lookup"><span data-stu-id="06bd8-p118">Average rate of RTP packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="06bd8-232"><strong>Tremulação (ms)</strong></span><span class="sxs-lookup"><span data-stu-id="06bd8-232"><strong>Jitter (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="06bd8-233">Não</span><span class="sxs-lookup"><span data-stu-id="06bd8-233">No</span></span></p></td>
<td><p><span data-ttu-id="06bd8-234">Tremulação média detectada entre chegadas de pacote RTP.</span><span class="sxs-lookup"><span data-stu-id="06bd8-234">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="06bd8-235">(Tremulação é uma medida do &quot; tremula &quot; de uma chamada.) Os valores de variação alta geralmente são causados por congestionamento ou por um servidor de mídia sobrecarregado e resultam em um áudio distorcido ou perdido.</span><span class="sxs-lookup"><span data-stu-id="06bd8-235">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="06bd8-236"><strong>Taxa de correção oculta</strong></span><span class="sxs-lookup"><span data-stu-id="06bd8-236"><strong>Healer concealed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="06bd8-237">Não</span><span class="sxs-lookup"><span data-stu-id="06bd8-237">No</span></span></p></td>
<td><p><span data-ttu-id="06bd8-p120">Taxa média de amostras de áudio ocultas para o número total de amostras. (Uma amostra de áudio oculta é uma técnica usada para suavizar a transição abrupta que normalmente seria causada por pacotes de rede descartados.) Valores altos indicam níveis consideráveis de perda de ocultação aplicada causada por perda de pacote ou tremulação e resulta na perda ou distorção de áudio.</span><span class="sxs-lookup"><span data-stu-id="06bd8-p120">Average ratio of concealed audio samples to the total to the total number of samples. (A concealed audio sample is a technique used to smooth out the abrupt transition that would usually be caused by dropped network packets.) High values indicate significant levels of loss concealment applied caused by packet loss or jitter, and results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="06bd8-240"><strong>Taxa de correção estendida</strong></span><span class="sxs-lookup"><span data-stu-id="06bd8-240"><strong>Healer stretched ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="06bd8-241">Não</span><span class="sxs-lookup"><span data-stu-id="06bd8-241">No</span></span></p></td>
<td><p><span data-ttu-id="06bd8-p121">Taxa média de amostras de áudio estendidas para o número total de amostras. (Áudio estendido é o áudio que foi expandido a fim de ajudar a manter a qualidade da chamada quando um pacote de rede descartado é detectado.) Valores altos indicam níveis significativos de extensão de amostra causada por tremulação e resultam em um som robótico ou distorcido.</span><span class="sxs-lookup"><span data-stu-id="06bd8-p121">Average ratio of stretched audio samples to the total to the total number of samples. (Stretched audio is audio that has been expanded to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample stretching caused by jitter, and result in audio sounding robotic or distorted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="06bd8-244"><strong>Taxa de correção compactada</strong></span><span class="sxs-lookup"><span data-stu-id="06bd8-244"><strong>Healer compressed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="06bd8-245">Não</span><span class="sxs-lookup"><span data-stu-id="06bd8-245">No</span></span></p></td>
<td><p><span data-ttu-id="06bd8-p122">Taxa média de amostras de áudio compactadas para o número total de amostras (áudio compactado é o áudio que foi comprimido para ajudar a manter a qualidade da chamada quando um pacote de rede ignorado foi detectado). Altos valores indicam níveis significativos de compressão de amostras causados por tremulação, o que resulta em áudio acelerado ou distorcido.</span><span class="sxs-lookup"><span data-stu-id="06bd8-p122">Average ratio of compressed audio samples to the total number of samples. (Compressed audio is audio that has been compressed to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample compression caused by jitter, and result in audio sounding accelerated or distorted.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="media-quality-summary-report-metrics-video-call-summary"></a><span data-ttu-id="06bd8-248">Métricas do Relatório de Resumo de Qualidade de Mídia: Resumo da chamada de vídeo</span><span class="sxs-lookup"><span data-stu-id="06bd8-248">Media Quality Summary Report Metrics: Video Call Summary</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="06bd8-249">Nome</span><span class="sxs-lookup"><span data-stu-id="06bd8-249">Name</span></span></th>
<th><span data-ttu-id="06bd8-250">É possível classificar este item?</span><span class="sxs-lookup"><span data-stu-id="06bd8-250">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="06bd8-251">Descrição</span><span class="sxs-lookup"><span data-stu-id="06bd8-251">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="06bd8-252"><strong>Tipo de Chamada/Tipo de Ponto de Extremidade</strong></span><span class="sxs-lookup"><span data-stu-id="06bd8-252"><strong>Call type/Endpoint type</strong></span></span></p></td>
<td><p><span data-ttu-id="06bd8-253">Não</span><span class="sxs-lookup"><span data-stu-id="06bd8-253">No</span></span></p></td>
<td><p><span data-ttu-id="06bd8-p123">Ao clicar neste item, o relatório mostra informações detalhadas sobre chamadas baseadas no tipo escolhido. Tipos de chamada incluem:</span><span class="sxs-lookup"><span data-stu-id="06bd8-p123">When you click this item, the report shows detailed information about calls based on that type. Call types include:</span></span></p>
<ul>
<li><p><span data-ttu-id="06bd8-256">Chamadas Ponto a Ponto de UC</span><span class="sxs-lookup"><span data-stu-id="06bd8-256">UC Peer-to-Peer Calls</span></span></p></li>
<li><p><span data-ttu-id="06bd8-257">Sessões de Conferência de UC</span><span class="sxs-lookup"><span data-stu-id="06bd8-257">UC Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="06bd8-258">Sessões de Conferência PSTN</span><span class="sxs-lookup"><span data-stu-id="06bd8-258">PSTN Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="06bd8-259">Chamadas PSTN: Desvio de Mídia</span><span class="sxs-lookup"><span data-stu-id="06bd8-259">PSTN Calls: Media Bypass</span></span></p></li>
<li><p><span data-ttu-id="06bd8-260">Chamadas PSTN (Não Ignorar): Trecho de UC</span><span class="sxs-lookup"><span data-stu-id="06bd8-260">PSTN Calls (Non-Bypass): UC Leg</span></span></p></li>
<li><p><span data-ttu-id="06bd8-261">Chamadas PSTN (Não Ignorar): Trecho de Gateway</span><span class="sxs-lookup"><span data-stu-id="06bd8-261">PSTN Calls (Non-Bypass): Gateway Leg</span></span></p></li>
<li><p><span data-ttu-id="06bd8-262">Outros Tipos de Chamada</span><span class="sxs-lookup"><span data-stu-id="06bd8-262">Other Call Types</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="06bd8-263"><strong>Volume da chamada</strong></span><span class="sxs-lookup"><span data-stu-id="06bd8-263"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="06bd8-264">Não</span><span class="sxs-lookup"><span data-stu-id="06bd8-264">No</span></span></p></td>
<td><p><span data-ttu-id="06bd8-265">Número total de chamadas por tipo de chamada.</span><span class="sxs-lookup"><span data-stu-id="06bd8-265">Total number of calls per call type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="06bd8-266"><strong>Percentual de chamadas ruins</strong></span><span class="sxs-lookup"><span data-stu-id="06bd8-266"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="06bd8-267">Não</span><span class="sxs-lookup"><span data-stu-id="06bd8-267">No</span></span></p></td>
<td><p><span data-ttu-id="06bd8-p124">Número total de chamadas classificadas como ruins. Uma chamada ruim é qualquer chamada em que no mínimo uma das métricas medidas excedeu o valor permitido (por exemplo, uma chamada com tremulação excessiva).</span><span class="sxs-lookup"><span data-stu-id="06bd8-p124">Total number of calls classified as poor. A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="06bd8-270"><strong>Volume de chamadas (chamadas sem fio)</strong></span><span class="sxs-lookup"><span data-stu-id="06bd8-270"><strong>Call volume (wireless call)</strong></span></span></p></td>
<td><p><span data-ttu-id="06bd8-271">Não</span><span class="sxs-lookup"><span data-stu-id="06bd8-271">No</span></span></p></td>
<td><p><span data-ttu-id="06bd8-272">Número total de chamadas que usaram uma conexão sem fio.</span><span class="sxs-lookup"><span data-stu-id="06bd8-272">Total number of calls that used a wireless connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="06bd8-273"><strong>Volume de chamadas (chamadas VPN)</strong></span><span class="sxs-lookup"><span data-stu-id="06bd8-273"><strong>Call volume (VPN call)</strong></span></span></p></td>
<td><p><span data-ttu-id="06bd8-274">Não</span><span class="sxs-lookup"><span data-stu-id="06bd8-274">No</span></span></p></td>
<td><p><span data-ttu-id="06bd8-275">Número total de chamadas que usaram uma conexão VPN.</span><span class="sxs-lookup"><span data-stu-id="06bd8-275">Total number of calls that used a VPN connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="06bd8-276"><strong>Volume de chamadas (chamadas externas)</strong></span><span class="sxs-lookup"><span data-stu-id="06bd8-276"><strong>Call volume (external call)</strong></span></span></p></td>
<td><p><span data-ttu-id="06bd8-277">Não</span><span class="sxs-lookup"><span data-stu-id="06bd8-277">No</span></span></p></td>
<td><p><span data-ttu-id="06bd8-278">Número de chamadas que usaram uma conexão externa (ou seja, uma conexão fora da rede interna).</span><span class="sxs-lookup"><span data-stu-id="06bd8-278">Number of calls that used an external connection (that is, a connection outside the internal network).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="06bd8-279"><strong>Taxa de bits média (Kbits/s)</strong></span><span class="sxs-lookup"><span data-stu-id="06bd8-279"><strong>Avg bit-rate (Kbits/s)</strong></span></span></p></td>
<td><p><span data-ttu-id="06bd8-280">Não</span><span class="sxs-lookup"><span data-stu-id="06bd8-280">No</span></span></p></td>
<td><p><span data-ttu-id="06bd8-281">Taxa de bits média (em quilobytes por segundo).</span><span class="sxs-lookup"><span data-stu-id="06bd8-281">Average video bit rate (in kilobits per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="06bd8-282"><strong>% de taxa de bits baixa</strong></span><span class="sxs-lookup"><span data-stu-id="06bd8-282"><strong>Low bit-rate %</strong></span></span></p></td>
<td><p><span data-ttu-id="06bd8-283">Não</span><span class="sxs-lookup"><span data-stu-id="06bd8-283">No</span></span></p></td>
<td><p><span data-ttu-id="06bd8-284">Porcentagem da chamada onde a taxa de bits foi baixa.</span><span class="sxs-lookup"><span data-stu-id="06bd8-284">Percentage of the call where the bit rate was low.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="06bd8-285"><strong>Perda de pacote de saída</strong></span><span class="sxs-lookup"><span data-stu-id="06bd8-285"><strong>Outbound packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="06bd8-286">Não</span><span class="sxs-lookup"><span data-stu-id="06bd8-286">No</span></span></p></td>
<td><p><span data-ttu-id="06bd8-p125">Perda de pacotes do Protocolo de transporte em tempo real (RTP) para pacotes enviados. (A perda de pacotes ocorre quando pacotes RTP, um protocolo usado para transmitir áudio e vídeo pela internet, falha ao tentar alcançar seu destino). Altas taxas de perda geralmente são causadas por congestionamento, insuficiência da largura de banda, congestionamento ou interferência na rede sem fio ou um servidor de mídia sobrecarregado. A perda de pacotes normalmente resulta em distorção ou perda de áudio.</span><span class="sxs-lookup"><span data-stu-id="06bd8-p125">Real-Time Transport Protocol (RTP) packet loss for outbound packets. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="06bd8-290"><strong>% de quadros congelados</strong></span><span class="sxs-lookup"><span data-stu-id="06bd8-290"><strong>Frozen frame %</strong></span></span></p></td>
<td><p><span data-ttu-id="06bd8-291">Não</span><span class="sxs-lookup"><span data-stu-id="06bd8-291">No</span></span></p></td>
<td><p><span data-ttu-id="06bd8-p126">Porcentagem de quadros "congelados". Em um quadro congelado, o vídeo não avança enquanto a parte de áudio da chamada prossegue.</span><span class="sxs-lookup"><span data-stu-id="06bd8-p126">Percentage of “frozen” frames. In a frozen frame, the video stops advancing while the audio portion of the call continues.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="06bd8-294"><strong>Taxa de quadros média de saída</strong></span><span class="sxs-lookup"><span data-stu-id="06bd8-294"><strong>Outbound avg frame rate</strong></span></span></p></td>
<td><p><span data-ttu-id="06bd8-295">Não</span><span class="sxs-lookup"><span data-stu-id="06bd8-295">No</span></span></p></td>
<td><p><span data-ttu-id="06bd8-296">Taxa de quadros média para transmissões de saída durante a chamada.</span><span class="sxs-lookup"><span data-stu-id="06bd8-296">Average frame rate for outbound transmissions during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="06bd8-297"><strong>Taxa de quadros média de entrada</strong></span><span class="sxs-lookup"><span data-stu-id="06bd8-297"><strong>Inbound avg frame rate</strong></span></span></p></td>
<td><p><span data-ttu-id="06bd8-298">Não</span><span class="sxs-lookup"><span data-stu-id="06bd8-298">No</span></span></p></td>
<td><p><span data-ttu-id="06bd8-299">Taxa de quadros média para transmissões de entrada durante a chamada.</span><span class="sxs-lookup"><span data-stu-id="06bd8-299">Average frame rate for incoming transmissions during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="06bd8-300"><strong>% de taxa de quadros baixa de entrada</strong></span><span class="sxs-lookup"><span data-stu-id="06bd8-300"><strong>Inbound low frame rate %</strong></span></span></p></td>
<td><p><span data-ttu-id="06bd8-301">Não</span><span class="sxs-lookup"><span data-stu-id="06bd8-301">No</span></span></p></td>
<td><p><span data-ttu-id="06bd8-302">Porcentagem da chamada onde a taxa de bits foi baixa para vídeo de entrada.</span><span class="sxs-lookup"><span data-stu-id="06bd8-302">Percentage of the call where the bit rate for incoming video was low.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="06bd8-303"><strong>% de integridade do cliente</strong></span><span class="sxs-lookup"><span data-stu-id="06bd8-303"><strong>Client health %</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="06bd8-304">Indica o estado relativo do dispositivo do cliente durante a chamada.</span><span class="sxs-lookup"><span data-stu-id="06bd8-304">Indicates the relative health of the client device during the call.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="media-quality-summary-report-metrics-application-sharing-call-summary"></a><span data-ttu-id="06bd8-305">Métricas do Relatório de resumo de qualidade de mídia: Resumo de chamada de compartilhamento de aplicativos</span><span class="sxs-lookup"><span data-stu-id="06bd8-305">Media Quality Summary Report Metrics: Application Sharing Call Summary</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="06bd8-306">Nome</span><span class="sxs-lookup"><span data-stu-id="06bd8-306">Name</span></span></th>
<th><span data-ttu-id="06bd8-307">É possível classificar este item?</span><span class="sxs-lookup"><span data-stu-id="06bd8-307">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="06bd8-308">Descrição</span><span class="sxs-lookup"><span data-stu-id="06bd8-308">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="06bd8-309"><strong>Tipo de Chamada/Tipo de Ponto de Extremidade</strong></span><span class="sxs-lookup"><span data-stu-id="06bd8-309"><strong>Call type/Endpoint type</strong></span></span></p></td>
<td><p><span data-ttu-id="06bd8-310">Não</span><span class="sxs-lookup"><span data-stu-id="06bd8-310">No</span></span></p></td>
<td><p><span data-ttu-id="06bd8-p127">Ao clicar neste item, o relatório mostra informações detalhadas sobre chamadas baseadas no tipo escolhido. Tipos de chamada incluem:</span><span class="sxs-lookup"><span data-stu-id="06bd8-p127">When you click this item, the report shows detailed information about calls based on that type. Call types include:</span></span></p>
<ul>
<li><p><span data-ttu-id="06bd8-313">Chamadas Ponto a Ponto de UC</span><span class="sxs-lookup"><span data-stu-id="06bd8-313">UC Peer-to-Peer Calls</span></span></p></li>
<li><p><span data-ttu-id="06bd8-314">Sessões de Conferência de UC</span><span class="sxs-lookup"><span data-stu-id="06bd8-314">UC Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="06bd8-315">Sessões de Conferência PSTN</span><span class="sxs-lookup"><span data-stu-id="06bd8-315">PSTN Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="06bd8-316">Chamadas PSTN: Desvio de Mídia</span><span class="sxs-lookup"><span data-stu-id="06bd8-316">PSTN Calls: Media Bypass</span></span></p></li>
<li><p><span data-ttu-id="06bd8-317">Chamadas PSTN (Não Ignorar): Trecho de UC</span><span class="sxs-lookup"><span data-stu-id="06bd8-317">PSTN Calls (Non-Bypass): UC Leg</span></span></p></li>
<li><p><span data-ttu-id="06bd8-318">Chamadas PSTN (Não Ignorar): Trecho de Gateway</span><span class="sxs-lookup"><span data-stu-id="06bd8-318">PSTN Calls (Non-Bypass): Gateway Leg</span></span></p></li>
<li><p><span data-ttu-id="06bd8-319">Outros Tipos de Chamada</span><span class="sxs-lookup"><span data-stu-id="06bd8-319">Other Call Types</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="06bd8-320"><strong>Volume da chamada</strong></span><span class="sxs-lookup"><span data-stu-id="06bd8-320"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="06bd8-321">Não</span><span class="sxs-lookup"><span data-stu-id="06bd8-321">No</span></span></p></td>
<td><p><span data-ttu-id="06bd8-322">Número total de chamadas por tipo de chamada.</span><span class="sxs-lookup"><span data-stu-id="06bd8-322">Total number of calls per call type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="06bd8-323"><strong>Percentual de chamadas ruins</strong></span><span class="sxs-lookup"><span data-stu-id="06bd8-323"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="06bd8-324">Não</span><span class="sxs-lookup"><span data-stu-id="06bd8-324">No</span></span></p></td>
<td><p><span data-ttu-id="06bd8-p128">Número total de chamadas classificadas como ruins. Uma chamada ruim é qualquer chamada em que no mínimo uma das métricas medidas excedeu o valor permitido (por exemplo, uma chamada com tremulação excessiva).</span><span class="sxs-lookup"><span data-stu-id="06bd8-p128">Total number of calls classified as poor. A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="06bd8-327"><strong>Volume de chamadas (chamadas sem fio)</strong></span><span class="sxs-lookup"><span data-stu-id="06bd8-327"><strong>Call volume (wireless call)</strong></span></span></p></td>
<td><p><span data-ttu-id="06bd8-328">Não</span><span class="sxs-lookup"><span data-stu-id="06bd8-328">No</span></span></p></td>
<td><p><span data-ttu-id="06bd8-329">Número total de chamadas que usaram uma conexão sem fio.</span><span class="sxs-lookup"><span data-stu-id="06bd8-329">Total number of calls that used a wireless connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="06bd8-330"><strong>Volume de chamadas (chamadas VPN)</strong></span><span class="sxs-lookup"><span data-stu-id="06bd8-330"><strong>Call volume (VPN call)</strong></span></span></p></td>
<td><p><span data-ttu-id="06bd8-331">Não</span><span class="sxs-lookup"><span data-stu-id="06bd8-331">No</span></span></p></td>
<td><p><span data-ttu-id="06bd8-332">Número total de chamadas que usaram uma conexão VPN.</span><span class="sxs-lookup"><span data-stu-id="06bd8-332">Total number of calls that used a VPN connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="06bd8-333"><strong>Volume de chamadas (chamadas externas)</strong></span><span class="sxs-lookup"><span data-stu-id="06bd8-333"><strong>Call volume (external call)</strong></span></span></p></td>
<td><p><span data-ttu-id="06bd8-334">Não</span><span class="sxs-lookup"><span data-stu-id="06bd8-334">No</span></span></p></td>
<td><p><span data-ttu-id="06bd8-335">Número de chamadas que usaram uma conexão externa (ou seja, uma conexão fora da rede interna).</span><span class="sxs-lookup"><span data-stu-id="06bd8-335">Number of calls that used an external connection (that is, a connection outside the internal network).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="06bd8-336"><strong>Tremulação (ms)</strong></span><span class="sxs-lookup"><span data-stu-id="06bd8-336"><strong>Jitter (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="06bd8-337">Não</span><span class="sxs-lookup"><span data-stu-id="06bd8-337">No</span></span></p></td>
<td><p><span data-ttu-id="06bd8-338">Tremulação média detectada entre chegadas de pacote RTP.</span><span class="sxs-lookup"><span data-stu-id="06bd8-338">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="06bd8-339">(Tremulação é uma medida do &quot; tremula &quot; de uma chamada.) Os valores de variação alta geralmente são causados por congestionamento ou por um servidor de mídia sobrecarregado e resultam em um áudio distorcido ou perdido.</span><span class="sxs-lookup"><span data-stu-id="06bd8-339">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="06bd8-340"><strong>Unidirecional relativo médio</strong></span><span class="sxs-lookup"><span data-stu-id="06bd8-340"><strong>Avg. relative one way</strong></span></span></p></td>
<td><p><span data-ttu-id="06bd8-341">Não</span><span class="sxs-lookup"><span data-stu-id="06bd8-341">No</span></span></p></td>
<td><p><span data-ttu-id="06bd8-p130">Atraso unidirecional relativo médio entre dois pontos de extremidade de mídia. Esta é uma medida de latência de salto único.</span><span class="sxs-lookup"><span data-stu-id="06bd8-p130">Average relative one-way delay between two media endpoints. This is a single-hop latency measure.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="06bd8-344"><strong>Latência média de processamento lado a lado RDP</strong></span><span class="sxs-lookup"><span data-stu-id="06bd8-344"><strong>Avg. RDP tile processing latency</strong></span></span></p></td>
<td><p><span data-ttu-id="06bd8-345">Não</span><span class="sxs-lookup"><span data-stu-id="06bd8-345">No</span></span></p></td>
<td><p><span data-ttu-id="06bd8-346">A latência média de processamento lado a lado RDP no Servidor de Conferência AS durante a sessão de visualização.</span><span class="sxs-lookup"><span data-stu-id="06bd8-346">The average RDP tile processing latency in the AS Conferencing Server over the duration of the viewing session.</span></span> <span data-ttu-id="06bd8-347">Uma média alta reflete um atraso maior na experiência de visualização e inclui latência de rede.</span><span class="sxs-lookup"><span data-stu-id="06bd8-347">A high average reflects a longer delay in the viewing experience, and includes network latency.</span></span> <span data-ttu-id="06bd8-348">Um servidor de conferência sobrecarregado pode enfrentar atrasos médios maiores.</span><span class="sxs-lookup"><span data-stu-id="06bd8-348">An overloaded conferencing server may experience higher average delays.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="06bd8-349"><strong>% total de lado a lado estragado</strong></span><span class="sxs-lookup"><span data-stu-id="06bd8-349"><strong>Total spoiled tile %</strong></span></span></p></td>
<td><p><span data-ttu-id="06bd8-350">Não</span><span class="sxs-lookup"><span data-stu-id="06bd8-350">No</span></span></p></td>
<td><p><span data-ttu-id="06bd8-351">A porcentagem total de lado a lado estragados.</span><span class="sxs-lookup"><span data-stu-id="06bd8-351">Total percentage of spoiled RDP tiles.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

