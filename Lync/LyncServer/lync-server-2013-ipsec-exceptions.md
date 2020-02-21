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
ms.openlocfilehash: bd649cea823ce13460de924ffc49741b3ca5c6d6
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42186784"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="ipsec-exceptions-in-lync-server-2013"></a><span data-ttu-id="000d8-102">Exceções de IPsec no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="000d8-102">IPsec exceptions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="000d8-103">_**Última modificação do tópico:** 2012-06-27_</span><span class="sxs-lookup"><span data-stu-id="000d8-103">_**Topic Last Modified:** 2012-06-27_</span></span>

<span data-ttu-id="000d8-p101">Nas redes corporativas em que o protocolo IPsec (consulte a RFC 4301-4309 da IETF) foi implantado, o protocolo IPsec deverá ser desabilitado no intervalo de portas usado para a entrega de áudio, vídeo e vídeo panorama. A recomendação vem da necessidade de evitar qualquer atraso na alocação das portas de mídia por causa da negociação IPsec.</span><span class="sxs-lookup"><span data-stu-id="000d8-p101">For enterprise networks where Internet Protocol security (IPsec) (see IETF RFC 4301-4309) has been deployed, IPsec must be disabled over the range of ports used for the delivery of audio, video, and panorama video. The recommendation is motivated by the need to avoid any delay in the allocation of media ports due to IPsec negotiation.</span></span>

<span data-ttu-id="000d8-106">A tabela a seguir explica as configurações de exceções recomendadas do IPsec.</span><span class="sxs-lookup"><span data-stu-id="000d8-106">The following table explains the recommended IPsec exception settings.</span></span>

