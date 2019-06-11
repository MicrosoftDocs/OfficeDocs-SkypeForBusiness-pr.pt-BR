---
title: 'Lync Server 2013: relatório de uso do grupo de resposta'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Response Group Usage Report
ms:assetid: 3248b320-a552-400a-8485-6891af4eb0f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558632(v=OCS.15)
ms:contentKeyID: 48183811
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9334fea5bded88b4f2453f46a0848819743766d9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823312"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="response-group-usage-report-in-lync-server-2013"></a><span data-ttu-id="1f792-102">Relatório de uso do grupo de resposta no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1f792-102">Response Group Usage Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1f792-103">_**Tópico da última modificação:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="1f792-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="1f792-104">O aplicativo grupo de resposta fornece uma maneira para que o Microsoft Lync Server 2013 atenda e encaminhe chamadas telefônicas com base no número que foi discado e, opcionalmente, nas respostas do chamador para uma série de perguntas.</span><span class="sxs-lookup"><span data-stu-id="1f792-104">The Response Group application provides a way for Microsoft Lync Server 2013 to answer and route phone calls based on the number that was dialed and, optionally, on the caller's responses to a series of questions.</span></span> <span data-ttu-id="1f792-105">Geralmente, as chamadas do Grupo de Resposta não são encaminhadas a uma pessoa específica, mas sim para uma equipe de pessoas referida como grupo de agentes.</span><span class="sxs-lookup"><span data-stu-id="1f792-105">Typically, Response Group calls are not routed to an individual person but, instead, are routed to a team of people referred to as an agent group.</span></span> <span data-ttu-id="1f792-106">Por exemplo, se alguém ligar para o número de telefone de seu suporte técnico, o Lync Server 2013 poderá direcionar automaticamente essa chamada para o primeiro agente de suporte técnico disponível.</span><span class="sxs-lookup"><span data-stu-id="1f792-106">For example, if someone calls the phone number for your help desk, Lync Server 2013 can automatically route that call to the first available help desk agent.</span></span> <span data-ttu-id="1f792-107">Ou, se preferir, o Lync Server pode fazer uma série de perguntas ("Pressione 1 se estiver com problemas de hardware).</span><span class="sxs-lookup"><span data-stu-id="1f792-107">Alternatively, Lync Server could ask a series of questions ("Press 1 if you are having hardware problems.</span></span> <span data-ttu-id="1f792-108">Pressione 2 se tiver problemas de software.</span><span class="sxs-lookup"><span data-stu-id="1f792-108">Press 2 if you are having software problems.</span></span> <span data-ttu-id="1f792-109">Pressione 3 se você estiver tendo problemas de rede. ") e, em seguida, encaminhar a chamada para o agente de suporte técnico mais apropriado com base na resposta a essas perguntas.</span><span class="sxs-lookup"><span data-stu-id="1f792-109">Press 3 if you are having network problems.") and then route the call to the most appropriate help desk agent based on the answer to those questions.</span></span>

<span data-ttu-id="1f792-110">O Relatório de Uso de Grupo de Resposta oferece uma visão detalhada do número de chamadas telefônicas recebidas por todos os fluxos de trabalho do Grupo de Resposta e decompõe essas chamadas em categorias mais restritas, como Chamadas oferecidas, Chamadas respondidas e Chamadas abandonadas.</span><span class="sxs-lookup"><span data-stu-id="1f792-110">The Response Group Usage Report provides a detailed look at the number of phone calls received by all your Response Group workflows, then breaks those calls down into more finite categories such as Offered calls, Answered calls, and Abandoned calls.</span></span>

