---
title: 'Lync Server 2013: escolhendo uma topologia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Choosing a topology
ms:assetid: 23f2aeb6-fed9-4349-8fba-dcbf18ee4b04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425716(v=OCS.15)
ms:contentKeyID: 48183634
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c3a77a37cb9f9c4f92f344988082086834ab3489
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046524"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="choosing-a-topology-in-lync-server-2013"></a><span data-ttu-id="efa04-102">Escolhendo uma topologia no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="efa04-102">Choosing a topology in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span data-ttu-id="efa04-103">_**Última modificação do tópico:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="efa04-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="efa04-104">Ao escolher uma topologia, você pode usar uma das seguintes opções de topologia suportadas:</span><span class="sxs-lookup"><span data-stu-id="efa04-104">When you choose a topology, you can use one the following supported topology options:</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="efa04-105">A menos que indicado de outra forma, se você tiver experiência com o Microsoft Lync Server 2010, você encontrará aqui uma orientação totalmente inalterada.</span><span class="sxs-lookup"><span data-stu-id="efa04-105">Unless otherwise noted, if you have experience with Microsoft Lync Server 2010, you will find the guidance here is largely unchanged.</span></span>



</div>

  - [<span data-ttu-id="efa04-106">Única borda consolidada com endereços IP privados e NAT no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="efa04-106">Single consolidated edge with private IP addresses and NAT in Lync Server 2013</span></span>](lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md)

  - [<span data-ttu-id="efa04-107">Única borda consolidada com endereços IP públicos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="efa04-107">Single consolidated edge with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md)

  - [<span data-ttu-id="efa04-108">Borda consolidada em escala, balanceamento de carga de DNS com endereços IP privados usando NAT no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="efa04-108">Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

  - [<span data-ttu-id="efa04-109">Borda consolidada em escala, balanceamento de carga de DNS com endereços IP públicos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="efa04-109">Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)

  - [<span data-ttu-id="efa04-110">Borda consolidada em escala com balanceadores de carga de hardware no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="efa04-110">Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md)

<div>


> [!IMPORTANT]
> <span data-ttu-id="efa04-p101">A interface de Borda interna e externa devem usar o mesmo tipo de balanceamento de carga. Não é possível usar o balanceamento de carga DNS na interface de Borda e o balanceamento de carga de hardware na outra interface de Borda.</span><span class="sxs-lookup"><span data-stu-id="efa04-p101">The internal Edge interface and external Edge interface must use the same type of load balancing. You cannot use DNS load balancing on one Edge interface and hardware load balancing on the other Edge interface.</span></span>



</div>

<span data-ttu-id="efa04-113">A tabela a seguir resume a funcionalidade disponível com as topologias do Microsoft Lync Server 2013 com suporte.</span><span class="sxs-lookup"><span data-stu-id="efa04-113">The following table summarizes the functionality available with the supported Microsoft Lync Server 2013 topologies.</span></span> <span data-ttu-id="efa04-114">Os títulos de coluna indicam a funcionalidade disponível para uma determinada opção de configuração de borda.</span><span class="sxs-lookup"><span data-stu-id="efa04-114">The column headings indicate the functionality available for a given Edge configuration option.</span></span> <span data-ttu-id="efa04-115">Usando a opção borda em escala (balanceamento de carga DNS) como exemplo, você pode ver que ele oferece suporte à alta disponibilidade, pode usar endereços IP privados não roteáveis (com NAT) ou endereços IP públicos roteáveis atribuídos às interfaces externas de borda e reduz o custo porque um o balanceador de carga de hardware não é necessário.</span><span class="sxs-lookup"><span data-stu-id="efa04-115">Using the Scaled Edge (DNS load balanced) option as an example, you can see that it supports high availability, can use non-routable private IP addresses (with NAT) or routable public IP addresses assigned to the Edge external interfaces, and reduces cost because a hardware load balancer is not required.</span></span>

<span data-ttu-id="efa04-116">Cenários de failover de borda suportados com balanceamento de carga DNS são sessões ponto a ponto do Lync para Lync, sessões de conferência do Lync, sessões do Lync para PSTN e o Office 365.</span><span class="sxs-lookup"><span data-stu-id="efa04-116">Edge failover scenarios supported with DNS Load Balancing are Lync-to-Lync point-to-point sessions, Lync conferencing sessions, Lync-to-PSTN sessions and Office 365.</span></span> <span data-ttu-id="efa04-117">Cenários de failover de borda que não se beneficiam do balanceamento de carga DNS são failover para o usuário remoto Exchange Unified Messaging (UM) (antes do Exchange 2010 SP1), conectividade de IM (mensagens instantâneas públicas) e Federação com servidores executando o Office Communications Do.</span><span class="sxs-lookup"><span data-stu-id="efa04-117">Edge failover scenarios that do not benefit from DNS Load Balancing are failover for remote user Exchange Unified Messaging (UM) (prior to Exchange 2010 SP1), public instant messaging (IM) connectivity, and federation with servers running Office Communications Server.</span></span>

### <a name="summary-of-edge-server-topology-options"></a><span data-ttu-id="efa04-118">Resumo das opções de topologia do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="efa04-118">Summary of Edge Server Topology Options</span></span>

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="efa04-119">Topologia</span><span class="sxs-lookup"><span data-stu-id="efa04-119">Topology</span></span></th>
<th><span data-ttu-id="efa04-120">Alta disponibilidade</span><span class="sxs-lookup"><span data-stu-id="efa04-120">High availability</span></span></th>
<th><span data-ttu-id="efa04-121">Registros DNS A adicionais necessários para servidor de borda externo no pool de borda</span><span class="sxs-lookup"><span data-stu-id="efa04-121">Additional DNS A records required for external Edge Server in the Edge pool</span></span></th>
<th><span data-ttu-id="efa04-122">Failover de borda para sessões do Lync para Lync</span><span class="sxs-lookup"><span data-stu-id="efa04-122">Edge Failover for Lync-to-Lync sessions</span></span></th>
<th><span data-ttu-id="efa04-123">Failover de borda para sessões de Federação do Lync para Lync EUM/PIC/OCS</span><span class="sxs-lookup"><span data-stu-id="efa04-123">Edge Failover for Lync-to-Lync EUM/PIC/OCS Federation sessions</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="efa04-124">Borda única usando NAT</span><span class="sxs-lookup"><span data-stu-id="efa04-124">Single Edge using NAT</span></span></p></td>
<td><p><span data-ttu-id="efa04-125">Não</span><span class="sxs-lookup"><span data-stu-id="efa04-125">No</span></span></p></td>
<td><p><span data-ttu-id="efa04-126">Não</span><span class="sxs-lookup"><span data-stu-id="efa04-126">No</span></span></p></td>
<td><p><span data-ttu-id="efa04-127">Não</span><span class="sxs-lookup"><span data-stu-id="efa04-127">No</span></span></p></td>
<td><p><span data-ttu-id="efa04-128">Não</span><span class="sxs-lookup"><span data-stu-id="efa04-128">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="efa04-129">Borda única usando IP público</span><span class="sxs-lookup"><span data-stu-id="efa04-129">Single Edge using Public IP</span></span></p></td>
<td><p><span data-ttu-id="efa04-130">Não</span><span class="sxs-lookup"><span data-stu-id="efa04-130">No</span></span></p></td>
<td><p><span data-ttu-id="efa04-131">Não</span><span class="sxs-lookup"><span data-stu-id="efa04-131">No</span></span></p></td>
<td><p><span data-ttu-id="efa04-132">Não</span><span class="sxs-lookup"><span data-stu-id="efa04-132">No</span></span></p></td>
<td><p><span data-ttu-id="efa04-133">Não</span><span class="sxs-lookup"><span data-stu-id="efa04-133">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="efa04-134">Borda dimensionada (balanceamento de carga DNS) usando NAT</span><span class="sxs-lookup"><span data-stu-id="efa04-134">Scaled Edge (DNS Load Balanced) using NAT</span></span></p></td>
<td><p><span data-ttu-id="efa04-135">Sim</span><span class="sxs-lookup"><span data-stu-id="efa04-135">Yes</span></span></p></td>
<td><p><span data-ttu-id="efa04-136">Sim</span><span class="sxs-lookup"><span data-stu-id="efa04-136">Yes</span></span></p></td>
<td><p><span data-ttu-id="efa04-137">Sim</span><span class="sxs-lookup"><span data-stu-id="efa04-137">Yes</span></span></p></td>
<td><p>*</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="efa04-138">Borda dimensionada (balanceamento de carga DNS) usando IP público</span><span class="sxs-lookup"><span data-stu-id="efa04-138">Scaled Edge (DNS Load Balanced) using Public IP</span></span></p></td>
<td><p><span data-ttu-id="efa04-139">Sim</span><span class="sxs-lookup"><span data-stu-id="efa04-139">Yes</span></span></p></td>
<td><p><span data-ttu-id="efa04-140">Sim</span><span class="sxs-lookup"><span data-stu-id="efa04-140">Yes</span></span></p></td>
<td><p><span data-ttu-id="efa04-141">Sim</span><span class="sxs-lookup"><span data-stu-id="efa04-141">Yes</span></span></p></td>
<td><p>*</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="efa04-142">Carga balanceada de hardware de borda em escala)</span><span class="sxs-lookup"><span data-stu-id="efa04-142">Scaled Edge Hardware load balanced)</span></span></p></td>
<td><p><span data-ttu-id="efa04-143">Sim</span><span class="sxs-lookup"><span data-stu-id="efa04-143">Yes</span></span></p></td>
<td><p><span data-ttu-id="efa04-144">Não (um registro DNS A por VIP)</span><span class="sxs-lookup"><span data-stu-id="efa04-144">No (one DNS A record per VIP)</span></span></p></td>
<td><p><span data-ttu-id="efa04-145">Sim</span><span class="sxs-lookup"><span data-stu-id="efa04-145">Yes</span></span></p></td>
<td><p><span data-ttu-id="efa04-146">Sim</span><span class="sxs-lookup"><span data-stu-id="efa04-146">Yes</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="efa04-147">**\*** O failover para conectividade de IM (mensagens instantâneas) públicas e a Federação com servidores que executam o Office Communications Server não estão disponíveis com o balanceamento de carga DNS.</span><span class="sxs-lookup"><span data-stu-id="efa04-147">**\*** Failover for public instant messaging (IM) connectivity, and federation with servers running Office Communications Server is not available with DNS load balancing.</span></span> <span data-ttu-id="efa04-148">O failover de UM (usuário remoto) do Exchange usando o balanceamento de carga DNS exige o Exchange Server 2010 SP1 ou mais recente.</span><span class="sxs-lookup"><span data-stu-id="efa04-148">Exchange UM (remote user) failover using DNS load balancing requires Exchange Server 2010 SP1 or newer.</span></span>



