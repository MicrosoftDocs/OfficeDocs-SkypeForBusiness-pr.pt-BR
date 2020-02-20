---
title: 'Lync Server 2013: relatório detalhado de sessão ponto a ponto'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Peer-to-Peer Session Detail Report
ms:assetid: 6be1d676-68f7-4a53-a72a-de73296c5571
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558659(v=OCS.15)
ms:contentKeyID: 48184416
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ca709ea2478d5ed2bdff2a80fbdc9c238d6e92cf
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153081"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="peer-to-peer-session-detail-report-in-lync-server-2013"></a><span data-ttu-id="292f5-102">Relatório detalhado de sessão ponto a ponto no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="292f5-102">Peer-to-Peer Session Detail Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="292f5-103">_**Última modificação do tópico:** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="292f5-103">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="292f5-p101">O Relatório Detalhado de Sessão Ponto a Ponto retorna informações detalhadas sobre uma sessão ponto a ponto. Por exemplo, se você selecionar uma sessão de mensagens instantâneas, o relatório informará o número de mensagens enviadas por cada um dos dois usuários na seção.</span><span class="sxs-lookup"><span data-stu-id="292f5-p101">The Peer-to-Peer Session Detail Report returns detailed information about a peer-to-peer session. For example, if you select an instant messaging session, the report will tell you the number of messages sent by each of the two users in the session.</span></span>

<div>

## <a name="accessing-the-peer-to-peer-session-detail-report"></a><span data-ttu-id="292f5-106">Acessando o Relatório Detalhado de Sessão Ponto a Ponto</span><span class="sxs-lookup"><span data-stu-id="292f5-106">Accessing the Peer-to-Peer Session Detail Report</span></span>

<span data-ttu-id="292f5-107">O Relatório Detalhado de Sessão Ponto a Ponto pode ser acessado a partir de qualquer um dos relatórios a seguir (todos os quais podem ser acessados a partir da home page Relatórios de Monitoramento):</span><span class="sxs-lookup"><span data-stu-id="292f5-107">The Peer-to-Peer Session Detail Report can be accessed from any of the following reports (all of which can be accessed from the Monitoring Reports home page):</span></span>

  - <span data-ttu-id="292f5-108">Relatório de Inventário de Telefones IP</span><span class="sxs-lookup"><span data-stu-id="292f5-108">IP Phone Inventory Report</span></span>

  - <span data-ttu-id="292f5-109">Relatório de Atividades do Usuário</span><span class="sxs-lookup"><span data-stu-id="292f5-109">User Activity Report</span></span>

  - <span data-ttu-id="292f5-110">Relatório de Controle de Admissão de Chamadas</span><span class="sxs-lookup"><span data-stu-id="292f5-110">Call Admission Control Report</span></span>

  - <span data-ttu-id="292f5-111">Relatório de Lista de Falhas</span><span class="sxs-lookup"><span data-stu-id="292f5-111">Failure List Report</span></span>

<span data-ttu-id="292f5-112">A partir do relatório de detalhes de sessão ponto a ponto, você pode acessar o [relatório de diagnóstico no Lync Server 2013](lync-server-2013-diagnostic-report.md) clicando na métrica relatório de diagnóstico (detalhes).</span><span class="sxs-lookup"><span data-stu-id="292f5-112">From within the Peer-to-Peer Session Detail Report you can access the [Diagnostic Report in Lync Server 2013](lync-server-2013-diagnostic-report.md) by clicking the Diagnostic Report (Details) metric.</span></span> <span data-ttu-id="292f5-113">Você também pode acessar o Relatório das Principais Falhas clicando em uma destas duas métricas:</span><span class="sxs-lookup"><span data-stu-id="292f5-113">You can also access the Top Failures Report by clicking either of these two metrics:</span></span>

  - <span data-ttu-id="292f5-114">Resposta</span><span class="sxs-lookup"><span data-stu-id="292f5-114">Response</span></span>

  - <span data-ttu-id="292f5-115">ID de diagnóstico</span><span class="sxs-lookup"><span data-stu-id="292f5-115">Diagnostic ID</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-peer-to-peer-session-detail-report"></a><span data-ttu-id="292f5-116">Usando o Relatório Detalhado de Sessão Ponto a Ponto da melhor maneira possível</span><span class="sxs-lookup"><span data-stu-id="292f5-116">Making the Best Use of the Peer-to-Peer session Detail Report</span></span>

