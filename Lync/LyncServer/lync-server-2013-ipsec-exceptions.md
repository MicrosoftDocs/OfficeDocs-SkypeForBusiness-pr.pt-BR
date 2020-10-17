---
title: Exceções IPsec do Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IPsec exceptions
ms:assetid: 241f1eca-6f2f-44de-90b1-2cb659cbe27c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425719(v=OCS.15)
ms:contentKeyID: 48183627
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4ee06e4b7f3cabc606a612cd0f332aed47b46823
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514148"
---
# <a name="ipsec-exceptions-in-lync-server-2013"></a><span data-ttu-id="67f29-102">Exceções de IPsec no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="67f29-102">IPsec exceptions in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="67f29-103">_**Última modificação do tópico:** 2012-06-27_</span><span class="sxs-lookup"><span data-stu-id="67f29-103">_**Topic Last Modified:** 2012-06-27_</span></span>

<span data-ttu-id="67f29-p101">Nas redes corporativas em que o protocolo IPsec (consulte a RFC 4301-4309 da IETF) foi implantado, o protocolo IPsec deverá ser desabilitado no intervalo de portas usado para a entrega de áudio, vídeo e vídeo panorama. A recomendação vem da necessidade de evitar qualquer atraso na alocação das portas de mídia por causa da negociação IPsec.</span><span class="sxs-lookup"><span data-stu-id="67f29-p101">For enterprise networks where Internet Protocol security (IPsec) (see IETF RFC 4301-4309) has been deployed, IPsec must be disabled over the range of ports used for the delivery of audio, video, and panorama video. The recommendation is motivated by the need to avoid any delay in the allocation of media ports due to IPsec negotiation.</span></span>

<span data-ttu-id="67f29-106">A tabela a seguir explica as configurações de exceções recomendadas do IPsec.</span><span class="sxs-lookup"><span data-stu-id="67f29-106">The following table explains the recommended IPsec exception settings.</span></span>

### <a name="recommended-ipsec-exceptions"></a><span data-ttu-id="67f29-107">Exceções recomendadas do IPsec</span><span class="sxs-lookup"><span data-stu-id="67f29-107">Recommended IPsec Exceptions</span></span>

