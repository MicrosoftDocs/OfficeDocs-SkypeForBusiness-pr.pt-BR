---
title: 'Lync Server 2013: relatório de vídeo e voz ponto a ponto'
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
ms.openlocfilehash: 974f403f65b494964affc4fbdc4880820ecb2db2
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038653"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="peer-to-peer-voice-and-video-report-in-lync-server-2013"></a><span data-ttu-id="4d065-102">Relatório de vídeo e voz ponto a ponto no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4d065-102">Peer-to-Peer Voice and Video Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4d065-103">_**Última modificação do tópico:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="4d065-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="4d065-104">O relatório de vídeo e voz ponto a ponto fornece uma visão detalhada da distribuição de chamadas de voz e vídeo em um período de tempo especificado (por exemplo, chamadas por hora ou chamadas por dia).</span><span class="sxs-lookup"><span data-stu-id="4d065-104">The Peer-to-Peer Voice and Video Report provides a detailed look at the distribution of voice and video calls over a specified period of time (for example, calls per hour or calls per day).</span></span> <span data-ttu-id="4d065-105">O relatório também oferece a opção de exibir todas as chamadas de voz e vídeo feitas ou de exibir apenas as chamadas com êxito ou com falha.</span><span class="sxs-lookup"><span data-stu-id="4d065-105">The report also gives you the option of viewing all the voice and video calls that were made, or of viewing only the successful or failed calls.</span></span> <span data-ttu-id="4d065-106">Os relatórios mostram as informações de chamadas divididas nos seguintes agrupamentos:</span><span class="sxs-lookup"><span data-stu-id="4d065-106">The reports shows call information broken down into the following groupings:</span></span>

  - <span data-ttu-id="4d065-107">Chamadas por pool</span><span class="sxs-lookup"><span data-stu-id="4d065-107">Calls per pool</span></span>

  - <span data-ttu-id="4d065-108">Chamadas por tipo de chamada (por exemplo, uma chamada Lync para Lync vs. uma chamada Lync para uma pessoa na rede PSTN)</span><span class="sxs-lookup"><span data-stu-id="4d065-108">Calls per call type (for example, a Lync to Lync call vs. a Lync call to a person on the PSTN network)</span></span>

  - <span data-ttu-id="4d065-109">Chamadas por tipo de acesso (usuários conectados à rede interna vs. usuários conectados à rede externa)</span><span class="sxs-lookup"><span data-stu-id="4d065-109">Calls per access type (users logged on to the internal network vs. users logged on to the external network)</span></span>

  - <span data-ttu-id="4d065-110">Chamadas por servidor de mediação</span><span class="sxs-lookup"><span data-stu-id="4d065-110">Calls per Mediation Server</span></span>

<div>

## <a name="to-access-the-peer-to-peer-voice-and-video-report"></a><span data-ttu-id="4d065-111">Para acessar o relatório de vídeo e voz ponto a ponto</span><span class="sxs-lookup"><span data-stu-id="4d065-111">To access the peer-to-peer voice and video report</span></span>

<span data-ttu-id="4d065-112">Você pode acessar o relatório de vídeo e voz ponto a ponto apenas abrindo o relatório de Resumo de atividades ponto a ponto e clicando em qualquer uma das seguintes métricas:</span><span class="sxs-lookup"><span data-stu-id="4d065-112">You can access the Peer-to-Peer Voice and Video Report only by opening the Peer-to-Peer Activity Summary Report and then clicking any of the following metrics:</span></span>

  - <span data-ttu-id="4d065-113">Total de sessões de áudio ponto a ponto</span><span class="sxs-lookup"><span data-stu-id="4d065-113">Total peer-to-peer audio sessions</span></span>

  - <span data-ttu-id="4d065-114">Total de minutos de áudio ponto a ponto</span><span class="sxs-lookup"><span data-stu-id="4d065-114">Total peer-to-peer audio minutes</span></span>

  - <span data-ttu-id="4d065-115">Total de sessões de vídeo ponto a ponto</span><span class="sxs-lookup"><span data-stu-id="4d065-115">Total peer-to-peer video sessions</span></span>

  - <span data-ttu-id="4d065-116">Total de minutos de vídeo ponto a ponto</span><span class="sxs-lookup"><span data-stu-id="4d065-116">Total peer-to-peer video minutes</span></span>

