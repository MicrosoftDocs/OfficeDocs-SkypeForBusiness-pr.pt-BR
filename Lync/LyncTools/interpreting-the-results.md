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
ms.openlocfilehash: 0dcb1d84392cf9f56f2996281eb53e798690ba1e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763293"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="interpreting-the-results"></a><span data-ttu-id="aa0b4-102">Interpretação dos resultados</span><span class="sxs-lookup"><span data-stu-id="aa0b4-102">Interpreting the Results</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aa0b4-103">_**Tópico da última modificação:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="aa0b4-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="aa0b4-104">A ferramenta de stress e desempenho do Lync Server 2013 (LyncPerfTool. exe) tem muitos contadores que você pode usar para compreender o que o cliente está fazendo e se está encontrando problemas.</span><span class="sxs-lookup"><span data-stu-id="aa0b4-104">The Lync Server 2013 Stress and Performance Tool (LyncPerfTool.exe) has many counters that you can use to understand what the client is doing and whether it is encountering issues.</span></span>

<div>

## <a name="client-counters"></a><span data-ttu-id="aa0b4-105">Contadores de cliente</span><span class="sxs-lookup"><span data-stu-id="aa0b4-105">Client Counters</span></span>

<span data-ttu-id="aa0b4-106">Cada instância do LyncPerfTool. exe que está sendo executada tem uma instância separada dos contadores.</span><span class="sxs-lookup"><span data-stu-id="aa0b4-106">Each instance of LyncPerfTool.exe that is running has a separate instance of the counters.</span></span> <span data-ttu-id="aa0b4-107">Cada instância é nomeada pela ID do processo.</span><span class="sxs-lookup"><span data-stu-id="aa0b4-107">Each instance is named by its process ID.</span></span>

<span data-ttu-id="aa0b4-108">Se os clientes estiverem sobrecarregados, podem ocorrer problemas.</span><span class="sxs-lookup"><span data-stu-id="aa0b4-108">If the clients are overloaded, issues can occur.</span></span> <span data-ttu-id="aa0b4-109">Para evitar esses problemas, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="aa0b4-109">To prevent these issues, do the following:</span></span>

1.  <span data-ttu-id="aa0b4-110">Monitore a CPU e o uso da memória nos computadores cliente.</span><span class="sxs-lookup"><span data-stu-id="aa0b4-110">Monitor the CPU and the memory usage on the client computers.</span></span> <span data-ttu-id="aa0b4-111">Se a CPU estiver consistentemente acima de 90%, reduza o número de usuários.</span><span class="sxs-lookup"><span data-stu-id="aa0b4-111">If the CPU is consistently above 90 percent, reduce the number of users.</span></span>

2.  <span data-ttu-id="aa0b4-112">Se o espaço da memória for alto, você poderá ter problemas se o arquivo da página não for grande o suficiente.</span><span class="sxs-lookup"><span data-stu-id="aa0b4-112">If the memory footprint is high, you could run into issues if the page file is not big enough.</span></span> <span data-ttu-id="aa0b4-113">Verifique se a carga comprometida não está atingindo o limite do computador.</span><span class="sxs-lookup"><span data-stu-id="aa0b4-113">Verify that the Commit Charge is not hitting the limit on the computer.</span></span> <span data-ttu-id="aa0b4-114">Se você estiver executando limites de memória, considere aumentar o tamanho do arquivo da página ou reduzir o número de usuários</span><span class="sxs-lookup"><span data-stu-id="aa0b4-114">If you are running into memory limits, consider increasing the page file size or reducing the number of users</span></span>

<span data-ttu-id="aa0b4-115">As tabelas a seguir listam os principais contadores de desempenho do LyncPerfTool.</span><span class="sxs-lookup"><span data-stu-id="aa0b4-115">The following tables list the key LyncPerfTool performance counters.</span></span>

