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
ms.openlocfilehash: b5063aca74fe3454569a2b2309be584a4ca11d13
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744851"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="ucwa-events-in-lync-server-2013"></a><span data-ttu-id="e93d5-102">Eventos do UCWA no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e93d5-102">UCWA events in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e93d5-103">_**Tópico da última modificação:** 2013-02-15_</span><span class="sxs-lookup"><span data-stu-id="e93d5-103">_**Topic Last Modified:** 2013-02-15_</span></span>

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<span data-ttu-id="e93d5-104">O Lync Server 2013 usa a API da Web de comunicação unificada (UCWA) para várias finalidades, desde o acesso ao Microsoft Exchange para pesquisas de contato até a atualização de presença para clientes móveis.</span><span class="sxs-lookup"><span data-stu-id="e93d5-104">Lync Server 2013 uses the Unified Communications Web API (UCWA) for a number of purposes, from accessing Microsoft Exchange for contact searches to updating presence for mobile clients.</span></span>

<span data-ttu-id="e93d5-p101">A UCWA gravará registros de comportamento operacional como tipos de evento Informacional, Aviso e Erro. A tabela a seguir descreve tais eventos que podem ser gravados com componentes da UCWA.</span><span class="sxs-lookup"><span data-stu-id="e93d5-p101">UCWA will write records of operational behavior as event types Informational, Warning, and Error. The following table describes the events that can be written by the UCWA components.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e93d5-107">ID do evento</span><span class="sxs-lookup"><span data-stu-id="e93d5-107">Event ID</span></span></th>
<th><span data-ttu-id="e93d5-108">Tipo de evento</span><span class="sxs-lookup"><span data-stu-id="e93d5-108">Event Type</span></span></th>
<th><span data-ttu-id="e93d5-109">Resumo</span><span class="sxs-lookup"><span data-stu-id="e93d5-109">Summary</span></span></th>
<th><span data-ttu-id="e93d5-110">Causa e resolução</span><span class="sxs-lookup"><span data-stu-id="e93d5-110">Cause and Resolution</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e93d5-111">20001</span><span class="sxs-lookup"><span data-stu-id="e93d5-111">20001</span></span></p></td>
<td><p><span data-ttu-id="e93d5-112">Informativo</span><span class="sxs-lookup"><span data-stu-id="e93d5-112">Informational</span></span></p></td>
<td><p><span data-ttu-id="e93d5-113">UCWA inicializado</span><span class="sxs-lookup"><span data-stu-id="e93d5-113">UCWA initialized</span></span></p></td>
<td><p><span data-ttu-id="e93d5-114">N/D</span><span class="sxs-lookup"><span data-stu-id="e93d5-114">N/A</span></span></p>
<p><span data-ttu-id="e93d5-115">N/D</span><span class="sxs-lookup"><span data-stu-id="e93d5-115">N/A</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e93d5-116">20002</span><span class="sxs-lookup"><span data-stu-id="e93d5-116">20002</span></span></p></td>
<td><p><span data-ttu-id="e93d5-117">Erro</span><span class="sxs-lookup"><span data-stu-id="e93d5-117">Error</span></span></p></td>
<td><p><span data-ttu-id="e93d5-118">A UCWA encontrou uma exceção inesperada durante a inicialização</span><span class="sxs-lookup"><span data-stu-id="e93d5-118">UCWA encountered an unexpected exception during initialization</span></span></p></td>
<td><p><span data-ttu-id="e93d5-119">Ocorreu um erro inesperado durante a inicialização</span><span class="sxs-lookup"><span data-stu-id="e93d5-119">An unexpected error has occurred during initialization</span></span></p>
<p><span data-ttu-id="e93d5-120">Examine os detalhes da exceção na entrada de log do evento associado para determinar a possível causa</span><span class="sxs-lookup"><span data-stu-id="e93d5-120">Examine the exception details in the associated event log entry to determine the possible cause</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e93d5-121">20003</span><span class="sxs-lookup"><span data-stu-id="e93d5-121">20003</span></span></p></td>
<td><p><span data-ttu-id="e93d5-122">Erro</span><span class="sxs-lookup"><span data-stu-id="e93d5-122">Error</span></span></p></td>
<td><p><span data-ttu-id="e93d5-123">A UCWA encontrou uma exceção não manipulada</span><span class="sxs-lookup"><span data-stu-id="e93d5-123">UCWA encountered an unhandled exception</span></span></p></td>
<td><p><span data-ttu-id="e93d5-124">Ocorreu uma exceção não manipulada</span><span class="sxs-lookup"><span data-stu-id="e93d5-124">An unhandled exception happened</span></span></p>
<p><span data-ttu-id="e93d5-p102">Reinicie o servidor. Se o problema persistir, entre em contato com o suporte do produto</span><span class="sxs-lookup"><span data-stu-id="e93d5-p102">Restart the server. If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e93d5-127">20004</span><span class="sxs-lookup"><span data-stu-id="e93d5-127">20004</span></span></p></td>
<td><p><span data-ttu-id="e93d5-128">Erro</span><span class="sxs-lookup"><span data-stu-id="e93d5-128">Error</span></span></p></td>
<td><p><span data-ttu-id="e93d5-129">Não é possível acessar o Exchange para foto HD</span><span class="sxs-lookup"><span data-stu-id="e93d5-129">Cannot access Exchange for HD photo</span></span></p></td>
<td><p><span data-ttu-id="e93d5-130">A conexão com o Exchange não está disponível</span><span class="sxs-lookup"><span data-stu-id="e93d5-130">Connection to Exchange is not available</span></span></p>
<p><span data-ttu-id="e93d5-131">Certifique-se de que a conexão com o Exchange está disponível</span><span class="sxs-lookup"><span data-stu-id="e93d5-131">Make sure the connection to Exchange is available</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e93d5-132">20005</span><span class="sxs-lookup"><span data-stu-id="e93d5-132">20005</span></span></p></td>
<td><p><span data-ttu-id="e93d5-133">Informativo</span><span class="sxs-lookup"><span data-stu-id="e93d5-133">Informational</span></span></p></td>
<td><p><span data-ttu-id="e93d5-134">Recuperação de uma falha ao acessar o Exchange para foto HD</span><span class="sxs-lookup"><span data-stu-id="e93d5-134">Recovered from failing to access Exchange for HD photo</span></span></p></td>
<td><p><span data-ttu-id="e93d5-135">Não disponível</span><span class="sxs-lookup"><span data-stu-id="e93d5-135">N/A</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e93d5-136">20006</span><span class="sxs-lookup"><span data-stu-id="e93d5-136">20006</span></span></p></td>
<td><p><span data-ttu-id="e93d5-137">Erro</span><span class="sxs-lookup"><span data-stu-id="e93d5-137">Error</span></span></p></td>
<td><p><span data-ttu-id="e93d5-138">Não é possível acessar o Exchange para pesquisa de contato</span><span class="sxs-lookup"><span data-stu-id="e93d5-138">Cannot access Exchange for contact search</span></span></p></td>
<td><p><span data-ttu-id="e93d5-139">A conexão com o Exchange não está disponível</span><span class="sxs-lookup"><span data-stu-id="e93d5-139">Connection to Exchange is not available</span></span></p>
<p><span data-ttu-id="e93d5-140">Certifique-se de que a conexão com o Exchange está disponível</span><span class="sxs-lookup"><span data-stu-id="e93d5-140">Make sure the connection to Exchange is available</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e93d5-141">20007</span><span class="sxs-lookup"><span data-stu-id="e93d5-141">20007</span></span></p></td>
<td><p><span data-ttu-id="e93d5-142">Informativo</span><span class="sxs-lookup"><span data-stu-id="e93d5-142">Informational</span></span></p></td>
<td><p><span data-ttu-id="e93d5-143">Recuperação de uma falha em pesquisar contato no Exchange</span><span class="sxs-lookup"><span data-stu-id="e93d5-143">Recovered from failing to search contact in Exchange</span></span></p></td>
<td><p><span data-ttu-id="e93d5-144">Não disponível</span><span class="sxs-lookup"><span data-stu-id="e93d5-144">N/A</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e93d5-145">20008</span><span class="sxs-lookup"><span data-stu-id="e93d5-145">20008</span></span></p></td>
<td><p><span data-ttu-id="e93d5-146">Aviso</span><span class="sxs-lookup"><span data-stu-id="e93d5-146">Warning</span></span></p></td>
<td><p><span data-ttu-id="e93d5-147">Tente assinar mais de uma assinatura de presença permitida por aplicativo</span><span class="sxs-lookup"><span data-stu-id="e93d5-147">Attempt to subscribe more than the allowed presence subscriptions per application</span></span></p></td>
<td><p><span data-ttu-id="e93d5-148">Tente assinar mais de uma assinatura de presença permitida por aplicativo</span><span class="sxs-lookup"><span data-stu-id="e93d5-148">Attempt to subscribe more than the allowed presence subscriptions per application</span></span></p>
<p><span data-ttu-id="e93d5-149">Verifique se os clientes possuem assinaturas desnecessárias</span><span class="sxs-lookup"><span data-stu-id="e93d5-149">Check the clients for unnecessary subscriptions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e93d5-150">20009</span><span class="sxs-lookup"><span data-stu-id="e93d5-150">20009</span></span></p></td>
<td><p><span data-ttu-id="e93d5-151">Aviso</span><span class="sxs-lookup"><span data-stu-id="e93d5-151">Warning</span></span></p></td>
<td><p><span data-ttu-id="e93d5-152">Tente assinar mais de uma assinatura de presença permitida por lote</span><span class="sxs-lookup"><span data-stu-id="e93d5-152">Attempt to subscribe more than the allowed presence subscriptions per batch</span></span></p></td>
<td><p><span data-ttu-id="e93d5-153">Tente assinar mais de uma assinatura de presença permitida por lote</span><span class="sxs-lookup"><span data-stu-id="e93d5-153">Attempt to subscribe more than the allowed presence subscriptions per batch</span></span></p>
<p><span data-ttu-id="e93d5-154">Verifique se os clientes possuem assinaturas desnecessárias</span><span class="sxs-lookup"><span data-stu-id="e93d5-154">Check the clients for unnecessary subscriptions</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e93d5-155">20010</span><span class="sxs-lookup"><span data-stu-id="e93d5-155">20010</span></span></p></td>
<td><p><span data-ttu-id="e93d5-156">Erro</span><span class="sxs-lookup"><span data-stu-id="e93d5-156">Error</span></span></p></td>
<td><p><span data-ttu-id="e93d5-157">Não é possível recuperar os dados inband</span><span class="sxs-lookup"><span data-stu-id="e93d5-157">Cannot retrieve inband data</span></span></p></td>
<td><p><span data-ttu-id="e93d5-158">Não é possível recuperar os dados inband</span><span class="sxs-lookup"><span data-stu-id="e93d5-158">Cannot retrieve inband data</span></span></p>
<p><span data-ttu-id="e93d5-159">Se o problema persistir entre em contato com o suporte do produto</span><span class="sxs-lookup"><span data-stu-id="e93d5-159">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e93d5-160">20011</span><span class="sxs-lookup"><span data-stu-id="e93d5-160">20011</span></span></p></td>
<td><p><span data-ttu-id="e93d5-161">Erro</span><span class="sxs-lookup"><span data-stu-id="e93d5-161">Error</span></span></p></td>
<td><p><span data-ttu-id="e93d5-162">Não é possível assinar a presença</span><span class="sxs-lookup"><span data-stu-id="e93d5-162">Cannot subscribe presence</span></span></p></td>
<td><p><span data-ttu-id="e93d5-163">Não é possível assinar a presença</span><span class="sxs-lookup"><span data-stu-id="e93d5-163">Cannot subscribe presence</span></span></p>
<p><span data-ttu-id="e93d5-164">Se o problema persistir entre em contato com o suporte do produto</span><span class="sxs-lookup"><span data-stu-id="e93d5-164">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e93d5-165">20012</span><span class="sxs-lookup"><span data-stu-id="e93d5-165">20012</span></span></p></td>
<td><p><span data-ttu-id="e93d5-166">Erro</span><span class="sxs-lookup"><span data-stu-id="e93d5-166">Error</span></span></p></td>
<td><p><span data-ttu-id="e93d5-167">Falha ao registrar o ponto de extremidade</span><span class="sxs-lookup"><span data-stu-id="e93d5-167">Failed to register endpoint</span></span></p></td>
<td><p><span data-ttu-id="e93d5-168">Falha ao registrar o ponto de extremidade</span><span class="sxs-lookup"><span data-stu-id="e93d5-168">Failed to register endpoint</span></span></p>
<p><span data-ttu-id="e93d5-169">Se o problema persistir entre em contato com o suporte do produto</span><span class="sxs-lookup"><span data-stu-id="e93d5-169">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e93d5-170">20013</span><span class="sxs-lookup"><span data-stu-id="e93d5-170">20013</span></span></p></td>
<td><p><span data-ttu-id="e93d5-171">Erro</span><span class="sxs-lookup"><span data-stu-id="e93d5-171">Error</span></span></p></td>
<td><p><span data-ttu-id="e93d5-172">A MCU de IM não está disponível</span><span class="sxs-lookup"><span data-stu-id="e93d5-172">IM MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="e93d5-173">A MCU de IM não está disponível</span><span class="sxs-lookup"><span data-stu-id="e93d5-173">IM MCU is unavailable</span></span></p>
<p><span data-ttu-id="e93d5-174">Consulte se a MCU de IM está sendo executada</span><span class="sxs-lookup"><span data-stu-id="e93d5-174">See whether IM MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e93d5-175">20014</span><span class="sxs-lookup"><span data-stu-id="e93d5-175">20014</span></span></p></td>
<td><p><span data-ttu-id="e93d5-176">Informativo</span><span class="sxs-lookup"><span data-stu-id="e93d5-176">Informational</span></span></p></td>
<td><p><span data-ttu-id="e93d5-177">Recuperação de uma falha ao conectar ao MCU de IM</span><span class="sxs-lookup"><span data-stu-id="e93d5-177">Recovered from failing to connect to IM MCU</span></span></p></td>
<td><p><span data-ttu-id="e93d5-178">Não disponível</span><span class="sxs-lookup"><span data-stu-id="e93d5-178">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e93d5-179">20015</span><span class="sxs-lookup"><span data-stu-id="e93d5-179">20015</span></span></p></td>
<td><p><span data-ttu-id="e93d5-180">Erro</span><span class="sxs-lookup"><span data-stu-id="e93d5-180">Error</span></span></p></td>
<td><p><span data-ttu-id="e93d5-181">A MCU de AV não está disponível</span><span class="sxs-lookup"><span data-stu-id="e93d5-181">AV MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="e93d5-182">A MCU de AV não está disponível</span><span class="sxs-lookup"><span data-stu-id="e93d5-182">AV MCU is unavailable</span></span></p>
<p><span data-ttu-id="e93d5-183">Consulte se a MCU de AV está sendo executada</span><span class="sxs-lookup"><span data-stu-id="e93d5-183">See whether AV MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e93d5-184">20016</span><span class="sxs-lookup"><span data-stu-id="e93d5-184">20016</span></span></p></td>
<td><p><span data-ttu-id="e93d5-185">Informativo</span><span class="sxs-lookup"><span data-stu-id="e93d5-185">Informational</span></span></p></td>
<td><p><span data-ttu-id="e93d5-186">Recuperação de uma falha ao conectar ao MCU de AV</span><span class="sxs-lookup"><span data-stu-id="e93d5-186">Recovered from failing to connect to AV MCU</span></span></p></td>
<td><p><span data-ttu-id="e93d5-187">Não disponível</span><span class="sxs-lookup"><span data-stu-id="e93d5-187">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e93d5-188">20017</span><span class="sxs-lookup"><span data-stu-id="e93d5-188">20017</span></span></p></td>
<td><p><span data-ttu-id="e93d5-189">Erro</span><span class="sxs-lookup"><span data-stu-id="e93d5-189">Error</span></span></p></td>
<td><p><span data-ttu-id="e93d5-190">A MCU de AS não está disponível</span><span class="sxs-lookup"><span data-stu-id="e93d5-190">AS MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="e93d5-191">A MCU de AS não está disponível</span><span class="sxs-lookup"><span data-stu-id="e93d5-191">AS MCU is unavailable</span></span></p>
<p><span data-ttu-id="e93d5-192">Consulte se a MCU de AS está sendo executada</span><span class="sxs-lookup"><span data-stu-id="e93d5-192">See whether AS MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e93d5-193">20018</span><span class="sxs-lookup"><span data-stu-id="e93d5-193">20018</span></span></p></td>
<td><p><span data-ttu-id="e93d5-194">Informativo</span><span class="sxs-lookup"><span data-stu-id="e93d5-194">Informational</span></span></p></td>
<td><p><span data-ttu-id="e93d5-195">Recuperação de uma falha ao conectar ao MCU de AS</span><span class="sxs-lookup"><span data-stu-id="e93d5-195">Recovered from failing to connect to AS MCU</span></span></p></td>
<td><p><span data-ttu-id="e93d5-196">N/D</span><span class="sxs-lookup"><span data-stu-id="e93d5-196">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e93d5-197">20019</span><span class="sxs-lookup"><span data-stu-id="e93d5-197">20019</span></span></p></td>
<td><p><span data-ttu-id="e93d5-198">Erro</span><span class="sxs-lookup"><span data-stu-id="e93d5-198">Error</span></span></p></td>
<td><p><span data-ttu-id="e93d5-199">A MCU de Dados não está disponível</span><span class="sxs-lookup"><span data-stu-id="e93d5-199">Data MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="e93d5-200">A MCU de Dados não está disponível</span><span class="sxs-lookup"><span data-stu-id="e93d5-200">Data MCU is unavailable</span></span></p>
<p><span data-ttu-id="e93d5-201">Consulte se a MCU de Dados está sendo executada</span><span class="sxs-lookup"><span data-stu-id="e93d5-201">See whether Data MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e93d5-202">20020</span><span class="sxs-lookup"><span data-stu-id="e93d5-202">20020</span></span></p></td>
<td><p><span data-ttu-id="e93d5-203">Informativo</span><span class="sxs-lookup"><span data-stu-id="e93d5-203">Informational</span></span></p></td>
<td><p><span data-ttu-id="e93d5-204">Recuperação de uma falha ao conectar ao MCU de dados</span><span class="sxs-lookup"><span data-stu-id="e93d5-204">Recovered from failing to connect to Data MCU</span></span></p></td>
<td><p><span data-ttu-id="e93d5-205">Não disponível</span><span class="sxs-lookup"><span data-stu-id="e93d5-205">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e93d5-206">20021</span><span class="sxs-lookup"><span data-stu-id="e93d5-206">20021</span></span></p></td>
<td><p><span data-ttu-id="e93d5-207">Erro</span><span class="sxs-lookup"><span data-stu-id="e93d5-207">Error</span></span></p></td>
<td><p><span data-ttu-id="e93d5-208">Não é possível participar da MCU de IM</span><span class="sxs-lookup"><span data-stu-id="e93d5-208">Cannot join IM MCU</span></span></p></td>
<td><p><span data-ttu-id="e93d5-209">Não é possível participar da MCU de IM</span><span class="sxs-lookup"><span data-stu-id="e93d5-209">Cannot join IM MCU</span></span></p>
<p><span data-ttu-id="e93d5-210">Consulte se a MCU de IM está sendo executada</span><span class="sxs-lookup"><span data-stu-id="e93d5-210">See whether IM MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e93d5-211">20022</span><span class="sxs-lookup"><span data-stu-id="e93d5-211">20022</span></span></p></td>
<td><p><span data-ttu-id="e93d5-212">Erro</span><span class="sxs-lookup"><span data-stu-id="e93d5-212">Error</span></span></p></td>
<td><p><span data-ttu-id="e93d5-213">Não é possível participar da MCU de AV</span><span class="sxs-lookup"><span data-stu-id="e93d5-213">Cannot join AV MCU</span></span></p></td>
<td><p><span data-ttu-id="e93d5-214">Não é possível participar da MCU de AV</span><span class="sxs-lookup"><span data-stu-id="e93d5-214">Cannot join AV MCU</span></span></p>
<p><span data-ttu-id="e93d5-215">Consulte se a MCU de AV está sendo executada</span><span class="sxs-lookup"><span data-stu-id="e93d5-215">See whether AV MCU is running</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e93d5-216">20023</span><span class="sxs-lookup"><span data-stu-id="e93d5-216">20023</span></span></p></td>
<td><p><span data-ttu-id="e93d5-217">Erro</span><span class="sxs-lookup"><span data-stu-id="e93d5-217">Error</span></span></p></td>
<td><p><span data-ttu-id="e93d5-218">Não é possível participar da MCU de AS</span><span class="sxs-lookup"><span data-stu-id="e93d5-218">Cannot join AS MCU</span></span></p></td>
<td><p><span data-ttu-id="e93d5-219">Não é possível participar da MCU de AS</span><span class="sxs-lookup"><span data-stu-id="e93d5-219">Cannot join AS MCU</span></span></p>
<p><span data-ttu-id="e93d5-220">Consulte se a MCU de AS está sendo executada</span><span class="sxs-lookup"><span data-stu-id="e93d5-220">See whether AS MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e93d5-221">20024</span><span class="sxs-lookup"><span data-stu-id="e93d5-221">20024</span></span></p></td>
<td><p><span data-ttu-id="e93d5-222">Erro</span><span class="sxs-lookup"><span data-stu-id="e93d5-222">Error</span></span></p></td>
<td><p><span data-ttu-id="e93d5-223">Não é possível participar da MCU de Dados</span><span class="sxs-lookup"><span data-stu-id="e93d5-223">Cannot join Data MCU</span></span></p></td>
<td><p><span data-ttu-id="e93d5-224">Não é possível participar da MCU de Dados</span><span class="sxs-lookup"><span data-stu-id="e93d5-224">Cannot join Data MCU</span></span></p>
<p><span data-ttu-id="e93d5-225">Consulte se a MCU de Dados está sendo executada</span><span class="sxs-lookup"><span data-stu-id="e93d5-225">See whether Data MCU is running</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e93d5-226">20025</span><span class="sxs-lookup"><span data-stu-id="e93d5-226">20025</span></span></p></td>
<td><p><span data-ttu-id="e93d5-227">Erro</span><span class="sxs-lookup"><span data-stu-id="e93d5-227">Error</span></span></p></td>
<td><p><span data-ttu-id="e93d5-228">Não é possível acessar o diretório ativo para foto</span><span class="sxs-lookup"><span data-stu-id="e93d5-228">Cannot access active directory for photo</span></span></p></td>
<td><p><span data-ttu-id="e93d5-229">A conexão com o diretório ativo não está disponível</span><span class="sxs-lookup"><span data-stu-id="e93d5-229">Connection to active directory is not available</span></span></p>
<p><span data-ttu-id="e93d5-230">Certifique-se de que a conexão com o diretório ativo está disponível</span><span class="sxs-lookup"><span data-stu-id="e93d5-230">Make sure the connection to active directory is available</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e93d5-231">20026</span><span class="sxs-lookup"><span data-stu-id="e93d5-231">20026</span></span></p></td>
<td><p><span data-ttu-id="e93d5-232">Informativo</span><span class="sxs-lookup"><span data-stu-id="e93d5-232">Informational</span></span></p></td>
<td><p><span data-ttu-id="e93d5-233">Recuperação de falha ao acessar o diretório ativo para foto</span><span class="sxs-lookup"><span data-stu-id="e93d5-233">Recovered from failing to access active directory for photo</span></span></p></td>
<td><p><span data-ttu-id="e93d5-234">N/D</span><span class="sxs-lookup"><span data-stu-id="e93d5-234">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e93d5-235">20027</span><span class="sxs-lookup"><span data-stu-id="e93d5-235">20027</span></span></p></td>
<td><p><span data-ttu-id="e93d5-236">Aviso</span><span class="sxs-lookup"><span data-stu-id="e93d5-236">Warning</span></span></p></td>
<td><p><span data-ttu-id="e93d5-237">Não é possível desserializar</span><span class="sxs-lookup"><span data-stu-id="e93d5-237">Cannot deserialize</span></span></p></td>
<td><p><span data-ttu-id="e93d5-238">Não é possível desserializar</span><span class="sxs-lookup"><span data-stu-id="e93d5-238">Cannot deserialize</span></span></p>
<p><span data-ttu-id="e93d5-239">Se o problema persistir entre em contato com o suporte do produto</span><span class="sxs-lookup"><span data-stu-id="e93d5-239">If the problem persists contact product support</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

