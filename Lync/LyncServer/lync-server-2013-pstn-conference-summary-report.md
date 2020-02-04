---
title: 'Lync Server 2013: relatório de Resumo de conferência PSTN'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: PSTN Conference Summary Report
ms:assetid: 8e2f0862-4dfa-4c2b-bf8d-ad71419f15d2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615014(v=OCS.15)
ms:contentKeyID: 48184764
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f8cd36f651a84b25f7e8163a8cfc40aff5162f90
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724791"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="pstn-conference-summary-report-in-lync-server-2013"></a><span data-ttu-id="edaf3-102">Relatório de Resumo de conferência PSTN no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="edaf3-102">PSTN Conference Summary Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="edaf3-103">_**Tópico da última modificação:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="edaf3-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="edaf3-104">No Microsoft Lync Server 2013, uma conferência PSTN é qualquer conferência na qual pelo menos um participante disca para a parte de áudio por meio de um telefone PSTN (rede telefônica pública comutada).</span><span class="sxs-lookup"><span data-stu-id="edaf3-104">In Microsoft Lync Server 2013, a PSTN conference is any conference in which at least one participant dials in to the audio portion by a using a PSTN (public switched telephone network) phone.</span></span> <span data-ttu-id="edaf3-105">(Um telefone PSTN é um "telefone fixo", um telefone celular ou qualquer outro telefone que não usa voz sobre IP.) Ainda que sejam chamadas de conferências PSTN nos relatórios de monitoramento, essas conferências talvez sejam mais conhecidas como conferências discadas.</span><span class="sxs-lookup"><span data-stu-id="edaf3-105">(A PSTN phone is a "landline," a cell phone, or any other phone which does not make use of Voice over IP.) Although referred to as PSTN conferences in the Monitoring Reports, these conferences are perhaps more-commonly known as dial-in conferences.</span></span>

<span data-ttu-id="edaf3-p102">O Relatório de resumo de conferência fornece informações sobre todas as conferências PSTN feitas em sua organização (isto é, todas as conferências que tenham pelo menos um usuário discado). O relatório contém informações sobre o número total de conferências PSTN, total de número de pessoas que participaram nessas conferências e, talvez, o mais importante, o número total de usuários discados (a métrica de Total de participantes PSTN).</span><span class="sxs-lookup"><span data-stu-id="edaf3-p102">The PSTN Conference Summary Report provides information about all the PSTN conferences held in your organization (that is, all the conferences that had at least one dial-in user). The report includes information about the total number of PSTN conferences, the total number of people who participated in those conferences, and, perhaps, most important, the total number of dial-in users (the Total PSTN participants metric).</span></span>

<div>

## <a name="accessing-the-pstn-conference-summary-report"></a><span data-ttu-id="edaf3-108">Como acessar o Relatório de resumo de conferência PSTN</span><span class="sxs-lookup"><span data-stu-id="edaf3-108">Accessing the PSTN Conference Summary Report</span></span>

<span data-ttu-id="edaf3-p103">O Relatório de resumo de conferência PSTN pode ser acessado apenas da página inicial dos Relatórios de Monitoramento. Este relatório não está vinculado a nenhum outro. Observe que você não pode recuperar informações de chamadas detalhadas para uma conferência PSTN, em parte porque os pontos de extremidade individuais são responsáveis por enviar essas informações. Os telefones PSTN não são capazes de rastrear ou enviar informações de detalhes de chamada.</span><span class="sxs-lookup"><span data-stu-id="edaf3-p103">The PSTN Conference Summary Report can only be accessed from the Monitoring Reports home page. This report is not linked to any other reports. Note that you cannot retrieve detailed call information for a PSTN conference, in part because individual endpoints are responsible for submitting this information. PSTN phones are not capable of tracking or submitting call detail information.</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-pstn-conference-summary-report"></a><span data-ttu-id="edaf3-113">Como usar melhor o Relatório de resumo de conferência PSTN</span><span class="sxs-lookup"><span data-stu-id="edaf3-113">Making the Best Use of the PSTN Conference Summary Report</span></span>