<span data-ttu-id="292f5-p103">O Relatório Detalhado de Sessão Ponto a Ponto inclui um grande número de métricas, muitas das quais os administradores de sistemas podem desconhecer. Muitas vezes, porém, você pode exibir uma dica de ferramenta que oferece uma breve descrição da métrica. Para isso, basta manter o cursor do mouse sobre o rótulo da métrica.</span><span class="sxs-lookup"><span data-stu-id="292f5-p103">The Peer-to-Peer Session Detail Report includes a large number of metrics, many of which might not be familiar to system administrators. Often-times, however, you can view a tooltip that offers a brief description of that metric simply by holding your mouse over the metric label.</span></span>

<span data-ttu-id="292f5-p104">Observe que as métricas mostradas em determinado relatório dependerão do tipo de sessão ponto a ponto selecionada. Uma sessão de áudio/vídeo mostrará um conjunto de métricas diferente de uma sessão de mensagens instantâneas.</span><span class="sxs-lookup"><span data-stu-id="292f5-p104">Note that the actual metrics shown on a given report will depend on the type of peer-to-peer session you selected. An audio/video session will report a different set of metrics than an instant messaging session.</span></span>

<span data-ttu-id="292f5-121">Você também pode manter o cursor do mouse sobre as métricas Código de resposta e ID de diagnóstico para obter uma descrição desses valores:</span><span class="sxs-lookup"><span data-stu-id="292f5-121">You can also hold your mouse over the Response code and Diagnostic ID metrics in order to obtain a description of those values:</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="292f5-122">Filtros</span><span class="sxs-lookup"><span data-stu-id="292f5-122">Filters</span></span>

<span data-ttu-id="292f5-p105">Nenhum. Não é possível filtrar o relatório de Detalhes de Sessão Ponto a Ponto.</span><span class="sxs-lookup"><span data-stu-id="292f5-p105">None. You cannot filter the Peer-to-Peer Session Detail Report.</span></span>

</div>

<div>

## <a name="session-information-metrics"></a><span data-ttu-id="292f5-125">Métricas de informações da sessão</span><span class="sxs-lookup"><span data-stu-id="292f5-125">Session Information Metrics</span></span>

<span data-ttu-id="292f5-126">A tabela a seguir lista as informações fornecidas no relatório de Detalhes de Sessão Ponto a Ponto para cada sessão.</span><span class="sxs-lookup"><span data-stu-id="292f5-126">The following table lists the information provided in the Peer-to-Peer Session Detail Report for each session.</span></span>

