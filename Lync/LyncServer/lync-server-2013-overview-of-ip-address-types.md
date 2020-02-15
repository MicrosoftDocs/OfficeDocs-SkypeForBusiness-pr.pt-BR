---
title: 'Lync Server 2013: visão geral dos tipos de endereço IP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of IP address types for Lync Server
ms:assetid: ee9a695f-5cf5-441e-94fb-6adeca50e8d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205363(v=OCS.15)
ms:contentKeyID: 48185759
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: feb900c6f3d2ac426c184048986a7a751a205874
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051043"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-ip-address-types-for-lync-server-2013"></a><span data-ttu-id="5b37d-102">Visão geral dos tipos de endereço IP para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5b37d-102">Overview of IP address types for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5b37d-103">_**Última modificação do tópico:** 2013-01-29_</span><span class="sxs-lookup"><span data-stu-id="5b37d-103">_**Topic Last Modified:** 2013-01-29_</span></span>

<span data-ttu-id="5b37d-104">Você tem três opções ao configurar endereços IP no Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5b37d-104">You have three options when configuring IP addresses in Lync Server 2013.</span></span> <span data-ttu-id="5b37d-105">Você pode configurar o Lync Server 2013 para oferecer suporte somente a IP versão 4 (IPv4), somente o IP versão 6 (IPv6) ou uma combinação dos dois (conhecido como *pilha Dual*).</span><span class="sxs-lookup"><span data-stu-id="5b37d-105">You can configure Lync Server 2013 to support only IP version 4 (IPv4), only IP version 6 (IPv6), or a combination of both (known as a *dual stack*).</span></span> <span data-ttu-id="5b37d-106">Há vários problemas que devem ser considerados em cada tipo de configuração:</span><span class="sxs-lookup"><span data-stu-id="5b37d-106">There are several issues to consider with each type of configuration:</span></span>

  - <span data-ttu-id="5b37d-107">\*\*\*\*   O IPv6 somente IPv4 foi criado porque o mundo está ficando sem endereços IPv4.</span><span class="sxs-lookup"><span data-stu-id="5b37d-107">**IPv4 only**   IPv6 was created because the world is running out of IPv4 addresses.</span></span> <span data-ttu-id="5b37d-108">Por fim, o IPv6 será totalmente suportado em todo o mundo, mas, neste momento, muitas empresas e dispositivos que sua empresa talvez precisem se comunicar com o não dão suporte a IPv6, e talvez não haja algum tempo.</span><span class="sxs-lookup"><span data-stu-id="5b37d-108">Ultimately, IPv6 will be fully supported worldwide, but at this time, many companies and devices that your enterprise might need to communicate with do not yet support IPv6, and may not for some time.</span></span> <span data-ttu-id="5b37d-109">Uma configuração somente IPv4 ajudará a garantir que sua implementação do Lync Server possa se comunicar com a maioria dos dispositivos existentes.</span><span class="sxs-lookup"><span data-stu-id="5b37d-109">An IPv4-only configuration will help to ensure that your Lync Server implementation can communicate with most existing devices.</span></span>

  - <span data-ttu-id="5b37d-110">**Somente IPv6 por**   outro lado, uma implementação IPv6 completa, neste momento, excluirá a comunicação com vários dispositivos existentes.</span><span class="sxs-lookup"><span data-stu-id="5b37d-110">**IPv6 only**   Conversely, a full IPv6 implementation, at this time, will exclude communication with many existing devices.</span></span>

  - <span data-ttu-id="5b37d-111">\*\*\*\*   Pilha dual de pilha dupla é uma rede onde endereços IPv4 e IPv6 estão habilitados.</span><span class="sxs-lookup"><span data-stu-id="5b37d-111">**Dual Stack**   Dual stack is a network where both IPv4 and IPv6 addresses are enabled.</span></span> <span data-ttu-id="5b37d-112">Essa configuração é suportada no Lync Server 2013 porque, na maioria dos casos, a transição de IPv4 para pleno IPv6 levará vários anos.</span><span class="sxs-lookup"><span data-stu-id="5b37d-112">This configuration is supported in Lync Server 2013 because in most cases the transition from full-IPv4 to full-IPv6 will take several years.</span></span>

