---
title: 'Lync Server 2013: Determinar firewall A/V externo e requisitos de porta'
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
ms.openlocfilehash: 3d5519ef37ff334ddf196e94b40aa7df14d69d25
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762469"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="determine-external-av-firewall-and-port-requirements-for-lync-server-2013"></a><span data-ttu-id="4aa84-102">Determinar firewall A/V externo e requisitos de porta para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4aa84-102">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4aa84-103">_**Tópico da última modificação:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="4aa84-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="4aa84-104">A comunicação de áudio/vídeo (A/V) pode ser um complexo.</span><span class="sxs-lookup"><span data-stu-id="4aa84-104">Audio/Video (A/V) communication can be a complex.</span></span> <span data-ttu-id="4aa84-105">Por causa da natureza dos protocolos usados em A/V e de como os clientes e servidores usam os protocolos, uma seção especial tem a garantia de explicar as diferenças entre as versões do cliente e do servidor.</span><span class="sxs-lookup"><span data-stu-id="4aa84-105">Because of the nature of protocols used in A/V and how clients and servers use the protocols, a special section is warranted to explain the differences between client and server versions.</span></span>

<span data-ttu-id="4aa84-106">Use a seguinte tabela de firewall e porta de A/V para determinar os requisitos de firewall e quais portas abrir.</span><span class="sxs-lookup"><span data-stu-id="4aa84-106">Use the following A/V Firewall and Port table to determine firewall requirements and which ports to open.</span></span> <span data-ttu-id="4aa84-107">Em seguida, examine a terminologia NAT (Network Address Translation) porque a NAT pode ser implementada de muitas maneiras diferentes.</span><span class="sxs-lookup"><span data-stu-id="4aa84-107">Then, review the network address translation (NAT) terminology because NAT can be implemented in many different ways.</span></span> <span data-ttu-id="4aa84-108">Para obter um exemplo detalhado das configurações de porta do firewall, consulte as arquiteturas de referência em [cenários para acesso de usuários externos no Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="4aa84-108">For a detailed example of firewall port settings, see the reference architectures in [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span></span>

### <a name="general-protocol-usage-for-udp-and-tcp-in-audiovideo-and-media-traffic"></a><span data-ttu-id="4aa84-109">Uso de protocolo geral para UDP e TCP em tráfego de áudio/vídeo e mídia</span><span class="sxs-lookup"><span data-stu-id="4aa84-109">General Protocol Usage for UDP and TCP in Audio/Video and Media Traffic</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4aa84-110">Transporte de áudio/vídeo</span><span class="sxs-lookup"><span data-stu-id="4aa84-110">Audio/Video Transport</span></span></th>
<th><span data-ttu-id="4aa84-111">Uso</span><span class="sxs-lookup"><span data-stu-id="4aa84-111">Usage</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4aa84-112">UDP</span><span class="sxs-lookup"><span data-stu-id="4aa84-112">UDP</span></span></p></td>
<td><p><span data-ttu-id="4aa84-113">Protocolo preferencial de camada de transporte para áudio e vídeo</span><span class="sxs-lookup"><span data-stu-id="4aa84-113">Preferred transport layer protocol for audio and video</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4aa84-114">TCP</span><span class="sxs-lookup"><span data-stu-id="4aa84-114">TCP</span></span></p></td>
<td><p><span data-ttu-id="4aa84-115">Protocolo de camada de transporte de fallback para áudio e vídeo</span><span class="sxs-lookup"><span data-stu-id="4aa84-115">Fallback transport layer protocol for audio and video</span></span></p>
<p><span data-ttu-id="4aa84-116">Protocolo de camada de transporte obrigatório para compartilhamento de aplicativos com o Office Communications Server 2007 R2, Lync Server 2010 e Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4aa84-116">Required transport layer protocol for application sharing to Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013</span></span></p>
<p><span data-ttu-id="4aa84-117">Protocolo de camada de transporte necessário para transferência de arquivos para o Lync Server 2010 e Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4aa84-117">Required transport layer protocol for file transfer to Lync Server 2010 and Lync Server 2013</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="external-av-firewall-port-requirements-for-external-user-access"></a><span data-ttu-id="4aa84-118">Requisitos de porta de firewall externo A/V para acesso de usuários externos</span><span class="sxs-lookup"><span data-stu-id="4aa84-118">External A/V Firewall Port Requirements for External User Access</span></span>

<span data-ttu-id="4aa84-119">Os requisitos de porta de firewall para interfaces SIP e de conferência externas (e internas) são consistentes, independentemente da versão do seu cliente ou da versão do parceiro de Federação.</span><span class="sxs-lookup"><span data-stu-id="4aa84-119">The firewall port requirements for external (and internal) SIP and conferencing interfaces are consistent, regardless of the version of your client or the version of the federation partner.</span></span>

<span data-ttu-id="4aa84-120">O mesmo não é válido para a interface externa da borda de áudio/vídeo.</span><span class="sxs-lookup"><span data-stu-id="4aa84-120">The same is not true for the Audio/Video Edge external interface.</span></span> <span data-ttu-id="4aa84-121">Para a Federação com o Office Communications Server 2007, o serviço de borda A/V exige que as regras de firewall externo permitam o tráfego RTP/TCP e RTP/UDP no intervalo de porta 50.000 a 59.999 para fluir nas duas direções.</span><span class="sxs-lookup"><span data-stu-id="4aa84-121">For federation with Office Communications Server 2007, the A/V Edge service requires that external firewall rules allow RTP/TCP and RTP/UDP traffic in the 50,000 through 59,999 port range to flow in both directions.</span></span> <span data-ttu-id="4aa84-122">A tabela anterior pressupõe que o Lync Server 2013 é o parceiro de Federação principal e está sendo configurado para se comunicar com um dos outros tipos de parceiros de Federação listados.</span><span class="sxs-lookup"><span data-stu-id="4aa84-122">The previous table assumes that Lync Server 2013 is the primary federation partner and it is being configured to communicate with one of the other federation partner types listed.</span></span>

<span data-ttu-id="4aa84-123">Configurar o intervalo de porta de áudio/vídeo de 50000-59.999 deve levar em conta que o intervalo de porta conterá as portas de origem para comunicações com os parceiros de Federação.</span><span class="sxs-lookup"><span data-stu-id="4aa84-123">Configuring the Audio/Video port range of 50,000-59,999 must take into account that the port range will contain the source ports for communications to federation partners.</span></span> <span data-ttu-id="4aa84-124">Em detalhes, considere que uma comunicação seja iniciada de um parceiro de Federação.</span><span class="sxs-lookup"><span data-stu-id="4aa84-124">In detail, consider that a communication is initiated from a federation partner.</span></span> <span data-ttu-id="4aa84-125">A comunicação das portas de serviço de borda a/V no intervalo de 50000 59.999 se conectará à porta TCP 443 do serviço de borda A/V do parceiro.</span><span class="sxs-lookup"><span data-stu-id="4aa84-125">The communication from the A/V Edge service ports in the 50,000-59,999 range will connect to the expected port TCP 443 of the partner’s A/V Edge service.</span></span> <span data-ttu-id="4aa84-126">Por outro lado, o tráfego de entrada para a sua porta de serviço de borda A/V TCP 443 terá uma porta de origem no intervalo de 50000 a 59.999.</span><span class="sxs-lookup"><span data-stu-id="4aa84-126">Conversely, inbound traffic to your A/V Edge service port TCP 443 will have a source port in the range of 50,000-59,999.</span></span>

<span data-ttu-id="4aa84-127">Firewalls e políticas diferentes para administração de firewall podem exigir que apenas as regras de destino sejam configuradas ou podem exigir que a origem e o destino sejam configurados.</span><span class="sxs-lookup"><span data-stu-id="4aa84-127">Different firewalls and policies for firewall administration may require only destination rules to be configured, or they may require both source and destination to be configured.</span></span> <span data-ttu-id="4aa84-128">Se seus requisitos são somente para portas de destino, os requisitos de áudio/vídeo são:</span><span class="sxs-lookup"><span data-stu-id="4aa84-128">If your requirements are for destination ports only, the Audio/Video requirements are:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4aa84-129">IP de origem</span><span class="sxs-lookup"><span data-stu-id="4aa84-129">Source IP</span></span></th>
<th><span data-ttu-id="4aa84-130">IP de destino</span><span class="sxs-lookup"><span data-stu-id="4aa84-130">Destination IP</span></span></th>
<th><span data-ttu-id="4aa84-131">Porta de Destino</span><span class="sxs-lookup"><span data-stu-id="4aa84-131">Destination Port</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4aa84-132">Interface de serviço de borda A/V</span><span class="sxs-lookup"><span data-stu-id="4aa84-132">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="4aa84-133">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="4aa84-133">Any</span></span></p></td>
<td><p><span data-ttu-id="4aa84-134">TCP 443</span><span class="sxs-lookup"><span data-stu-id="4aa84-134">TCP 443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4aa84-135">Interface de serviço de borda A/V</span><span class="sxs-lookup"><span data-stu-id="4aa84-135">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="4aa84-136">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="4aa84-136">Any</span></span></p></td>
<td><p><span data-ttu-id="4aa84-137">UDP 3478</span><span class="sxs-lookup"><span data-stu-id="4aa84-137">UDP 3478</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4aa84-138">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="4aa84-138">Any</span></span></p></td>
<td><p><span data-ttu-id="4aa84-139">Interface de serviço de borda A/V</span><span class="sxs-lookup"><span data-stu-id="4aa84-139">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="4aa84-140">TCP 443</span><span class="sxs-lookup"><span data-stu-id="4aa84-140">TCP 443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4aa84-141">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="4aa84-141">Any</span></span></p></td>
<td><p><span data-ttu-id="4aa84-142">Interface de serviço de borda A/V</span><span class="sxs-lookup"><span data-stu-id="4aa84-142">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="4aa84-143">UDP 3478</span><span class="sxs-lookup"><span data-stu-id="4aa84-143">UDP 3478</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="4aa84-144">Se as suas políticas exigirem as definições de regras de firewall de entrada e saída, os requisitos de áudio/vídeo serão:</span><span class="sxs-lookup"><span data-stu-id="4aa84-144">If your policies require both inbound and outbound firewall rule definitions, the Audio/Video requirements are:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4aa84-145">IP de origem</span><span class="sxs-lookup"><span data-stu-id="4aa84-145">Source IP</span></span></th>
<th><span data-ttu-id="4aa84-146">IP de destino</span><span class="sxs-lookup"><span data-stu-id="4aa84-146">Destination IP</span></span></th>
<th><span data-ttu-id="4aa84-147">Porta de origem</span><span class="sxs-lookup"><span data-stu-id="4aa84-147">Source Port</span></span></th>
<th><span data-ttu-id="4aa84-148">Porta de Destino</span><span class="sxs-lookup"><span data-stu-id="4aa84-148">Destination Port</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4aa84-149">Interface de serviço de borda A/V</span><span class="sxs-lookup"><span data-stu-id="4aa84-149">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="4aa84-150">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="4aa84-150">Any</span></span></p></td>
<td><p><span data-ttu-id="4aa84-151">TCP 50.000-59.999</span><span class="sxs-lookup"><span data-stu-id="4aa84-151">TCP 50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="4aa84-152">TCP 443</span><span class="sxs-lookup"><span data-stu-id="4aa84-152">TCP 443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4aa84-153">Interface de serviço de borda A/V</span><span class="sxs-lookup"><span data-stu-id="4aa84-153">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="4aa84-154">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="4aa84-154">Any</span></span></p></td>
<td><p><span data-ttu-id="4aa84-155">UDP 3478</span><span class="sxs-lookup"><span data-stu-id="4aa84-155">UDP 3478</span></span></p></td>
<td><p><span data-ttu-id="4aa84-156">UDP 3478</span><span class="sxs-lookup"><span data-stu-id="4aa84-156">UDP 3478</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4aa84-157">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="4aa84-157">Any</span></span></p></td>
<td><p><span data-ttu-id="4aa84-158">Interface de serviço de borda A/V</span><span class="sxs-lookup"><span data-stu-id="4aa84-158">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="4aa84-159">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="4aa84-159">Any</span></span></p></td>
<td><p><span data-ttu-id="4aa84-160">TCP 443</span><span class="sxs-lookup"><span data-stu-id="4aa84-160">TCP 443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4aa84-161">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="4aa84-161">Any</span></span></p></td>
<td><p><span data-ttu-id="4aa84-162">Interface de serviço de borda A/V</span><span class="sxs-lookup"><span data-stu-id="4aa84-162">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="4aa84-163">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="4aa84-163">Any</span></span></p></td>
<td><p><span data-ttu-id="4aa84-164">UDP 3478</span><span class="sxs-lookup"><span data-stu-id="4aa84-164">UDP 3478</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> <span data-ttu-id="4aa84-165">O Microsoft Office Communications Server 2007 requer uma configuração um pouco diferente.</span><span class="sxs-lookup"><span data-stu-id="4aa84-165">Microsoft Office Communications Server 2007 requires a slightly different configuration.</span></span> <span data-ttu-id="4aa84-166">O intervalo de portas TCP e UDP de 50000-59.999 deve estar aberto em entrada e saída.</span><span class="sxs-lookup"><span data-stu-id="4aa84-166">The TCP and UDP port range of 50,000-59,999 must be open inbound and outbound.</span></span> <span data-ttu-id="4aa84-167">Este requisito é somente para o Office Communicator 2007.</span><span class="sxs-lookup"><span data-stu-id="4aa84-167">This requirement is only for Office Communicator 2007.</span></span> <span data-ttu-id="4aa84-168">O Office Communications Server 2007 R2, o Lync Server 2010 e o Lync Server 2013 exigem somente o intervalo de TCP 50000-59.999 Open outbound.</span><span class="sxs-lookup"><span data-stu-id="4aa84-168">Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013 only require TCP range 50,000-59,999 open outbound.</span></span>



</div>

</div>

<div>

## <a name="nat-requirements-for-the-edge-service"></a><span data-ttu-id="4aa84-169">Requisitos de NAT para o serviço de borda</span><span class="sxs-lookup"><span data-stu-id="4aa84-169">NAT requirements for the Edge service</span></span>

<span data-ttu-id="4aa84-170">Os seguintes requisitos de NAT se aplicam se você optar por configurar endereços IP privados não roteáveis para o serviço de borda:</span><span class="sxs-lookup"><span data-stu-id="4aa84-170">The following NAT requirements apply if you choose to configure non-routable private IP addresses for the Edge service:</span></span>

  - <span data-ttu-id="4aa84-171">O NAT só pode ser usado com balanceamento de carga de DNS.</span><span class="sxs-lookup"><span data-stu-id="4aa84-171">NAT can only be used with DNS load-balancing.</span></span> <span data-ttu-id="4aa84-172">Não há suporte para NAT com uma topologia de borda de HLB (balanceamento de carga de hardware).</span><span class="sxs-lookup"><span data-stu-id="4aa84-172">NAT is not supported with a hardware load balancing (HLB) Edge topology.</span></span>

  - <span data-ttu-id="4aa84-173">O NAT só pode ser usado na interface de borda externa.</span><span class="sxs-lookup"><span data-stu-id="4aa84-173">NAT can only be used on the external Edge interface.</span></span> <span data-ttu-id="4aa84-174">Não há suporte para NAT na interface de borda interna.</span><span class="sxs-lookup"><span data-stu-id="4aa84-174">NAT is not supported on the internal Edge interface.</span></span>

  - <span data-ttu-id="4aa84-175">O NAT deve ser simétrico para o tráfego de entrada e saída.</span><span class="sxs-lookup"><span data-stu-id="4aa84-175">NAT must be symmetric for incoming and outgoing traffic.</span></span>
    
  - <span data-ttu-id="4aa84-176">Para o tráfego da Internet, o NAT deve alterar o endereço IP de destino do endereço IP público compatível com NAT do serviço de borda A/V para seu endereço IP externo.</span><span class="sxs-lookup"><span data-stu-id="4aa84-176">For traffic from the Internet, NAT must change the destination IP address from the NAT-enabled public IP address of the A/V Edge service to its external IP address.</span></span> <span data-ttu-id="4aa84-177">O endereço IP de origem deve permanecer intacto, para que o serviço de borda a/V possa encontrar o caminho de mídia ideal.</span><span class="sxs-lookup"><span data-stu-id="4aa84-177">The source IP address must remain intact, so that the A/V Edge service can find the optimal media path.</span></span>
  
  <span data-ttu-id="4aa84-178">Por exemplo, na direção de entrada na figura abaixo, o endereço de IP público 131.107.155.30 foi alterado para o 10.45.16.10 de endereço IP externo (particular).</span><span class="sxs-lookup"><span data-stu-id="4aa84-178">For example, in the inbound direction in the figure below, the public IP address 131.107.155.30 was changed to the external (private) IP address 10.45.16.10.</span></span> <span data-ttu-id="4aa84-179">O endereço IP de origem permaneceu inalterado.</span><span class="sxs-lookup"><span data-stu-id="4aa84-179">The source IP address remained unchanged.</span></span>
  
  - <span data-ttu-id="4aa84-180">Para o tráfego do serviço de borda a/V para a Internet, o NAT deve alterar o endereço IP de origem do endereço IP externo do serviço de borda a/V para o endereço IP público habilitado para NAT.</span><span class="sxs-lookup"><span data-stu-id="4aa84-180">For traffic from the A/V Edge service to the Internet, NAT must change the source IP address from the external IP address of the A/V Edge service to the NAT-enabled public IP address.</span></span>

<span data-ttu-id="4aa84-181">Por exemplo, na direção de saída na figura abaixo, o endereço IP externo (privado) 10.45.16.10 foi alterado para o endereço IP público 131.107.155.30.</span><span class="sxs-lookup"><span data-stu-id="4aa84-181">For example, in the outbound direction in the figure below, the external (private) IP address 10.45.16.10 was changed to the public IP address 131.107.155.30.</span></span>

<span data-ttu-id="4aa84-182">**A figura a seguir mostra como o NAT altera o endereço IP de destino para o tráfego de entrada e o endereço IP de origem para o tráfego de saída.**</span><span class="sxs-lookup"><span data-stu-id="4aa84-182">**The figure below shows how NAT changes the destination IP address for inbound traffic and the source IP Address for outbound traffic.**</span></span>

<span data-ttu-id="4aa84-183">![Alterar os endereços IP de destino/origem](images/Gg425882.0fee7ec5-4cb8-4aff-9164-e7fbab73336d(OCS.15).jpg "Alterar os endereços IP de destino/origem")</span><span class="sxs-lookup"><span data-stu-id="4aa84-183">![Changing destination/source IP addresses](images/Gg425882.0fee7ec5-4cb8-4aff-9164-e7fbab73336d(OCS.15).jpg "Changing destination/source IP addresses")</span></span>

<span data-ttu-id="4aa84-184">Os principais pontos são:</span><span class="sxs-lookup"><span data-stu-id="4aa84-184">The key points are:</span></span>

  - <span data-ttu-id="4aa84-185">O tráfego que está ligado ao servidor que executa o serviço de borda A/V, o endereço IP de origem não muda, mas o endereço IP de destino muda de 131.107.155.30 para o endereço IP traduzido do 10.45.16.10.</span><span class="sxs-lookup"><span data-stu-id="4aa84-185">Traffic that is inbound to the server running the A/V Edge service, the source IP address does not change but the destination IP address changes from 131.107.155.30 to the translated IP address of 10.45.16.10.</span></span>

  - <span data-ttu-id="4aa84-186">O tráfego de saída do servidor que executa o serviço de borda a/V de volta para a estação de trabalho, o endereço IP de origem muda do endereço IP público do servidor para o endereço IP público do servidor que executa o serviço de borda A/V.</span><span class="sxs-lookup"><span data-stu-id="4aa84-186">Traffic that is outbound from the server running the A/V Edge service back to the workstation, the source IP address changes from the server’s public IP address to the public IP address of the server running the A/V Edge service.</span></span> <span data-ttu-id="4aa84-187">O IP de destino permanece no endereço IP público da estação de trabalho.</span><span class="sxs-lookup"><span data-stu-id="4aa84-187">The destination IP remains the workstation’s public IP address.</span></span> <span data-ttu-id="4aa84-188">Depois que o pacote deixar o primeiro dispositivo NAT de saída, a regra no dispositivo NAT alterará o endereço IP de origem do servidor que executa o endereço IP da interface externa do serviço de borda A/V (10.45.16.10) para o endereço IP público (131.107.155.30).</span><span class="sxs-lookup"><span data-stu-id="4aa84-188">After the packet leaves the first NAT device outbound, the rule on the NAT device changes the source IP address of the server running the A/V Edge service external interface IP address (10.45.16.10) to its public IP address (131.107.155.30).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

