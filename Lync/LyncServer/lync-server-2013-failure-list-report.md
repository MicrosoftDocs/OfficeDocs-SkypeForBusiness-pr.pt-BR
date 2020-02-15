---
title: 'Lync Server 2013: relatório de lista de falhas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failure List Report
ms:assetid: b6f3a605-e0c6-461e-b17a-41d8039ace9d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615446(v=OCS.15)
ms:contentKeyID: 48185194
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f9cd8d15e81a54085624fab2dc751759d8196c48
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42041040"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failure-list-report-in-lync-server-2013"></a><span data-ttu-id="07894-102">Relatório de lista de falhas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="07894-102">Failure List Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="07894-103">_**Última modificação do tópico:** 2012-07-02_</span><span class="sxs-lookup"><span data-stu-id="07894-103">_**Topic Last Modified:** 2012-07-02_</span></span>

<span data-ttu-id="07894-p101">The Failure List report provides information about the individual participants who took part in a failed peer-to-peer or conferencing session. This information includes the URI of the user who experienced the problem, as well as the SIP Response code and Diagnostic ID associated with the failure.</span><span class="sxs-lookup"><span data-stu-id="07894-p101">The Failure List report provides information about the individual participants who took part in a failed peer-to-peer or conferencing session. This information includes the URI of the user who experienced the problem, as well as the SIP Response code and Diagnostic ID associated with the failure.</span></span>

<div>

## <a name="accessing-the-failure-list-report"></a><span data-ttu-id="07894-106">Accessing the Failure List Report</span><span class="sxs-lookup"><span data-stu-id="07894-106">Accessing the Failure List Report</span></span>

<span data-ttu-id="07894-107">O relatório de lista de falhas é acessado clicando em qualquer uma das seguintes métricas no [relatório de distribuição de falha no Lync Server 2013](lync-server-2013-failure-distribution-report.md):</span><span class="sxs-lookup"><span data-stu-id="07894-107">The Failure List Report is accessed by clicking any of the following metrics on the [Failure Distribution Report in Lync Server 2013](lync-server-2013-failure-distribution-report.md):</span></span>

  - <span data-ttu-id="07894-108">Principais motivos diagnósticos (sessões)</span><span class="sxs-lookup"><span data-stu-id="07894-108">Top diagnostic reasons (sessions)</span></span>

  - <span data-ttu-id="07894-109">Principais modalidades (sessões)</span><span class="sxs-lookup"><span data-stu-id="07894-109">Top modalities (sessions)</span></span>

  - <span data-ttu-id="07894-110">Principais pools (sessões)</span><span class="sxs-lookup"><span data-stu-id="07894-110">Top pools (sessions)</span></span>

  - <span data-ttu-id="07894-111">Principais fontes (sessões)</span><span class="sxs-lookup"><span data-stu-id="07894-111">Top sources (sessions)</span></span>

  - <span data-ttu-id="07894-112">Principais componentes (sessões)</span><span class="sxs-lookup"><span data-stu-id="07894-112">Top components (sessions)</span></span>

  - <span data-ttu-id="07894-113">Principais usuários de origem (sessões)</span><span class="sxs-lookup"><span data-stu-id="07894-113">Top from users (sessions)</span></span>

  - <span data-ttu-id="07894-114">Principais usuários de destino (sessões)</span><span class="sxs-lookup"><span data-stu-id="07894-114">Top to users (sessions)</span></span>

  - <span data-ttu-id="07894-115">Principais agentes de usuários de origem (sessões)</span><span class="sxs-lookup"><span data-stu-id="07894-115">Top from user agents (sessions)</span></span>

<span data-ttu-id="07894-116">No relatório de lista de falhas, é possível acessar o [relatório de detalhes de sessão ponto a ponto no Lync Server 2013](lync-server-2013-peer-to-peer-session-detail-report.md) clicando na métrica de detalhes da sessão para uma sessão ponto a ponto.</span><span class="sxs-lookup"><span data-stu-id="07894-116">From the Failure List Report you can access the [Peer-to-Peer Session Detail Report in Lync Server 2013](lync-server-2013-peer-to-peer-session-detail-report.md) by clicking the Session detail metric for a peer-to-peer session.</span></span> <span data-ttu-id="07894-117">You can also access the Conference Detail Report by clicking the Conference metric for a conference.</span><span class="sxs-lookup"><span data-stu-id="07894-117">You can also access the Conference Detail Report by clicking the Conference metric for a conference.</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-failure-list-report"></a><span data-ttu-id="07894-118">Making the Best Use of the Failure List Report</span><span class="sxs-lookup"><span data-stu-id="07894-118">Making the Best Use of the Failure List Report</span></span>

