---
title: 'Lync Server 2013: Visão geral dos tipos de endereços IP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of IP address types for Lync Server
ms:assetid: ee9a695f-5cf5-441e-94fb-6adeca50e8d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205363(v=OCS.15)
ms:contentKeyID: 48185759
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 90d31045879c4e6f488c232687346ed0413ef62b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825510"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-ip-address-types-for-lync-server-2013"></a><span data-ttu-id="a18f8-102">Visão geral dos tipos de endereços IP para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a18f8-102">Overview of IP address types for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a18f8-103">_**Tópico da última modificação:** 2013-01-29_</span><span class="sxs-lookup"><span data-stu-id="a18f8-103">_**Topic Last Modified:** 2013-01-29_</span></span>

<span data-ttu-id="a18f8-104">Você tem três opções ao configurar endereços IP no Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a18f8-104">You have three options when configuring IP addresses in Lync Server 2013.</span></span> <span data-ttu-id="a18f8-105">Você pode configurar o Lync Server 2013 para dar suporte somente para IP versão 4 (IPv4), somente para IP versão 6 (IPv6) ou uma combinação de ambos (conhecida como *pilha dupla*).</span><span class="sxs-lookup"><span data-stu-id="a18f8-105">You can configure Lync Server 2013 to support only IP version 4 (IPv4), only IP version 6 (IPv6), or a combination of both (known as a *dual stack*).</span></span> <span data-ttu-id="a18f8-106">Vários problemas devem ser considerados para cada tipo de configuração:</span><span class="sxs-lookup"><span data-stu-id="a18f8-106">There are several issues to consider with each type of configuration:</span></span>

  - <span data-ttu-id="a18f8-107">**IPv4 somente**   IPv6 foi criado porque o mundo está ficando sem endereços IPv4.</span><span class="sxs-lookup"><span data-stu-id="a18f8-107">**IPv4 only**   IPv6 was created because the world is running out of IPv4 addresses.</span></span> <span data-ttu-id="a18f8-108">No fim das contas, o IPv6 será completamente suportado em todo o mundo, mas no momento, várias empresas e dispositivos aos quais sua empresa pode precisar se comunicar ainda não oferecem suporte ao IPv6, e poderão não oferecer por algum tempo.</span><span class="sxs-lookup"><span data-stu-id="a18f8-108">Ultimately, IPv6 will be fully supported worldwide, but at this time, many companies and devices that your enterprise might need to communicate with do not yet support IPv6, and may not for some time.</span></span> <span data-ttu-id="a18f8-109">Uma configuração somente IPv4 ajudará a garantir que a implementação do Lync Server possa se comunicar com a maioria dos dispositivos existentes.</span><span class="sxs-lookup"><span data-stu-id="a18f8-109">An IPv4-only configuration will help to ensure that your Lync Server implementation can communicate with most existing devices.</span></span>

  - <span data-ttu-id="a18f8-110">\*\*\*\* Por outro lado, uma implementação IPv6 completa, no momento, excluirá a comunicação com muitos dispositivos existentes.   </span><span class="sxs-lookup"><span data-stu-id="a18f8-110">**IPv6 only**   Conversely, a full IPv6 implementation, at this time, will exclude communication with many existing devices.</span></span>

  - <span data-ttu-id="a18f8-111">\*\*\*\*   Pilha dupla dupla empilhada é uma rede onde ambos os endereços IPv4 e IPv6 são habilitados.</span><span class="sxs-lookup"><span data-stu-id="a18f8-111">**Dual Stack**   Dual stack is a network where both IPv4 and IPv6 addresses are enabled.</span></span> <span data-ttu-id="a18f8-112">Essa configuração tem suporte no Lync Server 2013 porque, na maioria dos casos, a transição de Full-IPv4 para Full-IPv6 levará vários anos.</span><span class="sxs-lookup"><span data-stu-id="a18f8-112">This configuration is supported in Lync Server 2013 because in most cases the transition from full-IPv4 to full-IPv6 will take several years.</span></span>

