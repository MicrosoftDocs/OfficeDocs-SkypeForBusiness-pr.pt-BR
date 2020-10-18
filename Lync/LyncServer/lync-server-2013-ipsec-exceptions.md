---
title: Exceções IPsec do Lync Server 2013
description: Lync Server 2013 exceções IPsec.
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
ms.openlocfilehash: 9b01264171592ec352b778e1aa7eee5861801991
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574997"
---
# <a name="ipsec-exceptions-in-lync-server-2013"></a><span data-ttu-id="6a1c0-103">Exceções de IPsec no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6a1c0-103">IPsec exceptions in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6a1c0-104">_**Última modificação do tópico:** 2012-06-27_</span><span class="sxs-lookup"><span data-stu-id="6a1c0-104">_**Topic Last Modified:** 2012-06-27_</span></span>

<span data-ttu-id="6a1c0-p101">Nas redes corporativas em que o protocolo IPsec (consulte a RFC 4301-4309 da IETF) foi implantado, o protocolo IPsec deverá ser desabilitado no intervalo de portas usado para a entrega de áudio, vídeo e vídeo panorama. A recomendação vem da necessidade de evitar qualquer atraso na alocação das portas de mídia por causa da negociação IPsec.</span><span class="sxs-lookup"><span data-stu-id="6a1c0-p101">For enterprise networks where Internet Protocol security (IPsec) (see IETF RFC 4301-4309) has been deployed, IPsec must be disabled over the range of ports used for the delivery of audio, video, and panorama video. The recommendation is motivated by the need to avoid any delay in the allocation of media ports due to IPsec negotiation.</span></span>

<span data-ttu-id="6a1c0-107">A tabela a seguir explica as configurações de exceções recomendadas do IPsec.</span><span class="sxs-lookup"><span data-stu-id="6a1c0-107">The following table explains the recommended IPsec exception settings.</span></span>