<span data-ttu-id="1f792-111">A chave para trabalhar com o Relatório de Uso do Grupo de Resposta é entender a diferença entre os tipos de chamada reportados:</span><span class="sxs-lookup"><span data-stu-id="1f792-111">The key to working with the Response Group Usage Report is to understand the difference between the reported call types:</span></span>

  - <span data-ttu-id="1f792-p102">**Chamadas recebidas**. Número total de chamadas recebidas por todas as instâncias do aplicativo Grupo de Resposta.</span><span class="sxs-lookup"><span data-stu-id="1f792-p102">**Received calls**. Total number of calls received by all instances of the Response Group application.</span></span>

  - <span data-ttu-id="1f792-p103">**Chamadas bem-sucedidas**. Número total de chamadas atendidas pelo aplicativo Grupo de Resposta.</span><span class="sxs-lookup"><span data-stu-id="1f792-p103">**Successful calls**. Total number of calls that were picked up by the Response Group application.</span></span>

  - <span data-ttu-id="1f792-p104">**Chamadas oferecidas**. Número total de chamadas transferidas para um agente do Grupo de Resposta.</span><span class="sxs-lookup"><span data-stu-id="1f792-p104">**Offered calls**. Total number of calls that were transferred to a Response Group agent.</span></span>

  - <span data-ttu-id="1f792-p105">**Chamadas atendidas**. Número total de chamadas atendidas por um agente do Grupo de Resposta.</span><span class="sxs-lookup"><span data-stu-id="1f792-p105">**Answered calls**. Total number of calls that were actually answered by a Response Group agent.</span></span>

  - <span data-ttu-id="1f792-p106">**Porcentagem de chamadas abandonadas**. Porcentagem de chamadas que foram recebidas pelo aplicativo Grupo de Resposta, mas que nunca foram atendidas por um agente. Esse valor é calculado subtraindo as chamadas atendidas pelas chamadas recebidas e, então, dividindo esse valor pelo número de chamadas recebidas. Por exemplo, se 10 chamadas foram recebidas e 7 foram atendidas, você deve subtrair 7 de 10, restando 3 chamadas não atendidas. Esse valor deve ser dividido por 10, resultando em uma porcentagem de 30% de chamadas abandonadas.</span><span class="sxs-lookup"><span data-stu-id="1f792-p106">**Percentage of abandoned calls**. Percentage of calls that were received by the Response Group application but were never answered by an agent. This value is calculated by subtracting the Answered calls from the Received calls, and then dividing that value by the number of Received calls. For example, if you received 10 calls and 7 were answered, you would subtract 7 from 10, leaving 3 unanswered calls. That value would then be divided by 10, giving you an abandoned call percentage of 30%.</span></span>

  - <span data-ttu-id="1f792-p107">**Chamadas transferidas**. Número total de chamadas do Grupo de Resposta transferidas devido a um tempo limite ou excedente de fila.</span><span class="sxs-lookup"><span data-stu-id="1f792-p107">**Transferred calls**. Total number of Response Group calls that were transferred because of a queue timeout or queue overflow.</span></span>

<span data-ttu-id="1f792-p108">Se estiver analisando o Relatório de Uso de Grupo de Resposta e não se lembrar da definição de qualquer um desses tipos de chamada, basta manter o mouse sobre o rótulo apropriado do tipo de chamada. Uma dica de ferramenta será exibida oferecendo uma breve descrição do tipo de chamada.</span><span class="sxs-lookup"><span data-stu-id="1f792-p108">If you are looking at the Response Group Usage Report and can't remember the definition for any of these call types, simply hold your mouse over the appropriate call type label. A tooltip will appear that offers a brief description of the call type.</span></span>

<span data-ttu-id="1f792-p109">O Relatório de Uso do Grupo de Resposta permite que você filtre em um URI de fluxo de trabalho (o endereço SIP associado a esse fluxo de trabalho). No entanto, os próprios URIs de fluxo de trabalho não são exibidos no relatório. Se quiser saber, por exemplo, quais fluxos de trabalho estão respondendo à maioria das chamadas ou quais estão recebendo a maioria das chamadas transferidas, clique na métrica apropriada para abrir o Relatório de Lista de Chamadas do Grupo de Resposta para o período. Esse relatório lista os URIs de fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="1f792-p109">The Response Group Usage Report allows you to filter on a workflow URI (the SIP address associated with that workflow). However, workflow URIs do not actually appear on the report itself. If you would like to know things such as which workflows are answering the most calls or which workflows are experiencing the most transferred calls, click the appropriate metric to open the Response Group Call List Report for that given time period. That reports does list the workflow URIs.</span></span>