<span data-ttu-id="a18f8-113">As seções a seguir descrevem a compatibilidade entre essas três configurações para vários recursos do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a18f8-113">The following sections outline the compatibility among these three configurations for various Lync Server features.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a18f8-p104">Configuração de cliente ou servidor com somente IPv6 é suportada apenas para fins de validação ou utilização em laboratório. A configuração somente IPv6 não é suportada na implantação de produção.</span><span class="sxs-lookup"><span data-stu-id="a18f8-p104">Client or server configuration with IPv6 only is supported only for lab or validation purposes. IPv6 only configuration is not supported in the production deployment.</span></span>



</div>

<div>

## <a name="client-registration"></a><span data-ttu-id="a18f8-116">Registro de cliente</span><span class="sxs-lookup"><span data-stu-id="a18f8-116">Client Registration</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a18f8-117">Extremidade de rede de cliente</span><span class="sxs-lookup"><span data-stu-id="a18f8-117">Client endpoint network</span></span></th>
<th><span data-ttu-id="a18f8-118">Rede de servidor</span><span class="sxs-lookup"><span data-stu-id="a18f8-118">Server network</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a18f8-119">IPv4</span><span class="sxs-lookup"><span data-stu-id="a18f8-119">IPv4</span></span></p></td>
<td><p><span data-ttu-id="a18f8-120">IPv4</span><span class="sxs-lookup"><span data-stu-id="a18f8-120">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a18f8-121">IPv4</span><span class="sxs-lookup"><span data-stu-id="a18f8-121">IPv4</span></span></p></td>
<td><p><span data-ttu-id="a18f8-122">Pilha dual</span><span class="sxs-lookup"><span data-stu-id="a18f8-122">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a18f8-123">Pilha dual</span><span class="sxs-lookup"><span data-stu-id="a18f8-123">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="a18f8-124">IPv4</span><span class="sxs-lookup"><span data-stu-id="a18f8-124">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a18f8-125">Pilha dual</span><span class="sxs-lookup"><span data-stu-id="a18f8-125">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="a18f8-126">Pilha dual</span><span class="sxs-lookup"><span data-stu-id="a18f8-126">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a18f8-127">Pilha dual</span><span class="sxs-lookup"><span data-stu-id="a18f8-127">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="a18f8-128">IPv6</span><span class="sxs-lookup"><span data-stu-id="a18f8-128">IPv6</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a18f8-129">IPv6</span><span class="sxs-lookup"><span data-stu-id="a18f8-129">IPv6</span></span></p></td>
<td><p><span data-ttu-id="a18f8-130">Pilha dual</span><span class="sxs-lookup"><span data-stu-id="a18f8-130">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a18f8-131">IPv6</span><span class="sxs-lookup"><span data-stu-id="a18f8-131">IPv6</span></span></p></td>
<td><p><span data-ttu-id="a18f8-132">IPv6</span><span class="sxs-lookup"><span data-stu-id="a18f8-132">IPv6</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="peer-to-peer-client"></a><span data-ttu-id="a18f8-133">Cliente ponto a ponto</span><span class="sxs-lookup"><span data-stu-id="a18f8-133">Peer-to-Peer Client</span></span>

