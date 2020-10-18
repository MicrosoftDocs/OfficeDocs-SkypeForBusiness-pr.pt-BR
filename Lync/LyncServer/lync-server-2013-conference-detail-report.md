---
title: 'Lync Server 2013: relatório detalhado de conferência'
description: 'Lync Server 2013: relatório de detalhes de conferência.'
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
ms.openlocfilehash: 07c50b545f4a9ee3308a840fc2aa5a15e617a5bd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577627"
---
# <a name="conference-detail-report-in-lync-server-2013"></a><span data-ttu-id="d4b22-103">Relatório de detalhes de conferência no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d4b22-103">Conference Detail Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d4b22-104">_**Última modificação do tópico:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="d4b22-104">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="d4b22-p101">O Relatório de Detalhe da Conferência oferece informações detalhadas sobre todos os usuários que participaram de uma conferência. Por exemplo, você pode ver tal informação como a data e hora que um usuário participou da conferência, a data e hora que o usuário saiu da conferência e o agente do usuário do ponto de extremidade que foi usado para conectar o usuário à conferência. Também é possível ver informações da função do usuário em cada conferência (por exemplo, Apresentador ou Participante). Talvez, o mais importante, você pode ver rapidamente quais usuários participaram com sucesso e concluíram a conferência e quais usuários não puderam participar e concluir a conferência.</span><span class="sxs-lookup"><span data-stu-id="d4b22-p101">The Conference Detail Report provides detailed information about all the users who participated in a conference. For example, you can see such information as the date and time that a user joined the conference, the date and time that the user left the conference, and the user agent of the endpoint that was used to connect that user to the conference. You can also see information the user's role in each conference (for example, Presenter or Attendee). Perhaps most important, you get quickly see which users successfully join and complete the conference, and which users were not able to successfully join and complete the conference.</span></span>

<div>

## <a name="accessing-the-conference-detail-report"></a><span data-ttu-id="d4b22-109">Acessar o Relatório de Detalhe da Conferência</span><span class="sxs-lookup"><span data-stu-id="d4b22-109">Accessing the Conference Detail Report</span></span>

<span data-ttu-id="d4b22-110">O Relatório de Detalhe da Conferência pode ser acessado pelos seguintes relatórios:</span><span class="sxs-lookup"><span data-stu-id="d4b22-110">The Conference Detail Report can be accessed from the following reports:</span></span>

  - <span data-ttu-id="d4b22-111">O [relatório de controle de admissão de chamadas no Lync Server 2013](lync-server-2013-call-admission-control-report.md) (clicando na métrica detalhe de uma conferência)</span><span class="sxs-lookup"><span data-stu-id="d4b22-111">The [Call Admission Control Report in Lync Server 2013](lync-server-2013-call-admission-control-report.md) (by clicking the Detail metric for a conference)</span></span>

  - <span data-ttu-id="d4b22-112">O [relatório de lista de falhas no Lync Server 2013](lync-server-2013-failure-list-report.md) (clicando na métrica conferência)</span><span class="sxs-lookup"><span data-stu-id="d4b22-112">The [Failure List Report in Lync Server 2013](lync-server-2013-failure-list-report.md) (by clicking the Conference metric)</span></span>

  - <span data-ttu-id="d4b22-113">O [relatório de atividades do usuário no Lync Server 2013](lync-server-2013-user-activity-report.md) (clicando na métrica URI da conferência)</span><span class="sxs-lookup"><span data-stu-id="d4b22-113">The [User Activity Report in Lync Server 2013](lync-server-2013-user-activity-report.md) (by clicking the Conference URI metric)</span></span>

<span data-ttu-id="d4b22-114">No relatório de detalhe da conferência, é possível acessar o [relatório de diagnóstico no Lync Server 2013](lync-server-2013-diagnostic-report.md) clicando na métrica relatório de diagnóstico (detalhe).</span><span class="sxs-lookup"><span data-stu-id="d4b22-114">From the Conference Detail Report you can access the [Diagnostic Report in Lync Server 2013](lync-server-2013-diagnostic-report.md) by clicking the Diagnostic Report (Detail) metric.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="d4b22-115">Filtros</span><span class="sxs-lookup"><span data-stu-id="d4b22-115">Filters</span></span>

<span data-ttu-id="d4b22-p102">Nenhum. Você não pode filtrar o Relatório de Detalhe da Conferência.</span><span class="sxs-lookup"><span data-stu-id="d4b22-p102">None. You cannot filter on the Conference Detail Report.</span></span>

</div>

<div>

## <a name="metrics"></a><span data-ttu-id="d4b22-118">Métrica</span><span class="sxs-lookup"><span data-stu-id="d4b22-118">Metrics</span></span>

