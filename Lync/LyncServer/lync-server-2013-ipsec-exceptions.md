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
ms.openlocfilehash: 665e97359af930614c2f7e2b251317f34e46ef0e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146084"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="ipsec-exceptions-in-lync-server-2013"></a><span data-ttu-id="43975-102">Exceções de IPsec no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="43975-102">IPsec exceptions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="43975-103">_**Última modificação do tópico:** 2012-06-27_</span><span class="sxs-lookup"><span data-stu-id="43975-103">_**Topic Last Modified:** 2012-06-27_</span></span>

<span data-ttu-id="43975-p101">Nas redes corporativas em que o protocolo IPsec (consulte a RFC 4301-4309 da IETF) foi implantado, o protocolo IPsec deverá ser desabilitado no intervalo de portas usado para a entrega de áudio, vídeo e vídeo panorama. A recomendação vem da necessidade de evitar qualquer atraso na alocação das portas de mídia por causa da negociação IPsec.</span><span class="sxs-lookup"><span data-stu-id="43975-p101">For enterprise networks where Internet Protocol security (IPsec) (see IETF RFC 4301-4309) has been deployed, IPsec must be disabled over the range of ports used for the delivery of audio, video, and panorama video. The recommendation is motivated by the need to avoid any delay in the allocation of media ports due to IPsec negotiation.</span></span>

<span data-ttu-id="43975-106">A tabela a seguir explica as configurações de exceções recomendadas do IPsec.</span><span class="sxs-lookup"><span data-stu-id="43975-106">The following table explains the recommended IPsec exception settings.</span></span>

