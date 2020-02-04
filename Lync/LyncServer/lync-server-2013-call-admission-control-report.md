---
title: 'Lync Server 2013: relatório de controle de admissão de chamadas'
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
ms.openlocfilehash: ff036a27149db4360a938fe2ce9d63c2718f4d94
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730281"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-admission-control-report-in-lync-server-2013"></a><span data-ttu-id="49a88-102">Relatório de controle de admissão de chamadas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="49a88-102">Call Admission Control Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="49a88-103">_**Tópico da última modificação:** 2012-06-29_</span><span class="sxs-lookup"><span data-stu-id="49a88-103">_**Topic Last Modified:** 2012-06-29_</span></span>

<span data-ttu-id="49a88-104">O Relatório de Controle de Admissão de Chamadas fornece informações sobre sessões de conferência e ponto a ponto que eram conduzidas sob restrições impostas pelo Controle de Admissão de Chamadas.</span><span class="sxs-lookup"><span data-stu-id="49a88-104">The Call Admission Control Report provides information about peer-to-peer and conferencing sessions that were conducted under restrictions set in place by Call Admission Control.</span></span> <span data-ttu-id="49a88-105">O controle de admissão de chamadas, introduzido no Microsoft Lync Server 2010, fornece uma maneira para os administradores permitirem (ou não permitirem) sessões de comunicação com base em restrições de largura de banda.</span><span class="sxs-lookup"><span data-stu-id="49a88-105">Call Admission Control, introduced in Microsoft Lync Server 2010, provides a way for administrators to allow (or not allow) communication sessions based on bandwidth constraints.</span></span> <span data-ttu-id="49a88-106">Por exemplo, os administradores podem criar políticas que imponham um limite na quantidade de banda disponível para chamadas de voz e vídeo.</span><span class="sxs-lookup"><span data-stu-id="49a88-106">For example, administrators can create policies that impose a limit on the amount of bandwidth available for voice and video calls.</span></span> <span data-ttu-id="49a88-107">Caso o limite de banda seja alcançado, novas chamadas de voz ou vídeo não poderão ser feitas até que uma das chamadas atuais termine e libere os recursos de rede necessários.</span><span class="sxs-lookup"><span data-stu-id="49a88-107">If that bandwidth limit has been reached, then no new voice or video calls can be placed until one of the current calls has ended and freed up the required network resources.</span></span>

<div>

## <a name="accessing-the-call-admission-control-report"></a><span data-ttu-id="49a88-108">Acessando o Relatório de Controle de Admissão de Chamadas</span><span class="sxs-lookup"><span data-stu-id="49a88-108">Accessing the Call Admission Control Report</span></span>

<span data-ttu-id="49a88-p102">O Relatório de Controle de Admissão de Chamadas é acessado através da página de Relatórios de Monitoramento. A partir do Relatório de Controle de Admissão de Chamadas você pode buscar mais detalhes em um dos seguintes relatórios:</span><span class="sxs-lookup"><span data-stu-id="49a88-p102">The Call Admission Control Report is accessed from the Monitoring Reports home page. From the Call Admission Control Report you can drill down to either of the following reports:</span></span>

  - <span data-ttu-id="49a88-111">Relatório Detalhado de Conferências – Para acessar esse relatório, clique na métrica Detalhes de uma sessão de conferência.</span><span class="sxs-lookup"><span data-stu-id="49a88-111">Conference Detail Report – To access this report, click the Details metric from a conference session.</span></span>

  - <span data-ttu-id="49a88-112">Relatório Detalhado de Sessão Ponto a Ponto – Para acessar esse relatório, clique na métrica Detalhes de uma sessão ponto a ponto.</span><span class="sxs-lookup"><span data-stu-id="49a88-112">Peer-to-Peer Session Detail Report – To access this report, click the Details metric for a peer-to-peer session.</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-call-admission-control-report"></a><span data-ttu-id="49a88-113">Como usar o Relatório de Controle de Admissão de Chamadas da melhor maneira possível</span><span class="sxs-lookup"><span data-stu-id="49a88-113">Making the Best Use of the Call Admission Control Report</span></span>