<span data-ttu-id="d4b22-119">A tabela a seguir lista as informações fornecidas na seção Informação da Conferência do Relatório de Detalhe da Conferência.</span><span class="sxs-lookup"><span data-stu-id="d4b22-119">The following table lists the information provided in the Conference Information section of the Conference Detail Report.</span></span>

### <a name="conference-information-metrics"></a><span data-ttu-id="d4b22-120">Métricas de Informação da Conferência</span><span class="sxs-lookup"><span data-stu-id="d4b22-120">Conference Information Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d4b22-121">Nome</span><span class="sxs-lookup"><span data-stu-id="d4b22-121">Name</span></span></th>
<th><span data-ttu-id="d4b22-122">É possível classificar este item?</span><span class="sxs-lookup"><span data-stu-id="d4b22-122">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="d4b22-123">Descrição</span><span class="sxs-lookup"><span data-stu-id="d4b22-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d4b22-124"><strong>URI de Conferência</strong></span><span class="sxs-lookup"><span data-stu-id="d4b22-124"><strong>Conference URI</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d4b22-p103">URI atribuído à conferência. Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="d4b22-p103">URI assigned to the conference. For example:</span></span></p>
<p><span data-ttu-id="d4b22-127">SIP: kmyer@litwareinc. com; GRUU; opaco = App: conf: Focus: ID: drg2y8v4</span><span class="sxs-lookup"><span data-stu-id="d4b22-127">sip:kmyer@litwareinc.com;gruu;opaque=app:conf:focus:id:drg2y8v4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d4b22-128"><strong>FQDN do Pool</strong></span><span class="sxs-lookup"><span data-stu-id="d4b22-128"><strong>Pool FQDN</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d4b22-129">Nome de domínio totalmente qualificado do pool do Registrador ou Servidor de Borda envolvido em uma sessão.</span><span class="sxs-lookup"><span data-stu-id="d4b22-129">Fully-qualified domain name of the Registrar pool or Edge Server involved in a session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d4b22-130"><strong>Hora inicial</strong></span><span class="sxs-lookup"><span data-stu-id="d4b22-130"><strong>Start time</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d4b22-131">Data e hora que a conferência iniciou.</span><span class="sxs-lookup"><span data-stu-id="d4b22-131">Date and time that the conference started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d4b22-132"><strong>Organizador</strong></span><span class="sxs-lookup"><span data-stu-id="d4b22-132"><strong>Organizer</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d4b22-133">Endereço SIP do usuário que organizou a conferência.</span><span class="sxs-lookup"><span data-stu-id="d4b22-133">SIP address of the user who organized the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d4b22-134"><strong>Hora final</strong></span><span class="sxs-lookup"><span data-stu-id="d4b22-134"><strong>End time</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d4b22-135">Data e hora que a conferência terminou.</span><span class="sxs-lookup"><span data-stu-id="d4b22-135">Date and time that the conference ended.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="d4b22-136">A tabela a seguir lista a informação oferecida na Seção de Participação da Conferência do Relatório de Detalhe da Conferência.</span><span class="sxs-lookup"><span data-stu-id="d4b22-136">The following table lists the information provided in the Conference Participation Section of the Conference Detail Report.</span></span>