> [!NOTE]
> <span data-ttu-id="efa04-149">As topologias de borda única e borda dimensionada (balanceamento de carga DNS) podem usar:</span><span class="sxs-lookup"><span data-stu-id="efa04-149">Single Edge and Scaled Edge (DNS load balanced) topologies can use:</span></span>
> <ul><li><p><span data-ttu-id="efa04-150">Endereços IP públicos roteáveis</span><span class="sxs-lookup"><span data-stu-id="efa04-150">Routable public IP addresses</span></span></p></li>
> <li><p><span data-ttu-id="efa04-151">Endereço IP privado não roteável se a NAT (conversão de endereço de rede simétrica) for usada</span><span class="sxs-lookup"><span data-stu-id="efa04-151">Non-routable private IP address if symmetric network address translation (NAT) is used</span></span></p></li>
>
> <ul><li> <span data-ttu-id="efa04-152">Se você usar o endereço IP público ou o endereço IP privado com NAT, ainda usará o mesmo número de endereços IP com base em sua opção de configuração no construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="efa04-152">If you use public IP address or private IP address with NAT, you will still use the same number of IP addresses based on your configuration choice in Topology Builder.</span></span> <span data-ttu-id="efa04-153">Você pode configurar o servidor de borda para usar um único endereço IP com portas distintas por serviço ou usar endereços IP distintos por serviço, mas usar a mesma porta (por padrão, TCP 443).</span><span class="sxs-lookup"><span data-stu-id="efa04-153">You can configure the Edge Server to use a single IP address with distinct ports per service, or use distinct IP addresses per service, but use the same port (by default, TCP 443).</span></span></li></ul>>
> <span data-ttu-id="efa04-154">Se você decidir usar endereços IP privados não roteáveis com NAT:</span><span class="sxs-lookup"><span data-stu-id="efa04-154">If you decide to use non-routable private IP addresses with NAT:</span></span>
> <ul><li><p><span data-ttu-id="efa04-155">Você deve usar endereços IP privados roteáveis em todas as três interfaces externas</span><span class="sxs-lookup"><span data-stu-id="efa04-155">You must use routable private IP addresses on all three external interfaces</span></span></p></li>
> <li><p><span data-ttu-id="efa04-156">Você deve configurar o NAT simétrico para tráfego de entrada e saída</span><span class="sxs-lookup"><span data-stu-id="efa04-156">You must configure symmetric NAT for incoming and outgoing traffic</span></span></p></li></ul>>
> <span data-ttu-id="efa04-157">A topologia de borda em escala (carga de hardware balanceada) deve usar endereços IP públicos.</span><span class="sxs-lookup"><span data-stu-id="efa04-157">Scaled Edge (hardware load balanced) topology must use public IP addresses.</span></span>