<span data-ttu-id="a18f8-p105">As comunicações ponto a ponto incluem áudio, áudio/vídeo, compartilhamento de aplicativos e transferência de arquivos. Após o registro bem sucedido de ambos os clientes, as combinações a seguir são suportadas.</span><span class="sxs-lookup"><span data-stu-id="a18f8-p105">Peer-to-peer communications include audio, audio/video, application sharing, and file transfer. After both clients have successfully registered, the following combinations are supported.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a18f8-136">Extremidade de cliente 1</span><span class="sxs-lookup"><span data-stu-id="a18f8-136">Client endpoint 1</span></span></th>
<th><span data-ttu-id="a18f8-137">Extremidade de cliente 2</span><span class="sxs-lookup"><span data-stu-id="a18f8-137">Client endpoint 2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a18f8-138">IPv4</span><span class="sxs-lookup"><span data-stu-id="a18f8-138">IPv4</span></span></p></td>
<td><p><span data-ttu-id="a18f8-139">IPv4</span><span class="sxs-lookup"><span data-stu-id="a18f8-139">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a18f8-140">IPv4</span><span class="sxs-lookup"><span data-stu-id="a18f8-140">IPv4</span></span></p></td>
<td><p><span data-ttu-id="a18f8-141">Pilha dual</span><span class="sxs-lookup"><span data-stu-id="a18f8-141">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a18f8-142">Pilha dual</span><span class="sxs-lookup"><span data-stu-id="a18f8-142">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="a18f8-143">Pilha dual</span><span class="sxs-lookup"><span data-stu-id="a18f8-143">Dual stack</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a18f8-144">IPv6</span><span class="sxs-lookup"><span data-stu-id="a18f8-144">IPv6</span></span></p></td>
<td><p><span data-ttu-id="a18f8-145">Pilha dual</span><span class="sxs-lookup"><span data-stu-id="a18f8-145">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a18f8-146">IPv6</span><span class="sxs-lookup"><span data-stu-id="a18f8-146">IPv6</span></span></p></td>
<td><p><span data-ttu-id="a18f8-147">IPv6</span><span class="sxs-lookup"><span data-stu-id="a18f8-147">IPv6</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="conferencing"></a><span data-ttu-id="a18f8-148">Conferência</span><span class="sxs-lookup"><span data-stu-id="a18f8-148">Conferencing</span></span>

<span data-ttu-id="a18f8-149">A conferência inclui áudio/vídeo, compartilhamento de aplicativos e colaboração de dados (quadro de comunicações e compartilhamento de arquivos).</span><span class="sxs-lookup"><span data-stu-id="a18f8-149">Conferencing includes audio/video, application sharing, and data collaboration (whiteboarding and file sharing).</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a18f8-150">Extremidade de rede de cliente</span><span class="sxs-lookup"><span data-stu-id="a18f8-150">Client endpoint network</span></span></th>
<th><span data-ttu-id="a18f8-151">Rede de servidor</span><span class="sxs-lookup"><span data-stu-id="a18f8-151">Server network</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a18f8-152">IPv4</span><span class="sxs-lookup"><span data-stu-id="a18f8-152">IPv4</span></span></p></td>
<td><p><span data-ttu-id="a18f8-153">IPv4</span><span class="sxs-lookup"><span data-stu-id="a18f8-153">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a18f8-154">IPv4</span><span class="sxs-lookup"><span data-stu-id="a18f8-154">IPv4</span></span></p></td>
<td><p><span data-ttu-id="a18f8-155">Pilha dual</span><span class="sxs-lookup"><span data-stu-id="a18f8-155">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a18f8-156">Pilha dual</span><span class="sxs-lookup"><span data-stu-id="a18f8-156">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="a18f8-157">IPv4</span><span class="sxs-lookup"><span data-stu-id="a18f8-157">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a18f8-158">Pilha dual</span><span class="sxs-lookup"><span data-stu-id="a18f8-158">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="a18f8-159">Pilha dual</span><span class="sxs-lookup"><span data-stu-id="a18f8-159">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a18f8-160">Pilha dual</span><span class="sxs-lookup"><span data-stu-id="a18f8-160">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="a18f8-161">IPv6</span><span class="sxs-lookup"><span data-stu-id="a18f8-161">IPv6</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a18f8-162">IPv6</span><span class="sxs-lookup"><span data-stu-id="a18f8-162">IPv6</span></span></p></td>
<td><p><span data-ttu-id="a18f8-163">Pilha dual</span><span class="sxs-lookup"><span data-stu-id="a18f8-163">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a18f8-164">IPv6</span><span class="sxs-lookup"><span data-stu-id="a18f8-164">IPv6</span></span></p></td>
<td><p><span data-ttu-id="a18f8-165">IPv6</span><span class="sxs-lookup"><span data-stu-id="a18f8-165">IPv6</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="mediation-serverpstn"></a><span data-ttu-id="a18f8-166">Servidor de Mediação/PSTN</span><span class="sxs-lookup"><span data-stu-id="a18f8-166">Mediation Server/PSTN</span></span>

