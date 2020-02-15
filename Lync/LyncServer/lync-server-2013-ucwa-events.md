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
ms.openlocfilehash: 4d42dbd967f90b6e2a905b92558c88fe52ef62d7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029162"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="ucwa-events-in-lync-server-2013"></a><span data-ttu-id="a162f-102">Eventos do UCWA no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a162f-102">UCWA events in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a162f-103">_**Última modificação do tópico:** 2013-02-15_</span><span class="sxs-lookup"><span data-stu-id="a162f-103">_**Topic Last Modified:** 2013-02-15_</span></span>

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<span data-ttu-id="a162f-104">O Lync Server 2013 usa a UCWA (Unified Communications Web API) para várias finalidades, desde o acesso ao Microsoft Exchange para pesquisas de contato até a atualização de presença para clientes móveis.</span><span class="sxs-lookup"><span data-stu-id="a162f-104">Lync Server 2013 uses the Unified Communications Web API (UCWA) for a number of purposes, from accessing Microsoft Exchange for contact searches to updating presence for mobile clients.</span></span>

<span data-ttu-id="a162f-105">O UCWA gravará registros de comportamento operacional como tipos de eventos informativos, avisos e erros.</span><span class="sxs-lookup"><span data-stu-id="a162f-105">UCWA will write records of operational behavior as event types Informational, Warning, and Error.</span></span> <span data-ttu-id="a162f-106">A tabela a seguir descreve os eventos que podem ser gravados pelos componentes do UCWA.</span><span class="sxs-lookup"><span data-stu-id="a162f-106">The following table describes the events that can be written by the UCWA components.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a162f-107">ID de evento</span><span class="sxs-lookup"><span data-stu-id="a162f-107">Event ID</span></span></th>
<th><span data-ttu-id="a162f-108">Tipo de Evento</span><span class="sxs-lookup"><span data-stu-id="a162f-108">Event Type</span></span></th>
<th><span data-ttu-id="a162f-109">Resumo</span><span class="sxs-lookup"><span data-stu-id="a162f-109">Summary</span></span></th>
<th><span data-ttu-id="a162f-110">Causa e resolução</span><span class="sxs-lookup"><span data-stu-id="a162f-110">Cause and Resolution</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a162f-111">20001</span><span class="sxs-lookup"><span data-stu-id="a162f-111">20001</span></span></p></td>
<td><p><span data-ttu-id="a162f-112">Informativa</span><span class="sxs-lookup"><span data-stu-id="a162f-112">Informational</span></span></p></td>
<td><p><span data-ttu-id="a162f-113">UCWA inicializado</span><span class="sxs-lookup"><span data-stu-id="a162f-113">UCWA initialized</span></span></p></td>
<td><p><span data-ttu-id="a162f-114">Não disponível</span><span class="sxs-lookup"><span data-stu-id="a162f-114">N/A</span></span></p>
<p><span data-ttu-id="a162f-115">Não disponível</span><span class="sxs-lookup"><span data-stu-id="a162f-115">N/A</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a162f-116">20002</span><span class="sxs-lookup"><span data-stu-id="a162f-116">20002</span></span></p></td>
<td><p><span data-ttu-id="a162f-117">Error</span><span class="sxs-lookup"><span data-stu-id="a162f-117">Error</span></span></p></td>
<td><p><span data-ttu-id="a162f-118">UCWA encontrou uma exceção inesperada durante a inicialização</span><span class="sxs-lookup"><span data-stu-id="a162f-118">UCWA encountered an unexpected exception during initialization</span></span></p></td>
<td><p><span data-ttu-id="a162f-119">Ocorreu um erro inesperado durante a inicialização</span><span class="sxs-lookup"><span data-stu-id="a162f-119">An unexpected error has occurred during initialization</span></span></p>
<p><span data-ttu-id="a162f-120">Examine os detalhes da exceção na entrada do log de eventos associada para determinar a possível causa</span><span class="sxs-lookup"><span data-stu-id="a162f-120">Examine the exception details in the associated event log entry to determine the possible cause</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a162f-121">20003</span><span class="sxs-lookup"><span data-stu-id="a162f-121">20003</span></span></p></td>
<td><p><span data-ttu-id="a162f-122">Error</span><span class="sxs-lookup"><span data-stu-id="a162f-122">Error</span></span></p></td>
<td><p><span data-ttu-id="a162f-123">UCWA encontrou uma exceção não manipulada</span><span class="sxs-lookup"><span data-stu-id="a162f-123">UCWA encountered an unhandled exception</span></span></p></td>
<td><p><span data-ttu-id="a162f-124">Ocorreu uma exceção não manipulada</span><span class="sxs-lookup"><span data-stu-id="a162f-124">An unhandled exception happened</span></span></p>
<p><span data-ttu-id="a162f-125">Reiniciar o servidor.</span><span class="sxs-lookup"><span data-stu-id="a162f-125">Restart the server.</span></span> <span data-ttu-id="a162f-126">Se o problema persistir, contate o suporte ao produto</span><span class="sxs-lookup"><span data-stu-id="a162f-126">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a162f-127">20004</span><span class="sxs-lookup"><span data-stu-id="a162f-127">20004</span></span></p></td>
<td><p><span data-ttu-id="a162f-128">Error</span><span class="sxs-lookup"><span data-stu-id="a162f-128">Error</span></span></p></td>
<td><p><span data-ttu-id="a162f-129">Não é possível acessar o Exchange para foto HD</span><span class="sxs-lookup"><span data-stu-id="a162f-129">Cannot access Exchange for HD photo</span></span></p></td>
<td><p><span data-ttu-id="a162f-130">A conexão com o Exchange não está disponível</span><span class="sxs-lookup"><span data-stu-id="a162f-130">Connection to Exchange is not available</span></span></p>
<p><span data-ttu-id="a162f-131">Certifique-se de que a conexão com o Exchange esteja disponível</span><span class="sxs-lookup"><span data-stu-id="a162f-131">Make sure the connection to Exchange is available</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a162f-132">20005</span><span class="sxs-lookup"><span data-stu-id="a162f-132">20005</span></span></p></td>
<td><p><span data-ttu-id="a162f-133">Informativa</span><span class="sxs-lookup"><span data-stu-id="a162f-133">Informational</span></span></p></td>
<td><p><span data-ttu-id="a162f-134">Recuperação de falha ao acessar o Exchange para foto HD</span><span class="sxs-lookup"><span data-stu-id="a162f-134">Recovered from failing to access Exchange for HD photo</span></span></p></td>
<td><p><span data-ttu-id="a162f-135">Não disponível</span><span class="sxs-lookup"><span data-stu-id="a162f-135">N/A</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a162f-136">20006</span><span class="sxs-lookup"><span data-stu-id="a162f-136">20006</span></span></p></td>
<td><p><span data-ttu-id="a162f-137">Error</span><span class="sxs-lookup"><span data-stu-id="a162f-137">Error</span></span></p></td>
<td><p><span data-ttu-id="a162f-138">Não é possível acessar o Exchange para pesquisa de contato</span><span class="sxs-lookup"><span data-stu-id="a162f-138">Cannot access Exchange for contact search</span></span></p></td>
<td><p><span data-ttu-id="a162f-139">A conexão com o Exchange não está disponível</span><span class="sxs-lookup"><span data-stu-id="a162f-139">Connection to Exchange is not available</span></span></p>
<p><span data-ttu-id="a162f-140">Certifique-se de que a conexão com o Exchange esteja disponível</span><span class="sxs-lookup"><span data-stu-id="a162f-140">Make sure the connection to Exchange is available</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a162f-141">20007</span><span class="sxs-lookup"><span data-stu-id="a162f-141">20007</span></span></p></td>
<td><p><span data-ttu-id="a162f-142">Informativa</span><span class="sxs-lookup"><span data-stu-id="a162f-142">Informational</span></span></p></td>
<td><p><span data-ttu-id="a162f-143">Recuperado da falha ao pesquisar o contato no Exchange</span><span class="sxs-lookup"><span data-stu-id="a162f-143">Recovered from failing to search contact in Exchange</span></span></p></td>
<td><p><span data-ttu-id="a162f-144">Não disponível</span><span class="sxs-lookup"><span data-stu-id="a162f-144">N/A</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a162f-145">20008</span><span class="sxs-lookup"><span data-stu-id="a162f-145">20008</span></span></p></td>
<td><p><span data-ttu-id="a162f-146">Aviso</span><span class="sxs-lookup"><span data-stu-id="a162f-146">Warning</span></span></p></td>
<td><p><span data-ttu-id="a162f-147">Tentativa de inscrever mais do que as assinaturas de presença permitidas por aplicativo</span><span class="sxs-lookup"><span data-stu-id="a162f-147">Attempt to subscribe more than the allowed presence subscriptions per application</span></span></p></td>
<td><p><span data-ttu-id="a162f-148">Tentativa de inscrever mais do que as assinaturas de presença permitidas por aplicativo</span><span class="sxs-lookup"><span data-stu-id="a162f-148">Attempt to subscribe more than the allowed presence subscriptions per application</span></span></p>
<p><span data-ttu-id="a162f-149">Verifique se há assinaturas desnecessárias nos clientes</span><span class="sxs-lookup"><span data-stu-id="a162f-149">Check the clients for unnecessary subscriptions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a162f-150">20009</span><span class="sxs-lookup"><span data-stu-id="a162f-150">20009</span></span></p></td>
<td><p><span data-ttu-id="a162f-151">Aviso</span><span class="sxs-lookup"><span data-stu-id="a162f-151">Warning</span></span></p></td>
<td><p><span data-ttu-id="a162f-152">Tentativa de inscrever mais do que as assinaturas de presença permitidas por lote</span><span class="sxs-lookup"><span data-stu-id="a162f-152">Attempt to subscribe more than the allowed presence subscriptions per batch</span></span></p></td>
<td><p><span data-ttu-id="a162f-153">Tentativa de inscrever mais do que as assinaturas de presença permitidas por lote</span><span class="sxs-lookup"><span data-stu-id="a162f-153">Attempt to subscribe more than the allowed presence subscriptions per batch</span></span></p>
<p><span data-ttu-id="a162f-154">Verifique se há assinaturas desnecessárias nos clientes</span><span class="sxs-lookup"><span data-stu-id="a162f-154">Check the clients for unnecessary subscriptions</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a162f-155">20010</span><span class="sxs-lookup"><span data-stu-id="a162f-155">20010</span></span></p></td>
<td><p><span data-ttu-id="a162f-156">Error</span><span class="sxs-lookup"><span data-stu-id="a162f-156">Error</span></span></p></td>
<td><p><span data-ttu-id="a162f-157">Não é possível recuperar dados de inband</span><span class="sxs-lookup"><span data-stu-id="a162f-157">Cannot retrieve inband data</span></span></p></td>
<td><p><span data-ttu-id="a162f-158">Não é possível recuperar dados de inband</span><span class="sxs-lookup"><span data-stu-id="a162f-158">Cannot retrieve inband data</span></span></p>
<p><span data-ttu-id="a162f-159">Se o problema persistir, contate o suporte ao produto</span><span class="sxs-lookup"><span data-stu-id="a162f-159">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a162f-160">20011</span><span class="sxs-lookup"><span data-stu-id="a162f-160">20011</span></span></p></td>
<td><p><span data-ttu-id="a162f-161">Error</span><span class="sxs-lookup"><span data-stu-id="a162f-161">Error</span></span></p></td>
<td><p><span data-ttu-id="a162f-162">Não é possível assinar a presença</span><span class="sxs-lookup"><span data-stu-id="a162f-162">Cannot subscribe presence</span></span></p></td>
<td><p><span data-ttu-id="a162f-163">Não é possível assinar a presença</span><span class="sxs-lookup"><span data-stu-id="a162f-163">Cannot subscribe presence</span></span></p>
<p><span data-ttu-id="a162f-164">Se o problema persistir, contate o suporte ao produto</span><span class="sxs-lookup"><span data-stu-id="a162f-164">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a162f-165">20012</span><span class="sxs-lookup"><span data-stu-id="a162f-165">20012</span></span></p></td>
<td><p><span data-ttu-id="a162f-166">Error</span><span class="sxs-lookup"><span data-stu-id="a162f-166">Error</span></span></p></td>
<td><p><span data-ttu-id="a162f-167">Falha ao registrar o ponto de extremidade</span><span class="sxs-lookup"><span data-stu-id="a162f-167">Failed to register endpoint</span></span></p></td>
<td><p><span data-ttu-id="a162f-168">Falha ao registrar o ponto de extremidade</span><span class="sxs-lookup"><span data-stu-id="a162f-168">Failed to register endpoint</span></span></p>
<p><span data-ttu-id="a162f-169">Se o problema persistir, contate o suporte ao produto</span><span class="sxs-lookup"><span data-stu-id="a162f-169">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a162f-170">20013</span><span class="sxs-lookup"><span data-stu-id="a162f-170">20013</span></span></p></td>
<td><p><span data-ttu-id="a162f-171">Error</span><span class="sxs-lookup"><span data-stu-id="a162f-171">Error</span></span></p></td>
<td><p><span data-ttu-id="a162f-172">IM MCU não está disponível</span><span class="sxs-lookup"><span data-stu-id="a162f-172">IM MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="a162f-173">IM MCU não está disponível</span><span class="sxs-lookup"><span data-stu-id="a162f-173">IM MCU is unavailable</span></span></p>
<p><span data-ttu-id="a162f-174">Veja se o IM MCU está em execução</span><span class="sxs-lookup"><span data-stu-id="a162f-174">See whether IM MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a162f-175">20014</span><span class="sxs-lookup"><span data-stu-id="a162f-175">20014</span></span></p></td>
<td><p><span data-ttu-id="a162f-176">Informativa</span><span class="sxs-lookup"><span data-stu-id="a162f-176">Informational</span></span></p></td>
<td><p><span data-ttu-id="a162f-177">Recuperação de falha na conexão com a MCU de IM</span><span class="sxs-lookup"><span data-stu-id="a162f-177">Recovered from failing to connect to IM MCU</span></span></p></td>
<td><p><span data-ttu-id="a162f-178">Não disponível</span><span class="sxs-lookup"><span data-stu-id="a162f-178">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a162f-179">20015</span><span class="sxs-lookup"><span data-stu-id="a162f-179">20015</span></span></p></td>
<td><p><span data-ttu-id="a162f-180">Error</span><span class="sxs-lookup"><span data-stu-id="a162f-180">Error</span></span></p></td>
<td><p><span data-ttu-id="a162f-181">AV MCU não está disponível</span><span class="sxs-lookup"><span data-stu-id="a162f-181">AV MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="a162f-182">AV MCU não está disponível</span><span class="sxs-lookup"><span data-stu-id="a162f-182">AV MCU is unavailable</span></span></p>
<p><span data-ttu-id="a162f-183">Veja se o AV MCU está em execução</span><span class="sxs-lookup"><span data-stu-id="a162f-183">See whether AV MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a162f-184">20016</span><span class="sxs-lookup"><span data-stu-id="a162f-184">20016</span></span></p></td>
<td><p><span data-ttu-id="a162f-185">Informativa</span><span class="sxs-lookup"><span data-stu-id="a162f-185">Informational</span></span></p></td>
<td><p><span data-ttu-id="a162f-186">Recuperação de falha na conexão com o AV MCU</span><span class="sxs-lookup"><span data-stu-id="a162f-186">Recovered from failing to connect to AV MCU</span></span></p></td>
<td><p><span data-ttu-id="a162f-187">Não disponível</span><span class="sxs-lookup"><span data-stu-id="a162f-187">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a162f-188">20017</span><span class="sxs-lookup"><span data-stu-id="a162f-188">20017</span></span></p></td>
<td><p><span data-ttu-id="a162f-189">Error</span><span class="sxs-lookup"><span data-stu-id="a162f-189">Error</span></span></p></td>
<td><p><span data-ttu-id="a162f-190">À medida que a MCU não está disponível</span><span class="sxs-lookup"><span data-stu-id="a162f-190">AS MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="a162f-191">À medida que a MCU não está disponível</span><span class="sxs-lookup"><span data-stu-id="a162f-191">AS MCU is unavailable</span></span></p>
<p><span data-ttu-id="a162f-192">Confira se a MCU está sendo executada</span><span class="sxs-lookup"><span data-stu-id="a162f-192">See whether AS MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a162f-193">20018</span><span class="sxs-lookup"><span data-stu-id="a162f-193">20018</span></span></p></td>
<td><p><span data-ttu-id="a162f-194">Informativa</span><span class="sxs-lookup"><span data-stu-id="a162f-194">Informational</span></span></p></td>
<td><p><span data-ttu-id="a162f-195">Recuperação de falha na conexão com a MCU</span><span class="sxs-lookup"><span data-stu-id="a162f-195">Recovered from failing to connect to AS MCU</span></span></p></td>
<td><p><span data-ttu-id="a162f-196">Não disponível</span><span class="sxs-lookup"><span data-stu-id="a162f-196">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a162f-197">20019</span><span class="sxs-lookup"><span data-stu-id="a162f-197">20019</span></span></p></td>
<td><p><span data-ttu-id="a162f-198">Error</span><span class="sxs-lookup"><span data-stu-id="a162f-198">Error</span></span></p></td>
<td><p><span data-ttu-id="a162f-199">Data MCU não está disponível</span><span class="sxs-lookup"><span data-stu-id="a162f-199">Data MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="a162f-200">Data MCU não está disponível</span><span class="sxs-lookup"><span data-stu-id="a162f-200">Data MCU is unavailable</span></span></p>
<p><span data-ttu-id="a162f-201">Ver se os dados MCU estão sendo executados</span><span class="sxs-lookup"><span data-stu-id="a162f-201">See whether Data MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a162f-202">20020</span><span class="sxs-lookup"><span data-stu-id="a162f-202">20020</span></span></p></td>
<td><p><span data-ttu-id="a162f-203">Informativa</span><span class="sxs-lookup"><span data-stu-id="a162f-203">Informational</span></span></p></td>
<td><p><span data-ttu-id="a162f-204">Recuperação de falha na conexão com o data MCU</span><span class="sxs-lookup"><span data-stu-id="a162f-204">Recovered from failing to connect to Data MCU</span></span></p></td>
<td><p><span data-ttu-id="a162f-205">Não disponível</span><span class="sxs-lookup"><span data-stu-id="a162f-205">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a162f-206">20021</span><span class="sxs-lookup"><span data-stu-id="a162f-206">20021</span></span></p></td>
<td><p><span data-ttu-id="a162f-207">Error</span><span class="sxs-lookup"><span data-stu-id="a162f-207">Error</span></span></p></td>
<td><p><span data-ttu-id="a162f-208">Não é possível ingressar no IM MCU</span><span class="sxs-lookup"><span data-stu-id="a162f-208">Cannot join IM MCU</span></span></p></td>
<td><p><span data-ttu-id="a162f-209">Não é possível ingressar no IM MCU</span><span class="sxs-lookup"><span data-stu-id="a162f-209">Cannot join IM MCU</span></span></p>
<p><span data-ttu-id="a162f-210">Veja se o IM MCU está em execução</span><span class="sxs-lookup"><span data-stu-id="a162f-210">See whether IM MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a162f-211">20022</span><span class="sxs-lookup"><span data-stu-id="a162f-211">20022</span></span></p></td>
<td><p><span data-ttu-id="a162f-212">Error</span><span class="sxs-lookup"><span data-stu-id="a162f-212">Error</span></span></p></td>
<td><p><span data-ttu-id="a162f-213">Não é possível ingressar no AV MCU</span><span class="sxs-lookup"><span data-stu-id="a162f-213">Cannot join AV MCU</span></span></p></td>
<td><p><span data-ttu-id="a162f-214">Não é possível ingressar no AV MCU</span><span class="sxs-lookup"><span data-stu-id="a162f-214">Cannot join AV MCU</span></span></p>
<p><span data-ttu-id="a162f-215">Veja se o AV MCU está em execução</span><span class="sxs-lookup"><span data-stu-id="a162f-215">See whether AV MCU is running</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a162f-216">20023</span><span class="sxs-lookup"><span data-stu-id="a162f-216">20023</span></span></p></td>
<td><p><span data-ttu-id="a162f-217">Error</span><span class="sxs-lookup"><span data-stu-id="a162f-217">Error</span></span></p></td>
<td><p><span data-ttu-id="a162f-218">Não é possível entrar como MCU</span><span class="sxs-lookup"><span data-stu-id="a162f-218">Cannot join AS MCU</span></span></p></td>
<td><p><span data-ttu-id="a162f-219">Não é possível entrar como MCU</span><span class="sxs-lookup"><span data-stu-id="a162f-219">Cannot join AS MCU</span></span></p>
<p><span data-ttu-id="a162f-220">Confira se a MCU está sendo executada</span><span class="sxs-lookup"><span data-stu-id="a162f-220">See whether AS MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a162f-221">20024</span><span class="sxs-lookup"><span data-stu-id="a162f-221">20024</span></span></p></td>
<td><p><span data-ttu-id="a162f-222">Error</span><span class="sxs-lookup"><span data-stu-id="a162f-222">Error</span></span></p></td>
<td><p><span data-ttu-id="a162f-223">Não é possível participar dos dados MCU</span><span class="sxs-lookup"><span data-stu-id="a162f-223">Cannot join Data MCU</span></span></p></td>
<td><p><span data-ttu-id="a162f-224">Não é possível participar dos dados MCU</span><span class="sxs-lookup"><span data-stu-id="a162f-224">Cannot join Data MCU</span></span></p>
<p><span data-ttu-id="a162f-225">Ver se os dados MCU estão sendo executados</span><span class="sxs-lookup"><span data-stu-id="a162f-225">See whether Data MCU is running</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a162f-226">20025</span><span class="sxs-lookup"><span data-stu-id="a162f-226">20025</span></span></p></td>
<td><p><span data-ttu-id="a162f-227">Error</span><span class="sxs-lookup"><span data-stu-id="a162f-227">Error</span></span></p></td>
<td><p><span data-ttu-id="a162f-228">Não é possível acessar o Active Directory para a foto</span><span class="sxs-lookup"><span data-stu-id="a162f-228">Cannot access active directory for photo</span></span></p></td>
<td><p><span data-ttu-id="a162f-229">A conexão com o Active Directory não está disponível</span><span class="sxs-lookup"><span data-stu-id="a162f-229">Connection to active directory is not available</span></span></p>
<p><span data-ttu-id="a162f-230">Certifique-se de que a conexão com o Active Directory está disponível</span><span class="sxs-lookup"><span data-stu-id="a162f-230">Make sure the connection to active directory is available</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a162f-231">20026</span><span class="sxs-lookup"><span data-stu-id="a162f-231">20026</span></span></p></td>
<td><p><span data-ttu-id="a162f-232">Informativa</span><span class="sxs-lookup"><span data-stu-id="a162f-232">Informational</span></span></p></td>
<td><p><span data-ttu-id="a162f-233">Recuperação de falha ao acessar o Active Directory para foto</span><span class="sxs-lookup"><span data-stu-id="a162f-233">Recovered from failing to access active directory for photo</span></span></p></td>
<td><p><span data-ttu-id="a162f-234">Não disponível</span><span class="sxs-lookup"><span data-stu-id="a162f-234">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a162f-235">20027</span><span class="sxs-lookup"><span data-stu-id="a162f-235">20027</span></span></p></td>
<td><p><span data-ttu-id="a162f-236">Aviso</span><span class="sxs-lookup"><span data-stu-id="a162f-236">Warning</span></span></p></td>
<td><p><span data-ttu-id="a162f-237">Não é possível desserializar</span><span class="sxs-lookup"><span data-stu-id="a162f-237">Cannot deserialize</span></span></p></td>
<td><p><span data-ttu-id="a162f-238">Não é possível desserializar</span><span class="sxs-lookup"><span data-stu-id="a162f-238">Cannot deserialize</span></span></p>
<p><span data-ttu-id="a162f-239">Se o problema persistir, contate o suporte ao produto</span><span class="sxs-lookup"><span data-stu-id="a162f-239">If the problem persists contact product support</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

