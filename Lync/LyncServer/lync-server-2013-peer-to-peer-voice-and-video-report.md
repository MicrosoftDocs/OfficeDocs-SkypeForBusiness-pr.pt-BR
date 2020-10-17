---
title: 'Lync Server 2013: relatório de vídeo e voz ponto a ponto'
description: 'Lync Server 2013: relatório de vídeo e voz ponto a ponto.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Peer-to-Peer Voice and Video Report
ms:assetid: e17c36b5-5a2f-4673-9696-3b2d31c2bb2f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615040(v=OCS.15)
ms:contentKeyID: 48185535
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 43041926b3d6b57508b6ee4c53ca9cb055bcb348
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557267"
---
# <a name="peer-to-peer-voice-and-video-report-in-lync-server-2013"></a><span data-ttu-id="806ab-103">Relatório de vídeo e voz ponto a ponto no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="806ab-103">Peer-to-Peer Voice and Video Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="806ab-104">_**Última modificação do tópico:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="806ab-104">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="806ab-105">O relatório de vídeo e voz ponto a ponto fornece uma visão detalhada da distribuição de chamadas de voz e vídeo em um período de tempo especificado (por exemplo, chamadas por hora ou chamadas por dia).</span><span class="sxs-lookup"><span data-stu-id="806ab-105">The Peer-to-Peer Voice and Video Report provides a detailed look at the distribution of voice and video calls over a specified period of time (for example, calls per hour or calls per day).</span></span> <span data-ttu-id="806ab-106">O relatório também oferece a opção de exibir todas as chamadas de voz e vídeo feitas ou de exibir apenas as chamadas com êxito ou com falha.</span><span class="sxs-lookup"><span data-stu-id="806ab-106">The report also gives you the option of viewing all the voice and video calls that were made, or of viewing only the successful or failed calls.</span></span> <span data-ttu-id="806ab-107">Os relatórios mostram as informações de chamadas divididas nos seguintes agrupamentos:</span><span class="sxs-lookup"><span data-stu-id="806ab-107">The reports shows call information broken down into the following groupings:</span></span>

  - <span data-ttu-id="806ab-108">Chamadas por pool</span><span class="sxs-lookup"><span data-stu-id="806ab-108">Calls per pool</span></span>

  - <span data-ttu-id="806ab-109">Chamadas por tipo de chamada (por exemplo, uma chamada Lync para Lync vs. uma chamada Lync para uma pessoa na rede PSTN)</span><span class="sxs-lookup"><span data-stu-id="806ab-109">Calls per call type (for example, a Lync to Lync call vs. a Lync call to a person on the PSTN network)</span></span>

  - <span data-ttu-id="806ab-110">Chamadas por tipo de acesso (usuários conectados à rede interna vs. usuários conectados à rede externa)</span><span class="sxs-lookup"><span data-stu-id="806ab-110">Calls per access type (users logged on to the internal network vs. users logged on to the external network)</span></span>

  - <span data-ttu-id="806ab-111">Chamadas por servidor de mediação</span><span class="sxs-lookup"><span data-stu-id="806ab-111">Calls per Mediation Server</span></span>

<div>

## <a name="to-access-the-peer-to-peer-voice-and-video-report"></a><span data-ttu-id="806ab-112">Para acessar o relatório de vídeo e voz ponto a ponto</span><span class="sxs-lookup"><span data-stu-id="806ab-112">To access the peer-to-peer voice and video report</span></span>

<span data-ttu-id="806ab-113">Você pode acessar o relatório de vídeo e voz ponto a ponto apenas abrindo o relatório de Resumo de atividades ponto a ponto e clicando em qualquer uma das seguintes métricas:</span><span class="sxs-lookup"><span data-stu-id="806ab-113">You can access the Peer-to-Peer Voice and Video Report only by opening the Peer-to-Peer Activity Summary Report and then clicking any of the following metrics:</span></span>

  - <span data-ttu-id="806ab-114">Total de sessões de áudio ponto a ponto</span><span class="sxs-lookup"><span data-stu-id="806ab-114">Total peer-to-peer audio sessions</span></span>

  - <span data-ttu-id="806ab-115">Total de minutos de áudio ponto a ponto</span><span class="sxs-lookup"><span data-stu-id="806ab-115">Total peer-to-peer audio minutes</span></span>

  - <span data-ttu-id="806ab-116">Total de sessões de vídeo ponto a ponto</span><span class="sxs-lookup"><span data-stu-id="806ab-116">Total peer-to-peer video sessions</span></span>

  - <span data-ttu-id="806ab-117">Total de minutos de vídeo ponto a ponto</span><span class="sxs-lookup"><span data-stu-id="806ab-117">Total peer-to-peer video minutes</span></span>