### <a name="session-information-metrics"></a><span data-ttu-id="292f5-127">Métricas de informações da sessão</span><span class="sxs-lookup"><span data-stu-id="292f5-127">Session Information Metrics</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="292f5-128">Nome</span><span class="sxs-lookup"><span data-stu-id="292f5-128">Name</span></span></th>
<th><span data-ttu-id="292f5-129">Descrição</span><span class="sxs-lookup"><span data-stu-id="292f5-129">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="292f5-130"><strong>FQDN do pool</strong></span><span class="sxs-lookup"><span data-stu-id="292f5-130"><strong>Pool FQDN</strong></span></span></p></td>
<td><p><span data-ttu-id="292f5-131">Nome de domínio totalmente qualificado (FQDN) do pool de Registradores ou Servidor de Borda envolvido na sessão.</span><span class="sxs-lookup"><span data-stu-id="292f5-131">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server involved in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="292f5-132"><strong>Hora do convite</strong></span><span class="sxs-lookup"><span data-stu-id="292f5-132"><strong>Invite time</strong></span></span></p></td>
<td><p><span data-ttu-id="292f5-133">Data e hora em que o convite de sessão foi originalmente enviado.</span><span class="sxs-lookup"><span data-stu-id="292f5-133">Date and time the session invitation was originally sent.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="292f5-134"><strong>Hora da resposta</strong></span><span class="sxs-lookup"><span data-stu-id="292f5-134"><strong>Response time</strong></span></span></p></td>
<td><p><span data-ttu-id="292f5-135">Data e hora em que a aceitação do convite foi recebida.</span><span class="sxs-lookup"><span data-stu-id="292f5-135">Date and time that the invitation acceptance was received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="292f5-136"><strong>Do usuário</strong></span><span class="sxs-lookup"><span data-stu-id="292f5-136"><strong>From user</strong></span></span></p></td>
<td><p><span data-ttu-id="292f5-137">Endereço SIP do usuário que iniciou a sessão.</span><span class="sxs-lookup"><span data-stu-id="292f5-137">SIP address of the user who initiated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="292f5-138"><strong>Do agente usuário</strong></span><span class="sxs-lookup"><span data-stu-id="292f5-138"><strong>From user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="292f5-139">Software usado pelo ponto de extremidade do usuário que iniciou a sessão.</span><span class="sxs-lookup"><span data-stu-id="292f5-139">Software used by the endpoint of the user who initiated the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="292f5-140"><strong>É Usuário interno de origem</strong></span><span class="sxs-lookup"><span data-stu-id="292f5-140"><strong>Is From user internal</strong></span></span></p></td>
<td><p><span data-ttu-id="292f5-141">Indica se o usuário que iniciou a sessão estava conectado à rede interna.</span><span class="sxs-lookup"><span data-stu-id="292f5-141">Indicates whether the user who initiated the session was logged on to the internal network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="292f5-142"><strong>É Usuário de origem integrado ao telefone de mesa</strong></span><span class="sxs-lookup"><span data-stu-id="292f5-142"><strong>Is From user integrated with desk phone</strong></span></span></p></td>
<td><p><span data-ttu-id="292f5-143">Indica se o ponto de extremidade usado pelo usuário que iniciou a sessão está integrado ao seu telefone de mesa.</span><span class="sxs-lookup"><span data-stu-id="292f5-143">Indicates whether the endpoint used by the user who initiated the session is integrated with his or her desktop phone.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="292f5-144"><strong>Prioridade da Sessão</strong></span><span class="sxs-lookup"><span data-stu-id="292f5-144"><strong>Session Priority</strong></span></span></p></td>
<td><p><span data-ttu-id="292f5-p106">Prioridade atribuída à sessão. As prioridades válidas são: Desconhecida; Não Urgente; Normal; Urgente; e Emergência.</span><span class="sxs-lookup"><span data-stu-id="292f5-p106">Priority assigned to the session. Valid priorities are: Unknown; Non-Urgent; Normal; Urgent; and Emergency.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="292f5-147"><strong>Código de resposta</strong></span><span class="sxs-lookup"><span data-stu-id="292f5-147"><strong>Response code</strong></span></span></p></td>
<td><p><span data-ttu-id="292f5-148">Código de resposta SIP enviado quando a sessão falhou.</span><span class="sxs-lookup"><span data-stu-id="292f5-148">SIP response code sent when the session failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="292f5-149"><strong>Front-End</strong>.</span><span class="sxs-lookup"><span data-stu-id="292f5-149"><strong>Front end</strong></span></span></p></td>
<td><p><span data-ttu-id="292f5-150">Nome do Servidor Front-End usado na conferência.</span><span class="sxs-lookup"><span data-stu-id="292f5-150">Name of the Front End Server used in the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="292f5-151"><strong>Hora da captura</strong></span><span class="sxs-lookup"><span data-stu-id="292f5-151"><strong>Capture time</strong></span></span></p></td>
<td><p><span data-ttu-id="292f5-152">Data e hora em que a sessão de informações foi gravada.</span><span class="sxs-lookup"><span data-stu-id="292f5-152">Date and time that the session information was recorded.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="292f5-153"><strong>Hora final</strong></span><span class="sxs-lookup"><span data-stu-id="292f5-153"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="292f5-154">Data e hora em que a sessão foi encerrada.</span><span class="sxs-lookup"><span data-stu-id="292f5-154">Date and time the session ended.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="292f5-155"><strong>Para o usuário</strong></span><span class="sxs-lookup"><span data-stu-id="292f5-155"><strong>To user</strong></span></span></p></td>
<td><p><span data-ttu-id="292f5-156">Endereço SIP do usuário que foi convidado para a sessão.</span><span class="sxs-lookup"><span data-stu-id="292f5-156">SIP address of the user who was invited to the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="292f5-157"><strong>Para o agente do usuário</strong></span><span class="sxs-lookup"><span data-stu-id="292f5-157"><strong>To user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="292f5-158">Software usado pelo ponto de extremidade do usuário que foi convidado para a sessão.</span><span class="sxs-lookup"><span data-stu-id="292f5-158">Software used by the endpoint of the user who was invited to the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="292f5-159"><strong>É Usuário interno de destino</strong></span><span class="sxs-lookup"><span data-stu-id="292f5-159"><strong>Is To user internal</strong></span></span></p></td>
<td><p><span data-ttu-id="292f5-160">Indica se o usuário que foi convidado para a sessão estava conectado à rede interna.</span><span class="sxs-lookup"><span data-stu-id="292f5-160">Indicates whether the user who was invited to the session was logged on to the internal network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="292f5-161"><strong>É Usuário de destino integrado ao telefone de mesa</strong></span><span class="sxs-lookup"><span data-stu-id="292f5-161"><strong>Is To user integrated with desk phone</strong></span></span></p></td>
<td><p><span data-ttu-id="292f5-162">Indica se o ponto de extremidade usado pelo usuário que foi convidado para a sessão está integrado ao seu telefone de mesa.</span><span class="sxs-lookup"><span data-stu-id="292f5-162">Indicates whether the endpoint used by the user who was invited to the session is integrated with his or her desktop phone.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="292f5-163"><strong>É sessão repetida</strong></span><span class="sxs-lookup"><span data-stu-id="292f5-163"><strong>Is retried session</strong></span></span></p></td>
<td><p><span data-ttu-id="292f5-164">Indica se a sessão é uma tentativa para repetir uma sessão que falhou anteriormente.</span><span class="sxs-lookup"><span data-stu-id="292f5-164">Indicates whether the session is an attempt to retry a session that previously failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="292f5-165"><strong>ID de diagnóstico</strong></span><span class="sxs-lookup"><span data-stu-id="292f5-165"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="292f5-p107">Identificador exclusivo (no formato de um cabeçalho ms-diagnostics) anexado a uma mensagem SIP que frequentemente oferece informações úteis para resolução de erros. Mantenha o mouse sobre o número de identificação para exibir informações adicionais sobre essa identificação.</span><span class="sxs-lookup"><span data-stu-id="292f5-p107">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors. Hold the mouse over the ID number to view additional information about that ID.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-modalities"></a><span data-ttu-id="292f5-168">Métricas para modalidades</span><span class="sxs-lookup"><span data-stu-id="292f5-168">Metrics for Modalities</span></span>

