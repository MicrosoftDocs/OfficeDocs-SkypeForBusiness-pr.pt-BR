---
title: 'Lync Server 2013: relatório de voz e vídeo ponto a ponto'
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
ms.openlocfilehash: 68cddb8296a94ff5d5b084895024d7379a42022c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755281"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="peer-to-peer-voice-and-video-report-in-lync-server-2013"></a><span data-ttu-id="74a4c-102">Relatório de voz e vídeo ponto a ponto no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="74a4c-102">Peer-to-Peer Voice and Video Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="74a4c-103">_**Tópico da última modificação:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="74a4c-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="74a4c-p101">O Relatório de Vídeo e Voz Ponto a Ponto oferece uma visão detalhada da distribuição de chamadas de voz e vídeo por um período específico (por exemplo, chamadas por hora ou chamadas por dia). O relatório também oferece a opção de exibir todas as chamadas de voz e vídeo realizadas ou de exibir apenas as chamadas bem-sucedidas ou com falha. Os relatórios mostram as informações das chamadas divididas nos seguintes agrupamentos:</span><span class="sxs-lookup"><span data-stu-id="74a4c-p101">The Peer-to-Peer Voice and Video Report provides a detailed look at the distribution of voice and video calls over a specified period of time (for example, calls per hour or calls per day). The report also gives you the option of viewing all the voice and video calls that were made, or of viewing only the successful or failed calls. The reports shows call information broken down into the following groupings:</span></span>

  - <span data-ttu-id="74a4c-107">Chamadas por pool</span><span class="sxs-lookup"><span data-stu-id="74a4c-107">Calls per pool</span></span>

  - <span data-ttu-id="74a4c-108">Chamadas por tipo de chamada (por exemplo, uma chamada de Lync para Lync versus uma chamada do Lync para uma pessoa na rede PSTN)</span><span class="sxs-lookup"><span data-stu-id="74a4c-108">Calls per call type (for example, a Lync to Lync call vs. a Lync call to a person on the PSTN network)</span></span>

  - <span data-ttu-id="74a4c-109">Chamadas por tipo de acesso (os usuários conectados na rede interna versus usuários conectados na rede externa)</span><span class="sxs-lookup"><span data-stu-id="74a4c-109">Calls per access type (users logged on to the internal network vs. users logged on to the external network)</span></span>

  - <span data-ttu-id="74a4c-110">Chamadas por servidor de mediação</span><span class="sxs-lookup"><span data-stu-id="74a4c-110">Calls per Mediation Server</span></span>

<div>

## <a name="to-access-the-peer-to-peer-voice-and-video-report"></a><span data-ttu-id="74a4c-111">Para acessar o relatório de vídeo e voz ponto a ponto</span><span class="sxs-lookup"><span data-stu-id="74a4c-111">To access the peer-to-peer voice and video report</span></span>

<span data-ttu-id="74a4c-112">É possível acessar o Relatório de Vídeo e Voz Ponto a Ponto apenas abrindo o Relatório de Resumo de Atividades Ponto a Ponto e clicando em qualquer uma das seguintes métricas:</span><span class="sxs-lookup"><span data-stu-id="74a4c-112">You can access the Peer-to-Peer Voice and Video Report only by opening the Peer-to-Peer Activity Summary Report and then clicking any of the following metrics:</span></span>

  - <span data-ttu-id="74a4c-113">Total de sessões de áudio ponto a ponto</span><span class="sxs-lookup"><span data-stu-id="74a4c-113">Total peer-to-peer audio sessions</span></span>

  - <span data-ttu-id="74a4c-114">Total de minutos de áudio ponto a ponto</span><span class="sxs-lookup"><span data-stu-id="74a4c-114">Total peer-to-peer audio minutes</span></span>

  - <span data-ttu-id="74a4c-115">Total de sessões de vídeo ponto a ponto</span><span class="sxs-lookup"><span data-stu-id="74a4c-115">Total peer-to-peer video sessions</span></span>

  - <span data-ttu-id="74a4c-116">Total de minutos de vídeo ponto a ponto</span><span class="sxs-lookup"><span data-stu-id="74a4c-116">Total peer-to-peer video minutes</span></span>