<span data-ttu-id="edaf3-114">Para determinar a porcentagem de todas as suas conferências que incluem usuários de discagem, compare o valor da métrica total de conferências PSTN com a métrica total de conferências encontradas no [relatório de Resumo de conferências no Lync Server 2013](lync-server-2013-conference-summary-report.md).</span><span class="sxs-lookup"><span data-stu-id="edaf3-114">To determine the percentage of all your conferences that include dial-in users, compare the value of the Total PSTN conferences metric with the Total conferences metric found on the [Conference Summary Report in Lync Server 2013](lync-server-2013-conference-summary-report.md).</span></span>

<span data-ttu-id="edaf3-115">Se você não vir o número de conferências PSTN que esperava ver, saiba que a capacidade de organizar uma conferência que permita usuários discados depende da política de conferência que foi atribuída a um usuário: se poucos usuários tiverem permissão para hospedar conferências PSTN, você obviamente verá poucas conferências PSTN.</span><span class="sxs-lookup"><span data-stu-id="edaf3-115">If you don't see as many PSTN conferences as you might have expected to see, keep in mind that the ability to organize a conference that allows dial-in users depends on the conferencing policy that has been assigned to a user: if very few of your users are allowed to hold PSTN conferences you would obviously see very few PSTN conferences.</span></span> <span data-ttu-id="edaf3-116">Você pode verificar rapidamente quais políticas de conferência (se houver) permitem que os usuários agendem conferências PSTN executando o seguinte comando no Shell de gerenciamento do Lync Server:</span><span class="sxs-lookup"><span data-stu-id="edaf3-116">You can quickly verify which of your conferencing policies (if any) allow users to schedule PSTN conferences by running the following command from within the Lync Server Management Shell:</span></span>

    Get-CsConferencingPolicy | Select-Object Identity, EnableDialInConferencing

<span data-ttu-id="edaf3-117">Serão retornados dados semelhantes a estes:</span><span class="sxs-lookup"><span data-stu-id="edaf3-117">That will return data similar to this:</span></span>

    Identity                                EnableDialInConferencing
    --------                                ------------------------
    Global                                                      True
    site:Redmond                                               False
    site:Dublin                                                False
    Tag:RedmondDialInUsers                                      True
    Tag:DublinDialInUsers                                       True

<span data-ttu-id="edaf3-118">Serão retornados dados semelhantes a estes:</span><span class="sxs-lookup"><span data-stu-id="edaf3-118">That will return data similar to this:</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="edaf3-119">Filtros</span><span class="sxs-lookup"><span data-stu-id="edaf3-119">Filters</span></span>

<span data-ttu-id="edaf3-120">Os filtros oferecem uma forma de retornar um conjunto de dados mais direcionado ou exibir os dados devolvidos em formas diferentes.</span><span class="sxs-lookup"><span data-stu-id="edaf3-120">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="edaf3-121">Por exemplo, o Relatório de Resumo de Conferências PSTN permite escolher como os dados devem ser agrupados.</span><span class="sxs-lookup"><span data-stu-id="edaf3-121">For example, the PSTN Conference Summary Report enables you to choose how data should be grouped.</span></span> <span data-ttu-id="edaf3-122">Neste caso, as conferências são agrupadas por hora, dia, semana ou mês.</span><span class="sxs-lookup"><span data-stu-id="edaf3-122">In this case, conferences are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="edaf3-123">A tabela a seguir lista os filtros que podem ser usados com o Relatório de Resumo de Conferências PSTN.</span><span class="sxs-lookup"><span data-stu-id="edaf3-123">The following table lists the filters that you can use with the PSTN Conference Summary Report.</span></span>