<span data-ttu-id="aa0b4-116">**Informações gerais**</span><span class="sxs-lookup"><span data-stu-id="aa0b4-116">**General Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="aa0b4-117"><strong>Contador de desempenho</strong></span><span class="sxs-lookup"><span data-stu-id="aa0b4-117"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="aa0b4-118"><strong>Descrição</strong></span><span class="sxs-lookup"><span data-stu-id="aa0b4-118"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="aa0b4-119">Tempo gasto em minutos</span><span class="sxs-lookup"><span data-stu-id="aa0b4-119">Time Spent in Minutes</span></span></p></td>
<td><p><span data-ttu-id="aa0b4-120">Tempo gasto desde o início do processo.</span><span class="sxs-lookup"><span data-stu-id="aa0b4-120">Time spent since the process was started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa0b4-121">Pontos de extremidade ativos</span><span class="sxs-lookup"><span data-stu-id="aa0b4-121">Active Endpoints</span></span></p></td>
<td><p><span data-ttu-id="aa0b4-122">Número de pontos de extremidade conectados ao servidor no momento.</span><span class="sxs-lookup"><span data-stu-id="aa0b4-122">Number of endpoints currently connected to the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aa0b4-123">Logons com falha</span><span class="sxs-lookup"><span data-stu-id="aa0b4-123">Failed Logons</span></span></p></td>
<td><p><span data-ttu-id="aa0b4-124">Número total de falhas de entrada de ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="aa0b4-124">Total number of endpoint sign-in failures.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa0b4-125">Tentativas de logon</span><span class="sxs-lookup"><span data-stu-id="aa0b4-125">Logon Attempts</span></span></p></td>
<td><p><span data-ttu-id="aa0b4-126">Número total de tentativas de entrada no ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="aa0b4-126">Total number of endpoint sign-in attempts.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aa0b4-127">Pontos de extremidade desconectados</span><span class="sxs-lookup"><span data-stu-id="aa0b4-127">Endpoints Disconnected</span></span></p></td>
<td><p><span data-ttu-id="aa0b4-128">Número total de pontos de extremidade desconectados.</span><span class="sxs-lookup"><span data-stu-id="aa0b4-128">Total number of endpoints that have been disconnected.</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="aa0b4-129">**Informações de presença**</span><span class="sxs-lookup"><span data-stu-id="aa0b4-129">**Presence Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="aa0b4-130"><strong>Contador de desempenho</strong></span><span class="sxs-lookup"><span data-stu-id="aa0b4-130"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="aa0b4-131"><strong>Descrição</strong></span><span class="sxs-lookup"><span data-stu-id="aa0b4-131"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="aa0b4-132">Chamadas de presença</span><span class="sxs-lookup"><span data-stu-id="aa0b4-132">SetPresence Calls</span></span></p></td>
<td><p><span data-ttu-id="aa0b4-133">Número total de tentativas de alteração de presença.</span><span class="sxs-lookup"><span data-stu-id="aa0b4-133">Total number of presence change attempts.</span></span> <span data-ttu-id="aa0b4-134">Para diferentes tipos de alterações de presença, consulte o contador de desempenho de chamadas de presença (tipo de presença).</span><span class="sxs-lookup"><span data-stu-id="aa0b4-134">For different types of presence changes, see the SetPresence (Presence Type) Calls Performance Counter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa0b4-135">Respostas de NNN para setpresence</span><span class="sxs-lookup"><span data-stu-id="aa0b4-135">NNN Responses for SetPresence</span></span></p></td>
<td><p><span data-ttu-id="aa0b4-136">Número total de códigos de resposta de nnn recebidos do servidor.</span><span class="sxs-lookup"><span data-stu-id="aa0b4-136">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aa0b4-137">Chamadas de getpresence</span><span class="sxs-lookup"><span data-stu-id="aa0b4-137">GetPresence Calls</span></span></p></td>
<td><p><span data-ttu-id="aa0b4-138">Número total de tentativas de obter solicitação de presença.</span><span class="sxs-lookup"><span data-stu-id="aa0b4-138">Total number of get presence request attempts.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa0b4-139">Respostas NNN para getpresence</span><span class="sxs-lookup"><span data-stu-id="aa0b4-139">NNN Responses for GetPresence</span></span></p></td>
<td><p><span data-ttu-id="aa0b4-140">Número total de códigos de resposta de nnn recebidos do servidor.</span><span class="sxs-lookup"><span data-stu-id="aa0b4-140">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="aa0b4-141">**Informações do serviço de catálogo de endereços**</span><span class="sxs-lookup"><span data-stu-id="aa0b4-141">**Address Book service Information**</span></span>