</div>

<div>

## <a name="to-make-the-best-use-of-the-peer-to-peer-voice-and-video-report"></a><span data-ttu-id="74a4c-117">Para aproveitar melhor o relatório de vídeo e voz ponto a ponto</span><span class="sxs-lookup"><span data-stu-id="74a4c-117">To make the best use of the peer-to-peer voice and video report</span></span>

<span data-ttu-id="74a4c-p102">Existem várias formas de filtrar o Relatório de Vídeo e Voz Ponto a Ponto. No entanto, essas opções de filtragem são ocultas da exibição por padrão. Para exibir as opções de filtragem disponíveis, clique no botão **Exibir/Ocultar Parâmetros** no canto superior direito da janela Relatório.</span><span class="sxs-lookup"><span data-stu-id="74a4c-p102">There are a number of ways you can filter the Peer-to-Peer Voice and Video Report. However, those filtering options are hidden from view by default. To view the filtering options available to you, click **Show/Hide Parameters** button in the upper-right corner of the Report window.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="74a4c-121">Filtros</span><span class="sxs-lookup"><span data-stu-id="74a4c-121">Filters</span></span>

<span data-ttu-id="74a4c-p103">Os filtros fornecem uma maneira de retornar um conjunto de dados mais direcionado ou de exibir dados de maneiras diferentes. A tabela a seguir lista os filtros que podem ser usados com o Relatório de Vídeo e Voz Ponto a Ponto.</span><span class="sxs-lookup"><span data-stu-id="74a4c-p103">Filters provide a way for you to return a more finely targeted set of data or to view the data in different ways. The following table lists the filters that you can use with the Peer-to-Peer Voice and Video Report.</span></span>

