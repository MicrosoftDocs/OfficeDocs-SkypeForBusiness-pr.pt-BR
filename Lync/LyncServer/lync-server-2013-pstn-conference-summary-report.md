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
ms.openlocfilehash: aa902b9e4d53bf0ebbedf835296a371437860095
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043453"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="pstn-conference-summary-report-in-lync-server-2013"></a><span data-ttu-id="1fb9e-102">Relatório de Resumo de conferência PSTN no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1fb9e-102">PSTN Conference Summary Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1fb9e-103">_**Última modificação do tópico:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="1fb9e-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="1fb9e-104">No Microsoft Lync Server 2013, uma conferência PSTN é qualquer conferência na qual pelo menos um participante disca para a parte de áudio usando um telefone PSTN (rede telefônica pública comutada).</span><span class="sxs-lookup"><span data-stu-id="1fb9e-104">In Microsoft Lync Server 2013, a PSTN conference is any conference in which at least one participant dials in to the audio portion by a using a PSTN (public switched telephone network) phone.</span></span> <span data-ttu-id="1fb9e-105">(Um telefone PSTN é um "fixa", um telefone celular ou qualquer outro telefone que não usa voz sobre IP.) Embora sejam conhecidas como conferências PSTN nos relatórios de monitoramento, essas conferências provavelmente são mais conhecidas como conferências discadas.</span><span class="sxs-lookup"><span data-stu-id="1fb9e-105">(A PSTN phone is a "landline," a cell phone, or any other phone which does not make use of Voice over IP.) Although referred to as PSTN conferences in the Monitoring Reports, these conferences are perhaps more-commonly known as dial-in conferences.</span></span>

<span data-ttu-id="1fb9e-106">O relatório de Resumo de conferência PSTN fornece informações sobre todas as conferências PSTN mantidas em sua organização (ou seja, todas as conferências que tiveram pelo menos um usuário de discagem).</span><span class="sxs-lookup"><span data-stu-id="1fb9e-106">The PSTN Conference Summary Report provides information about all the PSTN conferences held in your organization (that is, all the conferences that had at least one dial-in user).</span></span> <span data-ttu-id="1fb9e-107">O relatório inclui informações sobre o número total de conferências PSTN, o número total de pessoas que participaram dessas conferências e, talvez, a maioria importante, o número total de usuários de discagem (a métrica total de participantes PSTN).</span><span class="sxs-lookup"><span data-stu-id="1fb9e-107">The report includes information about the total number of PSTN conferences, the total number of people who participated in those conferences, and, perhaps, most important, the total number of dial-in users (the Total PSTN participants metric).</span></span>

<div>

## <a name="accessing-the-pstn-conference-summary-report"></a><span data-ttu-id="1fb9e-108">Acessando o relatório de Resumo de conferência PSTN</span><span class="sxs-lookup"><span data-stu-id="1fb9e-108">Accessing the PSTN Conference Summary Report</span></span>

<span data-ttu-id="1fb9e-109">O relatório de Resumo de conferência PSTN só pode ser acessado na página inicial de relatórios de monitoramento.</span><span class="sxs-lookup"><span data-stu-id="1fb9e-109">The PSTN Conference Summary Report can only be accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="1fb9e-110">Este relatório não está vinculado a outros relatórios.</span><span class="sxs-lookup"><span data-stu-id="1fb9e-110">This report is not linked to any other reports.</span></span> <span data-ttu-id="1fb9e-111">Observe que você não pode recuperar informações de chamada detalhadas para uma conferência PSTN, em parte porque os pontos de extremidade individuais são responsáveis por enviar essas informações.</span><span class="sxs-lookup"><span data-stu-id="1fb9e-111">Note that you cannot retrieve detailed call information for a PSTN conference, in part because individual endpoints are responsible for submitting this information.</span></span> <span data-ttu-id="1fb9e-112">Telefones PSTN não são capazes de controlar ou enviar informações de detalhes de chamada.</span><span class="sxs-lookup"><span data-stu-id="1fb9e-112">PSTN phones are not capable of tracking or submitting call detail information.</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-pstn-conference-summary-report"></a><span data-ttu-id="1fb9e-113">Fazendo o melhor uso do relatório de Resumo de conferência PSTN</span><span class="sxs-lookup"><span data-stu-id="1fb9e-113">Making the Best Use of the PSTN Conference Summary Report</span></span>