<div>

## <a name="accessing-the-response-group-usage-report"></a><span data-ttu-id="1f792-133">Acessando o Relatório de Uso do Grupo de Resposta</span><span class="sxs-lookup"><span data-stu-id="1f792-133">Accessing the Response Group Usage Report</span></span>

<span data-ttu-id="1f792-134">O Relatório de Uso do Grupo de Resposta é acessado pela home page Relatórios de Monitoramento.</span><span class="sxs-lookup"><span data-stu-id="1f792-134">The Response Group Usage Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="1f792-135">Você pode fazer uma busca detalhada no [relatório de lista de chamadas em grupo de resposta no Lync Server 2013](lync-server-2013-response-group-call-list-report.md) clicando em qualquer uma das seguintes métricas:</span><span class="sxs-lookup"><span data-stu-id="1f792-135">You can drill down to the [Response Group Call List Report in Lync Server 2013](lync-server-2013-response-group-call-list-report.md) by clicking any of the following metrics:</span></span>

  - <span data-ttu-id="1f792-136">Chamadas recebidas</span><span class="sxs-lookup"><span data-stu-id="1f792-136">Received calls</span></span>

  - <span data-ttu-id="1f792-137">Chamadas bem-sucedidas</span><span class="sxs-lookup"><span data-stu-id="1f792-137">Successful calls</span></span>

  - <span data-ttu-id="1f792-138">Chamadas oferecidas</span><span class="sxs-lookup"><span data-stu-id="1f792-138">Offered calls</span></span>

  - <span data-ttu-id="1f792-139">Chamadas atendidas</span><span class="sxs-lookup"><span data-stu-id="1f792-139">Answered calls</span></span>

  - <span data-ttu-id="1f792-140">Chamadas transferidas</span><span class="sxs-lookup"><span data-stu-id="1f792-140">Transferred calls</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-response-group-usage-report"></a><span data-ttu-id="1f792-141">Fazendo o melhor uso do Relatório de Uso do Grupo de Resposta</span><span class="sxs-lookup"><span data-stu-id="1f792-141">Making the Best Use of the Response Group Usage Report</span></span>

<span data-ttu-id="1f792-142">Um dos usos mais interessantes do Relatório de Uso do Grupo de Resposta pode não estar imediatamente aparente: a capacidade de recuperar informações de uso de um fluxo de trabalho individual do Grupo de Resposta.</span><span class="sxs-lookup"><span data-stu-id="1f792-142">One of the more interesting uses of the Response Group Usage Report might not be readily apparent: the ability to retrieve usage information for a single Response Group workflow.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="1f792-143">Um fluxo de trabalho de grupo de resposta é basicamente um conjunto de instruções que determina o que o Lync Server faz quando um usuário disca para um número de telefone específico.</span><span class="sxs-lookup"><span data-stu-id="1f792-143">A Response Group workflow is basically a set of instructions that determines what Lync Server does when a user dials a particular phone number.</span></span> <span data-ttu-id="1f792-144">Para isso, cada fluxo de trabalho é associado exclusivamente a um número de telefone.</span><span class="sxs-lookup"><span data-stu-id="1f792-144">To that end, each workflow is uniquely associated with a phone number.</span></span> <span data-ttu-id="1f792-145">Quando alguém liga para o número, o fluxo de trabalho determina como a chamada será tratada.</span><span class="sxs-lookup"><span data-stu-id="1f792-145">When someone calls that number, the workflow determines how the call will be handled.</span></span> <span data-ttu-id="1f792-146">Por exemplo, o fluxo de trabalho pode fazer com que a chamada seja roteada para uma série de perguntas de resposta interativa de voz (IVR), que solicitam que o chamador especifique informações adicionais ("Pressione 1 para suporte de hardware.</span><span class="sxs-lookup"><span data-stu-id="1f792-146">For example, the workflow might cause the call to be routed to a series of interactive voice response (IVR) questions that prompt the caller to enter additional information ("Press 1 for hardware support.</span></span> <span data-ttu-id="1f792-147">Pressione 2 para suporte de software").</span><span class="sxs-lookup"><span data-stu-id="1f792-147">Press 2 for software support.").</span></span> <span data-ttu-id="1f792-148">Como alternativa, o fluxo de trabalho pode fazer com que a chamada seja colocada em uma fila e o chamador colocado em espera até que um agente esteja disponível para atender a chamada.</span><span class="sxs-lookup"><span data-stu-id="1f792-148">Alternatively, the workflow might cause the call to be placed in a queue , with the caller put on hold until an agent is available to answer the call.</span></span> <span data-ttu-id="1f792-149">A disponibilidade dos agentes para atender chamadas também é determinada pelo fluxo de trabalho: eles são usados para configurar as horas comerciais (os dias da semana e as horas do dia em que os agentes estão disponíveis para atender chamadas) e feriados (dias em que nenhum agente está disponível para atender chamadas).</span><span class="sxs-lookup"><span data-stu-id="1f792-149">The availability of agents to answer calls is also dictated by the workflow: workflows are used to configure both business hours (the days of the week and the times of day when agents are available to answer calls) and holidays (days when no agents are available to answer calls).</span></span> <span data-ttu-id="1f792-150">Sempre que você liga para um número de telefone que pertence ao aplicativo Grupo de Resposta, você está essencialmente ligando para um fluxo de trabalho do Grupo de Resposta.</span><span class="sxs-lookup"><span data-stu-id="1f792-150">Any time you dial a phone number that belongs to the Response Group application you are essentially calling a Response Group workflow.</span></span>