</div>

<div>

## <a name="to-make-the-best-use-of-the-peer-to-peer-voice-and-video-report"></a><span data-ttu-id="4d065-117">Para usar melhor o relatório de vídeo e voz ponto a ponto</span><span class="sxs-lookup"><span data-stu-id="4d065-117">To make the best use of the peer-to-peer voice and video report</span></span>

<span data-ttu-id="4d065-118">Há várias maneiras de filtrar o relatório de vídeo e voz ponto a ponto.</span><span class="sxs-lookup"><span data-stu-id="4d065-118">There are a number of ways you can filter the Peer-to-Peer Voice and Video Report.</span></span> <span data-ttu-id="4d065-119">No entanto, essas opções de filtragem são ocultas da exibição por padrão.</span><span class="sxs-lookup"><span data-stu-id="4d065-119">However, those filtering options are hidden from view by default.</span></span> <span data-ttu-id="4d065-120">Para exibir as opções de filtragem disponíveis, clique no botão **Mostrar/ocultar parâmetros** no canto superior direito da janela relatório.</span><span class="sxs-lookup"><span data-stu-id="4d065-120">To view the filtering options available to you, click **Show/Hide Parameters** button in the upper-right corner of the Report window.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="4d065-121">Filtros</span><span class="sxs-lookup"><span data-stu-id="4d065-121">Filters</span></span>

<span data-ttu-id="4d065-122">Os filtros fornecem uma maneira de retornar um conjunto de dados mais direcionado ou exibir os dados de maneiras diferentes.</span><span class="sxs-lookup"><span data-stu-id="4d065-122">Filters provide a way for you to return a more finely targeted set of data or to view the data in different ways.</span></span> <span data-ttu-id="4d065-123">A tabela a seguir lista os filtros que você pode usar com o relatório de vídeo e voz ponto a ponto.</span><span class="sxs-lookup"><span data-stu-id="4d065-123">The following table lists the filters that you can use with the Peer-to-Peer Voice and Video Report.</span></span>

