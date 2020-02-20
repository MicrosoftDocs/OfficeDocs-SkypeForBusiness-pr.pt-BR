---
title: 'Lync Server 2013: relatório de comparação de qualidade de mídia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Media Quality Comparison Report
ms:assetid: c1d0b5a8-98ff-455a-b78b-a05a21cf066d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205236(v=OCS.15)
ms:contentKeyID: 48185317
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e2f32f2f97eb8bb5948a218b05d5718897dd0f58
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149811"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="media-quality-comparison-report-in-lync-server-2013"></a><span data-ttu-id="842b7-102">Relatório de comparação de qualidade de mídia no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="842b7-102">Media Quality Comparison Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="842b7-103">_**Última modificação do tópico:** 2014-04-22_</span><span class="sxs-lookup"><span data-stu-id="842b7-103">_**Topic Last Modified:** 2014-04-22_</span></span>

<span data-ttu-id="842b7-104">O Relatório de Comparação de Qualidade da Mídia permite você comparar os valores de qualidade da chamada para diferentes tipos de chamadas de áudio (por exemplo, chamadas realizadas através de uma rede sem fio contra chamadas realizadas em uma conexão com fio).</span><span class="sxs-lookup"><span data-stu-id="842b7-104">The Media Quality Comparison Report enables you to compare call quality values for different types of audio calls (for example, calls made over a wireless network vs. calls made across a wired connection).</span></span>

<div>

## <a name="accessing-the-media-quality-comparison-report"></a><span data-ttu-id="842b7-105">Acessando o Relatório de Comparação de Qualidade da Mídia</span><span class="sxs-lookup"><span data-stu-id="842b7-105">Accessing the Media Quality Comparison Report</span></span>

<span data-ttu-id="842b7-106">O Relatório de Comparação de Qualidade da Mídia é acessado na página inicial de Relatórios de Monitoramento.</span><span class="sxs-lookup"><span data-stu-id="842b7-106">The Media Quality Comparison Report is accessed from the Monitoring Reports home page.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="842b7-107">Filtros</span><span class="sxs-lookup"><span data-stu-id="842b7-107">Filters</span></span>

<span data-ttu-id="842b7-p101">Os filtros oferecem uma forma de retornar um conjunto de dados mais detalhado ou exibir os dados retornados em formas diferentes. A tabela a seguir lista os filtros que você pode usar com o Relatório de Comparação de Qualidade da Mídia.</span><span class="sxs-lookup"><span data-stu-id="842b7-p101">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. The following table lists the filters that you can use with the Media Quality Comparison Report.</span></span>

