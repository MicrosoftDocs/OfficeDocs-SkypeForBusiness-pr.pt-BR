---
title: 'Lync Server 2013: relatório de diagnóstico'
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
ms.openlocfilehash: 57d62e5938fd2d3b3d6966410a99e2f2e106325f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140314"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="diagnostic-report-in-lync-server-2013"></a><span data-ttu-id="d35f9-102">Relatório de diagnóstico no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d35f9-102">Diagnostic Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d35f9-103">_**Última modificação do tópico:** 2014-02-07_</span><span class="sxs-lookup"><span data-stu-id="d35f9-103">_**Topic Last Modified:** 2014-02-07_</span></span>

<span data-ttu-id="d35f9-104">O Relatório de diagnóstico fornece diagnósticos e informações para a solução de problemas de uma sessão com falha.</span><span class="sxs-lookup"><span data-stu-id="d35f9-104">The Diagnostic Report provides diagnostic and troubleshooting information for a failed session.</span></span> <span data-ttu-id="d35f9-105">Essas informações incluem a ID de diagnóstico e o cabeçalho de Diagnóstico que foram importados quando a sessão falhou.</span><span class="sxs-lookup"><span data-stu-id="d35f9-105">This information includes both the Diagnostic ID and the Diagnostic header that were reported when the session failed.</span></span> <span data-ttu-id="d35f9-106">A ID de diagnóstico é um identificador exclusivo (na forma de um cabeçalho ms-diagnostics) que é anexado a uma mensagem SIP, enquanto a cabeçalho de Diagnóstico fornece uma descrição da ID de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="d35f9-106">The Diagnostic ID is a unique identifier (in the form of an ms-diagnostics header) that gets attached to a SIP message, while the Diagnostic header provides an accompanying description for the Diagnostic ID.</span></span> <span data-ttu-id="d35f9-107">O relatório também pode conter detalhes importantes para a solução de problemas e que são conhecidos pelo componente de relatório.</span><span class="sxs-lookup"><span data-stu-id="d35f9-107">The report might also contain valuable troubleshooting details that are known by the reporting component.</span></span> <span data-ttu-id="d35f9-108">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="d35f9-108">For example:</span></span>

  - <span data-ttu-id="d35f9-p102">O código de motivo fornecido pelo gateway da PSTN que gerou a falha. Quando uma chamada de saída falha na rede PSTN, um código de causa ISUP (parte de usuário ISDN, em inglês) é gerado automaticamente. Por exemplo, um gateway PSTN pode enviar o código de causa 34 para indicar que nenhum circuito ou canal estava disponível para completar a chamada.</span><span class="sxs-lookup"><span data-stu-id="d35f9-p102">The cause code provided by the PSTN gateway that generated the failure. When an outgoing call fails on the PSTN network, an ISDN User Part (ISUP) cause code is automatically generated. For example, a PSTN gateway might send cause code 34 to indicate that no circuit or channel was available for completing the call.</span></span>

  - <span data-ttu-id="d35f9-112">FQDN do par, porta e erros de Winsock para falhas de conectividade.</span><span class="sxs-lookup"><span data-stu-id="d35f9-112">Peer FQDN, port, and Winsock errors for connectivity failures.</span></span>

  - <span data-ttu-id="d35f9-p103">Nomes pesquisados por falhas de resolução de DNS. A resolução DNS ocorre sempre que um cliente entra em contato com um servidor de nomes e solicita o endereço IP que corresponde ao nome de dispositivo especificado.</span><span class="sxs-lookup"><span data-stu-id="d35f9-p103">Names being looked up for DNS resolution failures. DNS resolution takes place any time a client contacts a name server and requests the IP address that corresponds to specified device name.</span></span>

<div>

## <a name="accessing-the-diagnostic-report"></a><span data-ttu-id="d35f9-115">Acessando o relatório de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="d35f9-115">Accessing the Diagnostic Report</span></span>

<span data-ttu-id="d35f9-116">O relatório de diagnóstico pode ser acessado clicando na métrica relatório de diagnóstico (detalhe) no [relatório de detalhes de sessão ponto a ponto no Lync Server 2013](lync-server-2013-peer-to-peer-session-detail-report.md) ou no relatório de detalhes da conferência.</span><span class="sxs-lookup"><span data-stu-id="d35f9-116">The Diagnostic Report can be accessed by clicking the Diagnostic Report (Detail) metric on either the [Peer-to-Peer Session Detail Report in Lync Server 2013](lync-server-2013-peer-to-peer-session-detail-report.md) or the Conference Detail Report.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="d35f9-117">Filtros</span><span class="sxs-lookup"><span data-stu-id="d35f9-117">Filters</span></span>

