---
title: 'Lync Server 2013: relatório detalhado de conferência'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conference Detail Report
ms:assetid: 1d61cd81-dcfe-40b4-9a41-a73b038bc216
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204728(v=OCS.15)
ms:contentKeyID: 48183565
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dce868d90d2811b36a4f11c159b4e7d9d29b5ffa
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007880"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conference-detail-report-in-lync-server-2013"></a><span data-ttu-id="48749-102">Relatório de detalhes de conferência no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="48749-102">Conference Detail Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="48749-103">_**Última modificação do tópico:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="48749-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="48749-p101">O Relatório de Detalhe da Conferência oferece informações detalhadas sobre todos os usuários que participaram de uma conferência. Por exemplo, você pode ver tal informação como a data e hora que um usuário participou da conferência, a data e hora que o usuário saiu da conferência e o agente do usuário do ponto de extremidade que foi usado para conectar o usuário à conferência. Também é possível ver informações da função do usuário em cada conferência (por exemplo, Apresentador ou Participante). Talvez, o mais importante, você pode ver rapidamente quais usuários participaram com sucesso e concluíram a conferência e quais usuários não puderam participar e concluir a conferência.</span><span class="sxs-lookup"><span data-stu-id="48749-p101">The Conference Detail Report provides detailed information about all the users who participated in a conference. For example, you can see such information as the date and time that a user joined the conference, the date and time that the user left the conference, and the user agent of the endpoint that was used to connect that user to the conference. You can also see information the user's role in each conference (for example, Presenter or Attendee). Perhaps most important, you get quickly see which users successfully join and complete the conference, and which users were not able to successfully join and complete the conference.</span></span>

<div>

## <a name="accessing-the-conference-detail-report"></a><span data-ttu-id="48749-108">Acessar o Relatório de Detalhe da Conferência</span><span class="sxs-lookup"><span data-stu-id="48749-108">Accessing the Conference Detail Report</span></span>

<span data-ttu-id="48749-109">O Relatório de Detalhe da Conferência pode ser acessado pelos seguintes relatórios:</span><span class="sxs-lookup"><span data-stu-id="48749-109">The Conference Detail Report can be accessed from the following reports:</span></span>

  - <span data-ttu-id="48749-110">O [relatório de controle de admissão de chamadas no Lync Server 2013](lync-server-2013-call-admission-control-report.md) (clicando na métrica detalhe de uma conferência)</span><span class="sxs-lookup"><span data-stu-id="48749-110">The [Call Admission Control Report in Lync Server 2013](lync-server-2013-call-admission-control-report.md) (by clicking the Detail metric for a conference)</span></span>

  - <span data-ttu-id="48749-111">O [relatório de lista de falhas no Lync Server 2013](lync-server-2013-failure-list-report.md) (clicando na métrica conferência)</span><span class="sxs-lookup"><span data-stu-id="48749-111">The [Failure List Report in Lync Server 2013](lync-server-2013-failure-list-report.md) (by clicking the Conference metric)</span></span>

  - <span data-ttu-id="48749-112">O [relatório de atividades do usuário no Lync Server 2013](lync-server-2013-user-activity-report.md) (clicando na métrica URI da conferência)</span><span class="sxs-lookup"><span data-stu-id="48749-112">The [User Activity Report in Lync Server 2013](lync-server-2013-user-activity-report.md) (by clicking the Conference URI metric)</span></span>

<span data-ttu-id="48749-113">No relatório de detalhe da conferência, é possível acessar o [relatório de diagnóstico no Lync Server 2013](lync-server-2013-diagnostic-report.md) clicando na métrica relatório de diagnóstico (detalhe).</span><span class="sxs-lookup"><span data-stu-id="48749-113">From the Conference Detail Report you can access the [Diagnostic Report in Lync Server 2013](lync-server-2013-diagnostic-report.md) by clicking the Diagnostic Report (Detail) metric.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="48749-114">Filtros</span><span class="sxs-lookup"><span data-stu-id="48749-114">Filters</span></span>

<span data-ttu-id="48749-p102">Nenhum. Você não pode filtrar o Relatório de Detalhe da Conferência.</span><span class="sxs-lookup"><span data-stu-id="48749-p102">None. You cannot filter on the Conference Detail Report.</span></span>

</div>

<div>

## <a name="metrics"></a><span data-ttu-id="48749-117">Métricas</span><span class="sxs-lookup"><span data-stu-id="48749-117">Metrics</span></span>

