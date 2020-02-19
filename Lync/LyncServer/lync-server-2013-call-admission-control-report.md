---
title: 'Lync Server 2013: relatório de controle de admissão de chamada'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call Admission Control Report
ms:assetid: ea4b0c9f-7f93-4b8a-b901-01e1636c44fb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615043(v=OCS.15)
ms:contentKeyID: 48185933
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 60a51a27a4aa5c6d0df5970da669bc1c67f068c2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134987"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="call-admission-control-report-in-lync-server-2013"></a><span data-ttu-id="5dff7-102">Relatório de controle de admissão de chamadas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5dff7-102">Call Admission Control Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5dff7-103">_**Última modificação do tópico:** 2012-06-29_</span><span class="sxs-lookup"><span data-stu-id="5dff7-103">_**Topic Last Modified:** 2012-06-29_</span></span>

<span data-ttu-id="5dff7-104">O Relatório de Controle de Admissão de Chamadas fornece informações sobre sessões de conferência e ponto a ponto que eram conduzidas sob restrições impostas pelo Controle de Admissão de Chamadas.</span><span class="sxs-lookup"><span data-stu-id="5dff7-104">The Call Admission Control Report provides information about peer-to-peer and conferencing sessions that were conducted under restrictions set in place by Call Admission Control.</span></span> <span data-ttu-id="5dff7-105">Call Admission Control, introduzido no Microsoft Lync Server 2010, oferece uma maneira de os administradores permitirem (ou não permitirem) sessões de comunicação com base nas restrições de largura de banda.</span><span class="sxs-lookup"><span data-stu-id="5dff7-105">Call Admission Control, introduced in Microsoft Lync Server 2010, provides a way for administrators to allow (or not allow) communication sessions based on bandwidth constraints.</span></span> <span data-ttu-id="5dff7-106">Por exemplo, os administradores podem criar políticas que impõe um limite na quantidade de banda disponível para chamadas de voz e vídeo.</span><span class="sxs-lookup"><span data-stu-id="5dff7-106">For example, administrators can create policies that impose a limit on the amount of bandwidth available for voice and video calls.</span></span> <span data-ttu-id="5dff7-107">Caso o limite de banda tenha sido alcançado, novas chamadas de voz ou vídeo não poderão ser feitas até que uma das chamadas atuais termine e libere os recursos de rede necessários.</span><span class="sxs-lookup"><span data-stu-id="5dff7-107">If that bandwidth limit has been reached, then no new voice or video calls can be placed until one of the current calls has ended and freed up the required network resources.</span></span>

<div>

## <a name="accessing-the-call-admission-control-report"></a><span data-ttu-id="5dff7-108">Acessando o Relatório de Controle de Admissão de Chamadas</span><span class="sxs-lookup"><span data-stu-id="5dff7-108">Accessing the Call Admission Control Report</span></span>

<span data-ttu-id="5dff7-p102">O Relatório de Controle de Admissão de Chamadas é acessado através da página de Relatórios de Monitoramento. A partir do Relatório de Controle de Admissão de Chamadas você pode buscar mais detalhes em um dos seguintes relatórios:</span><span class="sxs-lookup"><span data-stu-id="5dff7-p102">The Call Admission Control Report is accessed from the Monitoring Reports home page. From the Call Admission Control Report you can drill down to either of the following reports:</span></span>

  - <span data-ttu-id="5dff7-111">Relatório de Detalhes de Conferência – Para acessar este relatório, clique na métrica Detalhes em uma sessão de conferência.</span><span class="sxs-lookup"><span data-stu-id="5dff7-111">Conference Detail Report – To access this report, click the Details metric from a conference session.</span></span>

  - <span data-ttu-id="5dff7-112">Relatório de Detalhe de Sessão Ponto a Ponto – Para acessar este relatório, clique na métrica Detalhes para uma sessão ponto a ponto.</span><span class="sxs-lookup"><span data-stu-id="5dff7-112">Peer-to-Peer Session Detail Report – To access this report, click the Details metric for a peer-to-peer session.</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-call-admission-control-report"></a><span data-ttu-id="5dff7-113">Usando o Relatório de Controle de Admissão de Chamadas da melhor maneira possível</span><span class="sxs-lookup"><span data-stu-id="5dff7-113">Making the Best Use of the Call Admission Control Report</span></span>

