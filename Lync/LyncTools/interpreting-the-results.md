---
title: Interpretação dos resultados
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Interpreting the Results
ms:assetid: dd7f199f-7075-4d88-bb84-49a7e05eb593
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945608(v=OCS.15)
ms:contentKeyID: 51541433
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c226e3b677965db03ba4d5fcc3c3dadb37192548
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049413"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="interpreting-the-results"></a><span data-ttu-id="93084-102">Interpretação dos resultados</span><span class="sxs-lookup"><span data-stu-id="93084-102">Interpreting the Results</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="93084-103">_**Última modificação do tópico:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="93084-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="93084-104">A ferramenta de estresse e desempenho do Lync Server 2013 (LyncPerfTool. exe) tem muitos contadores que você pode usar para entender o que o cliente está fazendo e se ele está encontrando problemas.</span><span class="sxs-lookup"><span data-stu-id="93084-104">The Lync Server 2013 Stress and Performance Tool (LyncPerfTool.exe) has many counters that you can use to understand what the client is doing and whether it is encountering issues.</span></span>

<div>

## <a name="client-counters"></a><span data-ttu-id="93084-105">Contadores de cliente</span><span class="sxs-lookup"><span data-stu-id="93084-105">Client Counters</span></span>

<span data-ttu-id="93084-106">Cada instância de LyncPerfTool. exe que está sendo executada tem uma instância separada dos contadores.</span><span class="sxs-lookup"><span data-stu-id="93084-106">Each instance of LyncPerfTool.exe that is running has a separate instance of the counters.</span></span> <span data-ttu-id="93084-107">Cada instância é nomeada por ID de processo.</span><span class="sxs-lookup"><span data-stu-id="93084-107">Each instance is named by its process ID.</span></span>

<span data-ttu-id="93084-108">Se os clientes estiverem sobrecarregados, poderão ocorrer problemas.</span><span class="sxs-lookup"><span data-stu-id="93084-108">If the clients are overloaded, issues can occur.</span></span> <span data-ttu-id="93084-109">Para evitar esses problemas, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="93084-109">To prevent these issues, do the following:</span></span>

1.  <span data-ttu-id="93084-110">Monitore a CPU e o uso de memória nos computadores clientes.</span><span class="sxs-lookup"><span data-stu-id="93084-110">Monitor the CPU and the memory usage on the client computers.</span></span> <span data-ttu-id="93084-111">Se a CPU estiver consistentemente acima de 90%, reduza o número de usuários.</span><span class="sxs-lookup"><span data-stu-id="93084-111">If the CPU is consistently above 90 percent, reduce the number of users.</span></span>

2.  <span data-ttu-id="93084-112">Se o espaço de memória for alto, você poderá encontrar problemas se o arquivo de paginação não for grande o suficiente.</span><span class="sxs-lookup"><span data-stu-id="93084-112">If the memory footprint is high, you could run into issues if the page file is not big enough.</span></span> <span data-ttu-id="93084-113">Verifique se o encargo de confirmação não está atingindo o limite no computador.</span><span class="sxs-lookup"><span data-stu-id="93084-113">Verify that the Commit Charge is not hitting the limit on the computer.</span></span> <span data-ttu-id="93084-114">Se você estiver executando limites de memória, considere aumentar o tamanho do arquivo de paginação ou reduzir o número de usuários</span><span class="sxs-lookup"><span data-stu-id="93084-114">If you are running into memory limits, consider increasing the page file size or reducing the number of users</span></span>

<span data-ttu-id="93084-115">As tabelas a seguir listam os principais contadores de desempenho do LyncPerfTool.</span><span class="sxs-lookup"><span data-stu-id="93084-115">The following tables list the key LyncPerfTool performance counters.</span></span>