<span data-ttu-id="48749-118">A tabela a seguir lista as informações fornecidas na seção Informação da Conferência do Relatório de Detalhe da Conferência.</span><span class="sxs-lookup"><span data-stu-id="48749-118">The following table lists the information provided in the Conference Information section of the Conference Detail Report.</span></span>

### <a name="conference-information-metrics"></a><span data-ttu-id="48749-119">Métricas de Informação da Conferência</span><span class="sxs-lookup"><span data-stu-id="48749-119">Conference Information Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="48749-120">Nome</span><span class="sxs-lookup"><span data-stu-id="48749-120">Name</span></span></th>
<th><span data-ttu-id="48749-121">É possível classificar este item?</span><span class="sxs-lookup"><span data-stu-id="48749-121">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="48749-122">Descrição</span><span class="sxs-lookup"><span data-stu-id="48749-122">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="48749-123"><strong>URI de Conferência</strong></span><span class="sxs-lookup"><span data-stu-id="48749-123"><strong>Conference URI</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="48749-p103">URI atribuído à conferência. Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="48749-p103">URI assigned to the conference. For example:</span></span></p>
<p><span data-ttu-id="48749-126">SIP: kmyer@litwareinc. com; GRUU; opaco = App: conf: Focus: ID: drg2y8v4</span><span class="sxs-lookup"><span data-stu-id="48749-126">sip:kmyer@litwareinc.com;gruu;opaque=app:conf:focus:id:drg2y8v4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48749-127"><strong>FQDN do Pool</strong></span><span class="sxs-lookup"><span data-stu-id="48749-127"><strong>Pool FQDN</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="48749-128">Nome de domínio totalmente qualificado do pool do Registrador ou Servidor de Borda envolvido em uma sessão.</span><span class="sxs-lookup"><span data-stu-id="48749-128">Fully-qualified domain name of the Registrar pool or Edge Server involved in a session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="48749-129"><strong>Hora inicial</strong></span><span class="sxs-lookup"><span data-stu-id="48749-129"><strong>Start time</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="48749-130">Data e hora que a conferência iniciou.</span><span class="sxs-lookup"><span data-stu-id="48749-130">Date and time that the conference started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48749-131"><strong>Organizador</strong></span><span class="sxs-lookup"><span data-stu-id="48749-131"><strong>Organizer</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="48749-132">Endereço SIP do usuário que organizou a conferência.</span><span class="sxs-lookup"><span data-stu-id="48749-132">SIP address of the user who organized the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="48749-133"><strong>Hora final</strong></span><span class="sxs-lookup"><span data-stu-id="48749-133"><strong>End time</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="48749-134">Data e hora que a conferência terminou.</span><span class="sxs-lookup"><span data-stu-id="48749-134">Date and time that the conference ended.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="48749-135">A tabela a seguir lista a informação oferecida na Seção de Participação da Conferência do Relatório de Detalhe da Conferência.</span><span class="sxs-lookup"><span data-stu-id="48749-135">The following table lists the information provided in the Conference Participation Section of the Conference Detail Report.</span></span>

