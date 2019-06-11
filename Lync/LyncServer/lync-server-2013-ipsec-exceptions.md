---
title: Exceções IPsec do Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: IPsec exceptions
ms:assetid: 241f1eca-6f2f-44de-90b1-2cb659cbe27c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425719(v=OCS.15)
ms:contentKeyID: 48183627
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eae9061036c91793800fd744338347196d60494c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34828953"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="ipsec-exceptions-in-lync-server-2013"></a><span data-ttu-id="a0b96-102">Exceções de IPsec no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a0b96-102">IPsec exceptions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a0b96-103">_**Tópico da última modificação:** 2012-06-27_</span><span class="sxs-lookup"><span data-stu-id="a0b96-103">_**Topic Last Modified:** 2012-06-27_</span></span>

<span data-ttu-id="a0b96-104">Para redes corporativas onde a segurança do protocolo Internet (IPsec) (consulte IETF RFC 4301-4309) foi implantada, o IPsec deve ser desabilitado no intervalo de portas usado para a entrega de vídeo de áudio, vídeo e panorama.</span><span class="sxs-lookup"><span data-stu-id="a0b96-104">For enterprise networks where Internet Protocol security (IPsec) (see IETF RFC 4301-4309) has been deployed, IPsec must be disabled over the range of ports used for the delivery of audio, video, and panorama video.</span></span> <span data-ttu-id="a0b96-105">Essa recomendação existe porque é necessário evitar atrasos na alocação das portas de mídia por causa da negociação IPsec.</span><span class="sxs-lookup"><span data-stu-id="a0b96-105">The recommendation is motivated by the need to avoid any delay in the allocation of media ports due to IPsec negotiation.</span></span>

<span data-ttu-id="a0b96-106">A tabela a seguir explica as configurações de exceções recomendadas do IPsec.</span><span class="sxs-lookup"><span data-stu-id="a0b96-106">The following table explains the recommended IPsec exception settings.</span></span>

