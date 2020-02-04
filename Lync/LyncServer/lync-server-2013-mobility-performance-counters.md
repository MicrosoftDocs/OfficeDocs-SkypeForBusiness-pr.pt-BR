---
title: 'Lync Server 2013: contadores de desempenho da mobilidade'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Mobility performance counters
ms:assetid: d18ed85a-673d-4695-aa3f-ac83a38ab90a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690046(v=OCS.15)
ms:contentKeyID: 48185441
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 439c179476c89de8a5245e80e26586d42f4f6e3b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758683"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mobility-performance-counters-in-lync-server-2013"></a><span data-ttu-id="c6fb8-102">Contadores de desempenho de mobilidade no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c6fb8-102">Mobility performance counters in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c6fb8-103">_**Tópico da última modificação:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="c6fb8-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="c6fb8-104">As tabelas a seguir listam os nomes e descrições dos contadores de desempenho que você pode usar para monitorar servidores que executam a API da Web de comunicação unificada (UCWA) e o serviço de mobilidade do MCX do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c6fb8-104">The following tables list the names and descriptions of performance counters that you can use to monitor servers running the Unified Communications Web API (UCWA) and the Lync Server 2013 Mcx Mobility Service.</span></span>

<span data-ttu-id="c6fb8-105">O nome da categoria para os contadores na tabela UCWA é **LS:WEB – UCWA**.</span><span class="sxs-lookup"><span data-stu-id="c6fb8-105">The category name for the counters in the UCWA table is **LS:WEB – UCWA**.</span></span>

<span data-ttu-id="c6fb8-106">O nome da categoria para os contadores na tabela do Serviço de Mobilidade Mcx é **LS:WEB – Mobile Communication Service**.</span><span class="sxs-lookup"><span data-stu-id="c6fb8-106">The category name for the counters in the Mcx Mobility Service table is **LS:WEB - Mobile Communication Service**.</span></span>

<div>

