---
title: 'Lync Server 2013: contadores de desempenho de mobilidade'
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
ms.openlocfilehash: 56454e4ea4fa1498dc73056d5b5f01193b007352
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006147"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mobility-performance-counters-in-lync-server-2013"></a><span data-ttu-id="45217-102">Contadores de desempenho de mobilidade no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="45217-102">Mobility performance counters in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="45217-103">_**Última modificação do tópico:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="45217-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="45217-104">As tabelas a seguir listam os nomes e as descrições dos contadores de desempenho que você pode usar para monitorar servidores que executam a UCWA (Unified Communications Web API) e o serviço de mobilidade do Lync Server 2013 MCX.</span><span class="sxs-lookup"><span data-stu-id="45217-104">The following tables list the names and descriptions of performance counters that you can use to monitor servers running the Unified Communications Web API (UCWA) and the Lync Server 2013 Mcx Mobility Service.</span></span>

<span data-ttu-id="45217-105">O nome da categoria para os contadores na tabela UCWA é **ls: Web – UCWA**.</span><span class="sxs-lookup"><span data-stu-id="45217-105">The category name for the counters in the UCWA table is **LS:WEB – UCWA**.</span></span>

<span data-ttu-id="45217-106">O nome da categoria para os contadores na tabela de serviço de mobilidade do MCX é **ls: Web-Mobile Communication Service**.</span><span class="sxs-lookup"><span data-stu-id="45217-106">The category name for the counters in the Mcx Mobility Service table is **LS:WEB - Mobile Communication Service**.</span></span>

<div>