### <a name="conference-participation-metrics"></a><span data-ttu-id="d4b22-137">Métricas de Participação da Conferência</span><span class="sxs-lookup"><span data-stu-id="d4b22-137">Conference Participation Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d4b22-138">Nome</span><span class="sxs-lookup"><span data-stu-id="d4b22-138">Name</span></span></th>
<th><span data-ttu-id="d4b22-139">É possível classificar este item?</span><span class="sxs-lookup"><span data-stu-id="d4b22-139">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="d4b22-140">Descrição</span><span class="sxs-lookup"><span data-stu-id="d4b22-140">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d4b22-141"><strong>Usuário</strong></span><span class="sxs-lookup"><span data-stu-id="d4b22-141"><strong>User</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d4b22-142">Endereço SIP do usuário que participou da conferência.</span><span class="sxs-lookup"><span data-stu-id="d4b22-142">SIP address of the user who participated in the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d4b22-143"><strong>Função</strong></span><span class="sxs-lookup"><span data-stu-id="d4b22-143"><strong>Role</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d4b22-144">Função (por exemplo, Apresentador) do participante da conferência.</span><span class="sxs-lookup"><span data-stu-id="d4b22-144">Role (for example, Presenter) played by the conference participant.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d4b22-145"><strong>Conectividade</strong></span><span class="sxs-lookup"><span data-stu-id="d4b22-145"><strong>Connectivity</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d4b22-146">Conectividade de rede (geralmente Externa ou Interna) do participante.</span><span class="sxs-lookup"><span data-stu-id="d4b22-146">Network connectivity (typically From Internal or From External) for the participant.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d4b22-147">Hora de participação</span><span class="sxs-lookup"><span data-stu-id="d4b22-147">Join time</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d4b22-148">Data e hora que o participante entrou na conferência.</span><span class="sxs-lookup"><span data-stu-id="d4b22-148">Date and time that the participant joined the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d4b22-149"><strong>Hora de saída</strong></span><span class="sxs-lookup"><span data-stu-id="d4b22-149"><strong>Leave time</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d4b22-150">Data e hora que o participante saiu da conferência.</span><span class="sxs-lookup"><span data-stu-id="d4b22-150">Date and time that the participant left the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d4b22-151"><strong>Agente do usuário</strong></span><span class="sxs-lookup"><span data-stu-id="d4b22-151"><strong>User agent</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d4b22-152">Identificador do software usado pelo ponto de extremidade do participante.</span><span class="sxs-lookup"><span data-stu-id="d4b22-152">Identifier for the software used by the participant’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d4b22-153"><strong>Relatórios de diagnóstico</strong></span><span class="sxs-lookup"><span data-stu-id="d4b22-153"><strong>Diagnostic reports</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d4b22-p104">Oferece informação de resolução de problemas e diagnóstico. Incluindo códigos de resposta SIP, cabeçalhos de diagnóstico, hora de participação da conferência e IDs de diagnósticos para sessões em falha.</span><span class="sxs-lookup"><span data-stu-id="d4b22-p104">Provides diagnostic and troubleshooting information. Including SIP response codes, diagnostic headers, conference join times, and diagnostic IDs for failed sessions.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="d4b22-156">A tabela a seguir lista as informações fornecidas na seção modalidades de conferência do relatório de detalhe da conferência.</span><span class="sxs-lookup"><span data-stu-id="d4b22-156">The following table lists the information provided in the Conference Modalities section of the Conference Detail Report.</span></span>

### <a name="conference-modalities-metrics"></a><span data-ttu-id="d4b22-157">Métricas das Modalidades da Conferência</span><span class="sxs-lookup"><span data-stu-id="d4b22-157">Conference Modalities Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d4b22-158">Nome</span><span class="sxs-lookup"><span data-stu-id="d4b22-158">Name</span></span></th>
<th><span data-ttu-id="d4b22-159">É possível classificar este item?</span><span class="sxs-lookup"><span data-stu-id="d4b22-159">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="d4b22-160">Descrição</span><span class="sxs-lookup"><span data-stu-id="d4b22-160">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d4b22-161"><strong>Usuário</strong></span><span class="sxs-lookup"><span data-stu-id="d4b22-161"><strong>User</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d4b22-162">Endereço SIP do usuário que participou da conferência.</span><span class="sxs-lookup"><span data-stu-id="d4b22-162">SIP address of the user who participated in the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d4b22-163"><strong>Hora de participação</strong></span><span class="sxs-lookup"><span data-stu-id="d4b22-163"><strong>Join time</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d4b22-164">Data e hora que o participante entrou na conferência.</span><span class="sxs-lookup"><span data-stu-id="d4b22-164">Date and time that the participant joined the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d4b22-165"><strong>Hora de saída</strong></span><span class="sxs-lookup"><span data-stu-id="d4b22-165"><strong>Leave time</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d4b22-166">Data e hora que um participante deixou a conferência.</span><span class="sxs-lookup"><span data-stu-id="d4b22-166">Date and time that a participant left the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d4b22-167"><strong>URI do servidor de conferência</strong></span><span class="sxs-lookup"><span data-stu-id="d4b22-167"><strong>Conferencing server URI</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d4b22-168">URI para o servidor de Conferência usado na conferência.</span><span class="sxs-lookup"><span data-stu-id="d4b22-168">URI for the Conferencing server used in the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d4b22-169"><strong>Relatórios de diagnóstico</strong></span><span class="sxs-lookup"><span data-stu-id="d4b22-169"><strong>Diagnostic reports</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d4b22-p105">Oferece informação de resolução de problemas e diagnóstico. Incluindo códigos de resposta SIP, cabeçalhos de diagnóstico, hora de participação da conferência e IDs de diagnósticos para sessões em falha.</span><span class="sxs-lookup"><span data-stu-id="d4b22-p105">Provides diagnostic and troubleshooting information. Including SIP response codes, diagnostic headers, conference join times, and diagnostic IDs for failed sessions.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