### <a name="conference-participation-metrics"></a><span data-ttu-id="48749-136">Métricas de Participação da Conferência</span><span class="sxs-lookup"><span data-stu-id="48749-136">Conference Participation Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="48749-137">Nome</span><span class="sxs-lookup"><span data-stu-id="48749-137">Name</span></span></th>
<th><span data-ttu-id="48749-138">É possível classificar este item?</span><span class="sxs-lookup"><span data-stu-id="48749-138">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="48749-139">Descrição</span><span class="sxs-lookup"><span data-stu-id="48749-139">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="48749-140"><strong>Usuário</strong></span><span class="sxs-lookup"><span data-stu-id="48749-140"><strong>User</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="48749-141">Endereço SIP do usuário que participou da conferência.</span><span class="sxs-lookup"><span data-stu-id="48749-141">SIP address of the user who participated in the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48749-142"><strong>Função</strong></span><span class="sxs-lookup"><span data-stu-id="48749-142"><strong>Role</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="48749-143">Função (por exemplo, Apresentador) do participante da conferência.</span><span class="sxs-lookup"><span data-stu-id="48749-143">Role (for example, Presenter) played by the conference participant.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="48749-144"><strong>Conectividade</strong></span><span class="sxs-lookup"><span data-stu-id="48749-144"><strong>Connectivity</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="48749-145">Conectividade de rede (geralmente Externa ou Interna) do participante.</span><span class="sxs-lookup"><span data-stu-id="48749-145">Network connectivity (typically From Internal or From External) for the participant.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48749-146">Hora de participação</span><span class="sxs-lookup"><span data-stu-id="48749-146">Join time</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="48749-147">Data e hora de ingresso do participante na conferência.</span><span class="sxs-lookup"><span data-stu-id="48749-147">Date and time that the participant joined the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="48749-148"><strong>Hora de saída</strong></span><span class="sxs-lookup"><span data-stu-id="48749-148"><strong>Leave time</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="48749-149">Data e hora que o participante saiu da conferência.</span><span class="sxs-lookup"><span data-stu-id="48749-149">Date and time that the participant left the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48749-150"><strong>Agente do usuário</strong></span><span class="sxs-lookup"><span data-stu-id="48749-150"><strong>User agent</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="48749-151">Identificador do software usado pelo ponto de extremidade do participante.</span><span class="sxs-lookup"><span data-stu-id="48749-151">Identifier for the software used by the participant’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="48749-152"><strong>Relatórios de diagnóstico</strong></span><span class="sxs-lookup"><span data-stu-id="48749-152"><strong>Diagnostic reports</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="48749-p104">Oferece informação de resolução de problemas e diagnóstico. Incluindo códigos de resposta SIP, cabeçalhos de diagnóstico, hora de participação da conferência e IDs de diagnósticos para sessões em falha.</span><span class="sxs-lookup"><span data-stu-id="48749-p104">Provides diagnostic and troubleshooting information. Including SIP response codes, diagnostic headers, conference join times, and diagnostic IDs for failed sessions.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="48749-155">A tabela a seguir lista as informações fornecidas na seção modalidades de conferência do relatório de detalhe da conferência.</span><span class="sxs-lookup"><span data-stu-id="48749-155">The following table lists the information provided in the Conference Modalities section of the Conference Detail Report.</span></span>

### <a name="conference-modalities-metrics"></a><span data-ttu-id="48749-156">Métricas das Modalidades da Conferência</span><span class="sxs-lookup"><span data-stu-id="48749-156">Conference Modalities Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="48749-157">Nome</span><span class="sxs-lookup"><span data-stu-id="48749-157">Name</span></span></th>
<th><span data-ttu-id="48749-158">É possível classificar este item?</span><span class="sxs-lookup"><span data-stu-id="48749-158">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="48749-159">Descrição</span><span class="sxs-lookup"><span data-stu-id="48749-159">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="48749-160"><strong>Usuário</strong></span><span class="sxs-lookup"><span data-stu-id="48749-160"><strong>User</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="48749-161">Endereço SIP do usuário que participou da conferência.</span><span class="sxs-lookup"><span data-stu-id="48749-161">SIP address of the user who participated in the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48749-162"><strong>Hora de participação</strong></span><span class="sxs-lookup"><span data-stu-id="48749-162"><strong>Join time</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="48749-163">Data e hora que o participante entrou na conferência.</span><span class="sxs-lookup"><span data-stu-id="48749-163">Date and time that the participant joined the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="48749-164"><strong>Hora de saída</strong></span><span class="sxs-lookup"><span data-stu-id="48749-164"><strong>Leave time</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="48749-165">Data e hora que um participante deixou a conferência.</span><span class="sxs-lookup"><span data-stu-id="48749-165">Date and time that a participant left the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48749-166"><strong>URI do servidor de conferência</strong></span><span class="sxs-lookup"><span data-stu-id="48749-166"><strong>Conferencing server URI</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="48749-167">URI para o servidor de Conferência usado na conferência.</span><span class="sxs-lookup"><span data-stu-id="48749-167">URI for the Conferencing server used in the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="48749-168"><strong>Relatórios de diagnóstico</strong></span><span class="sxs-lookup"><span data-stu-id="48749-168"><strong>Diagnostic reports</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="48749-p105">Oferece informação de resolução de problemas e diagnóstico. Incluindo códigos de resposta SIP, cabeçalhos de diagnóstico, hora de participação da conferência e IDs de diagnósticos para sessões em falha.</span><span class="sxs-lookup"><span data-stu-id="48749-p105">Provides diagnostic and troubleshooting information. Including SIP response codes, diagnostic headers, conference join times, and diagnostic IDs for failed sessions.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