### <a name="peer-to-peer-voice-and-video-report-filters"></a><span data-ttu-id="74a4c-124">Filtros do relatório de vídeo e voz ponto a ponto</span><span class="sxs-lookup"><span data-stu-id="74a4c-124">Peer-to-peer voice and video report filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="74a4c-125">Nome</span><span class="sxs-lookup"><span data-stu-id="74a4c-125">Name</span></span></th>
<th><span data-ttu-id="74a4c-126">Descrição</span><span class="sxs-lookup"><span data-stu-id="74a4c-126">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="74a4c-127"><strong>De</strong></span><span class="sxs-lookup"><span data-stu-id="74a4c-127"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="74a4c-p104">Data e hora de início do intervalo de tempo. Para ver os dados por hora, insira a data e hora de início desta forma:</span><span class="sxs-lookup"><span data-stu-id="74a4c-p104">Start date and time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="74a4c-130">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="74a4c-130">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="74a4c-p105">Se você não inserir a hora de início, o relatório começará automaticamente à meia-noite do dia especificado. Para ver os dados por dia, insira somente a data:</span><span class="sxs-lookup"><span data-stu-id="74a4c-p105">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="74a4c-133">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="74a4c-133">7/7/2012</span></span></p>
<p><span data-ttu-id="74a4c-134">Para exibir por semana ou mês, insira uma data dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):</span><span class="sxs-lookup"><span data-stu-id="74a4c-134">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="74a4c-135">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="74a4c-135">7/3/2012</span></span></p>
<p><span data-ttu-id="74a4c-136">As semanas sempre vão de domingo a sábado.</span><span class="sxs-lookup"><span data-stu-id="74a4c-136">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74a4c-137"><strong>Até</strong></span><span class="sxs-lookup"><span data-stu-id="74a4c-137"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="74a4c-p106">Data/hora final de intervalo de tempo. Para ver os dados por horas, insira a data e hora final conforme segue:</span><span class="sxs-lookup"><span data-stu-id="74a4c-p106">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="74a4c-140">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="74a4c-140">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="74a4c-p107">Se você não inserir a hora final, o relatório terminará automaticamente à meia-noite do dia especificado. Para ver os dados por dia, insira somente a data:</span><span class="sxs-lookup"><span data-stu-id="74a4c-p107">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="74a4c-143">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="74a4c-143">7/7/2012</span></span></p>
<p><span data-ttu-id="74a4c-144">Para exibir por semana ou mês, insira uma data dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):</span><span class="sxs-lookup"><span data-stu-id="74a4c-144">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="74a4c-145">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="74a4c-145">7/3/2012</span></span></p>
<p><span data-ttu-id="74a4c-146">As semanas sempre vão de domingo a sábado.</span><span class="sxs-lookup"><span data-stu-id="74a4c-146">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74a4c-147"><strong>Intervalo</strong></span><span class="sxs-lookup"><span data-stu-id="74a4c-147"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="74a4c-p108">Intervalo de tempo. Selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="74a4c-p108">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="74a4c-150">Por hora (é possível exibir no máximo 25 horas)</span><span class="sxs-lookup"><span data-stu-id="74a4c-150">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="74a4c-151">Diariamente (é possível exibir no máximo 31 dias)</span><span class="sxs-lookup"><span data-stu-id="74a4c-151">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="74a4c-152">Semanalmente (é possível exibir no máximo 12 semanas)</span><span class="sxs-lookup"><span data-stu-id="74a4c-152">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="74a4c-153">Mensalmente (é possível exibir no máximo 12 meses)</span><span class="sxs-lookup"><span data-stu-id="74a4c-153">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="74a4c-154">Se as datas de início e término excederem o número máximo de valores permitidos para o intervalo selecionado, somente o número máximo de valores (a partir da data de início) será exibido.</span><span class="sxs-lookup"><span data-stu-id="74a4c-154">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed.</span></span> <span data-ttu-id="74a4c-155">Por exemplo, se você selecionar o intervalo diário com uma data de início de 7/7/2012 e uma data de término de 2/28/2012, os dados serão exibidos para os dias 8/7/2012 12:00 AM a 9/7/2012 12:00 AM (ou seja, um total de 31 dias da importância dos dados).</span><span class="sxs-lookup"><span data-stu-id="74a4c-155">For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74a4c-156"><strong>Tipo de mídia</strong></span><span class="sxs-lookup"><span data-stu-id="74a4c-156"><strong>Media type</strong></span></span></p></td>
<td><p><span data-ttu-id="74a4c-p110">Indica o tipo de mídia usado na sessão. Selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="74a4c-p110">Indicates the type of media used in the session. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="74a4c-159">Ambos</span><span class="sxs-lookup"><span data-stu-id="74a4c-159">Both</span></span></p></li>
<li><p><span data-ttu-id="74a4c-160">Áudio</span><span class="sxs-lookup"><span data-stu-id="74a4c-160">Audio</span></span></p></li>
<li><p><span data-ttu-id="74a4c-161">Vídeo</span><span class="sxs-lookup"><span data-stu-id="74a4c-161">Video</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74a4c-162"><strong>Disposição da chamada</strong></span><span class="sxs-lookup"><span data-stu-id="74a4c-162"><strong>Call disposition</strong></span></span></p></td>
<td><p><span data-ttu-id="74a4c-p111">Indica o sucesso ou fracasso da sessão. Selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="74a4c-p111">Indicates the success or failure of the session. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="74a4c-165">[Todos]</span><span class="sxs-lookup"><span data-stu-id="74a4c-165">[All]</span></span></p></li>
<li><p><span data-ttu-id="74a4c-166">Chamadas com Êxito</span><span class="sxs-lookup"><span data-stu-id="74a4c-166">Success Calls</span></span></p></li>
<li><p><span data-ttu-id="74a4c-167">Chamadas com Falha</span><span class="sxs-lookup"><span data-stu-id="74a4c-167">Failed Calls</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74a4c-168"><strong>Relatório por</strong></span><span class="sxs-lookup"><span data-stu-id="74a4c-168"><strong>Report by</strong></span></span></p></td>
<td><p><span data-ttu-id="74a4c-p112">Indica os valores a serem usados no relatório. Selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="74a4c-p112">Indicates the values to be used in the report. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="74a4c-171">Contagem de sessões</span><span class="sxs-lookup"><span data-stu-id="74a4c-171">Session count</span></span></p></li>
<li><p><span data-ttu-id="74a4c-172">Minutos de chamadas</span><span class="sxs-lookup"><span data-stu-id="74a4c-172">Call minutes</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-pool"></a><span data-ttu-id="74a4c-173">Métricas para atividade de vídeo e voz ponto a ponto por pool</span><span class="sxs-lookup"><span data-stu-id="74a4c-173">Metrics for peer-to-peer voice and video activity by Pool</span></span>

