---
title: 'Lync Server 2013: relatório de lista de chamadas de grupo de resposta'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Response Group Call List Report
ms:assetid: a2d3e08b-511b-4507-abba-8ff71aa27c8e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615443(v=OCS.15)
ms:contentKeyID: 48184954
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0b9ec44aa0b4c6063dd6c0a3cf1ae9e5b0c10356
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144818"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="response-group-call-list-report-in-lync-server-2013"></a><span data-ttu-id="fba39-102">Relatório de lista de chamadas de grupo de resposta no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fba39-102">Response Group Call List Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fba39-103">_**Última modificação do tópico:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="fba39-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="fba39-104">O aplicativo grupo de resposta oferece uma maneira de o Microsoft Lync Server 2013 responder e rotear chamadas telefônicas com base no número que foi discado e, opcionalmente, nas respostas do chamador para uma série de perguntas.</span><span class="sxs-lookup"><span data-stu-id="fba39-104">The Response Group application provides a way for Microsoft Lync Server 2013 to answer and route phone calls based on the number that was dialed and, optionally, on the caller's responses to a series of questions.</span></span> <span data-ttu-id="fba39-105">Normalmente, as chamadas do Grupo de Resposta não são roteadas a uma única pessoa, mas, em vez disso, são roteadas a uma equipe de pessoas chamada de grupo de agentes.</span><span class="sxs-lookup"><span data-stu-id="fba39-105">Typically, Response Group calls are not routed to an individual person but, instead, are routed to a team of people referred to as an agent group.</span></span> <span data-ttu-id="fba39-106">Por exemplo, se alguém ligar para o número de telefone de seu suporte técnico, o Lync Server 2013 pode encaminhar automaticamente a chamada para o primeiro agente de suporte técnico disponível.</span><span class="sxs-lookup"><span data-stu-id="fba39-106">For example, if someone calls the phone number for your help desk, Lync Server 2013 can automatically route that call to the first available help desk agent.</span></span> <span data-ttu-id="fba39-107">Como alternativa, o Lync Server pode fazer uma série de perguntas ("Pressione 1 se estiver com problemas de hardware.</span><span class="sxs-lookup"><span data-stu-id="fba39-107">Alternatively, Lync Server could ask a series of questions ("Press 1 if you are having hardware problems.</span></span> <span data-ttu-id="fba39-108">Pressione 2 se estiver com problemas de software.</span><span class="sxs-lookup"><span data-stu-id="fba39-108">Press 2 if you are having software problems.</span></span> <span data-ttu-id="fba39-109">Pressione 3 se você estiver tendo problemas de rede. ") e, em seguida, encaminhe a chamada para o agente de suporte técnico mais apropriado, com base na resposta a essas perguntas.</span><span class="sxs-lookup"><span data-stu-id="fba39-109">Press 3 if you are having network problems.") and then route the call to the most appropriate help desk agent based on the answer to those questions.</span></span>