### <a name="peer-to-peer-voice-and-video-report-filters"></a><span data-ttu-id="4d065-124">Filtros de relatório de vídeo e voz ponto a ponto</span><span class="sxs-lookup"><span data-stu-id="4d065-124">Peer-to-peer voice and video report filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4d065-125">Nome</span><span class="sxs-lookup"><span data-stu-id="4d065-125">Name</span></span></th>
<th><span data-ttu-id="4d065-126">Descrição</span><span class="sxs-lookup"><span data-stu-id="4d065-126">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4d065-127"><strong>De</strong></span><span class="sxs-lookup"><span data-stu-id="4d065-127"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="4d065-p104">Data e hora de início para o intervalo de tempo. Para ver os dados por hora, digite a data e hora de início no seguinte formato:</span><span class="sxs-lookup"><span data-stu-id="4d065-p104">Start date and time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="4d065-130">7/7/2012 13:00 horas</span><span class="sxs-lookup"><span data-stu-id="4d065-130">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="4d065-p105">Se você não inserir uma hora inicial, o relatório começa automaticamente as 12:00 AM no dia especificado. Para exibir os dados por dia, insira apenas a data:</span><span class="sxs-lookup"><span data-stu-id="4d065-p105">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="4d065-133">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="4d065-133">7/7/2012</span></span></p>
<p><span data-ttu-id="4d065-134">Para exibir por semana ou mês, insira uma data que está dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):</span><span class="sxs-lookup"><span data-stu-id="4d065-134">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="4d065-135">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="4d065-135">7/3/2012</span></span></p>
<p><span data-ttu-id="4d065-136">As semanas sempre são de Domingo a Sábado.</span><span class="sxs-lookup"><span data-stu-id="4d065-136">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4d065-137"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="4d065-137"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="4d065-p106">Data/hora final para o intervalo de tempo. Para exibir os dados por hora, insira a data e hora final como a seguir:</span><span class="sxs-lookup"><span data-stu-id="4d065-p106">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="4d065-140">7/7/2012 13:00 horas</span><span class="sxs-lookup"><span data-stu-id="4d065-140">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="4d065-p107">Se você não inserir uma hora final, o relatório termina automaticamente as 12:00 AM no dia especificado. Para exibir os dados por dia, insira apenas a data:</span><span class="sxs-lookup"><span data-stu-id="4d065-p107">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="4d065-143">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="4d065-143">7/7/2012</span></span></p>
<p><span data-ttu-id="4d065-144">Para exibir por semana ou mês, insira uma data que está dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):</span><span class="sxs-lookup"><span data-stu-id="4d065-144">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="4d065-145">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="4d065-145">7/3/2012</span></span></p>
<p><span data-ttu-id="4d065-146">As semanas são sempre de domingo a sábado.</span><span class="sxs-lookup"><span data-stu-id="4d065-146">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4d065-147"><strong>Intervalo</strong></span><span class="sxs-lookup"><span data-stu-id="4d065-147"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="4d065-p108">Intervalo de tempo. Selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="4d065-p108">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="4d065-150">Por hora (é possível exibir no máximo 25 horas)</span><span class="sxs-lookup"><span data-stu-id="4d065-150">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="4d065-151">Diariamente (é possível exibir no máximo 31 dias)</span><span class="sxs-lookup"><span data-stu-id="4d065-151">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="4d065-152">Semanalmente (é possível exibir no máximo 12 semanas)</span><span class="sxs-lookup"><span data-stu-id="4d065-152">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="4d065-153">Mensalmente (é possível exibir no máximo 12 meses)</span><span class="sxs-lookup"><span data-stu-id="4d065-153">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="4d065-p109">Se as datas de início e término excederem o número máximo de valores permitidos para o intervalo selecionado, somente o número máximo de valores (a partir da data de início) será exibido. Por exemplo, se você selecionar o intervalo Diariamente com data de início em 7/7/12 e data de término de 28/2/12, os dados serão exibidos do dia 7/8/12, às 12:00, até o dia 7/9/12, às 12:00 (ou seja, um total de 31 dias de dados).</span><span class="sxs-lookup"><span data-stu-id="4d065-p109">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed. For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4d065-156"><strong>Tipo de mídia</strong></span><span class="sxs-lookup"><span data-stu-id="4d065-156"><strong>Media type</strong></span></span></p></td>
<td><p><span data-ttu-id="4d065-157">Indica o tipo de mídia usado na sessão.</span><span class="sxs-lookup"><span data-stu-id="4d065-157">Indicates the type of media used in the session.</span></span> <span data-ttu-id="4d065-158">Selecione uma destas opções:</span><span class="sxs-lookup"><span data-stu-id="4d065-158">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="4d065-159">Ambos</span><span class="sxs-lookup"><span data-stu-id="4d065-159">Both</span></span></p></li>
<li><p><span data-ttu-id="4d065-160">Áudio</span><span class="sxs-lookup"><span data-stu-id="4d065-160">Audio</span></span></p></li>
<li><p><span data-ttu-id="4d065-161">Vídeo</span><span class="sxs-lookup"><span data-stu-id="4d065-161">Video</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4d065-162"><strong>Disposição da chamada</strong></span><span class="sxs-lookup"><span data-stu-id="4d065-162"><strong>Call disposition</strong></span></span></p></td>
<td><p><span data-ttu-id="4d065-163">Indica o êxito ou a falha da sessão.</span><span class="sxs-lookup"><span data-stu-id="4d065-163">Indicates the success or failure of the session.</span></span> <span data-ttu-id="4d065-164">Selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="4d065-164">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="4d065-165">Todos os</span><span class="sxs-lookup"><span data-stu-id="4d065-165">[All]</span></span></p></li>
<li><p><span data-ttu-id="4d065-166">Chamadas de êxito</span><span class="sxs-lookup"><span data-stu-id="4d065-166">Success Calls</span></span></p></li>
<li><p><span data-ttu-id="4d065-167">Chamadas com falha</span><span class="sxs-lookup"><span data-stu-id="4d065-167">Failed Calls</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4d065-168"><strong>Relatório por</strong></span><span class="sxs-lookup"><span data-stu-id="4d065-168"><strong>Report by</strong></span></span></p></td>
<td><p><span data-ttu-id="4d065-p112">Indica os valores a serem usados no relatório. Selecione um dos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="4d065-p112">Indicates the values to be used in the report. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="4d065-171">Contagem de sessão</span><span class="sxs-lookup"><span data-stu-id="4d065-171">Session count</span></span></p></li>
<li><p><span data-ttu-id="4d065-172">Minutos de chamada</span><span class="sxs-lookup"><span data-stu-id="4d065-172">Call minutes</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-pool"></a><span data-ttu-id="4d065-173">Métricas para atividade de vídeo e voz ponto a ponto por pool</span><span class="sxs-lookup"><span data-stu-id="4d065-173">Metrics for peer-to-peer voice and video activity by Pool</span></span>