<span data-ttu-id="5dff7-p103">Para obter uma lista de chamadas que falharam por causa de largura de banda insuficiente, selecione Chamadas rejeitadas por causa do controle de admisssão de chamadas, na lista suspensa de categoria de Chamadas. A maioria das chamadas retornadas provavelmente terão a ID de diagnóstico 5:</span><span class="sxs-lookup"><span data-stu-id="5dff7-p103">To get a list of calls that failed because of insufficient bandwidth, select Calls rejected because of call admission control from the Call category dropdown list. Most of the returned calls will likely have a diagnostic ID of 5:</span></span>

<span data-ttu-id="5dff7-p104">Largura de banda insuficiente para estabelecer sessão. Tente reencaminhamento PSTN.</span><span class="sxs-lookup"><span data-stu-id="5dff7-p104">Insufficient bandwidth to establish session. Attempt PSTN re-route.</span></span>

<span data-ttu-id="5dff7-118">Isso indica que as limitações do Controle de Admissão de Chamadas estavam impedidndo a chamada de ser feita na rede VoIP.</span><span class="sxs-lookup"><span data-stu-id="5dff7-118">That indicates that Call Admission Control limitations were preventing the call from being made on the VoIP network.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="5dff7-119">Filtros</span><span class="sxs-lookup"><span data-stu-id="5dff7-119">Filters</span></span>

<span data-ttu-id="5dff7-p105">Os filtros fornecem uma maneira de retornar um conjunto de dados mais direcionado ou de exibir os dados retornados de maneiras diferentes. Por exemplo, o Relatório de Controle de Admissão de Chamada permite que você filtre as chamadas de acordo com o usuário que iniciou a chamada ou com o usuário que está sendo chamado. Também é possível escolher como os dados devem ser agrupados. Nesse caso, as chamadas são agrupadas por hora, dia, semana ou mês.</span><span class="sxs-lookup"><span data-stu-id="5dff7-p105">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Call Admission Control Report enables you to filter calls by the user who initiated the call or by the user who was being called. You can also choose how data should be grouped. In this case, calls are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="5dff7-124">A tabela a seguir lista os filtros que podem ser usados com o Relatório de Controle de Admissão de Chamada.</span><span class="sxs-lookup"><span data-stu-id="5dff7-124">The following table lists the filters that you can use with the Call Admission Control Report.</span></span>