<span data-ttu-id="fba39-p102">O Relatório de lista de chamadas do grupo de resposta representa uma coleção de chamadas feitas por um período específico de tempo e para um tipo específico de chamada. O Relatório de uso de grupo de resposta (que deve ser aberto primeiro, antes de abrir o Relatório de lista de chamadas do grupo de resposta) reconhece os seguintes tipos de chamadas:</span><span class="sxs-lookup"><span data-stu-id="fba39-p102">The Response Group Call List Report represents a collection of calls made for a specified period of time and for a specified type of call. The Response Group Usage Report (which must be opened first before you can open the Response Group Call List Report) recognizes the following call types:</span></span>

  - <span data-ttu-id="fba39-p103">**Chamadas recebidas**. Número total de chamadas recebidas por todas as instâncias do aplicativo Grupo de Resposta.</span><span class="sxs-lookup"><span data-stu-id="fba39-p103">**Received calls**. Total number of calls received by all instances of the Response Group application.</span></span>

  - <span data-ttu-id="fba39-114">**Chamadas bem-sucedidas**.</span><span class="sxs-lookup"><span data-stu-id="fba39-114">**Successful calls**.</span></span> <span data-ttu-id="fba39-115">Número total de chamadas que foram escolhidas pelo aplicativo grupo de resposta.</span><span class="sxs-lookup"><span data-stu-id="fba39-115">Total number of calls that were picked up by the Response Group application.</span></span>

  - <span data-ttu-id="fba39-p105">**Chamadas oferecidas**. Número total de chamadas que foram transferidas ao um agente do Grupo de Resposta.</span><span class="sxs-lookup"><span data-stu-id="fba39-p105">**Offered calls**. Total number of calls that were transferred to a Response Group agent.</span></span>

  - <span data-ttu-id="fba39-p106">**Chamadas atendidas**. Número total de chamadas que foram verdadeiramente atendidas por um agente do Grupo de Resposta.</span><span class="sxs-lookup"><span data-stu-id="fba39-p106">**Answered calls**. Total number of calls that were actually answered by a Response Group agent.</span></span>

  - <span data-ttu-id="fba39-120">Porcentagem de chamadas abandonadas.</span><span class="sxs-lookup"><span data-stu-id="fba39-120">Percentage of abandoned calls.</span></span> <span data-ttu-id="fba39-121">Porcentagem de chamadas que foram recebidas pelo aplicativo Grupo de Resposta, mas que nunca foram atendidas por um agente.</span><span class="sxs-lookup"><span data-stu-id="fba39-121">Percentage of calls that were received by the Response Group application but were never answered by an agent.</span></span> <span data-ttu-id="fba39-122">Este valor é calculado subtraindo as chamadas atendidas pelas chamadas recebidas e, entãi, dividindo esse valor pelo número de chamadas recebidas.</span><span class="sxs-lookup"><span data-stu-id="fba39-122">This value is calculated by subtracting the Answered calls from the Received calls, and then dividing that value by the number of Received calls.</span></span> <span data-ttu-id="fba39-123">Por exemplo, se 10 chamadas foram recebidas e 7 foram atendidas, você deve subtrair 7 de 10, restando 3 chamadas não atendidas.</span><span class="sxs-lookup"><span data-stu-id="fba39-123">For example, if you received 10 calls and 7 were answered, you would subtract 7 from 10, leaving 3 unanswered calls.</span></span> <span data-ttu-id="fba39-124">Esse valor seria dividido por 10, proporcionando uma porcentagem de chamadas abandonadas de 30%.</span><span class="sxs-lookup"><span data-stu-id="fba39-124">That value would then be divided by 10, giving you an abandoned call percentage of 30%.</span></span>

  - <span data-ttu-id="fba39-p108">**Chamadas transferidas**. Número total de chamadas do Grupo de Resposta transferidas devido a um tempo limite ou estouro de fila.</span><span class="sxs-lookup"><span data-stu-id="fba39-p108">**Transferred calls**. Total number of Response Group calls that were transferred because of a queue timeout or queue overflow.</span></span>

<div>

## <a name="accessing-the-response-group-call-list-report"></a><span data-ttu-id="fba39-127">Como acessar o Relatório de Lista de Chamadas de Grupo de Resposta</span><span class="sxs-lookup"><span data-stu-id="fba39-127">Accessing the Response Group Call List Report</span></span>