</div>

<div>

## <a name="to-make-the-best-use-of-the-peer-to-peer-voice-and-video-report"></a><span data-ttu-id="806ab-118">Para usar melhor o relatório de vídeo e voz ponto a ponto</span><span class="sxs-lookup"><span data-stu-id="806ab-118">To make the best use of the peer-to-peer voice and video report</span></span>

<span data-ttu-id="806ab-119">Há várias maneiras de filtrar o relatório de vídeo e voz ponto a ponto.</span><span class="sxs-lookup"><span data-stu-id="806ab-119">There are a number of ways you can filter the Peer-to-Peer Voice and Video Report.</span></span> <span data-ttu-id="806ab-120">No entanto, essas opções de filtragem são ocultas da exibição por padrão.</span><span class="sxs-lookup"><span data-stu-id="806ab-120">However, those filtering options are hidden from view by default.</span></span> <span data-ttu-id="806ab-121">Para exibir as opções de filtragem disponíveis, clique no botão **Mostrar/ocultar parâmetros** no canto superior direito da janela relatório.</span><span class="sxs-lookup"><span data-stu-id="806ab-121">To view the filtering options available to you, click **Show/Hide Parameters** button in the upper-right corner of the Report window.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="806ab-122">Filtros</span><span class="sxs-lookup"><span data-stu-id="806ab-122">Filters</span></span>

<span data-ttu-id="806ab-123">Os filtros fornecem uma maneira de retornar um conjunto de dados mais direcionado ou exibir os dados de maneiras diferentes.</span><span class="sxs-lookup"><span data-stu-id="806ab-123">Filters provide a way for you to return a more finely targeted set of data or to view the data in different ways.</span></span> <span data-ttu-id="806ab-124">A tabela a seguir lista os filtros que você pode usar com o relatório de vídeo e voz ponto a ponto.</span><span class="sxs-lookup"><span data-stu-id="806ab-124">The following table lists the filters that you can use with the Peer-to-Peer Voice and Video Report.</span></span>