### <a name="media-quality-comparison-report-filters"></a><span data-ttu-id="842b7-110">Filtros do Relatório de Comparação de Qualidade da Mídia</span><span class="sxs-lookup"><span data-stu-id="842b7-110">Media Quality Comparison Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="842b7-111">Nome</span><span class="sxs-lookup"><span data-stu-id="842b7-111">Name</span></span></th>
<th><span data-ttu-id="842b7-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="842b7-112">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="842b7-113"><strong>De</strong></span><span class="sxs-lookup"><span data-stu-id="842b7-113"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="842b7-p102">Data/hora inicial para o intervalo de tempo. Para exibir os dados por hora, insira a data e hora inicial como a seguir:</span><span class="sxs-lookup"><span data-stu-id="842b7-p102">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="842b7-116">7/7/2012 13:00 horas</span><span class="sxs-lookup"><span data-stu-id="842b7-116">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="842b7-p103">Se você não inserir uma hora inicial, o relatório começa automaticamente as 12:00 AM no dia especificado. Para exibir os dados por dia, insira apenas a data:</span><span class="sxs-lookup"><span data-stu-id="842b7-p103">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="842b7-119">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="842b7-119">7/7/2012</span></span></p>
<p><span data-ttu-id="842b7-120">Para exibir por semana ou mês, insira uma data que está dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):</span><span class="sxs-lookup"><span data-stu-id="842b7-120">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="842b7-121">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="842b7-121">7/3/2012</span></span></p>
<p><span data-ttu-id="842b7-122">As semanas sempre correm do domingo até sábado.</span><span class="sxs-lookup"><span data-stu-id="842b7-122">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="842b7-123"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="842b7-123"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="842b7-p104">Data/hora final para o intervalo de tempo. Para exibir os dados por hora, insira a data e hora final como a seguir:</span><span class="sxs-lookup"><span data-stu-id="842b7-p104">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="842b7-126">7/7/2012 13:00 horas</span><span class="sxs-lookup"><span data-stu-id="842b7-126">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="842b7-p105">Se você não inserir uma hora final, o relatório termina automaticamente as 12:00 AM no dia especificado. Para exibir os dados por dia, insira apenas a data:</span><span class="sxs-lookup"><span data-stu-id="842b7-p105">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="842b7-129">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="842b7-129">7/7/2012</span></span></p>
<p><span data-ttu-id="842b7-130">Para exibir por semana ou mês, insira uma data que está dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):</span><span class="sxs-lookup"><span data-stu-id="842b7-130">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="842b7-131">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="842b7-131">7/3/2012</span></span></p>
<p><span data-ttu-id="842b7-132">As semanas são sempre de domingo a sábado.</span><span class="sxs-lookup"><span data-stu-id="842b7-132">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="842b7-133"><strong>Chamadas</strong></span><span class="sxs-lookup"><span data-stu-id="842b7-133"><strong>Calls</strong></span></span></p></td>
<td><p><span data-ttu-id="842b7-p106">Tipo de chamada a ser usada como o item de comparação principal. Os valores permitidos são:</span><span class="sxs-lookup"><span data-stu-id="842b7-p106">Type of call to be used as the main comparison item. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="842b7-136">Todos os</span><span class="sxs-lookup"><span data-stu-id="842b7-136">[All]</span></span></p></li>
<li><p><span data-ttu-id="842b7-137">Externa</span><span class="sxs-lookup"><span data-stu-id="842b7-137">External</span></span></p></li>
<li><p><span data-ttu-id="842b7-138">Interna</span><span class="sxs-lookup"><span data-stu-id="842b7-138">Internal</span></span></p></li>
<li><p><span data-ttu-id="842b7-139">VPN</span><span class="sxs-lookup"><span data-stu-id="842b7-139">VPN</span></span></p></li>
<li><p><span data-ttu-id="842b7-140">Não VPN</span><span class="sxs-lookup"><span data-stu-id="842b7-140">Non-VPN</span></span></p></li>
<li><p><span data-ttu-id="842b7-141">Com fio</span><span class="sxs-lookup"><span data-stu-id="842b7-141">Wired</span></span></p></li>
<li><p><span data-ttu-id="842b7-142">Conexão</span><span class="sxs-lookup"><span data-stu-id="842b7-142">Wireless</span></span></p></li>
<li><p><span data-ttu-id="842b7-143">Externa e com fio</span><span class="sxs-lookup"><span data-stu-id="842b7-143">External and wired</span></span></p></li>
<li><p><span data-ttu-id="842b7-144">Externa e sem fio</span><span class="sxs-lookup"><span data-stu-id="842b7-144">External and wireless</span></span></p></li>
<li><p><span data-ttu-id="842b7-145">Externa e VPN</span><span class="sxs-lookup"><span data-stu-id="842b7-145">External and VPN</span></span></p></li>
<li><p><span data-ttu-id="842b7-146">Externa e não-VPN</span><span class="sxs-lookup"><span data-stu-id="842b7-146">External and non-VPN</span></span></p></li>
<li><p><span data-ttu-id="842b7-147">Interna e com fio</span><span class="sxs-lookup"><span data-stu-id="842b7-147">Internal and wired</span></span></p></li>
<li><p><span data-ttu-id="842b7-148">Interna e sem fio</span><span class="sxs-lookup"><span data-stu-id="842b7-148">Internal and wireless</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="842b7-149"><strong>Comparar com chamadas</strong></span><span class="sxs-lookup"><span data-stu-id="842b7-149"><strong>Compare with calls</strong></span></span></p></td>
<td><p><span data-ttu-id="842b7-p107">Tipo de chamada a ser usada como o item de comparação secundária. Os valores permitidos são:</span><span class="sxs-lookup"><span data-stu-id="842b7-p107">Type of call to be used as the secondary comparison item. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="842b7-152">Todos os</span><span class="sxs-lookup"><span data-stu-id="842b7-152">[All]</span></span></p></li>
<li><p><span data-ttu-id="842b7-153">Externa</span><span class="sxs-lookup"><span data-stu-id="842b7-153">External</span></span></p></li>
<li><p><span data-ttu-id="842b7-154">Interna</span><span class="sxs-lookup"><span data-stu-id="842b7-154">Internal</span></span></p></li>
<li><p><span data-ttu-id="842b7-155">VPN</span><span class="sxs-lookup"><span data-stu-id="842b7-155">VPN</span></span></p></li>
<li><p><span data-ttu-id="842b7-156">Não VPN</span><span class="sxs-lookup"><span data-stu-id="842b7-156">Non-VPN</span></span></p></li>
<li><p><span data-ttu-id="842b7-157">Com fio</span><span class="sxs-lookup"><span data-stu-id="842b7-157">Wired</span></span></p></li>
<li><p><span data-ttu-id="842b7-158">Conexão</span><span class="sxs-lookup"><span data-stu-id="842b7-158">Wireless</span></span></p></li>
<li><p><span data-ttu-id="842b7-159">Externa e com fio</span><span class="sxs-lookup"><span data-stu-id="842b7-159">External and wired</span></span></p></li>
<li><p><span data-ttu-id="842b7-160">Externa e sem fio</span><span class="sxs-lookup"><span data-stu-id="842b7-160">External and wireless</span></span></p></li>
<li><p><span data-ttu-id="842b7-161">Externa e VPN</span><span class="sxs-lookup"><span data-stu-id="842b7-161">External and VPN</span></span></p></li>
<li><p><span data-ttu-id="842b7-162">Externa e não-VPN</span><span class="sxs-lookup"><span data-stu-id="842b7-162">External and non-VPN</span></span></p></li>
<li><p><span data-ttu-id="842b7-163">Interna e com fio</span><span class="sxs-lookup"><span data-stu-id="842b7-163">Internal and wired</span></span></p></li>
<li><p><span data-ttu-id="842b7-164">Interna e sem fio</span><span class="sxs-lookup"><span data-stu-id="842b7-164">Internal and wireless</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="842b7-165"><strong>Intervalo</strong></span><span class="sxs-lookup"><span data-stu-id="842b7-165"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="842b7-p108">Intervalo de tempo. Selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="842b7-p108">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="842b7-168">Por hora (é possível exibir no máximo 25 horas)</span><span class="sxs-lookup"><span data-stu-id="842b7-168">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="842b7-169">Diariamente (é possível exibir no máximo 31 dias)</span><span class="sxs-lookup"><span data-stu-id="842b7-169">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="842b7-170">Semanalmente (é possível exibir no máximo 12 semanas)</span><span class="sxs-lookup"><span data-stu-id="842b7-170">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="842b7-p109">Se as datas de início e término excederem o número máximo de valores permitidos para o intervalo selecionado, somente o número máximo de valores (a partir da data de início) será exibido. Por exemplo, se você selecionar o intervalo Diariamente com a data de início 7/7/12 e uma data de término de 28/2/12, os dados serão exibidos para os dias 7/8/2 00:00 horas até 7/9/12 00:00 horas (ou seja, um total de 31 dias de dados).</span><span class="sxs-lookup"><span data-stu-id="842b7-p109">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed. For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="842b7-173">Métricas</span><span class="sxs-lookup"><span data-stu-id="842b7-173">Metrics</span></span>