<span data-ttu-id="fba39-128">O relatório de lista de chamadas de grupo de resposta pode ser acessado apenas clicando em uma das seguintes métricas encontradas no [relatório de uso do grupo de resposta no Lync Server 2013](lync-server-2013-response-group-usage-report.md):</span><span class="sxs-lookup"><span data-stu-id="fba39-128">The Response Group Call List Report can only be accessed by clicking one of the following metrics found on the [Response Group Usage Report in Lync Server 2013](lync-server-2013-response-group-usage-report.md):</span></span>

  - <span data-ttu-id="fba39-129">Chamadas recebidas</span><span class="sxs-lookup"><span data-stu-id="fba39-129">Received calls</span></span>

  - <span data-ttu-id="fba39-130">Chamadas bem-sucedidas</span><span class="sxs-lookup"><span data-stu-id="fba39-130">Successful calls</span></span>

  - <span data-ttu-id="fba39-131">Chamadas oferecidas</span><span class="sxs-lookup"><span data-stu-id="fba39-131">Offered calls</span></span>

  - <span data-ttu-id="fba39-132">Chamadas atendidas</span><span class="sxs-lookup"><span data-stu-id="fba39-132">Answered calls</span></span>

  - <span data-ttu-id="fba39-133">Chamadas transferidas</span><span class="sxs-lookup"><span data-stu-id="fba39-133">Transferred calls</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-response-group-call-list-report"></a><span data-ttu-id="fba39-134">Como usar melhor o Relatório de Lista de Chamadas de Grupo de Resposta</span><span class="sxs-lookup"><span data-stu-id="fba39-134">Making the Best Use of the Response Group Call List Report</span></span>