### <a name="peer-to-peer-voice-and-video-report-filters"></a><span data-ttu-id="806ab-125">Filtros de relatório de vídeo e voz ponto a ponto</span><span class="sxs-lookup"><span data-stu-id="806ab-125">Peer-to-peer voice and video report filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="806ab-126">Nome</span><span class="sxs-lookup"><span data-stu-id="806ab-126">Name</span></span></th>
<th><span data-ttu-id="806ab-127">Descrição</span><span class="sxs-lookup"><span data-stu-id="806ab-127">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="806ab-128"><strong>De</strong></span><span class="sxs-lookup"><span data-stu-id="806ab-128"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="806ab-p104">Data e hora de início para o intervalo de tempo. Para ver os dados por hora, digite a data e hora de início no seguinte formato:</span><span class="sxs-lookup"><span data-stu-id="806ab-p104">Start date and time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="806ab-131">07/07/2012 13:00</span><span class="sxs-lookup"><span data-stu-id="806ab-131">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="806ab-p105">Se você não inserir uma hora inicial, o relatório começa automaticamente as 12:00 AM no dia especificado. Para exibir os dados por dia, insira apenas a data:</span><span class="sxs-lookup"><span data-stu-id="806ab-p105">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="806ab-134">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="806ab-134">7/7/2012</span></span></p>
<p><span data-ttu-id="806ab-135">Para exibir por semana ou mês, insira uma data que está dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):</span><span class="sxs-lookup"><span data-stu-id="806ab-135">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="806ab-136">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="806ab-136">7/3/2012</span></span></p>
<p><span data-ttu-id="806ab-137">As semanas são sempre de domingo a sábado.</span><span class="sxs-lookup"><span data-stu-id="806ab-137">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="806ab-138"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="806ab-138"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="806ab-p106">Data/hora final para o intervalo de tempo. Para exibir os dados por hora, insira a data e hora final como a seguir:</span><span class="sxs-lookup"><span data-stu-id="806ab-p106">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="806ab-141">7/7/2012 13:00 horas</span><span class="sxs-lookup"><span data-stu-id="806ab-141">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="806ab-p107">Se você não inserir uma hora final, o relatório termina automaticamente as 12:00 AM no dia especificado. Para exibir os dados por dia, insira apenas a data:</span><span class="sxs-lookup"><span data-stu-id="806ab-p107">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="806ab-144">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="806ab-144">7/7/2012</span></span></p>
<p><span data-ttu-id="806ab-145">Para exibir por semana ou mês, insira uma data que está dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):</span><span class="sxs-lookup"><span data-stu-id="806ab-145">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="806ab-146">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="806ab-146">7/3/2012</span></span></p>
<p><span data-ttu-id="806ab-147">As semanas são sempre de domingo a sábado.</span><span class="sxs-lookup"><span data-stu-id="806ab-147">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="806ab-148"><strong>Intervalo</strong></span><span class="sxs-lookup"><span data-stu-id="806ab-148"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="806ab-p108">Intervalo de tempo. Selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="806ab-p108">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="806ab-151">Por hora (é possível exibir no máximo 25 horas)</span><span class="sxs-lookup"><span data-stu-id="806ab-151">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="806ab-152">Diariamente (é possível exibir no máximo 31 dias)</span><span class="sxs-lookup"><span data-stu-id="806ab-152">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="806ab-153">Semanalmente (é possível exibir no máximo 12 semanas)</span><span class="sxs-lookup"><span data-stu-id="806ab-153">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="806ab-154">Mensalmente (é possível exibir no máximo 12 meses)</span><span class="sxs-lookup"><span data-stu-id="806ab-154">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="806ab-p109">Se as datas de início e término excederem o número máximo de valores permitidos para o intervalo selecionado, somente o número máximo de valores (a partir da data de início) será exibido. Por exemplo, se você selecionar o intervalo Diariamente com data de início em 7/7/12 e data de término de 28/2/12, os dados serão exibidos do dia 7/8/12, às 12:00, até o dia 7/9/12, às 12:00 (ou seja, um total de 31 dias de dados).</span><span class="sxs-lookup"><span data-stu-id="806ab-p109">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed. For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="806ab-157"><strong>Tipo de mídia</strong></span><span class="sxs-lookup"><span data-stu-id="806ab-157"><strong>Media type</strong></span></span></p></td>
<td><p><span data-ttu-id="806ab-158">Indica o tipo de mídia usado na sessão.</span><span class="sxs-lookup"><span data-stu-id="806ab-158">Indicates the type of media used in the session.</span></span> <span data-ttu-id="806ab-159">Selecione uma destas opções:</span><span class="sxs-lookup"><span data-stu-id="806ab-159">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="806ab-160">Ambos</span><span class="sxs-lookup"><span data-stu-id="806ab-160">Both</span></span></p></li>
<li><p><span data-ttu-id="806ab-161">Áudio</span><span class="sxs-lookup"><span data-stu-id="806ab-161">Audio</span></span></p></li>
<li><p><span data-ttu-id="806ab-162">Vídeo</span><span class="sxs-lookup"><span data-stu-id="806ab-162">Video</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="806ab-163"><strong>Disposição da chamada</strong></span><span class="sxs-lookup"><span data-stu-id="806ab-163"><strong>Call disposition</strong></span></span></p></td>
<td><p><span data-ttu-id="806ab-164">Indica o êxito ou a falha da sessão.</span><span class="sxs-lookup"><span data-stu-id="806ab-164">Indicates the success or failure of the session.</span></span> <span data-ttu-id="806ab-165">Selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="806ab-165">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="806ab-166">Todos os</span><span class="sxs-lookup"><span data-stu-id="806ab-166">[All]</span></span></p></li>
<li><p><span data-ttu-id="806ab-167">Chamadas de êxito</span><span class="sxs-lookup"><span data-stu-id="806ab-167">Success Calls</span></span></p></li>
<li><p><span data-ttu-id="806ab-168">Chamadas com falha</span><span class="sxs-lookup"><span data-stu-id="806ab-168">Failed Calls</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="806ab-169"><strong>Relatório por</strong></span><span class="sxs-lookup"><span data-stu-id="806ab-169"><strong>Report by</strong></span></span></p></td>
<td><p><span data-ttu-id="806ab-p112">Indica os valores a serem usados no relatório. Selecione um dos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="806ab-p112">Indicates the values to be used in the report. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="806ab-172">Contagem de sessão</span><span class="sxs-lookup"><span data-stu-id="806ab-172">Session count</span></span></p></li>
<li><p><span data-ttu-id="806ab-173">Minutos de chamada</span><span class="sxs-lookup"><span data-stu-id="806ab-173">Call minutes</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-pool"></a><span data-ttu-id="806ab-174">Métricas para atividade de vídeo e voz ponto a ponto por pool</span><span class="sxs-lookup"><span data-stu-id="806ab-174">Metrics for peer-to-peer voice and video activity by Pool</span></span>