<span data-ttu-id="292f5-169">A tabela a seguir lista as informações fornecidas no relatório de Detalhes de Sessão Ponto a Ponto para cada sessão de modalidade.</span><span class="sxs-lookup"><span data-stu-id="292f5-169">The following table lists the information provided in the Peer-to-Peer Session Detail Report for each session modality.</span></span>

### <a name="metrics-for-modalities"></a><span data-ttu-id="292f5-170">Métricas para modalidades</span><span class="sxs-lookup"><span data-stu-id="292f5-170">Metrics for Modalities</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="292f5-171">Nome</span><span class="sxs-lookup"><span data-stu-id="292f5-171">Name</span></span></th>
<th><span data-ttu-id="292f5-172">É possível classificar este item?</span><span class="sxs-lookup"><span data-stu-id="292f5-172">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="292f5-173">Descrição</span><span class="sxs-lookup"><span data-stu-id="292f5-173">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="292f5-174"><strong>Modalidades</strong></span><span class="sxs-lookup"><span data-stu-id="292f5-174"><strong>Modalities</strong></span></span></p></td>
<td><p><span data-ttu-id="292f5-175">Não</span><span class="sxs-lookup"><span data-stu-id="292f5-175">No</span></span></p></td>
<td><p><span data-ttu-id="292f5-p108">Modalidades usadas na sessão. Por exemplo, mensagens instantâneas ou transferência de arquivo.</span><span class="sxs-lookup"><span data-stu-id="292f5-p108">Modalities used in the session. For example, instant messaging (IM) or file transfer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="292f5-178"><strong>Mensagens do usuário de origem</strong></span><span class="sxs-lookup"><span data-stu-id="292f5-178"><strong>From user messages</strong></span></span></p></td>
<td><p><span data-ttu-id="292f5-179">Não</span><span class="sxs-lookup"><span data-stu-id="292f5-179">No</span></span></p></td>
<td><p><span data-ttu-id="292f5-180">Número de mensagens enviadas pelo usuário que iniciou a sessão.</span><span class="sxs-lookup"><span data-stu-id="292f5-180">Number of messages sent by the user who initiated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="292f5-181"><strong>Mensagens do usuário de destino</strong></span><span class="sxs-lookup"><span data-stu-id="292f5-181"><strong>To user messages</strong></span></span></p></td>
<td><p><span data-ttu-id="292f5-182">Não</span><span class="sxs-lookup"><span data-stu-id="292f5-182">No</span></span></p></td>
<td><p><span data-ttu-id="292f5-183">Número de mensagens enviadas pelo usuário que foi convidado para a sessão.</span><span class="sxs-lookup"><span data-stu-id="292f5-183">Number of messages sent by the user who was invited to join the session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-diagnostic-reports"></a><span data-ttu-id="292f5-184">Métricas para relatórios de diagnóstico</span><span class="sxs-lookup"><span data-stu-id="292f5-184">Metrics for Diagnostic Reports</span></span>