<span data-ttu-id="5b37d-113">As seções a seguir descrevem a compatibilidade entre essas três configurações para vários recursos do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5b37d-113">The following sections outline the compatibility among these three configurations for various Lync Server features.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5b37d-114">A configuração de cliente ou servidor com IPv6 só é suportada para fins de laboratório ou validação.</span><span class="sxs-lookup"><span data-stu-id="5b37d-114">Client or server configuration with IPv6 only is supported only for lab or validation purposes.</span></span> <span data-ttu-id="5b37d-115">A configuração IPv6 somente não é suportada na implantação de produção.</span><span class="sxs-lookup"><span data-stu-id="5b37d-115">IPv6 only configuration is not supported in the production deployment.</span></span>



</div>

<div>

## <a name="client-registration"></a><span data-ttu-id="5b37d-116">Registro de cliente</span><span class="sxs-lookup"><span data-stu-id="5b37d-116">Client Registration</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5b37d-117">Rede de ponto de extremidade do cliente</span><span class="sxs-lookup"><span data-stu-id="5b37d-117">Client endpoint network</span></span></th>
<th><span data-ttu-id="5b37d-118">Rede de servidor</span><span class="sxs-lookup"><span data-stu-id="5b37d-118">Server network</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5b37d-119">IPv4</span><span class="sxs-lookup"><span data-stu-id="5b37d-119">IPv4</span></span></p></td>
<td><p><span data-ttu-id="5b37d-120">IPv4</span><span class="sxs-lookup"><span data-stu-id="5b37d-120">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5b37d-121">IPv4</span><span class="sxs-lookup"><span data-stu-id="5b37d-121">IPv4</span></span></p></td>
<td><p><span data-ttu-id="5b37d-122">Pilha dual</span><span class="sxs-lookup"><span data-stu-id="5b37d-122">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5b37d-123">Pilha dual</span><span class="sxs-lookup"><span data-stu-id="5b37d-123">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="5b37d-124">IPv4</span><span class="sxs-lookup"><span data-stu-id="5b37d-124">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5b37d-125">Pilha dual</span><span class="sxs-lookup"><span data-stu-id="5b37d-125">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="5b37d-126">Pilha dual</span><span class="sxs-lookup"><span data-stu-id="5b37d-126">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5b37d-127">Pilha dual</span><span class="sxs-lookup"><span data-stu-id="5b37d-127">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="5b37d-128">IPv6</span><span class="sxs-lookup"><span data-stu-id="5b37d-128">IPv6</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5b37d-129">IPv6</span><span class="sxs-lookup"><span data-stu-id="5b37d-129">IPv6</span></span></p></td>
<td><p><span data-ttu-id="5b37d-130">Pilha dual</span><span class="sxs-lookup"><span data-stu-id="5b37d-130">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5b37d-131">IPv6</span><span class="sxs-lookup"><span data-stu-id="5b37d-131">IPv6</span></span></p></td>
<td><p><span data-ttu-id="5b37d-132">IPv6</span><span class="sxs-lookup"><span data-stu-id="5b37d-132">IPv6</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="peer-to-peer-client"></a><span data-ttu-id="5b37d-133">Cliente ponto a ponto</span><span class="sxs-lookup"><span data-stu-id="5b37d-133">Peer-to-Peer Client</span></span>