<span data-ttu-id="49a88-p103">Para obter uma lista de chamadas que falharam por causa de largura de banda insuficiente, selecione Chamadas rejeitadas devido ao controle de admissão de chamadas, na lista suspensa Categoria da chamada. A maioria das chamadas retornadas provavelmente terá a ID de diagnóstico 5:</span><span class="sxs-lookup"><span data-stu-id="49a88-p103">To get a list of calls that failed because of insufficient bandwidth, select Calls rejected because of call admission control from the Call category dropdown list. Most of the returned calls will likely have a diagnostic ID of 5:</span></span>

<span data-ttu-id="49a88-p104">Largura de banda insuficiente para estabelecer sessão. Tente reencaminhamento por PSTN.</span><span class="sxs-lookup"><span data-stu-id="49a88-p104">Insufficient bandwidth to establish session. Attempt PSTN re-route.</span></span>

<span data-ttu-id="49a88-118">Isso indica que as limitações do Controle de Admissão de Chamadas estavam impedindo a chamada de ser efetuada na rede VoIP.</span><span class="sxs-lookup"><span data-stu-id="49a88-118">That indicates that Call Admission Control limitations were preventing the call from being made on the VoIP network.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="49a88-119">Filtros</span><span class="sxs-lookup"><span data-stu-id="49a88-119">Filters</span></span>

<span data-ttu-id="49a88-p105">Os filtros fornecem uma maneira de retornar um conjunto de dados mais direcionado ou de exibir os dados retornados de maneiras diferentes. Por exemplo, o Relatório de Controle de Admissão de Chamadas permite que você filtre as chamadas de acordo com o usuário que iniciou a chamada ou com o usuário que está sendo chamado. Também é possível escolher como os dados devem ser agrupados. Nesse caso, as chamadas são agrupadas por hora, dia, semana ou mês.</span><span class="sxs-lookup"><span data-stu-id="49a88-p105">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Call Admission Control Report enables you to filter calls by the user who initiated the call or by the user who was being called. You can also choose how data should be grouped. In this case, calls are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="49a88-124">A tabela a seguir lista os filtros que podem ser usados com o Relatório de Controle de Admissão de Chamadas.</span><span class="sxs-lookup"><span data-stu-id="49a88-124">The following table lists the filters that you can use with the Call Admission Control Report.</span></span>