<span data-ttu-id="a18f8-167">O Lync Server 2013 não oferece suporte à bypass de mídia para chamadas PSTN (rede telefônica pública comutada) se o tráfego for por meio de uma interface IPv6.</span><span class="sxs-lookup"><span data-stu-id="a18f8-167">Lync Server 2013 does not support media bypass for public switched telephone network (PSTN) calls if the traffic is through an IPv6 interface.</span></span> <span data-ttu-id="a18f8-168">Se o desvio de mídia é necessário, recomendamos que o gateway PSTN seja configurado para IPv4.</span><span class="sxs-lookup"><span data-stu-id="a18f8-168">If media bypass is required, we recommend that the PSTN gateway is configured to IPv4.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a18f8-169">Interface principal\*</span><span class="sxs-lookup"><span data-stu-id="a18f8-169">Primary interface\*</span></span></th>
<th><span data-ttu-id="a18f8-170">Interface PSTN (no Servidor de Mediação)</span><span class="sxs-lookup"><span data-stu-id="a18f8-170">PSTN interface (on Mediation Server)</span></span></th>
<th><span data-ttu-id="a18f8-171">Configuração do gateway PSTN</span><span class="sxs-lookup"><span data-stu-id="a18f8-171">PSTN gateway setting</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a18f8-172">IPv4</span><span class="sxs-lookup"><span data-stu-id="a18f8-172">IPv4</span></span></p></td>
<td><p><span data-ttu-id="a18f8-173">Pilha dual</span><span class="sxs-lookup"><span data-stu-id="a18f8-173">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="a18f8-174">IPv4</span><span class="sxs-lookup"><span data-stu-id="a18f8-174">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a18f8-175">Pilha dual</span><span class="sxs-lookup"><span data-stu-id="a18f8-175">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="a18f8-176">Pilha dual</span><span class="sxs-lookup"><span data-stu-id="a18f8-176">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="a18f8-177">IPv4</span><span class="sxs-lookup"><span data-stu-id="a18f8-177">IPv4</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a18f8-178">Pilha dual</span><span class="sxs-lookup"><span data-stu-id="a18f8-178">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="a18f8-179">Pilha dual</span><span class="sxs-lookup"><span data-stu-id="a18f8-179">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="a18f8-180">IPv6</span><span class="sxs-lookup"><span data-stu-id="a18f8-180">IPv6</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="a18f8-181">\*A interface principal é a interface que se comunica com os componentes do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a18f8-181">\* The primary interface is the interface that communicates with the Lync Server components.</span></span>

</div>

<div>

## <a name="remote-user-peer-to-peer-communications"></a><span data-ttu-id="a18f8-182">Comunicações ponto a ponto de usuário remoto</span><span class="sxs-lookup"><span data-stu-id="a18f8-182">Remote User Peer-to-Peer Communications</span></span>

<span data-ttu-id="a18f8-183">As comunicações ponto a ponto com usuários remotos incluem mensagens instantâneas, áudio/vídeo, compartilhamento de aplicativos e transferência de arquivos.</span><span class="sxs-lookup"><span data-stu-id="a18f8-183">Peer-to-peer communications with remote users include instant messaging, audio/video, application sharing, and file transfer.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a18f8-184">Rede de usuários remotos</span><span class="sxs-lookup"><span data-stu-id="a18f8-184">Remote user network</span></span></th>
<th><span data-ttu-id="a18f8-185">Servidor de borda (Borda externa)</span><span class="sxs-lookup"><span data-stu-id="a18f8-185">Edge server (External edge)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a18f8-186">IPv4</span><span class="sxs-lookup"><span data-stu-id="a18f8-186">IPv4</span></span></p></td>
<td><p><span data-ttu-id="a18f8-187">IPv4</span><span class="sxs-lookup"><span data-stu-id="a18f8-187">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a18f8-188">Pilha dual</span><span class="sxs-lookup"><span data-stu-id="a18f8-188">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="a18f8-189">IPv4</span><span class="sxs-lookup"><span data-stu-id="a18f8-189">IPv4</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a18f8-190">Pilha dual</span><span class="sxs-lookup"><span data-stu-id="a18f8-190">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="a18f8-191">Pilha dual</span><span class="sxs-lookup"><span data-stu-id="a18f8-191">Dual stack</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a18f8-192">IPv6</span><span class="sxs-lookup"><span data-stu-id="a18f8-192">IPv6</span></span></p></td>
<td><p><span data-ttu-id="a18f8-193">Pilha dual</span><span class="sxs-lookup"><span data-stu-id="a18f8-193">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a18f8-194">IPv6</span><span class="sxs-lookup"><span data-stu-id="a18f8-194">IPv6</span></span></p></td>
<td><p><span data-ttu-id="a18f8-195">IPv6</span><span class="sxs-lookup"><span data-stu-id="a18f8-195">IPv6</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="front-end-pool-and-edge-pool-configuration"></a><span data-ttu-id="a18f8-196">Configuração do pool de Front-Ends e do pool do Servidor de Borda</span><span class="sxs-lookup"><span data-stu-id="a18f8-196">Front End Pool and Edge Pool Configuration</span></span>