### <a name="recommended-ipsec-exceptions"></a><span data-ttu-id="6a1c0-108">Exceções recomendadas do IPsec</span><span class="sxs-lookup"><span data-stu-id="6a1c0-108">Recommended IPsec Exceptions</span></span>

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
<th><span data-ttu-id="6a1c0-109">Nome da regra</span><span class="sxs-lookup"><span data-stu-id="6a1c0-109">Rule name</span></span></th>
<th><span data-ttu-id="6a1c0-110">IP de origem</span><span class="sxs-lookup"><span data-stu-id="6a1c0-110">Source IP</span></span></th>
<th><span data-ttu-id="6a1c0-111">IP de destino</span><span class="sxs-lookup"><span data-stu-id="6a1c0-111">Destination IP</span></span></th>
<th><span data-ttu-id="6a1c0-112">Protocolo</span><span class="sxs-lookup"><span data-stu-id="6a1c0-112">Protocol</span></span></th>
<th><span data-ttu-id="6a1c0-113">Porta de origem</span><span class="sxs-lookup"><span data-stu-id="6a1c0-113">Source port</span></span></th>
<th><span data-ttu-id="6a1c0-114">Porta de destino</span><span class="sxs-lookup"><span data-stu-id="6a1c0-114">Destination port</span></span></th>
<th><span data-ttu-id="6a1c0-115">Requisito de autenticação</span><span class="sxs-lookup"><span data-stu-id="6a1c0-115">Authentication Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6a1c0-116">Entrada interna do Servidor de Borda A/V</span><span class="sxs-lookup"><span data-stu-id="6a1c0-116">A/V Edge Server Internal Inbound</span></span></p></td>
<td><p><span data-ttu-id="6a1c0-117">Qualquer</span><span class="sxs-lookup"><span data-stu-id="6a1c0-117">Any</span></span></p></td>
<td><p><span data-ttu-id="6a1c0-118">Interno do Servidor de Borda A/V</span><span class="sxs-lookup"><span data-stu-id="6a1c0-118">A/V Edge Server Internal</span></span></p></td>
<td><p><span data-ttu-id="6a1c0-119">UDP e TCP</span><span class="sxs-lookup"><span data-stu-id="6a1c0-119">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="6a1c0-120">Qualquer</span><span class="sxs-lookup"><span data-stu-id="6a1c0-120">Any</span></span></p></td>
<td><p><span data-ttu-id="6a1c0-121">Qualquer</span><span class="sxs-lookup"><span data-stu-id="6a1c0-121">Any</span></span></p></td>
<td><p><span data-ttu-id="6a1c0-122">Não autenticar</span><span class="sxs-lookup"><span data-stu-id="6a1c0-122">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6a1c0-123">Entrada externa do Servidor de Borda A/V</span><span class="sxs-lookup"><span data-stu-id="6a1c0-123">A/V Edge Server External Inbound</span></span></p></td>
<td><p><span data-ttu-id="6a1c0-124">Qualquer</span><span class="sxs-lookup"><span data-stu-id="6a1c0-124">Any</span></span></p></td>
<td><p><span data-ttu-id="6a1c0-125">Externo do Servidor de Borda A/V</span><span class="sxs-lookup"><span data-stu-id="6a1c0-125">A/V Edge Server External</span></span></p></td>
<td><p><span data-ttu-id="6a1c0-126">UDP e TCP</span><span class="sxs-lookup"><span data-stu-id="6a1c0-126">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="6a1c0-127">Qualquer</span><span class="sxs-lookup"><span data-stu-id="6a1c0-127">Any</span></span></p></td>
<td><p><span data-ttu-id="6a1c0-128">Qualquer</span><span class="sxs-lookup"><span data-stu-id="6a1c0-128">Any</span></span></p></td>
<td><p><span data-ttu-id="6a1c0-129">Não autenticar</span><span class="sxs-lookup"><span data-stu-id="6a1c0-129">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6a1c0-130">Saída interna do Servidor de Borda A/V</span><span class="sxs-lookup"><span data-stu-id="6a1c0-130">A/V Edge Server Internal Outbound</span></span></p></td>
<td><p><span data-ttu-id="6a1c0-131">Interno do Servidor de Borda A/V</span><span class="sxs-lookup"><span data-stu-id="6a1c0-131">A/V Edge Server Internal</span></span></p></td>
<td><p><span data-ttu-id="6a1c0-132">Qualquer</span><span class="sxs-lookup"><span data-stu-id="6a1c0-132">Any</span></span></p></td>
<td><p><span data-ttu-id="6a1c0-133">&amp;TCP UDP</span><span class="sxs-lookup"><span data-stu-id="6a1c0-133">UDP &amp; TCP</span></span></p></td>
<td><p><span data-ttu-id="6a1c0-134">Qualquer</span><span class="sxs-lookup"><span data-stu-id="6a1c0-134">Any</span></span></p></td>
<td><p><span data-ttu-id="6a1c0-135">Qualquer</span><span class="sxs-lookup"><span data-stu-id="6a1c0-135">Any</span></span></p></td>
<td><p><span data-ttu-id="6a1c0-136">Não autenticar</span><span class="sxs-lookup"><span data-stu-id="6a1c0-136">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6a1c0-137">Saída externa do Servidor de Borda A/V</span><span class="sxs-lookup"><span data-stu-id="6a1c0-137">A/V Edge Server External Outbound</span></span></p></td>
<td><p><span data-ttu-id="6a1c0-138">Externo do Servidor de Borda A/V</span><span class="sxs-lookup"><span data-stu-id="6a1c0-138">A/V Edge Server External</span></span></p></td>
<td><p><span data-ttu-id="6a1c0-139">Qualquer</span><span class="sxs-lookup"><span data-stu-id="6a1c0-139">Any</span></span></p></td>
<td><p><span data-ttu-id="6a1c0-140">UDP e TCP</span><span class="sxs-lookup"><span data-stu-id="6a1c0-140">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="6a1c0-141">Qualquer</span><span class="sxs-lookup"><span data-stu-id="6a1c0-141">Any</span></span></p></td>
<td><p><span data-ttu-id="6a1c0-142">Qualquer</span><span class="sxs-lookup"><span data-stu-id="6a1c0-142">Any</span></span></p></td>
<td><p><span data-ttu-id="6a1c0-143">Não autenticar</span><span class="sxs-lookup"><span data-stu-id="6a1c0-143">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6a1c0-144">Entrada do Servidor de Mediação</span><span class="sxs-lookup"><span data-stu-id="6a1c0-144">Mediation Server Inbound</span></span></p></td>
<td><p><span data-ttu-id="6a1c0-145">Qualquer</span><span class="sxs-lookup"><span data-stu-id="6a1c0-145">Any</span></span></p></td>
<td><p><span data-ttu-id="6a1c0-146">Mediação</span><span class="sxs-lookup"><span data-stu-id="6a1c0-146">Mediation</span></span></p>
<p><span data-ttu-id="6a1c0-147">Servidor (es)</span><span class="sxs-lookup"><span data-stu-id="6a1c0-147">Server(s)</span></span></p></td>
<td><p><span data-ttu-id="6a1c0-148">UDP e TCP</span><span class="sxs-lookup"><span data-stu-id="6a1c0-148">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="6a1c0-149">Qualquer</span><span class="sxs-lookup"><span data-stu-id="6a1c0-149">Any</span></span></p></td>
<td><p><span data-ttu-id="6a1c0-150">Qualquer</span><span class="sxs-lookup"><span data-stu-id="6a1c0-150">Any</span></span></p></td>
<td><p><span data-ttu-id="6a1c0-151">Não autenticar</span><span class="sxs-lookup"><span data-stu-id="6a1c0-151">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6a1c0-152">Saída do Servidor de Mediação</span><span class="sxs-lookup"><span data-stu-id="6a1c0-152">Mediation Server Outbound</span></span></p></td>
<td><p><span data-ttu-id="6a1c0-153">Mediação</span><span class="sxs-lookup"><span data-stu-id="6a1c0-153">Mediation</span></span></p>
<p><span data-ttu-id="6a1c0-154">Servidor (es)</span><span class="sxs-lookup"><span data-stu-id="6a1c0-154">Server(s)</span></span></p></td>
<td><p><span data-ttu-id="6a1c0-155">Qualquer</span><span class="sxs-lookup"><span data-stu-id="6a1c0-155">Any</span></span></p></td>
<td><p><span data-ttu-id="6a1c0-156">UDP e TCP</span><span class="sxs-lookup"><span data-stu-id="6a1c0-156">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="6a1c0-157">Qualquer</span><span class="sxs-lookup"><span data-stu-id="6a1c0-157">Any</span></span></p></td>
<td><p><span data-ttu-id="6a1c0-158">Qualquer</span><span class="sxs-lookup"><span data-stu-id="6a1c0-158">Any</span></span></p></td>
<td><p><span data-ttu-id="6a1c0-159">Não autenticar</span><span class="sxs-lookup"><span data-stu-id="6a1c0-159">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6a1c0-160">Entrada do Atendedor de Conferência</span><span class="sxs-lookup"><span data-stu-id="6a1c0-160">Conferencing Attendant Inbound</span></span></p></td>
<td><p><span data-ttu-id="6a1c0-161">Qualquer</span><span class="sxs-lookup"><span data-stu-id="6a1c0-161">Any</span></span></p></td>
<td><p><span data-ttu-id="6a1c0-162">Servidor Front End executando o Atendedor de Conferência</span><span class="sxs-lookup"><span data-stu-id="6a1c0-162">Front End Server running Conferencing Attendant</span></span></p></td>
<td><p><span data-ttu-id="6a1c0-163">UDP e TCP</span><span class="sxs-lookup"><span data-stu-id="6a1c0-163">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="6a1c0-164">Qualquer</span><span class="sxs-lookup"><span data-stu-id="6a1c0-164">Any</span></span></p></td>
<td><p><span data-ttu-id="6a1c0-165">Qualquer</span><span class="sxs-lookup"><span data-stu-id="6a1c0-165">Any</span></span></p></td>
<td><p><span data-ttu-id="6a1c0-166">Não autenticar</span><span class="sxs-lookup"><span data-stu-id="6a1c0-166">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6a1c0-167">Saída do Atendedor de Conferência</span><span class="sxs-lookup"><span data-stu-id="6a1c0-167">Conferencing Attendant Outbound</span></span></p></td>
<td><p><span data-ttu-id="6a1c0-168">Servidor Front End executando o Atendedor de Conferência</span><span class="sxs-lookup"><span data-stu-id="6a1c0-168">Front End Server running Conferencing Attendant</span></span></p></td>
<td><p><span data-ttu-id="6a1c0-169">Qualquer</span><span class="sxs-lookup"><span data-stu-id="6a1c0-169">Any</span></span></p></td>
<td><p><span data-ttu-id="6a1c0-170">UDP e TCP</span><span class="sxs-lookup"><span data-stu-id="6a1c0-170">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="6a1c0-171">Qualquer</span><span class="sxs-lookup"><span data-stu-id="6a1c0-171">Any</span></span></p></td>
<td><p><span data-ttu-id="6a1c0-172">Qualquer</span><span class="sxs-lookup"><span data-stu-id="6a1c0-172">Any</span></span></p></td>
<td><p><span data-ttu-id="6a1c0-173">Não autenticar</span><span class="sxs-lookup"><span data-stu-id="6a1c0-173">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6a1c0-174">Entrada de Conferência A/V</span><span class="sxs-lookup"><span data-stu-id="6a1c0-174">A/V Conferencing Inbound</span></span></p></td>
<td><p><span data-ttu-id="6a1c0-175">Qualquer</span><span class="sxs-lookup"><span data-stu-id="6a1c0-175">Any</span></span></p></td>
<td><p><span data-ttu-id="6a1c0-176">Servidores Front-End</span><span class="sxs-lookup"><span data-stu-id="6a1c0-176">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="6a1c0-177">UDP e TCP</span><span class="sxs-lookup"><span data-stu-id="6a1c0-177">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="6a1c0-178">Qualquer</span><span class="sxs-lookup"><span data-stu-id="6a1c0-178">Any</span></span></p></td>
<td><p><span data-ttu-id="6a1c0-179">Qualquer</span><span class="sxs-lookup"><span data-stu-id="6a1c0-179">Any</span></span></p></td>
<td><p><span data-ttu-id="6a1c0-180">Não autenticar</span><span class="sxs-lookup"><span data-stu-id="6a1c0-180">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6a1c0-181">Saída de Conferência A/V</span><span class="sxs-lookup"><span data-stu-id="6a1c0-181">A/V Conferencing Outbound</span></span></p></td>
<td><p><span data-ttu-id="6a1c0-182">Servidores Front-End</span><span class="sxs-lookup"><span data-stu-id="6a1c0-182">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="6a1c0-183">Qualquer</span><span class="sxs-lookup"><span data-stu-id="6a1c0-183">Any</span></span></p></td>
<td><p><span data-ttu-id="6a1c0-184">UDP e TCP</span><span class="sxs-lookup"><span data-stu-id="6a1c0-184">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="6a1c0-185">Qualquer</span><span class="sxs-lookup"><span data-stu-id="6a1c0-185">Any</span></span></p></td>
<td><p><span data-ttu-id="6a1c0-186">Qualquer</span><span class="sxs-lookup"><span data-stu-id="6a1c0-186">Any</span></span></p></td>
<td><p><span data-ttu-id="6a1c0-187">Não autenticar</span><span class="sxs-lookup"><span data-stu-id="6a1c0-187">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6a1c0-188">Entrada do Exchange</span><span class="sxs-lookup"><span data-stu-id="6a1c0-188">Exchange Inbound</span></span></p></td>
<td><p><span data-ttu-id="6a1c0-189">Qualquer</span><span class="sxs-lookup"><span data-stu-id="6a1c0-189">Any</span></span></p></td>
<td><p><span data-ttu-id="6a1c0-190">Unificação de Mensagens do Exchange</span><span class="sxs-lookup"><span data-stu-id="6a1c0-190">Exchange Unified Messaging</span></span></p></td>
<td><p><span data-ttu-id="6a1c0-191">UDP e TCP</span><span class="sxs-lookup"><span data-stu-id="6a1c0-191">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="6a1c0-192">Qualquer</span><span class="sxs-lookup"><span data-stu-id="6a1c0-192">Any</span></span></p></td>
<td><p><span data-ttu-id="6a1c0-193">Qualquer</span><span class="sxs-lookup"><span data-stu-id="6a1c0-193">Any</span></span></p></td>
<td><p><span data-ttu-id="6a1c0-194">Não autenticar</span><span class="sxs-lookup"><span data-stu-id="6a1c0-194">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6a1c0-195">Entrada dos Servidores de Compartilhamento de Aplicativo</span><span class="sxs-lookup"><span data-stu-id="6a1c0-195">Application Sharing Servers Inbound</span></span></p></td>
<td><p><span data-ttu-id="6a1c0-196">Qualquer</span><span class="sxs-lookup"><span data-stu-id="6a1c0-196">Any</span></span></p></td>
<td><p><span data-ttu-id="6a1c0-197">Servidores de Compartilhamento de Aplicativos</span><span class="sxs-lookup"><span data-stu-id="6a1c0-197">Application Sharing Servers</span></span></p></td>
<td><p><span data-ttu-id="6a1c0-198">TCP</span><span class="sxs-lookup"><span data-stu-id="6a1c0-198">TCP</span></span></p></td>
<td><p><span data-ttu-id="6a1c0-199">Qualquer</span><span class="sxs-lookup"><span data-stu-id="6a1c0-199">Any</span></span></p></td>
<td><p><span data-ttu-id="6a1c0-200">Qualquer</span><span class="sxs-lookup"><span data-stu-id="6a1c0-200">Any</span></span></p></td>
<td><p><span data-ttu-id="6a1c0-201">Não autenticar</span><span class="sxs-lookup"><span data-stu-id="6a1c0-201">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6a1c0-202">Saída do Servidor de Compartilhamento de Aplicativos.</span><span class="sxs-lookup"><span data-stu-id="6a1c0-202">Application Sharing Server Outbound</span></span></p></td>
<td><p><span data-ttu-id="6a1c0-203">Servidores de Compartilhamento de Aplicativos</span><span class="sxs-lookup"><span data-stu-id="6a1c0-203">Application Sharing Servers</span></span></p></td>
<td><p><span data-ttu-id="6a1c0-204">Qualquer</span><span class="sxs-lookup"><span data-stu-id="6a1c0-204">Any</span></span></p></td>
<td><p><span data-ttu-id="6a1c0-205">TCP</span><span class="sxs-lookup"><span data-stu-id="6a1c0-205">TCP</span></span></p></td>
<td><p><span data-ttu-id="6a1c0-206">Qualquer</span><span class="sxs-lookup"><span data-stu-id="6a1c0-206">Any</span></span></p></td>
<td><p><span data-ttu-id="6a1c0-207">Qualquer</span><span class="sxs-lookup"><span data-stu-id="6a1c0-207">Any</span></span></p></td>
<td><p><span data-ttu-id="6a1c0-208">Não autenticar</span><span class="sxs-lookup"><span data-stu-id="6a1c0-208">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6a1c0-209">Saída do Exchange</span><span class="sxs-lookup"><span data-stu-id="6a1c0-209">Exchange Outbound</span></span></p></td>
<td><p><span data-ttu-id="6a1c0-210">Unificação de Mensagens do Exchange</span><span class="sxs-lookup"><span data-stu-id="6a1c0-210">Exchange Unified Messaging</span></span></p></td>
<td><p><span data-ttu-id="6a1c0-211">Qualquer</span><span class="sxs-lookup"><span data-stu-id="6a1c0-211">Any</span></span></p></td>
<td><p><span data-ttu-id="6a1c0-212">UDP e TCP</span><span class="sxs-lookup"><span data-stu-id="6a1c0-212">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="6a1c0-213">Qualquer</span><span class="sxs-lookup"><span data-stu-id="6a1c0-213">Any</span></span></p></td>
<td><p><span data-ttu-id="6a1c0-214">Qualquer</span><span class="sxs-lookup"><span data-stu-id="6a1c0-214">Any</span></span></p></td>
<td><p><span data-ttu-id="6a1c0-215">Não autenticar</span><span class="sxs-lookup"><span data-stu-id="6a1c0-215">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6a1c0-216">Clientes</span><span class="sxs-lookup"><span data-stu-id="6a1c0-216">Clients</span></span></p></td>
<td><p><span data-ttu-id="6a1c0-217">Qualquer</span><span class="sxs-lookup"><span data-stu-id="6a1c0-217">Any</span></span></p></td>
<td><p><span data-ttu-id="6a1c0-218">Qualquer</span><span class="sxs-lookup"><span data-stu-id="6a1c0-218">Any</span></span></p></td>
<td><p><span data-ttu-id="6a1c0-219">VIA</span><span class="sxs-lookup"><span data-stu-id="6a1c0-219">UDP</span></span></p></td>
<td><p><span data-ttu-id="6a1c0-220">Intervalo especificado de portas de mídia</span><span class="sxs-lookup"><span data-stu-id="6a1c0-220">Specified media port range</span></span></p></td>
<td><p><span data-ttu-id="6a1c0-221">Qualquer</span><span class="sxs-lookup"><span data-stu-id="6a1c0-221">Any</span></span></p></td>
<td><p><span data-ttu-id="6a1c0-222">Não autenticar</span><span class="sxs-lookup"><span data-stu-id="6a1c0-222">Do not authenticate</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