## <a name="performance-counters-for-ucwa"></a><span data-ttu-id="45217-107">Contadores de desempenho para UCWA</span><span class="sxs-lookup"><span data-stu-id="45217-107">Performance Counters for UCWA</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="45217-108">Contador</span><span class="sxs-lookup"><span data-stu-id="45217-108">Counter</span></span></th>
<th><span data-ttu-id="45217-109">Descrição</span><span class="sxs-lookup"><span data-stu-id="45217-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="45217-110">Contagem de aplicativos ativos</span><span class="sxs-lookup"><span data-stu-id="45217-110">Active Application Count</span></span></p></td>
<td><p><span data-ttu-id="45217-111">O número atual de aplicativos</span><span class="sxs-lookup"><span data-stu-id="45217-111">The current number of applications</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45217-112">Contagem de modalidades de compartilhamento de aplicativos ativos</span><span class="sxs-lookup"><span data-stu-id="45217-112">Active Application Sharing Modality Count</span></span></p></td>
<td><p><span data-ttu-id="45217-113">O número atual da modalidade de compartilhamento de aplicativos</span><span class="sxs-lookup"><span data-stu-id="45217-113">The current number of Application Sharing modality</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45217-114">Contagem de modalidade de áudio ativa</span><span class="sxs-lookup"><span data-stu-id="45217-114">Active Audio Modality Count</span></span></p></td>
<td><p><span data-ttu-id="45217-115">O número atual de modalidade de áudio</span><span class="sxs-lookup"><span data-stu-id="45217-115">The current number of Audio modality</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45217-116">Contagem de modalidade de colaboração de dados ativa</span><span class="sxs-lookup"><span data-stu-id="45217-116">Active Data Collaboration Modality Count</span></span></p></td>
<td><p><span data-ttu-id="45217-117">O número atual de modalidade de colaboração de dados</span><span class="sxs-lookup"><span data-stu-id="45217-117">The current number of Data Collaboration modality</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45217-118">Latência de obtenção de foto do Active Directory (MS)</span><span class="sxs-lookup"><span data-stu-id="45217-118">Active Directory Photo Get Latency (ms)</span></span></p></td>
<td><p><span data-ttu-id="45217-119">Este contador mostra o tempo médio (em milissegundos) para recuperar uma foto do Active Directory</span><span class="sxs-lookup"><span data-stu-id="45217-119">This counter shows the average time (in milliseconds) to retrieve a photo from active directory</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45217-120">Contagem de modalidades de mensagens ativas</span><span class="sxs-lookup"><span data-stu-id="45217-120">Active Messaging Modality Count</span></span></p></td>
<td><p><span data-ttu-id="45217-121">O número atual de modalidade de mensagens</span><span class="sxs-lookup"><span data-stu-id="45217-121">The current number of Messaging modality</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45217-122">Contagem de modalidades de vídeo panorâmico ativa</span><span class="sxs-lookup"><span data-stu-id="45217-122">Active Panoramic Video Modality Count</span></span></p></td>
<td><p><span data-ttu-id="45217-123">O número atual da modalidade de vídeo panorâmico</span><span class="sxs-lookup"><span data-stu-id="45217-123">The current number of Panoramic Video modality</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45217-124">Contagem de obtenção pendente ativa</span><span class="sxs-lookup"><span data-stu-id="45217-124">Active Pending Get Count</span></span></p></td>
<td><p><span data-ttu-id="45217-125">O número de ativos pendentes no momento; conexões de longa duração com o servidor</span><span class="sxs-lookup"><span data-stu-id="45217-125">The number of currently active pending gets; long-held connections to the server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45217-126">Contagem de sessão ativa</span><span class="sxs-lookup"><span data-stu-id="45217-126">Active Session Count</span></span></p></td>
<td><p><span data-ttu-id="45217-127">O número atual de pontos de extremidade registrados no UCWA por aplicativo e por total</span><span class="sxs-lookup"><span data-stu-id="45217-127">The current number of endpoints registered in UCWA per application and total</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45217-128">Contagem de instâncias de usuário ativas</span><span class="sxs-lookup"><span data-stu-id="45217-128">Active User Instance Count</span></span></p></td>
<td><p><span data-ttu-id="45217-129">O número atual de instâncias de usuário</span><span class="sxs-lookup"><span data-stu-id="45217-129">The current number of user instances</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45217-130">Instâncias de usuários ativos sem aplicativo</span><span class="sxs-lookup"><span data-stu-id="45217-130">Active User Instances without Application</span></span></p></td>
<td><p><span data-ttu-id="45217-131">O número atual de instâncias de usuário sem aplicativo</span><span class="sxs-lookup"><span data-stu-id="45217-131">The current number of user instances without application</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45217-132">Contagem de modalidade de vídeo ativa</span><span class="sxs-lookup"><span data-stu-id="45217-132">Active Video Modality Count</span></span></p></td>
<td><p><span data-ttu-id="45217-133">O número atual da modalidade de vídeo</span><span class="sxs-lookup"><span data-stu-id="45217-133">The current number of Video modality</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45217-134">Solicitações de criação de aplicativo recebidas/segundo</span><span class="sxs-lookup"><span data-stu-id="45217-134">Application Creation Requests Received/Second</span></span></p></td>
<td><p><span data-ttu-id="45217-135">A taxa de solicitações de criação de aplicativo recebidas por segundo</span><span class="sxs-lookup"><span data-stu-id="45217-135">The per second rate of received application creation requests</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45217-136">Como falhas de junção de MCU</span><span class="sxs-lookup"><span data-stu-id="45217-136">AS MCU Join Failures</span></span></p></td>
<td><p><span data-ttu-id="45217-137">O número de falhas de ingresso no MCU</span><span class="sxs-lookup"><span data-stu-id="45217-137">The number of AS MCU Join Failures</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45217-138">Falhas de ingresso do AV MCU</span><span class="sxs-lookup"><span data-stu-id="45217-138">AV MCU Join Failures</span></span></p></td>
<td><p><span data-ttu-id="45217-139">O número de falhas de ingresso no AV MCU</span><span class="sxs-lookup"><span data-stu-id="45217-139">The number of AV MCU Join Failures</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45217-140">Tempo médio de inicialização do aplicativo (MS)</span><span class="sxs-lookup"><span data-stu-id="45217-140">Average Application Startup Time (ms)</span></span></p></td>
<td><p><span data-ttu-id="45217-141">O tempo médio de inicialização do aplicativo em milissegundos</span><span class="sxs-lookup"><span data-stu-id="45217-141">The average application startup time in Milliseconds</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45217-142">Tempo de vida médio da sessão (MS)</span><span class="sxs-lookup"><span data-stu-id="45217-142">Average Lifetime for Session (ms)</span></span></p></td>
<td><p><span data-ttu-id="45217-143">O tempo médio de vida de uma sessão em milissegundos</span><span class="sxs-lookup"><span data-stu-id="45217-143">The average lifetime for a session in milliseconds</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45217-144">Falhas de ingresso no MCU de dados</span><span class="sxs-lookup"><span data-stu-id="45217-144">Data MCU Join Failures</span></span></p></td>
<td><p><span data-ttu-id="45217-145">O número de falhas de ingresso no MCU de dados</span><span class="sxs-lookup"><span data-stu-id="45217-145">The number of Data MCU Join Failures</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45217-146">Latência de pesquisa de contato do Exchange (MS)</span><span class="sxs-lookup"><span data-stu-id="45217-146">Exchange Contact Search Latency (ms)</span></span></p></td>
<td><p><span data-ttu-id="45217-147">Este contador mostra o tempo médio (em milissegundos) para pesquisar o contato no Exchange</span><span class="sxs-lookup"><span data-stu-id="45217-147">This counter shows the average time (in milliseconds) to search contact in Exchange</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45217-148">Latência de obtenção de foto HD do Exchange (MS)</span><span class="sxs-lookup"><span data-stu-id="45217-148">Exchange HD Photo Get Latency (ms)</span></span></p></td>
<td><p><span data-ttu-id="45217-149">Este contador mostra o tempo médio (em milissegundos) para recuperar uma foto do Exchange</span><span class="sxs-lookup"><span data-stu-id="45217-149">This counter shows the average time (in milliseconds) to retrieve a photo from Exchange</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45217-150">Respostas HTTP 4xx/segundo</span><span class="sxs-lookup"><span data-stu-id="45217-150">HTTP 4xx Responses/Second</span></span></p></td>
<td><p><span data-ttu-id="45217-151">A taxa de respostas por segundo com o código HTTP 4xx</span><span class="sxs-lookup"><span data-stu-id="45217-151">The per second rate of responses with HTTP 4xx code</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45217-152">Respostas de HTTP 5xx/segundo</span><span class="sxs-lookup"><span data-stu-id="45217-152">HTTP 5xx Responses/Second</span></span></p></td>
<td><p><span data-ttu-id="45217-153">A taxa de respostas por segundo com o código HTTP 5xx</span><span class="sxs-lookup"><span data-stu-id="45217-153">The per second rate of responses with HTTP 5xx code</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45217-154">Falhas de junção de IM MCU</span><span class="sxs-lookup"><span data-stu-id="45217-154">IM MCU Join Failures</span></span></p></td>
<td><p><span data-ttu-id="45217-155">O número de falhas de entrada de mensagens instantâneas de MCU</span><span class="sxs-lookup"><span data-stu-id="45217-155">The number of IM MCU Join Failures</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45217-156">Número de falhas ao baixar fotos do Active Directory</span><span class="sxs-lookup"><span data-stu-id="45217-156">Number of Active Directory Photo Get Failures</span></span></p></td>
<td><p><span data-ttu-id="45217-157">O número total de falhas para recuperar fotos do Active Directory</span><span class="sxs-lookup"><span data-stu-id="45217-157">The total number of failures to retrieve photos from Active Directory</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45217-158">Número de falhas de pesquisa de contato</span><span class="sxs-lookup"><span data-stu-id="45217-158">Number of Contact Search failures</span></span></p></td>
<td><p><span data-ttu-id="45217-159">O número total de falhas ao pesquisar contatos no Exchange</span><span class="sxs-lookup"><span data-stu-id="45217-159">The total number of failures to search contacts in Exchange</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45217-160">Número de falhas de desserialização</span><span class="sxs-lookup"><span data-stu-id="45217-160">Number of Deserialization Failures</span></span></p></td>
<td><p><span data-ttu-id="45217-161">O número total de falhas de desserialização</span><span class="sxs-lookup"><span data-stu-id="45217-161">The total number of deserialization failures</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45217-162">Número de falhas de obtenção de foto de HD</span><span class="sxs-lookup"><span data-stu-id="45217-162">Number of HD Photo Get Failures</span></span></p></td>
<td><p><span data-ttu-id="45217-163">O número total de falhas para recuperar fotos de HD do Exchange</span><span class="sxs-lookup"><span data-stu-id="45217-163">The total number of failures to retrieve HD photos from Exchange</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45217-164">Sobre as assinaturas máximas por aplicativo</span><span class="sxs-lookup"><span data-stu-id="45217-164">Over The Maximum Subscriptions Per Application</span></span></p></td>
<td><p><span data-ttu-id="45217-165">O número de solicitações de assinatura no máximo permitido por aplicativo</span><span class="sxs-lookup"><span data-stu-id="45217-165">The number of Subscription requests over the maximum allowed per application</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45217-166">Sobre o máximo de inscrições por lote</span><span class="sxs-lookup"><span data-stu-id="45217-166">Over The Maximum Subscriptions Per Batch</span></span></p></td>
<td><p><span data-ttu-id="45217-167">O número de solicitações de assinatura no máximo permitido por lote</span><span class="sxs-lookup"><span data-stu-id="45217-167">The number of Subscription requests over the maximum allowed per batch</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45217-168">Falhas de assinatura de presença</span><span class="sxs-lookup"><span data-stu-id="45217-168">Presence Subscription Failures</span></span></p></td>
<td><p><span data-ttu-id="45217-169">O número de falhas ao assinar a presença</span><span class="sxs-lookup"><span data-stu-id="45217-169">The number of failures to subscribe presence</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45217-170">Registrando falhas de pontos de extremidade</span><span class="sxs-lookup"><span data-stu-id="45217-170">Registering Endpoint Failures</span></span></p></td>
<td><p><span data-ttu-id="45217-171">O número de falhas para registrar pontos de extremidade</span><span class="sxs-lookup"><span data-stu-id="45217-171">The number of failures to register endpoints</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45217-172">Solicitações recebidas/segundo</span><span class="sxs-lookup"><span data-stu-id="45217-172">Requests Received/Second</span></span></p></td>
<td><p><span data-ttu-id="45217-173">A taxa de solicitações recebidas por segundo</span><span class="sxs-lookup"><span data-stu-id="45217-173">The per second rate of received requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45217-174">Solicitações bem-sucedidas/segundo</span><span class="sxs-lookup"><span data-stu-id="45217-174">Requests Succeeded/Second</span></span></p></td>
<td><p><span data-ttu-id="45217-175">A taxa de solicitações bem-sucedidas por segundo (códigos de resposta HTTP 2xx/3xx)</span><span class="sxs-lookup"><span data-stu-id="45217-175">The per second rate of successful requests (HTTP 2xx/3xx response codes)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45217-176">Solicitações de criação de aplicativo bem-sucedidas/segundo</span><span class="sxs-lookup"><span data-stu-id="45217-176">Succeeded Create Application Requests/Second</span></span></p></td>
<td><p><span data-ttu-id="45217-177">A taxa de solicitações de criação de aplicativo bem-sucedidas por segundo</span><span class="sxs-lookup"><span data-stu-id="45217-177">The per second rate of successful application creation requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45217-178">Contagem de obtenção pendente com tempo limite esgotado</span><span class="sxs-lookup"><span data-stu-id="45217-178">Timed Out Pending Get Count</span></span></p></td>
<td><p><span data-ttu-id="45217-179">O número de pendências que expiraram</span><span class="sxs-lookup"><span data-stu-id="45217-179">The number of pending gets that timed out</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45217-180">Total de solicitações de criação de aplicativos recebidas</span><span class="sxs-lookup"><span data-stu-id="45217-180">Total Application Creation Requests Received</span></span></p></td>
<td><p><span data-ttu-id="45217-181">O número total de solicitações de criação de aplicativos recebidas desde que o serviço foi iniciado</span><span class="sxs-lookup"><span data-stu-id="45217-181">The total number of application creation requests received since the service was started</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45217-182">Total de respostas de HTTP 4xx</span><span class="sxs-lookup"><span data-stu-id="45217-182">Total HTTP 4xx Responses</span></span></p></td>
<td><p><span data-ttu-id="45217-183">O número total de respostas HTTP 4xx</span><span class="sxs-lookup"><span data-stu-id="45217-183">The total number of HTTP 4xx responses</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45217-184">Total de respostas de HTTP 5xx</span><span class="sxs-lookup"><span data-stu-id="45217-184">Total HTTP 5xx Responses</span></span></p></td>
<td><p><span data-ttu-id="45217-185">O número total de respostas HTTP 5xx</span><span class="sxs-lookup"><span data-stu-id="45217-185">The total number of HTTP 5xx responses</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45217-186">Total de solicitações recebidas no canal de comando</span><span class="sxs-lookup"><span data-stu-id="45217-186">Total Requests Received on the Command Channel</span></span></p></td>
<td><p><span data-ttu-id="45217-187">O número total de solicitações recebidas no canal do comando</span><span class="sxs-lookup"><span data-stu-id="45217-187">The total number of requests received on the command channel</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45217-188">Total de solicitações bem-sucedidas</span><span class="sxs-lookup"><span data-stu-id="45217-188">Total Requests Succeeded</span></span></p></td>
<td><p><span data-ttu-id="45217-189">O número total de solicitações que tiveram êxito</span><span class="sxs-lookup"><span data-stu-id="45217-189">The total number of requests that succeeded</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45217-190">Total de sessões iniciadas</span><span class="sxs-lookup"><span data-stu-id="45217-190">Total Sessions Initiated</span></span></p></td>
<td><p><span data-ttu-id="45217-191">O número total de sessões que foram iniciadas desde o início do serviço</span><span class="sxs-lookup"><span data-stu-id="45217-191">The total number of sessions that were initiated since the service was started</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45217-192">Total de sessões encerradas devido ao tempo limite de ociosidade</span><span class="sxs-lookup"><span data-stu-id="45217-192">Total Sessions Terminated Because of Idle Timeout</span></span></p></td>
<td><p><span data-ttu-id="45217-193">O número total de sessões encerradas devido ao tempo limite de usuário ocioso</span><span class="sxs-lookup"><span data-stu-id="45217-193">The total number of sessions that were terminated because of user idle timeout</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45217-194">Total de aplicativos limitado</span><span class="sxs-lookup"><span data-stu-id="45217-194">Total Throttled Applications</span></span></p></td>
<td><p><span data-ttu-id="45217-195">O número de aplicativos regulados</span><span class="sxs-lookup"><span data-stu-id="45217-195">The number of throttled applications</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div id="sectionSection1" class="section">