<span data-ttu-id="a18f8-197">A tabela a seguir mostra a matriz de suporte entre o pool do servidor front-end e o pool do servidor de borda interna.</span><span class="sxs-lookup"><span data-stu-id="a18f8-197">The following table shows the support matrix between the Front End Server pool and the internal Edge Server pool.</span></span>

### <a name="front-end-pool-and-edge-pool-internal-edge-matrix"></a><span data-ttu-id="a18f8-198">Matriz do Pool de Front-Ends e do Pool de Borda (Borda interna)</span><span class="sxs-lookup"><span data-stu-id="a18f8-198">Front End Pool and Edge Pool (Internal Edge) Matrix</span></span>

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
<td><p><span data-ttu-id="a18f8-199"><strong>Pool de borda: IPv4</strong></span><span class="sxs-lookup"><span data-stu-id="a18f8-199"><strong>Edge Pool: IPv4</strong></span></span></p></td>
<td><p><span data-ttu-id="a18f8-200"><strong>Pool de borda: Pilha dual</strong></span><span class="sxs-lookup"><span data-stu-id="a18f8-200"><strong>Edge Pool: Dual Stack</strong></span></span></p></td>
<td><p><span data-ttu-id="a18f8-201"><strong>Pool de borda: IPv6</strong></span><span class="sxs-lookup"><span data-stu-id="a18f8-201"><strong>Edge Pool: IPv6</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a18f8-202"><strong>Pool de Front-Ends: IPv4</strong></span><span class="sxs-lookup"><span data-stu-id="a18f8-202"><strong>Front End Pool: IPv4</strong></span></span></p></td>
<td><p><span data-ttu-id="a18f8-203">Sim</span><span class="sxs-lookup"><span data-stu-id="a18f8-203">Yes</span></span></p></td>
<td><p><span data-ttu-id="a18f8-204">Sim</span><span class="sxs-lookup"><span data-stu-id="a18f8-204">Yes</span></span></p></td>
<td><p><span data-ttu-id="a18f8-205">Não</span><span class="sxs-lookup"><span data-stu-id="a18f8-205">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a18f8-206"><strong>Pool de Front-Ends: Pilha dual</strong></span><span class="sxs-lookup"><span data-stu-id="a18f8-206"><strong>Front End Pool: Dual Stack</strong></span></span></p></td>
<td><p><span data-ttu-id="a18f8-207">Sim </span><span class="sxs-lookup"><span data-stu-id="a18f8-207">Yes</span></span></p></td>
<td><p><span data-ttu-id="a18f8-208">Sim</span><span class="sxs-lookup"><span data-stu-id="a18f8-208">Yes</span></span></p></td>
<td><p><span data-ttu-id="a18f8-209">Não</span><span class="sxs-lookup"><span data-stu-id="a18f8-209">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a18f8-210"><strong>Pool de Front-Ends: IPv6</strong></span><span class="sxs-lookup"><span data-stu-id="a18f8-210"><strong>Front End Pool: IPv6</strong></span></span></p></td>
<td><p><span data-ttu-id="a18f8-211">Não</span><span class="sxs-lookup"><span data-stu-id="a18f8-211">No</span></span></p></td>
<td><p><span data-ttu-id="a18f8-212">Não</span><span class="sxs-lookup"><span data-stu-id="a18f8-212">No</span></span></p></td>
<td><p><span data-ttu-id="a18f8-213">Sim\*</span><span class="sxs-lookup"><span data-stu-id="a18f8-213">Yes\*</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="a18f8-214">\*Use essa combinação apenas em um ambiente de laboratório.</span><span class="sxs-lookup"><span data-stu-id="a18f8-214">\* Use this combination only in a lab environment.</span></span>