<span data-ttu-id="1fb9e-114">Para determinar a porcentagem de todas as conferências que incluem usuários de discagem, compare o valor da métrica total de conferências PSTN com a métrica total de conferências encontrada no [relatório de Resumo de conferências no Lync Server 2013](lync-server-2013-conference-summary-report.md).</span><span class="sxs-lookup"><span data-stu-id="1fb9e-114">To determine the percentage of all your conferences that include dial-in users, compare the value of the Total PSTN conferences metric with the Total conferences metric found on the [Conference Summary Report in Lync Server 2013](lync-server-2013-conference-summary-report.md).</span></span>

<span data-ttu-id="1fb9e-115">Se você não vir tantas conferências PSTN quanto as esperadas, tenha em mente que a capacidade de organizar uma conferência que permite que os usuários de discagem dependam da política de conferência que foi atribuída a um usuário: se poucos usuários tiverem permissão para manter o PS Conferências do TN você certamente veria muito poucas conferências PSTN.</span><span class="sxs-lookup"><span data-stu-id="1fb9e-115">If you don't see as many PSTN conferences as you might have expected to see, keep in mind that the ability to organize a conference that allows dial-in users depends on the conferencing policy that has been assigned to a user: if very few of your users are allowed to hold PSTN conferences you would obviously see very few PSTN conferences.</span></span> <span data-ttu-id="1fb9e-116">Você pode verificar rapidamente quais políticas de conferência (se houver) permitem que os usuários agendem conferências PSTN executando o seguinte comando no Shell de gerenciamento do Lync Server:</span><span class="sxs-lookup"><span data-stu-id="1fb9e-116">You can quickly verify which of your conferencing policies (if any) allow users to schedule PSTN conferences by running the following command from within the Lync Server Management Shell:</span></span>

    Get-CsConferencingPolicy | Select-Object Identity, EnableDialInConferencing

<span data-ttu-id="1fb9e-117">Isso retornará dados semelhantes a estes:</span><span class="sxs-lookup"><span data-stu-id="1fb9e-117">That will return data similar to this:</span></span>

    Identity                                EnableDialInConferencing
    --------                                ------------------------
    Global                                                      True
    site:Redmond                                               False
    site:Dublin                                                False
    Tag:RedmondDialInUsers                                      True
    Tag:DublinDialInUsers                                       True

<span data-ttu-id="1fb9e-118">That will return data similar to this:</span><span class="sxs-lookup"><span data-stu-id="1fb9e-118">That will return data similar to this:</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="1fb9e-119">Filtros</span><span class="sxs-lookup"><span data-stu-id="1fb9e-119">Filters</span></span>

<span data-ttu-id="1fb9e-120">Os filtros fornecem uma maneira de retornar um conjunto de dados mais direcionadas ou para exibir os dados retornados de diferentes maneiras.</span><span class="sxs-lookup"><span data-stu-id="1fb9e-120">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="1fb9e-121">Por exemplo, o relatório de Resumo de conferência PSTN permite que você escolha como os dados devem ser agrupados.</span><span class="sxs-lookup"><span data-stu-id="1fb9e-121">For example, the PSTN Conference Summary Report enables you to choose how data should be grouped.</span></span> <span data-ttu-id="1fb9e-122">Nesse caso, as conferências são agrupadas por hora, dia, semana ou mês.</span><span class="sxs-lookup"><span data-stu-id="1fb9e-122">In this case, conferences are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="1fb9e-123">A tabela a seguir lista os filtros que podem ser usados com o relatório de Resumo de conferência PSTN.</span><span class="sxs-lookup"><span data-stu-id="1fb9e-123">The following table lists the filters that you can use with the PSTN Conference Summary Report.</span></span>