<span data-ttu-id="292f5-185">A tabela a seguir lista as informações fornecidas no relatório de Detalhes de Sessão Ponto a Ponto para cada relatório de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="292f5-185">The following table lists the information provided in the Peer-to-Peer Session Detail Report for each diagnostic report.</span></span>

### <a name="metrics-for-diagnostic-reports"></a><span data-ttu-id="292f5-186">Métricas para relatórios de diagnóstico</span><span class="sxs-lookup"><span data-stu-id="292f5-186">Metrics for Diagnostic Reports</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="292f5-187">Nome</span><span class="sxs-lookup"><span data-stu-id="292f5-187">Name</span></span></th>
<th><span data-ttu-id="292f5-188">É possível classificar este item?</span><span class="sxs-lookup"><span data-stu-id="292f5-188">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="292f5-189">Descrição</span><span class="sxs-lookup"><span data-stu-id="292f5-189">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="292f5-190"><strong>Ver os detalhes</strong></span><span class="sxs-lookup"><span data-stu-id="292f5-190"><strong>Detail</strong></span></span></p></td>
<td><p><span data-ttu-id="292f5-191">Não</span><span class="sxs-lookup"><span data-stu-id="292f5-191">No</span></span></p></td>
<td><p><span data-ttu-id="292f5-192">Quando você clica nesse item, o relatório mostra o Relatório de Diagnóstico da sessão.</span><span class="sxs-lookup"><span data-stu-id="292f5-192">When you click this item, the report shows the Diagnostic Report for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="292f5-193"><strong>Hora do relatório</strong></span><span class="sxs-lookup"><span data-stu-id="292f5-193"><strong>Report time</strong></span></span></p></td>
<td><p><span data-ttu-id="292f5-194">Não</span><span class="sxs-lookup"><span data-stu-id="292f5-194">No</span></span></p></td>
<td><p><span data-ttu-id="292f5-195">Data e hora em que o relatório foi gravado.</span><span class="sxs-lookup"><span data-stu-id="292f5-195">Date and time the report was recorded.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="292f5-196"><strong>Solicitação</strong></span><span class="sxs-lookup"><span data-stu-id="292f5-196"><strong>Request</strong></span></span></p></td>
<td><p><span data-ttu-id="292f5-197">Não</span><span class="sxs-lookup"><span data-stu-id="292f5-197">No</span></span></p></td>
<td><p><span data-ttu-id="292f5-p109">Tipo de solicitação SIP. Por exemplo, INVITE ou BYE.</span><span class="sxs-lookup"><span data-stu-id="292f5-p109">SIP request type. For example, INVITE or BYE.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="292f5-200"><strong>ID de diagnóstico</strong></span><span class="sxs-lookup"><span data-stu-id="292f5-200"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="292f5-201">Não</span><span class="sxs-lookup"><span data-stu-id="292f5-201">No</span></span></p></td>
<td><p><span data-ttu-id="292f5-202">Identificador exclusivo (no formato de um cabeçalho ms-diagnostics) anexado a uma mensagem SIP que frequentemente oferece informações úteis para resolução de erros.</span><span class="sxs-lookup"><span data-stu-id="292f5-202">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="292f5-203"><strong>Tipo de conteúdo</strong></span><span class="sxs-lookup"><span data-stu-id="292f5-203"><strong>Content type</strong></span></span></p></td>
<td><p><span data-ttu-id="292f5-204">Não</span><span class="sxs-lookup"><span data-stu-id="292f5-204">No</span></span></p></td>
<td><p><span data-ttu-id="292f5-p110">Tipo de conteúdo de mídia usado na conferência. Por exemplo, um tipo de conteúdo comum é Application/sdp. O protocolo SDP  é um protocolo padrão de Internet usado para comunicados de sessão, convites de sessão e outras formas de início de sessão multimídia.</span><span class="sxs-lookup"><span data-stu-id="292f5-p110">Type of media content used in the conference. For example, a common content type is Application/sdp. Session Description Protocol (SDP) is a standard Internet protocol used for session announcements, session invitations, and other forms of multimedia session initiation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="292f5-208"><strong>Relatado por</strong></span><span class="sxs-lookup"><span data-stu-id="292f5-208"><strong>Reported by</strong></span></span></p></td>
<td><p><span data-ttu-id="292f5-209">Não</span><span class="sxs-lookup"><span data-stu-id="292f5-209">No</span></span></p></td>
<td><p><span data-ttu-id="292f5-210">Computador (isso é, o cliente ou servidor) que relatou o problema.</span><span class="sxs-lookup"><span data-stu-id="292f5-210">Computer (that is, client or server) that reported the problem.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