### <a name="pstn-conference-summary-report-filters"></a><span data-ttu-id="edaf3-124">Filtros do Relatório de Resumo de Conferências PSTN</span><span class="sxs-lookup"><span data-stu-id="edaf3-124">PSTN Conference Summary Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="edaf3-125">Nome</span><span class="sxs-lookup"><span data-stu-id="edaf3-125">Name</span></span></th>
<th><span data-ttu-id="edaf3-126">Descrição</span><span class="sxs-lookup"><span data-stu-id="edaf3-126">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="edaf3-127"><strong>De</strong></span><span class="sxs-lookup"><span data-stu-id="edaf3-127"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="edaf3-p106">Data/hora de início para o intervalo de tempo. Para ver os dados por horas, insira a data e hora de início conforme segue:</span><span class="sxs-lookup"><span data-stu-id="edaf3-p106">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="edaf3-130">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="edaf3-130">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="edaf3-p107">Se você não inserir a hora de início, o relatório começará automaticamente à meia-noite do dia especificado. Para ver os dados por dia, insira somente a data:</span><span class="sxs-lookup"><span data-stu-id="edaf3-p107">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="edaf3-133">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="edaf3-133">7/7/2012</span></span></p>
<p><span data-ttu-id="edaf3-134">Para exibir por semana ou mês, insira uma data dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):</span><span class="sxs-lookup"><span data-stu-id="edaf3-134">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="edaf3-135">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="edaf3-135">7/3/2012</span></span></p>
<p><span data-ttu-id="edaf3-136">As semanas sempre vão de domingo a sábado.</span><span class="sxs-lookup"><span data-stu-id="edaf3-136">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="edaf3-137"><strong>Até</strong></span><span class="sxs-lookup"><span data-stu-id="edaf3-137"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="edaf3-p108">Data/hora final de intervalo de tempo. Para ver os dados por horas, insira a data e hora final conforme segue:</span><span class="sxs-lookup"><span data-stu-id="edaf3-p108">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="edaf3-140">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="edaf3-140">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="edaf3-p109">Se você não inserir a hora final, o relatório terminará automaticamente à meia-noite do dia especificado. Para ver os dados por dia, insira somente a data:</span><span class="sxs-lookup"><span data-stu-id="edaf3-p109">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="edaf3-143">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="edaf3-143">7/7/2012</span></span></p>
<p><span data-ttu-id="edaf3-144">Para exibir por semana ou mês, insira uma data dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):</span><span class="sxs-lookup"><span data-stu-id="edaf3-144">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="edaf3-145">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="edaf3-145">7/3/2012</span></span></p>
<p><span data-ttu-id="edaf3-146">As semanas sempre vão de domingo a sábado.</span><span class="sxs-lookup"><span data-stu-id="edaf3-146">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="edaf3-147"><strong>Intervalo</strong></span><span class="sxs-lookup"><span data-stu-id="edaf3-147"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="edaf3-p110">Intervalo de tempo. Selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="edaf3-p110">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="edaf3-150">Por hora (é possível exibir no máximo 25 horas)</span><span class="sxs-lookup"><span data-stu-id="edaf3-150">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="edaf3-151">Diariamente (é possível exibir no máximo 31 dias)</span><span class="sxs-lookup"><span data-stu-id="edaf3-151">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="edaf3-152">Semanalmente (é possível exibir no máximo 12 semanas)</span><span class="sxs-lookup"><span data-stu-id="edaf3-152">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="edaf3-153">Mensalmente (é possível exibir no máximo 12 meses)</span><span class="sxs-lookup"><span data-stu-id="edaf3-153">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="edaf3-154">Se as datas de início e término excederem o número máximo de valores permitidos para o intervalo selecionado, somente o número máximo de valores (a partir da data de início) será exibido.</span><span class="sxs-lookup"><span data-stu-id="edaf3-154">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed.</span></span> <span data-ttu-id="edaf3-155">Por exemplo, se você selecionar o intervalo diário com uma data de início de 7/7/2012 e uma data de término de 2/28/2012, os dados serão exibidos para os dias 8/7/2012 12:00 AM a 9/7/2012 12:00 AM (ou seja, um total de 31 dias da importância dos dados).</span><span class="sxs-lookup"><span data-stu-id="edaf3-155">For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="edaf3-156">Métricas</span><span class="sxs-lookup"><span data-stu-id="edaf3-156">Metrics</span></span>