<span data-ttu-id="4d065-174">A tabela a seguir lista as informações fornecidas no relatório de vídeo e voz ponto a ponto para cada pool.</span><span class="sxs-lookup"><span data-stu-id="4d065-174">The following table lists the information provided in the Peer-to-Peer Voice and Video Report for each pool.</span></span>

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-pool"></a><span data-ttu-id="4d065-175">Métricas para atividade de vídeo e voz ponto a ponto por pool</span><span class="sxs-lookup"><span data-stu-id="4d065-175">Metrics for peer-to-peer voice and video activity by pool</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4d065-176">Nome</span><span class="sxs-lookup"><span data-stu-id="4d065-176">Name</span></span></th>
<th><span data-ttu-id="4d065-177">É possível classificar este item?</span><span class="sxs-lookup"><span data-stu-id="4d065-177">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="4d065-178">Descrição</span><span class="sxs-lookup"><span data-stu-id="4d065-178">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4d065-179"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="4d065-179"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="4d065-180">Não</span><span class="sxs-lookup"><span data-stu-id="4d065-180">No</span></span></p></td>
<td><p><span data-ttu-id="4d065-181">Nome do pool de registradores ou servidor de borda usado para a chamada.</span><span class="sxs-lookup"><span data-stu-id="4d065-181">Name of the Registrar pool or Edge Server used for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4d065-182"><strong>Data/Hora</strong></span><span class="sxs-lookup"><span data-stu-id="4d065-182"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="4d065-183">Não</span><span class="sxs-lookup"><span data-stu-id="4d065-183">No</span></span></p></td>
<td><p><span data-ttu-id="4d065-184">O período de data e hora em que a chamada ocorreu.</span><span class="sxs-lookup"><span data-stu-id="4d065-184">Date and time period in which the call took place.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4d065-185"><strong>Total</strong></span><span class="sxs-lookup"><span data-stu-id="4d065-185"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="4d065-186">Não</span><span class="sxs-lookup"><span data-stu-id="4d065-186">No</span></span></p></td>
<td><p><span data-ttu-id="4d065-187">Número total de sessões ou de contagem total de mensagens.</span><span class="sxs-lookup"><span data-stu-id="4d065-187">Total number of sessions or total message count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-call-type"></a><span data-ttu-id="4d065-188">Métricas para atividade de vídeo e voz ponto a ponto por tipo de chamada</span><span class="sxs-lookup"><span data-stu-id="4d065-188">Metrics for peer-to-peer voice and video activity by call type</span></span>