### <a name="call-admission-control-report-filters"></a><span data-ttu-id="49a88-125">Filtros do Relatório de Controle de Admissão de Chamadas</span><span class="sxs-lookup"><span data-stu-id="49a88-125">Call Admission Control Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="49a88-126">Nome</span><span class="sxs-lookup"><span data-stu-id="49a88-126">Name</span></span></th>
<th><span data-ttu-id="49a88-127">Descrição</span><span class="sxs-lookup"><span data-stu-id="49a88-127">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="49a88-128"><strong>De</strong></span><span class="sxs-lookup"><span data-stu-id="49a88-128"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="49a88-p106">Data/hora de início para o intervalo de tempo. Para ver os dados por horas, insira a data e hora de início conforme segue:</span><span class="sxs-lookup"><span data-stu-id="49a88-p106">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="49a88-131">7/17/12012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="49a88-131">7/17/12012 1:00 PM</span></span></p>
<p><span data-ttu-id="49a88-p107">Se você não inserir a hora de início, o relatório começará automaticamente à meia-noite do dia especificado. Para ver os dados por dia, insira somente a data:</span><span class="sxs-lookup"><span data-stu-id="49a88-p107">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="49a88-134">7/17/12012</span><span class="sxs-lookup"><span data-stu-id="49a88-134">7/17/12012</span></span></p>
<p><span data-ttu-id="49a88-135">Para exibir por semana ou mês, insira uma data dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):</span><span class="sxs-lookup"><span data-stu-id="49a88-135">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="49a88-136">7/13/2012</span><span class="sxs-lookup"><span data-stu-id="49a88-136">7/13/2012</span></span></p>
<p><span data-ttu-id="49a88-137">As semanas sempre vão de domingo a sábado.</span><span class="sxs-lookup"><span data-stu-id="49a88-137">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="49a88-138"><strong>Até</strong></span><span class="sxs-lookup"><span data-stu-id="49a88-138"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="49a88-p108">Data/hora final de intervalo de tempo. Para ver os dados por horas, insira a data e hora final conforme segue:</span><span class="sxs-lookup"><span data-stu-id="49a88-p108">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="49a88-141">7/17/12012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="49a88-141">7/17/12012 1:00 PM</span></span></p>
<p><span data-ttu-id="49a88-p109">Se você não inserir a hora final, o relatório terminará automaticamente à meia-noite do dia especificado. Para ver os dados por dia, insira somente a data:</span><span class="sxs-lookup"><span data-stu-id="49a88-p109">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="49a88-144">7/17/12012</span><span class="sxs-lookup"><span data-stu-id="49a88-144">7/17/12012</span></span></p>
<p><span data-ttu-id="49a88-145">Para exibir por semana ou mês, insira uma data dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):</span><span class="sxs-lookup"><span data-stu-id="49a88-145">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="49a88-146">7/13/2012</span><span class="sxs-lookup"><span data-stu-id="49a88-146">7/13/2012</span></span></p>
<p><span data-ttu-id="49a88-147">As semanas sempre vão de domingo a sábado.</span><span class="sxs-lookup"><span data-stu-id="49a88-147">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="49a88-148"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="49a88-148"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="49a88-p110">FQDN (Nome de domínio totalmente qualificado) do Pool de registradores ou Servidor de Borda. Você pode selecionar um pool individual ou clicar em <strong>[Todos]</strong> para ver os dados de todos os pools. Essa lista suspensa é automaticamente preenchida para você com base nos registros no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="49a88-p110">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="49a88-152"><strong>Tipo de atividade</strong></span><span class="sxs-lookup"><span data-stu-id="49a88-152"><strong>Activity type</strong></span></span></p></td>
<td><p><span data-ttu-id="49a88-p111">Tipo de atividade. Selecione uma das seguintes atividades:</span><span class="sxs-lookup"><span data-stu-id="49a88-p111">Type of activity. Select one of the following activities:</span></span></p>
<ul>
<li><p><span data-ttu-id="49a88-155">[Todos]</span><span class="sxs-lookup"><span data-stu-id="49a88-155">[All]</span></span></p></li>
<li><p><span data-ttu-id="49a88-156">Ponto a Ponto</span><span class="sxs-lookup"><span data-stu-id="49a88-156">Peer-to-Peer</span></span></p></li>
<li><p><span data-ttu-id="49a88-157">Conferência</span><span class="sxs-lookup"><span data-stu-id="49a88-157">Conference</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="49a88-158"><strong>Categoria da chamada</strong></span><span class="sxs-lookup"><span data-stu-id="49a88-158"><strong>Call category</strong></span></span></p></td>
<td><p><span data-ttu-id="49a88-p112">Indica o motivo de o CAC ter sido usado para a chamada. Selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="49a88-p112">Indicates the reason that CAC was used for the call. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="49a88-161">[Todos]</span><span class="sxs-lookup"><span data-stu-id="49a88-161">[All]</span></span></p></li>
<li><p><span data-ttu-id="49a88-162">Chamada rejeitada devido ao controle de admissão de chamadas</span><span class="sxs-lookup"><span data-stu-id="49a88-162">Call rejected because of call admission control</span></span></p></li>
<li><p><span data-ttu-id="49a88-163">Chamadas roteadas novamente por PSTN devido ao controle de admissão de chamadas</span><span class="sxs-lookup"><span data-stu-id="49a88-163">Calls rerouted through PSTN because of call admission control</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-sessions"></a><span data-ttu-id="49a88-164">Métricas para sessões ponto a ponto</span><span class="sxs-lookup"><span data-stu-id="49a88-164">Metrics for Peer-to-Peer Sessions</span></span>