</div>

<span data-ttu-id="1f792-p112">Embora os URIs de fluxo de trabalho não sejam exibidos no Relatório de Uso do Grupo de Resposta, ainda é possível exibir as estatísticas de uso de um fluxo de trabalho individual, algo que sempre é extremamente útil. Por exemplo, suponhamos que você tenha divulgado uma nova campanha publicitária e esteja curioso para saber se as pessoas estão ligando para se informar sobre o produto. Se o fluxo de trabalho do Grupo de Resposta tiver sido associado ao número de telefone dado na campanha publicitária, será possível verificar com facilidade quantas pessoas (se houverem) estão ligando para o número.</span><span class="sxs-lookup"><span data-stu-id="1f792-p112">Although workflow URIs do not appear in the Response Group Usage Report, it's still possible to view the usage statistics for a single workflow, something that is often extremely useful. For example, suppose you recently unveiled a new ad campaign and are curious to know whether people are calling in to ask about that product. If you have associated a Response Group workflow with the phone number given in the ad campaign, you can easily check to see how many people (if any) are calling that number.</span></span>

<span data-ttu-id="1f792-154">É possível também usar uma abordagem semelhante para medir o número de chamadas que estão sendo tratadas pelo suporte técnico interno ou pelo departamento de atendimento ao cliente.</span><span class="sxs-lookup"><span data-stu-id="1f792-154">You might also use a similar approach to gauge the number of calls being handled by your internal help desk or your customer service department.</span></span>

<span data-ttu-id="1f792-155">Para revisar as estatísticas de uso de determinado fluxo de trabalho, insira o URI do fluxo de trabalho na caixa URI do Fluxo de Trabalho.</span><span class="sxs-lookup"><span data-stu-id="1f792-155">To review usage statistics for a particular workflow, enter the workflow URI in the Workflow URI box.</span></span> <span data-ttu-id="1f792-156">Obviamente, como observado, os URIs do fluxo de trabalho (o endereço SIP associado a um fluxo de trabalho) não são exibidos no relatório.</span><span class="sxs-lookup"><span data-stu-id="1f792-156">Of course, as noted, workflow URIs (the SIP address associated with a workflow) do not appear on the report.</span></span> <span data-ttu-id="1f792-157">Isso significa que é preciso encontrar uma forma de determinar o URI de um fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="1f792-157">That means you need to find some other way to determine the URI of a workflow.</span></span> <span data-ttu-id="1f792-158">Uma maneira de fazer isso é usar o Windows PowerShell e o Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1f792-158">One way to do this is to use Windows PowerShell and the Lync Server Management Shell.</span></span> <span data-ttu-id="1f792-159">Por exemplo, este comando retorna todos os URIs de todos os fluxos de trabalho do Grupo de Resposta:</span><span class="sxs-lookup"><span data-stu-id="1f792-159">For example, this command returns the URIs for all your Response Group workflows:</span></span>

    Get-CsRgsWorkflow | Select-Object Name, PrimaryUri