<span data-ttu-id="efa04-158">O Lync Server 2013 oferece suporte à colocação de acesso, Webconferência e interfaces externas de borda A/V por trás de um roteador ou firewall que realiza a conversão de endereços de rede (NAT) para topologias de servidor de borda consolidadas simples e em escala.</span><span class="sxs-lookup"><span data-stu-id="efa04-158">Lync Server 2013 supports placing Access, Web Conferencing, and A/V Edge external interfaces behind a router or firewall that performs network address translation (NAT) for both single and scaled consolidated Edge Server topologies.</span></span>

<span data-ttu-id="efa04-159">Usar NAT para todas as interfaces externas de Borda exige o uso do balanceamento de carga DNS.</span><span class="sxs-lookup"><span data-stu-id="efa04-159">Using NAT for all Edge external interfaces requires the use of DNS load balancing.</span></span> <span data-ttu-id="efa04-160">Quando comparado ao uso de balanceadores de carga de hardware, o uso do balanceamento de carga DNS sem NAT permite reduzir o número de endereços IP públicos por servidor de borda em um pool de borda, conforme descrito na lista a seguir:</span><span class="sxs-lookup"><span data-stu-id="efa04-160">When compared to using hardware load balancers, using DNS load balancing without NAT allows you to reduce the number of public IP address per Edge Server in an Edge pool as described in the following list:</span></span>

  - <span data-ttu-id="efa04-161">Lync Server 2013 a borda consolidada dimensionada (balanceamento de carga DNS) exige três endereços IP públicos para cada servidor de borda em um pool de borda.</span><span class="sxs-lookup"><span data-stu-id="efa04-161">Lync Server 2013 Scaled Consolidated Edge (DNS load balanced) Requires three public IP addresses for each Edge Server in an Edge pool.</span></span>

  - <span data-ttu-id="efa04-162">Lync Server 2013 a borda consolidada dimensionada (carga de hardware balanceada) exige três endereços IP públicos para endereços IP virtuais do balanceador de carga (um requisito de tempo que não aumenta à medida que mais servidores de borda são adicionados ao pool) mais três endereços IP públicos por Servidor de borda em um pool.</span><span class="sxs-lookup"><span data-stu-id="efa04-162">Lync Server 2013 Scaled Consolidated Edge (hardware load balanced) Requires three public IP address for load balancer virtual IP addresses (one time requirement that does not increment as more Edge Servers are added to the pool) plus three public IP addresses per Edge Server in a pool.</span></span>