<span data-ttu-id="74a4c-174">A tabela a seguir lista as informações fornecidas no Relatório de Vídeo e Voz Ponto a Ponto para cada pool.</span><span class="sxs-lookup"><span data-stu-id="74a4c-174">The following table lists the information provided in the Peer-to-Peer Voice and Video Report for each pool.</span></span>

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-pool"></a><span data-ttu-id="74a4c-175">Métricas para atividade de vídeo e voz ponto a ponto por pool</span><span class="sxs-lookup"><span data-stu-id="74a4c-175">Metrics for peer-to-peer voice and video activity by pool</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="74a4c-176">Nome</span><span class="sxs-lookup"><span data-stu-id="74a4c-176">Name</span></span></th>
<th><span data-ttu-id="74a4c-177">Você pode classificar este item?</span><span class="sxs-lookup"><span data-stu-id="74a4c-177">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="74a4c-178">Descrição</span><span class="sxs-lookup"><span data-stu-id="74a4c-178">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="74a4c-179"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="74a4c-179"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="74a4c-180">Não</span><span class="sxs-lookup"><span data-stu-id="74a4c-180">No</span></span></p></td>
<td><p><span data-ttu-id="74a4c-181">Nome do pool de registradores ou servidor de borda usado para a chamada.</span><span class="sxs-lookup"><span data-stu-id="74a4c-181">Name of the Registrar pool or Edge Server used for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74a4c-182"><strong>Data/Hora</strong></span><span class="sxs-lookup"><span data-stu-id="74a4c-182"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="74a4c-183">Não</span><span class="sxs-lookup"><span data-stu-id="74a4c-183">No</span></span></p></td>
<td><p><span data-ttu-id="74a4c-184">Período de data e hora durante o qual a chamada foi realizada.</span><span class="sxs-lookup"><span data-stu-id="74a4c-184">Date and time period in which the call took place.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74a4c-185"><strong>Total</strong></span><span class="sxs-lookup"><span data-stu-id="74a4c-185"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="74a4c-186">Não</span><span class="sxs-lookup"><span data-stu-id="74a4c-186">No</span></span></p></td>
<td><p><span data-ttu-id="74a4c-187">Número total de sessões ou contagem total de mensagens.</span><span class="sxs-lookup"><span data-stu-id="74a4c-187">Total number of sessions or total message count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-call-type"></a><span data-ttu-id="74a4c-188">Métricas da atividade de vídeo e voz ponto a ponto por tipo de chamada</span><span class="sxs-lookup"><span data-stu-id="74a4c-188">Metrics for peer-to-peer voice and video activity by call type</span></span>