### <a name="call-admission-control-report-filters"></a><span data-ttu-id="5dff7-125">Filtros do Relatório de Controle de Admissão de Chamadas</span><span class="sxs-lookup"><span data-stu-id="5dff7-125">Call Admission Control Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5dff7-126">Nome</span><span class="sxs-lookup"><span data-stu-id="5dff7-126">Name</span></span></th>
<th><span data-ttu-id="5dff7-127">Descrição</span><span class="sxs-lookup"><span data-stu-id="5dff7-127">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5dff7-128"><strong>De</strong></span><span class="sxs-lookup"><span data-stu-id="5dff7-128"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="5dff7-p106">Data/hora de início para o intervalo de tempo. Para exibir os dados por horas, digite a data e a hora de início da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="5dff7-p106">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="5dff7-131">17/07/2012 13:00</span><span class="sxs-lookup"><span data-stu-id="5dff7-131">7/17/12012 1:00 PM</span></span></p>
<p><span data-ttu-id="5dff7-p107">Se você não digitar um horário de início, o relatório começará automaticamente às 12:00 AM no dia especificado. Para exibir os dados por dia, digite apenas a data:</span><span class="sxs-lookup"><span data-stu-id="5dff7-p107">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="5dff7-134">7/17/12012</span><span class="sxs-lookup"><span data-stu-id="5dff7-134">7/17/12012</span></span></p>
<p><span data-ttu-id="5dff7-135">Para exibir por semana ou por mês, insira uma data cai em qualquer lugar dentro da semana ou mês que você deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):</span><span class="sxs-lookup"><span data-stu-id="5dff7-135">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="5dff7-136">7/13/2012</span><span class="sxs-lookup"><span data-stu-id="5dff7-136">7/13/2012</span></span></p>
<p><span data-ttu-id="5dff7-137">As semanas são sempre de domingo a sábado.</span><span class="sxs-lookup"><span data-stu-id="5dff7-137">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5dff7-138"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="5dff7-138"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="5dff7-p108">Data/hora de término para o intervalo de tempo. Para exibir os dados por horas, digite a data e hora de término da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="5dff7-p108">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="5dff7-141">17/07/12012 13:00</span><span class="sxs-lookup"><span data-stu-id="5dff7-141">7/17/12012 1:00 PM</span></span></p>
<p><span data-ttu-id="5dff7-p109">Se você não digitar um horário de término, o relatório terminará automaticamente às 12:00 AM no dia especificado. Para exibir os dados por dia, digite apenas a data:</span><span class="sxs-lookup"><span data-stu-id="5dff7-p109">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="5dff7-144">7/17/12012</span><span class="sxs-lookup"><span data-stu-id="5dff7-144">7/17/12012</span></span></p>
<p><span data-ttu-id="5dff7-145">Para exibir por semana ou por mês, insira uma data cai em qualquer lugar dentro da semana ou mês que você deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):</span><span class="sxs-lookup"><span data-stu-id="5dff7-145">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="5dff7-146">7/13/2012</span><span class="sxs-lookup"><span data-stu-id="5dff7-146">7/13/2012</span></span></p>
<p><span data-ttu-id="5dff7-147">As semanas sempre correm do domingo até sábado.</span><span class="sxs-lookup"><span data-stu-id="5dff7-147">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5dff7-148"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="5dff7-148"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="5dff7-p110">FQDN (Nome de domínio totalmente qualificado) do pool de Registradores ou Servidor de Borda. Você pode selecionar um pool individual ou clicar em <strong>[Tudo]</strong> para ver os dados de todos os pools. Essa lista suspensa é automaticamente preenchida para você com base nos registros no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="5dff7-p110">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5dff7-152"><strong>Tipo de atividade </strong></span><span class="sxs-lookup"><span data-stu-id="5dff7-152"><strong>Activity type</strong></span></span></p></td>
<td><p><span data-ttu-id="5dff7-p111">Tipo de atividade. Selecione uma das seguintes atividades:</span><span class="sxs-lookup"><span data-stu-id="5dff7-p111">Type of activity. Select one of the following activities:</span></span></p>
<ul>
<li><p><span data-ttu-id="5dff7-155">Todos os</span><span class="sxs-lookup"><span data-stu-id="5dff7-155">[All]</span></span></p></li>
<li><p><span data-ttu-id="5dff7-156">Ponto a ponto</span><span class="sxs-lookup"><span data-stu-id="5dff7-156">Peer-to-Peer</span></span></p></li>
<li><p><span data-ttu-id="5dff7-157">Conferência</span><span class="sxs-lookup"><span data-stu-id="5dff7-157">Conference</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5dff7-158"><strong>Categoria da chamada</strong></span><span class="sxs-lookup"><span data-stu-id="5dff7-158"><strong>Call category</strong></span></span></p></td>
<td><p><span data-ttu-id="5dff7-p112">Indica o motivo de o CAC ter sido usado para a chamada. Selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="5dff7-p112">Indicates the reason that CAC was used for the call. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="5dff7-161">Todos os</span><span class="sxs-lookup"><span data-stu-id="5dff7-161">[All]</span></span></p></li>
<li><p><span data-ttu-id="5dff7-162">Chamada rejeitada devido ao controle de admissão de chamada</span><span class="sxs-lookup"><span data-stu-id="5dff7-162">Call rejected because of call admission control</span></span></p></li>
<li><p><span data-ttu-id="5dff7-163">Chamadas reencaminhadas por PSTN devido ao controle de admissão de chamada</span><span class="sxs-lookup"><span data-stu-id="5dff7-163">Calls rerouted through PSTN because of call admission control</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-sessions"></a><span data-ttu-id="5dff7-164">Métricas para sessões ponto a ponto</span><span class="sxs-lookup"><span data-stu-id="5dff7-164">Metrics for Peer-to-Peer Sessions</span></span>

