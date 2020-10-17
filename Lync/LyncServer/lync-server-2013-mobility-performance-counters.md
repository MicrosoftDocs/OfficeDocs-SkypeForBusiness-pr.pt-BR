---
title: 'Lync Server 2013: contadores de desempenho de mobilidade'
description: 'Lync Server 2013: contadores de desempenho de mobilidade.'
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
ms.openlocfilehash: 922288f6c026f088d651dc61afdcb6ba04fed30a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550527"
---
# <a name="mobility-performance-counters-in-lync-server-2013"></a><span data-ttu-id="1d1d2-103">Contadores de desempenho de mobilidade no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1d1d2-103">Mobility performance counters in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1d1d2-104">_**Última modificação do tópico:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="1d1d2-104">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="1d1d2-105">As tabelas a seguir listam os nomes e as descrições dos contadores de desempenho que você pode usar para monitorar servidores que executam a UCWA (Unified Communications Web API) e o serviço de mobilidade do Lync Server 2013 MCX.</span><span class="sxs-lookup"><span data-stu-id="1d1d2-105">The following tables list the names and descriptions of performance counters that you can use to monitor servers running the Unified Communications Web API (UCWA) and the Lync Server 2013 Mcx Mobility Service.</span></span>

<span data-ttu-id="1d1d2-106">O nome da categoria para os contadores na tabela UCWA é **ls: Web – UCWA**.</span><span class="sxs-lookup"><span data-stu-id="1d1d2-106">The category name for the counters in the UCWA table is **LS:WEB – UCWA**.</span></span>

<span data-ttu-id="1d1d2-107">O nome da categoria para os contadores na tabela de serviço de mobilidade do MCX é **ls: Web-Mobile Communication Service**.</span><span class="sxs-lookup"><span data-stu-id="1d1d2-107">The category name for the counters in the Mcx Mobility Service table is **LS:WEB - Mobile Communication Service**.</span></span>

<div>