<span data-ttu-id="edaf3-157">A tabela a seguir lista as informações no Relatório de Resumo de Conferências PSTN.</span><span class="sxs-lookup"><span data-stu-id="edaf3-157">The following table lists the information in the PSTN Conference Summary Report.</span></span>

### <a name="pstn-conference-summary-report-metrics"></a><span data-ttu-id="edaf3-158">Métricas do Relatório de Resumo de Conferências PSTN</span><span class="sxs-lookup"><span data-stu-id="edaf3-158">PSTN Conference Summary Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="edaf3-159">Nome</span><span class="sxs-lookup"><span data-stu-id="edaf3-159">Name</span></span></th>
<th><span data-ttu-id="edaf3-160">Você pode classificar este item?</span><span class="sxs-lookup"><span data-stu-id="edaf3-160">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="edaf3-161">Descrição</span><span class="sxs-lookup"><span data-stu-id="edaf3-161">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="edaf3-162"><strong>Por hora</strong></span><span class="sxs-lookup"><span data-stu-id="edaf3-162"><strong>Hourly</strong></span></span></p>
<p><span data-ttu-id="edaf3-163"><strong>Diário</strong></span><span class="sxs-lookup"><span data-stu-id="edaf3-163"><strong>Daily</strong></span></span></p>
<p><span data-ttu-id="edaf3-164"><strong>Semanal</strong></span><span class="sxs-lookup"><span data-stu-id="edaf3-164"><strong>Weekly</strong></span></span></p>
<p><span data-ttu-id="edaf3-165"><strong>Mensal</strong></span><span class="sxs-lookup"><span data-stu-id="edaf3-165"><strong>Monthly</strong></span></span></p></td>
<td><p><span data-ttu-id="edaf3-166">Não</span><span class="sxs-lookup"><span data-stu-id="edaf3-166">No</span></span></p></td>
<td><p><span data-ttu-id="edaf3-167">Indica o intervalo de tempo selecionado.</span><span class="sxs-lookup"><span data-stu-id="edaf3-167">Indicates the selected time interval.</span></span> <span data-ttu-id="edaf3-168">Quando aplicável, você pode clicar em um dado intervalo de tempo para exibir informações detalhadas para aquele intervalo.</span><span class="sxs-lookup"><span data-stu-id="edaf3-168">Where applicable, you can click a given time interval to view detailed information for that interval.</span></span> <span data-ttu-id="edaf3-169">Por exemplo, se você estiver usando o intervalo diário e clicar em 7/7/2012, verá um detalhamento por hora da atividade de registro do usuário para essa data.</span><span class="sxs-lookup"><span data-stu-id="edaf3-169">For example, if you are using the Daily interval and you click 7/7/2012, you see an hourly breakdown of user registration activity for that date.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="edaf3-170"><strong>Total de conferências PSTN</strong></span><span class="sxs-lookup"><span data-stu-id="edaf3-170"><strong>Total PSTN conferences</strong></span></span></p></td>
<td><p><span data-ttu-id="edaf3-171">Não</span><span class="sxs-lookup"><span data-stu-id="edaf3-171">No</span></span></p></td>
<td><p><span data-ttu-id="edaf3-172">Número total de conferências que permitiram acesso discado.</span><span class="sxs-lookup"><span data-stu-id="edaf3-172">Total number conferences that allowed dial-in access.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="edaf3-173"><strong>Total de participantes</strong></span><span class="sxs-lookup"><span data-stu-id="edaf3-173"><strong>Total participants</strong></span></span></p></td>
<td><p><span data-ttu-id="edaf3-174">Não</span><span class="sxs-lookup"><span data-stu-id="edaf3-174">No</span></span></p></td>
<td><p><span data-ttu-id="edaf3-175">Número total de pessoas que participaram de conferências que permitiram acesso discado.</span><span class="sxs-lookup"><span data-stu-id="edaf3-175">Total number of people who participated in conferences that allowed dial-in access.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="edaf3-176"><strong>Total de minutos de conferências de A/V</strong></span><span class="sxs-lookup"><span data-stu-id="edaf3-176"><strong>Total A/V conference minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="edaf3-177">Não</span><span class="sxs-lookup"><span data-stu-id="edaf3-177">No</span></span></p></td>
<td><p><span data-ttu-id="edaf3-178">Quantidade total do tempo de conferências audiovisuais.</span><span class="sxs-lookup"><span data-stu-id="edaf3-178">Total amount of audio/visual conference time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="edaf3-179"><strong>Total de minutos de participantes de conferências de A/V</strong></span><span class="sxs-lookup"><span data-stu-id="edaf3-179"><strong>Total A/V conference participant minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="edaf3-180">Não</span><span class="sxs-lookup"><span data-stu-id="edaf3-180">No</span></span></p></td>
<td><p><span data-ttu-id="edaf3-p113">Quantidade total do tempo de participantes audiovisuais. Por exemplo, se um participante passou cinco minutos em uma conferência de A/V e outro passou três minutos na mesma conferência, o tempo de participantes de conferência de A/V total seria oito minutos.</span><span class="sxs-lookup"><span data-stu-id="edaf3-p113">Total amount of audio/visual participant time. For example, if one participant spent five minutes in an A/V conference and another participant spent three minutes in the same conference, the total A/V conference participant time would be eight minutes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="edaf3-183"><strong>Total de participantes PSTN</strong></span><span class="sxs-lookup"><span data-stu-id="edaf3-183"><strong>Total PSTN participants</strong></span></span></p></td>
<td><p><span data-ttu-id="edaf3-184">Não</span><span class="sxs-lookup"><span data-stu-id="edaf3-184">No</span></span></p></td>
<td><p><span data-ttu-id="edaf3-185">Número total de usuários que discaram para conferências que permitiram acesso discado.</span><span class="sxs-lookup"><span data-stu-id="edaf3-185">Total number of users who dialed in to conferences that allowed dial-in access.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="edaf3-186"><strong>Total de minutos de participantes PSTN</strong></span><span class="sxs-lookup"><span data-stu-id="edaf3-186"><strong>Total PSTN participant minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="edaf3-187">Não</span><span class="sxs-lookup"><span data-stu-id="edaf3-187">No</span></span></p></td>
<td><p><span data-ttu-id="edaf3-p114">Quantidade total de tempo de conferência gasto por usuários discados. Por exemplo, se um participante discado passou cinco minutos em uma conferência e outro passou três minutos na mesma conferência, o tempo de participantes PSTN total seria oito minutos.</span><span class="sxs-lookup"><span data-stu-id="edaf3-p114">Total amount of conference time spent by dial-in users. For example, if one dial-in participant spent five minutes in a conference and another participant spent three minutes in the same conference, the total PSTN participant time would be eight minutes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="edaf3-190"><strong>Organizadores de conferência exclusivas</strong></span><span class="sxs-lookup"><span data-stu-id="edaf3-190"><strong>Unique conference organizers</strong></span></span></p></td>
<td><p><span data-ttu-id="edaf3-191">Não</span><span class="sxs-lookup"><span data-stu-id="edaf3-191">No</span></span></p></td>
<td><p><span data-ttu-id="edaf3-p115">Número total de usuários que organizaram no mínimo uma conferência que permitia acesso discado. Usuários que organizaram mais de uma conferência são contados como um organizador exclusivo, assim como usuários que organizaram somente uma única conferência.</span><span class="sxs-lookup"><span data-stu-id="edaf3-p115">Total number of users who organized at least one conference that allowed dial-in access. Users who organized more than one conference are counted as one unique organizer, just like users who only organized a single conference.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