<span data-ttu-id="4d065-189">A tabela a seguir lista as informações fornecidas no relatório de vídeo e voz ponto a ponto para cada tipo de chamada realizada.</span><span class="sxs-lookup"><span data-stu-id="4d065-189">The following table lists the information provided in the Peer-to-Peer Voice and Video Report for each type of call that was made.</span></span>

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-call-type"></a><span data-ttu-id="4d065-190">Métricas para atividade de vídeo e voz ponto a ponto por tipo de chamada</span><span class="sxs-lookup"><span data-stu-id="4d065-190">Metrics for peer-to-peer voice and video activity by call type</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4d065-191">Nome</span><span class="sxs-lookup"><span data-stu-id="4d065-191">Name</span></span></th>
<th><span data-ttu-id="4d065-192">É possível classificar este item?</span><span class="sxs-lookup"><span data-stu-id="4d065-192">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="4d065-193">Descrição</span><span class="sxs-lookup"><span data-stu-id="4d065-193">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4d065-194"><strong>Tipo de chamada</strong></span><span class="sxs-lookup"><span data-stu-id="4d065-194"><strong>Call type</strong></span></span></p></td>
<td><p><span data-ttu-id="4d065-195">Não</span><span class="sxs-lookup"><span data-stu-id="4d065-195">No</span></span></p></td>
<td><p><span data-ttu-id="4d065-196">Indica o tipo de chamada realizada.</span><span class="sxs-lookup"><span data-stu-id="4d065-196">Indicates the type of call that was made.</span></span> <span data-ttu-id="4d065-197">Os valores são um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="4d065-197">Values are one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="4d065-198">UC para UC</span><span class="sxs-lookup"><span data-stu-id="4d065-198">UC-to-UC</span></span></p></li>
<li><p><span data-ttu-id="4d065-199">UC para PSTN</span><span class="sxs-lookup"><span data-stu-id="4d065-199">UC-to-PSTN</span></span></p></li>
<li><p><span data-ttu-id="4d065-200">PSTN para UC</span><span class="sxs-lookup"><span data-stu-id="4d065-200">PSTN-to-UC</span></span></p></li>
<li><p><span data-ttu-id="4d065-201">PSTN para PSTN</span><span class="sxs-lookup"><span data-stu-id="4d065-201">PSTN-to-PSTN</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4d065-202"><strong>Data/Hora</strong></span><span class="sxs-lookup"><span data-stu-id="4d065-202"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="4d065-203">Não</span><span class="sxs-lookup"><span data-stu-id="4d065-203">No</span></span></p></td>
<td><p><span data-ttu-id="4d065-204">O período de data e hora em que a chamada ocorreu.</span><span class="sxs-lookup"><span data-stu-id="4d065-204">Date and time period in which the call took place.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4d065-205"><strong>Total</strong></span><span class="sxs-lookup"><span data-stu-id="4d065-205"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="4d065-206">Não</span><span class="sxs-lookup"><span data-stu-id="4d065-206">No</span></span></p></td>
<td><p><span data-ttu-id="4d065-207">Número total de sessões ou de contagem total de mensagens.</span><span class="sxs-lookup"><span data-stu-id="4d065-207">Total number of sessions or total message count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-access-type"></a><span data-ttu-id="4d065-208">Métricas para atividade de vídeo e voz ponto a ponto por tipo de acesso</span><span class="sxs-lookup"><span data-stu-id="4d065-208">Metrics for peer-to-peer voice and video activity by access type</span></span>