<span data-ttu-id="1f792-160">Isso retornará dados similares a esses:</span><span class="sxs-lookup"><span data-stu-id="1f792-160">That will return data similar to this:</span></span>

    Name                            PrimaryUri
    ----                            ----------
    Customer Support                sip:support@litwareinc.com
    Help Desk                       sip:helpdesk@litwareinc.com
    New Ad Campaign                 sip:newads@litwareinc.com

<span data-ttu-id="1f792-161">Este comando retorna informações sobre um fluxo de trabalho individual, cujo nome é Nova campanha publicitária:</span><span class="sxs-lookup"><span data-stu-id="1f792-161">This command returns information for a single workflow, the one with the name New Ad Campaign:</span></span>

    Get-CsRgsWorkflow -Name "New Ad Campaign" | Select-Object Name, PrimaryUri

</div>

<div>

## <a name="filters"></a><span data-ttu-id="1f792-162">Filtros</span><span class="sxs-lookup"><span data-stu-id="1f792-162">Filters</span></span>

<span data-ttu-id="1f792-p114">Os filtros fornecem uma maneira de retornar um conjunto de dados mais direcionado ou de exibir os dados retornados de maneiras diferentes. Por exemplo, o Relatório de Uso do Grupo de Resposta permite que você veja os dados dos fluxos de trabalho de todos os seus Grupos de Resposta ou que veja os dados de um fluxo de trabalho individual. Também é possível escolher como os dados devem ser agrupados. Nesse caso, os usos são agrupados por hora, dia, semana ou mês.</span><span class="sxs-lookup"><span data-stu-id="1f792-p114">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Response Group Usage Report enables you to view data for all your Response Group workflows or to view data for an individual workflow. You can also choose how data should be grouped. In this case, usages are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="1f792-167">A tabela a seguir lista os filtros que podem ser usados com o Relatório de Uso do Grupo de Resposta.</span><span class="sxs-lookup"><span data-stu-id="1f792-167">The following table lists the filters that you can use with the Response Group Usage Report.</span></span>