<span data-ttu-id="49a88-165">A tabela a seguir lista as informações fornecidas no Relatório de Controle de Admissão de Chamadas para sessões ponto a ponto (ou seja, sessões que envolvem apenas dois participantes).</span><span class="sxs-lookup"><span data-stu-id="49a88-165">The following table lists the information provided in the Call Admission Control Report for peer-to-peer sessions (that is, sessions involving just two participants).</span></span>

### <a name="metrics-for-peer-to-peer-sessions"></a><span data-ttu-id="49a88-166">Métricas para sessões ponto a ponto</span><span class="sxs-lookup"><span data-stu-id="49a88-166">Metrics for Peer-to-Peer Sessions</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="49a88-167">Nome</span><span class="sxs-lookup"><span data-stu-id="49a88-167">Name</span></span></th>
<th><span data-ttu-id="49a88-168">Você pode classificar este item?</span><span class="sxs-lookup"><span data-stu-id="49a88-168">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="49a88-169">Descrição</span><span class="sxs-lookup"><span data-stu-id="49a88-169">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="49a88-170"><strong>Detalhe</strong></span><span class="sxs-lookup"><span data-stu-id="49a88-170"><strong>Detail</strong></span></span></p></td>
<td><p><span data-ttu-id="49a88-171">Não</span><span class="sxs-lookup"><span data-stu-id="49a88-171">No</span></span></p></td>
<td><p><span data-ttu-id="49a88-172">Quando você clica nesse item, o relatório mostra o Relatório Detalhado de Sessão Ponto a Ponto para a sessão especificada.</span><span class="sxs-lookup"><span data-stu-id="49a88-172">When you click this item, the report shows you a Peer-to-Peer Session Detail Report for the specified session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="49a88-173"><strong>De usuário</strong></span><span class="sxs-lookup"><span data-stu-id="49a88-173"><strong>From user</strong></span></span></p></td>
<td><p><span data-ttu-id="49a88-174">Sim</span><span class="sxs-lookup"><span data-stu-id="49a88-174">Yes</span></span></p></td>
<td><p><span data-ttu-id="49a88-175">Endereço SIP do usuário que iniciou a sessão.</span><span class="sxs-lookup"><span data-stu-id="49a88-175">SIP address of the user who initiated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="49a88-176"><strong>Para usuário</strong></span><span class="sxs-lookup"><span data-stu-id="49a88-176"><strong>To user</strong></span></span></p></td>
<td><p><span data-ttu-id="49a88-177">Sim</span><span class="sxs-lookup"><span data-stu-id="49a88-177">Yes</span></span></p></td>
<td><p><span data-ttu-id="49a88-178">Endereço SIP do usuário convidado para ingressar na sessão.</span><span class="sxs-lookup"><span data-stu-id="49a88-178">SIP address of the user who was invited to join the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="49a88-179"><strong>Modalidades</strong></span><span class="sxs-lookup"><span data-stu-id="49a88-179"><strong>Modalities</strong></span></span></p></td>
<td><p><span data-ttu-id="49a88-180">Sim</span><span class="sxs-lookup"><span data-stu-id="49a88-180">Yes</span></span></p></td>
<td><p><span data-ttu-id="49a88-181">Modalidades de comunicação (como áudio e vídeo) usadas durante a sessão.</span><span class="sxs-lookup"><span data-stu-id="49a88-181">Communication modalities (such as audio and video) that were used during the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="49a88-182"><strong>Hora do convite</strong></span><span class="sxs-lookup"><span data-stu-id="49a88-182"><strong>Invite time</strong></span></span></p></td>
<td><p><span data-ttu-id="49a88-183">Sim</span><span class="sxs-lookup"><span data-stu-id="49a88-183">Yes</span></span></p></td>
<td><p><span data-ttu-id="49a88-184">Data e hora de envio do convite inicial da sessão para o usuário remetente.</span><span class="sxs-lookup"><span data-stu-id="49a88-184">Date and time the initial session invitation was sent to the From user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="49a88-185"><strong>Hora da resposta</strong></span><span class="sxs-lookup"><span data-stu-id="49a88-185"><strong>Response time</strong></span></span></p></td>
<td><p><span data-ttu-id="49a88-186">Sim</span><span class="sxs-lookup"><span data-stu-id="49a88-186">Yes</span></span></p></td>
<td><p><span data-ttu-id="49a88-187">Data e hora de recebimento da aceitação do convite.</span><span class="sxs-lookup"><span data-stu-id="49a88-187">Date and time that the invitation acceptance was received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="49a88-188"><strong>Hora de término</strong></span><span class="sxs-lookup"><span data-stu-id="49a88-188"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="49a88-189">Sim</span><span class="sxs-lookup"><span data-stu-id="49a88-189">Yes</span></span></p></td>
<td><p><span data-ttu-id="49a88-190">Data e hora de encerramento da sessão.</span><span class="sxs-lookup"><span data-stu-id="49a88-190">Date and time that the session ended.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="49a88-191"><strong>ID do Diagnóstico</strong></span><span class="sxs-lookup"><span data-stu-id="49a88-191"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="49a88-192">Sim</span><span class="sxs-lookup"><span data-stu-id="49a88-192">Yes</span></span></p></td>
<td><p><span data-ttu-id="49a88-p113">Identificador exclusivo (na forma de um cabeçalho ms-diagnostics) anexado a uma mensagem SIP que fornece informações úteis para resolução de erros. Os cabeçalhos de diagnóstico são opcionais (é possível ter sessões SIP que não os incluem), e as IDs de diagnóstico são relatadas somente em sessões com algum tipo de problema.</span><span class="sxs-lookup"><span data-stu-id="49a88-p113">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors. Diagnostics headers are optional (it is possible to have SIP sessions that do not include these headers), and diagnostic IDs are reported only for sessions that experienced problems of some kind.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferencing-sessions"></a><span data-ttu-id="49a88-195">Métricas para sessões de conferência</span><span class="sxs-lookup"><span data-stu-id="49a88-195">Metrics for Conferencing Sessions</span></span>