<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="67f29-108">Nome da regra</span><span class="sxs-lookup"><span data-stu-id="67f29-108">Rule name</span></span></th>
<th><span data-ttu-id="67f29-109">IP de origem</span><span class="sxs-lookup"><span data-stu-id="67f29-109">Source IP</span></span></th>
<th><span data-ttu-id="67f29-110">IP de destino</span><span class="sxs-lookup"><span data-stu-id="67f29-110">Destination IP</span></span></th>
<th><span data-ttu-id="67f29-111">Protocolo</span><span class="sxs-lookup"><span data-stu-id="67f29-111">Protocol</span></span></th>
<th><span data-ttu-id="67f29-112">Porta de origem</span><span class="sxs-lookup"><span data-stu-id="67f29-112">Source port</span></span></th>
<th><span data-ttu-id="67f29-113">Porta de destino</span><span class="sxs-lookup"><span data-stu-id="67f29-113">Destination port</span></span></th>
<th><span data-ttu-id="67f29-114">Requisito de autenticação</span><span class="sxs-lookup"><span data-stu-id="67f29-114">Authentication Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="67f29-115">Entrada interna do Servidor de Borda A/V</span><span class="sxs-lookup"><span data-stu-id="67f29-115">A/V Edge Server Internal Inbound</span></span></p></td>
<td><p><span data-ttu-id="67f29-116">Qualquer</span><span class="sxs-lookup"><span data-stu-id="67f29-116">Any</span></span></p></td>
<td><p><span data-ttu-id="67f29-117">Interno do Servidor de Borda A/V</span><span class="sxs-lookup"><span data-stu-id="67f29-117">A/V Edge Server Internal</span></span></p></td>
<td><p><span data-ttu-id="67f29-118">UDP e TCP</span><span class="sxs-lookup"><span data-stu-id="67f29-118">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="67f29-119">Qualquer</span><span class="sxs-lookup"><span data-stu-id="67f29-119">Any</span></span></p></td>
<td><p><span data-ttu-id="67f29-120">Qualquer</span><span class="sxs-lookup"><span data-stu-id="67f29-120">Any</span></span></p></td>
<td><p><span data-ttu-id="67f29-121">Não autenticar</span><span class="sxs-lookup"><span data-stu-id="67f29-121">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67f29-122">Entrada externa do Servidor de Borda A/V</span><span class="sxs-lookup"><span data-stu-id="67f29-122">A/V Edge Server External Inbound</span></span></p></td>
<td><p><span data-ttu-id="67f29-123">Qualquer</span><span class="sxs-lookup"><span data-stu-id="67f29-123">Any</span></span></p></td>
<td><p><span data-ttu-id="67f29-124">Externo do Servidor de Borda A/V</span><span class="sxs-lookup"><span data-stu-id="67f29-124">A/V Edge Server External</span></span></p></td>
<td><p><span data-ttu-id="67f29-125">UDP e TCP</span><span class="sxs-lookup"><span data-stu-id="67f29-125">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="67f29-126">Qualquer</span><span class="sxs-lookup"><span data-stu-id="67f29-126">Any</span></span></p></td>
<td><p><span data-ttu-id="67f29-127">Qualquer</span><span class="sxs-lookup"><span data-stu-id="67f29-127">Any</span></span></p></td>
<td><p><span data-ttu-id="67f29-128">Não autenticar</span><span class="sxs-lookup"><span data-stu-id="67f29-128">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67f29-129">Saída interna do Servidor de Borda A/V</span><span class="sxs-lookup"><span data-stu-id="67f29-129">A/V Edge Server Internal Outbound</span></span></p></td>
<td><p><span data-ttu-id="67f29-130">Interno do Servidor de Borda A/V</span><span class="sxs-lookup"><span data-stu-id="67f29-130">A/V Edge Server Internal</span></span></p></td>
<td><p><span data-ttu-id="67f29-131">Qualquer</span><span class="sxs-lookup"><span data-stu-id="67f29-131">Any</span></span></p></td>
<td><p><span data-ttu-id="67f29-132">&amp;TCP UDP</span><span class="sxs-lookup"><span data-stu-id="67f29-132">UDP &amp; TCP</span></span></p></td>
<td><p><span data-ttu-id="67f29-133">Qualquer</span><span class="sxs-lookup"><span data-stu-id="67f29-133">Any</span></span></p></td>
<td><p><span data-ttu-id="67f29-134">Qualquer</span><span class="sxs-lookup"><span data-stu-id="67f29-134">Any</span></span></p></td>
<td><p><span data-ttu-id="67f29-135">Não autenticar</span><span class="sxs-lookup"><span data-stu-id="67f29-135">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67f29-136">Saída externa do Servidor de Borda A/V</span><span class="sxs-lookup"><span data-stu-id="67f29-136">A/V Edge Server External Outbound</span></span></p></td>
<td><p><span data-ttu-id="67f29-137">Externo do Servidor de Borda A/V</span><span class="sxs-lookup"><span data-stu-id="67f29-137">A/V Edge Server External</span></span></p></td>
<td><p><span data-ttu-id="67f29-138">Qualquer</span><span class="sxs-lookup"><span data-stu-id="67f29-138">Any</span></span></p></td>
<td><p><span data-ttu-id="67f29-139">UDP e TCP</span><span class="sxs-lookup"><span data-stu-id="67f29-139">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="67f29-140">Qualquer</span><span class="sxs-lookup"><span data-stu-id="67f29-140">Any</span></span></p></td>
<td><p><span data-ttu-id="67f29-141">Qualquer</span><span class="sxs-lookup"><span data-stu-id="67f29-141">Any</span></span></p></td>
<td><p><span data-ttu-id="67f29-142">Não autenticar</span><span class="sxs-lookup"><span data-stu-id="67f29-142">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67f29-143">Entrada do Servidor de Mediação</span><span class="sxs-lookup"><span data-stu-id="67f29-143">Mediation Server Inbound</span></span></p></td>
<td><p><span data-ttu-id="67f29-144">Qualquer</span><span class="sxs-lookup"><span data-stu-id="67f29-144">Any</span></span></p></td>
<td><p><span data-ttu-id="67f29-145">Mediação</span><span class="sxs-lookup"><span data-stu-id="67f29-145">Mediation</span></span></p>
<p><span data-ttu-id="67f29-146">Servidor (es)</span><span class="sxs-lookup"><span data-stu-id="67f29-146">Server(s)</span></span></p></td>
<td><p><span data-ttu-id="67f29-147">UDP e TCP</span><span class="sxs-lookup"><span data-stu-id="67f29-147">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="67f29-148">Qualquer</span><span class="sxs-lookup"><span data-stu-id="67f29-148">Any</span></span></p></td>
<td><p><span data-ttu-id="67f29-149">Qualquer</span><span class="sxs-lookup"><span data-stu-id="67f29-149">Any</span></span></p></td>
<td><p><span data-ttu-id="67f29-150">Não autenticar</span><span class="sxs-lookup"><span data-stu-id="67f29-150">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67f29-151">Saída do Servidor de Mediação</span><span class="sxs-lookup"><span data-stu-id="67f29-151">Mediation Server Outbound</span></span></p></td>
<td><p><span data-ttu-id="67f29-152">Mediação</span><span class="sxs-lookup"><span data-stu-id="67f29-152">Mediation</span></span></p>
<p><span data-ttu-id="67f29-153">Servidor (es)</span><span class="sxs-lookup"><span data-stu-id="67f29-153">Server(s)</span></span></p></td>
<td><p><span data-ttu-id="67f29-154">Qualquer</span><span class="sxs-lookup"><span data-stu-id="67f29-154">Any</span></span></p></td>
<td><p><span data-ttu-id="67f29-155">UDP e TCP</span><span class="sxs-lookup"><span data-stu-id="67f29-155">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="67f29-156">Qualquer</span><span class="sxs-lookup"><span data-stu-id="67f29-156">Any</span></span></p></td>
<td><p><span data-ttu-id="67f29-157">Qualquer</span><span class="sxs-lookup"><span data-stu-id="67f29-157">Any</span></span></p></td>
<td><p><span data-ttu-id="67f29-158">Não autenticar</span><span class="sxs-lookup"><span data-stu-id="67f29-158">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67f29-159">Entrada do Atendedor de Conferência</span><span class="sxs-lookup"><span data-stu-id="67f29-159">Conferencing Attendant Inbound</span></span></p></td>
<td><p><span data-ttu-id="67f29-160">Qualquer</span><span class="sxs-lookup"><span data-stu-id="67f29-160">Any</span></span></p></td>
<td><p><span data-ttu-id="67f29-161">Servidor Front End executando o Atendedor de Conferência</span><span class="sxs-lookup"><span data-stu-id="67f29-161">Front End Server running Conferencing Attendant</span></span></p></td>
<td><p><span data-ttu-id="67f29-162">UDP e TCP</span><span class="sxs-lookup"><span data-stu-id="67f29-162">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="67f29-163">Qualquer</span><span class="sxs-lookup"><span data-stu-id="67f29-163">Any</span></span></p></td>
<td><p><span data-ttu-id="67f29-164">Qualquer</span><span class="sxs-lookup"><span data-stu-id="67f29-164">Any</span></span></p></td>
<td><p><span data-ttu-id="67f29-165">Não autenticar</span><span class="sxs-lookup"><span data-stu-id="67f29-165">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67f29-166">Saída do Atendedor de Conferência</span><span class="sxs-lookup"><span data-stu-id="67f29-166">Conferencing Attendant Outbound</span></span></p></td>
<td><p><span data-ttu-id="67f29-167">Servidor Front End executando o Atendedor de Conferência</span><span class="sxs-lookup"><span data-stu-id="67f29-167">Front End Server running Conferencing Attendant</span></span></p></td>
<td><p><span data-ttu-id="67f29-168">Qualquer</span><span class="sxs-lookup"><span data-stu-id="67f29-168">Any</span></span></p></td>
<td><p><span data-ttu-id="67f29-169">UDP e TCP</span><span class="sxs-lookup"><span data-stu-id="67f29-169">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="67f29-170">Qualquer</span><span class="sxs-lookup"><span data-stu-id="67f29-170">Any</span></span></p></td>
<td><p><span data-ttu-id="67f29-171">Qualquer</span><span class="sxs-lookup"><span data-stu-id="67f29-171">Any</span></span></p></td>
<td><p><span data-ttu-id="67f29-172">Não autenticar</span><span class="sxs-lookup"><span data-stu-id="67f29-172">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67f29-173">Entrada de Conferência A/V</span><span class="sxs-lookup"><span data-stu-id="67f29-173">A/V Conferencing Inbound</span></span></p></td>
<td><p><span data-ttu-id="67f29-174">Qualquer</span><span class="sxs-lookup"><span data-stu-id="67f29-174">Any</span></span></p></td>
<td><p><span data-ttu-id="67f29-175">Servidores Front-End</span><span class="sxs-lookup"><span data-stu-id="67f29-175">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="67f29-176">UDP e TCP</span><span class="sxs-lookup"><span data-stu-id="67f29-176">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="67f29-177">Qualquer</span><span class="sxs-lookup"><span data-stu-id="67f29-177">Any</span></span></p></td>
<td><p><span data-ttu-id="67f29-178">Qualquer</span><span class="sxs-lookup"><span data-stu-id="67f29-178">Any</span></span></p></td>
<td><p><span data-ttu-id="67f29-179">Não autenticar</span><span class="sxs-lookup"><span data-stu-id="67f29-179">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67f29-180">Saída de Conferência A/V</span><span class="sxs-lookup"><span data-stu-id="67f29-180">A/V Conferencing Outbound</span></span></p></td>
<td><p><span data-ttu-id="67f29-181">Servidores Front-End</span><span class="sxs-lookup"><span data-stu-id="67f29-181">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="67f29-182">Qualquer</span><span class="sxs-lookup"><span data-stu-id="67f29-182">Any</span></span></p></td>
<td><p><span data-ttu-id="67f29-183">UDP e TCP</span><span class="sxs-lookup"><span data-stu-id="67f29-183">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="67f29-184">Qualquer</span><span class="sxs-lookup"><span data-stu-id="67f29-184">Any</span></span></p></td>
<td><p><span data-ttu-id="67f29-185">Qualquer</span><span class="sxs-lookup"><span data-stu-id="67f29-185">Any</span></span></p></td>
<td><p><span data-ttu-id="67f29-186">Não autenticar</span><span class="sxs-lookup"><span data-stu-id="67f29-186">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67f29-187">Entrada do Exchange</span><span class="sxs-lookup"><span data-stu-id="67f29-187">Exchange Inbound</span></span></p></td>
<td><p><span data-ttu-id="67f29-188">Qualquer</span><span class="sxs-lookup"><span data-stu-id="67f29-188">Any</span></span></p></td>
<td><p><span data-ttu-id="67f29-189">Unificação de Mensagens do Exchange</span><span class="sxs-lookup"><span data-stu-id="67f29-189">Exchange Unified Messaging</span></span></p></td>
<td><p><span data-ttu-id="67f29-190">UDP e TCP</span><span class="sxs-lookup"><span data-stu-id="67f29-190">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="67f29-191">Qualquer</span><span class="sxs-lookup"><span data-stu-id="67f29-191">Any</span></span></p></td>
<td><p><span data-ttu-id="67f29-192">Qualquer</span><span class="sxs-lookup"><span data-stu-id="67f29-192">Any</span></span></p></td>
<td><p><span data-ttu-id="67f29-193">Não autenticar</span><span class="sxs-lookup"><span data-stu-id="67f29-193">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67f29-194">Entrada dos Servidores de Compartilhamento de Aplicativo</span><span class="sxs-lookup"><span data-stu-id="67f29-194">Application Sharing Servers Inbound</span></span></p></td>
<td><p><span data-ttu-id="67f29-195">Qualquer</span><span class="sxs-lookup"><span data-stu-id="67f29-195">Any</span></span></p></td>
<td><p><span data-ttu-id="67f29-196">Servidores de Compartilhamento de Aplicativos</span><span class="sxs-lookup"><span data-stu-id="67f29-196">Application Sharing Servers</span></span></p></td>
<td><p><span data-ttu-id="67f29-197">TCP</span><span class="sxs-lookup"><span data-stu-id="67f29-197">TCP</span></span></p></td>
<td><p><span data-ttu-id="67f29-198">Qualquer</span><span class="sxs-lookup"><span data-stu-id="67f29-198">Any</span></span></p></td>
<td><p><span data-ttu-id="67f29-199">Qualquer</span><span class="sxs-lookup"><span data-stu-id="67f29-199">Any</span></span></p></td>
<td><p><span data-ttu-id="67f29-200">Não autenticar</span><span class="sxs-lookup"><span data-stu-id="67f29-200">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67f29-201">Saída do Servidor de Compartilhamento de Aplicativos.</span><span class="sxs-lookup"><span data-stu-id="67f29-201">Application Sharing Server Outbound</span></span></p></td>
<td><p><span data-ttu-id="67f29-202">Servidores de Compartilhamento de Aplicativos</span><span class="sxs-lookup"><span data-stu-id="67f29-202">Application Sharing Servers</span></span></p></td>
<td><p><span data-ttu-id="67f29-203">Qualquer</span><span class="sxs-lookup"><span data-stu-id="67f29-203">Any</span></span></p></td>
<td><p><span data-ttu-id="67f29-204">TCP</span><span class="sxs-lookup"><span data-stu-id="67f29-204">TCP</span></span></p></td>
<td><p><span data-ttu-id="67f29-205">Qualquer</span><span class="sxs-lookup"><span data-stu-id="67f29-205">Any</span></span></p></td>
<td><p><span data-ttu-id="67f29-206">Qualquer</span><span class="sxs-lookup"><span data-stu-id="67f29-206">Any</span></span></p></td>
<td><p><span data-ttu-id="67f29-207">Não autenticar</span><span class="sxs-lookup"><span data-stu-id="67f29-207">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67f29-208">Saída do Exchange</span><span class="sxs-lookup"><span data-stu-id="67f29-208">Exchange Outbound</span></span></p></td>
<td><p><span data-ttu-id="67f29-209">Unificação de Mensagens do Exchange</span><span class="sxs-lookup"><span data-stu-id="67f29-209">Exchange Unified Messaging</span></span></p></td>
<td><p><span data-ttu-id="67f29-210">Qualquer</span><span class="sxs-lookup"><span data-stu-id="67f29-210">Any</span></span></p></td>
<td><p><span data-ttu-id="67f29-211">UDP e TCP</span><span class="sxs-lookup"><span data-stu-id="67f29-211">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="67f29-212">Qualquer</span><span class="sxs-lookup"><span data-stu-id="67f29-212">Any</span></span></p></td>
<td><p><span data-ttu-id="67f29-213">Qualquer</span><span class="sxs-lookup"><span data-stu-id="67f29-213">Any</span></span></p></td>
<td><p><span data-ttu-id="67f29-214">Não autenticar</span><span class="sxs-lookup"><span data-stu-id="67f29-214">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67f29-215">Clientes</span><span class="sxs-lookup"><span data-stu-id="67f29-215">Clients</span></span></p></td>
<td><p><span data-ttu-id="67f29-216">Qualquer</span><span class="sxs-lookup"><span data-stu-id="67f29-216">Any</span></span></p></td>
<td><p><span data-ttu-id="67f29-217">Qualquer</span><span class="sxs-lookup"><span data-stu-id="67f29-217">Any</span></span></p></td>
<td><p><span data-ttu-id="67f29-218">VIA</span><span class="sxs-lookup"><span data-stu-id="67f29-218">UDP</span></span></p></td>
<td><p><span data-ttu-id="67f29-219">Intervalo especificado de portas de mídia</span><span class="sxs-lookup"><span data-stu-id="67f29-219">Specified media port range</span></span></p></td>
<td><p><span data-ttu-id="67f29-220">Qualquer</span><span class="sxs-lookup"><span data-stu-id="67f29-220">Any</span></span></p></td>
<td><p><span data-ttu-id="67f29-221">Não autenticar</span><span class="sxs-lookup"><span data-stu-id="67f29-221">Do not authenticate</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

