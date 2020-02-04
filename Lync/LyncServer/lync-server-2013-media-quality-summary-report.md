---
title: 'Lync Server 2013: relatório de Resumo de qualidade da mídia'
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
ms.openlocfilehash: 6980168a2d509bc32b9aa48f30167bca8721fef2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41766082"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="media-quality-summary-report-in-lync-server-2013"></a><span data-ttu-id="a0aff-102">Relatório de Resumo de qualidade de mídia no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a0aff-102">Media Quality Summary Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a0aff-103">_**Tópico da última modificação:** 2016-06-29_</span><span class="sxs-lookup"><span data-stu-id="a0aff-103">_**Topic Last Modified:** 2016-06-29_</span></span>

<span data-ttu-id="a0aff-104">O Relatório de resumo de qualidade de mídia é talvez a melhor maneira de analisar a qualidade das chamadas em sua organização: este relatório fornece métricas de chamada para Qualidade de Serviço (QoS) divididas nas seguintes categorias:</span><span class="sxs-lookup"><span data-stu-id="a0aff-104">The Media Quality Summary Report is perhaps your best bet for analyzing call quality in your organization: this report provides detailed Quality of Experience (QoE) call metrics broken down into the following categories:</span></span>

  - <span data-ttu-id="a0aff-105">Chamadas ponto a ponto de comunicação unificada para chamadas ponto a ponto (como o Microsoft Lync 2013 para o Microsoft Lync 2013)</span><span class="sxs-lookup"><span data-stu-id="a0aff-105">UC Peer to Peer Calls (such as a Microsoft Lync 2013 to Microsoft Lync 2013 call)</span></span>

  - <span data-ttu-id="a0aff-106">Sessões de Conferência de UC</span><span class="sxs-lookup"><span data-stu-id="a0aff-106">UC Conference Sessions</span></span>

  - <span data-ttu-id="a0aff-107">Sessões de Conferência PSTN</span><span class="sxs-lookup"><span data-stu-id="a0aff-107">PSTN Conference Sessions</span></span>

  - <span data-ttu-id="a0aff-108">Chamadas PSTN: Desvio de Mídia</span><span class="sxs-lookup"><span data-stu-id="a0aff-108">PSTN Calls: Media Bypass</span></span>

  - <span data-ttu-id="a0aff-109">Chamadas PSTN (Não Ignorar): Trecho de UC</span><span class="sxs-lookup"><span data-stu-id="a0aff-109">PSTN Calls (Non-Bypass): UC Leg</span></span>

  - <span data-ttu-id="a0aff-110">Chamadas PSTN (Não Ignorar): Trecho de Gateway</span><span class="sxs-lookup"><span data-stu-id="a0aff-110">PSTN Calls (Non-Bypass): Gateway Leg</span></span>

  - <span data-ttu-id="a0aff-111">Outros Tipos de Chamada</span><span class="sxs-lookup"><span data-stu-id="a0aff-111">Other Call Types</span></span>

<span data-ttu-id="a0aff-112">Ao abrir pela primeira vez o relatório, você verá informações resumidas para cada uma das categorias.</span><span class="sxs-lookup"><span data-stu-id="a0aff-112">When you first open the report, you see summary information for each of these categories.</span></span> <span data-ttu-id="a0aff-113">Sem sair do relatório, você pode expandir cada categoria para ver subcategorias como chamadas feitas do Office Communicator 2007 R2 para o Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="a0aff-113">Without leaving the report, you can expand each category to look at subcategories such as calls made from Office Communicator 2007 R2 to Lync 2013.</span></span> <span data-ttu-id="a0aff-114">Por sua vez, você pode ver os detalhes de cada chamada feita dentro dessa subcategoria.</span><span class="sxs-lookup"><span data-stu-id="a0aff-114">In turn, you can then drill down into these subcategories to see details about each call made within that subcategory.</span></span>

<span data-ttu-id="a0aff-115">No Microsoft Lync Server 2013 o relatório de Resumo de qualidade de mídia divide ainda mais os dados em três tipos de chamadas: chamadas de áudio, chamadas com vídeo e chamadas de compartilhamento de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="a0aff-115">In Microsoft Lync Server 2013 the Media Quality Summary Report further breaks the data down into three call types: audio calls, video calls, and application sharing calls.</span></span> <span data-ttu-id="a0aff-116">Cada tipo de chamada tem sua própria seção no relatório, e seu próprio conjunto de métricas de chamadas.</span><span class="sxs-lookup"><span data-stu-id="a0aff-116">Each call type has its own section in the report, and its own custom set of call metrics.</span></span>

<span data-ttu-id="a0aff-117">O Relatório de resumo de qualidade de mídia também permite aplicar filtros que permitem comparar a qualidade de chamada de chamadas com fio em relação a chamadas sem fio, chamadas internas x chamadas externas e chamadas VPN x chamadas não VPN.</span><span class="sxs-lookup"><span data-stu-id="a0aff-117">The Media Quality Summary Report also allows you to apply filters that enable you to compare the call quality of wired calls vs. wireless calls, internal calls vs. external calls, and VPN calls vs. non-VPN calls.</span></span>

<div>

## <a name="accessing-the-media-quality-summary-report"></a><span data-ttu-id="a0aff-118">Como acessar o Relatório de resumo de qualidade de mídia</span><span class="sxs-lookup"><span data-stu-id="a0aff-118">Accessing the Media Quality Summary Report</span></span>

