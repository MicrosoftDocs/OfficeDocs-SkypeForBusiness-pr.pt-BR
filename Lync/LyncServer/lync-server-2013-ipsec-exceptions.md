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
ms.openlocfilehash: 37d5becaab996d6fe4889086d3a68a45ffc1f6d7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733451"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="ipsec-exceptions-in-lync-server-2013"></a><span data-ttu-id="0ab69-102">Exceções de IPsec no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0ab69-102">IPsec exceptions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0ab69-103">_**Tópico da última modificação:** 2012-06-27_</span><span class="sxs-lookup"><span data-stu-id="0ab69-103">_**Topic Last Modified:** 2012-06-27_</span></span>

<span data-ttu-id="0ab69-104">Para redes corporativas onde a segurança do protocolo Internet (IPsec) (consulte IETF RFC 4301-4309) foi implantada, o IPsec deve ser desabilitado no intervalo de portas usado para a entrega de vídeo de áudio, vídeo e panorama.</span><span class="sxs-lookup"><span data-stu-id="0ab69-104">For enterprise networks where Internet Protocol security (IPsec) (see IETF RFC 4301-4309) has been deployed, IPsec must be disabled over the range of ports used for the delivery of audio, video, and panorama video.</span></span> <span data-ttu-id="0ab69-105">Essa recomendação existe porque é necessário evitar atrasos na alocação das portas de mídia por causa da negociação IPsec.</span><span class="sxs-lookup"><span data-stu-id="0ab69-105">The recommendation is motivated by the need to avoid any delay in the allocation of media ports due to IPsec negotiation.</span></span>

<span data-ttu-id="0ab69-106">A tabela a seguir explica as configurações de exceções recomendadas do IPsec.</span><span class="sxs-lookup"><span data-stu-id="0ab69-106">The following table explains the recommended IPsec exception settings.</span></span>

