---
title: 'Lync Server 2013: eventos do UCWA'
description: 'Lync Server 2013: eventos do UCWA.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: UCWA events
ms:assetid: 26cb409d-f4e4-43c7-873f-b694702d491d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945621(v=OCS.15)
ms:contentKeyID: 51541461
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8104ce9c7533350f40ce194e1cde205bc3692792
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548847"
---
# <a name="ucwa-events-in-lync-server-2013"></a><span data-ttu-id="d4781-103">Eventos do UCWA no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d4781-103">UCWA events in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d4781-104">_**Última modificação do tópico:** 2013-02-15_</span><span class="sxs-lookup"><span data-stu-id="d4781-104">_**Topic Last Modified:** 2013-02-15_</span></span>

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<span data-ttu-id="d4781-105">O Lync Server 2013 usa a UCWA (Unified Communications Web API) para várias finalidades, desde o acesso ao Microsoft Exchange para pesquisas de contato até a atualização de presença para clientes móveis.</span><span class="sxs-lookup"><span data-stu-id="d4781-105">Lync Server 2013 uses the Unified Communications Web API (UCWA) for a number of purposes, from accessing Microsoft Exchange for contact searches to updating presence for mobile clients.</span></span>

<span data-ttu-id="d4781-106">O UCWA gravará registros de comportamento operacional como tipos de eventos informativos, avisos e erros.</span><span class="sxs-lookup"><span data-stu-id="d4781-106">UCWA will write records of operational behavior as event types Informational, Warning, and Error.</span></span> <span data-ttu-id="d4781-107">A tabela a seguir descreve os eventos que podem ser gravados pelos componentes do UCWA.</span><span class="sxs-lookup"><span data-stu-id="d4781-107">The following table describes the events that can be written by the UCWA components.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d4781-108">ID de evento</span><span class="sxs-lookup"><span data-stu-id="d4781-108">Event ID</span></span></th>
<th><span data-ttu-id="d4781-109">Tipo de Evento</span><span class="sxs-lookup"><span data-stu-id="d4781-109">Event Type</span></span></th>
<th><span data-ttu-id="d4781-110">Resumo</span><span class="sxs-lookup"><span data-stu-id="d4781-110">Summary</span></span></th>
<th><span data-ttu-id="d4781-111">Causa e resolução</span><span class="sxs-lookup"><span data-stu-id="d4781-111">Cause and Resolution</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d4781-112">20001</span><span class="sxs-lookup"><span data-stu-id="d4781-112">20001</span></span></p></td>
<td><p><span data-ttu-id="d4781-113">Informativa</span><span class="sxs-lookup"><span data-stu-id="d4781-113">Informational</span></span></p></td>
<td><p><span data-ttu-id="d4781-114">UCWA inicializado</span><span class="sxs-lookup"><span data-stu-id="d4781-114">UCWA initialized</span></span></p></td>
<td><p><span data-ttu-id="d4781-115">N/D</span><span class="sxs-lookup"><span data-stu-id="d4781-115">N/A</span></span></p>
<p><span data-ttu-id="d4781-116">N/D</span><span class="sxs-lookup"><span data-stu-id="d4781-116">N/A</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d4781-117">20002</span><span class="sxs-lookup"><span data-stu-id="d4781-117">20002</span></span></p></td>
<td><p><span data-ttu-id="d4781-118">Erro</span><span class="sxs-lookup"><span data-stu-id="d4781-118">Error</span></span></p></td>
<td><p><span data-ttu-id="d4781-119">UCWA encontrou uma exceção inesperada durante a inicialização</span><span class="sxs-lookup"><span data-stu-id="d4781-119">UCWA encountered an unexpected exception during initialization</span></span></p></td>
<td><p><span data-ttu-id="d4781-120">Ocorreu um erro inesperado durante a inicialização</span><span class="sxs-lookup"><span data-stu-id="d4781-120">An unexpected error has occurred during initialization</span></span></p>
<p><span data-ttu-id="d4781-121">Examine os detalhes da exceção na entrada do log de eventos associada para determinar a possível causa</span><span class="sxs-lookup"><span data-stu-id="d4781-121">Examine the exception details in the associated event log entry to determine the possible cause</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d4781-122">20003</span><span class="sxs-lookup"><span data-stu-id="d4781-122">20003</span></span></p></td>
<td><p><span data-ttu-id="d4781-123">Erro</span><span class="sxs-lookup"><span data-stu-id="d4781-123">Error</span></span></p></td>
<td><p><span data-ttu-id="d4781-124">UCWA encontrou uma exceção não manipulada</span><span class="sxs-lookup"><span data-stu-id="d4781-124">UCWA encountered an unhandled exception</span></span></p></td>
<td><p><span data-ttu-id="d4781-125">Ocorreu uma exceção não manipulada</span><span class="sxs-lookup"><span data-stu-id="d4781-125">An unhandled exception happened</span></span></p>
<p><span data-ttu-id="d4781-126">Reiniciar o servidor.</span><span class="sxs-lookup"><span data-stu-id="d4781-126">Restart the server.</span></span> <span data-ttu-id="d4781-127">Se o problema persistir, contate o suporte ao produto</span><span class="sxs-lookup"><span data-stu-id="d4781-127">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d4781-128">20004</span><span class="sxs-lookup"><span data-stu-id="d4781-128">20004</span></span></p></td>
<td><p><span data-ttu-id="d4781-129">Erro</span><span class="sxs-lookup"><span data-stu-id="d4781-129">Error</span></span></p></td>
<td><p><span data-ttu-id="d4781-130">Não é possível acessar o Exchange para foto HD</span><span class="sxs-lookup"><span data-stu-id="d4781-130">Cannot access Exchange for HD photo</span></span></p></td>
<td><p><span data-ttu-id="d4781-131">A conexão com o Exchange não está disponível</span><span class="sxs-lookup"><span data-stu-id="d4781-131">Connection to Exchange is not available</span></span></p>
<p><span data-ttu-id="d4781-132">Certifique-se de que a conexão com o Exchange esteja disponível</span><span class="sxs-lookup"><span data-stu-id="d4781-132">Make sure the connection to Exchange is available</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d4781-133">20005</span><span class="sxs-lookup"><span data-stu-id="d4781-133">20005</span></span></p></td>
<td><p><span data-ttu-id="d4781-134">Informativa</span><span class="sxs-lookup"><span data-stu-id="d4781-134">Informational</span></span></p></td>
<td><p><span data-ttu-id="d4781-135">Recuperação de falha ao acessar o Exchange para foto HD</span><span class="sxs-lookup"><span data-stu-id="d4781-135">Recovered from failing to access Exchange for HD photo</span></span></p></td>
<td><p><span data-ttu-id="d4781-136">N/D</span><span class="sxs-lookup"><span data-stu-id="d4781-136">N/A</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d4781-137">20006</span><span class="sxs-lookup"><span data-stu-id="d4781-137">20006</span></span></p></td>
<td><p><span data-ttu-id="d4781-138">Erro</span><span class="sxs-lookup"><span data-stu-id="d4781-138">Error</span></span></p></td>
<td><p><span data-ttu-id="d4781-139">Não é possível acessar o Exchange para pesquisa de contato</span><span class="sxs-lookup"><span data-stu-id="d4781-139">Cannot access Exchange for contact search</span></span></p></td>
<td><p><span data-ttu-id="d4781-140">A conexão com o Exchange não está disponível</span><span class="sxs-lookup"><span data-stu-id="d4781-140">Connection to Exchange is not available</span></span></p>
<p><span data-ttu-id="d4781-141">Certifique-se de que a conexão com o Exchange esteja disponível</span><span class="sxs-lookup"><span data-stu-id="d4781-141">Make sure the connection to Exchange is available</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d4781-142">20007</span><span class="sxs-lookup"><span data-stu-id="d4781-142">20007</span></span></p></td>
<td><p><span data-ttu-id="d4781-143">Informativa</span><span class="sxs-lookup"><span data-stu-id="d4781-143">Informational</span></span></p></td>
<td><p><span data-ttu-id="d4781-144">Recuperado da falha ao pesquisar o contato no Exchange</span><span class="sxs-lookup"><span data-stu-id="d4781-144">Recovered from failing to search contact in Exchange</span></span></p></td>
<td><p><span data-ttu-id="d4781-145">N/D</span><span class="sxs-lookup"><span data-stu-id="d4781-145">N/A</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d4781-146">20008</span><span class="sxs-lookup"><span data-stu-id="d4781-146">20008</span></span></p></td>
<td><p><span data-ttu-id="d4781-147">Aviso</span><span class="sxs-lookup"><span data-stu-id="d4781-147">Warning</span></span></p></td>
<td><p><span data-ttu-id="d4781-148">Tentativa de inscrever mais do que as assinaturas de presença permitidas por aplicativo</span><span class="sxs-lookup"><span data-stu-id="d4781-148">Attempt to subscribe more than the allowed presence subscriptions per application</span></span></p></td>
<td><p><span data-ttu-id="d4781-149">Tentativa de inscrever mais do que as assinaturas de presença permitidas por aplicativo</span><span class="sxs-lookup"><span data-stu-id="d4781-149">Attempt to subscribe more than the allowed presence subscriptions per application</span></span></p>
<p><span data-ttu-id="d4781-150">Verifique se há assinaturas desnecessárias nos clientes</span><span class="sxs-lookup"><span data-stu-id="d4781-150">Check the clients for unnecessary subscriptions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d4781-151">20009</span><span class="sxs-lookup"><span data-stu-id="d4781-151">20009</span></span></p></td>
<td><p><span data-ttu-id="d4781-152">Aviso</span><span class="sxs-lookup"><span data-stu-id="d4781-152">Warning</span></span></p></td>
<td><p><span data-ttu-id="d4781-153">Tentativa de inscrever mais do que as assinaturas de presença permitidas por lote</span><span class="sxs-lookup"><span data-stu-id="d4781-153">Attempt to subscribe more than the allowed presence subscriptions per batch</span></span></p></td>
<td><p><span data-ttu-id="d4781-154">Tentativa de inscrever mais do que as assinaturas de presença permitidas por lote</span><span class="sxs-lookup"><span data-stu-id="d4781-154">Attempt to subscribe more than the allowed presence subscriptions per batch</span></span></p>
<p><span data-ttu-id="d4781-155">Verifique se há assinaturas desnecessárias nos clientes</span><span class="sxs-lookup"><span data-stu-id="d4781-155">Check the clients for unnecessary subscriptions</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d4781-156">20010</span><span class="sxs-lookup"><span data-stu-id="d4781-156">20010</span></span></p></td>
<td><p><span data-ttu-id="d4781-157">Erro</span><span class="sxs-lookup"><span data-stu-id="d4781-157">Error</span></span></p></td>
<td><p><span data-ttu-id="d4781-158">Não é possível recuperar dados de inband</span><span class="sxs-lookup"><span data-stu-id="d4781-158">Cannot retrieve inband data</span></span></p></td>
<td><p><span data-ttu-id="d4781-159">Não é possível recuperar dados de inband</span><span class="sxs-lookup"><span data-stu-id="d4781-159">Cannot retrieve inband data</span></span></p>
<p><span data-ttu-id="d4781-160">Se o problema persistir, contate o suporte ao produto</span><span class="sxs-lookup"><span data-stu-id="d4781-160">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d4781-161">20011</span><span class="sxs-lookup"><span data-stu-id="d4781-161">20011</span></span></p></td>
<td><p><span data-ttu-id="d4781-162">Erro</span><span class="sxs-lookup"><span data-stu-id="d4781-162">Error</span></span></p></td>
<td><p><span data-ttu-id="d4781-163">Não é possível assinar a presença</span><span class="sxs-lookup"><span data-stu-id="d4781-163">Cannot subscribe presence</span></span></p></td>
<td><p><span data-ttu-id="d4781-164">Não é possível assinar a presença</span><span class="sxs-lookup"><span data-stu-id="d4781-164">Cannot subscribe presence</span></span></p>
<p><span data-ttu-id="d4781-165">Se o problema persistir, contate o suporte ao produto</span><span class="sxs-lookup"><span data-stu-id="d4781-165">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d4781-166">20012</span><span class="sxs-lookup"><span data-stu-id="d4781-166">20012</span></span></p></td>
<td><p><span data-ttu-id="d4781-167">Erro</span><span class="sxs-lookup"><span data-stu-id="d4781-167">Error</span></span></p></td>
<td><p><span data-ttu-id="d4781-168">Falha ao registrar o ponto de extremidade</span><span class="sxs-lookup"><span data-stu-id="d4781-168">Failed to register endpoint</span></span></p></td>
<td><p><span data-ttu-id="d4781-169">Falha ao registrar o ponto de extremidade</span><span class="sxs-lookup"><span data-stu-id="d4781-169">Failed to register endpoint</span></span></p>
<p><span data-ttu-id="d4781-170">Se o problema persistir, contate o suporte ao produto</span><span class="sxs-lookup"><span data-stu-id="d4781-170">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d4781-171">20013</span><span class="sxs-lookup"><span data-stu-id="d4781-171">20013</span></span></p></td>
<td><p><span data-ttu-id="d4781-172">Erro</span><span class="sxs-lookup"><span data-stu-id="d4781-172">Error</span></span></p></td>
<td><p><span data-ttu-id="d4781-173">IM MCU não está disponível</span><span class="sxs-lookup"><span data-stu-id="d4781-173">IM MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="d4781-174">IM MCU não está disponível</span><span class="sxs-lookup"><span data-stu-id="d4781-174">IM MCU is unavailable</span></span></p>
<p><span data-ttu-id="d4781-175">Veja se o IM MCU está em execução</span><span class="sxs-lookup"><span data-stu-id="d4781-175">See whether IM MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d4781-176">20014</span><span class="sxs-lookup"><span data-stu-id="d4781-176">20014</span></span></p></td>
<td><p><span data-ttu-id="d4781-177">Informativa</span><span class="sxs-lookup"><span data-stu-id="d4781-177">Informational</span></span></p></td>
<td><p><span data-ttu-id="d4781-178">Recuperação de falha na conexão com a MCU de IM</span><span class="sxs-lookup"><span data-stu-id="d4781-178">Recovered from failing to connect to IM MCU</span></span></p></td>
<td><p><span data-ttu-id="d4781-179">N/D</span><span class="sxs-lookup"><span data-stu-id="d4781-179">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d4781-180">20015</span><span class="sxs-lookup"><span data-stu-id="d4781-180">20015</span></span></p></td>
<td><p><span data-ttu-id="d4781-181">Erro</span><span class="sxs-lookup"><span data-stu-id="d4781-181">Error</span></span></p></td>
<td><p><span data-ttu-id="d4781-182">AV MCU não está disponível</span><span class="sxs-lookup"><span data-stu-id="d4781-182">AV MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="d4781-183">AV MCU não está disponível</span><span class="sxs-lookup"><span data-stu-id="d4781-183">AV MCU is unavailable</span></span></p>
<p><span data-ttu-id="d4781-184">Veja se o AV MCU está em execução</span><span class="sxs-lookup"><span data-stu-id="d4781-184">See whether AV MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d4781-185">20016</span><span class="sxs-lookup"><span data-stu-id="d4781-185">20016</span></span></p></td>
<td><p><span data-ttu-id="d4781-186">Informativa</span><span class="sxs-lookup"><span data-stu-id="d4781-186">Informational</span></span></p></td>
<td><p><span data-ttu-id="d4781-187">Recuperação de falha na conexão com o AV MCU</span><span class="sxs-lookup"><span data-stu-id="d4781-187">Recovered from failing to connect to AV MCU</span></span></p></td>
<td><p><span data-ttu-id="d4781-188">N/D</span><span class="sxs-lookup"><span data-stu-id="d4781-188">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d4781-189">20017</span><span class="sxs-lookup"><span data-stu-id="d4781-189">20017</span></span></p></td>
<td><p><span data-ttu-id="d4781-190">Erro</span><span class="sxs-lookup"><span data-stu-id="d4781-190">Error</span></span></p></td>
<td><p><span data-ttu-id="d4781-191">À medida que a MCU não está disponível</span><span class="sxs-lookup"><span data-stu-id="d4781-191">AS MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="d4781-192">À medida que a MCU não está disponível</span><span class="sxs-lookup"><span data-stu-id="d4781-192">AS MCU is unavailable</span></span></p>
<p><span data-ttu-id="d4781-193">Confira se a MCU está sendo executada</span><span class="sxs-lookup"><span data-stu-id="d4781-193">See whether AS MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d4781-194">20018</span><span class="sxs-lookup"><span data-stu-id="d4781-194">20018</span></span></p></td>
<td><p><span data-ttu-id="d4781-195">Informativa</span><span class="sxs-lookup"><span data-stu-id="d4781-195">Informational</span></span></p></td>
<td><p><span data-ttu-id="d4781-196">Recuperação de falha na conexão com a MCU</span><span class="sxs-lookup"><span data-stu-id="d4781-196">Recovered from failing to connect to AS MCU</span></span></p></td>
<td><p><span data-ttu-id="d4781-197">N/D</span><span class="sxs-lookup"><span data-stu-id="d4781-197">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d4781-198">20019</span><span class="sxs-lookup"><span data-stu-id="d4781-198">20019</span></span></p></td>
<td><p><span data-ttu-id="d4781-199">Erro</span><span class="sxs-lookup"><span data-stu-id="d4781-199">Error</span></span></p></td>
<td><p><span data-ttu-id="d4781-200">Data MCU não está disponível</span><span class="sxs-lookup"><span data-stu-id="d4781-200">Data MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="d4781-201">Data MCU não está disponível</span><span class="sxs-lookup"><span data-stu-id="d4781-201">Data MCU is unavailable</span></span></p>
<p><span data-ttu-id="d4781-202">Ver se os dados MCU estão sendo executados</span><span class="sxs-lookup"><span data-stu-id="d4781-202">See whether Data MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d4781-203">20020</span><span class="sxs-lookup"><span data-stu-id="d4781-203">20020</span></span></p></td>
<td><p><span data-ttu-id="d4781-204">Informativa</span><span class="sxs-lookup"><span data-stu-id="d4781-204">Informational</span></span></p></td>
<td><p><span data-ttu-id="d4781-205">Recuperação de falha na conexão com o data MCU</span><span class="sxs-lookup"><span data-stu-id="d4781-205">Recovered from failing to connect to Data MCU</span></span></p></td>
<td><p><span data-ttu-id="d4781-206">N/D</span><span class="sxs-lookup"><span data-stu-id="d4781-206">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d4781-207">20021</span><span class="sxs-lookup"><span data-stu-id="d4781-207">20021</span></span></p></td>
<td><p><span data-ttu-id="d4781-208">Erro</span><span class="sxs-lookup"><span data-stu-id="d4781-208">Error</span></span></p></td>
<td><p><span data-ttu-id="d4781-209">Não é possível ingressar no IM MCU</span><span class="sxs-lookup"><span data-stu-id="d4781-209">Cannot join IM MCU</span></span></p></td>
<td><p><span data-ttu-id="d4781-210">Não é possível ingressar no IM MCU</span><span class="sxs-lookup"><span data-stu-id="d4781-210">Cannot join IM MCU</span></span></p>
<p><span data-ttu-id="d4781-211">Veja se o IM MCU está em execução</span><span class="sxs-lookup"><span data-stu-id="d4781-211">See whether IM MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d4781-212">20022</span><span class="sxs-lookup"><span data-stu-id="d4781-212">20022</span></span></p></td>
<td><p><span data-ttu-id="d4781-213">Erro</span><span class="sxs-lookup"><span data-stu-id="d4781-213">Error</span></span></p></td>
<td><p><span data-ttu-id="d4781-214">Não é possível ingressar no AV MCU</span><span class="sxs-lookup"><span data-stu-id="d4781-214">Cannot join AV MCU</span></span></p></td>
<td><p><span data-ttu-id="d4781-215">Não é possível ingressar no AV MCU</span><span class="sxs-lookup"><span data-stu-id="d4781-215">Cannot join AV MCU</span></span></p>
<p><span data-ttu-id="d4781-216">Veja se o AV MCU está em execução</span><span class="sxs-lookup"><span data-stu-id="d4781-216">See whether AV MCU is running</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d4781-217">20023</span><span class="sxs-lookup"><span data-stu-id="d4781-217">20023</span></span></p></td>
<td><p><span data-ttu-id="d4781-218">Erro</span><span class="sxs-lookup"><span data-stu-id="d4781-218">Error</span></span></p></td>
<td><p><span data-ttu-id="d4781-219">Não é possível entrar como MCU</span><span class="sxs-lookup"><span data-stu-id="d4781-219">Cannot join AS MCU</span></span></p></td>
<td><p><span data-ttu-id="d4781-220">Não é possível entrar como MCU</span><span class="sxs-lookup"><span data-stu-id="d4781-220">Cannot join AS MCU</span></span></p>
<p><span data-ttu-id="d4781-221">Confira se a MCU está sendo executada</span><span class="sxs-lookup"><span data-stu-id="d4781-221">See whether AS MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d4781-222">20024</span><span class="sxs-lookup"><span data-stu-id="d4781-222">20024</span></span></p></td>
<td><p><span data-ttu-id="d4781-223">Erro</span><span class="sxs-lookup"><span data-stu-id="d4781-223">Error</span></span></p></td>
<td><p><span data-ttu-id="d4781-224">Não é possível participar dos dados MCU</span><span class="sxs-lookup"><span data-stu-id="d4781-224">Cannot join Data MCU</span></span></p></td>
<td><p><span data-ttu-id="d4781-225">Não é possível participar dos dados MCU</span><span class="sxs-lookup"><span data-stu-id="d4781-225">Cannot join Data MCU</span></span></p>
<p><span data-ttu-id="d4781-226">Ver se os dados MCU estão sendo executados</span><span class="sxs-lookup"><span data-stu-id="d4781-226">See whether Data MCU is running</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d4781-227">20025</span><span class="sxs-lookup"><span data-stu-id="d4781-227">20025</span></span></p></td>
<td><p><span data-ttu-id="d4781-228">Erro</span><span class="sxs-lookup"><span data-stu-id="d4781-228">Error</span></span></p></td>
<td><p><span data-ttu-id="d4781-229">Não é possível acessar o Active Directory para a foto</span><span class="sxs-lookup"><span data-stu-id="d4781-229">Cannot access active directory for photo</span></span></p></td>
<td><p><span data-ttu-id="d4781-230">A conexão com o Active Directory não está disponível</span><span class="sxs-lookup"><span data-stu-id="d4781-230">Connection to active directory is not available</span></span></p>
<p><span data-ttu-id="d4781-231">Certifique-se de que a conexão com o Active Directory está disponível</span><span class="sxs-lookup"><span data-stu-id="d4781-231">Make sure the connection to active directory is available</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d4781-232">20026</span><span class="sxs-lookup"><span data-stu-id="d4781-232">20026</span></span></p></td>
<td><p><span data-ttu-id="d4781-233">Informativa</span><span class="sxs-lookup"><span data-stu-id="d4781-233">Informational</span></span></p></td>
<td><p><span data-ttu-id="d4781-234">Recuperação de falha ao acessar o Active Directory para foto</span><span class="sxs-lookup"><span data-stu-id="d4781-234">Recovered from failing to access active directory for photo</span></span></p></td>
<td><p><span data-ttu-id="d4781-235">N/D</span><span class="sxs-lookup"><span data-stu-id="d4781-235">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d4781-236">20027</span><span class="sxs-lookup"><span data-stu-id="d4781-236">20027</span></span></p></td>
<td><p><span data-ttu-id="d4781-237">Aviso</span><span class="sxs-lookup"><span data-stu-id="d4781-237">Warning</span></span></p></td>
<td><p><span data-ttu-id="d4781-238">Não é possível desserializar</span><span class="sxs-lookup"><span data-stu-id="d4781-238">Cannot deserialize</span></span></p></td>
<td><p><span data-ttu-id="d4781-239">Não é possível desserializar</span><span class="sxs-lookup"><span data-stu-id="d4781-239">Cannot deserialize</span></span></p>
<p><span data-ttu-id="d4781-240">Se o problema persistir, contate o suporte ao produto</span><span class="sxs-lookup"><span data-stu-id="d4781-240">If the problem persists contact product support</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