### <a name="recommended-ipsec-exceptions"></a><span data-ttu-id="a0b96-107">Exceções recomendadas do IPsec</span><span class="sxs-lookup"><span data-stu-id="a0b96-107">Recommended IPsec Exceptions</span></span>

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
<th><span data-ttu-id="a0b96-108">Nome da regra</span><span class="sxs-lookup"><span data-stu-id="a0b96-108">Rule name</span></span></th>
<th><span data-ttu-id="a0b96-109">IP de origem</span><span class="sxs-lookup"><span data-stu-id="a0b96-109">Source IP</span></span></th>
<th><span data-ttu-id="a0b96-110">IP de destino</span><span class="sxs-lookup"><span data-stu-id="a0b96-110">Destination IP</span></span></th>
<th><span data-ttu-id="a0b96-111">Protocolo</span><span class="sxs-lookup"><span data-stu-id="a0b96-111">Protocol</span></span></th>
<th><span data-ttu-id="a0b96-112">Porta de origem</span><span class="sxs-lookup"><span data-stu-id="a0b96-112">Source port</span></span></th>
<th><span data-ttu-id="a0b96-113">Porta de destino</span><span class="sxs-lookup"><span data-stu-id="a0b96-113">Destination port</span></span></th>
<th><span data-ttu-id="a0b96-114">Requisito de autenticação</span><span class="sxs-lookup"><span data-stu-id="a0b96-114">Authentication Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a0b96-115">Entrada interna do Servidor de Borda A/V</span><span class="sxs-lookup"><span data-stu-id="a0b96-115">A/V Edge Server Internal Inbound</span></span></p></td>
<td><p><span data-ttu-id="a0b96-116">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="a0b96-116">Any</span></span></p></td>
<td><p><span data-ttu-id="a0b96-117">Interno do Servidor de Borda A/V</span><span class="sxs-lookup"><span data-stu-id="a0b96-117">A/V Edge Server Internal</span></span></p></td>
<td><p><span data-ttu-id="a0b96-118">UDP e TCP</span><span class="sxs-lookup"><span data-stu-id="a0b96-118">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="a0b96-119">Qualquer um </span><span class="sxs-lookup"><span data-stu-id="a0b96-119">Any</span></span></p></td>
<td><p><span data-ttu-id="a0b96-120">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="a0b96-120">Any</span></span></p></td>
<td><p><span data-ttu-id="a0b96-121">Não autenticar</span><span class="sxs-lookup"><span data-stu-id="a0b96-121">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0b96-122">Entrada externa do Servidor de Borda A/V</span><span class="sxs-lookup"><span data-stu-id="a0b96-122">A/V Edge Server External Inbound</span></span></p></td>
<td><p><span data-ttu-id="a0b96-123">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="a0b96-123">Any</span></span></p></td>
<td><p><span data-ttu-id="a0b96-124">Externo do Servidor de Borda A/V</span><span class="sxs-lookup"><span data-stu-id="a0b96-124">A/V Edge Server External</span></span></p></td>
<td><p><span data-ttu-id="a0b96-125">UDP e TCP</span><span class="sxs-lookup"><span data-stu-id="a0b96-125">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="a0b96-126">Qualquer um </span><span class="sxs-lookup"><span data-stu-id="a0b96-126">Any</span></span></p></td>
<td><p><span data-ttu-id="a0b96-127">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="a0b96-127">Any</span></span></p></td>
<td><p><span data-ttu-id="a0b96-128">Não autenticar</span><span class="sxs-lookup"><span data-stu-id="a0b96-128">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a0b96-129">Saída interna do Servidor de Borda A/V</span><span class="sxs-lookup"><span data-stu-id="a0b96-129">A/V Edge Server Internal Outbound</span></span></p></td>
<td><p><span data-ttu-id="a0b96-130">Interno do Servidor de Borda A/V</span><span class="sxs-lookup"><span data-stu-id="a0b96-130">A/V Edge Server Internal</span></span></p></td>
<td><p><span data-ttu-id="a0b96-131">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="a0b96-131">Any</span></span></p></td>
<td><p><span data-ttu-id="a0b96-132">UDP &amp; TCP</span><span class="sxs-lookup"><span data-stu-id="a0b96-132">UDP &amp; TCP</span></span></p></td>
<td><p><span data-ttu-id="a0b96-133">Qualquer um </span><span class="sxs-lookup"><span data-stu-id="a0b96-133">Any</span></span></p></td>
<td><p><span data-ttu-id="a0b96-134">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="a0b96-134">Any</span></span></p></td>
<td><p><span data-ttu-id="a0b96-135">Não autenticar</span><span class="sxs-lookup"><span data-stu-id="a0b96-135">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0b96-136">Saída externa do Servidor de Borda A/V</span><span class="sxs-lookup"><span data-stu-id="a0b96-136">A/V Edge Server External Outbound</span></span></p></td>
<td><p><span data-ttu-id="a0b96-137">Externo do Servidor de Borda A/V</span><span class="sxs-lookup"><span data-stu-id="a0b96-137">A/V Edge Server External</span></span></p></td>
<td><p><span data-ttu-id="a0b96-138">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="a0b96-138">Any</span></span></p></td>
<td><p><span data-ttu-id="a0b96-139">UDP e TCP</span><span class="sxs-lookup"><span data-stu-id="a0b96-139">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="a0b96-140">Qualquer um </span><span class="sxs-lookup"><span data-stu-id="a0b96-140">Any</span></span></p></td>
<td><p><span data-ttu-id="a0b96-141">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="a0b96-141">Any</span></span></p></td>
<td><p><span data-ttu-id="a0b96-142">Não autenticar</span><span class="sxs-lookup"><span data-stu-id="a0b96-142">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a0b96-143">Entrada do Servidor de Mediação</span><span class="sxs-lookup"><span data-stu-id="a0b96-143">Mediation Server Inbound</span></span></p></td>
<td><p><span data-ttu-id="a0b96-144">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="a0b96-144">Any</span></span></p></td>
<td><p><span data-ttu-id="a0b96-145">Mediação</span><span class="sxs-lookup"><span data-stu-id="a0b96-145">Mediation</span></span></p>
<p><span data-ttu-id="a0b96-146">Servidor(es)</span><span class="sxs-lookup"><span data-stu-id="a0b96-146">Server(s)</span></span></p></td>
<td><p><span data-ttu-id="a0b96-147">UDP e TCP</span><span class="sxs-lookup"><span data-stu-id="a0b96-147">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="a0b96-148">Qualquer um </span><span class="sxs-lookup"><span data-stu-id="a0b96-148">Any</span></span></p></td>
<td><p><span data-ttu-id="a0b96-149">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="a0b96-149">Any</span></span></p></td>
<td><p><span data-ttu-id="a0b96-150">Não autenticar</span><span class="sxs-lookup"><span data-stu-id="a0b96-150">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0b96-151">Saída do Servidor de Mediação</span><span class="sxs-lookup"><span data-stu-id="a0b96-151">Mediation Server Outbound</span></span></p></td>
<td><p><span data-ttu-id="a0b96-152">Mediação</span><span class="sxs-lookup"><span data-stu-id="a0b96-152">Mediation</span></span></p>
<p><span data-ttu-id="a0b96-153">Servidor(es)</span><span class="sxs-lookup"><span data-stu-id="a0b96-153">Server(s)</span></span></p></td>
<td><p><span data-ttu-id="a0b96-154">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="a0b96-154">Any</span></span></p></td>
<td><p><span data-ttu-id="a0b96-155">UDP e TCP</span><span class="sxs-lookup"><span data-stu-id="a0b96-155">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="a0b96-156">Qualquer um </span><span class="sxs-lookup"><span data-stu-id="a0b96-156">Any</span></span></p></td>
<td><p><span data-ttu-id="a0b96-157">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="a0b96-157">Any</span></span></p></td>
<td><p><span data-ttu-id="a0b96-158">Não autenticar</span><span class="sxs-lookup"><span data-stu-id="a0b96-158">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a0b96-159">Entrada do Atendedor de Conferência</span><span class="sxs-lookup"><span data-stu-id="a0b96-159">Conferencing Attendant Inbound</span></span></p></td>
<td><p><span data-ttu-id="a0b96-160">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="a0b96-160">Any</span></span></p></td>
<td><p><span data-ttu-id="a0b96-161">Servidor Front-End executando o Atendedor de Conferência</span><span class="sxs-lookup"><span data-stu-id="a0b96-161">Front End Server running Conferencing Attendant</span></span></p></td>
<td><p><span data-ttu-id="a0b96-162">UDP e TCP</span><span class="sxs-lookup"><span data-stu-id="a0b96-162">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="a0b96-163">Qualquer um </span><span class="sxs-lookup"><span data-stu-id="a0b96-163">Any</span></span></p></td>
<td><p><span data-ttu-id="a0b96-164">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="a0b96-164">Any</span></span></p></td>
<td><p><span data-ttu-id="a0b96-165">Não autenticar</span><span class="sxs-lookup"><span data-stu-id="a0b96-165">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0b96-166">Saída do Atendedor de Conferência</span><span class="sxs-lookup"><span data-stu-id="a0b96-166">Conferencing Attendant Outbound</span></span></p></td>
<td><p><span data-ttu-id="a0b96-167">Servidor Front-End executando o Atendedor de Conferência</span><span class="sxs-lookup"><span data-stu-id="a0b96-167">Front End Server running Conferencing Attendant</span></span></p></td>
<td><p><span data-ttu-id="a0b96-168">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="a0b96-168">Any</span></span></p></td>
<td><p><span data-ttu-id="a0b96-169">UDP e TCP</span><span class="sxs-lookup"><span data-stu-id="a0b96-169">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="a0b96-170">Qualquer um </span><span class="sxs-lookup"><span data-stu-id="a0b96-170">Any</span></span></p></td>
<td><p><span data-ttu-id="a0b96-171">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="a0b96-171">Any</span></span></p></td>
<td><p><span data-ttu-id="a0b96-172">Não autenticar</span><span class="sxs-lookup"><span data-stu-id="a0b96-172">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a0b96-173">Entrada de Conferência A/V</span><span class="sxs-lookup"><span data-stu-id="a0b96-173">A/V Conferencing Inbound</span></span></p></td>
<td><p><span data-ttu-id="a0b96-174">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="a0b96-174">Any</span></span></p></td>
<td><p><span data-ttu-id="a0b96-175">Servidores Front-End</span><span class="sxs-lookup"><span data-stu-id="a0b96-175">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="a0b96-176">UDP e TCP</span><span class="sxs-lookup"><span data-stu-id="a0b96-176">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="a0b96-177">Qualquer um </span><span class="sxs-lookup"><span data-stu-id="a0b96-177">Any</span></span></p></td>
<td><p><span data-ttu-id="a0b96-178">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="a0b96-178">Any</span></span></p></td>
<td><p><span data-ttu-id="a0b96-179">Não autenticar</span><span class="sxs-lookup"><span data-stu-id="a0b96-179">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0b96-180">Saída de Conferência A/V</span><span class="sxs-lookup"><span data-stu-id="a0b96-180">A/V Conferencing Outbound</span></span></p></td>
<td><p><span data-ttu-id="a0b96-181">Servidores Front-End</span><span class="sxs-lookup"><span data-stu-id="a0b96-181">Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="a0b96-182">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="a0b96-182">Any</span></span></p></td>
<td><p><span data-ttu-id="a0b96-183">UDP e TCP</span><span class="sxs-lookup"><span data-stu-id="a0b96-183">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="a0b96-184">Qualquer um </span><span class="sxs-lookup"><span data-stu-id="a0b96-184">Any</span></span></p></td>
<td><p><span data-ttu-id="a0b96-185">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="a0b96-185">Any</span></span></p></td>
<td><p><span data-ttu-id="a0b96-186">Não autenticar</span><span class="sxs-lookup"><span data-stu-id="a0b96-186">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a0b96-187">Entrada do Exchange</span><span class="sxs-lookup"><span data-stu-id="a0b96-187">Exchange Inbound</span></span></p></td>
<td><p><span data-ttu-id="a0b96-188">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="a0b96-188">Any</span></span></p></td>
<td><p><span data-ttu-id="a0b96-189">Unificação de Mensagens do Exchange</span><span class="sxs-lookup"><span data-stu-id="a0b96-189">Exchange Unified Messaging</span></span></p></td>
<td><p><span data-ttu-id="a0b96-190">UDP e TCP</span><span class="sxs-lookup"><span data-stu-id="a0b96-190">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="a0b96-191">Qualquer um </span><span class="sxs-lookup"><span data-stu-id="a0b96-191">Any</span></span></p></td>
<td><p><span data-ttu-id="a0b96-192">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="a0b96-192">Any</span></span></p></td>
<td><p><span data-ttu-id="a0b96-193">Não autenticar</span><span class="sxs-lookup"><span data-stu-id="a0b96-193">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0b96-194">Entrada dos Servidores de Compartilhamento de Aplicativo</span><span class="sxs-lookup"><span data-stu-id="a0b96-194">Application Sharing Servers Inbound</span></span></p></td>
<td><p><span data-ttu-id="a0b96-195">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="a0b96-195">Any</span></span></p></td>
<td><p><span data-ttu-id="a0b96-196">Servidores de Compartilhamento de Aplicativos</span><span class="sxs-lookup"><span data-stu-id="a0b96-196">Application Sharing Servers</span></span></p></td>
<td><p><span data-ttu-id="a0b96-197">TCP</span><span class="sxs-lookup"><span data-stu-id="a0b96-197">TCP</span></span></p></td>
<td><p><span data-ttu-id="a0b96-198">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="a0b96-198">Any</span></span></p></td>
<td><p><span data-ttu-id="a0b96-199">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="a0b96-199">Any</span></span></p></td>
<td><p><span data-ttu-id="a0b96-200">Não autenticar</span><span class="sxs-lookup"><span data-stu-id="a0b96-200">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a0b96-201">Saída do Servidor de Compartilhamento de Aplicativos</span><span class="sxs-lookup"><span data-stu-id="a0b96-201">Application Sharing Server Outbound</span></span></p></td>
<td><p><span data-ttu-id="a0b96-202">Servidores de Compartilhamento de Aplicativos</span><span class="sxs-lookup"><span data-stu-id="a0b96-202">Application Sharing Servers</span></span></p></td>
<td><p><span data-ttu-id="a0b96-203">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="a0b96-203">Any</span></span></p></td>
<td><p><span data-ttu-id="a0b96-204">TCP</span><span class="sxs-lookup"><span data-stu-id="a0b96-204">TCP</span></span></p></td>
<td><p><span data-ttu-id="a0b96-205">Qualquer um </span><span class="sxs-lookup"><span data-stu-id="a0b96-205">Any</span></span></p></td>
<td><p><span data-ttu-id="a0b96-206">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="a0b96-206">Any</span></span></p></td>
<td><p><span data-ttu-id="a0b96-207">Não autenticar</span><span class="sxs-lookup"><span data-stu-id="a0b96-207">Do not authenticate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0b96-208">Saída do Exchange</span><span class="sxs-lookup"><span data-stu-id="a0b96-208">Exchange Outbound</span></span></p></td>
<td><p><span data-ttu-id="a0b96-209">Unificação de Mensagens do Exchange</span><span class="sxs-lookup"><span data-stu-id="a0b96-209">Exchange Unified Messaging</span></span></p></td>
<td><p><span data-ttu-id="a0b96-210">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="a0b96-210">Any</span></span></p></td>
<td><p><span data-ttu-id="a0b96-211">UDP e TCP</span><span class="sxs-lookup"><span data-stu-id="a0b96-211">UDP and TCP</span></span></p></td>
<td><p><span data-ttu-id="a0b96-212">Qualquer um </span><span class="sxs-lookup"><span data-stu-id="a0b96-212">Any</span></span></p></td>
<td><p><span data-ttu-id="a0b96-213">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="a0b96-213">Any</span></span></p></td>
<td><p><span data-ttu-id="a0b96-214">Não autenticar</span><span class="sxs-lookup"><span data-stu-id="a0b96-214">Do not authenticate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a0b96-215">Clientes</span><span class="sxs-lookup"><span data-stu-id="a0b96-215">Clients</span></span></p></td>
<td><p><span data-ttu-id="a0b96-216">Qualquer um </span><span class="sxs-lookup"><span data-stu-id="a0b96-216">Any</span></span></p></td>
<td><p><span data-ttu-id="a0b96-217">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="a0b96-217">Any</span></span></p></td>
<td><p><span data-ttu-id="a0b96-218">UDP</span><span class="sxs-lookup"><span data-stu-id="a0b96-218">UDP</span></span></p></td>
<td><p><span data-ttu-id="a0b96-219">Intervalo especificado de portas de mídia</span><span class="sxs-lookup"><span data-stu-id="a0b96-219">Specified media port range</span></span></p></td>
<td><p><span data-ttu-id="a0b96-220">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="a0b96-220">Any</span></span></p></td>
<td><p><span data-ttu-id="a0b96-221">Não autenticar</span><span class="sxs-lookup"><span data-stu-id="a0b96-221">Do not authenticate</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