<span data-ttu-id="5b37d-134">As comunicações ponto a ponto incluem áudio, áudio/vídeo, compartilhamento de aplicativos e transferência de arquivos.</span><span class="sxs-lookup"><span data-stu-id="5b37d-134">Peer-to-peer communications include audio, audio/video, application sharing, and file transfer.</span></span> <span data-ttu-id="5b37d-135">Após os dois clientes terem sido registrados com êxito, as combinações a seguir são suportadas.</span><span class="sxs-lookup"><span data-stu-id="5b37d-135">After both clients have successfully registered, the following combinations are supported.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5b37d-136">Ponto de extremidade de cliente 1</span><span class="sxs-lookup"><span data-stu-id="5b37d-136">Client endpoint 1</span></span></th>
<th><span data-ttu-id="5b37d-137">Ponto de extremidade 2 do cliente</span><span class="sxs-lookup"><span data-stu-id="5b37d-137">Client endpoint 2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5b37d-138">IPv4</span><span class="sxs-lookup"><span data-stu-id="5b37d-138">IPv4</span></span></p></td>
<td><p><span data-ttu-id="5b37d-139">IPv4</span><span class="sxs-lookup"><span data-stu-id="5b37d-139">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5b37d-140">IPv4</span><span class="sxs-lookup"><span data-stu-id="5b37d-140">IPv4</span></span></p></td>
<td><p><span data-ttu-id="5b37d-141">Pilha dual</span><span class="sxs-lookup"><span data-stu-id="5b37d-141">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5b37d-142">Pilha dual</span><span class="sxs-lookup"><span data-stu-id="5b37d-142">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="5b37d-143">Pilha dual</span><span class="sxs-lookup"><span data-stu-id="5b37d-143">Dual stack</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5b37d-144">IPv6</span><span class="sxs-lookup"><span data-stu-id="5b37d-144">IPv6</span></span></p></td>
<td><p><span data-ttu-id="5b37d-145">Pilha dual</span><span class="sxs-lookup"><span data-stu-id="5b37d-145">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5b37d-146">IPv6</span><span class="sxs-lookup"><span data-stu-id="5b37d-146">IPv6</span></span></p></td>
<td><p><span data-ttu-id="5b37d-147">IPv6</span><span class="sxs-lookup"><span data-stu-id="5b37d-147">IPv6</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="conferencing"></a><span data-ttu-id="5b37d-148">Conferências</span><span class="sxs-lookup"><span data-stu-id="5b37d-148">Conferencing</span></span>

<span data-ttu-id="5b37d-149">A conferência inclui áudio/vídeo, compartilhamento de aplicativos e colaboração de dados (quadro de comunicações e compartilhamento de arquivos).</span><span class="sxs-lookup"><span data-stu-id="5b37d-149">Conferencing includes audio/video, application sharing, and data collaboration (whiteboarding and file sharing).</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5b37d-150">Rede de ponto de extremidade do cliente</span><span class="sxs-lookup"><span data-stu-id="5b37d-150">Client endpoint network</span></span></th>
<th><span data-ttu-id="5b37d-151">Rede de servidor</span><span class="sxs-lookup"><span data-stu-id="5b37d-151">Server network</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5b37d-152">IPv4</span><span class="sxs-lookup"><span data-stu-id="5b37d-152">IPv4</span></span></p></td>
<td><p><span data-ttu-id="5b37d-153">IPv4</span><span class="sxs-lookup"><span data-stu-id="5b37d-153">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5b37d-154">IPv4</span><span class="sxs-lookup"><span data-stu-id="5b37d-154">IPv4</span></span></p></td>
<td><p><span data-ttu-id="5b37d-155">Pilha dual</span><span class="sxs-lookup"><span data-stu-id="5b37d-155">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5b37d-156">Pilha dual</span><span class="sxs-lookup"><span data-stu-id="5b37d-156">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="5b37d-157">IPv4</span><span class="sxs-lookup"><span data-stu-id="5b37d-157">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5b37d-158">Pilha dual</span><span class="sxs-lookup"><span data-stu-id="5b37d-158">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="5b37d-159">Pilha dual</span><span class="sxs-lookup"><span data-stu-id="5b37d-159">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5b37d-160">Pilha dual</span><span class="sxs-lookup"><span data-stu-id="5b37d-160">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="5b37d-161">IPv6</span><span class="sxs-lookup"><span data-stu-id="5b37d-161">IPv6</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5b37d-162">IPv6</span><span class="sxs-lookup"><span data-stu-id="5b37d-162">IPv6</span></span></p></td>
<td><p><span data-ttu-id="5b37d-163">Pilha dual</span><span class="sxs-lookup"><span data-stu-id="5b37d-163">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5b37d-164">IPv6</span><span class="sxs-lookup"><span data-stu-id="5b37d-164">IPv6</span></span></p></td>
<td><p><span data-ttu-id="5b37d-165">IPv6</span><span class="sxs-lookup"><span data-stu-id="5b37d-165">IPv6</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="mediation-serverpstn"></a><span data-ttu-id="5b37d-166">Servidor de mediação/PSTN</span><span class="sxs-lookup"><span data-stu-id="5b37d-166">Mediation Server/PSTN</span></span>