## <a name="performance-counters-for-ucwa"></a><span data-ttu-id="c6fb8-107">Contadores de desempenho para UCWA</span><span class="sxs-lookup"><span data-stu-id="c6fb8-107">Performance Counters for UCWA</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c6fb8-108">Contador</span><span class="sxs-lookup"><span data-stu-id="c6fb8-108">Counter</span></span></th>
<th><span data-ttu-id="c6fb8-109">Descrição</span><span class="sxs-lookup"><span data-stu-id="c6fb8-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c6fb8-110">Contagem de aplicativos ativos</span><span class="sxs-lookup"><span data-stu-id="c6fb8-110">Active Application Count</span></span></p></td>
<td><p><span data-ttu-id="c6fb8-111">O número atual de aplicativos</span><span class="sxs-lookup"><span data-stu-id="c6fb8-111">The current number of applications</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6fb8-112">Contagem da modalidade de compartilhamento do aplicativo ativa</span><span class="sxs-lookup"><span data-stu-id="c6fb8-112">Active Application Sharing Modality Count</span></span></p></td>
<td><p><span data-ttu-id="c6fb8-113">O número atual da modalidade de compartilhamento do aplicativo</span><span class="sxs-lookup"><span data-stu-id="c6fb8-113">The current number of Application Sharing modality</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6fb8-114">Contagem da modalidade de áudio ativa</span><span class="sxs-lookup"><span data-stu-id="c6fb8-114">Active Audio Modality Count</span></span></p></td>
<td><p><span data-ttu-id="c6fb8-115">O número atual da modalidade de áudio</span><span class="sxs-lookup"><span data-stu-id="c6fb8-115">The current number of Audio modality</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6fb8-116">Contagem da modalidade de colaboração de dados ativa</span><span class="sxs-lookup"><span data-stu-id="c6fb8-116">Active Data Collaboration Modality Count</span></span></p></td>
<td><p><span data-ttu-id="c6fb8-117">O número atual da modalidade de colaboração de dados</span><span class="sxs-lookup"><span data-stu-id="c6fb8-117">The current number of Data Collaboration modality</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6fb8-118">Latência para baixar fotos do diretório ativo (ms)</span><span class="sxs-lookup"><span data-stu-id="c6fb8-118">Active Directory Photo Get Latency (ms)</span></span></p></td>
<td><p><span data-ttu-id="c6fb8-119">Esse contador mostra o tempo médio (em milissegundos) para obter uma foto do diretório ativo</span><span class="sxs-lookup"><span data-stu-id="c6fb8-119">This counter shows the average time (in milliseconds) to retrieve a photo from active directory</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6fb8-120">Contagem da modalidade de tráfego de mensagens ativa</span><span class="sxs-lookup"><span data-stu-id="c6fb8-120">Active Messaging Modality Count</span></span></p></td>
<td><p><span data-ttu-id="c6fb8-121">O número atual da modalidade de tráfego de mensagens</span><span class="sxs-lookup"><span data-stu-id="c6fb8-121">The current number of Messaging modality</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6fb8-122">Contagem da modalidade de vídeo panorâmico ativa</span><span class="sxs-lookup"><span data-stu-id="c6fb8-122">Active Panoramic Video Modality Count</span></span></p></td>
<td><p><span data-ttu-id="c6fb8-123">O número atual da modalidade de vídeo panorâmico</span><span class="sxs-lookup"><span data-stu-id="c6fb8-123">The current number of Panoramic Video modality</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6fb8-124">Contagem de downloads pendentes ativos</span><span class="sxs-lookup"><span data-stu-id="c6fb8-124">Active Pending Get Count</span></span></p></td>
<td><p><span data-ttu-id="c6fb8-125">O número de downloads pendentes atualmente ativos; conexões de longa duração com o servidor</span><span class="sxs-lookup"><span data-stu-id="c6fb8-125">The number of currently active pending gets; long-held connections to the server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6fb8-126">Contagem de sessões ativas</span><span class="sxs-lookup"><span data-stu-id="c6fb8-126">Active Session Count</span></span></p></td>
<td><p><span data-ttu-id="c6fb8-127">O número atual de pontos de extremidade registrados no UCWA por aplicativo e no total</span><span class="sxs-lookup"><span data-stu-id="c6fb8-127">The current number of endpoints registered in UCWA per application and total</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6fb8-128">Contagem de instâncias de usuário ativas</span><span class="sxs-lookup"><span data-stu-id="c6fb8-128">Active User Instance Count</span></span></p></td>
<td><p><span data-ttu-id="c6fb8-129">O número atual de instâncias de usuário ativas</span><span class="sxs-lookup"><span data-stu-id="c6fb8-129">The current number of user instances</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6fb8-130">Instâncias de usuário ativas sem aplicativo</span><span class="sxs-lookup"><span data-stu-id="c6fb8-130">Active User Instances without Application</span></span></p></td>
<td><p><span data-ttu-id="c6fb8-131">O número atual de instâncias de usuário sem aplicativo</span><span class="sxs-lookup"><span data-stu-id="c6fb8-131">The current number of user instances without application</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6fb8-132">Contagem da modalidade de vídeo ativa</span><span class="sxs-lookup"><span data-stu-id="c6fb8-132">Active Video Modality Count</span></span></p></td>
<td><p><span data-ttu-id="c6fb8-133">O número atual da modalidade de vídeo</span><span class="sxs-lookup"><span data-stu-id="c6fb8-133">The current number of Video modality</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6fb8-134">Solicitações de criação de aplicativo recebidas por segundo</span><span class="sxs-lookup"><span data-stu-id="c6fb8-134">Application Creation Requests Received/Second</span></span></p></td>
<td><p><span data-ttu-id="c6fb8-135">A taxa de solicitações de criação de aplicativo recebidas por segundo</span><span class="sxs-lookup"><span data-stu-id="c6fb8-135">The per second rate of received application creation requests</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6fb8-136">Falhas de entrada em MCU de AS</span><span class="sxs-lookup"><span data-stu-id="c6fb8-136">AS MCU Join Failures</span></span></p></td>
<td><p><span data-ttu-id="c6fb8-137">O número de falhas de entrada em MCU de AS</span><span class="sxs-lookup"><span data-stu-id="c6fb8-137">The number of AS MCU Join Failures</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6fb8-138">Falhas de entrada em MCU de AV</span><span class="sxs-lookup"><span data-stu-id="c6fb8-138">AV MCU Join Failures</span></span></p></td>
<td><p><span data-ttu-id="c6fb8-139">O número de falhas de entrada em MCU de AV</span><span class="sxs-lookup"><span data-stu-id="c6fb8-139">The number of AV MCU Join Failures</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6fb8-140">Tempo médio para inicialização do aplicativo (ms)</span><span class="sxs-lookup"><span data-stu-id="c6fb8-140">Average Application Startup Time (ms)</span></span></p></td>
<td><p><span data-ttu-id="c6fb8-141">O tempo médio para inicialização do aplicativo em milissegundos</span><span class="sxs-lookup"><span data-stu-id="c6fb8-141">The average application startup time in Milliseconds</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6fb8-142">Tempo médio de duração por sessão (ms)</span><span class="sxs-lookup"><span data-stu-id="c6fb8-142">Average Lifetime for Session (ms)</span></span></p></td>
<td><p><span data-ttu-id="c6fb8-143">O tempo médio de vida de uma sessão em milissegundos</span><span class="sxs-lookup"><span data-stu-id="c6fb8-143">The average lifetime for a session in milliseconds</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6fb8-144">Falhas de entrada em MCU de dados</span><span class="sxs-lookup"><span data-stu-id="c6fb8-144">Data MCU Join Failures</span></span></p></td>
<td><p><span data-ttu-id="c6fb8-145">O número de falhas de entrada em MCU de dados</span><span class="sxs-lookup"><span data-stu-id="c6fb8-145">The number of Data MCU Join Failures</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6fb8-146">Latência para pesquisa de contatos no Exchange (ms)</span><span class="sxs-lookup"><span data-stu-id="c6fb8-146">Exchange Contact Search Latency (ms)</span></span></p></td>
<td><p><span data-ttu-id="c6fb8-147">Esse contador mostra o tempo médio (em milissegundos) para se pesquisar contatos no Exchange</span><span class="sxs-lookup"><span data-stu-id="c6fb8-147">This counter shows the average time (in milliseconds) to search contact in Exchange</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6fb8-148">Latência para baixar fotos em HD no Exchange (ms)</span><span class="sxs-lookup"><span data-stu-id="c6fb8-148">Exchange HD Photo Get Latency (ms)</span></span></p></td>
<td><p><span data-ttu-id="c6fb8-149">Esse contador mostra o tempo médio (em milissegundos) para se baixar uma foto no Exchange</span><span class="sxs-lookup"><span data-stu-id="c6fb8-149">This counter shows the average time (in milliseconds) to retrieve a photo from Exchange</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6fb8-150">Respostas/segundo do HTTP 4xx</span><span class="sxs-lookup"><span data-stu-id="c6fb8-150">HTTP 4xx Responses/Second</span></span></p></td>
<td><p><span data-ttu-id="c6fb8-151">A taxa de respostas por segundo com o código HTTP 4xx</span><span class="sxs-lookup"><span data-stu-id="c6fb8-151">The per second rate of responses with HTTP 4xx code</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6fb8-152">Respostas/segundo do HTTP 5xx</span><span class="sxs-lookup"><span data-stu-id="c6fb8-152">HTTP 5xx Responses/Second</span></span></p></td>
<td><p><span data-ttu-id="c6fb8-153">A taxa de respostas por segundo com o código HTTP 5xx</span><span class="sxs-lookup"><span data-stu-id="c6fb8-153">The per second rate of responses with HTTP 5xx code</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6fb8-154">Falhas de entrada em MCU de IM</span><span class="sxs-lookup"><span data-stu-id="c6fb8-154">IM MCU Join Failures</span></span></p></td>
<td><p><span data-ttu-id="c6fb8-155">O número de falhas de entrada em MCU de IM</span><span class="sxs-lookup"><span data-stu-id="c6fb8-155">The number of IM MCU Join Failures</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6fb8-156">Número de falhas ao baixar fotos do Active Directory</span><span class="sxs-lookup"><span data-stu-id="c6fb8-156">Number of Active Directory Photo Get Failures</span></span></p></td>
<td><p><span data-ttu-id="c6fb8-157">O número total de falhas ao baixar fotos do Active Directory</span><span class="sxs-lookup"><span data-stu-id="c6fb8-157">The total number of failures to retrieve photos from Active Directory</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6fb8-158">Número de falhas ao pesquisar contatos</span><span class="sxs-lookup"><span data-stu-id="c6fb8-158">Number of Contact Search failures</span></span></p></td>
<td><p><span data-ttu-id="c6fb8-159">O número total de falhas ao pesquisar contatos no Exchange</span><span class="sxs-lookup"><span data-stu-id="c6fb8-159">The total number of failures to search contacts in Exchange</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6fb8-160">Número de falhas de desserialização</span><span class="sxs-lookup"><span data-stu-id="c6fb8-160">Number of Deserialization Failures</span></span></p></td>
<td><p><span data-ttu-id="c6fb8-161">O número total de falhas de desserialização</span><span class="sxs-lookup"><span data-stu-id="c6fb8-161">The total number of deserialization failures</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6fb8-162">Número de falhas de obtenção de foto HD</span><span class="sxs-lookup"><span data-stu-id="c6fb8-162">Number of HD Photo Get Failures</span></span></p></td>
<td><p><span data-ttu-id="c6fb8-163">O número total de falhas ao baixar fotos em HD do Exchange</span><span class="sxs-lookup"><span data-stu-id="c6fb8-163">The total number of failures to retrieve HD photos from Exchange</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6fb8-164">Excesso de inscrições por aplicativo</span><span class="sxs-lookup"><span data-stu-id="c6fb8-164">Over The Maximum Subscriptions Per Application</span></span></p></td>
<td><p><span data-ttu-id="c6fb8-165">O número de solicitações de inscrição além do máximo permitido por aplicativo</span><span class="sxs-lookup"><span data-stu-id="c6fb8-165">The number of Subscription requests over the maximum allowed per application</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6fb8-166">Excesso de inscrições por lote</span><span class="sxs-lookup"><span data-stu-id="c6fb8-166">Over The Maximum Subscriptions Per Batch</span></span></p></td>
<td><p><span data-ttu-id="c6fb8-167">O número de solicitações de inscrição além do máximo permitido por lote</span><span class="sxs-lookup"><span data-stu-id="c6fb8-167">The number of Subscription requests over the maximum allowed per batch</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6fb8-168">Falhas de inscrição de presença</span><span class="sxs-lookup"><span data-stu-id="c6fb8-168">Presence Subscription Failures</span></span></p></td>
<td><p><span data-ttu-id="c6fb8-169">O número de falhas ao realizar inscrições de presença</span><span class="sxs-lookup"><span data-stu-id="c6fb8-169">The number of failures to subscribe presence</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6fb8-170">Falhas ao se registrar pontos de extremidade</span><span class="sxs-lookup"><span data-stu-id="c6fb8-170">Registering Endpoint Failures</span></span></p></td>
<td><p><span data-ttu-id="c6fb8-171">O número de falhas ao se registrar pontos de extremidade</span><span class="sxs-lookup"><span data-stu-id="c6fb8-171">The number of failures to register endpoints</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6fb8-172">Solicitações recebidas/segundo</span><span class="sxs-lookup"><span data-stu-id="c6fb8-172">Requests Received/Second</span></span></p></td>
<td><p><span data-ttu-id="c6fb8-173">A taxa de solicitações recebidas por segundo</span><span class="sxs-lookup"><span data-stu-id="c6fb8-173">The per second rate of received requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6fb8-174">Solicitações bem-sucedidas/segundo</span><span class="sxs-lookup"><span data-stu-id="c6fb8-174">Requests Succeeded/Second</span></span></p></td>
<td><p><span data-ttu-id="c6fb8-175">A taxa por segundo de solicitações bem-sucedidas (códigos de resposta HTTP 2xx/3xx)</span><span class="sxs-lookup"><span data-stu-id="c6fb8-175">The per second rate of successful requests (HTTP 2xx/3xx response codes)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6fb8-176">Solicitações de criação de aplicativo bem-sucedidas/segundo</span><span class="sxs-lookup"><span data-stu-id="c6fb8-176">Succeeded Create Application Requests/Second</span></span></p></td>
<td><p><span data-ttu-id="c6fb8-177">A taxa de solicitações de criação de aplicativo bem-sucedidas por segundo</span><span class="sxs-lookup"><span data-stu-id="c6fb8-177">The per second rate of successful application creation requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6fb8-178">Contagem de downloads pendentes com tempo limite ultrapassado</span><span class="sxs-lookup"><span data-stu-id="c6fb8-178">Timed Out Pending Get Count</span></span></p></td>
<td><p><span data-ttu-id="c6fb8-179">O número de downloads pendentes que ultrapassaram o tempo limite</span><span class="sxs-lookup"><span data-stu-id="c6fb8-179">The number of pending gets that timed out</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6fb8-180">Total de solicitações de criação de aplicativo recebidas</span><span class="sxs-lookup"><span data-stu-id="c6fb8-180">Total Application Creation Requests Received</span></span></p></td>
<td><p><span data-ttu-id="c6fb8-181">O número total de solicitações de criação de aplicativo recebidas desde que o serviço foi iniciado</span><span class="sxs-lookup"><span data-stu-id="c6fb8-181">The total number of application creation requests received since the service was started</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6fb8-182">Total de respostas de HTTP 4xx</span><span class="sxs-lookup"><span data-stu-id="c6fb8-182">Total HTTP 4xx Responses</span></span></p></td>
<td><p><span data-ttu-id="c6fb8-183">O número total de respostas de HTTP 4xx</span><span class="sxs-lookup"><span data-stu-id="c6fb8-183">The total number of HTTP 4xx responses</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6fb8-184">Total de respostas de HTTP 5xx</span><span class="sxs-lookup"><span data-stu-id="c6fb8-184">Total HTTP 5xx Responses</span></span></p></td>
<td><p><span data-ttu-id="c6fb8-185">O número total de respostas de HTTP 5xx</span><span class="sxs-lookup"><span data-stu-id="c6fb8-185">The total number of HTTP 5xx responses</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6fb8-186">Total de solicitações recebidas no Canal de Comando</span><span class="sxs-lookup"><span data-stu-id="c6fb8-186">Total Requests Received on the Command Channel</span></span></p></td>
<td><p><span data-ttu-id="c6fb8-187">O número total de solicitações recebidas no canal do comando</span><span class="sxs-lookup"><span data-stu-id="c6fb8-187">The total number of requests received on the command channel</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6fb8-188">Total de solicitações bem-sucedidas</span><span class="sxs-lookup"><span data-stu-id="c6fb8-188">Total Requests Succeeded</span></span></p></td>
<td><p><span data-ttu-id="c6fb8-189">O número total de solicitações que tiveram êxito</span><span class="sxs-lookup"><span data-stu-id="c6fb8-189">The total number of requests that succeeded</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6fb8-190">Total de sessões iniciadas</span><span class="sxs-lookup"><span data-stu-id="c6fb8-190">Total Sessions Initiated</span></span></p></td>
<td><p><span data-ttu-id="c6fb8-191">O número total de sessões iniciadas desde a inicialização do serviço</span><span class="sxs-lookup"><span data-stu-id="c6fb8-191">The total number of sessions that were initiated since the service was started</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6fb8-192">Total de sessões encerradas devido ao tempo limite de ociosidade</span><span class="sxs-lookup"><span data-stu-id="c6fb8-192">Total Sessions Terminated Because of Idle Timeout</span></span></p></td>
<td><p><span data-ttu-id="c6fb8-193">O número total de sessões encerradas devido ao tempo limite de usuário ocioso</span><span class="sxs-lookup"><span data-stu-id="c6fb8-193">The total number of sessions that were terminated because of user idle timeout</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6fb8-194">Total de aplicativos limitados</span><span class="sxs-lookup"><span data-stu-id="c6fb8-194">Total Throttled Applications</span></span></p></td>
<td><p><span data-ttu-id="c6fb8-195">O número de aplicativos limitados</span><span class="sxs-lookup"><span data-stu-id="c6fb8-195">The number of throttled applications</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div id="sectionSection1" class="section">

