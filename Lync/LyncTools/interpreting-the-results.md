---
title: Interpretação dos resultados
description: Interpretação dos resultados.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Interpreting the Results
ms:assetid: dd7f199f-7075-4d88-bb84-49a7e05eb593
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945608(v=OCS.15)
ms:contentKeyID: 51541433
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b8342a1ec1e15e42852fc5293f87342e98587a60
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565337"
---
# <a name="interpreting-the-results"></a><span data-ttu-id="279c1-103">Interpretação dos resultados</span><span class="sxs-lookup"><span data-stu-id="279c1-103">Interpreting the Results</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="279c1-104">_**Última modificação do tópico:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="279c1-104">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="279c1-105">A ferramenta de estresse e desempenho do Lync Server 2013 (LyncPerfTool.exe) tem vários contadores que você pode usar para entender o que o cliente está fazendo e se ele está encontrando problemas.</span><span class="sxs-lookup"><span data-stu-id="279c1-105">The Lync Server 2013 Stress and Performance Tool (LyncPerfTool.exe) has many counters that you can use to understand what the client is doing and whether it is encountering issues.</span></span>

<div>

## <a name="client-counters"></a><span data-ttu-id="279c1-106">Contadores de cliente</span><span class="sxs-lookup"><span data-stu-id="279c1-106">Client Counters</span></span>

<span data-ttu-id="279c1-107">Cada instância do LyncPerfTool.exe que está sendo executada tem uma instância separada dos contadores.</span><span class="sxs-lookup"><span data-stu-id="279c1-107">Each instance of LyncPerfTool.exe that is running has a separate instance of the counters.</span></span> <span data-ttu-id="279c1-108">Cada instância é nomeada por ID de processo.</span><span class="sxs-lookup"><span data-stu-id="279c1-108">Each instance is named by its process ID.</span></span>

<span data-ttu-id="279c1-109">Se os clientes estiverem sobrecarregados, poderão ocorrer problemas.</span><span class="sxs-lookup"><span data-stu-id="279c1-109">If the clients are overloaded, issues can occur.</span></span> <span data-ttu-id="279c1-110">Para evitar esses problemas, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="279c1-110">To prevent these issues, do the following:</span></span>

1.  <span data-ttu-id="279c1-111">Monitore a CPU e o uso de memória nos computadores clientes.</span><span class="sxs-lookup"><span data-stu-id="279c1-111">Monitor the CPU and the memory usage on the client computers.</span></span> <span data-ttu-id="279c1-112">Se a CPU estiver consistentemente acima de 90%, reduza o número de usuários.</span><span class="sxs-lookup"><span data-stu-id="279c1-112">If the CPU is consistently above 90 percent, reduce the number of users.</span></span>

2.  <span data-ttu-id="279c1-113">Se o espaço de memória for alto, você poderá encontrar problemas se o arquivo de paginação não for grande o suficiente.</span><span class="sxs-lookup"><span data-stu-id="279c1-113">If the memory footprint is high, you could run into issues if the page file is not big enough.</span></span> <span data-ttu-id="279c1-114">Verifique se o encargo de confirmação não está atingindo o limite no computador.</span><span class="sxs-lookup"><span data-stu-id="279c1-114">Verify that the Commit Charge is not hitting the limit on the computer.</span></span> <span data-ttu-id="279c1-115">Se você estiver executando limites de memória, considere aumentar o tamanho do arquivo de paginação ou reduzir o número de usuários</span><span class="sxs-lookup"><span data-stu-id="279c1-115">If you are running into memory limits, consider increasing the page file size or reducing the number of users</span></span>

<span data-ttu-id="279c1-116">As tabelas a seguir listam os principais contadores de desempenho do LyncPerfTool.</span><span class="sxs-lookup"><span data-stu-id="279c1-116">The following tables list the key LyncPerfTool performance counters.</span></span>