<span data-ttu-id="806ab-175">A tabela a seguir lista as informações fornecidas no relatório de vídeo e voz ponto a ponto para cada pool.</span><span class="sxs-lookup"><span data-stu-id="806ab-175">The following table lists the information provided in the Peer-to-Peer Voice and Video Report for each pool.</span></span>

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-pool"></a><span data-ttu-id="806ab-176">Métricas para atividade de vídeo e voz ponto a ponto por pool</span><span class="sxs-lookup"><span data-stu-id="806ab-176">Metrics for peer-to-peer voice and video activity by pool</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="806ab-177">Nome</span><span class="sxs-lookup"><span data-stu-id="806ab-177">Name</span></span></th>
<th><span data-ttu-id="806ab-178">É possível classificar este item?</span><span class="sxs-lookup"><span data-stu-id="806ab-178">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="806ab-179">Descrição</span><span class="sxs-lookup"><span data-stu-id="806ab-179">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="806ab-180"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="806ab-180"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="806ab-181">Não</span><span class="sxs-lookup"><span data-stu-id="806ab-181">No</span></span></p></td>
<td><p><span data-ttu-id="806ab-182">Nome do pool de registradores ou servidor de borda usado para a chamada.</span><span class="sxs-lookup"><span data-stu-id="806ab-182">Name of the Registrar pool or Edge Server used for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="806ab-183"><strong>Data/Hora</strong></span><span class="sxs-lookup"><span data-stu-id="806ab-183"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="806ab-184">Não</span><span class="sxs-lookup"><span data-stu-id="806ab-184">No</span></span></p></td>
<td><p><span data-ttu-id="806ab-185">O período de data e hora em que a chamada ocorreu.</span><span class="sxs-lookup"><span data-stu-id="806ab-185">Date and time period in which the call took place.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="806ab-186"><strong>Total</strong></span><span class="sxs-lookup"><span data-stu-id="806ab-186"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="806ab-187">Não</span><span class="sxs-lookup"><span data-stu-id="806ab-187">No</span></span></p></td>
<td><p><span data-ttu-id="806ab-188">Número total de sessões ou de contagem total de mensagens.</span><span class="sxs-lookup"><span data-stu-id="806ab-188">Total number of sessions or total message count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-call-type"></a><span data-ttu-id="806ab-189">Métricas para atividade de vídeo e voz ponto a ponto por tipo de chamada</span><span class="sxs-lookup"><span data-stu-id="806ab-189">Metrics for peer-to-peer voice and video activity by call type</span></span>

