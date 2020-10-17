---
title: 'Lync Server 2013: determinar firewall A/V externo e requisitos de porta'
description: 'Lync Server 2013: determinar firewall A/V externo e requisitos de porta.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Determine external A/V firewall and port requirements
ms:assetid: 3b849dc7-175d-40d1-820d-80e6ade6d332
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425882(v=OCS.15)
ms:contentKeyID: 48183872
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 38c2a8c1e8e332a4a1e65adb87a1e962e82941c2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550927"
---
# <a name="determine-external-av-firewall-and-port-requirements-for-lync-server-2013"></a><span data-ttu-id="e00fc-103">Determinar firewall A/V externo e requisitos de porta para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e00fc-103">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e00fc-104">_**Última modificação do tópico:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="e00fc-104">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="e00fc-105">A comunicação de áudio/vídeo (A/V) pode ser um complexo.</span><span class="sxs-lookup"><span data-stu-id="e00fc-105">Audio/Video (A/V) communication can be a complex.</span></span> <span data-ttu-id="e00fc-106">Devido à natureza dos protocolos usados em A/V e como os clientes e servidores usam os protocolos, uma seção especial é garantida para explicar as diferenças entre as versões do cliente e do servidor.</span><span class="sxs-lookup"><span data-stu-id="e00fc-106">Because of the nature of protocols used in A/V and how clients and servers use the protocols, a special section is warranted to explain the differences between client and server versions.</span></span>