<span data-ttu-id="aa0b4-142">Esta categoria inclui contadores usados para monitorar downloads de arquivos do serviço de catálogo de endereços (ABS) e catálogo de endereços da Web consulta de serviço.</span><span class="sxs-lookup"><span data-stu-id="aa0b4-142">This category includes counters used to monitor Address Book service (ABS) file downloads and Address Book Web Query service requests.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="aa0b4-143"><strong>Contador de desempenho</strong></span><span class="sxs-lookup"><span data-stu-id="aa0b4-143"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="aa0b4-144"><strong>Descrição</strong></span><span class="sxs-lookup"><span data-stu-id="aa0b4-144"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="aa0b4-145">Tentativas de download de arquivo completo/Delta da ABS</span><span class="sxs-lookup"><span data-stu-id="aa0b4-145">ABS Full/Delta File Downloads Attempted</span></span></p></td>
<td><p><span data-ttu-id="aa0b4-146">Número total de solicitações de download de arquivos completas ou Delta tentadas.</span><span class="sxs-lookup"><span data-stu-id="aa0b4-146">Total number of full or delta file download requests attempted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa0b4-147">Downloads de arquivo completo/Delta do ABS bem-sucedido</span><span class="sxs-lookup"><span data-stu-id="aa0b4-147">ABS Full/Delta File Downloads Succeeded</span></span></p></td>
<td><p><span data-ttu-id="aa0b4-148">Número total de solicitações de download de arquivos completas ou Delta tentadas.</span><span class="sxs-lookup"><span data-stu-id="aa0b4-148">Total number of full or delta file download requests attempted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aa0b4-149">Contadores relacionados ao serviço de consulta na Web do catálogo de endereços</span><span class="sxs-lookup"><span data-stu-id="aa0b4-149">Address Book Web Query service related counters</span></span></p></td>
<td><p><span data-ttu-id="aa0b4-150">Contadores relacionados ao download de arquivos do catálogo de endereços.</span><span class="sxs-lookup"><span data-stu-id="aa0b4-150">Address book file download related counters.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa0b4-151">Chamadas de WS WS tentadas</span><span class="sxs-lookup"><span data-stu-id="aa0b4-151">ABS WS Calls attempted</span></span></p></td>
<td><p><span data-ttu-id="aa0b4-152">Número total de tentativas de solicitações de serviço de consulta à Web do catálogo de endereços.</span><span class="sxs-lookup"><span data-stu-id="aa0b4-152">Total number of Address Book Web Query service requests attempted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aa0b4-153">Chamadas do WS para ABS bem-sucedidas</span><span class="sxs-lookup"><span data-stu-id="aa0b4-153">ABS WS Calls Succeeded</span></span></p></td>
<td><p><span data-ttu-id="aa0b4-154">Número total de solicitações de serviço de consulta à Web do catálogo de endereços que retornaram um código de resposta bem-sucedido.</span><span class="sxs-lookup"><span data-stu-id="aa0b4-154">Total number of Address Book Web Query service requests that returned a successful response code.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa0b4-155">Falha nas chamadas ABS WS</span><span class="sxs-lookup"><span data-stu-id="aa0b4-155">ABS WS Calls Failed</span></span></p></td>
<td><p><span data-ttu-id="aa0b4-156">Número total de solicitações de serviço de consulta à Web do catálogo de endereços que retornaram um código de resposta de erro.</span><span class="sxs-lookup"><span data-stu-id="aa0b4-156">Total number of Address Book Web Query service requests that returned an error response code.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="aa0b4-157">**Informações de lista de distribuição (DL)**</span><span class="sxs-lookup"><span data-stu-id="aa0b4-157">**Distribution List (DL) Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="aa0b4-158"><strong>Contador de desempenho</strong></span><span class="sxs-lookup"><span data-stu-id="aa0b4-158"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="aa0b4-159"><strong>Descrição</strong></span><span class="sxs-lookup"><span data-stu-id="aa0b4-159"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="aa0b4-160">Chamadas tentadas</span><span class="sxs-lookup"><span data-stu-id="aa0b4-160">Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="aa0b4-161">Número total de solicitações de serviço Web de expansão da lista de distribuição (DLX) tentadas.</span><span class="sxs-lookup"><span data-stu-id="aa0b4-161">Total number of distribution list expansion (DLX) web service requests attempted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa0b4-162">Chamadas com êxito</span><span class="sxs-lookup"><span data-stu-id="aa0b4-162">Calls Succeeded</span></span></p></td>
<td><p><span data-ttu-id="aa0b4-163">Número total de solicitações de serviço Web DLX que retornaram um código de resposta bem-sucedido.</span><span class="sxs-lookup"><span data-stu-id="aa0b4-163">Total number of DLX web service requests that returned a successful response code.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aa0b4-164">Falha nas chamadas</span><span class="sxs-lookup"><span data-stu-id="aa0b4-164">Calls Failed</span></span></p></td>
<td><p><span data-ttu-id="aa0b4-165">Número total de solicitações de serviço Web DLX que retornaram um código de resposta de erro.</span><span class="sxs-lookup"><span data-stu-id="aa0b4-165">Total number of DLX web service requests that returned an error response code.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="aa0b4-166">**Informações básicas de VoIP**</span><span class="sxs-lookup"><span data-stu-id="aa0b4-166">**VoIP Basic Information**</span></span>