### <a name="response-group-usage-report-filters"></a><span data-ttu-id="1f792-168">Filtros do Relatório de Uso do Grupo de Resposta</span><span class="sxs-lookup"><span data-stu-id="1f792-168">Response Group Usage Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1f792-169">Nome</span><span class="sxs-lookup"><span data-stu-id="1f792-169">Name</span></span></th>
<th><span data-ttu-id="1f792-170">Descrição</span><span class="sxs-lookup"><span data-stu-id="1f792-170">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1f792-171"><strong>De</strong></span><span class="sxs-lookup"><span data-stu-id="1f792-171"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="1f792-p115">Data/hora de início para o intervalo de tempo. Para ver os dados por horas, insira a data e hora de início conforme segue:</span><span class="sxs-lookup"><span data-stu-id="1f792-p115">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="1f792-174">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="1f792-174">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="1f792-p116">Se você não inserir a hora de início, o relatório começará automaticamente à meia-noite do dia especificado. Para ver os dados por dia, insira somente a data:</span><span class="sxs-lookup"><span data-stu-id="1f792-p116">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="1f792-177">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="1f792-177">7/7/2012</span></span></p>
<p><span data-ttu-id="1f792-178">Para exibir por semana ou mês, insira uma data dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):</span><span class="sxs-lookup"><span data-stu-id="1f792-178">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="1f792-179">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="1f792-179">7/3/2012</span></span></p>
<p><span data-ttu-id="1f792-180">As semanas sempre vão de domingo a sábado.</span><span class="sxs-lookup"><span data-stu-id="1f792-180">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1f792-181"><strong>Até</strong></span><span class="sxs-lookup"><span data-stu-id="1f792-181"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="1f792-p117">Data/hora final de intervalo de tempo. Para ver os dados por horas, insira a data e hora final conforme segue:</span><span class="sxs-lookup"><span data-stu-id="1f792-p117">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="1f792-184">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="1f792-184">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="1f792-p118">Se você não inserir a hora final, o relatório terminará automaticamente à meia-noite do dia especificado. Para ver os dados por dia, insira somente a data:</span><span class="sxs-lookup"><span data-stu-id="1f792-p118">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="1f792-187">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="1f792-187">7/7/2012</span></span></p>
<p><span data-ttu-id="1f792-188">Para exibir por semana ou mês, insira uma data dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):</span><span class="sxs-lookup"><span data-stu-id="1f792-188">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="1f792-189">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="1f792-189">7/3/2012</span></span></p>
<p><span data-ttu-id="1f792-190">As semanas sempre vão de domingo a sábado.</span><span class="sxs-lookup"><span data-stu-id="1f792-190">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1f792-191"><strong>Intervalo</strong></span><span class="sxs-lookup"><span data-stu-id="1f792-191"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="1f792-p119">Intervalo de tempo. Selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="1f792-p119">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="1f792-194">Por hora (é possível exibir no máximo 25 horas)</span><span class="sxs-lookup"><span data-stu-id="1f792-194">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="1f792-195">Diariamente (é possível exibir no máximo 31 dias)</span><span class="sxs-lookup"><span data-stu-id="1f792-195">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="1f792-196">Semanalmente (é possível exibir no máximo 12 semanas)</span><span class="sxs-lookup"><span data-stu-id="1f792-196">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="1f792-197">Mensalmente (é possível exibir no máximo 12 meses)</span><span class="sxs-lookup"><span data-stu-id="1f792-197">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="1f792-198">Se as datas de início e término excederem o número máximo de valores permitidos para o intervalo selecionado, somente o número máximo de valores (a partir da data de início) será exibido.</span><span class="sxs-lookup"><span data-stu-id="1f792-198">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed.</span></span> <span data-ttu-id="1f792-199">Por exemplo, se você selecionar o intervalo diário com uma data de início de 7/7/2012 e uma data de término de 2/28/2012, os dados serão exibidos para os dias 8/7/2012 12:00 AM a 9/7/2012 12:00 AM (ou seja, um total de 31 dias da importância dos dados).</span><span class="sxs-lookup"><span data-stu-id="1f792-199">For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1f792-200"><strong>URI do Fluxo de Trabalho</strong></span><span class="sxs-lookup"><span data-stu-id="1f792-200"><strong>Workflow URI</strong></span></span></p></td>
<td><p><span data-ttu-id="1f792-p121">Permite limitar os dados retornados ao fluxo de trabalho do Grupo de Resposta especificado. Para usar esse filtro, insira o endereço SIP do Fluxo de Trabalho. Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="1f792-p121">Enables you to limit the returned data to the specified Response Group workflow. To use this filter, enter the Workflow SIP address. For example:</span></span></p>
<p><span data-ttu-id="1f792-204">sip:helpdesk@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="1f792-204">sip:helpdesk@litwareinc.com</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="1f792-205">Métricas</span><span class="sxs-lookup"><span data-stu-id="1f792-205">Metrics</span></span>

<span data-ttu-id="1f792-206">A tabela a seguir lista as informações fornecidas no Relatório de Uso do Grupo de Resposta.</span><span class="sxs-lookup"><span data-stu-id="1f792-206">The following table lists the information provided in the Response Group Usage Report.</span></span>