<span data-ttu-id="806ab-190">A tabela a seguir lista as informações fornecidas no relatório de vídeo e voz ponto a ponto para cada tipo de chamada realizada.</span><span class="sxs-lookup"><span data-stu-id="806ab-190">The following table lists the information provided in the Peer-to-Peer Voice and Video Report for each type of call that was made.</span></span>

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-call-type"></a><span data-ttu-id="806ab-191">Métricas para atividade de vídeo e voz ponto a ponto por tipo de chamada</span><span class="sxs-lookup"><span data-stu-id="806ab-191">Metrics for peer-to-peer voice and video activity by call type</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="806ab-192">Nome</span><span class="sxs-lookup"><span data-stu-id="806ab-192">Name</span></span></th>
<th><span data-ttu-id="806ab-193">É possível classificar este item?</span><span class="sxs-lookup"><span data-stu-id="806ab-193">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="806ab-194">Descrição</span><span class="sxs-lookup"><span data-stu-id="806ab-194">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="806ab-195"><strong>Tipo de chamada</strong></span><span class="sxs-lookup"><span data-stu-id="806ab-195"><strong>Call type</strong></span></span></p></td>
<td><p><span data-ttu-id="806ab-196">Não</span><span class="sxs-lookup"><span data-stu-id="806ab-196">No</span></span></p></td>
<td><p><span data-ttu-id="806ab-197">Indica o tipo de chamada realizada.</span><span class="sxs-lookup"><span data-stu-id="806ab-197">Indicates the type of call that was made.</span></span> <span data-ttu-id="806ab-198">Os valores são um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="806ab-198">Values are one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="806ab-199">UC para UC</span><span class="sxs-lookup"><span data-stu-id="806ab-199">UC-to-UC</span></span></p></li>
<li><p><span data-ttu-id="806ab-200">UC para PSTN</span><span class="sxs-lookup"><span data-stu-id="806ab-200">UC-to-PSTN</span></span></p></li>
<li><p><span data-ttu-id="806ab-201">PSTN para UC</span><span class="sxs-lookup"><span data-stu-id="806ab-201">PSTN-to-UC</span></span></p></li>
<li><p><span data-ttu-id="806ab-202">PSTN para PSTN</span><span class="sxs-lookup"><span data-stu-id="806ab-202">PSTN-to-PSTN</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="806ab-203"><strong>Data/Hora</strong></span><span class="sxs-lookup"><span data-stu-id="806ab-203"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="806ab-204">Não</span><span class="sxs-lookup"><span data-stu-id="806ab-204">No</span></span></p></td>
<td><p><span data-ttu-id="806ab-205">O período de data e hora em que a chamada ocorreu.</span><span class="sxs-lookup"><span data-stu-id="806ab-205">Date and time period in which the call took place.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="806ab-206"><strong>Total</strong></span><span class="sxs-lookup"><span data-stu-id="806ab-206"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="806ab-207">Não</span><span class="sxs-lookup"><span data-stu-id="806ab-207">No</span></span></p></td>
<td><p><span data-ttu-id="806ab-208">Número total de sessões ou de contagem total de mensagens.</span><span class="sxs-lookup"><span data-stu-id="806ab-208">Total number of sessions or total message count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-access-type"></a><span data-ttu-id="806ab-209">Métricas para atividade de vídeo e voz ponto a ponto por tipo de acesso</span><span class="sxs-lookup"><span data-stu-id="806ab-209">Metrics for peer-to-peer voice and video activity by access type</span></span>