<span data-ttu-id="5b37d-167">O Lync Server 2013 não é compatível com bypass de mídia para chamadas PSTN (rede telefônica pública comutada) se o tráfego estiver por meio de uma interface IPv6.</span><span class="sxs-lookup"><span data-stu-id="5b37d-167">Lync Server 2013 does not support media bypass for public switched telephone network (PSTN) calls if the traffic is through an IPv6 interface.</span></span> <span data-ttu-id="5b37d-168">Se o bypass de mídia for necessário, recomendamos que o gateway PSTN esteja configurado como IPv4.</span><span class="sxs-lookup"><span data-stu-id="5b37d-168">If media bypass is required, we recommend that the PSTN gateway is configured to IPv4.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5b37d-169">Interface principal \*</span><span class="sxs-lookup"><span data-stu-id="5b37d-169">Primary interface\*</span></span></th>
<th><span data-ttu-id="5b37d-170">Interface PSTN (no servidor de mediação)</span><span class="sxs-lookup"><span data-stu-id="5b37d-170">PSTN interface (on Mediation Server)</span></span></th>
<th><span data-ttu-id="5b37d-171">Configuração de gateway PSTN</span><span class="sxs-lookup"><span data-stu-id="5b37d-171">PSTN gateway setting</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5b37d-172">IPv4</span><span class="sxs-lookup"><span data-stu-id="5b37d-172">IPv4</span></span></p></td>
<td><p><span data-ttu-id="5b37d-173">Pilha dual</span><span class="sxs-lookup"><span data-stu-id="5b37d-173">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="5b37d-174">IPv4</span><span class="sxs-lookup"><span data-stu-id="5b37d-174">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5b37d-175">Pilha dual</span><span class="sxs-lookup"><span data-stu-id="5b37d-175">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="5b37d-176">Pilha dual</span><span class="sxs-lookup"><span data-stu-id="5b37d-176">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="5b37d-177">IPv4</span><span class="sxs-lookup"><span data-stu-id="5b37d-177">IPv4</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5b37d-178">Pilha dual</span><span class="sxs-lookup"><span data-stu-id="5b37d-178">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="5b37d-179">Pilha dual</span><span class="sxs-lookup"><span data-stu-id="5b37d-179">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="5b37d-180">IPv6</span><span class="sxs-lookup"><span data-stu-id="5b37d-180">IPv6</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="5b37d-181">\*A interface principal é a interface que se comunica com os componentes do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5b37d-181">\* The primary interface is the interface that communicates with the Lync Server components.</span></span>

</div>

<div>

## <a name="remote-user-peer-to-peer-communications"></a><span data-ttu-id="5b37d-182">Comunicações ponto a ponto de usuário remoto</span><span class="sxs-lookup"><span data-stu-id="5b37d-182">Remote User Peer-to-Peer Communications</span></span>

<span data-ttu-id="5b37d-183">Comunicações ponto a ponto com usuários remotos incluem mensagens instantâneas, áudio/vídeo, compartilhamento de aplicativos e transferência de arquivos.</span><span class="sxs-lookup"><span data-stu-id="5b37d-183">Peer-to-peer communications with remote users include instant messaging, audio/video, application sharing, and file transfer.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5b37d-184">Rede de usuário remoto</span><span class="sxs-lookup"><span data-stu-id="5b37d-184">Remote user network</span></span></th>
<th><span data-ttu-id="5b37d-185">Servidor de borda (borda externa)</span><span class="sxs-lookup"><span data-stu-id="5b37d-185">Edge server (External edge)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5b37d-186">IPv4</span><span class="sxs-lookup"><span data-stu-id="5b37d-186">IPv4</span></span></p></td>
<td><p><span data-ttu-id="5b37d-187">IPv4</span><span class="sxs-lookup"><span data-stu-id="5b37d-187">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5b37d-188">Pilha dual</span><span class="sxs-lookup"><span data-stu-id="5b37d-188">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="5b37d-189">IPv4</span><span class="sxs-lookup"><span data-stu-id="5b37d-189">IPv4</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5b37d-190">Pilha dual</span><span class="sxs-lookup"><span data-stu-id="5b37d-190">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="5b37d-191">Pilha dual</span><span class="sxs-lookup"><span data-stu-id="5b37d-191">Dual stack</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5b37d-192">IPv6</span><span class="sxs-lookup"><span data-stu-id="5b37d-192">IPv6</span></span></p></td>
<td><p><span data-ttu-id="5b37d-193">Pilha dual</span><span class="sxs-lookup"><span data-stu-id="5b37d-193">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5b37d-194">IPv6</span><span class="sxs-lookup"><span data-stu-id="5b37d-194">IPv6</span></span></p></td>
<td><p><span data-ttu-id="5b37d-195">IPv6</span><span class="sxs-lookup"><span data-stu-id="5b37d-195">IPv6</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="front-end-pool-and-edge-pool-configuration"></a><span data-ttu-id="5b37d-196">Configuração do pool de front-ends e do pool de borda</span><span class="sxs-lookup"><span data-stu-id="5b37d-196">Front End Pool and Edge Pool Configuration</span></span>