### <a name="response-group-usage-report-metrics"></a><span data-ttu-id="1f792-207">Métricas do Relatório de Uso do Grupo de Resposta</span><span class="sxs-lookup"><span data-stu-id="1f792-207">Response Group Usage Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1f792-208">Nome</span><span class="sxs-lookup"><span data-stu-id="1f792-208">Name</span></span></th>
<th><span data-ttu-id="1f792-209">Você pode classificar este item?</span><span class="sxs-lookup"><span data-stu-id="1f792-209">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="1f792-210">Descrição</span><span class="sxs-lookup"><span data-stu-id="1f792-210">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1f792-211"><strong>Por hora</strong></span><span class="sxs-lookup"><span data-stu-id="1f792-211"><strong>Hourly</strong></span></span></p>
<p><span data-ttu-id="1f792-212"><strong>Diário</strong></span><span class="sxs-lookup"><span data-stu-id="1f792-212"><strong>Daily</strong></span></span></p>
<p><span data-ttu-id="1f792-213"><strong>Semanal</strong></span><span class="sxs-lookup"><span data-stu-id="1f792-213"><strong>Weekly</strong></span></span></p>
<p><span data-ttu-id="1f792-214"><strong>Mensal</strong></span><span class="sxs-lookup"><span data-stu-id="1f792-214"><strong>Monthly</strong></span></span></p></td>
<td><p><span data-ttu-id="1f792-215">Não</span><span class="sxs-lookup"><span data-stu-id="1f792-215">No</span></span></p></td>
<td><p><span data-ttu-id="1f792-216">Indica o intervalo de tempo selecionado.</span><span class="sxs-lookup"><span data-stu-id="1f792-216">Indicates the selected time interval.</span></span> <span data-ttu-id="1f792-217">Quando aplicável, você pode clicar em um dado intervalo de tempo para exibir informações detalhadas para aquele intervalo.</span><span class="sxs-lookup"><span data-stu-id="1f792-217">Where applicable, you can click a given time interval to view detailed information for that interval.</span></span> <span data-ttu-id="1f792-218">Por exemplo, se você estiver usando o intervalo diário e clicar em 7/7/2012, verá um detalhamento por hora da atividade de registro do usuário para essa data.</span><span class="sxs-lookup"><span data-stu-id="1f792-218">For example, if you are using the Daily interval and you click 7/7/2012, you see an hourly breakdown of user registration activity for that date.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1f792-219"><strong>Chamadas recebidas</strong></span><span class="sxs-lookup"><span data-stu-id="1f792-219"><strong>Received calls</strong></span></span></p></td>
<td><p><span data-ttu-id="1f792-220">Não</span><span class="sxs-lookup"><span data-stu-id="1f792-220">No</span></span></p></td>
<td><p><span data-ttu-id="1f792-p123">Número total de chamadas recebidas por todas as instâncias do aplicativo Grupo de Resposta. Quando você clica nesse item, o relatório mostra a Lista de Chamadas do Grupo de Resposta para o período de tempo selecionado.</span><span class="sxs-lookup"><span data-stu-id="1f792-p123">Total number of calls received by all instances of the Response Group application. When you click this item, the report shows you the Response Group Call List report for the selected time period.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1f792-223"><strong>Chamadas bem-sucedidas</strong></span><span class="sxs-lookup"><span data-stu-id="1f792-223"><strong>Successful calls</strong></span></span></p></td>
<td><p><span data-ttu-id="1f792-224">Não</span><span class="sxs-lookup"><span data-stu-id="1f792-224">No</span></span></p></td>
<td><p><span data-ttu-id="1f792-p124">Número total de chamadas atendidas pelo aplicativo Grupo de Resposta. Quando você clica nesse item, o relatório mostra a Lista de Chamadas do Grupo de Resposta para o período de tempo selecionado.</span><span class="sxs-lookup"><span data-stu-id="1f792-p124">Total number of calls that were picked up the Response Group application. When you click this item, the report shows you the Response Group Call List report for the selected time period.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1f792-227"><strong>Chamadas oferecidas</strong></span><span class="sxs-lookup"><span data-stu-id="1f792-227"><strong>Offered calls</strong></span></span></p></td>
<td><p><span data-ttu-id="1f792-228">Não</span><span class="sxs-lookup"><span data-stu-id="1f792-228">No</span></span></p></td>
<td><p><span data-ttu-id="1f792-p125">Número total de chamadas transferidas para um agente do Grupo de Resposta. Quando você clica nesse item, o relatório mostra a Lista de Chamadas do Grupo de Resposta para o período de tempo selecionado.</span><span class="sxs-lookup"><span data-stu-id="1f792-p125">Total number of calls that were transferred to a Response Group agent. When you click this item, the report shows you the Response Group Call List report for the selected time period.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1f792-231"><strong>Chamadas atendidas</strong></span><span class="sxs-lookup"><span data-stu-id="1f792-231"><strong>Answered calls</strong></span></span></p></td>
<td><p><span data-ttu-id="1f792-232">Não</span><span class="sxs-lookup"><span data-stu-id="1f792-232">No</span></span></p></td>
<td><p><span data-ttu-id="1f792-p126">Número total de chamadas atendidas por um agente do Grupo de Resposta. Quando você clica nesse item, o relatório mostra a Lista de Chamadas do Grupo de Resposta para o período de tempo selecionado.</span><span class="sxs-lookup"><span data-stu-id="1f792-p126">Total number of calls that were actually answered by a Response Group agent. When you click this item, the report shows you the Response Group Call List report for the selected time period.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1f792-235"><strong>Porcentagem de chamadas abandonadas</strong></span><span class="sxs-lookup"><span data-stu-id="1f792-235"><strong>Percentage of abandoned calls</strong></span></span></p></td>
<td><p><span data-ttu-id="1f792-236">Não</span><span class="sxs-lookup"><span data-stu-id="1f792-236">No</span></span></p></td>
<td><p><span data-ttu-id="1f792-p127">Número total de chamadas recebidas pelo aplicativo Grupo de Resposta, mas que nunca foram atendidas por um agente. Isso é calculado subtraindo as Chamadas atendidas das Chamadas recebidas e dividindo esse valor pelo número de chamadas recebidas. Por exemplo, se você tiver 10 chamadas recebidas e sete respondidas, subtraia sete de 10, deixando três chamadas não respondidas. Esse valor seria dividido por 10, proporcionando uma porcentagem de chamadas abandonadas de 30%.</span><span class="sxs-lookup"><span data-stu-id="1f792-p127">Total number of calls that were received by the Response Group application but were never answered by an agent. This is calculated by subtracting the Answered calls from the Received calls, and then dividing that value by the number of received calls. For example, if you have 10 received calls and seven were answered, you would subtract seven from 10, leaving three unanswered calls. That value would then be divided by 10, giving you an abandoned call percentage of 30%.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1f792-241"><strong>Duração média em minutos de chamada por representante</strong></span><span class="sxs-lookup"><span data-stu-id="1f792-241"><strong>Average call minutes by agent</strong></span></span></p></td>
<td><p><span data-ttu-id="1f792-242">Não</span><span class="sxs-lookup"><span data-stu-id="1f792-242">No</span></span></p></td>
<td><p><span data-ttu-id="1f792-243">Duração média que um agente do Grupo de Resposta gasta em uma chamada.</span><span class="sxs-lookup"><span data-stu-id="1f792-243">Average amount of time a Response Group agent spent on a call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1f792-244"><strong>Chamadas transferidas</strong></span><span class="sxs-lookup"><span data-stu-id="1f792-244"><strong>Transferred calls</strong></span></span></p></td>
<td><p><span data-ttu-id="1f792-245">Não</span><span class="sxs-lookup"><span data-stu-id="1f792-245">No</span></span></p></td>
<td><p><span data-ttu-id="1f792-p128">Número total de chamadas do Grupo de Resposta transferidas devido a um tempo limite ou excedente de fila. Ao clicar nesse item, o relatório mostra a Lista de Chamadas do Grupo de Resposta para o período selecionado.</span><span class="sxs-lookup"><span data-stu-id="1f792-p128">Total number of Response Group calls that were transferred because of a queue timeout or queue overflow. When you click this item, the report shows you the Response Group Call List report for the selected time period.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