<span data-ttu-id="d35f9-p104">Nenhum. Não é possível filtrar o Relatório de Diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="d35f9-p104">None. You cannot filter the Diagnostic Report.</span></span>

</div>

<div>

## <a name="metrics"></a><span data-ttu-id="d35f9-120">Métricas</span><span class="sxs-lookup"><span data-stu-id="d35f9-120">Metrics</span></span>

<span data-ttu-id="d35f9-121">A tabela a seguir lista as informações fornecidas no Relatório de Diagnóstico para cada sessão.</span><span class="sxs-lookup"><span data-stu-id="d35f9-121">The following table lists the information provided in the Diagnostic Report for each session.</span></span>

### <a name="diagnostic-report-metrics"></a><span data-ttu-id="d35f9-122">Métricas do Relatório de Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="d35f9-122">Diagnostic Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d35f9-123">Nome</span><span class="sxs-lookup"><span data-stu-id="d35f9-123">Name</span></span></th>
<th><span data-ttu-id="d35f9-124">É possível classificar este item?</span><span class="sxs-lookup"><span data-stu-id="d35f9-124">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="d35f9-125">Descrição</span><span class="sxs-lookup"><span data-stu-id="d35f9-125">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d35f9-126"><strong>Hora do relatório</strong></span><span class="sxs-lookup"><span data-stu-id="d35f9-126"><strong>Report time</strong></span></span></p></td>
<td><p><span data-ttu-id="d35f9-127">Não</span><span class="sxs-lookup"><span data-stu-id="d35f9-127">No</span></span></p></td>
<td><p><span data-ttu-id="d35f9-128">Data e hora do registro do relatório.</span><span class="sxs-lookup"><span data-stu-id="d35f9-128">Date and time that the report was recorded.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d35f9-129"><strong>Código da resposta</strong></span><span class="sxs-lookup"><span data-stu-id="d35f9-129"><strong>Response code</strong></span></span></p></td>
<td><p><span data-ttu-id="d35f9-130">Não</span><span class="sxs-lookup"><span data-stu-id="d35f9-130">No</span></span></p></td>
<td><p><span data-ttu-id="d35f9-131">Código da resposta SIP enviado quando a sessão falhou.</span><span class="sxs-lookup"><span data-stu-id="d35f9-131">SIP response code sent when the session failed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d35f9-132"><strong>Tipo de solicitação</strong></span><span class="sxs-lookup"><span data-stu-id="d35f9-132"><strong>Request type</strong></span></span></p></td>
<td><p><span data-ttu-id="d35f9-133">Não</span><span class="sxs-lookup"><span data-stu-id="d35f9-133">No</span></span></p></td>
<td><p><span data-ttu-id="d35f9-p105">Tipo de solicitação SIP que falhou. Por exemplo, CONVIDAR, ATÉ LOGO ou SERVIÇO.</span><span class="sxs-lookup"><span data-stu-id="d35f9-p105">SIP request type that failed. For example, INVITE, BYE, or SERVICE.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d35f9-136"><strong>Fonte</strong></span><span class="sxs-lookup"><span data-stu-id="d35f9-136"><strong>Source</strong></span></span></p></td>
<td><p><span data-ttu-id="d35f9-137">Não</span><span class="sxs-lookup"><span data-stu-id="d35f9-137">No</span></span></p></td>
<td><p><span data-ttu-id="d35f9-138">Origem do erro.</span><span class="sxs-lookup"><span data-stu-id="d35f9-138">Source of the error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d35f9-139"><strong>URI do usuário de origem</strong></span><span class="sxs-lookup"><span data-stu-id="d35f9-139"><strong>From user URI</strong></span></span></p></td>
<td><p><span data-ttu-id="d35f9-140">Não</span><span class="sxs-lookup"><span data-stu-id="d35f9-140">No</span></span></p></td>
<td><p><span data-ttu-id="d35f9-141">Endereço SIP do usuário que iniciou a sessão.</span><span class="sxs-lookup"><span data-stu-id="d35f9-141">SIP address of the user who initiated the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d35f9-142"><strong>Representante do usuário de origem</strong></span><span class="sxs-lookup"><span data-stu-id="d35f9-142"><strong>From user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="d35f9-143">Não</span><span class="sxs-lookup"><span data-stu-id="d35f9-143">No</span></span></p></td>
<td><p><span data-ttu-id="d35f9-144">Software usado pelo ponto de extremidade do usuário que iniciou a sessão.</span><span class="sxs-lookup"><span data-stu-id="d35f9-144">Software used by the endpoint of the user who initiated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d35f9-145"><strong>ID do Diagnóstico</strong></span><span class="sxs-lookup"><span data-stu-id="d35f9-145"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="d35f9-146">Não</span><span class="sxs-lookup"><span data-stu-id="d35f9-146">No</span></span></p></td>
<td><p><span data-ttu-id="d35f9-147">Identificador exclusivo (no formato de um cabeçalho ms-diagnostics) anexado a uma mensagem SIP que frequentemente oferece informações úteis para resolução de erros.</span><span class="sxs-lookup"><span data-stu-id="d35f9-147">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d35f9-148"><strong>Tipo de conteúdo</strong></span><span class="sxs-lookup"><span data-stu-id="d35f9-148"><strong>Content type</strong></span></span></p></td>
<td><p><span data-ttu-id="d35f9-149">Não</span><span class="sxs-lookup"><span data-stu-id="d35f9-149">No</span></span></p></td>
<td><p><span data-ttu-id="d35f9-p106">Tipo de conteúdo de mídia que falhou. Por exemplo, um tipo de conteúdo comum é Application/sdp. SDP (Protocolo de descrição de sessão) é um protocolo padrão de Internet usado para anúncios de sessão, convites de sessão e outras formas de início de sessão multimídia.</span><span class="sxs-lookup"><span data-stu-id="d35f9-p106">Type of media content that failed. For example, a common content type is Application/sdp. Session Description Protocol (SDP) is a standard Internet protocol used for session announcements, session invitations, and other forms of multimedia session initiation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d35f9-153"><strong>Aplicativo</strong></span><span class="sxs-lookup"><span data-stu-id="d35f9-153"><strong>Application</strong></span></span></p></td>
<td><p><span data-ttu-id="d35f9-154">Não</span><span class="sxs-lookup"><span data-stu-id="d35f9-154">No</span></span></p></td>
<td><p><span data-ttu-id="d35f9-155">Aplicativo envolvido no erro.</span><span class="sxs-lookup"><span data-stu-id="d35f9-155">Application involved in the error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d35f9-156"><strong>URI do usuário de destino</strong></span><span class="sxs-lookup"><span data-stu-id="d35f9-156"><strong>To user URI</strong></span></span></p></td>
<td><p><span data-ttu-id="d35f9-157">Não</span><span class="sxs-lookup"><span data-stu-id="d35f9-157">No</span></span></p></td>
<td><p><span data-ttu-id="d35f9-158">Endereço SIP do usuário convidado para a sessão.</span><span class="sxs-lookup"><span data-stu-id="d35f9-158">SIP address of the user who was invited to the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d35f9-159">Hora de ingresso de conferência (ms)</span><span class="sxs-lookup"><span data-stu-id="d35f9-159">Conference join times (ms)</span></span></p></td>
<td><p><span data-ttu-id="d35f9-160">Não</span><span class="sxs-lookup"><span data-stu-id="d35f9-160">No</span></span></p></td>
<td><p><span data-ttu-id="d35f9-161">Tempo (em milissegundos) que o usuário precisou para ingressar na conferência.</span><span class="sxs-lookup"><span data-stu-id="d35f9-161">Amount of time (in milliseconds) it took for the user to join the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d35f9-162"><strong>Cabeçalho do diagnóstico</strong></span><span class="sxs-lookup"><span data-stu-id="d35f9-162"><strong>Diagnostic header</strong></span></span></p></td>
<td><p><span data-ttu-id="d35f9-163">Não</span><span class="sxs-lookup"><span data-stu-id="d35f9-163">No</span></span></p></td>
<td><p><span data-ttu-id="d35f9-164">Descrição do ID de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="d35f9-164">Diagnostic ID description.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="d35f9-165">Uma lista de erros de diagnóstico pode ser encontrada na [página de cabeçalho MS-Diagnostics](http://msdn.microsoft.com/library/gg132446\(v=office.12\).aspx).</span><span class="sxs-lookup"><span data-stu-id="d35f9-165">A list of diagnostic errors can be found on the [Ms-Diagnostics Header page](http://msdn.microsoft.com/library/gg132446\(v=office.12\).aspx).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