<span data-ttu-id="93084-116">**Informações gerais**</span><span class="sxs-lookup"><span data-stu-id="93084-116">**General Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="93084-117"><strong>Contador de desempenho</strong></span><span class="sxs-lookup"><span data-stu-id="93084-117"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="93084-118"><strong>Descrição</strong></span><span class="sxs-lookup"><span data-stu-id="93084-118"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="93084-119">Tempo gasto em minutos</span><span class="sxs-lookup"><span data-stu-id="93084-119">Time Spent in Minutes</span></span></p></td>
<td><p><span data-ttu-id="93084-120">Tempo gasto desde o início do processo.</span><span class="sxs-lookup"><span data-stu-id="93084-120">Time spent since the process was started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93084-121">Pontos de extremidade ativos</span><span class="sxs-lookup"><span data-stu-id="93084-121">Active Endpoints</span></span></p></td>
<td><p><span data-ttu-id="93084-122">Número de pontos de extremidade conectados atualmente ao servidor.</span><span class="sxs-lookup"><span data-stu-id="93084-122">Number of endpoints currently connected to the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93084-123">Logons com falha</span><span class="sxs-lookup"><span data-stu-id="93084-123">Failed Logons</span></span></p></td>
<td><p><span data-ttu-id="93084-124">Número total de falhas de entrada de ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="93084-124">Total number of endpoint sign-in failures.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93084-125">Tentativas de logon</span><span class="sxs-lookup"><span data-stu-id="93084-125">Logon Attempts</span></span></p></td>
<td><p><span data-ttu-id="93084-126">Número total de tentativas de entrada de ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="93084-126">Total number of endpoint sign-in attempts.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93084-127">Pontos de extremidade desconectados</span><span class="sxs-lookup"><span data-stu-id="93084-127">Endpoints Disconnected</span></span></p></td>
<td><p><span data-ttu-id="93084-128">Número total de pontos de extremidade que foram desconectados.</span><span class="sxs-lookup"><span data-stu-id="93084-128">Total number of endpoints that have been disconnected.</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="93084-129">**Informações de presença**</span><span class="sxs-lookup"><span data-stu-id="93084-129">**Presence Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="93084-130"><strong>Contador de desempenho</strong></span><span class="sxs-lookup"><span data-stu-id="93084-130"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="93084-131"><strong>Descrição</strong></span><span class="sxs-lookup"><span data-stu-id="93084-131"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="93084-132">Chamadas de setpresence</span><span class="sxs-lookup"><span data-stu-id="93084-132">SetPresence Calls</span></span></p></td>
<td><p><span data-ttu-id="93084-133">Número total de tentativas de alteração de presença.</span><span class="sxs-lookup"><span data-stu-id="93084-133">Total number of presence change attempts.</span></span> <span data-ttu-id="93084-134">Para diferentes tipos de alterações de presença, confira contador de desempenho de chamadas de setpresence (tipo de presença).</span><span class="sxs-lookup"><span data-stu-id="93084-134">For different types of presence changes, see the SetPresence (Presence Type) Calls Performance Counter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93084-135">Respostas de NNN para setpresence</span><span class="sxs-lookup"><span data-stu-id="93084-135">NNN Responses for SetPresence</span></span></p></td>
<td><p><span data-ttu-id="93084-136">Número total de códigos de resposta nnn recebidos do servidor.</span><span class="sxs-lookup"><span data-stu-id="93084-136">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93084-137">Chamadas de getpresence</span><span class="sxs-lookup"><span data-stu-id="93084-137">GetPresence Calls</span></span></p></td>
<td><p><span data-ttu-id="93084-138">Número total de tentativas de solicitação de presença de obtenção.</span><span class="sxs-lookup"><span data-stu-id="93084-138">Total number of get presence request attempts.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93084-139">Respostas de NNN para getpresence</span><span class="sxs-lookup"><span data-stu-id="93084-139">NNN Responses for GetPresence</span></span></p></td>
<td><p><span data-ttu-id="93084-140">Número total de códigos de resposta nnn recebidos do servidor.</span><span class="sxs-lookup"><span data-stu-id="93084-140">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="93084-141">**Informações do serviço de catálogo de endereços**</span><span class="sxs-lookup"><span data-stu-id="93084-141">**Address Book service Information**</span></span>