<span data-ttu-id="a0aff-119">O Relatório de resumo de qualidade de mídia é acessado na página inicial dos Relatórios de Monitoramento.</span><span class="sxs-lookup"><span data-stu-id="a0aff-119">The Media Quality Summary Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="a0aff-120">Você pode fazer uma busca detalhada no [relatório de lista de chamadas no Lync Server 2013](lync-server-2013-call-list-report.md) clicando em uma das seguintes métricas:</span><span class="sxs-lookup"><span data-stu-id="a0aff-120">You can drill down to the [Call List Report in Lync Server 2013](lync-server-2013-call-list-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="a0aff-121">Volume da chamada</span><span class="sxs-lookup"><span data-stu-id="a0aff-121">Call volume</span></span>

  - <span data-ttu-id="a0aff-122">Porcentagem de chamadas ruins</span><span class="sxs-lookup"><span data-stu-id="a0aff-122">Poor call percentage</span></span>

<span data-ttu-id="a0aff-123">Além disso, você pode acessar o Relatório de distribuição de métricas de qualidade de mídia clicando em uma das seguintes métricas de chamada de áudio:</span><span class="sxs-lookup"><span data-stu-id="a0aff-123">In addition, you can access the Media Quality Metrics Distribution Report by clicking any of the following audio call metrics:</span></span>

  - <span data-ttu-id="a0aff-124">Ida e volta (ms)</span><span class="sxs-lookup"><span data-stu-id="a0aff-124">Round trip (ms)</span></span>

  - <span data-ttu-id="a0aff-125">Degradação (MOS)</span><span class="sxs-lookup"><span data-stu-id="a0aff-125">Degradation (MOS)</span></span>

  - <span data-ttu-id="a0aff-126">Perda de pacote</span><span class="sxs-lookup"><span data-stu-id="a0aff-126">Packet loss</span></span>

  - <span data-ttu-id="a0aff-127">Tremulação (ms)</span><span class="sxs-lookup"><span data-stu-id="a0aff-127">Jitter (ms)</span></span>

  - <span data-ttu-id="a0aff-128">Taxa de correção oculta</span><span class="sxs-lookup"><span data-stu-id="a0aff-128">Healer concealed ratio</span></span>

  - <span data-ttu-id="a0aff-129">Taxa de correção estendida</span><span class="sxs-lookup"><span data-stu-id="a0aff-129">Healer stretched ratio</span></span>

  - <span data-ttu-id="a0aff-130">Taxa de correção compactada</span><span class="sxs-lookup"><span data-stu-id="a0aff-130">Healer compressed ratio</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="a0aff-131">Filtros</span><span class="sxs-lookup"><span data-stu-id="a0aff-131">Filters</span></span>

<span data-ttu-id="a0aff-p104">Filtros fornecem uma forma de retornar um conjunto de dados mais focado ou exibir os dados retornados de diferentes formas. Por exemplo, o Relatório de Resumo de Qualidade de Mídia permite filtrar os dados retornados por informações como tipo de acesso (ou seja, acesso interno x acesso externo) ou por conexão de rede com fio/sem fio. Você também pode escolher como os dados serão agrupados. Neste caso, as chamadas são agrupadas por hora, dia, semana ou mês.</span><span class="sxs-lookup"><span data-stu-id="a0aff-p104">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Media Quality Summary Report enables you to filter the returned data by such things as access type (that is, interval access vs. external access) or by wired/wireless network connection. You can also choose how data should be grouped. In this case, calls are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="a0aff-136">A tabela a seguir lista os filtros que podem ser usados com o Relatório de Resumo de Qualidade de Mídia.</span><span class="sxs-lookup"><span data-stu-id="a0aff-136">The following table lists the filters that you can use with the Media Quality Summary Report.</span></span>

### <a name="media-quality-summary-report-filters"></a><span data-ttu-id="a0aff-137">Filtros do Relatório de Resumo de Qualidade de Mídia</span><span class="sxs-lookup"><span data-stu-id="a0aff-137">Media Quality Summary Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a0aff-138">Nome</span><span class="sxs-lookup"><span data-stu-id="a0aff-138">Name</span></span></th>
<th><span data-ttu-id="a0aff-139">Descrição</span><span class="sxs-lookup"><span data-stu-id="a0aff-139">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a0aff-140"><strong>De</strong></span><span class="sxs-lookup"><span data-stu-id="a0aff-140"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="a0aff-p105">Data/hora de início para o intervalo de tempo. Para ver os dados por horas, insira a data e hora de início conforme segue:</span><span class="sxs-lookup"><span data-stu-id="a0aff-p105">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="a0aff-143">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="a0aff-143">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="a0aff-p106">Se você não inserir a hora de início, o relatório começará automaticamente à meia-noite do dia especificado. Para ver os dados por dia, insira somente a data:</span><span class="sxs-lookup"><span data-stu-id="a0aff-p106">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="a0aff-146">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="a0aff-146">7/7/2012</span></span></p>
<p><span data-ttu-id="a0aff-147">Para exibir por semana ou mês, insira uma data dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):</span><span class="sxs-lookup"><span data-stu-id="a0aff-147">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="a0aff-148">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="a0aff-148">7/3/2012</span></span></p>
<p><span data-ttu-id="a0aff-149">As semanas sempre vão de domingo a sábado.</span><span class="sxs-lookup"><span data-stu-id="a0aff-149">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0aff-150"><strong>Até</strong></span><span class="sxs-lookup"><span data-stu-id="a0aff-150"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="a0aff-p107">Data/hora final de intervalo de tempo. Para ver os dados por horas, insira a data e hora final conforme segue:</span><span class="sxs-lookup"><span data-stu-id="a0aff-p107">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="a0aff-153">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="a0aff-153">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="a0aff-p108">Se você não inserir a hora final, o relatório terminará automaticamente à meia-noite do dia especificado. Para ver os dados por dia, insira somente a data:</span><span class="sxs-lookup"><span data-stu-id="a0aff-p108">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="a0aff-156">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="a0aff-156">7/7/2012</span></span></p>
<p><span data-ttu-id="a0aff-157">Para exibir por semana ou mês, insira uma data dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):</span><span class="sxs-lookup"><span data-stu-id="a0aff-157">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="a0aff-158">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="a0aff-158">7/3/2012</span></span></p>
<p><span data-ttu-id="a0aff-159">As semanas sempre vão de domingo a sábado.</span><span class="sxs-lookup"><span data-stu-id="a0aff-159">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a0aff-160"><strong>Tipo de acesso</strong></span><span class="sxs-lookup"><span data-stu-id="a0aff-160"><strong>Access type</strong></span></span></p></td>
<td><p><span data-ttu-id="a0aff-p109">Indica se um cliente estava conectado na rede interna ou na rede externa quando a chamada foi realizada. Selecione um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="a0aff-p109">Indicates whether the client was logged on to the internal network or the external network when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="a0aff-163">[Todos]</span><span class="sxs-lookup"><span data-stu-id="a0aff-163">[All]</span></span></p></li>
<li><p><span data-ttu-id="a0aff-164">Interno</span><span class="sxs-lookup"><span data-stu-id="a0aff-164">Internal</span></span></p></li>
<li><p><span data-ttu-id="a0aff-165">Externo</span><span class="sxs-lookup"><span data-stu-id="a0aff-165">External</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0aff-166"><strong>Tipo de rede</strong></span><span class="sxs-lookup"><span data-stu-id="a0aff-166"><strong>Network type</strong></span></span></p></td>
<td><p><span data-ttu-id="a0aff-p110">Indica o tipo de rede que o cliente estava conectado quando a chamada foi realizada. Selecione um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="a0aff-p110">Indicates the type of network the client was connected to when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="a0aff-169">[Todos]</span><span class="sxs-lookup"><span data-stu-id="a0aff-169">[All]</span></span></p></li>
<li><p><span data-ttu-id="a0aff-170">Com fio</span><span class="sxs-lookup"><span data-stu-id="a0aff-170">Wired</span></span></p></li>
<li><p><span data-ttu-id="a0aff-171">Sem fio</span><span class="sxs-lookup"><span data-stu-id="a0aff-171">Wireless</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a0aff-172"><strong>VPN</strong></span><span class="sxs-lookup"><span data-stu-id="a0aff-172"><strong>VPN</strong></span></span></p></td>
<td><p><span data-ttu-id="a0aff-p111">Indica se um cliente externo estava usando uma conexão de rede privada virtual (VPN) quando a chamada foi realizada. Selecione um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="a0aff-p111">Indicates whether an external client was using a virtual private network (VPN) connection when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="a0aff-175">[Todos]</span><span class="sxs-lookup"><span data-stu-id="a0aff-175">[All]</span></span></p></li>
<li><p><span data-ttu-id="a0aff-176">VPN</span><span class="sxs-lookup"><span data-stu-id="a0aff-176">VPN</span></span></p></li>
<li><p><span data-ttu-id="a0aff-177">Não-VPN</span><span class="sxs-lookup"><span data-stu-id="a0aff-177">Non-VPN</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="a0aff-178">Métricas</span><span class="sxs-lookup"><span data-stu-id="a0aff-178">Metrics</span></span>