### <a name="pstn-conference-summary-report-filters"></a><span data-ttu-id="1fb9e-124">Filtros do relatório de Resumo de conferência PSTN</span><span class="sxs-lookup"><span data-stu-id="1fb9e-124">PSTN Conference Summary Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1fb9e-125">Nome</span><span class="sxs-lookup"><span data-stu-id="1fb9e-125">Name</span></span></th>
<th><span data-ttu-id="1fb9e-126">Descrição</span><span class="sxs-lookup"><span data-stu-id="1fb9e-126">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1fb9e-127"><strong>De</strong></span><span class="sxs-lookup"><span data-stu-id="1fb9e-127"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="1fb9e-p106">Data/hora inicial para o intervalo de tempo. Para exibir os dados por hora, insira a data e hora inicial como a seguir:</span><span class="sxs-lookup"><span data-stu-id="1fb9e-p106">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="1fb9e-130">7/7/2012 13:00 horas</span><span class="sxs-lookup"><span data-stu-id="1fb9e-130">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="1fb9e-p107">Se você não inserir uma hora inicial, o relatório começa automaticamente as 12:00 AM no dia especificado. Para exibir os dados por dia, insira apenas a data:</span><span class="sxs-lookup"><span data-stu-id="1fb9e-p107">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="1fb9e-133">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="1fb9e-133">7/7/2012</span></span></p>
<p><span data-ttu-id="1fb9e-134">Para exibir por semana ou mês, insira uma data que está dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):</span><span class="sxs-lookup"><span data-stu-id="1fb9e-134">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="1fb9e-135">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="1fb9e-135">7/3/2012</span></span></p>
<p><span data-ttu-id="1fb9e-136">As semanas sempre são de Domingo a Sábado.</span><span class="sxs-lookup"><span data-stu-id="1fb9e-136">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1fb9e-137"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="1fb9e-137"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="1fb9e-p108">Data/hora final para o intervalo de tempo. Para exibir os dados por hora, insira a data e hora final como a seguir:</span><span class="sxs-lookup"><span data-stu-id="1fb9e-p108">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="1fb9e-140">7/7/2012 13:00 horas</span><span class="sxs-lookup"><span data-stu-id="1fb9e-140">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="1fb9e-p109">Se você não inserir uma hora final, o relatório termina automaticamente as 12:00 AM no dia especificado. Para exibir os dados por dia, insira apenas a data:</span><span class="sxs-lookup"><span data-stu-id="1fb9e-p109">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="1fb9e-143">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="1fb9e-143">7/7/2012</span></span></p>
<p><span data-ttu-id="1fb9e-144">Para exibir por semana ou mês, insira uma data que está dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):</span><span class="sxs-lookup"><span data-stu-id="1fb9e-144">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="1fb9e-145">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="1fb9e-145">7/3/2012</span></span></p>
<p><span data-ttu-id="1fb9e-146">As semanas são sempre de domingo a sábado.</span><span class="sxs-lookup"><span data-stu-id="1fb9e-146">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1fb9e-147"><strong>Intervalo</strong></span><span class="sxs-lookup"><span data-stu-id="1fb9e-147"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="1fb9e-p110">Intervalo de tempo. Selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="1fb9e-p110">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="1fb9e-150">Por hora (é possível exibir no máximo 25 horas)</span><span class="sxs-lookup"><span data-stu-id="1fb9e-150">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="1fb9e-151">Diariamente (é possível exibir no máximo 31 dias)</span><span class="sxs-lookup"><span data-stu-id="1fb9e-151">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="1fb9e-152">Semanalmente (é possível exibir no máximo 12 semanas)</span><span class="sxs-lookup"><span data-stu-id="1fb9e-152">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="1fb9e-153">Mensalmente (é possível exibir no máximo 12 meses)</span><span class="sxs-lookup"><span data-stu-id="1fb9e-153">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="1fb9e-p111">Se as datas de início e término excederem o número máximo de valores permitidos para o intervalo selecionado, somente o número máximo de valores (a partir da data de início) será exibido. Por exemplo, se você selecionar o intervalo Diariamente com a data de início 7/7/12 e uma data de término de 28/2/12, os dados serão exibidos para os dias 7/8/2 00:00 horas até 7/9/12 00:00 horas (ou seja, um total de 31 dias de dados).</span><span class="sxs-lookup"><span data-stu-id="1fb9e-p111">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed. For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="1fb9e-156">Métricas</span><span class="sxs-lookup"><span data-stu-id="1fb9e-156">Metrics</span></span>