<span data-ttu-id="5b37d-197">A tabela a seguir mostra a matriz de suporte entre o pool do servidor front-end e o pool do servidor de borda interno.</span><span class="sxs-lookup"><span data-stu-id="5b37d-197">The following table shows the support matrix between the Front End Server pool and the internal Edge Server pool.</span></span>

### <a name="front-end-pool-and-edge-pool-internal-edge-matrix"></a><span data-ttu-id="5b37d-198">Matriz do pool de front-ends e do pool de borda (borda interna)</span><span class="sxs-lookup"><span data-stu-id="5b37d-198">Front End Pool and Edge Pool (Internal Edge) Matrix</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<tbody>
<tr class="odd">
<td></td>
<td><p><span data-ttu-id="5b37d-199"><strong>Pool de borda: IPv4</strong></span><span class="sxs-lookup"><span data-stu-id="5b37d-199"><strong>Edge Pool: IPv4</strong></span></span></p></td>
<td><p><span data-ttu-id="5b37d-200"><strong>Pool de borda: pilha dupla</strong></span><span class="sxs-lookup"><span data-stu-id="5b37d-200"><strong>Edge Pool: Dual Stack</strong></span></span></p></td>
<td><p><span data-ttu-id="5b37d-201"><strong>Pool de borda: IPv6</strong></span><span class="sxs-lookup"><span data-stu-id="5b37d-201"><strong>Edge Pool: IPv6</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5b37d-202"><strong>Pool de front-ends: IPv4</strong></span><span class="sxs-lookup"><span data-stu-id="5b37d-202"><strong>Front End Pool: IPv4</strong></span></span></p></td>
<td><p><span data-ttu-id="5b37d-203">Sim</span><span class="sxs-lookup"><span data-stu-id="5b37d-203">Yes</span></span></p></td>
<td><p><span data-ttu-id="5b37d-204">Sim</span><span class="sxs-lookup"><span data-stu-id="5b37d-204">Yes</span></span></p></td>
<td><p><span data-ttu-id="5b37d-205">Não</span><span class="sxs-lookup"><span data-stu-id="5b37d-205">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5b37d-206"><strong>Pool de front-ends: pilha dual</strong></span><span class="sxs-lookup"><span data-stu-id="5b37d-206"><strong>Front End Pool: Dual Stack</strong></span></span></p></td>
<td><p><span data-ttu-id="5b37d-207">Sim</span><span class="sxs-lookup"><span data-stu-id="5b37d-207">Yes</span></span></p></td>
<td><p><span data-ttu-id="5b37d-208">Sim</span><span class="sxs-lookup"><span data-stu-id="5b37d-208">Yes</span></span></p></td>
<td><p><span data-ttu-id="5b37d-209">Não</span><span class="sxs-lookup"><span data-stu-id="5b37d-209">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5b37d-210"><strong>Pool de front-ends: IPv6</strong></span><span class="sxs-lookup"><span data-stu-id="5b37d-210"><strong>Front End Pool: IPv6</strong></span></span></p></td>
<td><p><span data-ttu-id="5b37d-211">Não</span><span class="sxs-lookup"><span data-stu-id="5b37d-211">No</span></span></p></td>
<td><p><span data-ttu-id="5b37d-212">Não</span><span class="sxs-lookup"><span data-stu-id="5b37d-212">No</span></span></p></td>
<td><p><span data-ttu-id="5b37d-213">Sim</span><span class="sxs-lookup"><span data-stu-id="5b37d-213">Yes\*</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="5b37d-214">\*Use essa combinação somente em um ambiente de laboratório.</span><span class="sxs-lookup"><span data-stu-id="5b37d-214">\* Use this combination only in a lab environment.</span></span>