### <a name="performance-counters-for-mcx-mobility-service"></a><span data-ttu-id="c6fb8-196">Contadores de desempenho para Mobility Service (Mcx)</span><span class="sxs-lookup"><span data-stu-id="c6fb8-196">Performance Counters for Mcx Mobility Service</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c6fb8-197">Contador</span><span class="sxs-lookup"><span data-stu-id="c6fb8-197">Counter</span></span></th>
<th><span data-ttu-id="c6fb8-198">Descrição</span><span class="sxs-lookup"><span data-stu-id="c6fb8-198">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c6fb8-199">Tempo médio de vida de uma sessão em milissegundos</span><span class="sxs-lookup"><span data-stu-id="c6fb8-199">Average Lifetime for a Session in Milliseconds</span></span></p></td>
<td><p><span data-ttu-id="c6fb8-200">O tempo médio de vida de uma sessão em milissegundos</span><span class="sxs-lookup"><span data-stu-id="c6fb8-200">The average lifetime for a session in milliseconds</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6fb8-201">Assinaturas atuais de notificação por push</span><span class="sxs-lookup"><span data-stu-id="c6fb8-201">Current Push Notification Subscriptions</span></span></p></td>
<td><p><span data-ttu-id="c6fb8-p101">O número atual de assinaturas de notificação por push. Esse número, em conjunto com a Contagem de sessões atualmente ativas, representam o subconjunto de sessões atualmente ativas registradas para dispositivos Windows Mobile ou iPhone.</span><span class="sxs-lookup"><span data-stu-id="c6fb8-p101">The current number of push notification subscriptions. This number, in conjunction with Currently Active Session Count, represents the subset of currently active sessions that are registered for Windows Mobile or iPhone devices.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6fb8-204">Contagem de polls de tempo limite de rede ativos no momento</span><span class="sxs-lookup"><span data-stu-id="c6fb8-204">Currently Active Network Timeout Poll Count</span></span></p></td>
<td><p><span data-ttu-id="c6fb8-205">O número de pools de rede que ultrapassaram o tempo limite</span><span class="sxs-lookup"><span data-stu-id="c6fb8-205">The number of network polls that timed out</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6fb8-206">Contagem de pools ativos no momento</span><span class="sxs-lookup"><span data-stu-id="c6fb8-206">Currently Active Poll Count</span></span></p></td>
<td><p><span data-ttu-id="c6fb8-207">O número de polls atualmente ativos (conexões de longa duração com o servidor)</span><span class="sxs-lookup"><span data-stu-id="c6fb8-207">The number of currently active polls (long-held connections to the server)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6fb8-208">Contagem de sessão ativa no momento</span><span class="sxs-lookup"><span data-stu-id="c6fb8-208">Currently Active Session Count</span></span></p></td>
<td><p><span data-ttu-id="c6fb8-209">Número atual de pontos de extremidade registrados no Mobility Service</span><span class="sxs-lookup"><span data-stu-id="c6fb8-209">Current number of endpoints registered in the Mobility Service</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6fb8-210">Contagem de sessão ativa no momento com assinaturas de presença ativa</span><span class="sxs-lookup"><span data-stu-id="c6fb8-210">Currently Active Session Count with Active Presence Subscriptions</span></span></p></td>
<td><p><span data-ttu-id="c6fb8-211">O número de sessões ativas no momento com assinaturas de presença ativa</span><span class="sxs-lookup"><span data-stu-id="c6fb8-211">The number of currently active sessions with active presence subscriptions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6fb8-212">Solicitações de notificação por push sem êxito/segundo</span><span class="sxs-lookup"><span data-stu-id="c6fb8-212">Push Notification Requests Failed/Second</span></span></p></td>
<td><p><span data-ttu-id="c6fb8-213">A taxa de notificações por push sem êxito por segundo</span><span class="sxs-lookup"><span data-stu-id="c6fb8-213">The per second rate of failed push notifications</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6fb8-214">Solicitações de notificação por push bem-sucedidas/segundo</span><span class="sxs-lookup"><span data-stu-id="c6fb8-214">Push Notification Requests Succeeded/Second</span></span></p></td>
<td><p><span data-ttu-id="c6fb8-215">A taxa de notificações por push bem-sucedidas por segundo</span><span class="sxs-lookup"><span data-stu-id="c6fb8-215">The per second rate of successful push notifications</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6fb8-216">Solicitações de notificação por push limitadas/segundo</span><span class="sxs-lookup"><span data-stu-id="c6fb8-216">Push Notification Requests Throttled/Second</span></span></p></td>
<td><p><span data-ttu-id="c6fb8-217">A taxa de notificações por push limitadas por segundo</span><span class="sxs-lookup"><span data-stu-id="c6fb8-217">The per second rate of throttled push notifications</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6fb8-218">Solicitações de notificação por push/segundo</span><span class="sxs-lookup"><span data-stu-id="c6fb8-218">Push Notification Requests/Second</span></span></p></td>
<td><p><span data-ttu-id="c6fb8-219">A taxa de notificações por push enviadas por segundo</span><span class="sxs-lookup"><span data-stu-id="c6fb8-219">The per second rate of sent push notifications</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6fb8-220">Solicitações sem êxito/segundo</span><span class="sxs-lookup"><span data-stu-id="c6fb8-220">Requests Failed/Second</span></span></p></td>
<td><p><span data-ttu-id="c6fb8-221">A taxa de solicitações sem êxito por segundo</span><span class="sxs-lookup"><span data-stu-id="c6fb8-221">The per second rate of failed requests</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6fb8-222">Solicitações recebidas/segundo</span><span class="sxs-lookup"><span data-stu-id="c6fb8-222">Requests Received/Second</span></span></p></td>
<td><p><span data-ttu-id="c6fb8-223">A taxa de solicitações recebidas por segundo</span><span class="sxs-lookup"><span data-stu-id="c6fb8-223">The per second rate of received requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6fb8-224">Solicitações rejeitadas/segundo</span><span class="sxs-lookup"><span data-stu-id="c6fb8-224">Requests Rejected/Second</span></span></p></td>
<td><p><span data-ttu-id="c6fb8-225">A taxa de solicitações receitadas por segundo</span><span class="sxs-lookup"><span data-stu-id="c6fb8-225">The per second rate of rejected requests</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6fb8-226">Solicitações bem-sucedidas/segundo</span><span class="sxs-lookup"><span data-stu-id="c6fb8-226">Requests Succeeded/Second</span></span></p></td>
<td><p><span data-ttu-id="c6fb8-227">A taxa de solicitações bem-sucedidas por segundo</span><span class="sxs-lookup"><span data-stu-id="c6fb8-227">The per second rate of successful requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6fb8-228">Solicitações de início de sessão bem-sucedidas/segundo</span><span class="sxs-lookup"><span data-stu-id="c6fb8-228">Succeeded Initiate Session Requests/Second</span></span></p></td>
<td><p><span data-ttu-id="c6fb8-p102">A taxa de solicitações de Obter localização bem-sucedidas por segundo. As solicitações de início de uma sessão consomem grande parte do CPU no servidor. A carga de pico suportada é de 12/segundo. A sustentabilidade depende de outras cargas no servidor. Iniciar uma sessão normalmente significa um logon de um usuário que ficou desconectado durante um período extenso de tempo.</span><span class="sxs-lookup"><span data-stu-id="c6fb8-p102">The per second rate of successful Get Location requests. Requests to initiate a session consume the most CPU on the server. Peak supported load is 12/second. Sustainability depends on other loads on the server. Initiate a session typically means a sign-in for a user that has been signed out for an extended period of time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6fb8-234">Total de chamadas de voz de entrada recusadas</span><span class="sxs-lookup"><span data-stu-id="c6fb8-234">Total Declined Inbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="c6fb8-235">O número total de chamadas de voz de entrada recusadas</span><span class="sxs-lookup"><span data-stu-id="c6fb8-235">The total number of inbound voice calls that were declined</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6fb8-236">Total de chamadas de voz de entrada sem êxito</span><span class="sxs-lookup"><span data-stu-id="c6fb8-236">Total Failed Inbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="c6fb8-237">O número total de chamadas de voz de entrada que não tiveram êxito</span><span class="sxs-lookup"><span data-stu-id="c6fb8-237">The total number of inbound voice calls that failed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6fb8-238">Total de chamadas de voz de saída sem êxito</span><span class="sxs-lookup"><span data-stu-id="c6fb8-238">Total Failed Outbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="c6fb8-239">O número total de chamadas de voz de saída que não tiveram êxito</span><span class="sxs-lookup"><span data-stu-id="c6fb8-239">The total number of outbound voice calls that failed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6fb8-240">Número total de sessões encerradas pelo usuário</span><span class="sxs-lookup"><span data-stu-id="c6fb8-240">Total number of sessions terminated by user</span></span></p></td>
<td><p><span data-ttu-id="c6fb8-241">O número total de sessões encerradas por usuários</span><span class="sxs-lookup"><span data-stu-id="c6fb8-241">The total number of sessions terminated by users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6fb8-242">Total de solicitações de notificação por push</span><span class="sxs-lookup"><span data-stu-id="c6fb8-242">Total Push Notification Requests</span></span></p></td>
<td><p><span data-ttu-id="c6fb8-243">O número total de solicitações de notificação por push</span><span class="sxs-lookup"><span data-stu-id="c6fb8-243">The total number of push notification requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6fb8-244">Total de solicitações de notificação por push em êxito</span><span class="sxs-lookup"><span data-stu-id="c6fb8-244">Total Push Notification Requests Failed</span></span></p></td>
<td><p><span data-ttu-id="c6fb8-245">O número total de solicitações de notificação por push que não tiveram êxito</span><span class="sxs-lookup"><span data-stu-id="c6fb8-245">The total number of push notification requests that failed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6fb8-246">Total de solicitações de notificação por push bem-sucedidas</span><span class="sxs-lookup"><span data-stu-id="c6fb8-246">Total Push Notification Requests Succeeded</span></span></p></td>
<td><p><span data-ttu-id="c6fb8-247">O número total de solicitações de notificação por push bem-sucedidas</span><span class="sxs-lookup"><span data-stu-id="c6fb8-247">The total number of push notification requests that were successful</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6fb8-248">Total de solicitações de notificação por push limitadas</span><span class="sxs-lookup"><span data-stu-id="c6fb8-248">Total Push Notification Requests Throttled</span></span></p></td>
<td><p><span data-ttu-id="c6fb8-249">O número total de solicitações de notificação por push limitadas</span><span class="sxs-lookup"><span data-stu-id="c6fb8-249">The total number of push notification requests that were throttled</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6fb8-250">Total de solicitações sem êxito</span><span class="sxs-lookup"><span data-stu-id="c6fb8-250">Total Requests Failed</span></span></p></td>
<td><p><span data-ttu-id="c6fb8-251">O número total de solicitações que não tiveram êxito</span><span class="sxs-lookup"><span data-stu-id="c6fb8-251">The total number of requests that failed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6fb8-252">Total de solicitações recebidas no Canal de Comando</span><span class="sxs-lookup"><span data-stu-id="c6fb8-252">Total Requests received on the Command Channel</span></span></p></td>
<td><p><span data-ttu-id="c6fb8-253">O número total de solicitações recebidas no canal do comando</span><span class="sxs-lookup"><span data-stu-id="c6fb8-253">The total number of requests received on the command channel</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6fb8-254">Total de solicitações rejeitadas</span><span class="sxs-lookup"><span data-stu-id="c6fb8-254">Total Requests Rejected</span></span></p></td>
<td><p><span data-ttu-id="c6fb8-255">O número total de solicitações rejeitadas</span><span class="sxs-lookup"><span data-stu-id="c6fb8-255">The total number of requests that were rejected</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6fb8-256">Total de solicitações bem-sucedidas</span><span class="sxs-lookup"><span data-stu-id="c6fb8-256">Total Requests Succeeded</span></span></p></td>
<td><p><span data-ttu-id="c6fb8-257">O número total de solicitações feitas ao Mobility Service que tiveram êxito</span><span class="sxs-lookup"><span data-stu-id="c6fb8-257">The total number of requests made to the Mobility Service that succeeded</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6fb8-258">Contagem total de sessões iniciadas</span><span class="sxs-lookup"><span data-stu-id="c6fb8-258">Total Session Initiated Count</span></span></p></td>
<td><p><span data-ttu-id="c6fb8-259">O número total de sessões iniciadas desde a inicialização do Mobility Service</span><span class="sxs-lookup"><span data-stu-id="c6fb8-259">The total number of sessions that were initiated since the Mobility Service was started</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6fb8-260">Total de sessões encerradas devido ao tempo limite de usuário ocioso</span><span class="sxs-lookup"><span data-stu-id="c6fb8-260">Total Sessions Terminated Because of User Idle Timeout</span></span></p></td>
<td><p><span data-ttu-id="c6fb8-261">O número total de sessões encerradas devido ao tempo limite de usuário ocioso</span><span class="sxs-lookup"><span data-stu-id="c6fb8-261">The total number of sessions that were terminated because of user idle timeout</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6fb8-262">Total de chamadas de voz de entrada bem-sucedidas</span><span class="sxs-lookup"><span data-stu-id="c6fb8-262">Total Successful Inbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="c6fb8-263">O número total de chamadas de voz de entrada que tiveram êxito</span><span class="sxs-lookup"><span data-stu-id="c6fb8-263">The total number of inbound voice calls that were successful</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6fb8-264">Total de chamadas de voz de saída bem-sucedidas</span><span class="sxs-lookup"><span data-stu-id="c6fb8-264">Total Successful Outbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="c6fb8-265">O número total de chamadas de voz de saída que tiveram êxito</span><span class="sxs-lookup"><span data-stu-id="c6fb8-265">The total number of outbound voice calls that were successful</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