<span data-ttu-id="5dff7-165">A tabela a seguir lista as informações fornecidas no Relatório de Controle de Admissão de Chamada para sessões ponto a ponto (ou seja, sessões que envolvem apenas dois participantes).</span><span class="sxs-lookup"><span data-stu-id="5dff7-165">The following table lists the information provided in the Call Admission Control Report for peer-to-peer sessions (that is, sessions involving just two participants).</span></span>

### <a name="metrics-for-peer-to-peer-sessions"></a><span data-ttu-id="5dff7-166">Métricas para sessões ponto a ponto</span><span class="sxs-lookup"><span data-stu-id="5dff7-166">Metrics for Peer-to-Peer Sessions</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5dff7-167">Nome</span><span class="sxs-lookup"><span data-stu-id="5dff7-167">Name</span></span></th>
<th><span data-ttu-id="5dff7-168">É possível classificar este item?</span><span class="sxs-lookup"><span data-stu-id="5dff7-168">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="5dff7-169">Descrição</span><span class="sxs-lookup"><span data-stu-id="5dff7-169">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5dff7-170"><strong>Ver os detalhes</strong></span><span class="sxs-lookup"><span data-stu-id="5dff7-170"><strong>Detail</strong></span></span></p></td>
<td><p><span data-ttu-id="5dff7-171">Não</span><span class="sxs-lookup"><span data-stu-id="5dff7-171">No</span></span></p></td>
<td><p><span data-ttu-id="5dff7-172">Quando você clica nesse item, o relatório mostra o Relatório de Detalhes da Sessão Ponto a Ponto para a sessão especificada.</span><span class="sxs-lookup"><span data-stu-id="5dff7-172">When you click this item, the report shows you a Peer-to-Peer Session Detail Report for the specified session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5dff7-173"><strong>Do usuário </strong></span><span class="sxs-lookup"><span data-stu-id="5dff7-173"><strong>From user</strong></span></span></p></td>
<td><p><span data-ttu-id="5dff7-174">Sim</span><span class="sxs-lookup"><span data-stu-id="5dff7-174">Yes</span></span></p></td>
<td><p><span data-ttu-id="5dff7-175">Endereço SIP do usuário que iniciou a sessão.</span><span class="sxs-lookup"><span data-stu-id="5dff7-175">SIP address of the user who initiated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5dff7-176"><strong>Para usuário</strong></span><span class="sxs-lookup"><span data-stu-id="5dff7-176"><strong>To user</strong></span></span></p></td>
<td><p><span data-ttu-id="5dff7-177">Sim</span><span class="sxs-lookup"><span data-stu-id="5dff7-177">Yes</span></span></p></td>
<td><p><span data-ttu-id="5dff7-178">Endereço SIP do usuário convidado para ingressar na sessão.</span><span class="sxs-lookup"><span data-stu-id="5dff7-178">SIP address of the user who was invited to join the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5dff7-179"><strong>Modalidades</strong></span><span class="sxs-lookup"><span data-stu-id="5dff7-179"><strong>Modalities</strong></span></span></p></td>
<td><p><span data-ttu-id="5dff7-180">Sim</span><span class="sxs-lookup"><span data-stu-id="5dff7-180">Yes</span></span></p></td>
<td><p><span data-ttu-id="5dff7-181">Modalidades de comunicação (como áudio e vídeo) usadas durante a sessão.</span><span class="sxs-lookup"><span data-stu-id="5dff7-181">Communication modalities (such as audio and video) that were used during the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5dff7-182"><strong>Hora do convite</strong></span><span class="sxs-lookup"><span data-stu-id="5dff7-182"><strong>Invite time</strong></span></span></p></td>
<td><p><span data-ttu-id="5dff7-183">Sim</span><span class="sxs-lookup"><span data-stu-id="5dff7-183">Yes</span></span></p></td>
<td><p><span data-ttu-id="5dff7-184">Data e hora de envio do convite inicial da sessão para o usuário De.</span><span class="sxs-lookup"><span data-stu-id="5dff7-184">Date and time the initial session invitation was sent to the From user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5dff7-185"><strong>Hora da resposta</strong></span><span class="sxs-lookup"><span data-stu-id="5dff7-185"><strong>Response time</strong></span></span></p></td>
<td><p><span data-ttu-id="5dff7-186">Sim</span><span class="sxs-lookup"><span data-stu-id="5dff7-186">Yes</span></span></p></td>
<td><p><span data-ttu-id="5dff7-187">Data e hora de recebimento da aceitação do convite.</span><span class="sxs-lookup"><span data-stu-id="5dff7-187">Date and time that the invitation acceptance was received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5dff7-188"><strong>Hora de término</strong></span><span class="sxs-lookup"><span data-stu-id="5dff7-188"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="5dff7-189">Sim</span><span class="sxs-lookup"><span data-stu-id="5dff7-189">Yes</span></span></p></td>
<td><p><span data-ttu-id="5dff7-190">Data e hora de encerramento da sessão.</span><span class="sxs-lookup"><span data-stu-id="5dff7-190">Date and time that the session ended.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5dff7-191"><strong>ID do Diagnóstico</strong></span><span class="sxs-lookup"><span data-stu-id="5dff7-191"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="5dff7-192">Sim</span><span class="sxs-lookup"><span data-stu-id="5dff7-192">Yes</span></span></p></td>
<td><p><span data-ttu-id="5dff7-p113">Identificador exclusivo (na forma de um cabeçalho de diagnóstico-ms) anexado a uma mensagem SIP que fornece informações úteis sobre os erros de solução de problemas. Os cabeçalhos diagnósticos são opcionais (é possível ter sessões SIP que não os incluem), e os IDs diagnósticos são relatados somente para as sessões com algum tipo de problema.</span><span class="sxs-lookup"><span data-stu-id="5dff7-p113">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors. Diagnostics headers are optional (it is possible to have SIP sessions that do not include these headers), and diagnostic IDs are reported only for sessions that experienced problems of some kind.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferencing-sessions"></a><span data-ttu-id="5dff7-195">Métricas para sessões de conferência</span><span class="sxs-lookup"><span data-stu-id="5dff7-195">Metrics for Conferencing Sessions</span></span>