<span data-ttu-id="e00fc-107">Use a seguinte firewall de A/V e tabela de porta para determinar os requisitos de firewall e quais portas abrir.</span><span class="sxs-lookup"><span data-stu-id="e00fc-107">Use the following A/V Firewall and Port table to determine firewall requirements and which ports to open.</span></span> <span data-ttu-id="e00fc-108">Em seguida, revise a terminologia NAT (conversão de endereço de rede) porque o NAT pode ser implementado de várias maneiras diferentes.</span><span class="sxs-lookup"><span data-stu-id="e00fc-108">Then, review the network address translation (NAT) terminology because NAT can be implemented in many different ways.</span></span> <span data-ttu-id="e00fc-109">Para obter um exemplo detalhado das configurações de porta de firewall, consulte as arquiteturas de referência em [cenários para acesso de usuário externo no Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="e00fc-109">For a detailed example of firewall port settings, see the reference architectures in [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span></span>

### <a name="general-protocol-usage-for-udp-and-tcp-in-audiovideo-and-media-traffic"></a><span data-ttu-id="e00fc-110">Uso de protocolo geral para UDP e TCP no tráfego de áudio/vídeo e mídia</span><span class="sxs-lookup"><span data-stu-id="e00fc-110">General Protocol Usage for UDP and TCP in Audio/Video and Media Traffic</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e00fc-111">Transporte de áudio/vídeo</span><span class="sxs-lookup"><span data-stu-id="e00fc-111">Audio/Video Transport</span></span></th>
<th><span data-ttu-id="e00fc-112">Uso</span><span class="sxs-lookup"><span data-stu-id="e00fc-112">Usage</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e00fc-113">VIA</span><span class="sxs-lookup"><span data-stu-id="e00fc-113">UDP</span></span></p></td>
<td><p><span data-ttu-id="e00fc-114">Protocolo de camada de transporte preferencial para áudio e vídeo</span><span class="sxs-lookup"><span data-stu-id="e00fc-114">Preferred transport layer protocol for audio and video</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e00fc-115">TCP</span><span class="sxs-lookup"><span data-stu-id="e00fc-115">TCP</span></span></p></td>
<td><p><span data-ttu-id="e00fc-116">Protocolo de camada de transporte de fallback para áudio e vídeo</span><span class="sxs-lookup"><span data-stu-id="e00fc-116">Fallback transport layer protocol for audio and video</span></span></p>
<p><span data-ttu-id="e00fc-117">Protocolo de camada de transporte necessário para compartilhamento de aplicativos para o Office Communications Server 2007 R2, Lync Server 2010 e Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e00fc-117">Required transport layer protocol for application sharing to Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013</span></span></p>
<p><span data-ttu-id="e00fc-118">Protocolo de camada de transporte necessário para transferência de arquivo para Lync Server 2010 e Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e00fc-118">Required transport layer protocol for file transfer to Lync Server 2010 and Lync Server 2013</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="external-av-firewall-port-requirements-for-external-user-access"></a><span data-ttu-id="e00fc-119">Requisitos de porta de firewall A/V externo para acesso de usuário externo</span><span class="sxs-lookup"><span data-stu-id="e00fc-119">External A/V Firewall Port Requirements for External User Access</span></span>

<span data-ttu-id="e00fc-120">Os requisitos de porta de firewall para as interfaces de SIP e de conferência externas (e internas) são consistentes, independentemente da versão do cliente ou da versão do parceiro de Federação.</span><span class="sxs-lookup"><span data-stu-id="e00fc-120">The firewall port requirements for external (and internal) SIP and conferencing interfaces are consistent, regardless of the version of your client or the version of the federation partner.</span></span>

<span data-ttu-id="e00fc-121">O mesmo não se aplica à interface externa de borda de áudio/vídeo.</span><span class="sxs-lookup"><span data-stu-id="e00fc-121">The same is not true for the Audio/Video Edge external interface.</span></span> <span data-ttu-id="e00fc-122">Para federação com o Office Communications Server 2007, o serviço de borda A/V requer que as regras de firewall externas permitam que o tráfego RTP/TCP e RTP/UDP no intervalo de porta de 50.000 a 59.999 fluam em ambas as direções.</span><span class="sxs-lookup"><span data-stu-id="e00fc-122">For federation with Office Communications Server 2007, the A/V Edge service requires that external firewall rules allow RTP/TCP and RTP/UDP traffic in the 50,000 through 59,999 port range to flow in both directions.</span></span> <span data-ttu-id="e00fc-123">A tabela anterior pressupõe que o Lync Server 2013 é o parceiro de Federação principal e está sendo configurado para se comunicar com um dos outros tipos de parceiros de Federação listados.</span><span class="sxs-lookup"><span data-stu-id="e00fc-123">The previous table assumes that Lync Server 2013 is the primary federation partner and it is being configured to communicate with one of the other federation partner types listed.</span></span>

<span data-ttu-id="e00fc-124">Configurar o intervalo de porta de áudio/vídeo de 50000-59.999 deve levar em conta que o intervalo de porta conterá as portas de origem para comunicações com parceiros de Federação.</span><span class="sxs-lookup"><span data-stu-id="e00fc-124">Configuring the Audio/Video port range of 50,000-59,999 must take into account that the port range will contain the source ports for communications to federation partners.</span></span> <span data-ttu-id="e00fc-125">Em detalhes, considere que uma comunicação é iniciada a partir de um parceiro de Federação.</span><span class="sxs-lookup"><span data-stu-id="e00fc-125">In detail, consider that a communication is initiated from a federation partner.</span></span> <span data-ttu-id="e00fc-126">A comunicação das portas de serviço de borda a/V no intervalo de 50000 59.999 se conectará à porta TCP 443 esperada do serviço de borda A/V do parceiro.</span><span class="sxs-lookup"><span data-stu-id="e00fc-126">The communication from the A/V Edge service ports in the 50,000-59,999 range will connect to the expected port TCP 443 of the partner’s A/V Edge service.</span></span> <span data-ttu-id="e00fc-127">Por outro lado, o tráfego de entrada para sua porta de serviço de borda A/V TCP 443 terá uma porta de origem no intervalo de 50000 59.999.</span><span class="sxs-lookup"><span data-stu-id="e00fc-127">Conversely, inbound traffic to your A/V Edge service port TCP 443 will have a source port in the range of 50,000-59,999.</span></span>

<span data-ttu-id="e00fc-128">Firewalls e políticas diferentes para a administração de firewall podem exigir que apenas as regras de destino sejam configuradas ou podem exigir que a origem e o destino sejam configurados.</span><span class="sxs-lookup"><span data-stu-id="e00fc-128">Different firewalls and policies for firewall administration may require only destination rules to be configured, or they may require both source and destination to be configured.</span></span> <span data-ttu-id="e00fc-129">Se seus requisitos forem somente para portas de destino, os requisitos de áudio/vídeo são:</span><span class="sxs-lookup"><span data-stu-id="e00fc-129">If your requirements are for destination ports only, the Audio/Video requirements are:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e00fc-130">IP de origem</span><span class="sxs-lookup"><span data-stu-id="e00fc-130">Source IP</span></span></th>
<th><span data-ttu-id="e00fc-131">IP de destino</span><span class="sxs-lookup"><span data-stu-id="e00fc-131">Destination IP</span></span></th>
<th><span data-ttu-id="e00fc-132">Porta de destino</span><span class="sxs-lookup"><span data-stu-id="e00fc-132">Destination Port</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e00fc-133">Interface de serviço de borda A/V</span><span class="sxs-lookup"><span data-stu-id="e00fc-133">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="e00fc-134">Qualquer</span><span class="sxs-lookup"><span data-stu-id="e00fc-134">Any</span></span></p></td>
<td><p><span data-ttu-id="e00fc-135">TCP 443</span><span class="sxs-lookup"><span data-stu-id="e00fc-135">TCP 443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e00fc-136">Interface de serviço de borda A/V</span><span class="sxs-lookup"><span data-stu-id="e00fc-136">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="e00fc-137">Qualquer</span><span class="sxs-lookup"><span data-stu-id="e00fc-137">Any</span></span></p></td>
<td><p><span data-ttu-id="e00fc-138">UDP 3478</span><span class="sxs-lookup"><span data-stu-id="e00fc-138">UDP 3478</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e00fc-139">Qualquer</span><span class="sxs-lookup"><span data-stu-id="e00fc-139">Any</span></span></p></td>
<td><p><span data-ttu-id="e00fc-140">Interface de serviço de borda A/V</span><span class="sxs-lookup"><span data-stu-id="e00fc-140">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="e00fc-141">TCP 443</span><span class="sxs-lookup"><span data-stu-id="e00fc-141">TCP 443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e00fc-142">Qualquer</span><span class="sxs-lookup"><span data-stu-id="e00fc-142">Any</span></span></p></td>
<td><p><span data-ttu-id="e00fc-143">Interface de serviço de borda A/V</span><span class="sxs-lookup"><span data-stu-id="e00fc-143">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="e00fc-144">UDP 3478</span><span class="sxs-lookup"><span data-stu-id="e00fc-144">UDP 3478</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="e00fc-145">Se suas políticas exigem definições de regra de firewall de entrada e saída, os requisitos de áudio/vídeo são:</span><span class="sxs-lookup"><span data-stu-id="e00fc-145">If your policies require both inbound and outbound firewall rule definitions, the Audio/Video requirements are:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e00fc-146">IP de origem</span><span class="sxs-lookup"><span data-stu-id="e00fc-146">Source IP</span></span></th>
<th><span data-ttu-id="e00fc-147">IP de destino</span><span class="sxs-lookup"><span data-stu-id="e00fc-147">Destination IP</span></span></th>
<th><span data-ttu-id="e00fc-148">Porta de origem</span><span class="sxs-lookup"><span data-stu-id="e00fc-148">Source Port</span></span></th>
<th><span data-ttu-id="e00fc-149">Porta de destino</span><span class="sxs-lookup"><span data-stu-id="e00fc-149">Destination Port</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e00fc-150">Interface de serviço de borda A/V</span><span class="sxs-lookup"><span data-stu-id="e00fc-150">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="e00fc-151">Qualquer</span><span class="sxs-lookup"><span data-stu-id="e00fc-151">Any</span></span></p></td>
<td><p><span data-ttu-id="e00fc-152">TCP 50000-59.999</span><span class="sxs-lookup"><span data-stu-id="e00fc-152">TCP 50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="e00fc-153">TCP 443</span><span class="sxs-lookup"><span data-stu-id="e00fc-153">TCP 443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e00fc-154">Interface de serviço de borda A/V</span><span class="sxs-lookup"><span data-stu-id="e00fc-154">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="e00fc-155">Qualquer</span><span class="sxs-lookup"><span data-stu-id="e00fc-155">Any</span></span></p></td>
<td><p><span data-ttu-id="e00fc-156">UDP 3478</span><span class="sxs-lookup"><span data-stu-id="e00fc-156">UDP 3478</span></span></p></td>
<td><p><span data-ttu-id="e00fc-157">UDP 3478</span><span class="sxs-lookup"><span data-stu-id="e00fc-157">UDP 3478</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e00fc-158">Qualquer</span><span class="sxs-lookup"><span data-stu-id="e00fc-158">Any</span></span></p></td>
<td><p><span data-ttu-id="e00fc-159">Interface de serviço de borda A/V</span><span class="sxs-lookup"><span data-stu-id="e00fc-159">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="e00fc-160">Qualquer</span><span class="sxs-lookup"><span data-stu-id="e00fc-160">Any</span></span></p></td>
<td><p><span data-ttu-id="e00fc-161">TCP 443</span><span class="sxs-lookup"><span data-stu-id="e00fc-161">TCP 443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e00fc-162">Qualquer</span><span class="sxs-lookup"><span data-stu-id="e00fc-162">Any</span></span></p></td>
<td><p><span data-ttu-id="e00fc-163">Interface de serviço de borda A/V</span><span class="sxs-lookup"><span data-stu-id="e00fc-163">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="e00fc-164">Qualquer</span><span class="sxs-lookup"><span data-stu-id="e00fc-164">Any</span></span></p></td>
<td><p><span data-ttu-id="e00fc-165">UDP 3478</span><span class="sxs-lookup"><span data-stu-id="e00fc-165">UDP 3478</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> <span data-ttu-id="e00fc-166">O Microsoft Office Communications Server 2007 requer uma configuração um pouco diferente.</span><span class="sxs-lookup"><span data-stu-id="e00fc-166">Microsoft Office Communications Server 2007 requires a slightly different configuration.</span></span> <span data-ttu-id="e00fc-167">O intervalo de portas TCP e UDP de 50000-59.999 deve estar aberto e de saída.</span><span class="sxs-lookup"><span data-stu-id="e00fc-167">The TCP and UDP port range of 50,000-59,999 must be open inbound and outbound.</span></span> <span data-ttu-id="e00fc-168">Este requisito é apenas para o Office Communicator 2007.</span><span class="sxs-lookup"><span data-stu-id="e00fc-168">This requirement is only for Office Communicator 2007.</span></span> <span data-ttu-id="e00fc-169">O Office Communications Server 2007 R2, Lync Server 2010 e Lync Server 2013 só exigem o intervalo de TCP 50000-59.999 Open outbound.</span><span class="sxs-lookup"><span data-stu-id="e00fc-169">Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013 only require TCP range 50,000-59,999 open outbound.</span></span>



</div>

</div>

<div>

## <a name="nat-requirements-for-the-edge-service"></a><span data-ttu-id="e00fc-170">Requisitos de NAT para o serviço de borda</span><span class="sxs-lookup"><span data-stu-id="e00fc-170">NAT requirements for the Edge service</span></span>

<span data-ttu-id="e00fc-171">Os seguintes requisitos de NAT se aplicam se você optar por configurar endereços IP privados não roteáveis para o serviço de borda:</span><span class="sxs-lookup"><span data-stu-id="e00fc-171">The following NAT requirements apply if you choose to configure non-routable private IP addresses for the Edge service:</span></span>

  - <span data-ttu-id="e00fc-172">O NAT só pode ser usado com o balanceamento de carga DNS.</span><span class="sxs-lookup"><span data-stu-id="e00fc-172">NAT can only be used with DNS load-balancing.</span></span> <span data-ttu-id="e00fc-173">NAT não é compatível com uma topologia de borda de HLB (balanceamento de carga de hardware).</span><span class="sxs-lookup"><span data-stu-id="e00fc-173">NAT is not supported with a hardware load balancing (HLB) Edge topology.</span></span>

  - <span data-ttu-id="e00fc-174">O NAT só pode ser usado na interface de borda externa.</span><span class="sxs-lookup"><span data-stu-id="e00fc-174">NAT can only be used on the external Edge interface.</span></span> <span data-ttu-id="e00fc-175">O NAT não é suportado na interface de borda interna.</span><span class="sxs-lookup"><span data-stu-id="e00fc-175">NAT is not supported on the internal Edge interface.</span></span>

  - <span data-ttu-id="e00fc-176">NAT deve ser simétrico para tráfego de entrada e saída.</span><span class="sxs-lookup"><span data-stu-id="e00fc-176">NAT must be symmetric for incoming and outgoing traffic.</span></span>
    
  - <span data-ttu-id="e00fc-177">Para o tráfego da Internet, o NAT deve alterar o endereço IP de destino do endereço IP público habilitado para NAT do serviço de borda a/V para seu endereço IP externo.</span><span class="sxs-lookup"><span data-stu-id="e00fc-177">For traffic from the Internet, NAT must change the destination IP address from the NAT-enabled public IP address of the A/V Edge service to its external IP address.</span></span> <span data-ttu-id="e00fc-178">O endereço IP de origem deve permanecer intacto, para que o serviço de borda a/V possa encontrar o caminho de mídia ideal.</span><span class="sxs-lookup"><span data-stu-id="e00fc-178">The source IP address must remain intact, so that the A/V Edge service can find the optimal media path.</span></span>
  
  <span data-ttu-id="e00fc-179">Por exemplo, na direção de entrada na figura abaixo, o endereço IP público 131.107.155.30 foi alterado para o endereço IP externo (privado) 10.45.16.10.</span><span class="sxs-lookup"><span data-stu-id="e00fc-179">For example, in the inbound direction in the figure below, the public IP address 131.107.155.30 was changed to the external (private) IP address 10.45.16.10.</span></span> <span data-ttu-id="e00fc-180">O endereço IP de origem permaneceu inalterado.</span><span class="sxs-lookup"><span data-stu-id="e00fc-180">The source IP address remained unchanged.</span></span>
  
  - <span data-ttu-id="e00fc-181">Para o tráfego do serviço de borda a/V para a Internet, o NAT deve alterar o endereço IP de origem do endereço IP externo do serviço de borda a/V para o endereço IP público habilitado para NAT.</span><span class="sxs-lookup"><span data-stu-id="e00fc-181">For traffic from the A/V Edge service to the Internet, NAT must change the source IP address from the external IP address of the A/V Edge service to the NAT-enabled public IP address.</span></span>

<span data-ttu-id="e00fc-182">Por exemplo, na direção de saída na figura abaixo, o endereço IP externo (privado) 10.45.16.10 foi alterado para o endereço IP público 131.107.155.30.</span><span class="sxs-lookup"><span data-stu-id="e00fc-182">For example, in the outbound direction in the figure below, the external (private) IP address 10.45.16.10 was changed to the public IP address 131.107.155.30.</span></span>

<span data-ttu-id="e00fc-183">**A figura abaixo mostra como o NAT altera o endereço IP de destino para o tráfego de entrada e o endereço IP de origem para o tráfego de saída.**</span><span class="sxs-lookup"><span data-stu-id="e00fc-183">**The figure below shows how NAT changes the destination IP address for inbound traffic and the source IP Address for outbound traffic.**</span></span>

<span data-ttu-id="e00fc-184">![Alterando endereços IP de destino/origem](images/Gg425882.0fee7ec5-4cb8-4aff-9164-e7fbab73336d(OCS.15).jpg "Alterando endereços IP de destino/origem")</span><span class="sxs-lookup"><span data-stu-id="e00fc-184">![Changing destination/source IP addresses](images/Gg425882.0fee7ec5-4cb8-4aff-9164-e7fbab73336d(OCS.15).jpg "Changing destination/source IP addresses")</span></span>

<span data-ttu-id="e00fc-185">Os principais pontos são:</span><span class="sxs-lookup"><span data-stu-id="e00fc-185">The key points are:</span></span>

  - <span data-ttu-id="e00fc-186">O tráfego de entrada no servidor que executa o serviço de borda A/V, o endereço IP de origem não é alterado, mas o endereço IP de destino é alterado de 131.107.155.30 para o endereço IP convertido de 10.45.16.10.</span><span class="sxs-lookup"><span data-stu-id="e00fc-186">Traffic that is inbound to the server running the A/V Edge service, the source IP address does not change but the destination IP address changes from 131.107.155.30 to the translated IP address of 10.45.16.10.</span></span>

  - <span data-ttu-id="e00fc-187">Tráfego de saída do servidor que executa o serviço de borda A/V de volta para a estação de trabalho, o endereço IP de origem muda do endereço IP público do servidor para o endereço IP público do servidor que executa o serviço de borda A/V.</span><span class="sxs-lookup"><span data-stu-id="e00fc-187">Traffic that is outbound from the server running the A/V Edge service back to the workstation, the source IP address changes from the server’s public IP address to the public IP address of the server running the A/V Edge service.</span></span> <span data-ttu-id="e00fc-188">O IP de destino permanece no endereço IP público da estação de trabalho.</span><span class="sxs-lookup"><span data-stu-id="e00fc-188">The destination IP remains the workstation’s public IP address.</span></span> <span data-ttu-id="e00fc-189">Depois que o pacote deixa o primeiro dispositivo NAT de saída, a regra no dispositivo NAT altera o endereço IP de origem do servidor que executa o endereço IP da interface externa do serviço de borda A/V (10.45.16.10) para seu endereço IP público (131.107.155.30).</span><span class="sxs-lookup"><span data-stu-id="e00fc-189">After the packet leaves the first NAT device outbound, the rule on the NAT device changes the source IP address of the server running the A/V Edge service external interface IP address (10.45.16.10) to its public IP address (131.107.155.30).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