<span data-ttu-id="842b7-174">A tabela a seguir lista as informações fornecidas no Relatório de Comparação de Qualidade da Mídia.</span><span class="sxs-lookup"><span data-stu-id="842b7-174">The following table lists the information provided in the Media Quality Comparison Report.</span></span>

### <a name="media-quality-comparison-report-metrics"></a><span data-ttu-id="842b7-175">Métricas do Relatório de Comparação de Qualidade da Mídia</span><span class="sxs-lookup"><span data-stu-id="842b7-175">Media Quality Comparison Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="842b7-176">Nome</span><span class="sxs-lookup"><span data-stu-id="842b7-176">Name</span></span></th>
<th><span data-ttu-id="842b7-177">É possível classificar este item?</span><span class="sxs-lookup"><span data-stu-id="842b7-177">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="842b7-178">Descrição</span><span class="sxs-lookup"><span data-stu-id="842b7-178">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="842b7-179"><strong>Volume da chamada</strong></span><span class="sxs-lookup"><span data-stu-id="842b7-179"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="842b7-180">Não</span><span class="sxs-lookup"><span data-stu-id="842b7-180">No</span></span></p></td>
<td><p><span data-ttu-id="842b7-181">Número total de chamadas.</span><span class="sxs-lookup"><span data-stu-id="842b7-181">Total number of calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="842b7-182"><strong>Degradação (MOS)</strong></span><span class="sxs-lookup"><span data-stu-id="842b7-182"><strong>Degradation (MOS)</strong></span></span></p></td>
<td><p><span data-ttu-id="842b7-183">Não</span><span class="sxs-lookup"><span data-stu-id="842b7-183">No</span></span></p></td>
<td><p><span data-ttu-id="842b7-184">Valor médio de uma degradação de MOS (Pontuação média de opinião) em uma chamada.</span><span class="sxs-lookup"><span data-stu-id="842b7-184">Average amount of MOS (mean opinion score) degradation experienced during a call.</span></span> <span data-ttu-id="842b7-185">Os valores de degradação podem variar de um baixo de 0,0 para um alto de 5,0; um valor de 0,5 ou menos representa degradação aceitável.</span><span class="sxs-lookup"><span data-stu-id="842b7-185">Degradation values can range from a low of 0.0 to a high of 5.0; a value of 0.5 or less represents acceptable degradation.</span></span> <span data-ttu-id="842b7-186">Historicamente, médias pontuações de opinião foram calculadas tendo os usuários a taxa de qualidade de uma chamada em uma escala de 1 a 5.</span><span class="sxs-lookup"><span data-stu-id="842b7-186">Historically, mean opinion scores were calculated by having users rate the quality of a call on a scale of 1-to-5.</span></span> <span data-ttu-id="842b7-187">O Lync Server usa um conjunto de algoritmos para prever como os usuários classificaram uma chamada.</span><span class="sxs-lookup"><span data-stu-id="842b7-187">Lync Server uses a set of algorithms to predict how users would have rated a call.</span></span></p>
<p><span data-ttu-id="842b7-p111">Os valores de degradação altos podem ser causados por congestão, falta de largura de banda, congestionamento ou interferência sem fio ou um servidor de mídia ou ponto de extremidade sobrecarregado. A alta degradação resulta em perda ou distorção de áudio.</span><span class="sxs-lookup"><span data-stu-id="842b7-p111">High degradation values can be caused by congestion; lack of bandwidth; wireless congestion or interference, or an overloaded media server or endpoint. High degradation results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="842b7-190"><strong>Percentual de chamadas ruins</strong></span><span class="sxs-lookup"><span data-stu-id="842b7-190"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="842b7-191">Não</span><span class="sxs-lookup"><span data-stu-id="842b7-191">No</span></span></p></td>
<td><p><span data-ttu-id="842b7-p112">O número total de chamadas classificadas como ruins. Uma chamada ruim é qualquer chamada em que no mínimo uma das métricas medidas excedeu o valor permitido (por exemplo, uma chamada com tremulação excessiva).</span><span class="sxs-lookup"><span data-stu-id="842b7-p112">The total number of calls classified as poor. A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="842b7-194"><strong>Viagem de ida e volta (ms)</strong></span><span class="sxs-lookup"><span data-stu-id="842b7-194"><strong>Round trip (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="842b7-195">Não</span><span class="sxs-lookup"><span data-stu-id="842b7-195">No</span></span></p></td>
<td><p><span data-ttu-id="842b7-p113">Quantidade média de (em milissegundos) exigida para que um pacote de Protocolo de Transporte em Tempo Real viaje até outra extremidade e retorne. Tempos de viagem de ida e volta de 200 milissegundos ou menos são considerados de qualidade aceitável.</span><span class="sxs-lookup"><span data-stu-id="842b7-p113">Average amount of (in milliseconds) required for a Real-Time Transport Protocol packet to travel to another endpoint and then back. Round-trip times of 200 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="842b7-p114">Altos valores de tempo de resposta podem ser causados por roteamento de chamadas internacionais, configuração incorreta de um roteamento ou um servidor de mídia sobrecarregado. Tempos de resposta altos resultam em dificuldades para conversas de áudio bidirecionais e em tempo real.</span><span class="sxs-lookup"><span data-stu-id="842b7-p114">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="842b7-200"><strong>Perda de pacote </strong></span><span class="sxs-lookup"><span data-stu-id="842b7-200"><strong>Packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="842b7-201">Não</span><span class="sxs-lookup"><span data-stu-id="842b7-201">No</span></span></p></td>
<td><p><span data-ttu-id="842b7-p115">Taxa média de perda de pacotes de Protocolo de Transporte em Tempo Real (RTP). (A perda de pacotes ocorre quando pacotes RTP, um protocolo usado para transmitir áudio e vídeo pela internet, falha ao tentar alcançar seu destino). Altas taxas de perda geralmente são causadas por congestionamento, insuficiência da largura de banda, congestionamento ou interferência na rede sem fio ou um servidor de mídia sobrecarregado. A perda de pacotes normalmente resulta em distorção ou perda de áudio.</span><span class="sxs-lookup"><span data-stu-id="842b7-p115">Average rate of Real-Time Transport Protocol (RTP) packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="842b7-205"><strong>Tremulação (ms)</strong></span><span class="sxs-lookup"><span data-stu-id="842b7-205"><strong>Jitter (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="842b7-206">Não</span><span class="sxs-lookup"><span data-stu-id="842b7-206">No</span></span></p></td>
<td><p><span data-ttu-id="842b7-207">Tremulação média detectada entre chegadas de pacote RTP.</span><span class="sxs-lookup"><span data-stu-id="842b7-207">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="842b7-208">(Tremulação é uma medida do &quot;tremula&quot; de uma chamada.) Os valores de variação alta geralmente são causados por congestionamento ou por um servidor de mídia sobrecarregado e resultam em um áudio distorcido ou perdido.</span><span class="sxs-lookup"><span data-stu-id="842b7-208">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="842b7-209"><strong>Taxa de correção oculta</strong></span><span class="sxs-lookup"><span data-stu-id="842b7-209"><strong>Healer concealed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="842b7-210">Não</span><span class="sxs-lookup"><span data-stu-id="842b7-210">No</span></span></p></td>
<td><p><span data-ttu-id="842b7-p117">Taxa média de amostras de áudio ocultas para o número total de amostras. (Uma amostra de áudio oculta é uma técnica usada para suavizar a transição abrupta que normalmente seria causada por pacotes de rede descartados.) Valores altos indicam níveis consideráveis de perda de ocultação aplicada causada por perda de pacote ou tremulação e resulta na perda ou distorção de áudio.</span><span class="sxs-lookup"><span data-stu-id="842b7-p117">Average ratio of concealed audio samples to the total to the total number of samples. (A concealed audio sample is a technique used to smooth out the abrupt transition that would usually be caused by dropped network packets.) High values indicate significant levels of loss concealment applied caused by packet loss or jitter, and results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="842b7-213"><strong>Taxa de correção estendida</strong></span><span class="sxs-lookup"><span data-stu-id="842b7-213"><strong>Healer stretched ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="842b7-214">Não</span><span class="sxs-lookup"><span data-stu-id="842b7-214">No</span></span></p></td>
<td><p><span data-ttu-id="842b7-p118">Taxa média de amostras de áudio estendidas para o número total de amostras. (Áudio estendido é o áudio que foi expandido a fim de ajudar a manter a qualidade da chamada quando um pacote de rede descartado é detectado.) Valores altos indicam níveis significativos de extensão de amostra causada por tremulação e resultam em um som robótico ou distorcido.</span><span class="sxs-lookup"><span data-stu-id="842b7-p118">Average ratio of stretched audio samples to the total to the total number of samples. (Stretched audio is audio that has been expanded to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample stretching caused by jitter, and result in audio sounding robotic or distorted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="842b7-217"><strong>Taxa de correção compactada</strong></span><span class="sxs-lookup"><span data-stu-id="842b7-217"><strong>Healer compressed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="842b7-218">Não</span><span class="sxs-lookup"><span data-stu-id="842b7-218">No</span></span></p></td>
<td><p><span data-ttu-id="842b7-p119">Taxa média de amostras de áudio compactadas para o número total de amostras. (Áudio compactado é o áudio que foi compactado para ajudar a manter a qualidade da chamada quando um pacote de rede descartado é detectado.) Valores altos podem indicar níveis consideráveis de compactação de amostra causada por tremulação e resultam em um som acelerado ou distorcido.</span><span class="sxs-lookup"><span data-stu-id="842b7-p119">Average ratio of compressed audio samples to the total number of samples. (Compressed audio is audio that has been compressed to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample compression caused by jitter, and result in audio sounding accelerated or distorted.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