### <a name="ip-address-requirements-for-scaled-consolidated-edge-ip-address-per-role"></a><span data-ttu-id="efa04-163">Requisitos de endereço IP para borda consolidada em escala (endereço IP por função)</span><span class="sxs-lookup"><span data-stu-id="efa04-163">IP Address Requirements for Scaled Consolidated Edge (IP Address per role)</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="efa04-164">Número de Servidores de Borda por pool</span><span class="sxs-lookup"><span data-stu-id="efa04-164">Number of Edge Servers per pool</span></span></th>
<th><span data-ttu-id="efa04-165">Número de endereços IP necessários Lync Server 2013 (balanceamento de carga DNS)</span><span class="sxs-lookup"><span data-stu-id="efa04-165">Number of required IP addresses Lync Server 2013 (DNS load balanced)</span></span></th>
<th><span data-ttu-id="efa04-166">Número de endereços IP necessários Lync Server 2013 (carga de hardware balanceada)</span><span class="sxs-lookup"><span data-stu-id="efa04-166">Number of required IP addresses Lync Server 2013 (hardware load balanced)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="efa04-167">2 </span><span class="sxs-lookup"><span data-stu-id="efa04-167">2</span></span></p></td>
<td><p><span data-ttu-id="efa04-168">6 </span><span class="sxs-lookup"><span data-stu-id="efa04-168">6</span></span></p></td>
<td><p><span data-ttu-id="efa04-169">3 (1 por VIP) + 6</span><span class="sxs-lookup"><span data-stu-id="efa04-169">3 (1 per VIP) + 6</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="efa04-170">3 </span><span class="sxs-lookup"><span data-stu-id="efa04-170">3</span></span></p></td>
<td><p><span data-ttu-id="efa04-171">9 </span><span class="sxs-lookup"><span data-stu-id="efa04-171">9</span></span></p></td>
<td><p><span data-ttu-id="efa04-172">3 (1 por VIP) + 9</span><span class="sxs-lookup"><span data-stu-id="efa04-172">3 (1 per VIP) + 9</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="efa04-173">4 </span><span class="sxs-lookup"><span data-stu-id="efa04-173">4</span></span></p></td>
<td><p><span data-ttu-id="efa04-174">12 </span><span class="sxs-lookup"><span data-stu-id="efa04-174">12</span></span></p></td>
<td><p><span data-ttu-id="efa04-175">3 (1 por VIP) + 12</span><span class="sxs-lookup"><span data-stu-id="efa04-175">3 (1 per VIP) + 12</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="efa04-176">5 </span><span class="sxs-lookup"><span data-stu-id="efa04-176">5</span></span></p></td>
<td><p><span data-ttu-id="efa04-177">15 </span><span class="sxs-lookup"><span data-stu-id="efa04-177">15</span></span></p></td>
<td><p><span data-ttu-id="efa04-178">3 (1 por VIP) + 15</span><span class="sxs-lookup"><span data-stu-id="efa04-178">3 (1 per VIP) + 15</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="ip-address-requirements-for-scaled-consolidated-edge-single-ip-address-for-all-roles"></a><span data-ttu-id="efa04-179">Requisitos de endereço IP para borda consolidada em escala (endereço IP único para todas as funções)</span><span class="sxs-lookup"><span data-stu-id="efa04-179">IP Address Requirements for Scaled Consolidated Edge (Single IP address for all roles)</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="efa04-180">Número de Servidores de Borda por pool</span><span class="sxs-lookup"><span data-stu-id="efa04-180">Number of Edge Servers per pool</span></span></th>
<th><span data-ttu-id="efa04-181">Número de endereços IP necessários Lync Server 2013 (balanceamento de carga DNS)</span><span class="sxs-lookup"><span data-stu-id="efa04-181">Number of required IP addresses Lync Server 2013 (DNS load balanced)</span></span></th>
<th><span data-ttu-id="efa04-182">Número de endereços IP necessários Lync Server 2013 (carga de hardware balanceada)</span><span class="sxs-lookup"><span data-stu-id="efa04-182">Number of required IP addresses Lync Server 2013 (hardware load balanced)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="efa04-183">2 </span><span class="sxs-lookup"><span data-stu-id="efa04-183">2</span></span></p></td>
<td><p><span data-ttu-id="efa04-184">2 </span><span class="sxs-lookup"><span data-stu-id="efa04-184">2</span></span></p></td>
<td><p><span data-ttu-id="efa04-185">1 (1 por VIP) + 2</span><span class="sxs-lookup"><span data-stu-id="efa04-185">1 (1 per VIP) + 2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="efa04-186">3 </span><span class="sxs-lookup"><span data-stu-id="efa04-186">3</span></span></p></td>
<td><p><span data-ttu-id="efa04-187">3 </span><span class="sxs-lookup"><span data-stu-id="efa04-187">3</span></span></p></td>
<td><p><span data-ttu-id="efa04-188">1 (1 por VIP) + 3</span><span class="sxs-lookup"><span data-stu-id="efa04-188">1 (1 per VIP) + 3</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="efa04-189">4 </span><span class="sxs-lookup"><span data-stu-id="efa04-189">4</span></span></p></td>
<td><p><span data-ttu-id="efa04-190">4 </span><span class="sxs-lookup"><span data-stu-id="efa04-190">4</span></span></p></td>
<td><p><span data-ttu-id="efa04-191">1 (1 por VIP) + 4</span><span class="sxs-lookup"><span data-stu-id="efa04-191">1 (1 per VIP) + 4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="efa04-192">5 </span><span class="sxs-lookup"><span data-stu-id="efa04-192">5</span></span></p></td>
<td><p><span data-ttu-id="efa04-193">0,5</span><span class="sxs-lookup"><span data-stu-id="efa04-193">5</span></span></p></td>
<td><p><span data-ttu-id="efa04-194">1 (1 por VIP) + 5</span><span class="sxs-lookup"><span data-stu-id="efa04-194">1 (1 per VIP) + 5</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="efa04-195">Os principais pontos de decisão para a seleção de topologia são alta disponibilidade e balanceamento de carga.</span><span class="sxs-lookup"><span data-stu-id="efa04-195">The primary decision points for topology selection are high availability and load balancing.</span></span> <span data-ttu-id="efa04-196">O requisito de alta disponibilidade pode influenciar a decisão de balanceamento de carga.</span><span class="sxs-lookup"><span data-stu-id="efa04-196">The requirement for high availability can influence the load balancing decision.</span></span>

  - <span data-ttu-id="efa04-197">**Alta disponibilidade**   Se você precisar de alta disponibilidade, implante pelo menos dois servidores de borda em um pool.</span><span class="sxs-lookup"><span data-stu-id="efa04-197">**High availability**   If you need high availability, deploy at least two Edge Servers in a pool.</span></span> <span data-ttu-id="efa04-198">Um único pool de borda aceitará até doze servidores de borda.</span><span class="sxs-lookup"><span data-stu-id="efa04-198">A single Edge pool will support up to twelve Edge Servers.</span></span> <span data-ttu-id="efa04-199">Se for necessário mais capacidade, você poderá implantar vários pools de borda.</span><span class="sxs-lookup"><span data-stu-id="efa04-199">If more capacity is required, you can deploy multiple Edge pools.</span></span> <span data-ttu-id="efa04-200">Como regra geral, 10% de uma determinada base de usuários precisarão de acesso externo.</span><span class="sxs-lookup"><span data-stu-id="efa04-200">As a general rule, 10% of a given user base will need external access.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="efa04-201">O construtor de topologias permitirá configurar até vinte servidores de borda em um único pool de borda.</span><span class="sxs-lookup"><span data-stu-id="efa04-201">Topology Builder will allow you to configure up to twenty Edge Servers in a single Edge pool.</span></span> <span data-ttu-id="efa04-202">O número máximo de servidores de borda testados e suportados em um pool é de doze e o construtor de topologias que permite um número maior que doze não devem ser interpretados como suporte implícito para mais de doze servidores de borda em um único pool de borda.</span><span class="sxs-lookup"><span data-stu-id="efa04-202">The tested and supported maximum number of Edge Servers in a pool is twelve and Topology Builder allowing for a number larger than twelve should not be construed as implied support for more than twelve Edge Servers in a single Edge pool.</span></span>

    
    </div>

  - <span data-ttu-id="efa04-203">**Balanceamento de carga de hardware**   O balanceamento de carga de hardware tem suporte para balanceamento de carga de servidores de borda do Lync Server 2013 ao usar endereços IP roteáveis publicamente para as interfaces externas de borda.</span><span class="sxs-lookup"><span data-stu-id="efa04-203">**Hardware load balancing**   Hardware load balancing is supported for load balancing Lync Server 2013 Edge Servers when using publicly routable IP addresses for the Edge external interfaces.</span></span> <span data-ttu-id="efa04-204">Por exemplo, você poderia usar essa abordagem em situações em que o failover é necessário para qualquer um dos seguintes aplicativos:</span><span class="sxs-lookup"><span data-stu-id="efa04-204">For example, you would use this approach in situations where failover is required for any of the following applications:</span></span>
    
      - <span data-ttu-id="efa04-205">Conectividade a redes públicas de mensagens instantâneas</span><span class="sxs-lookup"><span data-stu-id="efa04-205">Public IM connectivity</span></span>
    
      - <span data-ttu-id="efa04-206">Federação com empresas que executam o Microsoft Office Communications Server 2007 ou o Microsoft Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="efa04-206">Federation with companies running Microsoft Office Communications Server 2007 or Microsoft Office Communications Server 2007 R2</span></span>
    
      - <span data-ttu-id="efa04-207">Acesso externo à UM (Unificação de mensagens) do Exchange 2007 ou a UM do Exchange 2010</span><span class="sxs-lookup"><span data-stu-id="efa04-207">External access to Exchange 2007 Unified Messaging (UM) or Exchange 2010 UM</span></span>
        
        <div>
        

        > [!IMPORTANT]
        > <span data-ttu-id="efa04-208">O balanceamento de carga DNS para o Exchange 2010 SP1 e mais recente é suportado para UM do Exchange.</span><span class="sxs-lookup"><span data-stu-id="efa04-208">DNS load balancing for Exchange 2010 SP1 and newer is supported for Exchange UM.</span></span>

        
        </div>
    
    <span data-ttu-id="efa04-209">Esses três aplicativos continuarão a funcionar, mas eles não são compatíveis com o balanceamento de carga DNS e só se conectarão ao primeiro servidor de borda no pool.</span><span class="sxs-lookup"><span data-stu-id="efa04-209">These three applications will continue to operate, but they are not DNS load balancing aware and will only connect to the first Edge Server in the pool.</span></span> <span data-ttu-id="efa04-210">Se esse servidor não estiver disponível, a conexão falhará.</span><span class="sxs-lookup"><span data-stu-id="efa04-210">If that server is unavailable, the connection will fail.</span></span> <span data-ttu-id="efa04-211">Por exemplo, se vários servidores de borda são implantados em um pool para lidar com a carga de tráfego federado, apenas um proxy de acesso realmente recebe tráfego enquanto os outros estão ociosos.</span><span class="sxs-lookup"><span data-stu-id="efa04-211">For example, if multiple Edge Servers are deployed in a pool to handle the federated traffic load, only one access proxy actually receives traffic while the others are idle.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="efa04-212">É recomendável usar o balanceamento de carga DNS se você estiver se Federando com empresas que usam o Lync Server 2010 e o Microsoft Office 365.</span><span class="sxs-lookup"><span data-stu-id="efa04-212">Using DNS load balancing is recommended if you are federating with companies using Lync Server 2010 and Microsoft Office 365.</span></span> <span data-ttu-id="efa04-213">Lembre-se de que há impactos significativos no desempenho se a maioria dos seus parceiros federados estiverem usando o Office Communications Server 2007 ou o Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="efa04-213">Be aware that there are significant performance impacts if most of your federated partners are using Office Communications Server 2007 or Office Communications Server 2007 R2.</span></span>



<span data-ttu-id="efa04-214"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="efa04-214"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