<span data-ttu-id="74a4c-189">A tabela a seguir lista as informações fornecidas no Relatório de Vídeo e Voz Ponto a Ponto para cada tipo de chamada realizada.</span><span class="sxs-lookup"><span data-stu-id="74a4c-189">The following table lists the information provided in the Peer-to-Peer Voice and Video Report for each type of call that was made.</span></span>

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-call-type"></a><span data-ttu-id="74a4c-190">Métricas da atividade de vídeo e voz ponto a ponto por tipo de chamada</span><span class="sxs-lookup"><span data-stu-id="74a4c-190">Metrics for peer-to-peer voice and video activity by call type</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="74a4c-191">Nome</span><span class="sxs-lookup"><span data-stu-id="74a4c-191">Name</span></span></th>
<th><span data-ttu-id="74a4c-192">Você pode classificar este item?</span><span class="sxs-lookup"><span data-stu-id="74a4c-192">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="74a4c-193">Descrição</span><span class="sxs-lookup"><span data-stu-id="74a4c-193">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="74a4c-194"><strong>Tipo de chamada</strong></span><span class="sxs-lookup"><span data-stu-id="74a4c-194"><strong>Call type</strong></span></span></p></td>
<td><p><span data-ttu-id="74a4c-195">Não</span><span class="sxs-lookup"><span data-stu-id="74a4c-195">No</span></span></p></td>
<td><p><span data-ttu-id="74a4c-p113">Indica o tipo de chamada realizada. Os valores são um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="74a4c-p113">Indicates the type of call that was made. Values are one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="74a4c-198">UC-para-UC</span><span class="sxs-lookup"><span data-stu-id="74a4c-198">UC-to-UC</span></span></p></li>
<li><p><span data-ttu-id="74a4c-199">UC-para-PSTN</span><span class="sxs-lookup"><span data-stu-id="74a4c-199">UC-to-PSTN</span></span></p></li>
<li><p><span data-ttu-id="74a4c-200">PSTN-para-UC</span><span class="sxs-lookup"><span data-stu-id="74a4c-200">PSTN-to-UC</span></span></p></li>
<li><p><span data-ttu-id="74a4c-201">PSTN-para-PSTN</span><span class="sxs-lookup"><span data-stu-id="74a4c-201">PSTN-to-PSTN</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74a4c-202"><strong>Data/Hora</strong></span><span class="sxs-lookup"><span data-stu-id="74a4c-202"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="74a4c-203">Não</span><span class="sxs-lookup"><span data-stu-id="74a4c-203">No</span></span></p></td>
<td><p><span data-ttu-id="74a4c-204">Período de data e hora durante o qual a chamada foi realizada.</span><span class="sxs-lookup"><span data-stu-id="74a4c-204">Date and time period in which the call took place.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74a4c-205"><strong>Total</strong></span><span class="sxs-lookup"><span data-stu-id="74a4c-205"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="74a4c-206">Não</span><span class="sxs-lookup"><span data-stu-id="74a4c-206">No</span></span></p></td>
<td><p><span data-ttu-id="74a4c-207">Número total de sessões ou contagem total de mensagens.</span><span class="sxs-lookup"><span data-stu-id="74a4c-207">Total number of sessions or total message count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-access-type"></a><span data-ttu-id="74a4c-208">Métricas da atividade de vídeo e voz ponto a ponto por tipo de acesso</span><span class="sxs-lookup"><span data-stu-id="74a4c-208">Metrics for peer-to-peer voice and video activity by access type</span></span>