## <a name="performance-counters-for-ucwa"></a><span data-ttu-id="1d1d2-108">Contadores de desempenho para UCWA</span><span class="sxs-lookup"><span data-stu-id="1d1d2-108">Performance Counters for UCWA</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1d1d2-109">Contador</span><span class="sxs-lookup"><span data-stu-id="1d1d2-109">Counter</span></span></th>
<th><span data-ttu-id="1d1d2-110">Descrição</span><span class="sxs-lookup"><span data-stu-id="1d1d2-110">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1d1d2-111">Contagem de aplicativos ativos</span><span class="sxs-lookup"><span data-stu-id="1d1d2-111">Active Application Count</span></span></p></td>
<td><p><span data-ttu-id="1d1d2-112">O número atual de aplicativos</span><span class="sxs-lookup"><span data-stu-id="1d1d2-112">The current number of applications</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d1d2-113">Contagem de modalidades de compartilhamento de aplicativos ativos</span><span class="sxs-lookup"><span data-stu-id="1d1d2-113">Active Application Sharing Modality Count</span></span></p></td>
<td><p><span data-ttu-id="1d1d2-114">O número atual da modalidade de compartilhamento de aplicativos</span><span class="sxs-lookup"><span data-stu-id="1d1d2-114">The current number of Application Sharing modality</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d1d2-115">Contagem de modalidade de áudio ativa</span><span class="sxs-lookup"><span data-stu-id="1d1d2-115">Active Audio Modality Count</span></span></p></td>
<td><p><span data-ttu-id="1d1d2-116">O número atual de modalidade de áudio</span><span class="sxs-lookup"><span data-stu-id="1d1d2-116">The current number of Audio modality</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d1d2-117">Contagem de modalidade de colaboração de dados ativa</span><span class="sxs-lookup"><span data-stu-id="1d1d2-117">Active Data Collaboration Modality Count</span></span></p></td>
<td><p><span data-ttu-id="1d1d2-118">O número atual de modalidade de colaboração de dados</span><span class="sxs-lookup"><span data-stu-id="1d1d2-118">The current number of Data Collaboration modality</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d1d2-119">Latência de obtenção de foto do Active Directory (MS)</span><span class="sxs-lookup"><span data-stu-id="1d1d2-119">Active Directory Photo Get Latency (ms)</span></span></p></td>
<td><p><span data-ttu-id="1d1d2-120">Este contador mostra o tempo médio (em milissegundos) para recuperar uma foto do Active Directory</span><span class="sxs-lookup"><span data-stu-id="1d1d2-120">This counter shows the average time (in milliseconds) to retrieve a photo from active directory</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d1d2-121">Contagem de modalidades de mensagens ativas</span><span class="sxs-lookup"><span data-stu-id="1d1d2-121">Active Messaging Modality Count</span></span></p></td>
<td><p><span data-ttu-id="1d1d2-122">O número atual de modalidade de mensagens</span><span class="sxs-lookup"><span data-stu-id="1d1d2-122">The current number of Messaging modality</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d1d2-123">Contagem de modalidades de vídeo panorâmico ativa</span><span class="sxs-lookup"><span data-stu-id="1d1d2-123">Active Panoramic Video Modality Count</span></span></p></td>
<td><p><span data-ttu-id="1d1d2-124">O número atual da modalidade de vídeo panorâmico</span><span class="sxs-lookup"><span data-stu-id="1d1d2-124">The current number of Panoramic Video modality</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d1d2-125">Contagem de obtenção pendente ativa</span><span class="sxs-lookup"><span data-stu-id="1d1d2-125">Active Pending Get Count</span></span></p></td>
<td><p><span data-ttu-id="1d1d2-126">O número de ativos pendentes no momento; conexões de longa duração com o servidor</span><span class="sxs-lookup"><span data-stu-id="1d1d2-126">The number of currently active pending gets; long-held connections to the server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d1d2-127">Contagem de sessão ativa</span><span class="sxs-lookup"><span data-stu-id="1d1d2-127">Active Session Count</span></span></p></td>
<td><p><span data-ttu-id="1d1d2-128">O número atual de pontos de extremidade registrados no UCWA por aplicativo e por total</span><span class="sxs-lookup"><span data-stu-id="1d1d2-128">The current number of endpoints registered in UCWA per application and total</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d1d2-129">Contagem de instâncias de usuário ativas</span><span class="sxs-lookup"><span data-stu-id="1d1d2-129">Active User Instance Count</span></span></p></td>
<td><p><span data-ttu-id="1d1d2-130">O número atual de instâncias de usuário</span><span class="sxs-lookup"><span data-stu-id="1d1d2-130">The current number of user instances</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d1d2-131">Instâncias de usuários ativos sem aplicativo</span><span class="sxs-lookup"><span data-stu-id="1d1d2-131">Active User Instances without Application</span></span></p></td>
<td><p><span data-ttu-id="1d1d2-132">O número atual de instâncias de usuário sem aplicativo</span><span class="sxs-lookup"><span data-stu-id="1d1d2-132">The current number of user instances without application</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d1d2-133">Contagem de modalidade de vídeo ativa</span><span class="sxs-lookup"><span data-stu-id="1d1d2-133">Active Video Modality Count</span></span></p></td>
<td><p><span data-ttu-id="1d1d2-134">O número atual da modalidade de vídeo</span><span class="sxs-lookup"><span data-stu-id="1d1d2-134">The current number of Video modality</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d1d2-135">Solicitações de criação de aplicativo recebidas/segundo</span><span class="sxs-lookup"><span data-stu-id="1d1d2-135">Application Creation Requests Received/Second</span></span></p></td>
<td><p><span data-ttu-id="1d1d2-136">A taxa de solicitações de criação de aplicativo recebidas por segundo</span><span class="sxs-lookup"><span data-stu-id="1d1d2-136">The per second rate of received application creation requests</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d1d2-137">Como falhas de junção de MCU</span><span class="sxs-lookup"><span data-stu-id="1d1d2-137">AS MCU Join Failures</span></span></p></td>
<td><p><span data-ttu-id="1d1d2-138">O número de falhas de ingresso no MCU</span><span class="sxs-lookup"><span data-stu-id="1d1d2-138">The number of AS MCU Join Failures</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d1d2-139">Falhas de ingresso do AV MCU</span><span class="sxs-lookup"><span data-stu-id="1d1d2-139">AV MCU Join Failures</span></span></p></td>
<td><p><span data-ttu-id="1d1d2-140">O número de falhas de ingresso no AV MCU</span><span class="sxs-lookup"><span data-stu-id="1d1d2-140">The number of AV MCU Join Failures</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d1d2-141">Tempo médio de inicialização do aplicativo (MS)</span><span class="sxs-lookup"><span data-stu-id="1d1d2-141">Average Application Startup Time (ms)</span></span></p></td>
<td><p><span data-ttu-id="1d1d2-142">O tempo médio de inicialização do aplicativo em milissegundos</span><span class="sxs-lookup"><span data-stu-id="1d1d2-142">The average application startup time in Milliseconds</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d1d2-143">Tempo de vida médio da sessão (MS)</span><span class="sxs-lookup"><span data-stu-id="1d1d2-143">Average Lifetime for Session (ms)</span></span></p></td>
<td><p><span data-ttu-id="1d1d2-144">O tempo médio de vida de uma sessão em milissegundos</span><span class="sxs-lookup"><span data-stu-id="1d1d2-144">The average lifetime for a session in milliseconds</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d1d2-145">Falhas de ingresso no MCU de dados</span><span class="sxs-lookup"><span data-stu-id="1d1d2-145">Data MCU Join Failures</span></span></p></td>
<td><p><span data-ttu-id="1d1d2-146">O número de falhas de ingresso no MCU de dados</span><span class="sxs-lookup"><span data-stu-id="1d1d2-146">The number of Data MCU Join Failures</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d1d2-147">Latência de pesquisa de contato do Exchange (MS)</span><span class="sxs-lookup"><span data-stu-id="1d1d2-147">Exchange Contact Search Latency (ms)</span></span></p></td>
<td><p><span data-ttu-id="1d1d2-148">Este contador mostra o tempo médio (em milissegundos) para pesquisar o contato no Exchange</span><span class="sxs-lookup"><span data-stu-id="1d1d2-148">This counter shows the average time (in milliseconds) to search contact in Exchange</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d1d2-149">Latência de obtenção de foto HD do Exchange (MS)</span><span class="sxs-lookup"><span data-stu-id="1d1d2-149">Exchange HD Photo Get Latency (ms)</span></span></p></td>
<td><p><span data-ttu-id="1d1d2-150">Este contador mostra o tempo médio (em milissegundos) para recuperar uma foto do Exchange</span><span class="sxs-lookup"><span data-stu-id="1d1d2-150">This counter shows the average time (in milliseconds) to retrieve a photo from Exchange</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d1d2-151">Respostas HTTP 4xx/segundo</span><span class="sxs-lookup"><span data-stu-id="1d1d2-151">HTTP 4xx Responses/Second</span></span></p></td>
<td><p><span data-ttu-id="1d1d2-152">A taxa de respostas por segundo com o código HTTP 4xx</span><span class="sxs-lookup"><span data-stu-id="1d1d2-152">The per second rate of responses with HTTP 4xx code</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d1d2-153">Respostas de HTTP 5xx/segundo</span><span class="sxs-lookup"><span data-stu-id="1d1d2-153">HTTP 5xx Responses/Second</span></span></p></td>
<td><p><span data-ttu-id="1d1d2-154">A taxa de respostas por segundo com o código HTTP 5xx</span><span class="sxs-lookup"><span data-stu-id="1d1d2-154">The per second rate of responses with HTTP 5xx code</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d1d2-155">Falhas de junção de IM MCU</span><span class="sxs-lookup"><span data-stu-id="1d1d2-155">IM MCU Join Failures</span></span></p></td>
<td><p><span data-ttu-id="1d1d2-156">O número de falhas de entrada de mensagens instantâneas de MCU</span><span class="sxs-lookup"><span data-stu-id="1d1d2-156">The number of IM MCU Join Failures</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d1d2-157">Número de falhas ao baixar fotos do Active Directory</span><span class="sxs-lookup"><span data-stu-id="1d1d2-157">Number of Active Directory Photo Get Failures</span></span></p></td>
<td><p><span data-ttu-id="1d1d2-158">O número total de falhas para recuperar fotos do Active Directory</span><span class="sxs-lookup"><span data-stu-id="1d1d2-158">The total number of failures to retrieve photos from Active Directory</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d1d2-159">Número de falhas de pesquisa de contato</span><span class="sxs-lookup"><span data-stu-id="1d1d2-159">Number of Contact Search failures</span></span></p></td>
<td><p><span data-ttu-id="1d1d2-160">O número total de falhas ao pesquisar contatos no Exchange</span><span class="sxs-lookup"><span data-stu-id="1d1d2-160">The total number of failures to search contacts in Exchange</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d1d2-161">Número de falhas de desserialização</span><span class="sxs-lookup"><span data-stu-id="1d1d2-161">Number of Deserialization Failures</span></span></p></td>
<td><p><span data-ttu-id="1d1d2-162">O número total de falhas de desserialização</span><span class="sxs-lookup"><span data-stu-id="1d1d2-162">The total number of deserialization failures</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d1d2-163">Número de falhas de obtenção de foto de HD</span><span class="sxs-lookup"><span data-stu-id="1d1d2-163">Number of HD Photo Get Failures</span></span></p></td>
<td><p><span data-ttu-id="1d1d2-164">O número total de falhas para recuperar fotos de HD do Exchange</span><span class="sxs-lookup"><span data-stu-id="1d1d2-164">The total number of failures to retrieve HD photos from Exchange</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d1d2-165">Sobre as assinaturas máximas por aplicativo</span><span class="sxs-lookup"><span data-stu-id="1d1d2-165">Over The Maximum Subscriptions Per Application</span></span></p></td>
<td><p><span data-ttu-id="1d1d2-166">O número de solicitações de assinatura no máximo permitido por aplicativo</span><span class="sxs-lookup"><span data-stu-id="1d1d2-166">The number of Subscription requests over the maximum allowed per application</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d1d2-167">Sobre o máximo de inscrições por lote</span><span class="sxs-lookup"><span data-stu-id="1d1d2-167">Over The Maximum Subscriptions Per Batch</span></span></p></td>
<td><p><span data-ttu-id="1d1d2-168">O número de solicitações de assinatura no máximo permitido por lote</span><span class="sxs-lookup"><span data-stu-id="1d1d2-168">The number of Subscription requests over the maximum allowed per batch</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d1d2-169">Falhas de assinatura de presença</span><span class="sxs-lookup"><span data-stu-id="1d1d2-169">Presence Subscription Failures</span></span></p></td>
<td><p><span data-ttu-id="1d1d2-170">O número de falhas ao assinar a presença</span><span class="sxs-lookup"><span data-stu-id="1d1d2-170">The number of failures to subscribe presence</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d1d2-171">Registrando falhas de pontos de extremidade</span><span class="sxs-lookup"><span data-stu-id="1d1d2-171">Registering Endpoint Failures</span></span></p></td>
<td><p><span data-ttu-id="1d1d2-172">O número de falhas para registrar pontos de extremidade</span><span class="sxs-lookup"><span data-stu-id="1d1d2-172">The number of failures to register endpoints</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d1d2-173">Solicitações recebidas/segundo</span><span class="sxs-lookup"><span data-stu-id="1d1d2-173">Requests Received/Second</span></span></p></td>
<td><p><span data-ttu-id="1d1d2-174">A taxa de solicitações recebidas por segundo</span><span class="sxs-lookup"><span data-stu-id="1d1d2-174">The per second rate of received requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d1d2-175">Solicitações bem-sucedidas/segundo</span><span class="sxs-lookup"><span data-stu-id="1d1d2-175">Requests Succeeded/Second</span></span></p></td>
<td><p><span data-ttu-id="1d1d2-176">A taxa de solicitações bem-sucedidas por segundo (códigos de resposta HTTP 2xx/3xx)</span><span class="sxs-lookup"><span data-stu-id="1d1d2-176">The per second rate of successful requests (HTTP 2xx/3xx response codes)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d1d2-177">Solicitações de criação de aplicativo bem-sucedidas/segundo</span><span class="sxs-lookup"><span data-stu-id="1d1d2-177">Succeeded Create Application Requests/Second</span></span></p></td>
<td><p><span data-ttu-id="1d1d2-178">A taxa de solicitações de criação de aplicativo bem-sucedidas por segundo</span><span class="sxs-lookup"><span data-stu-id="1d1d2-178">The per second rate of successful application creation requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d1d2-179">Contagem de obtenção pendente com tempo limite esgotado</span><span class="sxs-lookup"><span data-stu-id="1d1d2-179">Timed Out Pending Get Count</span></span></p></td>
<td><p><span data-ttu-id="1d1d2-180">O número de pendências que expiraram</span><span class="sxs-lookup"><span data-stu-id="1d1d2-180">The number of pending gets that timed out</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d1d2-181">Total de solicitações de criação de aplicativos recebidas</span><span class="sxs-lookup"><span data-stu-id="1d1d2-181">Total Application Creation Requests Received</span></span></p></td>
<td><p><span data-ttu-id="1d1d2-182">O número total de solicitações de criação de aplicativos recebidas desde que o serviço foi iniciado</span><span class="sxs-lookup"><span data-stu-id="1d1d2-182">The total number of application creation requests received since the service was started</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d1d2-183">Total de respostas de HTTP 4xx</span><span class="sxs-lookup"><span data-stu-id="1d1d2-183">Total HTTP 4xx Responses</span></span></p></td>
<td><p><span data-ttu-id="1d1d2-184">O número total de respostas HTTP 4xx</span><span class="sxs-lookup"><span data-stu-id="1d1d2-184">The total number of HTTP 4xx responses</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d1d2-185">Total de respostas de HTTP 5xx</span><span class="sxs-lookup"><span data-stu-id="1d1d2-185">Total HTTP 5xx Responses</span></span></p></td>
<td><p><span data-ttu-id="1d1d2-186">O número total de respostas HTTP 5xx</span><span class="sxs-lookup"><span data-stu-id="1d1d2-186">The total number of HTTP 5xx responses</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d1d2-187">Total de solicitações recebidas no canal de comando</span><span class="sxs-lookup"><span data-stu-id="1d1d2-187">Total Requests Received on the Command Channel</span></span></p></td>
<td><p><span data-ttu-id="1d1d2-188">O número total de solicitações recebidas no canal do comando</span><span class="sxs-lookup"><span data-stu-id="1d1d2-188">The total number of requests received on the command channel</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d1d2-189">Total de solicitações bem-sucedidas</span><span class="sxs-lookup"><span data-stu-id="1d1d2-189">Total Requests Succeeded</span></span></p></td>
<td><p><span data-ttu-id="1d1d2-190">O número total de solicitações que tiveram êxito</span><span class="sxs-lookup"><span data-stu-id="1d1d2-190">The total number of requests that succeeded</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d1d2-191">Total de sessões iniciadas</span><span class="sxs-lookup"><span data-stu-id="1d1d2-191">Total Sessions Initiated</span></span></p></td>
<td><p><span data-ttu-id="1d1d2-192">O número total de sessões que foram iniciadas desde o início do serviço</span><span class="sxs-lookup"><span data-stu-id="1d1d2-192">The total number of sessions that were initiated since the service was started</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d1d2-193">Total de sessões encerradas devido ao tempo limite de ociosidade</span><span class="sxs-lookup"><span data-stu-id="1d1d2-193">Total Sessions Terminated Because of Idle Timeout</span></span></p></td>
<td><p><span data-ttu-id="1d1d2-194">O número total de sessões encerradas devido ao tempo limite de usuário ocioso</span><span class="sxs-lookup"><span data-stu-id="1d1d2-194">The total number of sessions that were terminated because of user idle timeout</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d1d2-195">Total de aplicativos limitado</span><span class="sxs-lookup"><span data-stu-id="1d1d2-195">Total Throttled Applications</span></span></p></td>
<td><p><span data-ttu-id="1d1d2-196">O número de aplicativos regulados</span><span class="sxs-lookup"><span data-stu-id="1d1d2-196">The number of throttled applications</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div id="sectionSection1" class="section">