<span data-ttu-id="fba39-p109">O Relatório de Lista de Chamadas de Grupo de Resposta permite que você limite os dados exibidos para chamadas que envolvem um fluxo de trabalho específico de Grupo de Resposta. Para fazer isso, você precisa inserir o URI do fluxo de trabalho (o endereço SIP do fluxo de trabalho) na caixa do URI do fluxo de trabalho. Antes que você possa fazer isso, no entanto, é necessário realmente poder ver a caixa do URI do fluxo de trabalho. Para exibir as opções de filtragem do Relatório de Lista de Chamadas de Grupo de Resposta, clique no botão Exibir/Ocultar Parâmetros, na parte superior esquerda da janela do relatório.</span><span class="sxs-lookup"><span data-stu-id="fba39-p109">The Response Group Call List Report allows you to limit the displayed data to calls involving a particular Response Group workflow. To do that, you need to enter the workflow URI (the workflow's SIP address) in the Workflow URI box. Before you can do that, however, you must actually be able to see the Workflow URI box. To display the filtering options for the Response Group Call List Report, click the Show/Hide Parameters button in the upper left-hand portion of the report window.</span></span>

<span data-ttu-id="fba39-139">Observe que a lista de chamadas do grupo de resposta não exibe informações sobre o código de Resposta nem do ID do Diagnóstico se você manter o mouse sobre uma dessas métricas.</span><span class="sxs-lookup"><span data-stu-id="fba39-139">Note that the Response Group Call List does not display information about either the Response code or the Diagnostic ID if you hold the mouse over either of those metrics.</span></span> <span data-ttu-id="fba39-140">Se precisar de mais informações, você poderá anotar o código de resposta e/ou a ID de diagnóstico e, em seguida, procurar esses valores no [relatório de falhas principais no Lync Server 2013](lync-server-2013-top-failures-report.md).</span><span class="sxs-lookup"><span data-stu-id="fba39-140">If you need more information, you might note the Response code and/or Diagnostic ID, and then search for those values in the [Top Failures Report in Lync Server 2013](lync-server-2013-top-failures-report.md).</span></span>

<span data-ttu-id="fba39-141">uma pergunta como esta: "Qual é o fluxo de trabalho individual que recebeu a maioria das chamadas?", é possível fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="fba39-141">a question like this one: "Which individual workflow received the most calls?", you can do the following:</span></span>

1.  <span data-ttu-id="fba39-p111">No Relatório de uso do grupo de resposta, defina o período desejado de tempo e depois clique na métrica Chamadas Recebidas. Isso abrirá o Relatório de lista de chamadas do grupo de resposta.</span><span class="sxs-lookup"><span data-stu-id="fba39-p111">On the Response Group Usage Report, set the desired time period and then click the Received Calls metric. That will open the Response Group Call List Report.</span></span>

2.  <span data-ttu-id="fba39-p112">Exporte os dados exibidos no Relatório de lista de chamadas do grupo de resposta. Por exemplo, você poderá exportar os dados em formato Microsoft Excel, e depois usar o Excel para converter esses dados a um arquivo de valores separados por vírgula.</span><span class="sxs-lookup"><span data-stu-id="fba39-p112">Export the data shown on the Response Group Call List Report. For example, you might export the data in Microsoft Excel format, and then use Excel to convert that data to a comma-separated values file.</span></span>

3.  <span data-ttu-id="fba39-146">Execute suas análises usando o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fba39-146">Run your analyses using Windows PowerShell.</span></span>

<span data-ttu-id="fba39-147">Por exemplo, se você salvou os dados em um arquivo denominado C\\: relatório de\\lista\_\_\_de chamadas\_de grupo de resposta de dados. csv, você pode usar o seguinte comando para retornar o número total de chamadas recebidas para cada fluxo de trabalho listado no relatório:</span><span class="sxs-lookup"><span data-stu-id="fba39-147">For example, if you have saved the data to a file named C:\\Data\\Response\_Group\_Call\_List\_Report.csv, you can then use the following command to return the total number of received calls for each workflow listed in the report:</span></span>

    $calls = Import-Csv -Path "C:\ Data\Response_Group_Call_List_Report.csv"
    $calls | Group-Object Workflow | Select-Object Count, Name | Sort-Object Count -Descending

<span data-ttu-id="fba39-148">As informações serão similares a essas:</span><span class="sxs-lookup"><span data-stu-id="fba39-148">That will information similar to this:</span></span>

    Count    Name
    -----    ----
      160    Redmond Help Desk
       47    Dublin Help Desk
       31    North America Customer Support
       16    EMEA Customer Support
       14    Employment Opportunities

</div>

<div>

## <a name="filters"></a><span data-ttu-id="fba39-149">Filtros</span><span class="sxs-lookup"><span data-stu-id="fba39-149">Filters</span></span>

<span data-ttu-id="fba39-p113">Filtros fornecem uma forma de retornar um conjunto de dados mais focado ou exibir os dados retornados de diferentes formas. A tabela a seguir lista os filtros que podem ser usados com o Relatório de Lista de Chamadas de Grupo de Resposta.</span><span class="sxs-lookup"><span data-stu-id="fba39-p113">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. The following table lists the filters that you can use with the Response Group Call List Report.</span></span>

### <a name="response-group-call-list-report-filters"></a><span data-ttu-id="fba39-152">Filtros do Relatório de Lista de Chamadas de Grupo de Respostas</span><span class="sxs-lookup"><span data-stu-id="fba39-152">Response Group Call List Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fba39-153">Nome</span><span class="sxs-lookup"><span data-stu-id="fba39-153">Name</span></span></th>
<th><span data-ttu-id="fba39-154">Descrição</span><span class="sxs-lookup"><span data-stu-id="fba39-154">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fba39-155"><strong>De</strong></span><span class="sxs-lookup"><span data-stu-id="fba39-155"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="fba39-p114">Data/hora inicial para o intervalo de tempo. Para exibir os dados por hora, insira a data e hora inicial como a seguir:</span><span class="sxs-lookup"><span data-stu-id="fba39-p114">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="fba39-158">7/7/2012 13:00 horas</span><span class="sxs-lookup"><span data-stu-id="fba39-158">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="fba39-p115">Se você não inserir uma hora inicial, o relatório começa automaticamente as 12:00 AM no dia especificado. Para exibir os dados por dia, insira apenas a data:</span><span class="sxs-lookup"><span data-stu-id="fba39-p115">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="fba39-161">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="fba39-161">7/7/2012</span></span></p>
<p><span data-ttu-id="fba39-162">Para exibir por semana ou mês, insira uma data que está dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):</span><span class="sxs-lookup"><span data-stu-id="fba39-162">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="fba39-163">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="fba39-163">7/3/2012</span></span></p>
<p><span data-ttu-id="fba39-164">As semanas são sempre de domingo a sábado.</span><span class="sxs-lookup"><span data-stu-id="fba39-164">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fba39-165"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="fba39-165"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="fba39-p116">Data/hora final para o intervalo de tempo. Para exibir os dados por hora, insira a data e hora final como a seguir:</span><span class="sxs-lookup"><span data-stu-id="fba39-p116">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="fba39-168">7/7/2012 13:00 horas</span><span class="sxs-lookup"><span data-stu-id="fba39-168">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="fba39-p117">Se você não inserir uma hora final, o relatório termina automaticamente as 12:00 AM no dia especificado. Para exibir os dados por dia, insira apenas a data:</span><span class="sxs-lookup"><span data-stu-id="fba39-p117">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="fba39-171">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="fba39-171">7/7/2012</span></span></p>
<p><span data-ttu-id="fba39-172">Para exibir por semana ou mês, insira uma data que está dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):</span><span class="sxs-lookup"><span data-stu-id="fba39-172">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="fba39-173">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="fba39-173">7/3/2012</span></span></p>
<p><span data-ttu-id="fba39-174">As semanas sempre vão de domingo a sábado.</span><span class="sxs-lookup"><span data-stu-id="fba39-174">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fba39-175"><strong>URI do Fluxo de trabalho</strong></span><span class="sxs-lookup"><span data-stu-id="fba39-175"><strong>Workflow URI</strong></span></span></p></td>
<td><p><span data-ttu-id="fba39-p118">Permite que você limite os dados retornados para o fluxo de trabalho do Grupo de Resposta especificado. Para usar esse filtro, digite o endereço SIP do Fluxo de Trabalho. Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="fba39-p118">Enables you to limit the returned data to the specified Response Group workflow. To use this filter, enter the Workflow SIP address. For example:</span></span></p>
<p><span data-ttu-id="fba39-179">sip:helpdesk@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="fba39-179">sip:helpdesk@litwareinc.com</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fba39-180"><strong>Chamadas</strong></span><span class="sxs-lookup"><span data-stu-id="fba39-180"><strong>Calls</strong></span></span></p></td>
<td><p><span data-ttu-id="fba39-181">Você pode selecionar um dos seguintes tipos de chamadas:</span><span class="sxs-lookup"><span data-stu-id="fba39-181">You can select one of the following call types:</span></span></p>
<ul>
<li><p><span data-ttu-id="fba39-182">Chamadas Recebidas</span><span class="sxs-lookup"><span data-stu-id="fba39-182">Received Calls</span></span></p></li>
<li><p><span data-ttu-id="fba39-183">Chamadas com Êxito</span><span class="sxs-lookup"><span data-stu-id="fba39-183">Successful Calls</span></span></p></li>
<li><p><span data-ttu-id="fba39-184">Chamadas Oferecidas</span><span class="sxs-lookup"><span data-stu-id="fba39-184">Offered Calls</span></span></p></li>
<li><p><span data-ttu-id="fba39-185">Chamadas Atendidas</span><span class="sxs-lookup"><span data-stu-id="fba39-185">Answered Calls</span></span></p></li>
<li><p><span data-ttu-id="fba39-186">Chamadas Transferidas</span><span class="sxs-lookup"><span data-stu-id="fba39-186">Transferred Calls</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="fba39-187">Métricas</span><span class="sxs-lookup"><span data-stu-id="fba39-187">Metrics</span></span>