<span data-ttu-id="aa0b4-167">Os contadores de desempenho listados abaixo numeram os números de todas as chamadas de voz sobre IP (VoIP), incluindo chamadas para servidor de mediação, servidor de conferência A/V, servidor de borda, aplicativo de grupo de resposta e atendedor automático de conferência, quando esses cenários são habilitados.</span><span class="sxs-lookup"><span data-stu-id="aa0b4-167">The performance counters listed below report numbers for all Voice over IP (VoIP) calls, including calls to Mediation Server, A/V Conferencing Server, Edge Server, Response Group application, and Conference Auto Attendant, when these scenarios are enabled.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="aa0b4-168"><strong>Contador de desempenho</strong></span><span class="sxs-lookup"><span data-stu-id="aa0b4-168"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="aa0b4-169"><strong>Descrição</strong></span><span class="sxs-lookup"><span data-stu-id="aa0b4-169"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="aa0b4-170">Chamadas ativas</span><span class="sxs-lookup"><span data-stu-id="aa0b4-170">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="aa0b4-171">Número total de chamadas de voz de entrada/saída em andamento no momento.</span><span class="sxs-lookup"><span data-stu-id="aa0b4-171">Total number of incoming/outgoing voice calls ongoing currently.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa0b4-172">Chamadas terminadas</span><span class="sxs-lookup"><span data-stu-id="aa0b4-172">Calls Terminated</span></span></p></td>
<td><p><span data-ttu-id="aa0b4-173">Número total de chamadas de voz de entrada/saída já terminadas.</span><span class="sxs-lookup"><span data-stu-id="aa0b4-173">Total number of incoming/outgoing voice calls already terminated.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aa0b4-174">Chamadas recusadas</span><span class="sxs-lookup"><span data-stu-id="aa0b4-174">Calls Declined</span></span></p></td>
<td><p><span data-ttu-id="aa0b4-175">Número total de chamadas de voz recebidas recusadas.</span><span class="sxs-lookup"><span data-stu-id="aa0b4-175">Total number of incoming voice calls declined.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa0b4-176">Tentativa de fazer chamadas de entrada/saída</span><span class="sxs-lookup"><span data-stu-id="aa0b4-176">Incoming/Outgoing Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="aa0b4-177">Número total de chamadas de voz de entrada/saída tentadas.</span><span class="sxs-lookup"><span data-stu-id="aa0b4-177">Total number of incoming/outgoing voice calls attempted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aa0b4-178">Chamadas de entrada/saída estabelecidas</span><span class="sxs-lookup"><span data-stu-id="aa0b4-178">Incoming/Outgoing Calls Established</span></span></p></td>
<td><p><span data-ttu-id="aa0b4-179">Número total de chamadas de voz de entrada/saída estabelecidas.</span><span class="sxs-lookup"><span data-stu-id="aa0b4-179">Total number of incoming/outgoing voice calls established.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa0b4-180">Chamadas recebidas NNN</span><span class="sxs-lookup"><span data-stu-id="aa0b4-180">Calls Received NNN</span></span></p></td>
<td><p><span data-ttu-id="aa0b4-181">Número total de códigos de resposta de nnn recebidos do servidor.</span><span class="sxs-lookup"><span data-stu-id="aa0b4-181">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aa0b4-182">Taxa de aprovação de VoIP (%)</span><span class="sxs-lookup"><span data-stu-id="aa0b4-182">VoIP Pass Rate (%)</span></span></p></td>
<td><p><span data-ttu-id="aa0b4-183">Total de chamadas estabelecidas/total de chamadas tentadas.</span><span class="sxs-lookup"><span data-stu-id="aa0b4-183">Total calls established/Total calls attempted.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="aa0b4-184">**Informações de chamada do serviço de grupo de resposta**</span><span class="sxs-lookup"><span data-stu-id="aa0b4-184">**Response Group service Call Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="aa0b4-185"><strong>Contador de desempenho</strong></span><span class="sxs-lookup"><span data-stu-id="aa0b4-185"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="aa0b4-186"><strong>Descrição</strong></span><span class="sxs-lookup"><span data-stu-id="aa0b4-186"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="aa0b4-187">Chamadas ativas</span><span class="sxs-lookup"><span data-stu-id="aa0b4-187">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="aa0b4-188">Número total de chamadas ativas para o aplicativo de grupo de resposta.</span><span class="sxs-lookup"><span data-stu-id="aa0b4-188">Total number of active calls to the Response Group application.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa0b4-189">Chamadas tentadas</span><span class="sxs-lookup"><span data-stu-id="aa0b4-189">Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="aa0b4-190">Número total de chamadas tentadas.</span><span class="sxs-lookup"><span data-stu-id="aa0b4-190">Total number of calls attempted.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="aa0b4-191">**Informações de chamada de mensagens instantâneas (IM)**</span><span class="sxs-lookup"><span data-stu-id="aa0b4-191">**Instant Messaging (IM) Call Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="aa0b4-192"><strong>Contador de desempenho</strong></span><span class="sxs-lookup"><span data-stu-id="aa0b4-192"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="aa0b4-193"><strong>Descrição</strong></span><span class="sxs-lookup"><span data-stu-id="aa0b4-193"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="aa0b4-194">Chamadas ativas</span><span class="sxs-lookup"><span data-stu-id="aa0b4-194">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="aa0b4-195">Número total de chamadas de mensagens instantâneas de entrada/saída contínuas.</span><span class="sxs-lookup"><span data-stu-id="aa0b4-195">Total number of ongoing incoming/outgoing instant messaging calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa0b4-196">Chamadas terminadas</span><span class="sxs-lookup"><span data-stu-id="aa0b4-196">Calls Terminated</span></span></p></td>
<td><p><span data-ttu-id="aa0b4-197">Número total de chamadas de entrada/saída de mensagens instantâneas já terminadas.</span><span class="sxs-lookup"><span data-stu-id="aa0b4-197">Total number of incoming/outgoing instant messaging calls already terminated.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aa0b4-198">Chamadas recebidas NNN</span><span class="sxs-lookup"><span data-stu-id="aa0b4-198">Calls Received NNN</span></span></p></td>
<td><p><span data-ttu-id="aa0b4-199">Número total de códigos de resposta de nnn recebidos do servidor.</span><span class="sxs-lookup"><span data-stu-id="aa0b4-199">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa0b4-200">Mensagens INSTANTÂNEAs recebidas/enviadas</span><span class="sxs-lookup"><span data-stu-id="aa0b4-200">IM Messages Received/Sent</span></span></p></td>
<td><p><span data-ttu-id="aa0b4-201">Número total de mensagens recebidas ou enviadas para todas as sessões.</span><span class="sxs-lookup"><span data-stu-id="aa0b4-201">Total number of messages received or sent for all sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aa0b4-202">Tentativa de fazer chamadas de entrada/saída</span><span class="sxs-lookup"><span data-stu-id="aa0b4-202">Incoming/Outgoing Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="aa0b4-203">Número total de tentativas de entrada/saída de mensagens instantâneas feitas.</span><span class="sxs-lookup"><span data-stu-id="aa0b4-203">Total number of incoming/outgoing instant messaging calls attempted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa0b4-204">Chamadas de entrada/saída estabelecidas</span><span class="sxs-lookup"><span data-stu-id="aa0b4-204">Incoming/Outgoing Calls Established</span></span></p></td>
<td><p><span data-ttu-id="aa0b4-205">Número total de chamadas de entrada/saída de mensagens instantâneas estabelecidas.</span><span class="sxs-lookup"><span data-stu-id="aa0b4-205">Total number of incoming/outgoing instant message calls established.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="aa0b4-206">**Informações de chamada de compartilhamento de aplicativo**</span><span class="sxs-lookup"><span data-stu-id="aa0b4-206">**App Sharing Call Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="aa0b4-207"><strong>Contador de desempenho</strong></span><span class="sxs-lookup"><span data-stu-id="aa0b4-207"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="aa0b4-208"><strong>Descrição</strong></span><span class="sxs-lookup"><span data-stu-id="aa0b4-208"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="aa0b4-209">Chamadas ativas</span><span class="sxs-lookup"><span data-stu-id="aa0b4-209">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="aa0b4-210">Número total de chamadas de compartilhamento de aplicativo de entrada/saída contínuas.</span><span class="sxs-lookup"><span data-stu-id="aa0b4-210">Total number of ongoing incoming/outgoing application sharing calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa0b4-211">Chamadas terminadas</span><span class="sxs-lookup"><span data-stu-id="aa0b4-211">Calls Terminated</span></span></p></td>
<td><p><span data-ttu-id="aa0b4-212">Número total de chamadas de compartilhamento de aplicativo de entrada/saída já terminadas.</span><span class="sxs-lookup"><span data-stu-id="aa0b4-212">Total number of incoming/outgoing application sharing calls already terminated.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aa0b4-213">Chamadas recebidas NNN</span><span class="sxs-lookup"><span data-stu-id="aa0b4-213">Calls Received NNN</span></span></p></td>
<td><p><span data-ttu-id="aa0b4-214">Número total de códigos de resposta de nnn recebidos do servidor.</span><span class="sxs-lookup"><span data-stu-id="aa0b4-214">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa0b4-215">Tentativa de fazer chamadas de entrada/saída</span><span class="sxs-lookup"><span data-stu-id="aa0b4-215">Incoming/Outgoing Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="aa0b4-216">Número total de chamadas de compartilhamento de aplicativo de entrada/saída tentadas.</span><span class="sxs-lookup"><span data-stu-id="aa0b4-216">Total number of incoming/outgoing application sharing calls attempted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aa0b4-217">Chamadas de entrada/saída estabelecidas</span><span class="sxs-lookup"><span data-stu-id="aa0b4-217">Incoming/Outgoing Calls Established</span></span></p></td>
<td><p><span data-ttu-id="aa0b4-218">Número total de chamadas de compartilhamento de aplicativo de entrada/saída estabelecidas.</span><span class="sxs-lookup"><span data-stu-id="aa0b4-218">Total number of incoming/outgoing application sharing calls established.</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="aa0b4-219">**Informações de chamada do CAA**</span><span class="sxs-lookup"><span data-stu-id="aa0b4-219">**CAA Call Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="aa0b4-220"><strong>Contador de desempenho</strong></span><span class="sxs-lookup"><span data-stu-id="aa0b4-220"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="aa0b4-221"><strong>Descrição</strong></span><span class="sxs-lookup"><span data-stu-id="aa0b4-221"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="aa0b4-222">Chamadas ativas</span><span class="sxs-lookup"><span data-stu-id="aa0b4-222">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="aa0b4-223">Número total de chamadas em PSTN (rede telefônica pública comutada) de entrada/saída em andamento no momento.</span><span class="sxs-lookup"><span data-stu-id="aa0b4-223">Total number of incoming/outgoing public switched telephone network (PSTN) calls ongoing currently.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa0b4-224">Chamadas terminadas</span><span class="sxs-lookup"><span data-stu-id="aa0b4-224">Calls Terminated</span></span></p></td>
<td><p><span data-ttu-id="aa0b4-225">Número total de chamadas PSTN de entrada/saída já terminadas.</span><span class="sxs-lookup"><span data-stu-id="aa0b4-225">Total number of incoming/outgoing PSTN calls already terminated.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aa0b4-226">Tentativa de fazer chamadas de entrada/saída</span><span class="sxs-lookup"><span data-stu-id="aa0b4-226">Incoming/Outgoing Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="aa0b4-227">Número total de chamadas de entrada PSTN de entrada/saída tentadas.</span><span class="sxs-lookup"><span data-stu-id="aa0b4-227">Total number of incoming/outgoing PSTN calls attempted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa0b4-228">Chamadas de entrada/saída estabelecidas</span><span class="sxs-lookup"><span data-stu-id="aa0b4-228">Incoming/Outgoing Calls Established</span></span></p></td>
<td><p><span data-ttu-id="aa0b4-229">Número total de chamadas PSTN de entrada/saída estabelecidas.</span><span class="sxs-lookup"><span data-stu-id="aa0b4-229">Total number of incoming/outgoing PSTN calls established.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="aa0b4-230">**Informações de conferência**</span><span class="sxs-lookup"><span data-stu-id="aa0b4-230">**Conference Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="aa0b4-231"><strong>Contador de desempenho</strong></span><span class="sxs-lookup"><span data-stu-id="aa0b4-231"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="aa0b4-232"><strong>Descrição</strong></span><span class="sxs-lookup"><span data-stu-id="aa0b4-232"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="aa0b4-233">Conferências de mensagens instantâneas ativas</span><span class="sxs-lookup"><span data-stu-id="aa0b4-233">Active Instant Messaging Conferences</span></span></p></td>
<td><p><span data-ttu-id="aa0b4-234">Número total de conferências de mensagens instantâneas em andamento.</span><span class="sxs-lookup"><span data-stu-id="aa0b4-234">Total number of ongoing instant messaging conferences.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa0b4-235">Conferências de áudio/vídeo ativas</span><span class="sxs-lookup"><span data-stu-id="aa0b4-235">Active Audio/Video Conferences</span></span></p></td>
<td><p><span data-ttu-id="aa0b4-236">Número total de conferências contínuas de áudio/vídeo (A/V).</span><span class="sxs-lookup"><span data-stu-id="aa0b4-236">Total number of ongoing audio/video (A/V) conferences.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aa0b4-237">Conferências de compartilhamento de aplicativos ativos</span><span class="sxs-lookup"><span data-stu-id="aa0b4-237">Active Application Sharing Conferences</span></span></p></td>
<td><p><span data-ttu-id="aa0b4-238">Número total de conferências de compartilhamento de aplicativos contínuas.</span><span class="sxs-lookup"><span data-stu-id="aa0b4-238">Total number of ongoing application sharing conferences.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa0b4-239">Número de participantes</span><span class="sxs-lookup"><span data-stu-id="aa0b4-239">Number of Participants</span></span></p></td>
<td><p><span data-ttu-id="aa0b4-240">Número total de participantes atualmente conectados a conferências.</span><span class="sxs-lookup"><span data-stu-id="aa0b4-240">Total number of participants currently connected to conferences.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aa0b4-241">Falha no cronograma da conferência</span><span class="sxs-lookup"><span data-stu-id="aa0b4-241">Conference Schedule Failure</span></span></p></td>
<td><p><span data-ttu-id="aa0b4-242">Número total de falhas ao tentar agendar uma conferência.</span><span class="sxs-lookup"><span data-stu-id="aa0b4-242">Total number of failures while trying to schedule a conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa0b4-243">Ingressar na falha na conferência</span><span class="sxs-lookup"><span data-stu-id="aa0b4-243">Join Conference Failure</span></span></p></td>
<td><p><span data-ttu-id="aa0b4-244">Número total de falhas ao tentar se conectar a uma conferência.</span><span class="sxs-lookup"><span data-stu-id="aa0b4-244">Total number of failures while trying to connect to a conference.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="aa0b4-245">**Contadores do cliente UCWA**</span><span class="sxs-lookup"><span data-stu-id="aa0b4-245">**UCWA Client Counters**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="aa0b4-246"><strong>Contador de desempenho</strong></span><span class="sxs-lookup"><span data-stu-id="aa0b4-246"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="aa0b4-247"><strong>Descrição</strong></span><span class="sxs-lookup"><span data-stu-id="aa0b4-247"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="aa0b4-248">Número total de junções de IMMCU bem-sucedida</span><span class="sxs-lookup"><span data-stu-id="aa0b4-248">Total Number of IMMCU Joins Succeeded</span></span></p></td>
<td><p><span data-ttu-id="aa0b4-249">Número total de conferências de mensagens instantâneas Unidas.</span><span class="sxs-lookup"><span data-stu-id="aa0b4-249">Total number of instant messaging conferences joined.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa0b4-250">Número total de junções de DMCU bem-sucedida</span><span class="sxs-lookup"><span data-stu-id="aa0b4-250">Total Number of DMCU Joins Succeeded</span></span></p></td>
<td><p><span data-ttu-id="aa0b4-251">Número total de conferências de A/V Unidas.</span><span class="sxs-lookup"><span data-stu-id="aa0b4-251">Total number of A/V conferences joined.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

