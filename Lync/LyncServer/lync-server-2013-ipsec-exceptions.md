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
ms.openlocfilehash: db7291674485dec30211d88e2739b0da89fb334f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035053"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="ipsec-exceptions-in-lync-server-2013"></a><span data-ttu-id="b497f-102">Exceções de IPsec no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b497f-102">IPsec exceptions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b497f-103">_**Última modificação do tópico:** 2012-06-27_</span><span class="sxs-lookup"><span data-stu-id="b497f-103">_**Topic Last Modified:** 2012-06-27_</span></span>

<span data-ttu-id="b497f-p101">Nas redes corporativas em que o protocolo IPsec (consulte a RFC 4301-4309 da IETF) foi implantado, o protocolo IPsec deverá ser desabilitado no intervalo de portas usado para a entrega de áudio, vídeo e vídeo panorama. A recomendação vem da necessidade de evitar qualquer atraso na alocação das portas de mídia por causa da negociação IPsec.</span><span class="sxs-lookup"><span data-stu-id="b497f-p101">For enterprise networks where Internet Protocol security (IPsec) (see IETF RFC 4301-4309) has been deployed, IPsec must be disabled over the range of ports used for the delivery of audio, video, and panorama video. The recommendation is motivated by the need to avoid any delay in the allocation of media ports due to IPsec negotiation.</span></span>

<span data-ttu-id="b497f-106">A tabela a seguir explica as configurações de exceções recomendadas do IPsec.</span><span class="sxs-lookup"><span data-stu-id="b497f-106">The following table explains the recommended IPsec exception settings.</span></span>