<span data-ttu-id="4d065-209">A tabela a seguir lista as informações fornecidas no relatório de vídeo e voz ponto a ponto para cada tipo de acesso à rede.</span><span class="sxs-lookup"><span data-stu-id="4d065-209">The following table lists the information provided in the Peer-to-Peer Voice and Video Report for each network access type.</span></span>

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-access-type"></a><span data-ttu-id="4d065-210">Métricas para atividade de vídeo e voz ponto a ponto por tipo de acesso</span><span class="sxs-lookup"><span data-stu-id="4d065-210">Metrics for peer-to-peer voice and video activity by access type</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4d065-211">Nome</span><span class="sxs-lookup"><span data-stu-id="4d065-211">Name</span></span></th>
<th><span data-ttu-id="4d065-212">É possível classificar este item?</span><span class="sxs-lookup"><span data-stu-id="4d065-212">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="4d065-213">Descrição</span><span class="sxs-lookup"><span data-stu-id="4d065-213">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4d065-214"><strong>Tipo de atividade</strong></span><span class="sxs-lookup"><span data-stu-id="4d065-214"><strong>Activity type</strong></span></span></p></td>
<td><p><span data-ttu-id="4d065-215">Não</span><span class="sxs-lookup"><span data-stu-id="4d065-215">No</span></span></p></td>
<td><p><span data-ttu-id="4d065-216">Indica se os clientes fizeram logon na rede interna ou na rede externa quando a chamada foi feita.</span><span class="sxs-lookup"><span data-stu-id="4d065-216">Indicates whether the clients were logged on to the internal network or the external network when the call was placed.</span></span> <span data-ttu-id="4d065-217">Normalmente, os valores são um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="4d065-217">Values are typically one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="4d065-218">Interna</span><span class="sxs-lookup"><span data-stu-id="4d065-218">Internal</span></span></p></li>
<li><p><span data-ttu-id="4d065-219">Externa</span><span class="sxs-lookup"><span data-stu-id="4d065-219">External</span></span></p></li>
<li><p><span data-ttu-id="4d065-220">Mistos</span><span class="sxs-lookup"><span data-stu-id="4d065-220">Mixed</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4d065-221"><strong>Data/Hora</strong></span><span class="sxs-lookup"><span data-stu-id="4d065-221"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="4d065-222">Não</span><span class="sxs-lookup"><span data-stu-id="4d065-222">No</span></span></p></td>
<td><p><span data-ttu-id="4d065-223">O período de data e hora em que a chamada ocorreu.</span><span class="sxs-lookup"><span data-stu-id="4d065-223">Date and time period in which the call took place.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4d065-224"><strong>Total</strong></span><span class="sxs-lookup"><span data-stu-id="4d065-224"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="4d065-225">Não</span><span class="sxs-lookup"><span data-stu-id="4d065-225">No</span></span></p></td>
<td><p><span data-ttu-id="4d065-226">Número total de sessões ou de contagem total de mensagens.</span><span class="sxs-lookup"><span data-stu-id="4d065-226">Total number of sessions or total message count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-mediation-server"></a><span data-ttu-id="4d065-227">Métricas para atividade de vídeo e voz ponto a ponto por servidor de mediação</span><span class="sxs-lookup"><span data-stu-id="4d065-227">Metrics for peer-to-peer voice and video activity by mediation server</span></span>

<span data-ttu-id="4d065-228">A tabela a seguir lista as informações fornecidas no relatório de vídeo e voz ponto a ponto para cada servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="4d065-228">The following table lists the information provided in the Peer-to-Peer Voice and Video Report for each Mediation Server.</span></span>

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-mediation-server"></a><span data-ttu-id="4d065-229">Métricas para atividade de vídeo e voz ponto a ponto por servidor de mediação</span><span class="sxs-lookup"><span data-stu-id="4d065-229">Metrics for peer-to-peer voice and video activity by mediation server</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4d065-230">Nome</span><span class="sxs-lookup"><span data-stu-id="4d065-230">Name</span></span></th>
<th><span data-ttu-id="4d065-231">É possível classificar este item?</span><span class="sxs-lookup"><span data-stu-id="4d065-231">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="4d065-232">Descrição</span><span class="sxs-lookup"><span data-stu-id="4d065-232">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4d065-233"><strong>Servidor de Mediação</strong></span><span class="sxs-lookup"><span data-stu-id="4d065-233"><strong>Mediation Server</strong></span></span></p></td>
<td><p><span data-ttu-id="4d065-234">Não</span><span class="sxs-lookup"><span data-stu-id="4d065-234">No</span></span></p></td>
<td><p><span data-ttu-id="4d065-235">Nome do servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="4d065-235">Name of the Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4d065-236"><strong>Data/Hora</strong></span><span class="sxs-lookup"><span data-stu-id="4d065-236"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="4d065-237">Não</span><span class="sxs-lookup"><span data-stu-id="4d065-237">No</span></span></p></td>
<td><p><span data-ttu-id="4d065-238">O período de data e hora em que a chamada ocorreu.</span><span class="sxs-lookup"><span data-stu-id="4d065-238">Date and time period in which the call took place.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4d065-239"><strong>Total</strong></span><span class="sxs-lookup"><span data-stu-id="4d065-239"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="4d065-240">Não</span><span class="sxs-lookup"><span data-stu-id="4d065-240">No</span></span></p></td>
<td><p><span data-ttu-id="4d065-241">Número total de sessões ou de contagem total de mensagens.</span><span class="sxs-lookup"><span data-stu-id="4d065-241">Total number of sessions or total message count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