<span data-ttu-id="279c1-117">**Informações gerais**</span><span class="sxs-lookup"><span data-stu-id="279c1-117">**General Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="279c1-118"><strong>Contador de desempenho</strong></span><span class="sxs-lookup"><span data-stu-id="279c1-118"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="279c1-119"><strong>Descrição</strong></span><span class="sxs-lookup"><span data-stu-id="279c1-119"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="279c1-120">Tempo gasto em minutos</span><span class="sxs-lookup"><span data-stu-id="279c1-120">Time Spent in Minutes</span></span></p></td>
<td><p><span data-ttu-id="279c1-121">Tempo gasto desde o início do processo.</span><span class="sxs-lookup"><span data-stu-id="279c1-121">Time spent since the process was started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="279c1-122">Pontos de extremidade ativos</span><span class="sxs-lookup"><span data-stu-id="279c1-122">Active Endpoints</span></span></p></td>
<td><p><span data-ttu-id="279c1-123">Número de pontos de extremidade conectados atualmente ao servidor.</span><span class="sxs-lookup"><span data-stu-id="279c1-123">Number of endpoints currently connected to the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="279c1-124">Logons com falha</span><span class="sxs-lookup"><span data-stu-id="279c1-124">Failed Logons</span></span></p></td>
<td><p><span data-ttu-id="279c1-125">Número total de falhas de entrada de ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="279c1-125">Total number of endpoint sign-in failures.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="279c1-126">Tentativas de logon</span><span class="sxs-lookup"><span data-stu-id="279c1-126">Logon Attempts</span></span></p></td>
<td><p><span data-ttu-id="279c1-127">Número total de tentativas de entrada de ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="279c1-127">Total number of endpoint sign-in attempts.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="279c1-128">Pontos de extremidade desconectados</span><span class="sxs-lookup"><span data-stu-id="279c1-128">Endpoints Disconnected</span></span></p></td>
<td><p><span data-ttu-id="279c1-129">Número total de pontos de extremidade que foram desconectados.</span><span class="sxs-lookup"><span data-stu-id="279c1-129">Total number of endpoints that have been disconnected.</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="279c1-130">**Informações de presença**</span><span class="sxs-lookup"><span data-stu-id="279c1-130">**Presence Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="279c1-131"><strong>Contador de desempenho</strong></span><span class="sxs-lookup"><span data-stu-id="279c1-131"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="279c1-132"><strong>Descrição</strong></span><span class="sxs-lookup"><span data-stu-id="279c1-132"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="279c1-133">Chamadas de setpresence</span><span class="sxs-lookup"><span data-stu-id="279c1-133">SetPresence Calls</span></span></p></td>
<td><p><span data-ttu-id="279c1-134">Número total de tentativas de alteração de presença.</span><span class="sxs-lookup"><span data-stu-id="279c1-134">Total number of presence change attempts.</span></span> <span data-ttu-id="279c1-135">Para diferentes tipos de alterações de presença, confira contador de desempenho de chamadas de setpresence (tipo de presença).</span><span class="sxs-lookup"><span data-stu-id="279c1-135">For different types of presence changes, see the SetPresence (Presence Type) Calls Performance Counter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="279c1-136">Respostas de NNN para setpresence</span><span class="sxs-lookup"><span data-stu-id="279c1-136">NNN Responses for SetPresence</span></span></p></td>
<td><p><span data-ttu-id="279c1-137">Número total de códigos de resposta nnn recebidos do servidor.</span><span class="sxs-lookup"><span data-stu-id="279c1-137">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="279c1-138">Chamadas de getpresence</span><span class="sxs-lookup"><span data-stu-id="279c1-138">GetPresence Calls</span></span></p></td>
<td><p><span data-ttu-id="279c1-139">Número total de tentativas de solicitação de presença de obtenção.</span><span class="sxs-lookup"><span data-stu-id="279c1-139">Total number of get presence request attempts.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="279c1-140">Respostas de NNN para getpresence</span><span class="sxs-lookup"><span data-stu-id="279c1-140">NNN Responses for GetPresence</span></span></p></td>
<td><p><span data-ttu-id="279c1-141">Número total de códigos de resposta nnn recebidos do servidor.</span><span class="sxs-lookup"><span data-stu-id="279c1-141">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="279c1-142">**Informações do serviço de catálogo de endereços**</span><span class="sxs-lookup"><span data-stu-id="279c1-142">**Address Book service Information**</span></span>