<span data-ttu-id="5dff7-196">A tabela a seguir lista as informações fornecidas no Relatório de Controle de Admissão de Chamada para sessões de conferência (ou seja, sessões que envolvem três ou mais participantes).</span><span class="sxs-lookup"><span data-stu-id="5dff7-196">The following table lists the information provided in the Call Admission Control Report for conferencing sessions (that is, sessions involving three or more participants).</span></span>

### <a name="metrics-for-conferencing-sessions"></a><span data-ttu-id="5dff7-197">Métricas para sessões de conferência</span><span class="sxs-lookup"><span data-stu-id="5dff7-197">Metrics for Conferencing Sessions</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5dff7-198">Nome</span><span class="sxs-lookup"><span data-stu-id="5dff7-198">Name</span></span></th>
<th><span data-ttu-id="5dff7-199">É possível classificar este item?</span><span class="sxs-lookup"><span data-stu-id="5dff7-199">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="5dff7-200">Descrição</span><span class="sxs-lookup"><span data-stu-id="5dff7-200">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5dff7-201"><strong>URI de conferência</strong></span><span class="sxs-lookup"><span data-stu-id="5dff7-201"><strong>Conference URI</strong></span></span></p></td>
<td><p><span data-ttu-id="5dff7-202">Sim</span><span class="sxs-lookup"><span data-stu-id="5dff7-202">Yes</span></span></p></td>
<td><p><span data-ttu-id="5dff7-p114">Identificador exclusivo para a conferência. Quando você clica nesse item, o relatório mostra os participantes individuais da conferência.</span><span class="sxs-lookup"><span data-stu-id="5dff7-p114">Unique identifier for the conference. When you click this item, the report shows the individual conference participants.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5dff7-205"><strong>Organizador</strong></span><span class="sxs-lookup"><span data-stu-id="5dff7-205"><strong>Organizer</strong></span></span></p></td>
<td><p><span data-ttu-id="5dff7-206">Sim</span><span class="sxs-lookup"><span data-stu-id="5dff7-206">Yes</span></span></p></td>
<td><p><span data-ttu-id="5dff7-207">Endereço SIP do usuário que organizou a conferência.</span><span class="sxs-lookup"><span data-stu-id="5dff7-207">SIP address of the user who organized the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5dff7-208"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="5dff7-208"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="5dff7-209">Sim</span><span class="sxs-lookup"><span data-stu-id="5dff7-209">Yes</span></span></p></td>
<td><p><span data-ttu-id="5dff7-210">Servidor de Borda usado na conferência.</span><span class="sxs-lookup"><span data-stu-id="5dff7-210">Edge Server used in the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5dff7-211"><strong>Hora de início</strong></span><span class="sxs-lookup"><span data-stu-id="5dff7-211"><strong>Start time</strong></span></span></p></td>
<td><p><span data-ttu-id="5dff7-212">Sim</span><span class="sxs-lookup"><span data-stu-id="5dff7-212">Yes</span></span></p></td>
<td><p><span data-ttu-id="5dff7-213">Data e hora de início da sessão.</span><span class="sxs-lookup"><span data-stu-id="5dff7-213">Date and time that the conference started.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5dff7-214"><strong>Hora de término</strong></span><span class="sxs-lookup"><span data-stu-id="5dff7-214"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="5dff7-215">Sim</span><span class="sxs-lookup"><span data-stu-id="5dff7-215">Yes</span></span></p></td>
<td><p><span data-ttu-id="5dff7-216">Data e hora de encerramento da conferência.</span><span class="sxs-lookup"><span data-stu-id="5dff7-216">Date and time that the conference ended.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-individual-conference-participants"></a><span data-ttu-id="5dff7-217">Métricas para participantes individuais de conferência</span><span class="sxs-lookup"><span data-stu-id="5dff7-217">Metrics for Individual Conference Participants</span></span>