<span data-ttu-id="93084-142">Esta categoria inclui contadores usados para monitorar downloads de arquivo do serviço de catálogo de endereços (ABS) e solicitações de serviço de consulta à Web do catálogo de endereços.</span><span class="sxs-lookup"><span data-stu-id="93084-142">This category includes counters used to monitor Address Book service (ABS) file downloads and Address Book Web Query service requests.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="93084-143"><strong>Contador de desempenho</strong></span><span class="sxs-lookup"><span data-stu-id="93084-143"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="93084-144"><strong>Descrição</strong></span><span class="sxs-lookup"><span data-stu-id="93084-144"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="93084-145">Tentativa de downloads de arquivo completo/Delta do ABS</span><span class="sxs-lookup"><span data-stu-id="93084-145">ABS Full/Delta File Downloads Attempted</span></span></p></td>
<td><p><span data-ttu-id="93084-146">Número total de solicitações de download de arquivo completo ou Delta tentadas.</span><span class="sxs-lookup"><span data-stu-id="93084-146">Total number of full or delta file download requests attempted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93084-147">Downloads de arquivo completo/Delta do ABS bem-sucedido</span><span class="sxs-lookup"><span data-stu-id="93084-147">ABS Full/Delta File Downloads Succeeded</span></span></p></td>
<td><p><span data-ttu-id="93084-148">Número total de solicitações de download de arquivo completo ou Delta tentadas.</span><span class="sxs-lookup"><span data-stu-id="93084-148">Total number of full or delta file download requests attempted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93084-149">Contadores relacionados ao serviço de consulta da Web do catálogo de endereços</span><span class="sxs-lookup"><span data-stu-id="93084-149">Address Book Web Query service related counters</span></span></p></td>
<td><p><span data-ttu-id="93084-150">Contadores relacionados ao download de arquivos do catálogo de endereços.</span><span class="sxs-lookup"><span data-stu-id="93084-150">Address book file download related counters.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93084-151">Tentativa de chamadas WS do ABS</span><span class="sxs-lookup"><span data-stu-id="93084-151">ABS WS Calls attempted</span></span></p></td>
<td><p><span data-ttu-id="93084-152">Número total de tentativas de solicitações de serviço de consulta à Web do catálogo de endereços.</span><span class="sxs-lookup"><span data-stu-id="93084-152">Total number of Address Book Web Query service requests attempted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93084-153">Chamadas WS WS bem-sucedidas</span><span class="sxs-lookup"><span data-stu-id="93084-153">ABS WS Calls Succeeded</span></span></p></td>
<td><p><span data-ttu-id="93084-154">Número total de solicitações de serviço de consulta à Web do catálogo de endereços que retornaram um código de resposta bem-sucedido.</span><span class="sxs-lookup"><span data-stu-id="93084-154">Total number of Address Book Web Query service requests that returned a successful response code.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93084-155">Falha nas chamadas WS do ABS</span><span class="sxs-lookup"><span data-stu-id="93084-155">ABS WS Calls Failed</span></span></p></td>
<td><p><span data-ttu-id="93084-156">Número total de solicitações de serviço de consulta à Web do catálogo de endereços que retornaram um código de resposta de erro.</span><span class="sxs-lookup"><span data-stu-id="93084-156">Total number of Address Book Web Query service requests that returned an error response code.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="93084-157">**Informações da lista de distribuição (DL)**</span><span class="sxs-lookup"><span data-stu-id="93084-157">**Distribution List (DL) Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="93084-158"><strong>Contador de desempenho</strong></span><span class="sxs-lookup"><span data-stu-id="93084-158"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="93084-159"><strong>Descrição</strong></span><span class="sxs-lookup"><span data-stu-id="93084-159"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="93084-160">Tentativas de chamadas</span><span class="sxs-lookup"><span data-stu-id="93084-160">Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="93084-161">Número total de solicitações de serviço Web de expansão de lista de distribuição (DLX) tentadas.</span><span class="sxs-lookup"><span data-stu-id="93084-161">Total number of distribution list expansion (DLX) web service requests attempted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93084-162">Chamadas com êxito</span><span class="sxs-lookup"><span data-stu-id="93084-162">Calls Succeeded</span></span></p></td>
<td><p><span data-ttu-id="93084-163">Número total de solicitações de serviço Web do DLX que retornaram um código de resposta bem-sucedido.</span><span class="sxs-lookup"><span data-stu-id="93084-163">Total number of DLX web service requests that returned a successful response code.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93084-164">Chamadas com falha</span><span class="sxs-lookup"><span data-stu-id="93084-164">Calls Failed</span></span></p></td>
<td><p><span data-ttu-id="93084-165">Número total de solicitações de serviço Web do DLX que retornaram um código de resposta de erro.</span><span class="sxs-lookup"><span data-stu-id="93084-165">Total number of DLX web service requests that returned an error response code.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="93084-166">**Informações básicas de VoIP**</span><span class="sxs-lookup"><span data-stu-id="93084-166">**VoIP Basic Information**</span></span>