<span data-ttu-id="806ab-210">A tabela a seguir lista as informações fornecidas no relatório de vídeo e voz ponto a ponto para cada tipo de acesso à rede.</span><span class="sxs-lookup"><span data-stu-id="806ab-210">The following table lists the information provided in the Peer-to-Peer Voice and Video Report for each network access type.</span></span>

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-access-type"></a><span data-ttu-id="806ab-211">Métricas para atividade de vídeo e voz ponto a ponto por tipo de acesso</span><span class="sxs-lookup"><span data-stu-id="806ab-211">Metrics for peer-to-peer voice and video activity by access type</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="806ab-212">Nome</span><span class="sxs-lookup"><span data-stu-id="806ab-212">Name</span></span></th>
<th><span data-ttu-id="806ab-213">É possível classificar este item?</span><span class="sxs-lookup"><span data-stu-id="806ab-213">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="806ab-214">Descrição</span><span class="sxs-lookup"><span data-stu-id="806ab-214">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="806ab-215"><strong>Tipo de atividade</strong></span><span class="sxs-lookup"><span data-stu-id="806ab-215"><strong>Activity type</strong></span></span></p></td>
<td><p><span data-ttu-id="806ab-216">Não</span><span class="sxs-lookup"><span data-stu-id="806ab-216">No</span></span></p></td>
<td><p><span data-ttu-id="806ab-217">Indica se os clientes fizeram logon na rede interna ou na rede externa quando a chamada foi feita.</span><span class="sxs-lookup"><span data-stu-id="806ab-217">Indicates whether the clients were logged on to the internal network or the external network when the call was placed.</span></span> <span data-ttu-id="806ab-218">Normalmente, os valores são um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="806ab-218">Values are typically one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="806ab-219">Interno</span><span class="sxs-lookup"><span data-stu-id="806ab-219">Internal</span></span></p></li>
<li><p><span data-ttu-id="806ab-220">Externo</span><span class="sxs-lookup"><span data-stu-id="806ab-220">External</span></span></p></li>
<li><p><span data-ttu-id="806ab-221">Mistos</span><span class="sxs-lookup"><span data-stu-id="806ab-221">Mixed</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="806ab-222"><strong>Data/Hora</strong></span><span class="sxs-lookup"><span data-stu-id="806ab-222"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="806ab-223">Não</span><span class="sxs-lookup"><span data-stu-id="806ab-223">No</span></span></p></td>
<td><p><span data-ttu-id="806ab-224">O período de data e hora em que a chamada ocorreu.</span><span class="sxs-lookup"><span data-stu-id="806ab-224">Date and time period in which the call took place.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="806ab-225"><strong>Total</strong></span><span class="sxs-lookup"><span data-stu-id="806ab-225"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="806ab-226">Não</span><span class="sxs-lookup"><span data-stu-id="806ab-226">No</span></span></p></td>
<td><p><span data-ttu-id="806ab-227">Número total de sessões ou de contagem total de mensagens.</span><span class="sxs-lookup"><span data-stu-id="806ab-227">Total number of sessions or total message count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-mediation-server"></a><span data-ttu-id="806ab-228">Métricas para atividade de vídeo e voz ponto a ponto por servidor de mediação</span><span class="sxs-lookup"><span data-stu-id="806ab-228">Metrics for peer-to-peer voice and video activity by mediation server</span></span>

<span data-ttu-id="806ab-229">A tabela a seguir lista as informações fornecidas no relatório de vídeo e voz ponto a ponto para cada servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="806ab-229">The following table lists the information provided in the Peer-to-Peer Voice and Video Report for each Mediation Server.</span></span>

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-mediation-server"></a><span data-ttu-id="806ab-230">Métricas para atividade de vídeo e voz ponto a ponto por servidor de mediação</span><span class="sxs-lookup"><span data-stu-id="806ab-230">Metrics for peer-to-peer voice and video activity by mediation server</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="806ab-231">Nome</span><span class="sxs-lookup"><span data-stu-id="806ab-231">Name</span></span></th>
<th><span data-ttu-id="806ab-232">É possível classificar este item?</span><span class="sxs-lookup"><span data-stu-id="806ab-232">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="806ab-233">Descrição</span><span class="sxs-lookup"><span data-stu-id="806ab-233">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="806ab-234"><strong>Servidor de mediação</strong></span><span class="sxs-lookup"><span data-stu-id="806ab-234"><strong>Mediation Server</strong></span></span></p></td>
<td><p><span data-ttu-id="806ab-235">Não</span><span class="sxs-lookup"><span data-stu-id="806ab-235">No</span></span></p></td>
<td><p><span data-ttu-id="806ab-236">Nome do servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="806ab-236">Name of the Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="806ab-237"><strong>Data/Hora</strong></span><span class="sxs-lookup"><span data-stu-id="806ab-237"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="806ab-238">Não</span><span class="sxs-lookup"><span data-stu-id="806ab-238">No</span></span></p></td>
<td><p><span data-ttu-id="806ab-239">O período de data e hora em que a chamada ocorreu.</span><span class="sxs-lookup"><span data-stu-id="806ab-239">Date and time period in which the call took place.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="806ab-240"><strong>Total</strong></span><span class="sxs-lookup"><span data-stu-id="806ab-240"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="806ab-241">Não</span><span class="sxs-lookup"><span data-stu-id="806ab-241">No</span></span></p></td>
<td><p><span data-ttu-id="806ab-242">Número total de sessões ou de contagem total de mensagens.</span><span class="sxs-lookup"><span data-stu-id="806ab-242">Total number of sessions or total message count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