### <a name="performance-counters-for-mcx-mobility-service"></a><span data-ttu-id="45217-196">Contadores de desempenho para o serviço de mobilidade do MCX</span><span class="sxs-lookup"><span data-stu-id="45217-196">Performance Counters for Mcx Mobility Service</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="45217-197">Contador</span><span class="sxs-lookup"><span data-stu-id="45217-197">Counter</span></span></th>
<th><span data-ttu-id="45217-198">Descrição</span><span class="sxs-lookup"><span data-stu-id="45217-198">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="45217-199">Tempo média de vida de uma sessão em milissegundos</span><span class="sxs-lookup"><span data-stu-id="45217-199">Average Lifetime for a Session in Milliseconds</span></span></p></td>
<td><p><span data-ttu-id="45217-200">O tempo médio de vida de uma sessão em milissegundos</span><span class="sxs-lookup"><span data-stu-id="45217-200">The average lifetime for a session in milliseconds</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45217-201">Assinaturas atuais de notificação por push</span><span class="sxs-lookup"><span data-stu-id="45217-201">Current Push Notification Subscriptions</span></span></p></td>
<td><p><span data-ttu-id="45217-202">O número atual de assinaturas de notificação por push.</span><span class="sxs-lookup"><span data-stu-id="45217-202">The current number of push notification subscriptions.</span></span> <span data-ttu-id="45217-203">Esse número, em conjunto com a contagem de sessão ativa no momento, representa o subconjunto de sessões ativas no momento que são registradas para dispositivos Windows Mobile ou iPhone.</span><span class="sxs-lookup"><span data-stu-id="45217-203">This number, in conjunction with Currently Active Session Count, represents the subset of currently active sessions that are registered for Windows Mobile or iPhone devices.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45217-204">Contagem de polls de tempo limite de rede ativos no momento</span><span class="sxs-lookup"><span data-stu-id="45217-204">Currently Active Network Timeout Poll Count</span></span></p></td>
<td><p><span data-ttu-id="45217-205">O número de pools de rede que ultrapassaram o tempo limite</span><span class="sxs-lookup"><span data-stu-id="45217-205">The number of network polls that timed out</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45217-206">Contagem de pools ativos no momento</span><span class="sxs-lookup"><span data-stu-id="45217-206">Currently Active Poll Count</span></span></p></td>
<td><p><span data-ttu-id="45217-207">O número de polls atualmente ativos (conexões de longa duração com o servidor)</span><span class="sxs-lookup"><span data-stu-id="45217-207">The number of currently active polls (long-held connections to the server)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45217-208">Contagem de sessão ativa no momento</span><span class="sxs-lookup"><span data-stu-id="45217-208">Currently Active Session Count</span></span></p></td>
<td><p><span data-ttu-id="45217-209">Número atual de pontos de extremidade registrados no Serviço de Mobilidade</span><span class="sxs-lookup"><span data-stu-id="45217-209">Current number of endpoints registered in the Mobility Service</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45217-210">Contagem de sessão ativa no momento com assinaturas de presença ativa</span><span class="sxs-lookup"><span data-stu-id="45217-210">Currently Active Session Count with Active Presence Subscriptions</span></span></p></td>
<td><p><span data-ttu-id="45217-211">O número de sessões ativas no momento com assinaturas de presença ativa</span><span class="sxs-lookup"><span data-stu-id="45217-211">The number of currently active sessions with active presence subscriptions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45217-212">Solicitações de notificação por push sem êxito/segundo</span><span class="sxs-lookup"><span data-stu-id="45217-212">Push Notification Requests Failed/Second</span></span></p></td>
<td><p><span data-ttu-id="45217-213">A taxa de notificações por push sem êxito por segundo</span><span class="sxs-lookup"><span data-stu-id="45217-213">The per second rate of failed push notifications</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45217-214">Solicitações de notificação por push bem-sucedidas/segundo</span><span class="sxs-lookup"><span data-stu-id="45217-214">Push Notification Requests Succeeded/Second</span></span></p></td>
<td><p><span data-ttu-id="45217-215">A taxa de notificações por push bem-sucedidas por segundo</span><span class="sxs-lookup"><span data-stu-id="45217-215">The per second rate of successful push notifications</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45217-216">Solicitações de notificação por push limitadas/segundo</span><span class="sxs-lookup"><span data-stu-id="45217-216">Push Notification Requests Throttled/Second</span></span></p></td>
<td><p><span data-ttu-id="45217-217">A taxa de notificações por push limitadas por segundo</span><span class="sxs-lookup"><span data-stu-id="45217-217">The per second rate of throttled push notifications</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45217-218">Solicitações de notificação por push/segundo</span><span class="sxs-lookup"><span data-stu-id="45217-218">Push Notification Requests/Second</span></span></p></td>
<td><p><span data-ttu-id="45217-219">A taxa de notificações por push enviadas por segundo</span><span class="sxs-lookup"><span data-stu-id="45217-219">The per second rate of sent push notifications</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45217-220">Solicitações sem êxito/segundo</span><span class="sxs-lookup"><span data-stu-id="45217-220">Requests Failed/Second</span></span></p></td>
<td><p><span data-ttu-id="45217-221">A taxa de solicitações sem êxito por segundo</span><span class="sxs-lookup"><span data-stu-id="45217-221">The per second rate of failed requests</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45217-222">Solicitações recebidas/segundo</span><span class="sxs-lookup"><span data-stu-id="45217-222">Requests Received/Second</span></span></p></td>
<td><p><span data-ttu-id="45217-223">A taxa de solicitações recebidas por segundo</span><span class="sxs-lookup"><span data-stu-id="45217-223">The per second rate of received requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45217-224">Solicitações rejeitadas/segundo</span><span class="sxs-lookup"><span data-stu-id="45217-224">Requests Rejected/Second</span></span></p></td>
<td><p><span data-ttu-id="45217-225">A taxa de solicitações receitadas por segundo</span><span class="sxs-lookup"><span data-stu-id="45217-225">The per second rate of rejected requests</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45217-226">Solicitações bem-sucedidas/segundo</span><span class="sxs-lookup"><span data-stu-id="45217-226">Requests Succeeded/Second</span></span></p></td>
<td><p><span data-ttu-id="45217-227">A taxa de solicitações bem-sucedidas por segundo</span><span class="sxs-lookup"><span data-stu-id="45217-227">The per second rate of successful requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45217-228">Solicitações de início de sessão bem-sucedidas/segundo</span><span class="sxs-lookup"><span data-stu-id="45217-228">Succeeded Initiate Session Requests/Second</span></span></p></td>
<td><p><span data-ttu-id="45217-p102">A taxa de solicitações de Obter localização bem-sucedidas por segundo. As solicitações de início de uma sessão consomem grande parte do CPU no servidor. A carga de pico suportada é de 12/segundo. A sustentabilidade depende de outras cargas no servidor. Iniciar uma sessão normalmente significa um logon de um usuário que ficou desconectado durante um período extenso de tempo.</span><span class="sxs-lookup"><span data-stu-id="45217-p102">The per second rate of successful Get Location requests. Requests to initiate a session consume the most CPU on the server. Peak supported load is 12/second. Sustainability depends on other loads on the server. Initiate a session typically means a sign-in for a user that has been signed out for an extended period of time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45217-234">Total de chamadas de voz de entrada recusadas</span><span class="sxs-lookup"><span data-stu-id="45217-234">Total Declined Inbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="45217-235">O número total de chamadas de voz de entrada recusadas</span><span class="sxs-lookup"><span data-stu-id="45217-235">The total number of inbound voice calls that were declined</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45217-236">Total de chamadas de voz de entrada sem êxito</span><span class="sxs-lookup"><span data-stu-id="45217-236">Total Failed Inbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="45217-237">O número total de chamadas de voz de entrada que não tiveram êxito</span><span class="sxs-lookup"><span data-stu-id="45217-237">The total number of inbound voice calls that failed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45217-238">Total de chamadas de voz de saída sem êxito</span><span class="sxs-lookup"><span data-stu-id="45217-238">Total Failed Outbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="45217-239">O número total de chamadas de voz de saída que não tiveram êxito</span><span class="sxs-lookup"><span data-stu-id="45217-239">The total number of outbound voice calls that failed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45217-240">Número total de sessões encerradas pelo usuário</span><span class="sxs-lookup"><span data-stu-id="45217-240">Total number of sessions terminated by user</span></span></p></td>
<td><p><span data-ttu-id="45217-241">O número total de sessões encerradas por usuários</span><span class="sxs-lookup"><span data-stu-id="45217-241">The total number of sessions terminated by users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45217-242">Total de solicitações de notificação por push</span><span class="sxs-lookup"><span data-stu-id="45217-242">Total Push Notification Requests</span></span></p></td>
<td><p><span data-ttu-id="45217-243">O número total de solicitações de notificação por push</span><span class="sxs-lookup"><span data-stu-id="45217-243">The total number of push notification requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45217-244">Total de solicitações de notificação por push em êxito</span><span class="sxs-lookup"><span data-stu-id="45217-244">Total Push Notification Requests Failed</span></span></p></td>
<td><p><span data-ttu-id="45217-245">O número total de solicitações de notificação por push que não tiveram êxito</span><span class="sxs-lookup"><span data-stu-id="45217-245">The total number of push notification requests that failed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45217-246">Total de solicitações de notificação por push bem-sucedidas</span><span class="sxs-lookup"><span data-stu-id="45217-246">Total Push Notification Requests Succeeded</span></span></p></td>
<td><p><span data-ttu-id="45217-247">O número total de solicitações de notificação por push bem-sucedidas</span><span class="sxs-lookup"><span data-stu-id="45217-247">The total number of push notification requests that were successful</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45217-248">Total de solicitações de notificação por push limitadas</span><span class="sxs-lookup"><span data-stu-id="45217-248">Total Push Notification Requests Throttled</span></span></p></td>
<td><p><span data-ttu-id="45217-249">O número total de solicitações de notificação por push limitadas</span><span class="sxs-lookup"><span data-stu-id="45217-249">The total number of push notification requests that were throttled</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45217-250">Total de solicitações sem êxito</span><span class="sxs-lookup"><span data-stu-id="45217-250">Total Requests Failed</span></span></p></td>
<td><p><span data-ttu-id="45217-251">O número total de solicitações que não tiveram êxito</span><span class="sxs-lookup"><span data-stu-id="45217-251">The total number of requests that failed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45217-252">Total de solicitações recebidas no Canal de Comando</span><span class="sxs-lookup"><span data-stu-id="45217-252">Total Requests received on the Command Channel</span></span></p></td>
<td><p><span data-ttu-id="45217-253">O número total de solicitações recebidas no canal do comando</span><span class="sxs-lookup"><span data-stu-id="45217-253">The total number of requests received on the command channel</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45217-254">Total de solicitações rejeitadas</span><span class="sxs-lookup"><span data-stu-id="45217-254">Total Requests Rejected</span></span></p></td>
<td><p><span data-ttu-id="45217-255">O número total de solicitações rejeitadas</span><span class="sxs-lookup"><span data-stu-id="45217-255">The total number of requests that were rejected</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45217-256">Total de solicitações bem-sucedidas</span><span class="sxs-lookup"><span data-stu-id="45217-256">Total Requests Succeeded</span></span></p></td>
<td><p><span data-ttu-id="45217-257">O número total de solicitações feitas ao Serviço de Mobilidade que tiveram êxito</span><span class="sxs-lookup"><span data-stu-id="45217-257">The total number of requests made to the Mobility Service that succeeded</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45217-258">Contagem total de sessões iniciadas</span><span class="sxs-lookup"><span data-stu-id="45217-258">Total Session Initiated Count</span></span></p></td>
<td><p><span data-ttu-id="45217-259">O número total de sessões iniciadas desde a inicialização do Serviço de Mobilidade</span><span class="sxs-lookup"><span data-stu-id="45217-259">The total number of sessions that were initiated since the Mobility Service was started</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45217-260">Total de sessões encerradas devido ao tempo limite de usuário ocioso</span><span class="sxs-lookup"><span data-stu-id="45217-260">Total Sessions Terminated Because of User Idle Timeout</span></span></p></td>
<td><p><span data-ttu-id="45217-261">O número total de sessões encerradas devido ao tempo limite de usuário ocioso</span><span class="sxs-lookup"><span data-stu-id="45217-261">The total number of sessions that were terminated because of user idle timeout</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45217-262">Total de chamadas de voz de entrada bem-sucedidas</span><span class="sxs-lookup"><span data-stu-id="45217-262">Total Successful Inbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="45217-263">O número total de chamadas de voz de entrada que tiveram êxito</span><span class="sxs-lookup"><span data-stu-id="45217-263">The total number of inbound voice calls that were successful</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45217-264">Total de chamadas de voz de saída bem-sucedidas</span><span class="sxs-lookup"><span data-stu-id="45217-264">Total Successful Outbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="45217-265">O número total de chamadas de voz de saída que tiveram êxito</span><span class="sxs-lookup"><span data-stu-id="45217-265">The total number of outbound voice calls that were successful</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