<span data-ttu-id="279c1-143">Esta categoria inclui contadores usados para monitorar downloads de arquivo do serviço de catálogo de endereços (ABS) e solicitações de serviço de consulta à Web do catálogo de endereços.</span><span class="sxs-lookup"><span data-stu-id="279c1-143">This category includes counters used to monitor Address Book service (ABS) file downloads and Address Book Web Query service requests.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="279c1-144"><strong>Contador de desempenho</strong></span><span class="sxs-lookup"><span data-stu-id="279c1-144"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="279c1-145"><strong>Descrição</strong></span><span class="sxs-lookup"><span data-stu-id="279c1-145"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="279c1-146">Tentativa de downloads de arquivo completo/Delta do ABS</span><span class="sxs-lookup"><span data-stu-id="279c1-146">ABS Full/Delta File Downloads Attempted</span></span></p></td>
<td><p><span data-ttu-id="279c1-147">Número total de solicitações de download de arquivo completo ou Delta tentadas.</span><span class="sxs-lookup"><span data-stu-id="279c1-147">Total number of full or delta file download requests attempted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="279c1-148">Downloads de arquivo completo/Delta do ABS bem-sucedido</span><span class="sxs-lookup"><span data-stu-id="279c1-148">ABS Full/Delta File Downloads Succeeded</span></span></p></td>
<td><p><span data-ttu-id="279c1-149">Número total de solicitações de download de arquivo completo ou Delta tentadas.</span><span class="sxs-lookup"><span data-stu-id="279c1-149">Total number of full or delta file download requests attempted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="279c1-150">Contadores relacionados ao serviço de consulta da Web do catálogo de endereços</span><span class="sxs-lookup"><span data-stu-id="279c1-150">Address Book Web Query service related counters</span></span></p></td>
<td><p><span data-ttu-id="279c1-151">Contadores relacionados ao download de arquivos do catálogo de endereços.</span><span class="sxs-lookup"><span data-stu-id="279c1-151">Address book file download related counters.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="279c1-152">Tentativa de chamadas WS do ABS</span><span class="sxs-lookup"><span data-stu-id="279c1-152">ABS WS Calls attempted</span></span></p></td>
<td><p><span data-ttu-id="279c1-153">Número total de tentativas de solicitações de serviço de consulta à Web do catálogo de endereços.</span><span class="sxs-lookup"><span data-stu-id="279c1-153">Total number of Address Book Web Query service requests attempted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="279c1-154">Chamadas WS WS bem-sucedidas</span><span class="sxs-lookup"><span data-stu-id="279c1-154">ABS WS Calls Succeeded</span></span></p></td>
<td><p><span data-ttu-id="279c1-155">Número total de solicitações de serviço de consulta à Web do catálogo de endereços que retornaram um código de resposta bem-sucedido.</span><span class="sxs-lookup"><span data-stu-id="279c1-155">Total number of Address Book Web Query service requests that returned a successful response code.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="279c1-156">Falha nas chamadas WS do ABS</span><span class="sxs-lookup"><span data-stu-id="279c1-156">ABS WS Calls Failed</span></span></p></td>
<td><p><span data-ttu-id="279c1-157">Número total de solicitações de serviço de consulta à Web do catálogo de endereços que retornaram um código de resposta de erro.</span><span class="sxs-lookup"><span data-stu-id="279c1-157">Total number of Address Book Web Query service requests that returned an error response code.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="279c1-158">**Informações da lista de distribuição (DL)**</span><span class="sxs-lookup"><span data-stu-id="279c1-158">**Distribution List (DL) Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="279c1-159"><strong>Contador de desempenho</strong></span><span class="sxs-lookup"><span data-stu-id="279c1-159"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="279c1-160"><strong>Descrição</strong></span><span class="sxs-lookup"><span data-stu-id="279c1-160"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="279c1-161">Tentativas de chamadas</span><span class="sxs-lookup"><span data-stu-id="279c1-161">Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="279c1-162">Número total de solicitações de serviço Web de expansão de lista de distribuição (DLX) tentadas.</span><span class="sxs-lookup"><span data-stu-id="279c1-162">Total number of distribution list expansion (DLX) web service requests attempted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="279c1-163">Chamadas com êxito</span><span class="sxs-lookup"><span data-stu-id="279c1-163">Calls Succeeded</span></span></p></td>
<td><p><span data-ttu-id="279c1-164">Número total de solicitações de serviço Web do DLX que retornaram um código de resposta bem-sucedido.</span><span class="sxs-lookup"><span data-stu-id="279c1-164">Total number of DLX web service requests that returned a successful response code.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="279c1-165">Chamadas com falha</span><span class="sxs-lookup"><span data-stu-id="279c1-165">Calls Failed</span></span></p></td>
<td><p><span data-ttu-id="279c1-166">Número total de solicitações de serviço Web do DLX que retornaram um código de resposta de erro.</span><span class="sxs-lookup"><span data-stu-id="279c1-166">Total number of DLX web service requests that returned an error response code.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="279c1-167">**Informações básicas de VoIP**</span><span class="sxs-lookup"><span data-stu-id="279c1-167">**VoIP Basic Information**</span></span>