<span data-ttu-id="07894-p103">In the Failure List Report, you can view a description for each Response code or each Diagnostic ID simply by holding your mouse over that value. For example, if you hold your mouse over Diagnostic ID 7025 you'll see the following displayed in a tooltip:</span><span class="sxs-lookup"><span data-stu-id="07894-p103">In the Failure List Report, you can view a description for each Response code or each Diagnostic ID simply by holding your mouse over that value. For example, if you hold your mouse over Diagnostic ID 7025 you'll see the following displayed in a tooltip:</span></span>

<span data-ttu-id="07894-121">Internal server error creating media for user.</span><span class="sxs-lookup"><span data-stu-id="07894-121">Internal server error creating media for user.</span></span>

<span data-ttu-id="07894-122">It's important to note that the Failure List Report does not provide a straightforward way to directly retrieve a list of all the users who participated in at least one failed session, nor does it provide a way to determine which users were most-often involved in a failed session.</span><span class="sxs-lookup"><span data-stu-id="07894-122">It's important to note that the Failure List Report does not provide a straightforward way to directly retrieve a list of all the users who participated in at least one failed session, nor does it provide a way to determine which users were most-often involved in a failed session.</span></span> <span data-ttu-id="07894-123">(Por um motivo, o relatório de lista de falhas não tem recursos de filtragem.) No entanto, se você exportar os dados e convertê-los em um arquivo de valores separados por vírgula, você poderá usar o Windows PowerShell para encontrar as respostas a perguntas como essas.</span><span class="sxs-lookup"><span data-stu-id="07894-123">(For one thing, the Failure List Report has no filtering capabilities.) However, if you export the data and then convert it to a comma-separated values file, you can use Windows PowerShell to find the answers to questions like those.</span></span> <span data-ttu-id="07894-124">Por exemplo, suponha que você salve os dados em um. Arquivo CSV chamado C:\\data\\Failure\_List. csv.</span><span class="sxs-lookup"><span data-stu-id="07894-124">For example, suppose you save the data to a .CSV file named C:\\Data\\Failure\_List.csv.</span></span> <span data-ttu-id="07894-125">Based on the data saved in that file, this command lists all the users who were involved in at least one failed session:</span><span class="sxs-lookup"><span data-stu-id="07894-125">Based on the data saved in that file, this command lists all the users who were involved in at least one failed session:</span></span>

    $failures = Import-Csv -Path " C:\Data\Failure_List.csv"
    $failure |Sort-Object "From user" | Select-Object "From user" -Unique

<span data-ttu-id="07894-126">That command will return a list similar to this:</span><span class="sxs-lookup"><span data-stu-id="07894-126">That command will return a list similar to this:</span></span>

    From user
    ----
    Pilar.Ackerman@litwareinc.com
    Henrik.Jensen@litwareinc.com
    Gilead.Amosnino@litwareinc.com
    David.Ahs@litwareinc.com
    Ken.Myer@litwareinc.com

<span data-ttu-id="07894-127">These two commands report back the total number of failed sessions that each user was involved in:</span><span class="sxs-lookup"><span data-stu-id="07894-127">These two commands report back the total number of failed sessions that each user was involved in:</span></span>

    $failures = Import-Csv -Path "C:\Data\Failure_List.csv"
    $failures | Group-Object "From user" | Select-Object Count, Name | Sort-Object -Property Count -Descending

<span data-ttu-id="07894-128">That will return data similar to this:</span><span class="sxs-lookup"><span data-stu-id="07894-128">That will return data similar to this:</span></span>

    Count    Name
     -----    ----
        20    Pilar.Ackerman@litwareinc.com
        20    David.Ahs@litwareinc.com
        16    Gilead.Amosnino@litwareinc.com
        16    Ken.Myero@litwareinc.com
        14    Henrik.Jensen@litwareinc.com

</div>

<div>

## <a name="filters"></a><span data-ttu-id="07894-129">Filtros</span><span class="sxs-lookup"><span data-stu-id="07894-129">Filters</span></span>

<span data-ttu-id="07894-p105">Nenhum. Não é possível filtrar o Relatório de Lista de Falhas.</span><span class="sxs-lookup"><span data-stu-id="07894-p105">None. You cannot filter the Failure List Report.</span></span>

</div>

<div>

## <a name="metrics"></a><span data-ttu-id="07894-132">Métricas</span><span class="sxs-lookup"><span data-stu-id="07894-132">Metrics</span></span>

<span data-ttu-id="07894-133">A tabela a seguir lista as informações fornecidas no Relatório de Lista de Falhas para cada chamada mal-sucedida.</span><span class="sxs-lookup"><span data-stu-id="07894-133">The following table lists the information provided in the Failure List Report for each failed call.</span></span>