<span data-ttu-id="49a88-196">A tabela a seguir lista as informações fornecidas no Relatório de Controle de Admissão de Chamadas para sessões de conferência (ou seja, sessões que envolvem três ou mais participantes).</span><span class="sxs-lookup"><span data-stu-id="49a88-196">The following table lists the information provided in the Call Admission Control Report for conferencing sessions (that is, sessions involving three or more participants).</span></span>

### <a name="metrics-for-conferencing-sessions"></a><span data-ttu-id="49a88-197">Métricas para sessões de conferência</span><span class="sxs-lookup"><span data-stu-id="49a88-197">Metrics for Conferencing Sessions</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="49a88-198">Nome</span><span class="sxs-lookup"><span data-stu-id="49a88-198">Name</span></span></th>
<th><span data-ttu-id="49a88-199">Você pode classificar este item?</span><span class="sxs-lookup"><span data-stu-id="49a88-199">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="49a88-200">Descrição</span><span class="sxs-lookup"><span data-stu-id="49a88-200">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="49a88-201"><strong>URI de conferência</strong></span><span class="sxs-lookup"><span data-stu-id="49a88-201"><strong>Conference URI</strong></span></span></p></td>
<td><p><span data-ttu-id="49a88-202">Sim</span><span class="sxs-lookup"><span data-stu-id="49a88-202">Yes</span></span></p></td>
<td><p><span data-ttu-id="49a88-p114">Identificador exclusivo para a conferência. Quando você clica nesse item, o relatório mostra os participantes individuais da conferência.</span><span class="sxs-lookup"><span data-stu-id="49a88-p114">Unique identifier for the conference. When you click this item, the report shows the individual conference participants.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="49a88-205"><strong>Organizador</strong></span><span class="sxs-lookup"><span data-stu-id="49a88-205"><strong>Organizer</strong></span></span></p></td>
<td><p><span data-ttu-id="49a88-206">Sim</span><span class="sxs-lookup"><span data-stu-id="49a88-206">Yes</span></span></p></td>
<td><p><span data-ttu-id="49a88-207">Endereço SIP do usuário que organizou a conferência.</span><span class="sxs-lookup"><span data-stu-id="49a88-207">SIP address of the user who organized the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="49a88-208"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="49a88-208"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="49a88-209">Sim</span><span class="sxs-lookup"><span data-stu-id="49a88-209">Yes</span></span></p></td>
<td><p><span data-ttu-id="49a88-210">Servidor de Borda usado na conferência.</span><span class="sxs-lookup"><span data-stu-id="49a88-210">Edge Server used in the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="49a88-211"><strong>Hora de início</strong></span><span class="sxs-lookup"><span data-stu-id="49a88-211"><strong>Start time</strong></span></span></p></td>
<td><p><span data-ttu-id="49a88-212">Sim</span><span class="sxs-lookup"><span data-stu-id="49a88-212">Yes</span></span></p></td>
<td><p><span data-ttu-id="49a88-213">Data e hora de início da sessão.</span><span class="sxs-lookup"><span data-stu-id="49a88-213">Date and time that the conference started.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="49a88-214"><strong>Hora de término</strong></span><span class="sxs-lookup"><span data-stu-id="49a88-214"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="49a88-215">Sim</span><span class="sxs-lookup"><span data-stu-id="49a88-215">Yes</span></span></p></td>
<td><p><span data-ttu-id="49a88-216">Data e hora em que a conferência terminou.</span><span class="sxs-lookup"><span data-stu-id="49a88-216">Date and time that the conference ended.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-individual-conference-participants"></a><span data-ttu-id="49a88-217">Métricas para participantes individuais da conferência</span><span class="sxs-lookup"><span data-stu-id="49a88-217">Metrics for Individual Conference Participants</span></span>

