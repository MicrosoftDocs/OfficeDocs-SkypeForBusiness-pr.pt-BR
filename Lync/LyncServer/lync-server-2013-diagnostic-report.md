---
title: 'Lync Server 2013: relatório de diagnóstico'
description: 'Lync Server 2013: relatório de diagnóstico.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Diagnostic Report
ms:assetid: b389dbd9-f2e8-4184-93d0-2e504796ac16
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615445(v=OCS.15)
ms:contentKeyID: 48185159
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 198b836437285b464ba9172e59c9a60ed0a53b65
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576247"
---
# <a name="diagnostic-report-in-lync-server-2013"></a><span data-ttu-id="c59f9-103">Relatório de diagnóstico no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c59f9-103">Diagnostic Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c59f9-104">_**Última modificação do tópico:** 2014-02-07_</span><span class="sxs-lookup"><span data-stu-id="c59f9-104">_**Topic Last Modified:** 2014-02-07_</span></span>

<span data-ttu-id="c59f9-105">O Relatório de diagnóstico fornece diagnósticos e informações para a solução de problemas de uma sessão com falha.</span><span class="sxs-lookup"><span data-stu-id="c59f9-105">The Diagnostic Report provides diagnostic and troubleshooting information for a failed session.</span></span> <span data-ttu-id="c59f9-106">Essas informações incluem a ID de diagnóstico e o cabeçalho de Diagnóstico que foram importados quando a sessão falhou.</span><span class="sxs-lookup"><span data-stu-id="c59f9-106">This information includes both the Diagnostic ID and the Diagnostic header that were reported when the session failed.</span></span> <span data-ttu-id="c59f9-107">A ID de diagnóstico é um identificador exclusivo (na forma de um cabeçalho ms-diagnostics) que é anexado a uma mensagem SIP, enquanto a cabeçalho de Diagnóstico fornece uma descrição da ID de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="c59f9-107">The Diagnostic ID is a unique identifier (in the form of an ms-diagnostics header) that gets attached to a SIP message, while the Diagnostic header provides an accompanying description for the Diagnostic ID.</span></span> <span data-ttu-id="c59f9-108">O relatório também pode conter detalhes importantes para a solução de problemas e que são conhecidos pelo componente de relatório.</span><span class="sxs-lookup"><span data-stu-id="c59f9-108">The report might also contain valuable troubleshooting details that are known by the reporting component.</span></span> <span data-ttu-id="c59f9-109">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="c59f9-109">For example:</span></span>

  - <span data-ttu-id="c59f9-p102">O código de motivo fornecido pelo gateway da PSTN que gerou a falha. Quando uma chamada de saída falha na rede PSTN, um código de causa ISUP (parte de usuário ISDN, em inglês) é gerado automaticamente. Por exemplo, um gateway PSTN pode enviar o código de causa 34 para indicar que nenhum circuito ou canal estava disponível para completar a chamada.</span><span class="sxs-lookup"><span data-stu-id="c59f9-p102">The cause code provided by the PSTN gateway that generated the failure. When an outgoing call fails on the PSTN network, an ISDN User Part (ISUP) cause code is automatically generated. For example, a PSTN gateway might send cause code 34 to indicate that no circuit or channel was available for completing the call.</span></span>

  - <span data-ttu-id="c59f9-113">FQDN do par, porta e erros de Winsock para falhas de conectividade.</span><span class="sxs-lookup"><span data-stu-id="c59f9-113">Peer FQDN, port, and Winsock errors for connectivity failures.</span></span>

  - <span data-ttu-id="c59f9-p103">Nomes pesquisados por falhas de resolução de DNS. A resolução DNS ocorre sempre que um cliente entra em contato com um servidor de nomes e solicita o endereço IP que corresponde ao nome de dispositivo especificado.</span><span class="sxs-lookup"><span data-stu-id="c59f9-p103">Names being looked up for DNS resolution failures. DNS resolution takes place any time a client contacts a name server and requests the IP address that corresponds to specified device name.</span></span>

<div>

## <a name="accessing-the-diagnostic-report"></a><span data-ttu-id="c59f9-116">Acessando o relatório de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="c59f9-116">Accessing the Diagnostic Report</span></span>