<span data-ttu-id="5b37d-215">A tabela a seguir é uma matriz das combinações suportadas de interfaces de borda internas e externas.</span><span class="sxs-lookup"><span data-stu-id="5b37d-215">The following table is a matrix of the supported combinations of internal and external edge interfaces.</span></span>

### <a name="edge-pool-internal-edge-and-edge-pool-external-edge-matrix"></a><span data-ttu-id="5b37d-216">Matriz do pool de borda (borda interna) e do pool de borda (borda externa)</span><span class="sxs-lookup"><span data-stu-id="5b37d-216">Edge Pool (Internal Edge) and Edge pool (External Edge) Matrix</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<tbody>
<tr class="odd">
<td></td>
<td><p><span data-ttu-id="5b37d-217"><strong>Pool de borda (borda externa): IPv4</strong></span><span class="sxs-lookup"><span data-stu-id="5b37d-217"><strong>Edge Pool (External Edge) : IPv4</strong></span></span></p></td>
<td><p><span data-ttu-id="5b37d-218"><strong>Pool de borda (borda externa): pilha dupla</strong></span><span class="sxs-lookup"><span data-stu-id="5b37d-218"><strong>Edge Pool (External Edge): Dual Stack</strong></span></span></p></td>
<td><p><span data-ttu-id="5b37d-219"><strong>Pool de borda (borda externa): IPv6</strong></span><span class="sxs-lookup"><span data-stu-id="5b37d-219"><strong>Edge Pool (External Edge): IPv6</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5b37d-220"><strong>Pool de borda (borda interna): IPv4</strong></span><span class="sxs-lookup"><span data-stu-id="5b37d-220"><strong>Edge Pool (Internal Edge): IPv4</strong></span></span></p></td>
<td><p><span data-ttu-id="5b37d-221">Sim</span><span class="sxs-lookup"><span data-stu-id="5b37d-221">Yes</span></span></p></td>
<td><p><span data-ttu-id="5b37d-222">Sim</span><span class="sxs-lookup"><span data-stu-id="5b37d-222">Yes</span></span></p></td>
<td><p><span data-ttu-id="5b37d-223">Não</span><span class="sxs-lookup"><span data-stu-id="5b37d-223">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5b37d-224"><strong>Pool de borda (borda interna): pilha dupla</strong></span><span class="sxs-lookup"><span data-stu-id="5b37d-224"><strong>Edge Pool (Internal Edge): Dual Stack</strong></span></span></p></td>
<td><p><span data-ttu-id="5b37d-225">Não</span><span class="sxs-lookup"><span data-stu-id="5b37d-225">No</span></span></p></td>
<td><p><span data-ttu-id="5b37d-226">Sim</span><span class="sxs-lookup"><span data-stu-id="5b37d-226">Yes</span></span></p></td>
<td><p><span data-ttu-id="5b37d-227">Não</span><span class="sxs-lookup"><span data-stu-id="5b37d-227">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5b37d-228"><strong>Pool de borda (borda interna): IPv6</strong></span><span class="sxs-lookup"><span data-stu-id="5b37d-228"><strong>Edge Pool (Internal Edge): IPv6</strong></span></span></p></td>
<td><p><span data-ttu-id="5b37d-229">Não</span><span class="sxs-lookup"><span data-stu-id="5b37d-229">No</span></span></p></td>
<td><p><span data-ttu-id="5b37d-230">Não</span><span class="sxs-lookup"><span data-stu-id="5b37d-230">No</span></span></p></td>
<td><p><span data-ttu-id="5b37d-231">Sim</span><span class="sxs-lookup"><span data-stu-id="5b37d-231">Yes\*</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="5b37d-232">\*Use essa combinação somente em um ambiente de laboratório.</span><span class="sxs-lookup"><span data-stu-id="5b37d-232">\* Use this combination only in a lab environment.</span></span>

</div>

<div>