### <a name="failure-list-report-metrics"></a><span data-ttu-id="07894-134">Métricas do Relatório de Lista de Falhas</span><span class="sxs-lookup"><span data-stu-id="07894-134">Failure List Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="07894-135">Nome</span><span class="sxs-lookup"><span data-stu-id="07894-135">Name</span></span></th>
<th><span data-ttu-id="07894-136">É possível classificar este item?</span><span class="sxs-lookup"><span data-stu-id="07894-136">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="07894-137">Descrição</span><span class="sxs-lookup"><span data-stu-id="07894-137">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="07894-138"><strong>Hora de relatório</strong></span><span class="sxs-lookup"><span data-stu-id="07894-138"><strong>Reported time</strong></span></span></p></td>
<td><p><span data-ttu-id="07894-139">Não</span><span class="sxs-lookup"><span data-stu-id="07894-139">No</span></span></p></td>
<td><p><span data-ttu-id="07894-140">Data e hora em que o relatório foi gravado.</span><span class="sxs-lookup"><span data-stu-id="07894-140">Date and time the report was recorded.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="07894-141"><strong>Solicitação</strong></span><span class="sxs-lookup"><span data-stu-id="07894-141"><strong>Request</strong></span></span></p></td>
<td><p><span data-ttu-id="07894-142">Não</span><span class="sxs-lookup"><span data-stu-id="07894-142">No</span></span></p></td>
<td><p><span data-ttu-id="07894-p106">Tipo de solicitação SIP que falhou. Por exemplo, CONVIDAR ou ATÉ LOGO.</span><span class="sxs-lookup"><span data-stu-id="07894-p106">SIP request type that failed. For example, INVITE or BYE.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="07894-145"><strong>Código da resposta</strong></span><span class="sxs-lookup"><span data-stu-id="07894-145"><strong>Response code</strong></span></span></p></td>
<td><p><span data-ttu-id="07894-146">Não</span><span class="sxs-lookup"><span data-stu-id="07894-146">No</span></span></p></td>
<td><p><span data-ttu-id="07894-147">Código da resposta SIP enviado quando a conferência falhou.</span><span class="sxs-lookup"><span data-stu-id="07894-147">SIP response code sent when the conference failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="07894-148"><strong>ID do Diagnóstico</strong></span><span class="sxs-lookup"><span data-stu-id="07894-148"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="07894-149">Não</span><span class="sxs-lookup"><span data-stu-id="07894-149">No</span></span></p></td>
<td><p><span data-ttu-id="07894-150">Identificador exclusivo (na forma de um cabeçalho ms-diagnostics) anexado a uma mensagem SIP que frequentemente fornece informações úteis para solução de erros.</span><span class="sxs-lookup"><span data-stu-id="07894-150">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="07894-151"><strong>Join cost time (ms)</strong></span><span class="sxs-lookup"><span data-stu-id="07894-151"><strong>Join cost time (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="07894-152">Não</span><span class="sxs-lookup"><span data-stu-id="07894-152">No</span></span></p></td>
<td><p><span data-ttu-id="07894-153">Amount of time (in milliseconds) required for the user to join the conference.</span><span class="sxs-lookup"><span data-stu-id="07894-153">Amount of time (in milliseconds) required for the user to join the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="07894-154"><strong>Do usuário </strong></span><span class="sxs-lookup"><span data-stu-id="07894-154"><strong>From user</strong></span></span></p></td>
<td><p><span data-ttu-id="07894-155">Não</span><span class="sxs-lookup"><span data-stu-id="07894-155">No</span></span></p></td>
<td><p><span data-ttu-id="07894-156">Endereço SIP do usuário que iniciou a chamada.</span><span class="sxs-lookup"><span data-stu-id="07894-156">SIP address of the user who initiated the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="07894-157"><strong>Representante do usuário de origem</strong></span><span class="sxs-lookup"><span data-stu-id="07894-157"><strong>From user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="07894-158">Não</span><span class="sxs-lookup"><span data-stu-id="07894-158">No</span></span></p></td>
<td><p><span data-ttu-id="07894-159">Software usado pelo ponto de extremidade do usuário que iniciou a chamada.</span><span class="sxs-lookup"><span data-stu-id="07894-159">Software used by the endpoint of the user who initiated the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="07894-160"><strong>Para usuário</strong></span><span class="sxs-lookup"><span data-stu-id="07894-160"><strong>To user</strong></span></span></p></td>
<td><p><span data-ttu-id="07894-161">Não</span><span class="sxs-lookup"><span data-stu-id="07894-161">No</span></span></p></td>
<td><p><span data-ttu-id="07894-162">Endereço SIP do usuário que estava recebendo a chamada.</span><span class="sxs-lookup"><span data-stu-id="07894-162">SIP address of the user who was being called.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