<span data-ttu-id="279c1-168">Os contadores de desempenho listados abaixo relatam números para todas as chamadas de VoIP (voz sobre IP), incluindo chamadas para servidor de mediação, servidor de conferência A/V, servidor de borda, aplicativo de grupo de resposta e atendedor automático de conferência, quando esses cenários estão habilitados.</span><span class="sxs-lookup"><span data-stu-id="279c1-168">The performance counters listed below report numbers for all Voice over IP (VoIP) calls, including calls to Mediation Server, A/V Conferencing Server, Edge Server, Response Group application, and Conference Auto Attendant, when these scenarios are enabled.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="279c1-169"><strong>Contador de desempenho</strong></span><span class="sxs-lookup"><span data-stu-id="279c1-169"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="279c1-170"><strong>Descrição</strong></span><span class="sxs-lookup"><span data-stu-id="279c1-170"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="279c1-171">Chamadas ativas</span><span class="sxs-lookup"><span data-stu-id="279c1-171">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="279c1-172">Número total de chamadas de voz de entrada/saída em andamento no momento.</span><span class="sxs-lookup"><span data-stu-id="279c1-172">Total number of incoming/outgoing voice calls ongoing currently.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="279c1-173">Chamadas terminadas</span><span class="sxs-lookup"><span data-stu-id="279c1-173">Calls Terminated</span></span></p></td>
<td><p><span data-ttu-id="279c1-174">Número total de chamadas de voz de entrada/saída já terminadas.</span><span class="sxs-lookup"><span data-stu-id="279c1-174">Total number of incoming/outgoing voice calls already terminated.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="279c1-175">Chamadas recusadas</span><span class="sxs-lookup"><span data-stu-id="279c1-175">Calls Declined</span></span></p></td>
<td><p><span data-ttu-id="279c1-176">Número total de chamadas de voz de entrada recusadas.</span><span class="sxs-lookup"><span data-stu-id="279c1-176">Total number of incoming voice calls declined.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="279c1-177">Tentativa de chamadas de entrada/saída</span><span class="sxs-lookup"><span data-stu-id="279c1-177">Incoming/Outgoing Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="279c1-178">Número total de chamadas de voz de entrada/saída tentadas.</span><span class="sxs-lookup"><span data-stu-id="279c1-178">Total number of incoming/outgoing voice calls attempted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="279c1-179">Chamadas de entrada/saída estabelecidas</span><span class="sxs-lookup"><span data-stu-id="279c1-179">Incoming/Outgoing Calls Established</span></span></p></td>
<td><p><span data-ttu-id="279c1-180">Número total de chamadas de voz de entrada/saída estabelecidas.</span><span class="sxs-lookup"><span data-stu-id="279c1-180">Total number of incoming/outgoing voice calls established.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="279c1-181">Chamadas recebidas NNN</span><span class="sxs-lookup"><span data-stu-id="279c1-181">Calls Received NNN</span></span></p></td>
<td><p><span data-ttu-id="279c1-182">Número total de códigos de resposta nnn recebidos do servidor.</span><span class="sxs-lookup"><span data-stu-id="279c1-182">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="279c1-183">Taxa de aprovação de VoIP (%)</span><span class="sxs-lookup"><span data-stu-id="279c1-183">VoIP Pass Rate (%)</span></span></p></td>
<td><p><span data-ttu-id="279c1-184">Total de chamadas estabelecidas/total de chamadas tentadas.</span><span class="sxs-lookup"><span data-stu-id="279c1-184">Total calls established/Total calls attempted.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="279c1-185">**Informações de chamada do serviço de grupo de resposta**</span><span class="sxs-lookup"><span data-stu-id="279c1-185">**Response Group service Call Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="279c1-186"><strong>Contador de desempenho</strong></span><span class="sxs-lookup"><span data-stu-id="279c1-186"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="279c1-187"><strong>Descrição</strong></span><span class="sxs-lookup"><span data-stu-id="279c1-187"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="279c1-188">Chamadas ativas</span><span class="sxs-lookup"><span data-stu-id="279c1-188">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="279c1-189">Número total de chamadas ativas para o aplicativo grupo de resposta.</span><span class="sxs-lookup"><span data-stu-id="279c1-189">Total number of active calls to the Response Group application.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="279c1-190">Tentativas de chamadas</span><span class="sxs-lookup"><span data-stu-id="279c1-190">Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="279c1-191">Número total de chamadas tentadas.</span><span class="sxs-lookup"><span data-stu-id="279c1-191">Total number of calls attempted.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="279c1-192">**Informações de chamada de mensagens instantâneas (IM)**</span><span class="sxs-lookup"><span data-stu-id="279c1-192">**Instant Messaging (IM) Call Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="279c1-193"><strong>Contador de desempenho</strong></span><span class="sxs-lookup"><span data-stu-id="279c1-193"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="279c1-194"><strong>Descrição</strong></span><span class="sxs-lookup"><span data-stu-id="279c1-194"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="279c1-195">Chamadas ativas</span><span class="sxs-lookup"><span data-stu-id="279c1-195">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="279c1-196">Número total de chamadas de mensagens instantâneas de entrada/saída contínuas.</span><span class="sxs-lookup"><span data-stu-id="279c1-196">Total number of ongoing incoming/outgoing instant messaging calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="279c1-197">Chamadas terminadas</span><span class="sxs-lookup"><span data-stu-id="279c1-197">Calls Terminated</span></span></p></td>
<td><p><span data-ttu-id="279c1-198">Número total de chamadas de mensagens instantâneas de entrada/saída já terminadas.</span><span class="sxs-lookup"><span data-stu-id="279c1-198">Total number of incoming/outgoing instant messaging calls already terminated.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="279c1-199">Chamadas recebidas NNN</span><span class="sxs-lookup"><span data-stu-id="279c1-199">Calls Received NNN</span></span></p></td>
<td><p><span data-ttu-id="279c1-200">Número total de códigos de resposta nnn recebidos do servidor.</span><span class="sxs-lookup"><span data-stu-id="279c1-200">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="279c1-201">Mensagens IM recebidas/enviadas</span><span class="sxs-lookup"><span data-stu-id="279c1-201">IM Messages Received/Sent</span></span></p></td>
<td><p><span data-ttu-id="279c1-202">Número total de mensagens recebidas ou enviadas para todas as sessões.</span><span class="sxs-lookup"><span data-stu-id="279c1-202">Total number of messages received or sent for all sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="279c1-203">Tentativa de chamadas de entrada/saída</span><span class="sxs-lookup"><span data-stu-id="279c1-203">Incoming/Outgoing Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="279c1-204">Número total de chamadas de mensagens instantâneas de entrada/saída tentadas.</span><span class="sxs-lookup"><span data-stu-id="279c1-204">Total number of incoming/outgoing instant messaging calls attempted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="279c1-205">Chamadas de entrada/saída estabelecidas</span><span class="sxs-lookup"><span data-stu-id="279c1-205">Incoming/Outgoing Calls Established</span></span></p></td>
<td><p><span data-ttu-id="279c1-206">Número total de chamadas de mensagens instantâneas de entrada/saída estabelecidas.</span><span class="sxs-lookup"><span data-stu-id="279c1-206">Total number of incoming/outgoing instant message calls established.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="279c1-207">**Informações de chamada de compartilhamento de aplicativo**</span><span class="sxs-lookup"><span data-stu-id="279c1-207">**App Sharing Call Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="279c1-208"><strong>Contador de desempenho</strong></span><span class="sxs-lookup"><span data-stu-id="279c1-208"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="279c1-209"><strong>Descrição</strong></span><span class="sxs-lookup"><span data-stu-id="279c1-209"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="279c1-210">Chamadas ativas</span><span class="sxs-lookup"><span data-stu-id="279c1-210">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="279c1-211">Número total de chamadas de compartilhamento de aplicativo de entrada/saída em andamento.</span><span class="sxs-lookup"><span data-stu-id="279c1-211">Total number of ongoing incoming/outgoing application sharing calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="279c1-212">Chamadas terminadas</span><span class="sxs-lookup"><span data-stu-id="279c1-212">Calls Terminated</span></span></p></td>
<td><p><span data-ttu-id="279c1-213">Número total de chamadas de compartilhamento de aplicativo de entrada/saída já terminadas.</span><span class="sxs-lookup"><span data-stu-id="279c1-213">Total number of incoming/outgoing application sharing calls already terminated.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="279c1-214">Chamadas recebidas NNN</span><span class="sxs-lookup"><span data-stu-id="279c1-214">Calls Received NNN</span></span></p></td>
<td><p><span data-ttu-id="279c1-215">Número total de códigos de resposta nnn recebidos do servidor.</span><span class="sxs-lookup"><span data-stu-id="279c1-215">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="279c1-216">Tentativa de chamadas de entrada/saída</span><span class="sxs-lookup"><span data-stu-id="279c1-216">Incoming/Outgoing Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="279c1-217">Número total de chamadas de compartilhamento de aplicativo de entrada/saída tentadas.</span><span class="sxs-lookup"><span data-stu-id="279c1-217">Total number of incoming/outgoing application sharing calls attempted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="279c1-218">Chamadas de entrada/saída estabelecidas</span><span class="sxs-lookup"><span data-stu-id="279c1-218">Incoming/Outgoing Calls Established</span></span></p></td>
<td><p><span data-ttu-id="279c1-219">Número total de chamadas de compartilhamento de aplicativo de entrada/saída estabelecidas.</span><span class="sxs-lookup"><span data-stu-id="279c1-219">Total number of incoming/outgoing application sharing calls established.</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="279c1-220">**Informações de chamada CAA**</span><span class="sxs-lookup"><span data-stu-id="279c1-220">**CAA Call Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="279c1-221"><strong>Contador de desempenho</strong></span><span class="sxs-lookup"><span data-stu-id="279c1-221"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="279c1-222"><strong>Descrição</strong></span><span class="sxs-lookup"><span data-stu-id="279c1-222"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="279c1-223">Chamadas ativas</span><span class="sxs-lookup"><span data-stu-id="279c1-223">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="279c1-224">Número total de chamadas de rede telefônica pública comutada (PSTN) de entrada/saída em andamento no momento.</span><span class="sxs-lookup"><span data-stu-id="279c1-224">Total number of incoming/outgoing public switched telephone network (PSTN) calls ongoing currently.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="279c1-225">Chamadas terminadas</span><span class="sxs-lookup"><span data-stu-id="279c1-225">Calls Terminated</span></span></p></td>
<td><p><span data-ttu-id="279c1-226">Número total de chamadas PSTN de entrada/saída já terminadas.</span><span class="sxs-lookup"><span data-stu-id="279c1-226">Total number of incoming/outgoing PSTN calls already terminated.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="279c1-227">Tentativa de chamadas de entrada/saída</span><span class="sxs-lookup"><span data-stu-id="279c1-227">Incoming/Outgoing Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="279c1-228">Número total de chamadas PSTN de entrada/saída tentadas.</span><span class="sxs-lookup"><span data-stu-id="279c1-228">Total number of incoming/outgoing PSTN calls attempted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="279c1-229">Chamadas de entrada/saída estabelecidas</span><span class="sxs-lookup"><span data-stu-id="279c1-229">Incoming/Outgoing Calls Established</span></span></p></td>
<td><p><span data-ttu-id="279c1-230">Número total de chamadas PSTN de entrada/saída estabelecidas.</span><span class="sxs-lookup"><span data-stu-id="279c1-230">Total number of incoming/outgoing PSTN calls established.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="279c1-231">**Informações de conferência**</span><span class="sxs-lookup"><span data-stu-id="279c1-231">**Conference Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="279c1-232"><strong>Contador de desempenho</strong></span><span class="sxs-lookup"><span data-stu-id="279c1-232"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="279c1-233"><strong>Descrição</strong></span><span class="sxs-lookup"><span data-stu-id="279c1-233"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="279c1-234">Conferências de mensagens instantâneas ativas</span><span class="sxs-lookup"><span data-stu-id="279c1-234">Active Instant Messaging Conferences</span></span></p></td>
<td><p><span data-ttu-id="279c1-235">Número total de conferências de mensagens instantâneas em andamento.</span><span class="sxs-lookup"><span data-stu-id="279c1-235">Total number of ongoing instant messaging conferences.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="279c1-236">Conferências ativas de áudio/vídeo</span><span class="sxs-lookup"><span data-stu-id="279c1-236">Active Audio/Video Conferences</span></span></p></td>
<td><p><span data-ttu-id="279c1-237">Número total de conferências de áudio/vídeo (A/V) em andamento.</span><span class="sxs-lookup"><span data-stu-id="279c1-237">Total number of ongoing audio/video (A/V) conferences.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="279c1-238">Conferências de compartilhamento de aplicativos ativos</span><span class="sxs-lookup"><span data-stu-id="279c1-238">Active Application Sharing Conferences</span></span></p></td>
<td><p><span data-ttu-id="279c1-239">Número total de conferências de compartilhamento de aplicativos contínuos.</span><span class="sxs-lookup"><span data-stu-id="279c1-239">Total number of ongoing application sharing conferences.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="279c1-240">Número de participantes</span><span class="sxs-lookup"><span data-stu-id="279c1-240">Number of Participants</span></span></p></td>
<td><p><span data-ttu-id="279c1-241">Número total de participantes conectados atualmente a conferências.</span><span class="sxs-lookup"><span data-stu-id="279c1-241">Total number of participants currently connected to conferences.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="279c1-242">Falha no agendamento da conferência</span><span class="sxs-lookup"><span data-stu-id="279c1-242">Conference Schedule Failure</span></span></p></td>
<td><p><span data-ttu-id="279c1-243">Número total de falhas ao tentar agendar uma conferência.</span><span class="sxs-lookup"><span data-stu-id="279c1-243">Total number of failures while trying to schedule a conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="279c1-244">Falha de conferência de ingresso</span><span class="sxs-lookup"><span data-stu-id="279c1-244">Join Conference Failure</span></span></p></td>
<td><p><span data-ttu-id="279c1-245">Número total de falhas ao tentar se conectar a uma conferência.</span><span class="sxs-lookup"><span data-stu-id="279c1-245">Total number of failures while trying to connect to a conference.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="279c1-246">**Contadores do cliente UCWA**</span><span class="sxs-lookup"><span data-stu-id="279c1-246">**UCWA Client Counters**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="279c1-247"><strong>Contador de desempenho</strong></span><span class="sxs-lookup"><span data-stu-id="279c1-247"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="279c1-248"><strong>Descrição</strong></span><span class="sxs-lookup"><span data-stu-id="279c1-248"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="279c1-249">Número total de junções IMMCU com êxito</span><span class="sxs-lookup"><span data-stu-id="279c1-249">Total Number of IMMCU Joins Succeeded</span></span></p></td>
<td><p><span data-ttu-id="279c1-250">Número total de conferências de mensagens instantâneas Unidas.</span><span class="sxs-lookup"><span data-stu-id="279c1-250">Total number of instant messaging conferences joined.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="279c1-251">Número total de junções DMCU com êxito</span><span class="sxs-lookup"><span data-stu-id="279c1-251">Total Number of DMCU Joins Succeeded</span></span></p></td>
<td><p><span data-ttu-id="279c1-252">Número total de conferências de A/V Unidas.</span><span class="sxs-lookup"><span data-stu-id="279c1-252">Total number of A/V conferences joined.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