<span data-ttu-id="a0aff-179">A tabela a seguir lista as informações fornecidas no Relatório de Resumo de Qualidade de Mídia.</span><span class="sxs-lookup"><span data-stu-id="a0aff-179">The following table lists the information provided in the Media Quality Summary Report.</span></span>

### <a name="media-quality-summary-report-metrics-audio-call-summary"></a><span data-ttu-id="a0aff-180">Métricas do Relatório de Resumo de Qualidade de Mídia: Resumo da chamada de áudio</span><span class="sxs-lookup"><span data-stu-id="a0aff-180">Media Quality Summary Report Metrics: Audio Call Summary</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a0aff-181">Nome</span><span class="sxs-lookup"><span data-stu-id="a0aff-181">Name</span></span></th>
<th><span data-ttu-id="a0aff-182">Você pode classificar este item?</span><span class="sxs-lookup"><span data-stu-id="a0aff-182">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="a0aff-183">Descrição</span><span class="sxs-lookup"><span data-stu-id="a0aff-183">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a0aff-184"><strong>Tipo de chamada/Tipo de ponto de extremidade</strong></span><span class="sxs-lookup"><span data-stu-id="a0aff-184"><strong>Call type/Endpoint type</strong></span></span></p></td>
<td><p><span data-ttu-id="a0aff-185">Não</span><span class="sxs-lookup"><span data-stu-id="a0aff-185">No</span></span></p></td>
<td><p><span data-ttu-id="a0aff-p112">Ao clicar neste item, o relatório mostra informações detalhadas sobre chamadas baseadas no tipo escolhido. Tipos de chamada incluem:</span><span class="sxs-lookup"><span data-stu-id="a0aff-p112">When you click this item, the report shows detailed information about calls based on that type. Call types include:</span></span></p>
<ul>
<li><p><span data-ttu-id="a0aff-188">Chamadas Ponto a Ponto de UC</span><span class="sxs-lookup"><span data-stu-id="a0aff-188">UC Peer-to-Peer Calls</span></span></p></li>
<li><p><span data-ttu-id="a0aff-189">Sessões de Conferência de UC</span><span class="sxs-lookup"><span data-stu-id="a0aff-189">UC Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="a0aff-190">Sessões de Conferência PSTN</span><span class="sxs-lookup"><span data-stu-id="a0aff-190">PSTN Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="a0aff-191">Chamadas PSTN: Desvio de Mídia</span><span class="sxs-lookup"><span data-stu-id="a0aff-191">PSTN Calls: Media Bypass</span></span></p></li>
<li><p><span data-ttu-id="a0aff-192">Chamadas PSTN (Não Ignorar): Trecho de UC</span><span class="sxs-lookup"><span data-stu-id="a0aff-192">PSTN Calls (Non-Bypass): UC Leg</span></span></p></li>
<li><p><span data-ttu-id="a0aff-193">Chamadas PSTN (Não Ignorar): Trecho de Gateway</span><span class="sxs-lookup"><span data-stu-id="a0aff-193">PSTN Calls (Non-Bypass): Gateway Leg</span></span></p></li>
<li><p><span data-ttu-id="a0aff-194">Outros Tipos de Chamada</span><span class="sxs-lookup"><span data-stu-id="a0aff-194">Other Call Types</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0aff-195"><strong>Volume da chamada</strong></span><span class="sxs-lookup"><span data-stu-id="a0aff-195"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="a0aff-196">Não</span><span class="sxs-lookup"><span data-stu-id="a0aff-196">No</span></span></p></td>
<td><p><span data-ttu-id="a0aff-197">Número total de chamadas por tipo de chamada.</span><span class="sxs-lookup"><span data-stu-id="a0aff-197">Total number of calls per call type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a0aff-198"><strong>Porcentagem de chamada inválida</strong></span><span class="sxs-lookup"><span data-stu-id="a0aff-198"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="a0aff-199">Não</span><span class="sxs-lookup"><span data-stu-id="a0aff-199">No</span></span></p></td>
<td><p><span data-ttu-id="a0aff-p113">Número total de chamadas classificadas como ruins. Uma chamada ruim é qualquer chamada em que no mínimo uma das métricas medidas excedeu o valor permitido (por exemplo, uma chamada com tremulação excessiva).</span><span class="sxs-lookup"><span data-stu-id="a0aff-p113">Total number of calls classified as poor. A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0aff-202"><strong>Volume de chamadas (chamadas sem fio)</strong></span><span class="sxs-lookup"><span data-stu-id="a0aff-202"><strong>Call volume (wireless call)</strong></span></span></p></td>
<td><p><span data-ttu-id="a0aff-203">Não</span><span class="sxs-lookup"><span data-stu-id="a0aff-203">No</span></span></p></td>
<td><p><span data-ttu-id="a0aff-204">Número total de chamadas que usaram uma conexão sem fio.</span><span class="sxs-lookup"><span data-stu-id="a0aff-204">Total number of calls that used a wireless connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a0aff-205"><strong>Volume de chamadas (chamadas VPN)</strong></span><span class="sxs-lookup"><span data-stu-id="a0aff-205"><strong>Call volume (VPN call)</strong></span></span></p></td>
<td><p><span data-ttu-id="a0aff-206">Não</span><span class="sxs-lookup"><span data-stu-id="a0aff-206">No</span></span></p></td>
<td><p><span data-ttu-id="a0aff-207">Número total de chamadas que usaram uma conexão VPN.</span><span class="sxs-lookup"><span data-stu-id="a0aff-207">Total number of calls that used a VPN connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0aff-208"><strong>Volume de chamadas (chamadas externas)</strong></span><span class="sxs-lookup"><span data-stu-id="a0aff-208"><strong>Call volume (external call)</strong></span></span></p></td>
<td><p><span data-ttu-id="a0aff-209">Não</span><span class="sxs-lookup"><span data-stu-id="a0aff-209">No</span></span></p></td>
<td><p><span data-ttu-id="a0aff-210">Número de chamadas que usaram uma conexão externa (ou seja, uma conexão fora da rede interna).</span><span class="sxs-lookup"><span data-stu-id="a0aff-210">Number of calls that used an external connection (that is, a connection outside the internal network).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a0aff-211"><strong>Viagem de ida e volta (ms)</strong></span><span class="sxs-lookup"><span data-stu-id="a0aff-211"><strong>Round trip (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="a0aff-212">Não</span><span class="sxs-lookup"><span data-stu-id="a0aff-212">No</span></span></p></td>
<td><p><span data-ttu-id="a0aff-p114">Quantidade média de (em milissegundos) exigida para que um pacote RTP (protocolo de transporte em tempo real) viaje até outra extremidade e retorne. Tempos de viagem de ida e volta de 100 milissegundos ou menos são considerados de qualidade aceitável.</span><span class="sxs-lookup"><span data-stu-id="a0aff-p114">Average amount of (in milliseconds) required for a real-time transport protocol (RTP) packet to travel to another endpoint and then back. Round-trip times of 100 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="a0aff-p115">Os valores altos de ida e volta pode ser causados por roteamento de chamada internacional, um erro de configuração de roteamento ou um servidor de mídia sobrecarregado. Tempos de ida e volta altos resultam em dificuldades com conversas de áudio em tempo real e bidirecionais.</span><span class="sxs-lookup"><span data-stu-id="a0aff-p115">High round-trip values can be caused by international call routing, a routing misconfiguration, or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0aff-217"><strong>Degradação (MOS)</strong></span><span class="sxs-lookup"><span data-stu-id="a0aff-217"><strong>Degradation (MOS)</strong></span></span></p></td>
<td><p><span data-ttu-id="a0aff-218">Não</span><span class="sxs-lookup"><span data-stu-id="a0aff-218">No</span></span></p></td>
<td><p><span data-ttu-id="a0aff-219">Quantidade média da degradação MOS enfrentada durante uma chamada.</span><span class="sxs-lookup"><span data-stu-id="a0aff-219">Average amount of mean opinion score (MOS) degradation experienced during a call.</span></span> <span data-ttu-id="a0aff-220">Os valores de degradação variam de um baixo de 0,0 a um alto de 5,0.</span><span class="sxs-lookup"><span data-stu-id="a0aff-220">Degradation values can range from a low of 0.0 to a high of 5.0.</span></span> <span data-ttu-id="a0aff-221">Um valor de 0,5 ou menos representa degradação aceitável.</span><span class="sxs-lookup"><span data-stu-id="a0aff-221">A value of 0.5 or less represents acceptable degradation.</span></span> <span data-ttu-id="a0aff-222">As pontuações médias de opinião costumava ser calculadas a partir da classificação da qualidade de uma chamada em uma escala de 1 a 5, feita pelos dos usuários.</span><span class="sxs-lookup"><span data-stu-id="a0aff-222">Historically, mean options scores were calculated by having users rate the quality of a call on a scale of 1-to-5.</span></span> <span data-ttu-id="a0aff-223">No Lync Server, o Lync Server usa um conjunto de algoritmos para prever como os usuários teriam classificado uma chamada.</span><span class="sxs-lookup"><span data-stu-id="a0aff-223">In Lync Server, Lync Server uses a set of algorithms to predict how users would have rated a call.</span></span></p>
<p><span data-ttu-id="a0aff-p117">Os valores de degradação altos podem ser causados por congestão, falta de largura de banda, congestionamento ou interferência sem fio ou um servidor de mídia ou ponto de extremidade sobrecarregado. A alta degradação resulta em perda ou distorção de áudio.</span><span class="sxs-lookup"><span data-stu-id="a0aff-p117">High degradation values can be caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server or endpoint. High degradation results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a0aff-226"><strong>Perda de pacote</strong></span><span class="sxs-lookup"><span data-stu-id="a0aff-226"><strong>Packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="a0aff-227">Não</span><span class="sxs-lookup"><span data-stu-id="a0aff-227">No</span></span></p></td>
<td><p><span data-ttu-id="a0aff-p118">Taxa média de perda de pacote RTP. (A perda de pacote ocorre quando os pacotes RTP, um protocolo usado para transmissão de áudio e vídeo pela Internet, não conseguem chegar aos seus destinos.) Taxas de perda altas normalmente são causadas por congestionamento, falta de largura de banda, congestionamento ou interferência sem fio ou um servidor de mídia sobrecarregado. A perda de pacote normalmente resulta em perda ou distorção de áudio.</span><span class="sxs-lookup"><span data-stu-id="a0aff-p118">Average rate of RTP packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0aff-231"><strong>Tremulação (ms)</strong></span><span class="sxs-lookup"><span data-stu-id="a0aff-231"><strong>Jitter (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="a0aff-232">Não</span><span class="sxs-lookup"><span data-stu-id="a0aff-232">No</span></span></p></td>
<td><p><span data-ttu-id="a0aff-233">Tremulação média detectada entre chegadas de pacote RTP.</span><span class="sxs-lookup"><span data-stu-id="a0aff-233">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="a0aff-234">(Tremulação é uma medida do &quot;shakiness&quot; de uma chamada.) Os valores de variação alta geralmente são causados por congestionamento ou um servidor de mídia sobrecarregado, resultando em áudio distorcido ou perdido.</span><span class="sxs-lookup"><span data-stu-id="a0aff-234">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a0aff-235"><strong>Taxa de correção oculta</strong></span><span class="sxs-lookup"><span data-stu-id="a0aff-235"><strong>Healer concealed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="a0aff-236">Não</span><span class="sxs-lookup"><span data-stu-id="a0aff-236">No</span></span></p></td>
<td><p><span data-ttu-id="a0aff-p120">Taxa média de amostras de áudio ocultas para o número total de amostras. (Uma amostra de áudio oculta é uma técnica usada para suavizar a transição abrupta que normalmente seria causada por pacotes de rede descartados.) Valores altos indicam níveis consideráveis de perda de ocultação aplicada causada por perda de pacote ou tremulação e resulta na perda ou distorção de áudio.</span><span class="sxs-lookup"><span data-stu-id="a0aff-p120">Average ratio of concealed audio samples to the total to the total number of samples. (A concealed audio sample is a technique used to smooth out the abrupt transition that would usually be caused by dropped network packets.) High values indicate significant levels of loss concealment applied caused by packet loss or jitter, and results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0aff-239"><strong>Taxa de correção estendida</strong></span><span class="sxs-lookup"><span data-stu-id="a0aff-239"><strong>Healer stretched ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="a0aff-240">Não</span><span class="sxs-lookup"><span data-stu-id="a0aff-240">No</span></span></p></td>
<td><p><span data-ttu-id="a0aff-p121">Taxa média de amostras de áudio estendidas para o número total de amostras. (Áudio estendido é o áudio que foi expandido a fim de ajudar a manter a qualidade da chamada quando um pacote de rede descartado é detectado.) Valores altos indicam níveis significativos de extensão de amostra causada por tremulação e resultam em um som robótico ou distorcido.</span><span class="sxs-lookup"><span data-stu-id="a0aff-p121">Average ratio of stretched audio samples to the total to the total number of samples. (Stretched audio is audio that has been expanded to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample stretching caused by jitter, and result in audio sounding robotic or distorted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a0aff-243"><strong>Taxa de correção compactada</strong></span><span class="sxs-lookup"><span data-stu-id="a0aff-243"><strong>Healer compressed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="a0aff-244">Não</span><span class="sxs-lookup"><span data-stu-id="a0aff-244">No</span></span></p></td>
<td><p><span data-ttu-id="a0aff-p122">Taxa média de amostras de áudio compactadas para o número total de amostras. (Áudio compactado é o áudio que foi compactado para ajudar a manter a qualidade da chamada quando um pacote de rede descartado é detectado.) Valores altos podem indicar níveis consideráveis de compactação de amostra causada por tremulação e resultam em um som acelerado ou distorcido.</span><span class="sxs-lookup"><span data-stu-id="a0aff-p122">Average ratio of compressed audio samples to the total number of samples. (Compressed audio is audio that has been compressed to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample compression caused by jitter, and result in audio sounding accelerated or distorted.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="media-quality-summary-report-metrics-video-call-summary"></a><span data-ttu-id="a0aff-247">Métricas do Relatório de Resumo de Qualidade de Mídia: Resumo da chamada de vídeo</span><span class="sxs-lookup"><span data-stu-id="a0aff-247">Media Quality Summary Report Metrics: Video Call Summary</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a0aff-248">Nome</span><span class="sxs-lookup"><span data-stu-id="a0aff-248">Name</span></span></th>
<th><span data-ttu-id="a0aff-249">Você pode classificar este item?</span><span class="sxs-lookup"><span data-stu-id="a0aff-249">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="a0aff-250">Descrição</span><span class="sxs-lookup"><span data-stu-id="a0aff-250">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a0aff-251"><strong>Tipo de chamada/Tipo de ponto de extremidade</strong></span><span class="sxs-lookup"><span data-stu-id="a0aff-251"><strong>Call type/Endpoint type</strong></span></span></p></td>
<td><p><span data-ttu-id="a0aff-252">Não</span><span class="sxs-lookup"><span data-stu-id="a0aff-252">No</span></span></p></td>
<td><p><span data-ttu-id="a0aff-p123">Ao clicar neste item, o relatório mostra informações detalhadas sobre chamadas baseadas no tipo escolhido. Tipos de chamada incluem:</span><span class="sxs-lookup"><span data-stu-id="a0aff-p123">When you click this item, the report shows detailed information about calls based on that type. Call types include:</span></span></p>
<ul>
<li><p><span data-ttu-id="a0aff-255">Chamadas Ponto a Ponto de UC</span><span class="sxs-lookup"><span data-stu-id="a0aff-255">UC Peer-to-Peer Calls</span></span></p></li>
<li><p><span data-ttu-id="a0aff-256">Sessões de Conferência de UC</span><span class="sxs-lookup"><span data-stu-id="a0aff-256">UC Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="a0aff-257">Sessões de Conferência PSTN</span><span class="sxs-lookup"><span data-stu-id="a0aff-257">PSTN Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="a0aff-258">Chamadas PSTN: Desvio de Mídia</span><span class="sxs-lookup"><span data-stu-id="a0aff-258">PSTN Calls: Media Bypass</span></span></p></li>
<li><p><span data-ttu-id="a0aff-259">Chamadas PSTN (Não Ignorar): Trecho de UC</span><span class="sxs-lookup"><span data-stu-id="a0aff-259">PSTN Calls (Non-Bypass): UC Leg</span></span></p></li>
<li><p><span data-ttu-id="a0aff-260">Chamadas PSTN (Não Ignorar): Trecho de Gateway</span><span class="sxs-lookup"><span data-stu-id="a0aff-260">PSTN Calls (Non-Bypass): Gateway Leg</span></span></p></li>
<li><p><span data-ttu-id="a0aff-261">Outros Tipos de Chamada</span><span class="sxs-lookup"><span data-stu-id="a0aff-261">Other Call Types</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0aff-262"><strong>Volume da chamada</strong></span><span class="sxs-lookup"><span data-stu-id="a0aff-262"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="a0aff-263">Não</span><span class="sxs-lookup"><span data-stu-id="a0aff-263">No</span></span></p></td>
<td><p><span data-ttu-id="a0aff-264">Número total de chamadas por tipo de chamada.</span><span class="sxs-lookup"><span data-stu-id="a0aff-264">Total number of calls per call type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a0aff-265"><strong>Porcentagem de chamada inválida</strong></span><span class="sxs-lookup"><span data-stu-id="a0aff-265"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="a0aff-266">Não</span><span class="sxs-lookup"><span data-stu-id="a0aff-266">No</span></span></p></td>
<td><p><span data-ttu-id="a0aff-p124">Número total de chamadas classificadas como ruins. Uma chamada ruim é qualquer chamada em que no mínimo uma das métricas medidas excedeu o valor permitido (por exemplo, uma chamada com tremulação excessiva).</span><span class="sxs-lookup"><span data-stu-id="a0aff-p124">Total number of calls classified as poor. A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0aff-269"><strong>Volume de chamadas (chamadas sem fio)</strong></span><span class="sxs-lookup"><span data-stu-id="a0aff-269"><strong>Call volume (wireless call)</strong></span></span></p></td>
<td><p><span data-ttu-id="a0aff-270">Não</span><span class="sxs-lookup"><span data-stu-id="a0aff-270">No</span></span></p></td>
<td><p><span data-ttu-id="a0aff-271">Número total de chamadas que usaram uma conexão sem fio.</span><span class="sxs-lookup"><span data-stu-id="a0aff-271">Total number of calls that used a wireless connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a0aff-272"><strong>Volume de chamadas (chamadas VPN)</strong></span><span class="sxs-lookup"><span data-stu-id="a0aff-272"><strong>Call volume (VPN call)</strong></span></span></p></td>
<td><p><span data-ttu-id="a0aff-273">Não</span><span class="sxs-lookup"><span data-stu-id="a0aff-273">No</span></span></p></td>
<td><p><span data-ttu-id="a0aff-274">Número total de chamadas que usaram uma conexão VPN.</span><span class="sxs-lookup"><span data-stu-id="a0aff-274">Total number of calls that used a VPN connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0aff-275"><strong>Volume de chamadas (chamadas externas)</strong></span><span class="sxs-lookup"><span data-stu-id="a0aff-275"><strong>Call volume (external call)</strong></span></span></p></td>
<td><p><span data-ttu-id="a0aff-276">Não</span><span class="sxs-lookup"><span data-stu-id="a0aff-276">No</span></span></p></td>
<td><p><span data-ttu-id="a0aff-277">Número de chamadas que usaram uma conexão externa (ou seja, uma conexão fora da rede interna).</span><span class="sxs-lookup"><span data-stu-id="a0aff-277">Number of calls that used an external connection (that is, a connection outside the internal network).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a0aff-278"><strong>Taxa de bits média (Kbits/s)</strong></span><span class="sxs-lookup"><span data-stu-id="a0aff-278"><strong>Avg bit-rate (Kbits/s)</strong></span></span></p></td>
<td><p><span data-ttu-id="a0aff-279">Não</span><span class="sxs-lookup"><span data-stu-id="a0aff-279">No</span></span></p></td>
<td><p><span data-ttu-id="a0aff-280">Taxa de bits média (em quilobytes por segundo).</span><span class="sxs-lookup"><span data-stu-id="a0aff-280">Average video bit rate (in kilobits per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0aff-281"><strong>Taxa de bits baixa %</strong></span><span class="sxs-lookup"><span data-stu-id="a0aff-281"><strong>Low bit-rate %</strong></span></span></p></td>
<td><p><span data-ttu-id="a0aff-282">Não</span><span class="sxs-lookup"><span data-stu-id="a0aff-282">No</span></span></p></td>
<td><p><span data-ttu-id="a0aff-283">Porcentagem da chamada onde a taxa de bits foi baixa.</span><span class="sxs-lookup"><span data-stu-id="a0aff-283">Percentage of the call where the bit rate was low.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a0aff-284"><strong>Perda de pacote de saída</strong></span><span class="sxs-lookup"><span data-stu-id="a0aff-284"><strong>Outbound packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="a0aff-285">Não</span><span class="sxs-lookup"><span data-stu-id="a0aff-285">No</span></span></p></td>
<td><p><span data-ttu-id="a0aff-p125">Perda de pacotes do Protocolo de transporte em tempo real (RTP) para pacotes enviados. (A perda de pacotes ocorre quando pacotes RTP, um protocolo usado para transmitir áudio e vídeo pela internet, falha ao tentar alcançar seu destino). Altas taxas de perda geralmente são causadas por congestionamento, insuficiência da largura de banda, congestionamento ou interferência na rede sem fio ou um servidor de mídia sobrecarregado. A perda de pacotes normalmente resulta em distorção ou perda de áudio.</span><span class="sxs-lookup"><span data-stu-id="a0aff-p125">Real-Time Transport Protocol (RTP) packet loss for outbound packets. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0aff-289"><strong>% de quadros congelados</strong></span><span class="sxs-lookup"><span data-stu-id="a0aff-289"><strong>Frozen frame %</strong></span></span></p></td>
<td><p><span data-ttu-id="a0aff-290">Não</span><span class="sxs-lookup"><span data-stu-id="a0aff-290">No</span></span></p></td>
<td><p><span data-ttu-id="a0aff-p126">Porcentagem de quadros "congelados". Em um quadro congelado, o vídeo não avança enquanto a parte de áudio da chamada prossegue.</span><span class="sxs-lookup"><span data-stu-id="a0aff-p126">Percentage of “frozen” frames. In a frozen frame, the video stops advancing while the audio portion of the call continues.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a0aff-293"><strong>Taxa de quadros média de saída</strong></span><span class="sxs-lookup"><span data-stu-id="a0aff-293"><strong>Outbound avg frame rate</strong></span></span></p></td>
<td><p><span data-ttu-id="a0aff-294">Não</span><span class="sxs-lookup"><span data-stu-id="a0aff-294">No</span></span></p></td>
<td><p><span data-ttu-id="a0aff-295">Taxa de quadros média para transmissões de saída durante a chamada.</span><span class="sxs-lookup"><span data-stu-id="a0aff-295">Average frame rate for outbound transmissions during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0aff-296"><strong>Taxa de quadros média de entrada</strong></span><span class="sxs-lookup"><span data-stu-id="a0aff-296"><strong>Inbound avg frame rate</strong></span></span></p></td>
<td><p><span data-ttu-id="a0aff-297">Não</span><span class="sxs-lookup"><span data-stu-id="a0aff-297">No</span></span></p></td>
<td><p><span data-ttu-id="a0aff-298">Taxa de quadros média para transmissões de entrada durante a chamada.</span><span class="sxs-lookup"><span data-stu-id="a0aff-298">Average frame rate for incoming transmissions during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a0aff-299"><strong>% de taxa de quadros baixa de entrada</strong></span><span class="sxs-lookup"><span data-stu-id="a0aff-299"><strong>Inbound low frame rate %</strong></span></span></p></td>
<td><p><span data-ttu-id="a0aff-300">Não</span><span class="sxs-lookup"><span data-stu-id="a0aff-300">No</span></span></p></td>
<td><p><span data-ttu-id="a0aff-301">Porcentagem da chamada onde a taxa de bits foi baixa para vídeo de entrada.</span><span class="sxs-lookup"><span data-stu-id="a0aff-301">Percentage of the call where the bit rate for incoming video was low.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0aff-302"><strong>% de integridade do cliente</strong></span><span class="sxs-lookup"><span data-stu-id="a0aff-302"><strong>Client health %</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a0aff-303">Indica o estado relativo do dispositivo do cliente durante a chamada.</span><span class="sxs-lookup"><span data-stu-id="a0aff-303">Indicates the relative health of the client device during the call.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="media-quality-summary-report-metrics-application-sharing-call-summary"></a><span data-ttu-id="a0aff-304">Métricas do Relatório de resumo de qualidade de mídia: Resumo de chamada de compartilhamento de aplicativos</span><span class="sxs-lookup"><span data-stu-id="a0aff-304">Media Quality Summary Report Metrics: Application Sharing Call Summary</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a0aff-305">Nome</span><span class="sxs-lookup"><span data-stu-id="a0aff-305">Name</span></span></th>
<th><span data-ttu-id="a0aff-306">Você pode classificar este item?</span><span class="sxs-lookup"><span data-stu-id="a0aff-306">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="a0aff-307">Descrição</span><span class="sxs-lookup"><span data-stu-id="a0aff-307">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a0aff-308"><strong>Tipo de chamada/Tipo de ponto de extremidade</strong></span><span class="sxs-lookup"><span data-stu-id="a0aff-308"><strong>Call type/Endpoint type</strong></span></span></p></td>
<td><p><span data-ttu-id="a0aff-309">Não</span><span class="sxs-lookup"><span data-stu-id="a0aff-309">No</span></span></p></td>
<td><p><span data-ttu-id="a0aff-p127">Ao clicar neste item, o relatório mostra informações detalhadas sobre chamadas baseadas no tipo escolhido. Tipos de chamada incluem:</span><span class="sxs-lookup"><span data-stu-id="a0aff-p127">When you click this item, the report shows detailed information about calls based on that type. Call types include:</span></span></p>
<ul>
<li><p><span data-ttu-id="a0aff-312">Chamadas Ponto a Ponto de UC</span><span class="sxs-lookup"><span data-stu-id="a0aff-312">UC Peer-to-Peer Calls</span></span></p></li>
<li><p><span data-ttu-id="a0aff-313">Sessões de Conferência de UC</span><span class="sxs-lookup"><span data-stu-id="a0aff-313">UC Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="a0aff-314">Sessões de Conferência PSTN</span><span class="sxs-lookup"><span data-stu-id="a0aff-314">PSTN Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="a0aff-315">Chamadas PSTN: Desvio de Mídia</span><span class="sxs-lookup"><span data-stu-id="a0aff-315">PSTN Calls: Media Bypass</span></span></p></li>
<li><p><span data-ttu-id="a0aff-316">Chamadas PSTN (Não Ignorar): Trecho de UC</span><span class="sxs-lookup"><span data-stu-id="a0aff-316">PSTN Calls (Non-Bypass): UC Leg</span></span></p></li>
<li><p><span data-ttu-id="a0aff-317">Chamadas PSTN (Não Ignorar): Trecho de Gateway</span><span class="sxs-lookup"><span data-stu-id="a0aff-317">PSTN Calls (Non-Bypass): Gateway Leg</span></span></p></li>
<li><p><span data-ttu-id="a0aff-318">Outros Tipos de Chamada</span><span class="sxs-lookup"><span data-stu-id="a0aff-318">Other Call Types</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0aff-319"><strong>Volume da chamada</strong></span><span class="sxs-lookup"><span data-stu-id="a0aff-319"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="a0aff-320">Não</span><span class="sxs-lookup"><span data-stu-id="a0aff-320">No</span></span></p></td>
<td><p><span data-ttu-id="a0aff-321">Número total de chamadas por tipo de chamada.</span><span class="sxs-lookup"><span data-stu-id="a0aff-321">Total number of calls per call type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a0aff-322"><strong>Porcentagem de chamada inválida</strong></span><span class="sxs-lookup"><span data-stu-id="a0aff-322"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="a0aff-323">Não</span><span class="sxs-lookup"><span data-stu-id="a0aff-323">No</span></span></p></td>
<td><p><span data-ttu-id="a0aff-p128">Número total de chamadas classificadas como ruins. Uma chamada ruim é qualquer chamada em que no mínimo uma das métricas medidas excedeu o valor permitido (por exemplo, uma chamada com tremulação excessiva).</span><span class="sxs-lookup"><span data-stu-id="a0aff-p128">Total number of calls classified as poor. A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0aff-326"><strong>Volume de chamadas (chamadas sem fio)</strong></span><span class="sxs-lookup"><span data-stu-id="a0aff-326"><strong>Call volume (wireless call)</strong></span></span></p></td>
<td><p><span data-ttu-id="a0aff-327">Não</span><span class="sxs-lookup"><span data-stu-id="a0aff-327">No</span></span></p></td>
<td><p><span data-ttu-id="a0aff-328">Número total de chamadas que usaram uma conexão sem fio.</span><span class="sxs-lookup"><span data-stu-id="a0aff-328">Total number of calls that used a wireless connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a0aff-329"><strong>Volume de chamadas (chamadas VPN)</strong></span><span class="sxs-lookup"><span data-stu-id="a0aff-329"><strong>Call volume (VPN call)</strong></span></span></p></td>
<td><p><span data-ttu-id="a0aff-330">Não</span><span class="sxs-lookup"><span data-stu-id="a0aff-330">No</span></span></p></td>
<td><p><span data-ttu-id="a0aff-331">Número total de chamadas que usaram uma conexão VPN.</span><span class="sxs-lookup"><span data-stu-id="a0aff-331">Total number of calls that used a VPN connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0aff-332"><strong>Volume de chamadas (chamadas externas)</strong></span><span class="sxs-lookup"><span data-stu-id="a0aff-332"><strong>Call volume (external call)</strong></span></span></p></td>
<td><p><span data-ttu-id="a0aff-333">Não</span><span class="sxs-lookup"><span data-stu-id="a0aff-333">No</span></span></p></td>
<td><p><span data-ttu-id="a0aff-334">Número de chamadas que usaram uma conexão externa (ou seja, uma conexão fora da rede interna).</span><span class="sxs-lookup"><span data-stu-id="a0aff-334">Number of calls that used an external connection (that is, a connection outside the internal network).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a0aff-335"><strong>Tremulação (ms)</strong></span><span class="sxs-lookup"><span data-stu-id="a0aff-335"><strong>Jitter (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="a0aff-336">Não</span><span class="sxs-lookup"><span data-stu-id="a0aff-336">No</span></span></p></td>
<td><p><span data-ttu-id="a0aff-337">Tremulação média detectada entre chegadas de pacote RTP.</span><span class="sxs-lookup"><span data-stu-id="a0aff-337">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="a0aff-338">(Tremulação é uma medida do &quot;shakiness&quot; de uma chamada.) Os valores de variação alta geralmente são causados por congestionamento ou um servidor de mídia sobrecarregado, resultando em áudio distorcido ou perdido.</span><span class="sxs-lookup"><span data-stu-id="a0aff-338">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0aff-339"><strong>Unidirecional relativo médio</strong></span><span class="sxs-lookup"><span data-stu-id="a0aff-339"><strong>Avg. relative one way</strong></span></span></p></td>
<td><p><span data-ttu-id="a0aff-340">Não</span><span class="sxs-lookup"><span data-stu-id="a0aff-340">No</span></span></p></td>
<td><p><span data-ttu-id="a0aff-p130">Atraso unidirecional relativo médio entre dois pontos de extremidade de mídia. Esta é uma medida de latência de salto único.</span><span class="sxs-lookup"><span data-stu-id="a0aff-p130">Average relative one-way delay between two media endpoints. This is a single-hop latency measure.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a0aff-343"><strong>Latência média de processamento lado a lado RDP</strong></span><span class="sxs-lookup"><span data-stu-id="a0aff-343"><strong>Avg. RDP tile processing latency</strong></span></span></p></td>
<td><p><span data-ttu-id="a0aff-344">Não</span><span class="sxs-lookup"><span data-stu-id="a0aff-344">No</span></span></p></td>
<td><p><span data-ttu-id="a0aff-p131">A latência média de processamento lado a lado RDP no Servidor de Conferência AS durante a sessão de visualização. Uma média alta reflete um atraso maior na experiência de visualização e inclui latência de rede. Um servidor de conferência sobrecarregado pode sofrer médias maiores de atrasos.</span><span class="sxs-lookup"><span data-stu-id="a0aff-p131">The average RDP tile processing latency in the AS Conferencing Server over the duration of the viewing session. A high average reflects a longer delay in the viewing experience, and includes network latency. An overloaded conferencing server may experience higher average delays.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0aff-348"><strong>% total de lado a lado estragado</strong></span><span class="sxs-lookup"><span data-stu-id="a0aff-348"><strong>Total spoiled tile %</strong></span></span></p></td>
<td><p><span data-ttu-id="a0aff-349">Não</span><span class="sxs-lookup"><span data-stu-id="a0aff-349">No</span></span></p></td>
<td><p><span data-ttu-id="a0aff-350">A porcentagem total de lado a lado estragados.</span><span class="sxs-lookup"><span data-stu-id="a0aff-350">Total percentage of spoiled RDP tiles.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