### <a name="recommended-ipsec-exceptions"></a><span data-ttu-id="43975-107">Exceções recomendadas do IPsec</span><span class="sxs-lookup"><span data-stu-id="43975-107">Recommended IPsec Exceptions</span></span>

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
<th><span data-ttu-id="43975-108">Nome da regra</span><span class="sxs-lookup"><span data-stu-id="43975-108">Rule name</span></span></th>
<th><span data-ttu-id="43975-109">IP de origem</span><span class="sxs-lookup"><span data-stu-id="43975-109">Source IP</span></span></th>
<th><span data-ttu-id="43975-110">IP de destino</span><span class="sxs-lookup"><span data-stu-id="43975-110">Destination IP</span></span></th>
<th><span data-ttu-id="43975-111">Protocolo</span><span class="sxs-lookup"><span data-stu-id="43975-111">Protocol</span></span></th>
<th><span data-ttu-id="43975-112">Porta de origem</span><span class="sxs-lookup"><span data-stu-id="43975-112">Source port</span></span></th>
<th><span data-ttu-id="43975-113">Porta de destino</span><span class="sxs-lookup"><span data-stu-id="43975-113">Destination port</span></span></th>
<th><span data-ttu-id="43975-114">Requisito de autenticação</span><span class="sxs-lookup"><span data-stu-id="43975-114">Authentication Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="43975-115">Entrada interna do Servidor de Borda A/V</span><span class="sxs-lookup"><span data-stu-id="43975-115">A/V Edge Server Internal Inbound</span></span></p></td>
<td><p><span data-ttu-id="43975-116">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="43975-116">Any</span></span></p></td>
<td><p><span data-ttu-id="43975-117">Interno do Servidor de Borda A/V</span><span class="sxs-lookup"><span data-stu-id="43975-117">A/V Edge Server Internal</span></span></p></td>
<td><p><span data-ttu-id="43975-118">UDP e TCP</span><span class="sxs-lookup"><span data-stu-id="43975-118">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="43975-119">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="43975-119">Any</span></span></p></td>
<td><p><span data-ttu-id="43975-120">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="43975-120">Any</span></span></p></td>
<td><p><span data-ttu-id="43975-121">Não autenticar</span><span class="sxs-lookup"><span data-stu-id="43975-121">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43975-122">Entrada externa do Servidor de Borda A/V</span><span class="sxs-lookup"><span data-stu-id="43975-122">A/V Edge Server External Inbound</span></span></p></td>
<td><p><span data-ttu-id="43975-123">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="43975-123">Any</span></span></p></td>
<td><p><span data-ttu-id="43975-124">Externo do Servidor de Borda A/V</span><span class="sxs-lookup"><span data-stu-id="43975-124">A/V Edge Server External</span></span></p></td>
<td><p><span data-ttu-id="43975-125">UDP e TCP</span><span class="sxs-lookup"><span data-stu-id="43975-125">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="43975-126">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="43975-126">Any</span></span></p></td>
<td><p><span data-ttu-id="43975-127">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="43975-127">Any</span></span></p></td>
<td><p><span data-ttu-id="43975-128">Não autenticar</span><span class="sxs-lookup"><span data-stu-id="43975-128">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="43975-129">Saída interna do Servidor de Borda A/V</span><span class="sxs-lookup"><span data-stu-id="43975-129">A/V Edge Server Internal Outbound</span></span></p></td>
<td><p><span data-ttu-id="43975-130">Interno do Servidor de Borda A/V</span><span class="sxs-lookup"><span data-stu-id="43975-130">A/V Edge Server Internal</span></span></p></td>
<td><p><span data-ttu-id="43975-131">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="43975-131">Any</span></span></p></td>
<td><p><span data-ttu-id="43975-132">TCP &amp; UDP</span><span class="sxs-lookup"><span data-stu-id="43975-132">UDP &amp; TCP</span></span></p></td>
<td><p><span data-ttu-id="43975-133">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="43975-133">Any</span></span></p></td>
<td><p><span data-ttu-id="43975-134">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="43975-134">Any</span></span></p></td>
<td><p><span data-ttu-id="43975-135">Não autenticar</span><span class="sxs-lookup"><span data-stu-id="43975-135">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43975-136">Saída externa do Servidor de Borda A/V</span><span class="sxs-lookup"><span data-stu-id="43975-136">A/V Edge Server External Outbound</span></span></p></td>
<td><p><span data-ttu-id="43975-137">Externo do Servidor de Borda A/V</span><span class="sxs-lookup"><span data-stu-id="43975-137">A/V Edge Server External</span></span></p></td>
<td><p><span data-ttu-id="43975-138">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="43975-138">Any</span></span></p></td>
<td><p><span data-ttu-id="43975-139">UDP e TCP</span><span class="sxs-lookup"><span data-stu-id="43975-139">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="43975-140">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="43975-140">Any</span></span></p></td>
<td><p><span data-ttu-id="43975-141">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="43975-141">Any</span></span></p></td>
<td><p><span data-ttu-id="43975-142">Não autenticar</span><span class="sxs-lookup"><span data-stu-id="43975-142">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="43975-143">Entrada do Servidor de Mediação</span><span class="sxs-lookup"><span data-stu-id="43975-143">Mediation Server Inbound</span></span></p></td>
<td><p><span data-ttu-id="43975-144">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="43975-144">Any</span></span></p></td>
<td><p><span data-ttu-id="43975-145">Mediação</span><span class="sxs-lookup"><span data-stu-id="43975-145">Mediation</span></span></p>
<p><span data-ttu-id="43975-146">Servidor (es)</span><span class="sxs-lookup"><span data-stu-id="43975-146">Server(s)</span></span></p></td>
<td><p><span data-ttu-id="43975-147">UDP e TCP</span><span class="sxs-lookup"><span data-stu-id="43975-147">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="43975-148">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="43975-148">Any</span></span></p></td>
<td><p><span data-ttu-id="43975-149">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="43975-149">Any</span></span></p></td>
<td><p><span data-ttu-id="43975-150">Não autenticar</span><span class="sxs-lookup"><span data-stu-id="43975-150">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43975-151">Saída do Servidor de Mediação</span><span class="sxs-lookup"><span data-stu-id="43975-151">Mediation Server Outbound</span></span></p></td>
<td><p><span data-ttu-id="43975-152">Mediação</span><span class="sxs-lookup"><span data-stu-id="43975-152">Mediation</span></span></p>
<p><span data-ttu-id="43975-153">Servidor (es)</span><span class="sxs-lookup"><span data-stu-id="43975-153">Server(s)</span></span></p></td>
<td><p><span data-ttu-id="43975-154">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="43975-154">Any</span></span></p></td>
<td><p><span data-ttu-id="43975-155">UDP e TCP</span><span class="sxs-lookup"><span data-stu-id="43975-155">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="43975-156">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="43975-156">Any</span></span></p></td>
<td><p><span data-ttu-id="43975-157">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="43975-157">Any</span></span></p></td>
<td><p><span data-ttu-id="43975-158">Não autenticar</span><span class="sxs-lookup"><span data-stu-id="43975-158">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="43975-159">Entrada do Atendedor de Conferência</span><span class="sxs-lookup"><span data-stu-id="43975-159">Conferencing Attendant Inbound</span></span></p></td>
<td><p><span data-ttu-id="43975-160">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="43975-160">Any</span></span></p></td>
<td><p><span data-ttu-id="43975-161">Servidor Front End executando o Atendedor de Conferência</span><span class="sxs-lookup"><span data-stu-id="43975-161">Front End Server running Conferencing Attendant</span></span></p></td>
<td><p><span data-ttu-id="43975-162">UDP e TCP</span><span class="sxs-lookup"><span data-stu-id="43975-162">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="43975-163">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="43975-163">Any</span></span></p></td>
<td><p><span data-ttu-id="43975-164">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="43975-164">Any</span></span></p></td>
<td><p><span data-ttu-id="43975-165">Não autenticar</span><span class="sxs-lookup"><span data-stu-id="43975-165">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43975-166">Saída do Atendedor de Conferência</span><span class="sxs-lookup"><span data-stu-id="43975-166">Conferencing Attendant Outbound</span></span></p></td>
<td><p><span data-ttu-id="43975-167">Servidor Front End executando o Atendedor de Conferência</span><span class="sxs-lookup"><span data-stu-id="43975-167">Front End Server running Conferencing Attendant</span></span></p></td>
<td><p><span data-ttu-id="43975-168">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="43975-168">Any</span></span></p></td>
<td><p><span data-ttu-id="43975-169">UDP e TCP</span><span class="sxs-lookup"><span data-stu-id="43975-169">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="43975-170">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="43975-170">Any</span></span></p></td>
<td><p><span data-ttu-id="43975-171">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="43975-171">Any</span></span></p></td>
<td><p><span data-ttu-id="43975-172">Não autenticar</span><span class="sxs-lookup"><span data-stu-id="43975-172">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="43975-173">Entrada de Conferência A/V</span><span class="sxs-lookup"><span data-stu-id="43975-173">A/V Conferencing Inbound</span></span></p></td>
<td><p><span data-ttu-id="43975-174">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="43975-174">Any</span></span></p></td>
<td><p><span data-ttu-id="43975-175">Servidores Front-End</span><span class="sxs-lookup"><span data-stu-id="43975-175">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="43975-176">UDP e TCP</span><span class="sxs-lookup"><span data-stu-id="43975-176">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="43975-177">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="43975-177">Any</span></span></p></td>
<td><p><span data-ttu-id="43975-178">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="43975-178">Any</span></span></p></td>
<td><p><span data-ttu-id="43975-179">Não autenticar</span><span class="sxs-lookup"><span data-stu-id="43975-179">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43975-180">Saída de Conferência A/V</span><span class="sxs-lookup"><span data-stu-id="43975-180">A/V Conferencing Outbound</span></span></p></td>
<td><p><span data-ttu-id="43975-181">Servidores Front-End</span><span class="sxs-lookup"><span data-stu-id="43975-181">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="43975-182">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="43975-182">Any</span></span></p></td>
<td><p><span data-ttu-id="43975-183">UDP e TCP</span><span class="sxs-lookup"><span data-stu-id="43975-183">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="43975-184">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="43975-184">Any</span></span></p></td>
<td><p><span data-ttu-id="43975-185">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="43975-185">Any</span></span></p></td>
<td><p><span data-ttu-id="43975-186">Não autenticar</span><span class="sxs-lookup"><span data-stu-id="43975-186">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="43975-187">Entrada do Exchange</span><span class="sxs-lookup"><span data-stu-id="43975-187">Exchange Inbound</span></span></p></td>
<td><p><span data-ttu-id="43975-188">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="43975-188">Any</span></span></p></td>
<td><p><span data-ttu-id="43975-189">Unificação de Mensagens do Exchange</span><span class="sxs-lookup"><span data-stu-id="43975-189">Exchange Unified Messaging</span></span></p></td>
<td><p><span data-ttu-id="43975-190">UDP e TCP</span><span class="sxs-lookup"><span data-stu-id="43975-190">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="43975-191">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="43975-191">Any</span></span></p></td>
<td><p><span data-ttu-id="43975-192">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="43975-192">Any</span></span></p></td>
<td><p><span data-ttu-id="43975-193">Não autenticar</span><span class="sxs-lookup"><span data-stu-id="43975-193">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43975-194">Entrada dos Servidores de Compartilhamento de Aplicativo</span><span class="sxs-lookup"><span data-stu-id="43975-194">Application Sharing Servers Inbound</span></span></p></td>
<td><p><span data-ttu-id="43975-195">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="43975-195">Any</span></span></p></td>
<td><p><span data-ttu-id="43975-196">Servidores de Compartilhamento de Aplicativos</span><span class="sxs-lookup"><span data-stu-id="43975-196">Application Sharing Servers</span></span></p></td>
<td><p><span data-ttu-id="43975-197">TCP</span><span class="sxs-lookup"><span data-stu-id="43975-197">TCP</span></span></p></td>
<td><p><span data-ttu-id="43975-198">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="43975-198">Any</span></span></p></td>
<td><p><span data-ttu-id="43975-199">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="43975-199">Any</span></span></p></td>
<td><p><span data-ttu-id="43975-200">Não autenticar</span><span class="sxs-lookup"><span data-stu-id="43975-200">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="43975-201">Saída do Servidor de Compartilhamento de Aplicativos.</span><span class="sxs-lookup"><span data-stu-id="43975-201">Application Sharing Server Outbound</span></span></p></td>
<td><p><span data-ttu-id="43975-202">Servidores de Compartilhamento de Aplicativos</span><span class="sxs-lookup"><span data-stu-id="43975-202">Application Sharing Servers</span></span></p></td>
<td><p><span data-ttu-id="43975-203">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="43975-203">Any</span></span></p></td>
<td><p><span data-ttu-id="43975-204">TCP</span><span class="sxs-lookup"><span data-stu-id="43975-204">TCP</span></span></p></td>
<td><p><span data-ttu-id="43975-205">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="43975-205">Any</span></span></p></td>
<td><p><span data-ttu-id="43975-206">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="43975-206">Any</span></span></p></td>
<td><p><span data-ttu-id="43975-207">Não autenticar</span><span class="sxs-lookup"><span data-stu-id="43975-207">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43975-208">Saída do Exchange</span><span class="sxs-lookup"><span data-stu-id="43975-208">Exchange Outbound</span></span></p></td>
<td><p><span data-ttu-id="43975-209">Unificação de Mensagens do Exchange</span><span class="sxs-lookup"><span data-stu-id="43975-209">Exchange Unified Messaging</span></span></p></td>
<td><p><span data-ttu-id="43975-210">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="43975-210">Any</span></span></p></td>
<td><p><span data-ttu-id="43975-211">UDP e TCP</span><span class="sxs-lookup"><span data-stu-id="43975-211">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="43975-212">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="43975-212">Any</span></span></p></td>
<td><p><span data-ttu-id="43975-213">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="43975-213">Any</span></span></p></td>
<td><p><span data-ttu-id="43975-214">Não autenticar</span><span class="sxs-lookup"><span data-stu-id="43975-214">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="43975-215">Clientes</span><span class="sxs-lookup"><span data-stu-id="43975-215">Clients</span></span></p></td>
<td><p><span data-ttu-id="43975-216">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="43975-216">Any</span></span></p></td>
<td><p><span data-ttu-id="43975-217">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="43975-217">Any</span></span></p></td>
<td><p><span data-ttu-id="43975-218">VIA</span><span class="sxs-lookup"><span data-stu-id="43975-218">UDP</span></span></p></td>
<td><p><span data-ttu-id="43975-219">Intervalo especificado de portas de mídia</span><span class="sxs-lookup"><span data-stu-id="43975-219">Specified media port range</span></span></p></td>
<td><p><span data-ttu-id="43975-220">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="43975-220">Any</span></span></p></td>
<td><p><span data-ttu-id="43975-221">Não autenticar</span><span class="sxs-lookup"><span data-stu-id="43975-221">Do not authenticate</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