<span data-ttu-id="5dff7-218">A tabela a seguir lista as informações fornecidas no Relatório de Controle de Admissão de Chamada para participantes individuais da conferência.</span><span class="sxs-lookup"><span data-stu-id="5dff7-218">The following table lists the information provided in the Call Admission Control Report for individual conference participants.</span></span>

### <a name="metrics-for-individual-conference-participants"></a><span data-ttu-id="5dff7-219">Métricas para participantes individuais de conferência</span><span class="sxs-lookup"><span data-stu-id="5dff7-219">Metrics for Individual Conference Participants</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5dff7-220">Nome</span><span class="sxs-lookup"><span data-stu-id="5dff7-220">Name</span></span></th>
<th><span data-ttu-id="5dff7-221">É possível classificar este item?</span><span class="sxs-lookup"><span data-stu-id="5dff7-221">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="5dff7-222">Descrição</span><span class="sxs-lookup"><span data-stu-id="5dff7-222">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5dff7-223"><strong>Função</strong></span><span class="sxs-lookup"><span data-stu-id="5dff7-223"><strong>Role</strong></span></span></p></td>
<td><p><span data-ttu-id="5dff7-224">Não</span><span class="sxs-lookup"><span data-stu-id="5dff7-224">No</span></span></p></td>
<td><p><span data-ttu-id="5dff7-225">Função (por exemplo, Apresentador) desempenhada pelo participante da conferência.</span><span class="sxs-lookup"><span data-stu-id="5dff7-225">Role (for example, Presenter) played by the conference participant.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5dff7-226"><strong>Participante</strong></span><span class="sxs-lookup"><span data-stu-id="5dff7-226"><strong>Participant</strong></span></span></p></td>
<td><p><span data-ttu-id="5dff7-227">Não</span><span class="sxs-lookup"><span data-stu-id="5dff7-227">No</span></span></p></td>
<td><p><span data-ttu-id="5dff7-228">Endereço SIP do participante de conferência.</span><span class="sxs-lookup"><span data-stu-id="5dff7-228">SIP address of the conference participant.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5dff7-229"><strong>Conectividade</strong></span><span class="sxs-lookup"><span data-stu-id="5dff7-229"><strong>Connectivity</strong></span></span></p></td>
<td><p><span data-ttu-id="5dff7-230">Não</span><span class="sxs-lookup"><span data-stu-id="5dff7-230">No</span></span></p></td>
<td><p><span data-ttu-id="5dff7-231">Conectividade de rede (normalmente Interna ou Externa) para o participante.</span><span class="sxs-lookup"><span data-stu-id="5dff7-231">Network connectivity (typically From Internal or From External) for the participant.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5dff7-232"><strong>Modalidade</strong></span><span class="sxs-lookup"><span data-stu-id="5dff7-232"><strong>Modality</strong></span></span></p></td>
<td><p><span data-ttu-id="5dff7-233">Não</span><span class="sxs-lookup"><span data-stu-id="5dff7-233">No</span></span></p></td>
<td><p><span data-ttu-id="5dff7-234">Tipo de conferência (por exemplo, conferência A/V).</span><span class="sxs-lookup"><span data-stu-id="5dff7-234">Conference type (for example, A/V conferencing).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5dff7-235"><strong>Hora de ingresso</strong></span><span class="sxs-lookup"><span data-stu-id="5dff7-235"><strong>Join time</strong></span></span></p></td>
<td><p><span data-ttu-id="5dff7-236">Não</span><span class="sxs-lookup"><span data-stu-id="5dff7-236">No</span></span></p></td>
<td><p><span data-ttu-id="5dff7-237">Data e hora de ingresso do participante na conferência.</span><span class="sxs-lookup"><span data-stu-id="5dff7-237">Date and time that the participant joined the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5dff7-238"><strong>Hora de saída</strong></span><span class="sxs-lookup"><span data-stu-id="5dff7-238"><strong>Leave time</strong></span></span></p></td>
<td><p><span data-ttu-id="5dff7-239">Não</span><span class="sxs-lookup"><span data-stu-id="5dff7-239">No</span></span></p></td>
<td><p><span data-ttu-id="5dff7-240">Data e hora de saída do participante da conferência.</span><span class="sxs-lookup"><span data-stu-id="5dff7-240">Date and time that the participant left the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5dff7-241"><strong>ID do Diagnóstico</strong></span><span class="sxs-lookup"><span data-stu-id="5dff7-241"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="5dff7-242">Não</span><span class="sxs-lookup"><span data-stu-id="5dff7-242">No</span></span></p></td>
<td><p><span data-ttu-id="5dff7-p115">Identificador exclusivo (na forma de um cabeçalho ms-diagnostics) anexado a uma mensagem SIP que frequentemente fornece informações úteis para solução de erros. Os cabeçalhos de diagnóstico são opcionais (é possível ter sessões SIP que não incluem esses cabeçalhos) e os IDs de diagnóstico são reportadas somente para sessões que enfrentaram problemas de algum tipo.</span><span class="sxs-lookup"><span data-stu-id="5dff7-p115">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors. Diagnostics headers are optional (it is possible to have SIP sessions that do not include these headers), and diagnostic IDs are reported only for sessions that experienced problems of some kind.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