<span data-ttu-id="a18f8-215">A tabela a seguir descreve a matriz de combinações suportadas das interfaces de borda interna e externa.</span><span class="sxs-lookup"><span data-stu-id="a18f8-215">The following table is a matrix of the supported combinations of internal and external edge interfaces.</span></span>

### <a name="edge-pool-internal-edge-and-edge-pool-external-edge-matrix"></a><span data-ttu-id="a18f8-216">Matriz do Pool de borda (Borda interna) e do Pool de borda (Borda externa)</span><span class="sxs-lookup"><span data-stu-id="a18f8-216">Edge Pool (Internal Edge) and Edge pool (External Edge) Matrix</span></span>

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
<td><p><span data-ttu-id="a18f8-217"><strong>Pool de borda (Borda externa): IPv4</strong></span><span class="sxs-lookup"><span data-stu-id="a18f8-217"><strong>Edge Pool (External Edge) : IPv4</strong></span></span></p></td>
<td><p><span data-ttu-id="a18f8-218"><strong>Pool de borda (Borda externa): Pilha dual</strong></span><span class="sxs-lookup"><span data-stu-id="a18f8-218"><strong>Edge Pool (External Edge): Dual Stack</strong></span></span></p></td>
<td><p><span data-ttu-id="a18f8-219"><strong>Pool de borda (Borda externa): IPv6</strong></span><span class="sxs-lookup"><span data-stu-id="a18f8-219"><strong>Edge Pool (External Edge): IPv6</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a18f8-220"><strong>Pool de borda (Borda interna): IPv4</strong></span><span class="sxs-lookup"><span data-stu-id="a18f8-220"><strong>Edge Pool (Internal Edge): IPv4</strong></span></span></p></td>
<td><p><span data-ttu-id="a18f8-221">Sim</span><span class="sxs-lookup"><span data-stu-id="a18f8-221">Yes</span></span></p></td>
<td><p><span data-ttu-id="a18f8-222">Sim</span><span class="sxs-lookup"><span data-stu-id="a18f8-222">Yes</span></span></p></td>
<td><p><span data-ttu-id="a18f8-223">Não</span><span class="sxs-lookup"><span data-stu-id="a18f8-223">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a18f8-224"><strong>Pool de borda (Borda interna): Pilha dual</strong></span><span class="sxs-lookup"><span data-stu-id="a18f8-224"><strong>Edge Pool (Internal Edge): Dual Stack</strong></span></span></p></td>
<td><p><span data-ttu-id="a18f8-225">Não</span><span class="sxs-lookup"><span data-stu-id="a18f8-225">No</span></span></p></td>
<td><p><span data-ttu-id="a18f8-226">Sim</span><span class="sxs-lookup"><span data-stu-id="a18f8-226">Yes</span></span></p></td>
<td><p><span data-ttu-id="a18f8-227">Não</span><span class="sxs-lookup"><span data-stu-id="a18f8-227">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a18f8-228"><strong>Pool de borda (Borda interna): IPv6</strong></span><span class="sxs-lookup"><span data-stu-id="a18f8-228"><strong>Edge Pool (Internal Edge): IPv6</strong></span></span></p></td>
<td><p><span data-ttu-id="a18f8-229">Não</span><span class="sxs-lookup"><span data-stu-id="a18f8-229">No</span></span></p></td>
<td><p><span data-ttu-id="a18f8-230">Não</span><span class="sxs-lookup"><span data-stu-id="a18f8-230">No</span></span></p></td>
<td><p><span data-ttu-id="a18f8-231">Sim\*</span><span class="sxs-lookup"><span data-stu-id="a18f8-231">Yes\*</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="a18f8-232">\*Use essa combinação apenas em um ambiente de laboratório.</span><span class="sxs-lookup"><span data-stu-id="a18f8-232">\* Use this combination only in a lab environment.</span></span>