### <a name="recommended-ipsec-exceptions"></a><span data-ttu-id="b497f-107">Exceções recomendadas do IPsec</span><span class="sxs-lookup"><span data-stu-id="b497f-107">Recommended IPsec Exceptions</span></span>

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
<th><span data-ttu-id="b497f-108">Nome da regra</span><span class="sxs-lookup"><span data-stu-id="b497f-108">Rule name</span></span></th>
<th><span data-ttu-id="b497f-109">IP de origem</span><span class="sxs-lookup"><span data-stu-id="b497f-109">Source IP</span></span></th>
<th><span data-ttu-id="b497f-110">IP de destino</span><span class="sxs-lookup"><span data-stu-id="b497f-110">Destination IP</span></span></th>
<th><span data-ttu-id="b497f-111">Protocolo</span><span class="sxs-lookup"><span data-stu-id="b497f-111">Protocol</span></span></th>
<th><span data-ttu-id="b497f-112">Porta de origem</span><span class="sxs-lookup"><span data-stu-id="b497f-112">Source port</span></span></th>
<th><span data-ttu-id="b497f-113">Porta de destino</span><span class="sxs-lookup"><span data-stu-id="b497f-113">Destination port</span></span></th>
<th><span data-ttu-id="b497f-114">Requisito de autenticação</span><span class="sxs-lookup"><span data-stu-id="b497f-114">Authentication Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b497f-115">Entrada interna do Servidor de Borda A/V</span><span class="sxs-lookup"><span data-stu-id="b497f-115">A/V Edge Server Internal Inbound</span></span></p></td>
<td><p><span data-ttu-id="b497f-116">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="b497f-116">Any</span></span></p></td>
<td><p><span data-ttu-id="b497f-117">Interno do Servidor de Borda A/V</span><span class="sxs-lookup"><span data-stu-id="b497f-117">A/V Edge Server Internal</span></span></p></td>
<td><p><span data-ttu-id="b497f-118">UDP e TCP</span><span class="sxs-lookup"><span data-stu-id="b497f-118">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="b497f-119">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="b497f-119">Any</span></span></p></td>
<td><p><span data-ttu-id="b497f-120">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="b497f-120">Any</span></span></p></td>
<td><p><span data-ttu-id="b497f-121">Não autenticar</span><span class="sxs-lookup"><span data-stu-id="b497f-121">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b497f-122">Entrada externa do Servidor de Borda A/V</span><span class="sxs-lookup"><span data-stu-id="b497f-122">A/V Edge Server External Inbound</span></span></p></td>
<td><p><span data-ttu-id="b497f-123">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="b497f-123">Any</span></span></p></td>
<td><p><span data-ttu-id="b497f-124">Externo do Servidor de Borda A/V</span><span class="sxs-lookup"><span data-stu-id="b497f-124">A/V Edge Server External</span></span></p></td>
<td><p><span data-ttu-id="b497f-125">UDP e TCP</span><span class="sxs-lookup"><span data-stu-id="b497f-125">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="b497f-126">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="b497f-126">Any</span></span></p></td>
<td><p><span data-ttu-id="b497f-127">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="b497f-127">Any</span></span></p></td>
<td><p><span data-ttu-id="b497f-128">Não autenticar</span><span class="sxs-lookup"><span data-stu-id="b497f-128">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b497f-129">Saída interna do Servidor de Borda A/V</span><span class="sxs-lookup"><span data-stu-id="b497f-129">A/V Edge Server Internal Outbound</span></span></p></td>
<td><p><span data-ttu-id="b497f-130">Interno do Servidor de Borda A/V</span><span class="sxs-lookup"><span data-stu-id="b497f-130">A/V Edge Server Internal</span></span></p></td>
<td><p><span data-ttu-id="b497f-131">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="b497f-131">Any</span></span></p></td>
<td><p><span data-ttu-id="b497f-132">TCP &amp; UDP</span><span class="sxs-lookup"><span data-stu-id="b497f-132">UDP &amp; TCP</span></span></p></td>
<td><p><span data-ttu-id="b497f-133">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="b497f-133">Any</span></span></p></td>
<td><p><span data-ttu-id="b497f-134">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="b497f-134">Any</span></span></p></td>
<td><p><span data-ttu-id="b497f-135">Não autenticar</span><span class="sxs-lookup"><span data-stu-id="b497f-135">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b497f-136">Saída externa do Servidor de Borda A/V</span><span class="sxs-lookup"><span data-stu-id="b497f-136">A/V Edge Server External Outbound</span></span></p></td>
<td><p><span data-ttu-id="b497f-137">Externo do Servidor de Borda A/V</span><span class="sxs-lookup"><span data-stu-id="b497f-137">A/V Edge Server External</span></span></p></td>
<td><p><span data-ttu-id="b497f-138">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="b497f-138">Any</span></span></p></td>
<td><p><span data-ttu-id="b497f-139">UDP e TCP</span><span class="sxs-lookup"><span data-stu-id="b497f-139">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="b497f-140">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="b497f-140">Any</span></span></p></td>
<td><p><span data-ttu-id="b497f-141">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="b497f-141">Any</span></span></p></td>
<td><p><span data-ttu-id="b497f-142">Não autenticar</span><span class="sxs-lookup"><span data-stu-id="b497f-142">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b497f-143">Entrada do Servidor de Mediação</span><span class="sxs-lookup"><span data-stu-id="b497f-143">Mediation Server Inbound</span></span></p></td>
<td><p><span data-ttu-id="b497f-144">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="b497f-144">Any</span></span></p></td>
<td><p><span data-ttu-id="b497f-145">Mediação</span><span class="sxs-lookup"><span data-stu-id="b497f-145">Mediation</span></span></p>
<p><span data-ttu-id="b497f-146">Servidor (es)</span><span class="sxs-lookup"><span data-stu-id="b497f-146">Server(s)</span></span></p></td>
<td><p><span data-ttu-id="b497f-147">UDP e TCP</span><span class="sxs-lookup"><span data-stu-id="b497f-147">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="b497f-148">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="b497f-148">Any</span></span></p></td>
<td><p><span data-ttu-id="b497f-149">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="b497f-149">Any</span></span></p></td>
<td><p><span data-ttu-id="b497f-150">Não autenticar</span><span class="sxs-lookup"><span data-stu-id="b497f-150">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b497f-151">Saída do Servidor de Mediação</span><span class="sxs-lookup"><span data-stu-id="b497f-151">Mediation Server Outbound</span></span></p></td>
<td><p><span data-ttu-id="b497f-152">Mediação</span><span class="sxs-lookup"><span data-stu-id="b497f-152">Mediation</span></span></p>
<p><span data-ttu-id="b497f-153">Servidor (es)</span><span class="sxs-lookup"><span data-stu-id="b497f-153">Server(s)</span></span></p></td>
<td><p><span data-ttu-id="b497f-154">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="b497f-154">Any</span></span></p></td>
<td><p><span data-ttu-id="b497f-155">UDP e TCP</span><span class="sxs-lookup"><span data-stu-id="b497f-155">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="b497f-156">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="b497f-156">Any</span></span></p></td>
<td><p><span data-ttu-id="b497f-157">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="b497f-157">Any</span></span></p></td>
<td><p><span data-ttu-id="b497f-158">Não autenticar</span><span class="sxs-lookup"><span data-stu-id="b497f-158">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b497f-159">Entrada do Atendedor de Conferência</span><span class="sxs-lookup"><span data-stu-id="b497f-159">Conferencing Attendant Inbound</span></span></p></td>
<td><p><span data-ttu-id="b497f-160">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="b497f-160">Any</span></span></p></td>
<td><p><span data-ttu-id="b497f-161">Servidor Front End executando o Atendedor de Conferência</span><span class="sxs-lookup"><span data-stu-id="b497f-161">Front End Server running Conferencing Attendant</span></span></p></td>
<td><p><span data-ttu-id="b497f-162">UDP e TCP</span><span class="sxs-lookup"><span data-stu-id="b497f-162">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="b497f-163">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="b497f-163">Any</span></span></p></td>
<td><p><span data-ttu-id="b497f-164">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="b497f-164">Any</span></span></p></td>
<td><p><span data-ttu-id="b497f-165">Não autenticar</span><span class="sxs-lookup"><span data-stu-id="b497f-165">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b497f-166">Saída do Atendedor de Conferência</span><span class="sxs-lookup"><span data-stu-id="b497f-166">Conferencing Attendant Outbound</span></span></p></td>
<td><p><span data-ttu-id="b497f-167">Servidor Front End executando o Atendedor de Conferência</span><span class="sxs-lookup"><span data-stu-id="b497f-167">Front End Server running Conferencing Attendant</span></span></p></td>
<td><p><span data-ttu-id="b497f-168">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="b497f-168">Any</span></span></p></td>
<td><p><span data-ttu-id="b497f-169">UDP e TCP</span><span class="sxs-lookup"><span data-stu-id="b497f-169">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="b497f-170">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="b497f-170">Any</span></span></p></td>
<td><p><span data-ttu-id="b497f-171">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="b497f-171">Any</span></span></p></td>
<td><p><span data-ttu-id="b497f-172">Não autenticar</span><span class="sxs-lookup"><span data-stu-id="b497f-172">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b497f-173">Entrada de Conferência A/V</span><span class="sxs-lookup"><span data-stu-id="b497f-173">A/V Conferencing Inbound</span></span></p></td>
<td><p><span data-ttu-id="b497f-174">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="b497f-174">Any</span></span></p></td>
<td><p><span data-ttu-id="b497f-175">Servidores Front-End</span><span class="sxs-lookup"><span data-stu-id="b497f-175">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="b497f-176">UDP e TCP</span><span class="sxs-lookup"><span data-stu-id="b497f-176">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="b497f-177">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="b497f-177">Any</span></span></p></td>
<td><p><span data-ttu-id="b497f-178">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="b497f-178">Any</span></span></p></td>
<td><p><span data-ttu-id="b497f-179">Não autenticar</span><span class="sxs-lookup"><span data-stu-id="b497f-179">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b497f-180">Saída de Conferência A/V</span><span class="sxs-lookup"><span data-stu-id="b497f-180">A/V Conferencing Outbound</span></span></p></td>
<td><p><span data-ttu-id="b497f-181">Servidores Front-End</span><span class="sxs-lookup"><span data-stu-id="b497f-181">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="b497f-182">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="b497f-182">Any</span></span></p></td>
<td><p><span data-ttu-id="b497f-183">UDP e TCP</span><span class="sxs-lookup"><span data-stu-id="b497f-183">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="b497f-184">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="b497f-184">Any</span></span></p></td>
<td><p><span data-ttu-id="b497f-185">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="b497f-185">Any</span></span></p></td>
<td><p><span data-ttu-id="b497f-186">Não autenticar</span><span class="sxs-lookup"><span data-stu-id="b497f-186">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b497f-187">Entrada do Exchange</span><span class="sxs-lookup"><span data-stu-id="b497f-187">Exchange Inbound</span></span></p></td>
<td><p><span data-ttu-id="b497f-188">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="b497f-188">Any</span></span></p></td>
<td><p><span data-ttu-id="b497f-189">Unificação de Mensagens do Exchange</span><span class="sxs-lookup"><span data-stu-id="b497f-189">Exchange Unified Messaging</span></span></p></td>
<td><p><span data-ttu-id="b497f-190">UDP e TCP</span><span class="sxs-lookup"><span data-stu-id="b497f-190">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="b497f-191">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="b497f-191">Any</span></span></p></td>
<td><p><span data-ttu-id="b497f-192">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="b497f-192">Any</span></span></p></td>
<td><p><span data-ttu-id="b497f-193">Não autenticar</span><span class="sxs-lookup"><span data-stu-id="b497f-193">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b497f-194">Entrada dos Servidores de Compartilhamento de Aplicativo</span><span class="sxs-lookup"><span data-stu-id="b497f-194">Application Sharing Servers Inbound</span></span></p></td>
<td><p><span data-ttu-id="b497f-195">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="b497f-195">Any</span></span></p></td>
<td><p><span data-ttu-id="b497f-196">Servidores de Compartilhamento de Aplicativos</span><span class="sxs-lookup"><span data-stu-id="b497f-196">Application Sharing Servers</span></span></p></td>
<td><p><span data-ttu-id="b497f-197">TCP</span><span class="sxs-lookup"><span data-stu-id="b497f-197">TCP</span></span></p></td>
<td><p><span data-ttu-id="b497f-198">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="b497f-198">Any</span></span></p></td>
<td><p><span data-ttu-id="b497f-199">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="b497f-199">Any</span></span></p></td>
<td><p><span data-ttu-id="b497f-200">Não autenticar</span><span class="sxs-lookup"><span data-stu-id="b497f-200">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b497f-201">Saída do Servidor de Compartilhamento de Aplicativos.</span><span class="sxs-lookup"><span data-stu-id="b497f-201">Application Sharing Server Outbound</span></span></p></td>
<td><p><span data-ttu-id="b497f-202">Servidores de Compartilhamento de Aplicativos</span><span class="sxs-lookup"><span data-stu-id="b497f-202">Application Sharing Servers</span></span></p></td>
<td><p><span data-ttu-id="b497f-203">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="b497f-203">Any</span></span></p></td>
<td><p><span data-ttu-id="b497f-204">TCP</span><span class="sxs-lookup"><span data-stu-id="b497f-204">TCP</span></span></p></td>
<td><p><span data-ttu-id="b497f-205">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="b497f-205">Any</span></span></p></td>
<td><p><span data-ttu-id="b497f-206">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="b497f-206">Any</span></span></p></td>
<td><p><span data-ttu-id="b497f-207">Não autenticar</span><span class="sxs-lookup"><span data-stu-id="b497f-207">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b497f-208">Saída do Exchange</span><span class="sxs-lookup"><span data-stu-id="b497f-208">Exchange Outbound</span></span></p></td>
<td><p><span data-ttu-id="b497f-209">Unificação de Mensagens do Exchange</span><span class="sxs-lookup"><span data-stu-id="b497f-209">Exchange Unified Messaging</span></span></p></td>
<td><p><span data-ttu-id="b497f-210">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="b497f-210">Any</span></span></p></td>
<td><p><span data-ttu-id="b497f-211">UDP e TCP</span><span class="sxs-lookup"><span data-stu-id="b497f-211">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="b497f-212">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="b497f-212">Any</span></span></p></td>
<td><p><span data-ttu-id="b497f-213">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="b497f-213">Any</span></span></p></td>
<td><p><span data-ttu-id="b497f-214">Não autenticar</span><span class="sxs-lookup"><span data-stu-id="b497f-214">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b497f-215">Clientes</span><span class="sxs-lookup"><span data-stu-id="b497f-215">Clients</span></span></p></td>
<td><p><span data-ttu-id="b497f-216">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="b497f-216">Any</span></span></p></td>
<td><p><span data-ttu-id="b497f-217">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="b497f-217">Any</span></span></p></td>
<td><p><span data-ttu-id="b497f-218">VIA</span><span class="sxs-lookup"><span data-stu-id="b497f-218">UDP</span></span></p></td>
<td><p><span data-ttu-id="b497f-219">Intervalo especificado de portas de mídia</span><span class="sxs-lookup"><span data-stu-id="b497f-219">Specified media port range</span></span></p></td>
<td><p><span data-ttu-id="b497f-220">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="b497f-220">Any</span></span></p></td>
<td><p><span data-ttu-id="b497f-221">Não autenticar</span><span class="sxs-lookup"><span data-stu-id="b497f-221">Do not authenticate</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