## <a name="advanced-enterprise-voice-support-for-ipv6"></a><span data-ttu-id="5b37d-233">Suporte avançado do Enterprise Voice para IPv6</span><span class="sxs-lookup"><span data-stu-id="5b37d-233">Advanced Enterprise Voice Support for IPv6</span></span>

<span data-ttu-id="5b37d-234">Implantações que incluem controle de admissão de chamadas (CAC), Enhanced 9-1-1 (E9-1-1) ou bypass de mídia devem ser configurados como IPv4 somente ou como uma implementação de pilha dupla.</span><span class="sxs-lookup"><span data-stu-id="5b37d-234">Deployments that include call admission control (CAC), Enhanced 9-1-1 (E9-1-1), or media bypass must be configured as IPv4 only or as a dual-stacked implementation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5b37d-235">Em uma implantação de pilha dupla, mesmo que um cliente do Lync se conecte a um Lync Server usando IPv6, o Lync fará um melhor esforço para mapear um endereço IPv4 apropriado para suportar o E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="5b37d-235">In a dual-stacked deployment, even if a Lync client connects to a Lync Server by using IPv6, Lync will make a best effort to map an appropriate IPv4 address to support E9-1-1.</span></span>



</div>

<span data-ttu-id="5b37d-236">O serviço de informações de local com endereços IPv6 não é suportado.</span><span class="sxs-lookup"><span data-stu-id="5b37d-236">Location Information service with IPv6 addresses is not supported.</span></span>

<span data-ttu-id="5b37d-237">A Unificação de mensagens (UM) do Exchange não oferece suporte a IPv6.</span><span class="sxs-lookup"><span data-stu-id="5b37d-237">Exchange Unified Messaging (UM) does not support IPv6.</span></span> <span data-ttu-id="5b37d-238">Para UM do Exchange, certifique-se de que a resolução de DNS não retorna um endereço IPv6.</span><span class="sxs-lookup"><span data-stu-id="5b37d-238">For Exchange UM, be sure that DNS resolution does not return an IPv6 address.</span></span> <span data-ttu-id="5b37d-239">O uso do IPv6 pode causar falha quando as chamadas são enviadas para caixa postal.</span><span class="sxs-lookup"><span data-stu-id="5b37d-239">Using IPv6 may cause failure when calls are sent to voice mail.</span></span>

</div>

<div>

## <a name="other-lync-server-2013-feature-support-for-ipv6"></a><span data-ttu-id="5b37d-240">Outro suporte de recurso do Lync Server 2013 para IPv6</span><span class="sxs-lookup"><span data-stu-id="5b37d-240">Other Lync Server 2013 Feature Support for IPv6</span></span>

<span data-ttu-id="5b37d-241">Além dos recursos e componentes mencionados anteriormente, o Lync Server 2013 suporta IPv6 para os seguintes recursos:</span><span class="sxs-lookup"><span data-stu-id="5b37d-241">In addition to the features and components mentioned previously, Lync Server 2013 supports IPv6 for the following features:</span></span>

  - <span data-ttu-id="5b37d-242">**Chat persistente**</span><span class="sxs-lookup"><span data-stu-id="5b37d-242">**Persistent Chat**</span></span>
    
    <span data-ttu-id="5b37d-243">Você configura o IPv6 para chat persistente usando o construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="5b37d-243">You configure IPv6 for Persistent Chat by using Topology Builder.</span></span> <span data-ttu-id="5b37d-244">Para obter detalhes sobre como configurar o chat persistente, consulte a documentação implantando o servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="5b37d-244">For details about configuring Persistent Chat, see the Deploying Persistent Chat Server documentation.</span></span>

  - <span data-ttu-id="5b37d-245">**Relatórios de QoE (qualidade da experiência) e de registro de detalhes das chamadas (CDR)**</span><span class="sxs-lookup"><span data-stu-id="5b37d-245">**Quality of Experience (QoE) and call detail recording (CDR) reports**</span></span>
    
    <span data-ttu-id="5b37d-246">Os relatórios de monitoramento incluem o endereço IP conforme ele é armazenado no banco de dados do Monitoring Server, seja do tipo IPv4 ou IPv6.</span><span class="sxs-lookup"><span data-stu-id="5b37d-246">Monitoring reports include the IP address as it is stored in the Monitoring Server database, whether of type IPv4 or IPv6.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