</div>

<div>

## <a name="advanced-enterprise-voice-support-for-ipv6"></a><span data-ttu-id="a18f8-233">Suporte avançado do Enterprise Voice para IPv6</span><span class="sxs-lookup"><span data-stu-id="a18f8-233">Advanced Enterprise Voice Support for IPv6</span></span>

<span data-ttu-id="a18f8-234">Implantações que incluem controle de admissão de chamadas (CAC), Enhanced 9-1-1 (E9-1-1) ou passagem livre de mídia devem ser configurados como implementações somente IPv4 ou de pilha dual.</span><span class="sxs-lookup"><span data-stu-id="a18f8-234">Deployments that include call admission control (CAC), Enhanced 9-1-1 (E9-1-1), or media bypass must be configured as IPv4 only or as a dual-stacked implementation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a18f8-235">Em uma implantação de pilha dupla, mesmo que um cliente do Lync se conecte a um servidor do Lync usando o IPv6, o Lync fará um melhor esforço para mapear um endereço IPv4 apropriado para dar suporte a E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="a18f8-235">In a dual-stacked deployment, even if a Lync client connects to a Lync Server by using IPv6, Lync will make a best effort to map an appropriate IPv4 address to support E9-1-1.</span></span>



</div>

<span data-ttu-id="a18f8-236">Não há suporte para o serviço de informações de localização com endereços IPv6.</span><span class="sxs-lookup"><span data-stu-id="a18f8-236">Location Information service with IPv6 addresses is not supported.</span></span>

<span data-ttu-id="a18f8-p107">O Unified Messaging (UM) do Exchange não suporta IPv6. Para o UM do Exchange, certifique-se de que a resolução do DNS não retorna um endereço IPv6. A utilização de IPv6 pode provocar falhas ao enviar chamadas para correios de voz.</span><span class="sxs-lookup"><span data-stu-id="a18f8-p107">Exchange Unified Messaging (UM) does not support IPv6. For Exchange UM, be sure that DNS resolution does not return an IPv6 address. Using IPv6 may cause failure when calls are sent to voice mail.</span></span>

</div>

<div>

## <a name="other-lync-server-2013-feature-support-for-ipv6"></a><span data-ttu-id="a18f8-240">Outro suporte do recurso Lync Server 2013 para IPv6</span><span class="sxs-lookup"><span data-stu-id="a18f8-240">Other Lync Server 2013 Feature Support for IPv6</span></span>

<span data-ttu-id="a18f8-241">Além dos recursos e componentes mencionados anteriormente, o Lync Server 2013 oferece suporte ao IPv6 para os seguintes recursos:</span><span class="sxs-lookup"><span data-stu-id="a18f8-241">In addition to the features and components mentioned previously, Lync Server 2013 supports IPv6 for the following features:</span></span>

  - <span data-ttu-id="a18f8-242">**Chat Persistente**</span><span class="sxs-lookup"><span data-stu-id="a18f8-242">**Persistent Chat**</span></span>
    
    <span data-ttu-id="a18f8-243">Você configura o IPv6 para chats persistentes usando o construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="a18f8-243">You configure IPv6 for Persistent Chat by using Topology Builder.</span></span> <span data-ttu-id="a18f8-244">Para obter detalhes sobre como configurar o chat persistente, consulte a documentação implantando o servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="a18f8-244">For details about configuring Persistent Chat, see the Deploying Persistent Chat Server documentation.</span></span>

  - <span data-ttu-id="a18f8-245">**Relatórios de CDR (registro de detalhes de chamada) e QoE (Qualidade de experiência)**</span><span class="sxs-lookup"><span data-stu-id="a18f8-245">**Quality of Experience (QoE) and call detail recording (CDR) reports**</span></span>
    
    <span data-ttu-id="a18f8-246">Os relatórios de monitoramento incluem o endereço IP conforme é armazenado no banco de dados do Servidor de Monitoramento, independente de ser do tipo IPv4 ou IPv6.</span><span class="sxs-lookup"><span data-stu-id="a18f8-246">Monitoring reports include the IP address as it is stored in the Monitoring Server database, whether of type IPv4 or IPv6.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