<span data-ttu-id="fba39-188">A tabela a seguir lista as informações fornecidas no Relatório de Lisa de Chamadas de Grupo de Resposta para cada chamada recebida pelo aplicativo do Grupo de Resposta.</span><span class="sxs-lookup"><span data-stu-id="fba39-188">The following table lists the information provided in the Response Group Call List Report for each call received by the Response Group application.</span></span>

### <a name="response-group-call-list-report-metrics"></a><span data-ttu-id="fba39-189">Métricas do Relatório de Lista de Chamadas de Grupo de Resposta</span><span class="sxs-lookup"><span data-stu-id="fba39-189">Response Group Call List Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fba39-190">Nome</span><span class="sxs-lookup"><span data-stu-id="fba39-190">Name</span></span></th>
<th><span data-ttu-id="fba39-191">É possível classificar este item?</span><span class="sxs-lookup"><span data-stu-id="fba39-191">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="fba39-192">Descrição</span><span class="sxs-lookup"><span data-stu-id="fba39-192">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fba39-193"><strong>Caller</strong></span><span class="sxs-lookup"><span data-stu-id="fba39-193"><strong>Caller</strong></span></span></p></td>
<td><p><span data-ttu-id="fba39-194">Não</span><span class="sxs-lookup"><span data-stu-id="fba39-194">No</span></span></p></td>
<td><p><span data-ttu-id="fba39-195">Endereço SIP do chamador.</span><span class="sxs-lookup"><span data-stu-id="fba39-195">SIP address of the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fba39-196"><strong>Fluxo de trabalho</strong></span><span class="sxs-lookup"><span data-stu-id="fba39-196"><strong>Workflow</strong></span></span></p></td>
<td><p><span data-ttu-id="fba39-197">Não</span><span class="sxs-lookup"><span data-stu-id="fba39-197">No</span></span></p></td>
<td><p><span data-ttu-id="fba39-198">Endereço SIP do fluxo de trabalho do Grupo de Resposta.</span><span class="sxs-lookup"><span data-stu-id="fba39-198">SIP address of the Response Group workflow.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fba39-199"><strong>Horário de início</strong></span><span class="sxs-lookup"><span data-stu-id="fba39-199"><strong>Start time</strong></span></span></p></td>
<td><p><span data-ttu-id="fba39-200">Não</span><span class="sxs-lookup"><span data-stu-id="fba39-200">No</span></span></p></td>
<td><p><span data-ttu-id="fba39-201">Data e horário em que a chamada teve início.</span><span class="sxs-lookup"><span data-stu-id="fba39-201">Date and time that the call started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fba39-202"><strong>Horário de término</strong></span><span class="sxs-lookup"><span data-stu-id="fba39-202"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="fba39-203">Não</span><span class="sxs-lookup"><span data-stu-id="fba39-203">No</span></span></p></td>
<td><p><span data-ttu-id="fba39-204">Data e horário em que a chamada terminou.</span><span class="sxs-lookup"><span data-stu-id="fba39-204">Date and time that the call ended.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fba39-205"><strong>Código da resposta</strong></span><span class="sxs-lookup"><span data-stu-id="fba39-205"><strong>Response code</strong></span></span></p></td>
<td><p><span data-ttu-id="fba39-206">Não</span><span class="sxs-lookup"><span data-stu-id="fba39-206">No</span></span></p></td>
<td><p><span data-ttu-id="fba39-207">Código da resposta SIP enviado quando a sessão falhou.</span><span class="sxs-lookup"><span data-stu-id="fba39-207">SIP response code sent when the session failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fba39-208"><strong>ID do Diagnóstico</strong></span><span class="sxs-lookup"><span data-stu-id="fba39-208"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="fba39-209">Não</span><span class="sxs-lookup"><span data-stu-id="fba39-209">No</span></span></p></td>
<td><p><span data-ttu-id="fba39-210">Identificador único (na forma de um cabeçalho ms-diagnostics) anexado a uma mensagem SIP que geralmente fornece informações úteis para solucionar erros.</span><span class="sxs-lookup"><span data-stu-id="fba39-210">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