### <a name="performance-counters-for-mcx-mobility-service"></a><span data-ttu-id="1d1d2-197">Contadores de desempenho para o serviço de mobilidade do MCX</span><span class="sxs-lookup"><span data-stu-id="1d1d2-197">Performance Counters for Mcx Mobility Service</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1d1d2-198">Contador</span><span class="sxs-lookup"><span data-stu-id="1d1d2-198">Counter</span></span></th>
<th><span data-ttu-id="1d1d2-199">Descrição</span><span class="sxs-lookup"><span data-stu-id="1d1d2-199">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1d1d2-200">Tempo média de vida de uma sessão em milissegundos</span><span class="sxs-lookup"><span data-stu-id="1d1d2-200">Average Lifetime for a Session in Milliseconds</span></span></p></td>
<td><p><span data-ttu-id="1d1d2-201">O tempo médio de vida de uma sessão em milissegundos</span><span class="sxs-lookup"><span data-stu-id="1d1d2-201">The average lifetime for a session in milliseconds</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d1d2-202">Assinaturas atuais de notificação por push</span><span class="sxs-lookup"><span data-stu-id="1d1d2-202">Current Push Notification Subscriptions</span></span></p></td>
<td><p><span data-ttu-id="1d1d2-203">O número atual de assinaturas de notificação por push.</span><span class="sxs-lookup"><span data-stu-id="1d1d2-203">The current number of push notification subscriptions.</span></span> <span data-ttu-id="1d1d2-204">Esse número, em conjunto com a contagem de sessão ativa no momento, representa o subconjunto de sessões ativas no momento que são registradas para dispositivos Windows Mobile ou iPhone.</span><span class="sxs-lookup"><span data-stu-id="1d1d2-204">This number, in conjunction with Currently Active Session Count, represents the subset of currently active sessions that are registered for Windows Mobile or iPhone devices.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d1d2-205">Contagem de polls de tempo limite de rede ativos no momento</span><span class="sxs-lookup"><span data-stu-id="1d1d2-205">Currently Active Network Timeout Poll Count</span></span></p></td>
<td><p><span data-ttu-id="1d1d2-206">O número de pools de rede que ultrapassaram o tempo limite</span><span class="sxs-lookup"><span data-stu-id="1d1d2-206">The number of network polls that timed out</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d1d2-207">Contagem de pools ativos no momento</span><span class="sxs-lookup"><span data-stu-id="1d1d2-207">Currently Active Poll Count</span></span></p></td>
<td><p><span data-ttu-id="1d1d2-208">O número de polls atualmente ativos (conexões de longa duração com o servidor)</span><span class="sxs-lookup"><span data-stu-id="1d1d2-208">The number of currently active polls (long-held connections to the server)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d1d2-209">Contagem de sessão ativa no momento</span><span class="sxs-lookup"><span data-stu-id="1d1d2-209">Currently Active Session Count</span></span></p></td>
<td><p><span data-ttu-id="1d1d2-210">Número atual de pontos de extremidade registrados no Serviço de Mobilidade</span><span class="sxs-lookup"><span data-stu-id="1d1d2-210">Current number of endpoints registered in the Mobility Service</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d1d2-211">Contagem de sessão ativa no momento com assinaturas de presença ativa</span><span class="sxs-lookup"><span data-stu-id="1d1d2-211">Currently Active Session Count with Active Presence Subscriptions</span></span></p></td>
<td><p><span data-ttu-id="1d1d2-212">O número de sessões ativas no momento com assinaturas de presença ativa</span><span class="sxs-lookup"><span data-stu-id="1d1d2-212">The number of currently active sessions with active presence subscriptions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d1d2-213">Solicitações de notificação por push sem êxito/segundo</span><span class="sxs-lookup"><span data-stu-id="1d1d2-213">Push Notification Requests Failed/Second</span></span></p></td>
<td><p><span data-ttu-id="1d1d2-214">A taxa de notificações por push sem êxito por segundo</span><span class="sxs-lookup"><span data-stu-id="1d1d2-214">The per second rate of failed push notifications</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d1d2-215">Solicitações de notificação por push bem-sucedidas/segundo</span><span class="sxs-lookup"><span data-stu-id="1d1d2-215">Push Notification Requests Succeeded/Second</span></span></p></td>
<td><p><span data-ttu-id="1d1d2-216">A taxa de notificações por push bem-sucedidas por segundo</span><span class="sxs-lookup"><span data-stu-id="1d1d2-216">The per second rate of successful push notifications</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d1d2-217">Solicitações de notificação por push limitadas/segundo</span><span class="sxs-lookup"><span data-stu-id="1d1d2-217">Push Notification Requests Throttled/Second</span></span></p></td>
<td><p><span data-ttu-id="1d1d2-218">A taxa de notificações por push limitadas por segundo</span><span class="sxs-lookup"><span data-stu-id="1d1d2-218">The per second rate of throttled push notifications</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d1d2-219">Solicitações de notificação por push/segundo</span><span class="sxs-lookup"><span data-stu-id="1d1d2-219">Push Notification Requests/Second</span></span></p></td>
<td><p><span data-ttu-id="1d1d2-220">A taxa de notificações por push enviadas por segundo</span><span class="sxs-lookup"><span data-stu-id="1d1d2-220">The per second rate of sent push notifications</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d1d2-221">Solicitações sem êxito/segundo</span><span class="sxs-lookup"><span data-stu-id="1d1d2-221">Requests Failed/Second</span></span></p></td>
<td><p><span data-ttu-id="1d1d2-222">A taxa de solicitações sem êxito por segundo</span><span class="sxs-lookup"><span data-stu-id="1d1d2-222">The per second rate of failed requests</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d1d2-223">Solicitações recebidas/segundo</span><span class="sxs-lookup"><span data-stu-id="1d1d2-223">Requests Received/Second</span></span></p></td>
<td><p><span data-ttu-id="1d1d2-224">A taxa de solicitações recebidas por segundo</span><span class="sxs-lookup"><span data-stu-id="1d1d2-224">The per second rate of received requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d1d2-225">Solicitações rejeitadas/segundo</span><span class="sxs-lookup"><span data-stu-id="1d1d2-225">Requests Rejected/Second</span></span></p></td>
<td><p><span data-ttu-id="1d1d2-226">A taxa de solicitações receitadas por segundo</span><span class="sxs-lookup"><span data-stu-id="1d1d2-226">The per second rate of rejected requests</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d1d2-227">Solicitações bem-sucedidas/segundo</span><span class="sxs-lookup"><span data-stu-id="1d1d2-227">Requests Succeeded/Second</span></span></p></td>
<td><p><span data-ttu-id="1d1d2-228">A taxa de solicitações bem-sucedidas por segundo</span><span class="sxs-lookup"><span data-stu-id="1d1d2-228">The per second rate of successful requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d1d2-229">Solicitações de início de sessão bem-sucedidas/segundo</span><span class="sxs-lookup"><span data-stu-id="1d1d2-229">Succeeded Initiate Session Requests/Second</span></span></p></td>
<td><p><span data-ttu-id="1d1d2-p102">A taxa de solicitações de Obter localização bem-sucedidas por segundo. As solicitações de início de uma sessão consomem grande parte do CPU no servidor. A carga de pico suportada é de 12/segundo. A sustentabilidade depende de outras cargas no servidor. Iniciar uma sessão normalmente significa um logon de um usuário que ficou desconectado durante um período extenso de tempo.</span><span class="sxs-lookup"><span data-stu-id="1d1d2-p102">The per second rate of successful Get Location requests. Requests to initiate a session consume the most CPU on the server. Peak supported load is 12/second. Sustainability depends on other loads on the server. Initiate a session typically means a sign-in for a user that has been signed out for an extended period of time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d1d2-235">Total de chamadas de voz de entrada recusadas</span><span class="sxs-lookup"><span data-stu-id="1d1d2-235">Total Declined Inbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="1d1d2-236">O número total de chamadas de voz de entrada recusadas</span><span class="sxs-lookup"><span data-stu-id="1d1d2-236">The total number of inbound voice calls that were declined</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d1d2-237">Total de chamadas de voz de entrada sem êxito</span><span class="sxs-lookup"><span data-stu-id="1d1d2-237">Total Failed Inbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="1d1d2-238">O número total de chamadas de voz de entrada que não tiveram êxito</span><span class="sxs-lookup"><span data-stu-id="1d1d2-238">The total number of inbound voice calls that failed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d1d2-239">Total de chamadas de voz de saída sem êxito</span><span class="sxs-lookup"><span data-stu-id="1d1d2-239">Total Failed Outbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="1d1d2-240">O número total de chamadas de voz de saída que não tiveram êxito</span><span class="sxs-lookup"><span data-stu-id="1d1d2-240">The total number of outbound voice calls that failed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d1d2-241">Número total de sessões encerradas pelo usuário</span><span class="sxs-lookup"><span data-stu-id="1d1d2-241">Total number of sessions terminated by user</span></span></p></td>
<td><p><span data-ttu-id="1d1d2-242">O número total de sessões encerradas por usuários</span><span class="sxs-lookup"><span data-stu-id="1d1d2-242">The total number of sessions terminated by users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d1d2-243">Total de solicitações de notificação por push</span><span class="sxs-lookup"><span data-stu-id="1d1d2-243">Total Push Notification Requests</span></span></p></td>
<td><p><span data-ttu-id="1d1d2-244">O número total de solicitações de notificação por push</span><span class="sxs-lookup"><span data-stu-id="1d1d2-244">The total number of push notification requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d1d2-245">Total de solicitações de notificação por push em êxito</span><span class="sxs-lookup"><span data-stu-id="1d1d2-245">Total Push Notification Requests Failed</span></span></p></td>
<td><p><span data-ttu-id="1d1d2-246">O número total de solicitações de notificação por push que não tiveram êxito</span><span class="sxs-lookup"><span data-stu-id="1d1d2-246">The total number of push notification requests that failed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d1d2-247">Total de solicitações de notificação por push bem-sucedidas</span><span class="sxs-lookup"><span data-stu-id="1d1d2-247">Total Push Notification Requests Succeeded</span></span></p></td>
<td><p><span data-ttu-id="1d1d2-248">O número total de solicitações de notificação por push bem-sucedidas</span><span class="sxs-lookup"><span data-stu-id="1d1d2-248">The total number of push notification requests that were successful</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d1d2-249">Total de solicitações de notificação por push limitadas</span><span class="sxs-lookup"><span data-stu-id="1d1d2-249">Total Push Notification Requests Throttled</span></span></p></td>
<td><p><span data-ttu-id="1d1d2-250">O número total de solicitações de notificação por push limitadas</span><span class="sxs-lookup"><span data-stu-id="1d1d2-250">The total number of push notification requests that were throttled</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d1d2-251">Total de solicitações sem êxito</span><span class="sxs-lookup"><span data-stu-id="1d1d2-251">Total Requests Failed</span></span></p></td>
<td><p><span data-ttu-id="1d1d2-252">O número total de solicitações que não tiveram êxito</span><span class="sxs-lookup"><span data-stu-id="1d1d2-252">The total number of requests that failed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d1d2-253">Total de solicitações recebidas no Canal de Comando</span><span class="sxs-lookup"><span data-stu-id="1d1d2-253">Total Requests received on the Command Channel</span></span></p></td>
<td><p><span data-ttu-id="1d1d2-254">O número total de solicitações recebidas no canal do comando</span><span class="sxs-lookup"><span data-stu-id="1d1d2-254">The total number of requests received on the command channel</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d1d2-255">Total de solicitações rejeitadas</span><span class="sxs-lookup"><span data-stu-id="1d1d2-255">Total Requests Rejected</span></span></p></td>
<td><p><span data-ttu-id="1d1d2-256">O número total de solicitações rejeitadas</span><span class="sxs-lookup"><span data-stu-id="1d1d2-256">The total number of requests that were rejected</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d1d2-257">Total de solicitações bem-sucedidas</span><span class="sxs-lookup"><span data-stu-id="1d1d2-257">Total Requests Succeeded</span></span></p></td>
<td><p><span data-ttu-id="1d1d2-258">O número total de solicitações feitas ao Serviço de Mobilidade que tiveram êxito</span><span class="sxs-lookup"><span data-stu-id="1d1d2-258">The total number of requests made to the Mobility Service that succeeded</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d1d2-259">Contagem total de sessões iniciadas</span><span class="sxs-lookup"><span data-stu-id="1d1d2-259">Total Session Initiated Count</span></span></p></td>
<td><p><span data-ttu-id="1d1d2-260">O número total de sessões iniciadas desde a inicialização do Serviço de Mobilidade</span><span class="sxs-lookup"><span data-stu-id="1d1d2-260">The total number of sessions that were initiated since the Mobility Service was started</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d1d2-261">Total de sessões encerradas devido ao tempo limite de usuário ocioso</span><span class="sxs-lookup"><span data-stu-id="1d1d2-261">Total Sessions Terminated Because of User Idle Timeout</span></span></p></td>
<td><p><span data-ttu-id="1d1d2-262">O número total de sessões encerradas devido ao tempo limite de usuário ocioso</span><span class="sxs-lookup"><span data-stu-id="1d1d2-262">The total number of sessions that were terminated because of user idle timeout</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d1d2-263">Total de chamadas de voz de entrada bem-sucedidas</span><span class="sxs-lookup"><span data-stu-id="1d1d2-263">Total Successful Inbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="1d1d2-264">O número total de chamadas de voz de entrada que tiveram êxito</span><span class="sxs-lookup"><span data-stu-id="1d1d2-264">The total number of inbound voice calls that were successful</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d1d2-265">Total de chamadas de voz de saída bem-sucedidas</span><span class="sxs-lookup"><span data-stu-id="1d1d2-265">Total Successful Outbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="1d1d2-266">O número total de chamadas de voz de saída que tiveram êxito</span><span class="sxs-lookup"><span data-stu-id="1d1d2-266">The total number of outbound voice calls that were successful</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