<span data-ttu-id="c59f9-117">O relatório de diagnóstico pode ser acessado clicando na métrica relatório de diagnóstico (detalhe) no [relatório de detalhes de sessão ponto a ponto no Lync Server 2013](lync-server-2013-peer-to-peer-session-detail-report.md) ou no relatório de detalhes da conferência.</span><span class="sxs-lookup"><span data-stu-id="c59f9-117">The Diagnostic Report can be accessed by clicking the Diagnostic Report (Detail) metric on either the [Peer-to-Peer Session Detail Report in Lync Server 2013](lync-server-2013-peer-to-peer-session-detail-report.md) or the Conference Detail Report.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="c59f9-118">Filtros</span><span class="sxs-lookup"><span data-stu-id="c59f9-118">Filters</span></span>

<span data-ttu-id="c59f9-p104">Nenhum. Não é possível filtrar o Relatório de Diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="c59f9-p104">None. You cannot filter the Diagnostic Report.</span></span>

</div>

<div>

## <a name="metrics"></a><span data-ttu-id="c59f9-121">Métrica</span><span class="sxs-lookup"><span data-stu-id="c59f9-121">Metrics</span></span>

<span data-ttu-id="c59f9-122">A tabela a seguir lista as informações fornecidas no Relatório de Diagnóstico para cada sessão.</span><span class="sxs-lookup"><span data-stu-id="c59f9-122">The following table lists the information provided in the Diagnostic Report for each session.</span></span>