<span data-ttu-id="1fb9e-157">A tabela a seguir lista as informações no relatório de Resumo de conferência PSTN.</span><span class="sxs-lookup"><span data-stu-id="1fb9e-157">The following table lists the information in the PSTN Conference Summary Report.</span></span>

### <a name="pstn-conference-summary-report-metrics"></a><span data-ttu-id="1fb9e-158">Métricas do relatório de Resumo de conferência PSTN</span><span class="sxs-lookup"><span data-stu-id="1fb9e-158">PSTN Conference Summary Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1fb9e-159">Nome</span><span class="sxs-lookup"><span data-stu-id="1fb9e-159">Name</span></span></th>
<th><span data-ttu-id="1fb9e-160">É possível classificar este item?</span><span class="sxs-lookup"><span data-stu-id="1fb9e-160">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="1fb9e-161">Descrição</span><span class="sxs-lookup"><span data-stu-id="1fb9e-161">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1fb9e-162"><strong>A cada hora</strong></span><span class="sxs-lookup"><span data-stu-id="1fb9e-162"><strong>Hourly</strong></span></span></p>
<p><span data-ttu-id="1fb9e-163"><strong>Diariamente</strong></span><span class="sxs-lookup"><span data-stu-id="1fb9e-163"><strong>Daily</strong></span></span></p>
<p><span data-ttu-id="1fb9e-164"><strong>Semanalmente</strong></span><span class="sxs-lookup"><span data-stu-id="1fb9e-164"><strong>Weekly</strong></span></span></p>
<p><span data-ttu-id="1fb9e-165"><strong>Mensal</strong></span><span class="sxs-lookup"><span data-stu-id="1fb9e-165"><strong>Monthly</strong></span></span></p></td>
<td><p><span data-ttu-id="1fb9e-166">Não</span><span class="sxs-lookup"><span data-stu-id="1fb9e-166">No</span></span></p></td>
<td><p><span data-ttu-id="1fb9e-p112">Indica o intervalo de tempo selecionado. Quando aplicável, é possível clicar em um determinado intervalo de tempo para exibir informações detalhadas desse intervalo. Por exemplo, se estiver usando o intervalo Diário e clicar em 7/7/12, você verá uma divisão por hora da atividade de registro do usuário para essa data.</span><span class="sxs-lookup"><span data-stu-id="1fb9e-p112">Indicates the selected time interval. Where applicable, you can click a given time interval to view detailed information for that interval. For example, if you are using the Daily interval and you click 7/7/2012, you see an hourly breakdown of user registration activity for that date.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1fb9e-170"><strong>Total de conferências PSTN</strong></span><span class="sxs-lookup"><span data-stu-id="1fb9e-170"><strong>Total PSTN conferences</strong></span></span></p></td>
<td><p><span data-ttu-id="1fb9e-171">Não</span><span class="sxs-lookup"><span data-stu-id="1fb9e-171">No</span></span></p></td>
<td><p><span data-ttu-id="1fb9e-172">Número total de conferências que permitiram acesso discado.</span><span class="sxs-lookup"><span data-stu-id="1fb9e-172">Total number conferences that allowed dial-in access.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1fb9e-173"><strong>Total de participantes</strong></span><span class="sxs-lookup"><span data-stu-id="1fb9e-173"><strong>Total participants</strong></span></span></p></td>
<td><p><span data-ttu-id="1fb9e-174">Não</span><span class="sxs-lookup"><span data-stu-id="1fb9e-174">No</span></span></p></td>
<td><p><span data-ttu-id="1fb9e-175">Número total de pessoas que participaram de conferências que permitiram acesso discado.</span><span class="sxs-lookup"><span data-stu-id="1fb9e-175">Total number of people who participated in conferences that allowed dial-in access.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1fb9e-176"><strong>Total de minutos da conferência A/V</strong></span><span class="sxs-lookup"><span data-stu-id="1fb9e-176"><strong>Total A/V conference minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="1fb9e-177">Não</span><span class="sxs-lookup"><span data-stu-id="1fb9e-177">No</span></span></p></td>
<td><p><span data-ttu-id="1fb9e-178">Quantidade total de tempo de áudio/conferência Visual.</span><span class="sxs-lookup"><span data-stu-id="1fb9e-178">Total amount of audio/visual conference time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1fb9e-179"><strong>Total de minutos do participante da conferência A/V</strong></span><span class="sxs-lookup"><span data-stu-id="1fb9e-179"><strong>Total A/V conference participant minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="1fb9e-180">Não</span><span class="sxs-lookup"><span data-stu-id="1fb9e-180">No</span></span></p></td>
<td><p><span data-ttu-id="1fb9e-181">Quantidade total de tempo de áudio/do participante Visual.</span><span class="sxs-lookup"><span data-stu-id="1fb9e-181">Total amount of audio/visual participant time.</span></span> <span data-ttu-id="1fb9e-182">Por exemplo, se um participante gastou cinco minutos em uma conferência de A/V e outro participante gastou três minutos na mesma conferência, o tempo de participante da Conferência A/V deve ser de oito minutos.</span><span class="sxs-lookup"><span data-stu-id="1fb9e-182">For example, if one participant spent five minutes in an A/V conference and another participant spent three minutes in the same conference, the total A/V conference participant time would be eight minutes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1fb9e-183"><strong>Total de participantes PSTN</strong></span><span class="sxs-lookup"><span data-stu-id="1fb9e-183"><strong>Total PSTN participants</strong></span></span></p></td>
<td><p><span data-ttu-id="1fb9e-184">Não</span><span class="sxs-lookup"><span data-stu-id="1fb9e-184">No</span></span></p></td>
<td><p><span data-ttu-id="1fb9e-185">Número total de usuários que discaram para conferências que permitiram acesso discado.</span><span class="sxs-lookup"><span data-stu-id="1fb9e-185">Total number of users who dialed in to conferences that allowed dial-in access.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1fb9e-186"><strong>Total de minutos de participantes PSTN</strong></span><span class="sxs-lookup"><span data-stu-id="1fb9e-186"><strong>Total PSTN participant minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="1fb9e-187">Não</span><span class="sxs-lookup"><span data-stu-id="1fb9e-187">No</span></span></p></td>
<td><p><span data-ttu-id="1fb9e-188">Quantidade total de tempo de conferência gasto por usuários discados.</span><span class="sxs-lookup"><span data-stu-id="1fb9e-188">Total amount of conference time spent by dial-in users.</span></span> <span data-ttu-id="1fb9e-189">Por exemplo, se um participante de discagem gastou cinco minutos em uma conferência e outro participante gastou três minutos na mesma conferência, o tempo de participante PSTN total será de oito minutos.</span><span class="sxs-lookup"><span data-stu-id="1fb9e-189">For example, if one dial-in participant spent five minutes in a conference and another participant spent three minutes in the same conference, the total PSTN participant time would be eight minutes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1fb9e-190"><strong>Organizadores de conferência exclusivos</strong></span><span class="sxs-lookup"><span data-stu-id="1fb9e-190"><strong>Unique conference organizers</strong></span></span></p></td>
<td><p><span data-ttu-id="1fb9e-191">Não</span><span class="sxs-lookup"><span data-stu-id="1fb9e-191">No</span></span></p></td>
<td><p><span data-ttu-id="1fb9e-192">Número total de usuários que organizaram pelo menos uma conferência que permitia acesso de discagem.</span><span class="sxs-lookup"><span data-stu-id="1fb9e-192">Total number of users who organized at least one conference that allowed dial-in access.</span></span> <span data-ttu-id="1fb9e-193">Os usuários que organizaram mais de uma conferência são contados como um organizador exclusivo, assim como os usuários que só organizaram uma única conferência.</span><span class="sxs-lookup"><span data-stu-id="1fb9e-193">Users who organized more than one conference are counted as one unique organizer, just like users who only organized a single conference.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