### <a name="recommended-ipsec-exceptions"></a><span data-ttu-id="000d8-107">Exceções recomendadas do IPsec</span><span class="sxs-lookup"><span data-stu-id="000d8-107">Recommended IPsec Exceptions</span></span>

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
<th><span data-ttu-id="000d8-108">Nome da regra</span><span class="sxs-lookup"><span data-stu-id="000d8-108">Rule name</span></span></th>
<th><span data-ttu-id="000d8-109">IP de origem</span><span class="sxs-lookup"><span data-stu-id="000d8-109">Source IP</span></span></th>
<th><span data-ttu-id="000d8-110">IP de destino</span><span class="sxs-lookup"><span data-stu-id="000d8-110">Destination IP</span></span></th>
<th><span data-ttu-id="000d8-111">Protocolo</span><span class="sxs-lookup"><span data-stu-id="000d8-111">Protocol</span></span></th>
<th><span data-ttu-id="000d8-112">Porta de origem</span><span class="sxs-lookup"><span data-stu-id="000d8-112">Source port</span></span></th>
<th><span data-ttu-id="000d8-113">Porta de destino</span><span class="sxs-lookup"><span data-stu-id="000d8-113">Destination port</span></span></th>
<th><span data-ttu-id="000d8-114">Requisito de autenticação</span><span class="sxs-lookup"><span data-stu-id="000d8-114">Authentication Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="000d8-115">Entrada interna do Servidor de Borda A/V</span><span class="sxs-lookup"><span data-stu-id="000d8-115">A/V Edge Server Internal Inbound</span></span></p></td>
<td><p><span data-ttu-id="000d8-116">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="000d8-116">Any</span></span></p></td>
<td><p><span data-ttu-id="000d8-117">Interno do Servidor de Borda A/V</span><span class="sxs-lookup"><span data-stu-id="000d8-117">A/V Edge Server Internal</span></span></p></td>
<td><p><span data-ttu-id="000d8-118">UDP e TCP</span><span class="sxs-lookup"><span data-stu-id="000d8-118">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="000d8-119">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="000d8-119">Any</span></span></p></td>
<td><p><span data-ttu-id="000d8-120">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="000d8-120">Any</span></span></p></td>
<td><p><span data-ttu-id="000d8-121">Não autenticar</span><span class="sxs-lookup"><span data-stu-id="000d8-121">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="000d8-122">Entrada externa do Servidor de Borda A/V</span><span class="sxs-lookup"><span data-stu-id="000d8-122">A/V Edge Server External Inbound</span></span></p></td>
<td><p><span data-ttu-id="000d8-123">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="000d8-123">Any</span></span></p></td>
<td><p><span data-ttu-id="000d8-124">Externo do Servidor de Borda A/V</span><span class="sxs-lookup"><span data-stu-id="000d8-124">A/V Edge Server External</span></span></p></td>
<td><p><span data-ttu-id="000d8-125">UDP e TCP</span><span class="sxs-lookup"><span data-stu-id="000d8-125">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="000d8-126">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="000d8-126">Any</span></span></p></td>
<td><p><span data-ttu-id="000d8-127">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="000d8-127">Any</span></span></p></td>
<td><p><span data-ttu-id="000d8-128">Não autenticar</span><span class="sxs-lookup"><span data-stu-id="000d8-128">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="000d8-129">Saída interna do Servidor de Borda A/V</span><span class="sxs-lookup"><span data-stu-id="000d8-129">A/V Edge Server Internal Outbound</span></span></p></td>
<td><p><span data-ttu-id="000d8-130">Interno do Servidor de Borda A/V</span><span class="sxs-lookup"><span data-stu-id="000d8-130">A/V Edge Server Internal</span></span></p></td>
<td><p><span data-ttu-id="000d8-131">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="000d8-131">Any</span></span></p></td>
<td><p><span data-ttu-id="000d8-132">TCP &amp; UDP</span><span class="sxs-lookup"><span data-stu-id="000d8-132">UDP &amp; TCP</span></span></p></td>
<td><p><span data-ttu-id="000d8-133">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="000d8-133">Any</span></span></p></td>
<td><p><span data-ttu-id="000d8-134">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="000d8-134">Any</span></span></p></td>
<td><p><span data-ttu-id="000d8-135">Não autenticar</span><span class="sxs-lookup"><span data-stu-id="000d8-135">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="000d8-136">Saída externa do Servidor de Borda A/V</span><span class="sxs-lookup"><span data-stu-id="000d8-136">A/V Edge Server External Outbound</span></span></p></td>
<td><p><span data-ttu-id="000d8-137">Externo do Servidor de Borda A/V</span><span class="sxs-lookup"><span data-stu-id="000d8-137">A/V Edge Server External</span></span></p></td>
<td><p><span data-ttu-id="000d8-138">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="000d8-138">Any</span></span></p></td>
<td><p><span data-ttu-id="000d8-139">UDP e TCP</span><span class="sxs-lookup"><span data-stu-id="000d8-139">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="000d8-140">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="000d8-140">Any</span></span></p></td>
<td><p><span data-ttu-id="000d8-141">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="000d8-141">Any</span></span></p></td>
<td><p><span data-ttu-id="000d8-142">Não autenticar</span><span class="sxs-lookup"><span data-stu-id="000d8-142">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="000d8-143">Entrada do Servidor de Mediação</span><span class="sxs-lookup"><span data-stu-id="000d8-143">Mediation Server Inbound</span></span></p></td>
<td><p><span data-ttu-id="000d8-144">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="000d8-144">Any</span></span></p></td>
<td><p><span data-ttu-id="000d8-145">Mediação</span><span class="sxs-lookup"><span data-stu-id="000d8-145">Mediation</span></span></p>
<p><span data-ttu-id="000d8-146">Servidor (es)</span><span class="sxs-lookup"><span data-stu-id="000d8-146">Server(s)</span></span></p></td>
<td><p><span data-ttu-id="000d8-147">UDP e TCP</span><span class="sxs-lookup"><span data-stu-id="000d8-147">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="000d8-148">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="000d8-148">Any</span></span></p></td>
<td><p><span data-ttu-id="000d8-149">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="000d8-149">Any</span></span></p></td>
<td><p><span data-ttu-id="000d8-150">Não autenticar</span><span class="sxs-lookup"><span data-stu-id="000d8-150">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="000d8-151">Saída do Servidor de Mediação</span><span class="sxs-lookup"><span data-stu-id="000d8-151">Mediation Server Outbound</span></span></p></td>
<td><p><span data-ttu-id="000d8-152">Mediação</span><span class="sxs-lookup"><span data-stu-id="000d8-152">Mediation</span></span></p>
<p><span data-ttu-id="000d8-153">Servidor (es)</span><span class="sxs-lookup"><span data-stu-id="000d8-153">Server(s)</span></span></p></td>
<td><p><span data-ttu-id="000d8-154">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="000d8-154">Any</span></span></p></td>
<td><p><span data-ttu-id="000d8-155">UDP e TCP</span><span class="sxs-lookup"><span data-stu-id="000d8-155">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="000d8-156">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="000d8-156">Any</span></span></p></td>
<td><p><span data-ttu-id="000d8-157">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="000d8-157">Any</span></span></p></td>
<td><p><span data-ttu-id="000d8-158">Não autenticar</span><span class="sxs-lookup"><span data-stu-id="000d8-158">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="000d8-159">Entrada do Atendedor de Conferência</span><span class="sxs-lookup"><span data-stu-id="000d8-159">Conferencing Attendant Inbound</span></span></p></td>
<td><p><span data-ttu-id="000d8-160">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="000d8-160">Any</span></span></p></td>
<td><p><span data-ttu-id="000d8-161">Servidor Front End executando o Atendedor de Conferência</span><span class="sxs-lookup"><span data-stu-id="000d8-161">Front End Server running Conferencing Attendant</span></span></p></td>
<td><p><span data-ttu-id="000d8-162">UDP e TCP</span><span class="sxs-lookup"><span data-stu-id="000d8-162">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="000d8-163">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="000d8-163">Any</span></span></p></td>
<td><p><span data-ttu-id="000d8-164">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="000d8-164">Any</span></span></p></td>
<td><p><span data-ttu-id="000d8-165">Não autenticar</span><span class="sxs-lookup"><span data-stu-id="000d8-165">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="000d8-166">Saída do Atendedor de Conferência</span><span class="sxs-lookup"><span data-stu-id="000d8-166">Conferencing Attendant Outbound</span></span></p></td>
<td><p><span data-ttu-id="000d8-167">Servidor Front End executando o Atendedor de Conferência</span><span class="sxs-lookup"><span data-stu-id="000d8-167">Front End Server running Conferencing Attendant</span></span></p></td>
<td><p><span data-ttu-id="000d8-168">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="000d8-168">Any</span></span></p></td>
<td><p><span data-ttu-id="000d8-169">UDP e TCP</span><span class="sxs-lookup"><span data-stu-id="000d8-169">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="000d8-170">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="000d8-170">Any</span></span></p></td>
<td><p><span data-ttu-id="000d8-171">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="000d8-171">Any</span></span></p></td>
<td><p><span data-ttu-id="000d8-172">Não autenticar</span><span class="sxs-lookup"><span data-stu-id="000d8-172">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="000d8-173">Entrada de Conferência A/V</span><span class="sxs-lookup"><span data-stu-id="000d8-173">A/V Conferencing Inbound</span></span></p></td>
<td><p><span data-ttu-id="000d8-174">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="000d8-174">Any</span></span></p></td>
<td><p><span data-ttu-id="000d8-175">Servidores Front-End</span><span class="sxs-lookup"><span data-stu-id="000d8-175">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="000d8-176">UDP e TCP</span><span class="sxs-lookup"><span data-stu-id="000d8-176">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="000d8-177">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="000d8-177">Any</span></span></p></td>
<td><p><span data-ttu-id="000d8-178">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="000d8-178">Any</span></span></p></td>
<td><p><span data-ttu-id="000d8-179">Não autenticar</span><span class="sxs-lookup"><span data-stu-id="000d8-179">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="000d8-180">Saída de Conferência A/V</span><span class="sxs-lookup"><span data-stu-id="000d8-180">A/V Conferencing Outbound</span></span></p></td>
<td><p><span data-ttu-id="000d8-181">Servidores Front-End</span><span class="sxs-lookup"><span data-stu-id="000d8-181">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="000d8-182">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="000d8-182">Any</span></span></p></td>
<td><p><span data-ttu-id="000d8-183">UDP e TCP</span><span class="sxs-lookup"><span data-stu-id="000d8-183">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="000d8-184">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="000d8-184">Any</span></span></p></td>
<td><p><span data-ttu-id="000d8-185">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="000d8-185">Any</span></span></p></td>
<td><p><span data-ttu-id="000d8-186">Não autenticar</span><span class="sxs-lookup"><span data-stu-id="000d8-186">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="000d8-187">Entrada do Exchange</span><span class="sxs-lookup"><span data-stu-id="000d8-187">Exchange Inbound</span></span></p></td>
<td><p><span data-ttu-id="000d8-188">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="000d8-188">Any</span></span></p></td>
<td><p><span data-ttu-id="000d8-189">Unificação de Mensagens do Exchange</span><span class="sxs-lookup"><span data-stu-id="000d8-189">Exchange Unified Messaging</span></span></p></td>
<td><p><span data-ttu-id="000d8-190">UDP e TCP</span><span class="sxs-lookup"><span data-stu-id="000d8-190">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="000d8-191">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="000d8-191">Any</span></span></p></td>
<td><p><span data-ttu-id="000d8-192">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="000d8-192">Any</span></span></p></td>
<td><p><span data-ttu-id="000d8-193">Não autenticar</span><span class="sxs-lookup"><span data-stu-id="000d8-193">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="000d8-194">Entrada dos Servidores de Compartilhamento de Aplicativo</span><span class="sxs-lookup"><span data-stu-id="000d8-194">Application Sharing Servers Inbound</span></span></p></td>
<td><p><span data-ttu-id="000d8-195">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="000d8-195">Any</span></span></p></td>
<td><p><span data-ttu-id="000d8-196">Servidores de Compartilhamento de Aplicativos</span><span class="sxs-lookup"><span data-stu-id="000d8-196">Application Sharing Servers</span></span></p></td>
<td><p><span data-ttu-id="000d8-197">TCP</span><span class="sxs-lookup"><span data-stu-id="000d8-197">TCP</span></span></p></td>
<td><p><span data-ttu-id="000d8-198">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="000d8-198">Any</span></span></p></td>
<td><p><span data-ttu-id="000d8-199">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="000d8-199">Any</span></span></p></td>
<td><p><span data-ttu-id="000d8-200">Não autenticar</span><span class="sxs-lookup"><span data-stu-id="000d8-200">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="000d8-201">Saída do Servidor de Compartilhamento de Aplicativos.</span><span class="sxs-lookup"><span data-stu-id="000d8-201">Application Sharing Server Outbound</span></span></p></td>
<td><p><span data-ttu-id="000d8-202">Servidores de Compartilhamento de Aplicativos</span><span class="sxs-lookup"><span data-stu-id="000d8-202">Application Sharing Servers</span></span></p></td>
<td><p><span data-ttu-id="000d8-203">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="000d8-203">Any</span></span></p></td>
<td><p><span data-ttu-id="000d8-204">TCP</span><span class="sxs-lookup"><span data-stu-id="000d8-204">TCP</span></span></p></td>
<td><p><span data-ttu-id="000d8-205">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="000d8-205">Any</span></span></p></td>
<td><p><span data-ttu-id="000d8-206">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="000d8-206">Any</span></span></p></td>
<td><p><span data-ttu-id="000d8-207">Não autenticar</span><span class="sxs-lookup"><span data-stu-id="000d8-207">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="000d8-208">Saída do Exchange</span><span class="sxs-lookup"><span data-stu-id="000d8-208">Exchange Outbound</span></span></p></td>
<td><p><span data-ttu-id="000d8-209">Unificação de Mensagens do Exchange</span><span class="sxs-lookup"><span data-stu-id="000d8-209">Exchange Unified Messaging</span></span></p></td>
<td><p><span data-ttu-id="000d8-210">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="000d8-210">Any</span></span></p></td>
<td><p><span data-ttu-id="000d8-211">UDP e TCP</span><span class="sxs-lookup"><span data-stu-id="000d8-211">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="000d8-212">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="000d8-212">Any</span></span></p></td>
<td><p><span data-ttu-id="000d8-213">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="000d8-213">Any</span></span></p></td>
<td><p><span data-ttu-id="000d8-214">Não autenticar</span><span class="sxs-lookup"><span data-stu-id="000d8-214">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="000d8-215">Clientes</span><span class="sxs-lookup"><span data-stu-id="000d8-215">Clients</span></span></p></td>
<td><p><span data-ttu-id="000d8-216">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="000d8-216">Any</span></span></p></td>
<td><p><span data-ttu-id="000d8-217">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="000d8-217">Any</span></span></p></td>
<td><p><span data-ttu-id="000d8-218">VIA</span><span class="sxs-lookup"><span data-stu-id="000d8-218">UDP</span></span></p></td>
<td><p><span data-ttu-id="000d8-219">Intervalo especificado de portas de mídia</span><span class="sxs-lookup"><span data-stu-id="000d8-219">Specified media port range</span></span></p></td>
<td><p><span data-ttu-id="000d8-220">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="000d8-220">Any</span></span></p></td>
<td><p><span data-ttu-id="000d8-221">Não autenticar</span><span class="sxs-lookup"><span data-stu-id="000d8-221">Do not authenticate</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