### <a name="recommended-ipsec-exceptions"></a><span data-ttu-id="0ab69-107">Exceções recomendadas do IPsec</span><span class="sxs-lookup"><span data-stu-id="0ab69-107">Recommended IPsec Exceptions</span></span>

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
<th><span data-ttu-id="0ab69-108">Nome da regra</span><span class="sxs-lookup"><span data-stu-id="0ab69-108">Rule name</span></span></th>
<th><span data-ttu-id="0ab69-109">IP de origem</span><span class="sxs-lookup"><span data-stu-id="0ab69-109">Source IP</span></span></th>
<th><span data-ttu-id="0ab69-110">IP de destino</span><span class="sxs-lookup"><span data-stu-id="0ab69-110">Destination IP</span></span></th>
<th><span data-ttu-id="0ab69-111">Protocolo</span><span class="sxs-lookup"><span data-stu-id="0ab69-111">Protocol</span></span></th>
<th><span data-ttu-id="0ab69-112">Porta de origem</span><span class="sxs-lookup"><span data-stu-id="0ab69-112">Source port</span></span></th>
<th><span data-ttu-id="0ab69-113">Porta de destino</span><span class="sxs-lookup"><span data-stu-id="0ab69-113">Destination port</span></span></th>
<th><span data-ttu-id="0ab69-114">Requisito de autenticação</span><span class="sxs-lookup"><span data-stu-id="0ab69-114">Authentication Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0ab69-115">Entrada interna do Servidor de Borda A/V</span><span class="sxs-lookup"><span data-stu-id="0ab69-115">A/V Edge Server Internal Inbound</span></span></p></td>
<td><p><span data-ttu-id="0ab69-116">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="0ab69-116">Any</span></span></p></td>
<td><p><span data-ttu-id="0ab69-117">Interno do Servidor de Borda A/V</span><span class="sxs-lookup"><span data-stu-id="0ab69-117">A/V Edge Server Internal</span></span></p></td>
<td><p><span data-ttu-id="0ab69-118">UDP e TCP</span><span class="sxs-lookup"><span data-stu-id="0ab69-118">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="0ab69-119">Qualquer um </span><span class="sxs-lookup"><span data-stu-id="0ab69-119">Any</span></span></p></td>
<td><p><span data-ttu-id="0ab69-120">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="0ab69-120">Any</span></span></p></td>
<td><p><span data-ttu-id="0ab69-121">Não autenticar</span><span class="sxs-lookup"><span data-stu-id="0ab69-121">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0ab69-122">Entrada externa do Servidor de Borda A/V</span><span class="sxs-lookup"><span data-stu-id="0ab69-122">A/V Edge Server External Inbound</span></span></p></td>
<td><p><span data-ttu-id="0ab69-123">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="0ab69-123">Any</span></span></p></td>
<td><p><span data-ttu-id="0ab69-124">Externo do Servidor de Borda A/V</span><span class="sxs-lookup"><span data-stu-id="0ab69-124">A/V Edge Server External</span></span></p></td>
<td><p><span data-ttu-id="0ab69-125">UDP e TCP</span><span class="sxs-lookup"><span data-stu-id="0ab69-125">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="0ab69-126">Qualquer um </span><span class="sxs-lookup"><span data-stu-id="0ab69-126">Any</span></span></p></td>
<td><p><span data-ttu-id="0ab69-127">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="0ab69-127">Any</span></span></p></td>
<td><p><span data-ttu-id="0ab69-128">Não autenticar</span><span class="sxs-lookup"><span data-stu-id="0ab69-128">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0ab69-129">Saída interna do Servidor de Borda A/V</span><span class="sxs-lookup"><span data-stu-id="0ab69-129">A/V Edge Server Internal Outbound</span></span></p></td>
<td><p><span data-ttu-id="0ab69-130">Interno do Servidor de Borda A/V</span><span class="sxs-lookup"><span data-stu-id="0ab69-130">A/V Edge Server Internal</span></span></p></td>
<td><p><span data-ttu-id="0ab69-131">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="0ab69-131">Any</span></span></p></td>
<td><p><span data-ttu-id="0ab69-132">UDP &amp; TCP</span><span class="sxs-lookup"><span data-stu-id="0ab69-132">UDP &amp; TCP</span></span></p></td>
<td><p><span data-ttu-id="0ab69-133">Qualquer um </span><span class="sxs-lookup"><span data-stu-id="0ab69-133">Any</span></span></p></td>
<td><p><span data-ttu-id="0ab69-134">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="0ab69-134">Any</span></span></p></td>
<td><p><span data-ttu-id="0ab69-135">Não autenticar</span><span class="sxs-lookup"><span data-stu-id="0ab69-135">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0ab69-136">Saída externa do Servidor de Borda A/V</span><span class="sxs-lookup"><span data-stu-id="0ab69-136">A/V Edge Server External Outbound</span></span></p></td>
<td><p><span data-ttu-id="0ab69-137">Externo do Servidor de Borda A/V</span><span class="sxs-lookup"><span data-stu-id="0ab69-137">A/V Edge Server External</span></span></p></td>
<td><p><span data-ttu-id="0ab69-138">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="0ab69-138">Any</span></span></p></td>
<td><p><span data-ttu-id="0ab69-139">UDP e TCP</span><span class="sxs-lookup"><span data-stu-id="0ab69-139">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="0ab69-140">Qualquer um </span><span class="sxs-lookup"><span data-stu-id="0ab69-140">Any</span></span></p></td>
<td><p><span data-ttu-id="0ab69-141">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="0ab69-141">Any</span></span></p></td>
<td><p><span data-ttu-id="0ab69-142">Não autenticar</span><span class="sxs-lookup"><span data-stu-id="0ab69-142">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0ab69-143">Entrada do Servidor de Mediação</span><span class="sxs-lookup"><span data-stu-id="0ab69-143">Mediation Server Inbound</span></span></p></td>
<td><p><span data-ttu-id="0ab69-144">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="0ab69-144">Any</span></span></p></td>
<td><p><span data-ttu-id="0ab69-145">Mediação</span><span class="sxs-lookup"><span data-stu-id="0ab69-145">Mediation</span></span></p>
<p><span data-ttu-id="0ab69-146">Servidor(es)</span><span class="sxs-lookup"><span data-stu-id="0ab69-146">Server(s)</span></span></p></td>
<td><p><span data-ttu-id="0ab69-147">UDP e TCP</span><span class="sxs-lookup"><span data-stu-id="0ab69-147">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="0ab69-148">Qualquer um </span><span class="sxs-lookup"><span data-stu-id="0ab69-148">Any</span></span></p></td>
<td><p><span data-ttu-id="0ab69-149">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="0ab69-149">Any</span></span></p></td>
<td><p><span data-ttu-id="0ab69-150">Não autenticar</span><span class="sxs-lookup"><span data-stu-id="0ab69-150">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0ab69-151">Saída do Servidor de Mediação</span><span class="sxs-lookup"><span data-stu-id="0ab69-151">Mediation Server Outbound</span></span></p></td>
<td><p><span data-ttu-id="0ab69-152">Mediação</span><span class="sxs-lookup"><span data-stu-id="0ab69-152">Mediation</span></span></p>
<p><span data-ttu-id="0ab69-153">Servidor(es)</span><span class="sxs-lookup"><span data-stu-id="0ab69-153">Server(s)</span></span></p></td>
<td><p><span data-ttu-id="0ab69-154">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="0ab69-154">Any</span></span></p></td>
<td><p><span data-ttu-id="0ab69-155">UDP e TCP</span><span class="sxs-lookup"><span data-stu-id="0ab69-155">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="0ab69-156">Qualquer um </span><span class="sxs-lookup"><span data-stu-id="0ab69-156">Any</span></span></p></td>
<td><p><span data-ttu-id="0ab69-157">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="0ab69-157">Any</span></span></p></td>
<td><p><span data-ttu-id="0ab69-158">Não autenticar</span><span class="sxs-lookup"><span data-stu-id="0ab69-158">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0ab69-159">Entrada do Atendedor de Conferência</span><span class="sxs-lookup"><span data-stu-id="0ab69-159">Conferencing Attendant Inbound</span></span></p></td>
<td><p><span data-ttu-id="0ab69-160">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="0ab69-160">Any</span></span></p></td>
<td><p><span data-ttu-id="0ab69-161">Servidor Front-End executando o Atendedor de Conferência</span><span class="sxs-lookup"><span data-stu-id="0ab69-161">Front End Server running Conferencing Attendant</span></span></p></td>
<td><p><span data-ttu-id="0ab69-162">UDP e TCP</span><span class="sxs-lookup"><span data-stu-id="0ab69-162">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="0ab69-163">Qualquer um </span><span class="sxs-lookup"><span data-stu-id="0ab69-163">Any</span></span></p></td>
<td><p><span data-ttu-id="0ab69-164">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="0ab69-164">Any</span></span></p></td>
<td><p><span data-ttu-id="0ab69-165">Não autenticar</span><span class="sxs-lookup"><span data-stu-id="0ab69-165">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0ab69-166">Saída do Atendedor de Conferência</span><span class="sxs-lookup"><span data-stu-id="0ab69-166">Conferencing Attendant Outbound</span></span></p></td>
<td><p><span data-ttu-id="0ab69-167">Servidor Front-End executando o Atendedor de Conferência</span><span class="sxs-lookup"><span data-stu-id="0ab69-167">Front End Server running Conferencing Attendant</span></span></p></td>
<td><p><span data-ttu-id="0ab69-168">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="0ab69-168">Any</span></span></p></td>
<td><p><span data-ttu-id="0ab69-169">UDP e TCP</span><span class="sxs-lookup"><span data-stu-id="0ab69-169">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="0ab69-170">Qualquer um </span><span class="sxs-lookup"><span data-stu-id="0ab69-170">Any</span></span></p></td>
<td><p><span data-ttu-id="0ab69-171">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="0ab69-171">Any</span></span></p></td>
<td><p><span data-ttu-id="0ab69-172">Não autenticar</span><span class="sxs-lookup"><span data-stu-id="0ab69-172">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0ab69-173">Entrada de Conferência A/V</span><span class="sxs-lookup"><span data-stu-id="0ab69-173">A/V Conferencing Inbound</span></span></p></td>
<td><p><span data-ttu-id="0ab69-174">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="0ab69-174">Any</span></span></p></td>
<td><p><span data-ttu-id="0ab69-175">Servidores Front-End</span><span class="sxs-lookup"><span data-stu-id="0ab69-175">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="0ab69-176">UDP e TCP</span><span class="sxs-lookup"><span data-stu-id="0ab69-176">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="0ab69-177">Qualquer um </span><span class="sxs-lookup"><span data-stu-id="0ab69-177">Any</span></span></p></td>
<td><p><span data-ttu-id="0ab69-178">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="0ab69-178">Any</span></span></p></td>
<td><p><span data-ttu-id="0ab69-179">Não autenticar</span><span class="sxs-lookup"><span data-stu-id="0ab69-179">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0ab69-180">Saída de Conferência A/V</span><span class="sxs-lookup"><span data-stu-id="0ab69-180">A/V Conferencing Outbound</span></span></p></td>
<td><p><span data-ttu-id="0ab69-181">Servidores Front-End</span><span class="sxs-lookup"><span data-stu-id="0ab69-181">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="0ab69-182">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="0ab69-182">Any</span></span></p></td>
<td><p><span data-ttu-id="0ab69-183">UDP e TCP</span><span class="sxs-lookup"><span data-stu-id="0ab69-183">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="0ab69-184">Qualquer um </span><span class="sxs-lookup"><span data-stu-id="0ab69-184">Any</span></span></p></td>
<td><p><span data-ttu-id="0ab69-185">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="0ab69-185">Any</span></span></p></td>
<td><p><span data-ttu-id="0ab69-186">Não autenticar</span><span class="sxs-lookup"><span data-stu-id="0ab69-186">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0ab69-187">Entrada do Exchange</span><span class="sxs-lookup"><span data-stu-id="0ab69-187">Exchange Inbound</span></span></p></td>
<td><p><span data-ttu-id="0ab69-188">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="0ab69-188">Any</span></span></p></td>
<td><p><span data-ttu-id="0ab69-189">Unificação de Mensagens do Exchange</span><span class="sxs-lookup"><span data-stu-id="0ab69-189">Exchange Unified Messaging</span></span></p></td>
<td><p><span data-ttu-id="0ab69-190">UDP e TCP</span><span class="sxs-lookup"><span data-stu-id="0ab69-190">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="0ab69-191">Qualquer um </span><span class="sxs-lookup"><span data-stu-id="0ab69-191">Any</span></span></p></td>
<td><p><span data-ttu-id="0ab69-192">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="0ab69-192">Any</span></span></p></td>
<td><p><span data-ttu-id="0ab69-193">Não autenticar</span><span class="sxs-lookup"><span data-stu-id="0ab69-193">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0ab69-194">Entrada dos Servidores de Compartilhamento de Aplicativo</span><span class="sxs-lookup"><span data-stu-id="0ab69-194">Application Sharing Servers Inbound</span></span></p></td>
<td><p><span data-ttu-id="0ab69-195">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="0ab69-195">Any</span></span></p></td>
<td><p><span data-ttu-id="0ab69-196">Servidores de Compartilhamento de Aplicativos</span><span class="sxs-lookup"><span data-stu-id="0ab69-196">Application Sharing Servers</span></span></p></td>
<td><p><span data-ttu-id="0ab69-197">TCP</span><span class="sxs-lookup"><span data-stu-id="0ab69-197">TCP</span></span></p></td>
<td><p><span data-ttu-id="0ab69-198">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="0ab69-198">Any</span></span></p></td>
<td><p><span data-ttu-id="0ab69-199">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="0ab69-199">Any</span></span></p></td>
<td><p><span data-ttu-id="0ab69-200">Não autenticar</span><span class="sxs-lookup"><span data-stu-id="0ab69-200">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0ab69-201">Saída do Servidor de Compartilhamento de Aplicativos</span><span class="sxs-lookup"><span data-stu-id="0ab69-201">Application Sharing Server Outbound</span></span></p></td>
<td><p><span data-ttu-id="0ab69-202">Servidores de Compartilhamento de Aplicativos</span><span class="sxs-lookup"><span data-stu-id="0ab69-202">Application Sharing Servers</span></span></p></td>
<td><p><span data-ttu-id="0ab69-203">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="0ab69-203">Any</span></span></p></td>
<td><p><span data-ttu-id="0ab69-204">TCP</span><span class="sxs-lookup"><span data-stu-id="0ab69-204">TCP</span></span></p></td>
<td><p><span data-ttu-id="0ab69-205">Qualquer um </span><span class="sxs-lookup"><span data-stu-id="0ab69-205">Any</span></span></p></td>
<td><p><span data-ttu-id="0ab69-206">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="0ab69-206">Any</span></span></p></td>
<td><p><span data-ttu-id="0ab69-207">Não autenticar</span><span class="sxs-lookup"><span data-stu-id="0ab69-207">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0ab69-208">Saída do Exchange</span><span class="sxs-lookup"><span data-stu-id="0ab69-208">Exchange Outbound</span></span></p></td>
<td><p><span data-ttu-id="0ab69-209">Unificação de Mensagens do Exchange</span><span class="sxs-lookup"><span data-stu-id="0ab69-209">Exchange Unified Messaging</span></span></p></td>
<td><p><span data-ttu-id="0ab69-210">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="0ab69-210">Any</span></span></p></td>
<td><p><span data-ttu-id="0ab69-211">UDP e TCP</span><span class="sxs-lookup"><span data-stu-id="0ab69-211">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="0ab69-212">Qualquer um </span><span class="sxs-lookup"><span data-stu-id="0ab69-212">Any</span></span></p></td>
<td><p><span data-ttu-id="0ab69-213">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="0ab69-213">Any</span></span></p></td>
<td><p><span data-ttu-id="0ab69-214">Não autenticar</span><span class="sxs-lookup"><span data-stu-id="0ab69-214">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0ab69-215">Clientes</span><span class="sxs-lookup"><span data-stu-id="0ab69-215">Clients</span></span></p></td>
<td><p><span data-ttu-id="0ab69-216">Qualquer um </span><span class="sxs-lookup"><span data-stu-id="0ab69-216">Any</span></span></p></td>
<td><p><span data-ttu-id="0ab69-217">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="0ab69-217">Any</span></span></p></td>
<td><p><span data-ttu-id="0ab69-218">UDP</span><span class="sxs-lookup"><span data-stu-id="0ab69-218">UDP</span></span></p></td>
<td><p><span data-ttu-id="0ab69-219">Intervalo especificado de portas de mídia</span><span class="sxs-lookup"><span data-stu-id="0ab69-219">Specified media port range</span></span></p></td>
<td><p><span data-ttu-id="0ab69-220">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="0ab69-220">Any</span></span></p></td>
<td><p><span data-ttu-id="0ab69-221">Não autenticar</span><span class="sxs-lookup"><span data-stu-id="0ab69-221">Do not authenticate</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