### <a name="diagnostic-report-metrics"></a><span data-ttu-id="c59f9-123">Métricas do Relatório de Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="c59f9-123">Diagnostic Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c59f9-124">Nome</span><span class="sxs-lookup"><span data-stu-id="c59f9-124">Name</span></span></th>
<th><span data-ttu-id="c59f9-125">É possível classificar este item?</span><span class="sxs-lookup"><span data-stu-id="c59f9-125">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="c59f9-126">Descrição</span><span class="sxs-lookup"><span data-stu-id="c59f9-126">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c59f9-127"><strong>Hora do relatório</strong></span><span class="sxs-lookup"><span data-stu-id="c59f9-127"><strong>Report time</strong></span></span></p></td>
<td><p><span data-ttu-id="c59f9-128">Não</span><span class="sxs-lookup"><span data-stu-id="c59f9-128">No</span></span></p></td>
<td><p><span data-ttu-id="c59f9-129">Data e hora do registro do relatório.</span><span class="sxs-lookup"><span data-stu-id="c59f9-129">Date and time that the report was recorded.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c59f9-130"><strong>Código da resposta</strong></span><span class="sxs-lookup"><span data-stu-id="c59f9-130"><strong>Response code</strong></span></span></p></td>
<td><p><span data-ttu-id="c59f9-131">Não</span><span class="sxs-lookup"><span data-stu-id="c59f9-131">No</span></span></p></td>
<td><p><span data-ttu-id="c59f9-132">Código da resposta SIP enviado quando a sessão falhou.</span><span class="sxs-lookup"><span data-stu-id="c59f9-132">SIP response code sent when the session failed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c59f9-133"><strong>Tipo de solicitação</strong></span><span class="sxs-lookup"><span data-stu-id="c59f9-133"><strong>Request type</strong></span></span></p></td>
<td><p><span data-ttu-id="c59f9-134">Não</span><span class="sxs-lookup"><span data-stu-id="c59f9-134">No</span></span></p></td>
<td><p><span data-ttu-id="c59f9-p105">Tipo de solicitação SIP que falhou. Por exemplo, CONVIDAR, ATÉ LOGO ou SERVIÇO.</span><span class="sxs-lookup"><span data-stu-id="c59f9-p105">SIP request type that failed. For example, INVITE, BYE, or SERVICE.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c59f9-137"><strong>Fonte</strong></span><span class="sxs-lookup"><span data-stu-id="c59f9-137"><strong>Source</strong></span></span></p></td>
<td><p><span data-ttu-id="c59f9-138">Não</span><span class="sxs-lookup"><span data-stu-id="c59f9-138">No</span></span></p></td>
<td><p><span data-ttu-id="c59f9-139">Origem do erro.</span><span class="sxs-lookup"><span data-stu-id="c59f9-139">Source of the error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c59f9-140"><strong>URI do usuário de origem</strong></span><span class="sxs-lookup"><span data-stu-id="c59f9-140"><strong>From user URI</strong></span></span></p></td>
<td><p><span data-ttu-id="c59f9-141">Não</span><span class="sxs-lookup"><span data-stu-id="c59f9-141">No</span></span></p></td>
<td><p><span data-ttu-id="c59f9-142">Endereço SIP do usuário que iniciou a sessão.</span><span class="sxs-lookup"><span data-stu-id="c59f9-142">SIP address of the user who initiated the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c59f9-143"><strong>Representante do usuário de origem</strong></span><span class="sxs-lookup"><span data-stu-id="c59f9-143"><strong>From user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="c59f9-144">Não</span><span class="sxs-lookup"><span data-stu-id="c59f9-144">No</span></span></p></td>
<td><p><span data-ttu-id="c59f9-145">Software usado pelo ponto de extremidade do usuário que iniciou a sessão.</span><span class="sxs-lookup"><span data-stu-id="c59f9-145">Software used by the endpoint of the user who initiated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c59f9-146"><strong>ID do Diagnóstico</strong></span><span class="sxs-lookup"><span data-stu-id="c59f9-146"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="c59f9-147">Não</span><span class="sxs-lookup"><span data-stu-id="c59f9-147">No</span></span></p></td>
<td><p><span data-ttu-id="c59f9-148">Identificador exclusivo (no formato de um cabeçalho ms-diagnostics) anexado a uma mensagem SIP que frequentemente oferece informações úteis para resolução de erros.</span><span class="sxs-lookup"><span data-stu-id="c59f9-148">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c59f9-149"><strong>Tipo de conteúdo</strong></span><span class="sxs-lookup"><span data-stu-id="c59f9-149"><strong>Content type</strong></span></span></p></td>
<td><p><span data-ttu-id="c59f9-150">Não</span><span class="sxs-lookup"><span data-stu-id="c59f9-150">No</span></span></p></td>
<td><p><span data-ttu-id="c59f9-p106">Tipo de conteúdo de mídia que falhou. Por exemplo, um tipo de conteúdo comum é Application/sdp. SDP (Protocolo de descrição de sessão) é um protocolo padrão de Internet usado para anúncios de sessão, convites de sessão e outras formas de início de sessão multimídia.</span><span class="sxs-lookup"><span data-stu-id="c59f9-p106">Type of media content that failed. For example, a common content type is Application/sdp. Session Description Protocol (SDP) is a standard Internet protocol used for session announcements, session invitations, and other forms of multimedia session initiation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c59f9-154"><strong>Aplicação</strong></span><span class="sxs-lookup"><span data-stu-id="c59f9-154"><strong>Application</strong></span></span></p></td>
<td><p><span data-ttu-id="c59f9-155">Não</span><span class="sxs-lookup"><span data-stu-id="c59f9-155">No</span></span></p></td>
<td><p><span data-ttu-id="c59f9-156">Aplicativo envolvido no erro.</span><span class="sxs-lookup"><span data-stu-id="c59f9-156">Application involved in the error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c59f9-157"><strong>URI do usuário de destino</strong></span><span class="sxs-lookup"><span data-stu-id="c59f9-157"><strong>To user URI</strong></span></span></p></td>
<td><p><span data-ttu-id="c59f9-158">Não</span><span class="sxs-lookup"><span data-stu-id="c59f9-158">No</span></span></p></td>
<td><p><span data-ttu-id="c59f9-159">Endereço SIP do usuário convidado para a sessão.</span><span class="sxs-lookup"><span data-stu-id="c59f9-159">SIP address of the user who was invited to the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c59f9-160">Hora de ingresso de conferência (ms)</span><span class="sxs-lookup"><span data-stu-id="c59f9-160">Conference join times (ms)</span></span></p></td>
<td><p><span data-ttu-id="c59f9-161">Não</span><span class="sxs-lookup"><span data-stu-id="c59f9-161">No</span></span></p></td>
<td><p><span data-ttu-id="c59f9-162">Tempo (em milissegundos) que o usuário precisou para ingressar na conferência.</span><span class="sxs-lookup"><span data-stu-id="c59f9-162">Amount of time (in milliseconds) it took for the user to join the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c59f9-163"><strong>Cabeçalho do diagnóstico</strong></span><span class="sxs-lookup"><span data-stu-id="c59f9-163"><strong>Diagnostic header</strong></span></span></p></td>
<td><p><span data-ttu-id="c59f9-164">Não</span><span class="sxs-lookup"><span data-stu-id="c59f9-164">No</span></span></p></td>
<td><p><span data-ttu-id="c59f9-165">Descrição do ID de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="c59f9-165">Diagnostic ID description.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="c59f9-166">Uma lista de erros de diagnóstico pode ser encontrada na [página de cabeçalho MS-Diagnostics](https://msdn.microsoft.com/library/gg132446\(v=office.12\).aspx).</span><span class="sxs-lookup"><span data-stu-id="c59f9-166">A list of diagnostic errors can be found on the [Ms-Diagnostics Header page](https://msdn.microsoft.com/library/gg132446\(v=office.12\).aspx).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