<span data-ttu-id="93084-167">Os contadores de desempenho listados abaixo relatam números para todas as chamadas de VoIP (voz sobre IP), incluindo chamadas para servidor de mediação, servidor de conferência A/V, servidor de borda, aplicativo de grupo de resposta e atendedor automático de conferência, quando esses cenários estão habilitados.</span><span class="sxs-lookup"><span data-stu-id="93084-167">The performance counters listed below report numbers for all Voice over IP (VoIP) calls, including calls to Mediation Server, A/V Conferencing Server, Edge Server, Response Group application, and Conference Auto Attendant, when these scenarios are enabled.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="93084-168"><strong>Contador de desempenho</strong></span><span class="sxs-lookup"><span data-stu-id="93084-168"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="93084-169"><strong>Descrição</strong></span><span class="sxs-lookup"><span data-stu-id="93084-169"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="93084-170">Chamadas ativas</span><span class="sxs-lookup"><span data-stu-id="93084-170">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="93084-171">Número total de chamadas de voz de entrada/saída em andamento no momento.</span><span class="sxs-lookup"><span data-stu-id="93084-171">Total number of incoming/outgoing voice calls ongoing currently.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93084-172">Chamadas terminadas</span><span class="sxs-lookup"><span data-stu-id="93084-172">Calls Terminated</span></span></p></td>
<td><p><span data-ttu-id="93084-173">Número total de chamadas de voz de entrada/saída já terminadas.</span><span class="sxs-lookup"><span data-stu-id="93084-173">Total number of incoming/outgoing voice calls already terminated.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93084-174">Chamadas recusadas</span><span class="sxs-lookup"><span data-stu-id="93084-174">Calls Declined</span></span></p></td>
<td><p><span data-ttu-id="93084-175">Número total de chamadas de voz de entrada recusadas.</span><span class="sxs-lookup"><span data-stu-id="93084-175">Total number of incoming voice calls declined.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93084-176">Tentativa de chamadas de entrada/saída</span><span class="sxs-lookup"><span data-stu-id="93084-176">Incoming/Outgoing Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="93084-177">Número total de chamadas de voz de entrada/saída tentadas.</span><span class="sxs-lookup"><span data-stu-id="93084-177">Total number of incoming/outgoing voice calls attempted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93084-178">Chamadas de entrada/saída estabelecidas</span><span class="sxs-lookup"><span data-stu-id="93084-178">Incoming/Outgoing Calls Established</span></span></p></td>
<td><p><span data-ttu-id="93084-179">Número total de chamadas de voz de entrada/saída estabelecidas.</span><span class="sxs-lookup"><span data-stu-id="93084-179">Total number of incoming/outgoing voice calls established.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93084-180">Chamadas recebidas NNN</span><span class="sxs-lookup"><span data-stu-id="93084-180">Calls Received NNN</span></span></p></td>
<td><p><span data-ttu-id="93084-181">Número total de códigos de resposta nnn recebidos do servidor.</span><span class="sxs-lookup"><span data-stu-id="93084-181">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93084-182">Taxa de aprovação de VoIP (%)</span><span class="sxs-lookup"><span data-stu-id="93084-182">VoIP Pass Rate (%)</span></span></p></td>
<td><p><span data-ttu-id="93084-183">Total de chamadas estabelecidas/total de chamadas tentadas.</span><span class="sxs-lookup"><span data-stu-id="93084-183">Total calls established/Total calls attempted.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="93084-184">**Informações de chamada do serviço de grupo de resposta**</span><span class="sxs-lookup"><span data-stu-id="93084-184">**Response Group service Call Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="93084-185"><strong>Contador de desempenho</strong></span><span class="sxs-lookup"><span data-stu-id="93084-185"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="93084-186"><strong>Descrição</strong></span><span class="sxs-lookup"><span data-stu-id="93084-186"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="93084-187">Chamadas ativas</span><span class="sxs-lookup"><span data-stu-id="93084-187">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="93084-188">Número total de chamadas ativas para o aplicativo grupo de resposta.</span><span class="sxs-lookup"><span data-stu-id="93084-188">Total number of active calls to the Response Group application.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93084-189">Tentativas de chamadas</span><span class="sxs-lookup"><span data-stu-id="93084-189">Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="93084-190">Número total de chamadas tentadas.</span><span class="sxs-lookup"><span data-stu-id="93084-190">Total number of calls attempted.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="93084-191">**Informações de chamada de mensagens instantâneas (IM)**</span><span class="sxs-lookup"><span data-stu-id="93084-191">**Instant Messaging (IM) Call Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="93084-192"><strong>Contador de desempenho</strong></span><span class="sxs-lookup"><span data-stu-id="93084-192"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="93084-193"><strong>Descrição</strong></span><span class="sxs-lookup"><span data-stu-id="93084-193"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="93084-194">Chamadas ativas</span><span class="sxs-lookup"><span data-stu-id="93084-194">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="93084-195">Número total de chamadas de mensagens instantâneas de entrada/saída contínuas.</span><span class="sxs-lookup"><span data-stu-id="93084-195">Total number of ongoing incoming/outgoing instant messaging calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93084-196">Chamadas terminadas</span><span class="sxs-lookup"><span data-stu-id="93084-196">Calls Terminated</span></span></p></td>
<td><p><span data-ttu-id="93084-197">Número total de chamadas de mensagens instantâneas de entrada/saída já terminadas.</span><span class="sxs-lookup"><span data-stu-id="93084-197">Total number of incoming/outgoing instant messaging calls already terminated.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93084-198">Chamadas recebidas NNN</span><span class="sxs-lookup"><span data-stu-id="93084-198">Calls Received NNN</span></span></p></td>
<td><p><span data-ttu-id="93084-199">Número total de códigos de resposta nnn recebidos do servidor.</span><span class="sxs-lookup"><span data-stu-id="93084-199">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93084-200">Mensagens IM recebidas/enviadas</span><span class="sxs-lookup"><span data-stu-id="93084-200">IM Messages Received/Sent</span></span></p></td>
<td><p><span data-ttu-id="93084-201">Número total de mensagens recebidas ou enviadas para todas as sessões.</span><span class="sxs-lookup"><span data-stu-id="93084-201">Total number of messages received or sent for all sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93084-202">Tentativa de chamadas de entrada/saída</span><span class="sxs-lookup"><span data-stu-id="93084-202">Incoming/Outgoing Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="93084-203">Número total de chamadas de mensagens instantâneas de entrada/saída tentadas.</span><span class="sxs-lookup"><span data-stu-id="93084-203">Total number of incoming/outgoing instant messaging calls attempted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93084-204">Chamadas de entrada/saída estabelecidas</span><span class="sxs-lookup"><span data-stu-id="93084-204">Incoming/Outgoing Calls Established</span></span></p></td>
<td><p><span data-ttu-id="93084-205">Número total de chamadas de mensagens instantâneas de entrada/saída estabelecidas.</span><span class="sxs-lookup"><span data-stu-id="93084-205">Total number of incoming/outgoing instant message calls established.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="93084-206">**Informações de chamada de compartilhamento de aplicativo**</span><span class="sxs-lookup"><span data-stu-id="93084-206">**App Sharing Call Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="93084-207"><strong>Contador de desempenho</strong></span><span class="sxs-lookup"><span data-stu-id="93084-207"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="93084-208"><strong>Descrição</strong></span><span class="sxs-lookup"><span data-stu-id="93084-208"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="93084-209">Chamadas ativas</span><span class="sxs-lookup"><span data-stu-id="93084-209">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="93084-210">Número total de chamadas de compartilhamento de aplicativo de entrada/saída em andamento.</span><span class="sxs-lookup"><span data-stu-id="93084-210">Total number of ongoing incoming/outgoing application sharing calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93084-211">Chamadas terminadas</span><span class="sxs-lookup"><span data-stu-id="93084-211">Calls Terminated</span></span></p></td>
<td><p><span data-ttu-id="93084-212">Número total de chamadas de compartilhamento de aplicativo de entrada/saída já terminadas.</span><span class="sxs-lookup"><span data-stu-id="93084-212">Total number of incoming/outgoing application sharing calls already terminated.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93084-213">Chamadas recebidas NNN</span><span class="sxs-lookup"><span data-stu-id="93084-213">Calls Received NNN</span></span></p></td>
<td><p><span data-ttu-id="93084-214">Número total de códigos de resposta nnn recebidos do servidor.</span><span class="sxs-lookup"><span data-stu-id="93084-214">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93084-215">Tentativa de chamadas de entrada/saída</span><span class="sxs-lookup"><span data-stu-id="93084-215">Incoming/Outgoing Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="93084-216">Número total de chamadas de compartilhamento de aplicativo de entrada/saída tentadas.</span><span class="sxs-lookup"><span data-stu-id="93084-216">Total number of incoming/outgoing application sharing calls attempted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93084-217">Chamadas de entrada/saída estabelecidas</span><span class="sxs-lookup"><span data-stu-id="93084-217">Incoming/Outgoing Calls Established</span></span></p></td>
<td><p><span data-ttu-id="93084-218">Número total de chamadas de compartilhamento de aplicativo de entrada/saída estabelecidas.</span><span class="sxs-lookup"><span data-stu-id="93084-218">Total number of incoming/outgoing application sharing calls established.</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="93084-219">**Informações de chamada CAA**</span><span class="sxs-lookup"><span data-stu-id="93084-219">**CAA Call Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="93084-220"><strong>Contador de desempenho</strong></span><span class="sxs-lookup"><span data-stu-id="93084-220"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="93084-221"><strong>Descrição</strong></span><span class="sxs-lookup"><span data-stu-id="93084-221"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="93084-222">Chamadas ativas</span><span class="sxs-lookup"><span data-stu-id="93084-222">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="93084-223">Número total de chamadas de rede telefônica pública comutada (PSTN) de entrada/saída em andamento no momento.</span><span class="sxs-lookup"><span data-stu-id="93084-223">Total number of incoming/outgoing public switched telephone network (PSTN) calls ongoing currently.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93084-224">Chamadas terminadas</span><span class="sxs-lookup"><span data-stu-id="93084-224">Calls Terminated</span></span></p></td>
<td><p><span data-ttu-id="93084-225">Número total de chamadas PSTN de entrada/saída já terminadas.</span><span class="sxs-lookup"><span data-stu-id="93084-225">Total number of incoming/outgoing PSTN calls already terminated.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93084-226">Tentativa de chamadas de entrada/saída</span><span class="sxs-lookup"><span data-stu-id="93084-226">Incoming/Outgoing Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="93084-227">Número total de chamadas PSTN de entrada/saída tentadas.</span><span class="sxs-lookup"><span data-stu-id="93084-227">Total number of incoming/outgoing PSTN calls attempted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93084-228">Chamadas de entrada/saída estabelecidas</span><span class="sxs-lookup"><span data-stu-id="93084-228">Incoming/Outgoing Calls Established</span></span></p></td>
<td><p><span data-ttu-id="93084-229">Número total de chamadas PSTN de entrada/saída estabelecidas.</span><span class="sxs-lookup"><span data-stu-id="93084-229">Total number of incoming/outgoing PSTN calls established.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="93084-230">**Informações de conferência**</span><span class="sxs-lookup"><span data-stu-id="93084-230">**Conference Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="93084-231"><strong>Contador de desempenho</strong></span><span class="sxs-lookup"><span data-stu-id="93084-231"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="93084-232"><strong>Descrição</strong></span><span class="sxs-lookup"><span data-stu-id="93084-232"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="93084-233">Conferências de mensagens instantâneas ativas</span><span class="sxs-lookup"><span data-stu-id="93084-233">Active Instant Messaging Conferences</span></span></p></td>
<td><p><span data-ttu-id="93084-234">Número total de conferências de mensagens instantâneas em andamento.</span><span class="sxs-lookup"><span data-stu-id="93084-234">Total number of ongoing instant messaging conferences.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93084-235">Conferências ativas de áudio/vídeo</span><span class="sxs-lookup"><span data-stu-id="93084-235">Active Audio/Video Conferences</span></span></p></td>
<td><p><span data-ttu-id="93084-236">Número total de conferências de áudio/vídeo (A/V) em andamento.</span><span class="sxs-lookup"><span data-stu-id="93084-236">Total number of ongoing audio/video (A/V) conferences.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93084-237">Conferências de compartilhamento de aplicativos ativos</span><span class="sxs-lookup"><span data-stu-id="93084-237">Active Application Sharing Conferences</span></span></p></td>
<td><p><span data-ttu-id="93084-238">Número total de conferências de compartilhamento de aplicativos contínuos.</span><span class="sxs-lookup"><span data-stu-id="93084-238">Total number of ongoing application sharing conferences.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93084-239">Número de participantes</span><span class="sxs-lookup"><span data-stu-id="93084-239">Number of Participants</span></span></p></td>
<td><p><span data-ttu-id="93084-240">Número total de participantes conectados atualmente a conferências.</span><span class="sxs-lookup"><span data-stu-id="93084-240">Total number of participants currently connected to conferences.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93084-241">Falha no agendamento da conferência</span><span class="sxs-lookup"><span data-stu-id="93084-241">Conference Schedule Failure</span></span></p></td>
<td><p><span data-ttu-id="93084-242">Número total de falhas ao tentar agendar uma conferência.</span><span class="sxs-lookup"><span data-stu-id="93084-242">Total number of failures while trying to schedule a conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93084-243">Falha de conferência de ingresso</span><span class="sxs-lookup"><span data-stu-id="93084-243">Join Conference Failure</span></span></p></td>
<td><p><span data-ttu-id="93084-244">Número total de falhas ao tentar se conectar a uma conferência.</span><span class="sxs-lookup"><span data-stu-id="93084-244">Total number of failures while trying to connect to a conference.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="93084-245">**Contadores do cliente UCWA**</span><span class="sxs-lookup"><span data-stu-id="93084-245">**UCWA Client Counters**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="93084-246"><strong>Contador de desempenho</strong></span><span class="sxs-lookup"><span data-stu-id="93084-246"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="93084-247"><strong>Descrição</strong></span><span class="sxs-lookup"><span data-stu-id="93084-247"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="93084-248">Número total de junções IMMCU com êxito</span><span class="sxs-lookup"><span data-stu-id="93084-248">Total Number of IMMCU Joins Succeeded</span></span></p></td>
<td><p><span data-ttu-id="93084-249">Número total de conferências de mensagens instantâneas Unidas.</span><span class="sxs-lookup"><span data-stu-id="93084-249">Total number of instant messaging conferences joined.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93084-250">Número total de junções DMCU com êxito</span><span class="sxs-lookup"><span data-stu-id="93084-250">Total Number of DMCU Joins Succeeded</span></span></p></td>
<td><p><span data-ttu-id="93084-251">Número total de conferências de A/V Unidas.</span><span class="sxs-lookup"><span data-stu-id="93084-251">Total number of A/V conferences joined.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