<span data-ttu-id="74a4c-209">A tabela a seguir lista as informações fornecidas no Relatório de Vídeo e Voz Ponto a Ponto para cada tipo de acesso à rede.</span><span class="sxs-lookup"><span data-stu-id="74a4c-209">The following table lists the information provided in the Peer-to-Peer Voice and Video Report for each network access type.</span></span>

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-access-type"></a><span data-ttu-id="74a4c-210">Métricas da atividade de vídeo e voz ponto a ponto por tipo de acesso</span><span class="sxs-lookup"><span data-stu-id="74a4c-210">Metrics for peer-to-peer voice and video activity by access type</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="74a4c-211">Nome</span><span class="sxs-lookup"><span data-stu-id="74a4c-211">Name</span></span></th>
<th><span data-ttu-id="74a4c-212">Você pode classificar este item?</span><span class="sxs-lookup"><span data-stu-id="74a4c-212">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="74a4c-213">Descrição</span><span class="sxs-lookup"><span data-stu-id="74a4c-213">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="74a4c-214"><strong>Tipo de atividade</strong></span><span class="sxs-lookup"><span data-stu-id="74a4c-214"><strong>Activity type</strong></span></span></p></td>
<td><p><span data-ttu-id="74a4c-215">Não</span><span class="sxs-lookup"><span data-stu-id="74a4c-215">No</span></span></p></td>
<td><p><span data-ttu-id="74a4c-p114">Indica se os clientes estavam conectados na rede interna ou rede externa quando a chamada foi realizada. Os valores são normalmente um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="74a4c-p114">Indicates whether the clients were logged on to the internal network or the external network when the call was placed. Values are typically one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="74a4c-218">Interno</span><span class="sxs-lookup"><span data-stu-id="74a4c-218">Internal</span></span></p></li>
<li><p><span data-ttu-id="74a4c-219">Externo</span><span class="sxs-lookup"><span data-stu-id="74a4c-219">External</span></span></p></li>
<li><p><span data-ttu-id="74a4c-220">Misto</span><span class="sxs-lookup"><span data-stu-id="74a4c-220">Mixed</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74a4c-221"><strong>Data/Hora</strong></span><span class="sxs-lookup"><span data-stu-id="74a4c-221"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="74a4c-222">Não</span><span class="sxs-lookup"><span data-stu-id="74a4c-222">No</span></span></p></td>
<td><p><span data-ttu-id="74a4c-223">Período de data e hora durante o qual a chamada foi realizada.</span><span class="sxs-lookup"><span data-stu-id="74a4c-223">Date and time period in which the call took place.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74a4c-224"><strong>Total</strong></span><span class="sxs-lookup"><span data-stu-id="74a4c-224"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="74a4c-225">Não</span><span class="sxs-lookup"><span data-stu-id="74a4c-225">No</span></span></p></td>
<td><p><span data-ttu-id="74a4c-226">Número total de sessões ou contagem total de mensagens.</span><span class="sxs-lookup"><span data-stu-id="74a4c-226">Total number of sessions or total message count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-mediation-server"></a><span data-ttu-id="74a4c-227">Métricas para atividade de vídeo e voz ponto a ponto por servidor de mediação</span><span class="sxs-lookup"><span data-stu-id="74a4c-227">Metrics for peer-to-peer voice and video activity by mediation server</span></span>

<span data-ttu-id="74a4c-228">A tabela a seguir lista as informações fornecidas no relatório de voz e vídeo ponto a ponto para cada servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="74a4c-228">The following table lists the information provided in the Peer-to-Peer Voice and Video Report for each Mediation Server.</span></span>

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-mediation-server"></a><span data-ttu-id="74a4c-229">Métricas para atividade de vídeo e voz ponto a ponto por servidor de mediação</span><span class="sxs-lookup"><span data-stu-id="74a4c-229">Metrics for peer-to-peer voice and video activity by mediation server</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="74a4c-230">Nome</span><span class="sxs-lookup"><span data-stu-id="74a4c-230">Name</span></span></th>
<th><span data-ttu-id="74a4c-231">Você pode classificar este item?</span><span class="sxs-lookup"><span data-stu-id="74a4c-231">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="74a4c-232">Descrição</span><span class="sxs-lookup"><span data-stu-id="74a4c-232">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="74a4c-233"><strong>Servidor de Mediação</strong></span><span class="sxs-lookup"><span data-stu-id="74a4c-233"><strong>Mediation Server</strong></span></span></p></td>
<td><p><span data-ttu-id="74a4c-234">Não</span><span class="sxs-lookup"><span data-stu-id="74a4c-234">No</span></span></p></td>
<td><p><span data-ttu-id="74a4c-235">Nome do servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="74a4c-235">Name of the Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74a4c-236"><strong>Data/Hora</strong></span><span class="sxs-lookup"><span data-stu-id="74a4c-236"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="74a4c-237">Não</span><span class="sxs-lookup"><span data-stu-id="74a4c-237">No</span></span></p></td>
<td><p><span data-ttu-id="74a4c-238">Período de data e hora durante o qual a chamada foi realizada.</span><span class="sxs-lookup"><span data-stu-id="74a4c-238">Date and time period in which the call took place.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74a4c-239"><strong>Total</strong></span><span class="sxs-lookup"><span data-stu-id="74a4c-239"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="74a4c-240">Não</span><span class="sxs-lookup"><span data-stu-id="74a4c-240">No</span></span></p></td>
<td><p><span data-ttu-id="74a4c-241">Número total de sessões ou contagem total de mensagens.</span><span class="sxs-lookup"><span data-stu-id="74a4c-241">Total number of sessions or total message count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

