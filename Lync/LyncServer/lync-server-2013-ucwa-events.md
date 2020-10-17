---
title: 'Lync Server 2013: eventos do UCWA'
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
ms.openlocfilehash: 1ae71fa6e91c0bc212bc019b1afa85ebcacb4d0d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527788"
---
# <a name="ucwa-events-in-lync-server-2013"></a><span data-ttu-id="a297c-102">Eventos do UCWA no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a297c-102">UCWA events in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a297c-103">_**Última modificação do tópico:** 2013-02-15_</span><span class="sxs-lookup"><span data-stu-id="a297c-103">_**Topic Last Modified:** 2013-02-15_</span></span>

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<span data-ttu-id="a297c-104">O Lync Server 2013 usa a UCWA (Unified Communications Web API) para várias finalidades, desde o acesso ao Microsoft Exchange para pesquisas de contato até a atualização de presença para clientes móveis.</span><span class="sxs-lookup"><span data-stu-id="a297c-104">Lync Server 2013 uses the Unified Communications Web API (UCWA) for a number of purposes, from accessing Microsoft Exchange for contact searches to updating presence for mobile clients.</span></span>

<span data-ttu-id="a297c-105">O UCWA gravará registros de comportamento operacional como tipos de eventos informativos, avisos e erros.</span><span class="sxs-lookup"><span data-stu-id="a297c-105">UCWA will write records of operational behavior as event types Informational, Warning, and Error.</span></span> <span data-ttu-id="a297c-106">A tabela a seguir descreve os eventos que podem ser gravados pelos componentes do UCWA.</span><span class="sxs-lookup"><span data-stu-id="a297c-106">The following table describes the events that can be written by the UCWA components.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a297c-107">ID de evento</span><span class="sxs-lookup"><span data-stu-id="a297c-107">Event ID</span></span></th>
<th><span data-ttu-id="a297c-108">Tipo de Evento</span><span class="sxs-lookup"><span data-stu-id="a297c-108">Event Type</span></span></th>
<th><span data-ttu-id="a297c-109">Resumo</span><span class="sxs-lookup"><span data-stu-id="a297c-109">Summary</span></span></th>
<th><span data-ttu-id="a297c-110">Causa e resolução</span><span class="sxs-lookup"><span data-stu-id="a297c-110">Cause and Resolution</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a297c-111">20001</span><span class="sxs-lookup"><span data-stu-id="a297c-111">20001</span></span></p></td>
<td><p><span data-ttu-id="a297c-112">Informativa</span><span class="sxs-lookup"><span data-stu-id="a297c-112">Informational</span></span></p></td>
<td><p><span data-ttu-id="a297c-113">UCWA inicializado</span><span class="sxs-lookup"><span data-stu-id="a297c-113">UCWA initialized</span></span></p></td>
<td><p><span data-ttu-id="a297c-114">N/D</span><span class="sxs-lookup"><span data-stu-id="a297c-114">N/A</span></span></p>
<p><span data-ttu-id="a297c-115">N/D</span><span class="sxs-lookup"><span data-stu-id="a297c-115">N/A</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a297c-116">20002</span><span class="sxs-lookup"><span data-stu-id="a297c-116">20002</span></span></p></td>
<td><p><span data-ttu-id="a297c-117">Erro</span><span class="sxs-lookup"><span data-stu-id="a297c-117">Error</span></span></p></td>
<td><p><span data-ttu-id="a297c-118">UCWA encontrou uma exceção inesperada durante a inicialização</span><span class="sxs-lookup"><span data-stu-id="a297c-118">UCWA encountered an unexpected exception during initialization</span></span></p></td>
<td><p><span data-ttu-id="a297c-119">Ocorreu um erro inesperado durante a inicialização</span><span class="sxs-lookup"><span data-stu-id="a297c-119">An unexpected error has occurred during initialization</span></span></p>
<p><span data-ttu-id="a297c-120">Examine os detalhes da exceção na entrada do log de eventos associada para determinar a possível causa</span><span class="sxs-lookup"><span data-stu-id="a297c-120">Examine the exception details in the associated event log entry to determine the possible cause</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a297c-121">20003</span><span class="sxs-lookup"><span data-stu-id="a297c-121">20003</span></span></p></td>
<td><p><span data-ttu-id="a297c-122">Erro</span><span class="sxs-lookup"><span data-stu-id="a297c-122">Error</span></span></p></td>
<td><p><span data-ttu-id="a297c-123">UCWA encontrou uma exceção não manipulada</span><span class="sxs-lookup"><span data-stu-id="a297c-123">UCWA encountered an unhandled exception</span></span></p></td>
<td><p><span data-ttu-id="a297c-124">Ocorreu uma exceção não manipulada</span><span class="sxs-lookup"><span data-stu-id="a297c-124">An unhandled exception happened</span></span></p>
<p><span data-ttu-id="a297c-125">Reiniciar o servidor.</span><span class="sxs-lookup"><span data-stu-id="a297c-125">Restart the server.</span></span> <span data-ttu-id="a297c-126">Se o problema persistir, contate o suporte ao produto</span><span class="sxs-lookup"><span data-stu-id="a297c-126">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a297c-127">20004</span><span class="sxs-lookup"><span data-stu-id="a297c-127">20004</span></span></p></td>
<td><p><span data-ttu-id="a297c-128">Erro</span><span class="sxs-lookup"><span data-stu-id="a297c-128">Error</span></span></p></td>
<td><p><span data-ttu-id="a297c-129">Não é possível acessar o Exchange para foto HD</span><span class="sxs-lookup"><span data-stu-id="a297c-129">Cannot access Exchange for HD photo</span></span></p></td>
<td><p><span data-ttu-id="a297c-130">A conexão com o Exchange não está disponível</span><span class="sxs-lookup"><span data-stu-id="a297c-130">Connection to Exchange is not available</span></span></p>
<p><span data-ttu-id="a297c-131">Certifique-se de que a conexão com o Exchange esteja disponível</span><span class="sxs-lookup"><span data-stu-id="a297c-131">Make sure the connection to Exchange is available</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a297c-132">20005</span><span class="sxs-lookup"><span data-stu-id="a297c-132">20005</span></span></p></td>
<td><p><span data-ttu-id="a297c-133">Informativa</span><span class="sxs-lookup"><span data-stu-id="a297c-133">Informational</span></span></p></td>
<td><p><span data-ttu-id="a297c-134">Recuperação de falha ao acessar o Exchange para foto HD</span><span class="sxs-lookup"><span data-stu-id="a297c-134">Recovered from failing to access Exchange for HD photo</span></span></p></td>
<td><p><span data-ttu-id="a297c-135">N/D</span><span class="sxs-lookup"><span data-stu-id="a297c-135">N/A</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a297c-136">20006</span><span class="sxs-lookup"><span data-stu-id="a297c-136">20006</span></span></p></td>
<td><p><span data-ttu-id="a297c-137">Erro</span><span class="sxs-lookup"><span data-stu-id="a297c-137">Error</span></span></p></td>
<td><p><span data-ttu-id="a297c-138">Não é possível acessar o Exchange para pesquisa de contato</span><span class="sxs-lookup"><span data-stu-id="a297c-138">Cannot access Exchange for contact search</span></span></p></td>
<td><p><span data-ttu-id="a297c-139">A conexão com o Exchange não está disponível</span><span class="sxs-lookup"><span data-stu-id="a297c-139">Connection to Exchange is not available</span></span></p>
<p><span data-ttu-id="a297c-140">Certifique-se de que a conexão com o Exchange esteja disponível</span><span class="sxs-lookup"><span data-stu-id="a297c-140">Make sure the connection to Exchange is available</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a297c-141">20007</span><span class="sxs-lookup"><span data-stu-id="a297c-141">20007</span></span></p></td>
<td><p><span data-ttu-id="a297c-142">Informativa</span><span class="sxs-lookup"><span data-stu-id="a297c-142">Informational</span></span></p></td>
<td><p><span data-ttu-id="a297c-143">Recuperado da falha ao pesquisar o contato no Exchange</span><span class="sxs-lookup"><span data-stu-id="a297c-143">Recovered from failing to search contact in Exchange</span></span></p></td>
<td><p><span data-ttu-id="a297c-144">N/D</span><span class="sxs-lookup"><span data-stu-id="a297c-144">N/A</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a297c-145">20008</span><span class="sxs-lookup"><span data-stu-id="a297c-145">20008</span></span></p></td>
<td><p><span data-ttu-id="a297c-146">Aviso</span><span class="sxs-lookup"><span data-stu-id="a297c-146">Warning</span></span></p></td>
<td><p><span data-ttu-id="a297c-147">Tentativa de inscrever mais do que as assinaturas de presença permitidas por aplicativo</span><span class="sxs-lookup"><span data-stu-id="a297c-147">Attempt to subscribe more than the allowed presence subscriptions per application</span></span></p></td>
<td><p><span data-ttu-id="a297c-148">Tentativa de inscrever mais do que as assinaturas de presença permitidas por aplicativo</span><span class="sxs-lookup"><span data-stu-id="a297c-148">Attempt to subscribe more than the allowed presence subscriptions per application</span></span></p>
<p><span data-ttu-id="a297c-149">Verifique se há assinaturas desnecessárias nos clientes</span><span class="sxs-lookup"><span data-stu-id="a297c-149">Check the clients for unnecessary subscriptions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a297c-150">20009</span><span class="sxs-lookup"><span data-stu-id="a297c-150">20009</span></span></p></td>
<td><p><span data-ttu-id="a297c-151">Aviso</span><span class="sxs-lookup"><span data-stu-id="a297c-151">Warning</span></span></p></td>
<td><p><span data-ttu-id="a297c-152">Tentativa de inscrever mais do que as assinaturas de presença permitidas por lote</span><span class="sxs-lookup"><span data-stu-id="a297c-152">Attempt to subscribe more than the allowed presence subscriptions per batch</span></span></p></td>
<td><p><span data-ttu-id="a297c-153">Tentativa de inscrever mais do que as assinaturas de presença permitidas por lote</span><span class="sxs-lookup"><span data-stu-id="a297c-153">Attempt to subscribe more than the allowed presence subscriptions per batch</span></span></p>
<p><span data-ttu-id="a297c-154">Verifique se há assinaturas desnecessárias nos clientes</span><span class="sxs-lookup"><span data-stu-id="a297c-154">Check the clients for unnecessary subscriptions</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a297c-155">20010</span><span class="sxs-lookup"><span data-stu-id="a297c-155">20010</span></span></p></td>
<td><p><span data-ttu-id="a297c-156">Erro</span><span class="sxs-lookup"><span data-stu-id="a297c-156">Error</span></span></p></td>
<td><p><span data-ttu-id="a297c-157">Não é possível recuperar dados de inband</span><span class="sxs-lookup"><span data-stu-id="a297c-157">Cannot retrieve inband data</span></span></p></td>
<td><p><span data-ttu-id="a297c-158">Não é possível recuperar dados de inband</span><span class="sxs-lookup"><span data-stu-id="a297c-158">Cannot retrieve inband data</span></span></p>
<p><span data-ttu-id="a297c-159">Se o problema persistir, contate o suporte ao produto</span><span class="sxs-lookup"><span data-stu-id="a297c-159">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a297c-160">20011</span><span class="sxs-lookup"><span data-stu-id="a297c-160">20011</span></span></p></td>
<td><p><span data-ttu-id="a297c-161">Erro</span><span class="sxs-lookup"><span data-stu-id="a297c-161">Error</span></span></p></td>
<td><p><span data-ttu-id="a297c-162">Não é possível assinar a presença</span><span class="sxs-lookup"><span data-stu-id="a297c-162">Cannot subscribe presence</span></span></p></td>
<td><p><span data-ttu-id="a297c-163">Não é possível assinar a presença</span><span class="sxs-lookup"><span data-stu-id="a297c-163">Cannot subscribe presence</span></span></p>
<p><span data-ttu-id="a297c-164">Se o problema persistir, contate o suporte ao produto</span><span class="sxs-lookup"><span data-stu-id="a297c-164">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a297c-165">20012</span><span class="sxs-lookup"><span data-stu-id="a297c-165">20012</span></span></p></td>
<td><p><span data-ttu-id="a297c-166">Erro</span><span class="sxs-lookup"><span data-stu-id="a297c-166">Error</span></span></p></td>
<td><p><span data-ttu-id="a297c-167">Falha ao registrar o ponto de extremidade</span><span class="sxs-lookup"><span data-stu-id="a297c-167">Failed to register endpoint</span></span></p></td>
<td><p><span data-ttu-id="a297c-168">Falha ao registrar o ponto de extremidade</span><span class="sxs-lookup"><span data-stu-id="a297c-168">Failed to register endpoint</span></span></p>
<p><span data-ttu-id="a297c-169">Se o problema persistir, contate o suporte ao produto</span><span class="sxs-lookup"><span data-stu-id="a297c-169">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a297c-170">20013</span><span class="sxs-lookup"><span data-stu-id="a297c-170">20013</span></span></p></td>
<td><p><span data-ttu-id="a297c-171">Erro</span><span class="sxs-lookup"><span data-stu-id="a297c-171">Error</span></span></p></td>
<td><p><span data-ttu-id="a297c-172">IM MCU não está disponível</span><span class="sxs-lookup"><span data-stu-id="a297c-172">IM MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="a297c-173">IM MCU não está disponível</span><span class="sxs-lookup"><span data-stu-id="a297c-173">IM MCU is unavailable</span></span></p>
<p><span data-ttu-id="a297c-174">Veja se o IM MCU está em execução</span><span class="sxs-lookup"><span data-stu-id="a297c-174">See whether IM MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a297c-175">20014</span><span class="sxs-lookup"><span data-stu-id="a297c-175">20014</span></span></p></td>
<td><p><span data-ttu-id="a297c-176">Informativa</span><span class="sxs-lookup"><span data-stu-id="a297c-176">Informational</span></span></p></td>
<td><p><span data-ttu-id="a297c-177">Recuperação de falha na conexão com a MCU de IM</span><span class="sxs-lookup"><span data-stu-id="a297c-177">Recovered from failing to connect to IM MCU</span></span></p></td>
<td><p><span data-ttu-id="a297c-178">N/D</span><span class="sxs-lookup"><span data-stu-id="a297c-178">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a297c-179">20015</span><span class="sxs-lookup"><span data-stu-id="a297c-179">20015</span></span></p></td>
<td><p><span data-ttu-id="a297c-180">Erro</span><span class="sxs-lookup"><span data-stu-id="a297c-180">Error</span></span></p></td>
<td><p><span data-ttu-id="a297c-181">AV MCU não está disponível</span><span class="sxs-lookup"><span data-stu-id="a297c-181">AV MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="a297c-182">AV MCU não está disponível</span><span class="sxs-lookup"><span data-stu-id="a297c-182">AV MCU is unavailable</span></span></p>
<p><span data-ttu-id="a297c-183">Veja se o AV MCU está em execução</span><span class="sxs-lookup"><span data-stu-id="a297c-183">See whether AV MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a297c-184">20016</span><span class="sxs-lookup"><span data-stu-id="a297c-184">20016</span></span></p></td>
<td><p><span data-ttu-id="a297c-185">Informativa</span><span class="sxs-lookup"><span data-stu-id="a297c-185">Informational</span></span></p></td>
<td><p><span data-ttu-id="a297c-186">Recuperação de falha na conexão com o AV MCU</span><span class="sxs-lookup"><span data-stu-id="a297c-186">Recovered from failing to connect to AV MCU</span></span></p></td>
<td><p><span data-ttu-id="a297c-187">N/D</span><span class="sxs-lookup"><span data-stu-id="a297c-187">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a297c-188">20017</span><span class="sxs-lookup"><span data-stu-id="a297c-188">20017</span></span></p></td>
<td><p><span data-ttu-id="a297c-189">Erro</span><span class="sxs-lookup"><span data-stu-id="a297c-189">Error</span></span></p></td>
<td><p><span data-ttu-id="a297c-190">À medida que a MCU não está disponível</span><span class="sxs-lookup"><span data-stu-id="a297c-190">AS MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="a297c-191">À medida que a MCU não está disponível</span><span class="sxs-lookup"><span data-stu-id="a297c-191">AS MCU is unavailable</span></span></p>
<p><span data-ttu-id="a297c-192">Confira se a MCU está sendo executada</span><span class="sxs-lookup"><span data-stu-id="a297c-192">See whether AS MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a297c-193">20018</span><span class="sxs-lookup"><span data-stu-id="a297c-193">20018</span></span></p></td>
<td><p><span data-ttu-id="a297c-194">Informativa</span><span class="sxs-lookup"><span data-stu-id="a297c-194">Informational</span></span></p></td>
<td><p><span data-ttu-id="a297c-195">Recuperação de falha na conexão com a MCU</span><span class="sxs-lookup"><span data-stu-id="a297c-195">Recovered from failing to connect to AS MCU</span></span></p></td>
<td><p><span data-ttu-id="a297c-196">N/D</span><span class="sxs-lookup"><span data-stu-id="a297c-196">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a297c-197">20019</span><span class="sxs-lookup"><span data-stu-id="a297c-197">20019</span></span></p></td>
<td><p><span data-ttu-id="a297c-198">Erro</span><span class="sxs-lookup"><span data-stu-id="a297c-198">Error</span></span></p></td>
<td><p><span data-ttu-id="a297c-199">Data MCU não está disponível</span><span class="sxs-lookup"><span data-stu-id="a297c-199">Data MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="a297c-200">Data MCU não está disponível</span><span class="sxs-lookup"><span data-stu-id="a297c-200">Data MCU is unavailable</span></span></p>
<p><span data-ttu-id="a297c-201">Ver se os dados MCU estão sendo executados</span><span class="sxs-lookup"><span data-stu-id="a297c-201">See whether Data MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a297c-202">20020</span><span class="sxs-lookup"><span data-stu-id="a297c-202">20020</span></span></p></td>
<td><p><span data-ttu-id="a297c-203">Informativa</span><span class="sxs-lookup"><span data-stu-id="a297c-203">Informational</span></span></p></td>
<td><p><span data-ttu-id="a297c-204">Recuperação de falha na conexão com o data MCU</span><span class="sxs-lookup"><span data-stu-id="a297c-204">Recovered from failing to connect to Data MCU</span></span></p></td>
<td><p><span data-ttu-id="a297c-205">N/D</span><span class="sxs-lookup"><span data-stu-id="a297c-205">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a297c-206">20021</span><span class="sxs-lookup"><span data-stu-id="a297c-206">20021</span></span></p></td>
<td><p><span data-ttu-id="a297c-207">Erro</span><span class="sxs-lookup"><span data-stu-id="a297c-207">Error</span></span></p></td>
<td><p><span data-ttu-id="a297c-208">Não é possível ingressar no IM MCU</span><span class="sxs-lookup"><span data-stu-id="a297c-208">Cannot join IM MCU</span></span></p></td>
<td><p><span data-ttu-id="a297c-209">Não é possível ingressar no IM MCU</span><span class="sxs-lookup"><span data-stu-id="a297c-209">Cannot join IM MCU</span></span></p>
<p><span data-ttu-id="a297c-210">Veja se o IM MCU está em execução</span><span class="sxs-lookup"><span data-stu-id="a297c-210">See whether IM MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a297c-211">20022</span><span class="sxs-lookup"><span data-stu-id="a297c-211">20022</span></span></p></td>
<td><p><span data-ttu-id="a297c-212">Erro</span><span class="sxs-lookup"><span data-stu-id="a297c-212">Error</span></span></p></td>
<td><p><span data-ttu-id="a297c-213">Não é possível ingressar no AV MCU</span><span class="sxs-lookup"><span data-stu-id="a297c-213">Cannot join AV MCU</span></span></p></td>
<td><p><span data-ttu-id="a297c-214">Não é possível ingressar no AV MCU</span><span class="sxs-lookup"><span data-stu-id="a297c-214">Cannot join AV MCU</span></span></p>
<p><span data-ttu-id="a297c-215">Veja se o AV MCU está em execução</span><span class="sxs-lookup"><span data-stu-id="a297c-215">See whether AV MCU is running</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a297c-216">20023</span><span class="sxs-lookup"><span data-stu-id="a297c-216">20023</span></span></p></td>
<td><p><span data-ttu-id="a297c-217">Erro</span><span class="sxs-lookup"><span data-stu-id="a297c-217">Error</span></span></p></td>
<td><p><span data-ttu-id="a297c-218">Não é possível entrar como MCU</span><span class="sxs-lookup"><span data-stu-id="a297c-218">Cannot join AS MCU</span></span></p></td>
<td><p><span data-ttu-id="a297c-219">Não é possível entrar como MCU</span><span class="sxs-lookup"><span data-stu-id="a297c-219">Cannot join AS MCU</span></span></p>
<p><span data-ttu-id="a297c-220">Confira se a MCU está sendo executada</span><span class="sxs-lookup"><span data-stu-id="a297c-220">See whether AS MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a297c-221">20024</span><span class="sxs-lookup"><span data-stu-id="a297c-221">20024</span></span></p></td>
<td><p><span data-ttu-id="a297c-222">Erro</span><span class="sxs-lookup"><span data-stu-id="a297c-222">Error</span></span></p></td>
<td><p><span data-ttu-id="a297c-223">Não é possível participar dos dados MCU</span><span class="sxs-lookup"><span data-stu-id="a297c-223">Cannot join Data MCU</span></span></p></td>
<td><p><span data-ttu-id="a297c-224">Não é possível participar dos dados MCU</span><span class="sxs-lookup"><span data-stu-id="a297c-224">Cannot join Data MCU</span></span></p>
<p><span data-ttu-id="a297c-225">Ver se os dados MCU estão sendo executados</span><span class="sxs-lookup"><span data-stu-id="a297c-225">See whether Data MCU is running</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a297c-226">20025</span><span class="sxs-lookup"><span data-stu-id="a297c-226">20025</span></span></p></td>
<td><p><span data-ttu-id="a297c-227">Erro</span><span class="sxs-lookup"><span data-stu-id="a297c-227">Error</span></span></p></td>
<td><p><span data-ttu-id="a297c-228">Não é possível acessar o Active Directory para a foto</span><span class="sxs-lookup"><span data-stu-id="a297c-228">Cannot access active directory for photo</span></span></p></td>
<td><p><span data-ttu-id="a297c-229">A conexão com o Active Directory não está disponível</span><span class="sxs-lookup"><span data-stu-id="a297c-229">Connection to active directory is not available</span></span></p>
<p><span data-ttu-id="a297c-230">Certifique-se de que a conexão com o Active Directory está disponível</span><span class="sxs-lookup"><span data-stu-id="a297c-230">Make sure the connection to active directory is available</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a297c-231">20026</span><span class="sxs-lookup"><span data-stu-id="a297c-231">20026</span></span></p></td>
<td><p><span data-ttu-id="a297c-232">Informativa</span><span class="sxs-lookup"><span data-stu-id="a297c-232">Informational</span></span></p></td>
<td><p><span data-ttu-id="a297c-233">Recuperação de falha ao acessar o Active Directory para foto</span><span class="sxs-lookup"><span data-stu-id="a297c-233">Recovered from failing to access active directory for photo</span></span></p></td>
<td><p><span data-ttu-id="a297c-234">N/D</span><span class="sxs-lookup"><span data-stu-id="a297c-234">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a297c-235">20027</span><span class="sxs-lookup"><span data-stu-id="a297c-235">20027</span></span></p></td>
<td><p><span data-ttu-id="a297c-236">Aviso</span><span class="sxs-lookup"><span data-stu-id="a297c-236">Warning</span></span></p></td>
<td><p><span data-ttu-id="a297c-237">Não é possível desserializar</span><span class="sxs-lookup"><span data-stu-id="a297c-237">Cannot deserialize</span></span></p></td>
<td><p><span data-ttu-id="a297c-238">Não é possível desserializar</span><span class="sxs-lookup"><span data-stu-id="a297c-238">Cannot deserialize</span></span></p>
<p><span data-ttu-id="a297c-239">Se o problema persistir, contate o suporte ao produto</span><span class="sxs-lookup"><span data-stu-id="a297c-239">If the problem persists contact product support</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