<span data-ttu-id="49a88-218">A tabela a seguir lista as informações fornecidas no Relatório de Controle de Admissão de Chamadas para participantes individuais da conferência.</span><span class="sxs-lookup"><span data-stu-id="49a88-218">The following table lists the information provided in the Call Admission Control Report for individual conference participants.</span></span>

### <a name="metrics-for-individual-conference-participants"></a><span data-ttu-id="49a88-219">Métricas para participantes individuais da conferência</span><span class="sxs-lookup"><span data-stu-id="49a88-219">Metrics for Individual Conference Participants</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="49a88-220">Nome</span><span class="sxs-lookup"><span data-stu-id="49a88-220">Name</span></span></th>
<th><span data-ttu-id="49a88-221">Você pode classificar este item?</span><span class="sxs-lookup"><span data-stu-id="49a88-221">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="49a88-222">Descrição</span><span class="sxs-lookup"><span data-stu-id="49a88-222">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="49a88-223"><strong>Função</strong></span><span class="sxs-lookup"><span data-stu-id="49a88-223"><strong>Role</strong></span></span></p></td>
<td><p><span data-ttu-id="49a88-224">Não</span><span class="sxs-lookup"><span data-stu-id="49a88-224">No</span></span></p></td>
<td><p><span data-ttu-id="49a88-225">Função (por exemplo, Apresentador) desempenhada pelo participante da conferência.</span><span class="sxs-lookup"><span data-stu-id="49a88-225">Role (for example, Presenter) played by the conference participant.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="49a88-226"><strong>Participante</strong></span><span class="sxs-lookup"><span data-stu-id="49a88-226"><strong>Participant</strong></span></span></p></td>
<td><p><span data-ttu-id="49a88-227">Não</span><span class="sxs-lookup"><span data-stu-id="49a88-227">No</span></span></p></td>
<td><p><span data-ttu-id="49a88-228">Endereço SIP do participante de conferência.</span><span class="sxs-lookup"><span data-stu-id="49a88-228">SIP address of the conference participant.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="49a88-229"><strong>Conectividade</strong></span><span class="sxs-lookup"><span data-stu-id="49a88-229"><strong>Connectivity</strong></span></span></p></td>
<td><p><span data-ttu-id="49a88-230">Não</span><span class="sxs-lookup"><span data-stu-id="49a88-230">No</span></span></p></td>
<td><p><span data-ttu-id="49a88-231">Conectividade de rede (normalmente Interna ou Externa) para o participante.</span><span class="sxs-lookup"><span data-stu-id="49a88-231">Network connectivity (typically From Internal or From External) for the participant.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="49a88-232"><strong>Modalidade</strong></span><span class="sxs-lookup"><span data-stu-id="49a88-232"><strong>Modality</strong></span></span></p></td>
<td><p><span data-ttu-id="49a88-233">Não</span><span class="sxs-lookup"><span data-stu-id="49a88-233">No</span></span></p></td>
<td><p><span data-ttu-id="49a88-234">Tipo de conferência (por exemplo, conferência de A/V).</span><span class="sxs-lookup"><span data-stu-id="49a88-234">Conference type (for example, A/V conferencing).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="49a88-235"><strong>Hora de ingresso</strong></span><span class="sxs-lookup"><span data-stu-id="49a88-235"><strong>Join time</strong></span></span></p></td>
<td><p><span data-ttu-id="49a88-236">Não</span><span class="sxs-lookup"><span data-stu-id="49a88-236">No</span></span></p></td>
<td><p><span data-ttu-id="49a88-237">Data e hora de ingresso do participante na conferência.</span><span class="sxs-lookup"><span data-stu-id="49a88-237">Date and time that the participant joined the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="49a88-238"><strong>Hora da saída</strong></span><span class="sxs-lookup"><span data-stu-id="49a88-238"><strong>Leave time</strong></span></span></p></td>
<td><p><span data-ttu-id="49a88-239">Não</span><span class="sxs-lookup"><span data-stu-id="49a88-239">No</span></span></p></td>
<td><p><span data-ttu-id="49a88-240">Data e hora de saída do participante da conferência.</span><span class="sxs-lookup"><span data-stu-id="49a88-240">Date and time that the participant left the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="49a88-241"><strong>ID do Diagnóstico</strong></span><span class="sxs-lookup"><span data-stu-id="49a88-241"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="49a88-242">Não</span><span class="sxs-lookup"><span data-stu-id="49a88-242">No</span></span></p></td>
<td><p><span data-ttu-id="49a88-p115">Identificador exclusivo (na forma de um cabeçalho de diagnóstico-ms) anexado a uma mensagem SIP que fornece informações úteis sobre os erros de solução de problemas. Os cabeçalhos diagnósticos são opcionais (é possível ter sessões SIP que não os incluem), e os IDs diagnósticos são relatados somente para as sessões com algum tipo de problema.</span><span class="sxs-lookup"><span data-stu-id="49a88-p115">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors. Diagnostics headers are optional (it is possible to have SIP sessions that do not include these headers), and diagnostic IDs are reported only for sessions that experienced problems of some kind.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

