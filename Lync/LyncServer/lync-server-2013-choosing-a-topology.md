---
title: 'Lync Server 2013: Escolhendo uma topologia'
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
ms.openlocfilehash: 0b9f59648d845f37c7cf6d92c471b81a29415753
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729881"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="choosing-a-topology-in-lync-server-2013"></a><span data-ttu-id="f2da3-102">Escolhendo uma topologia no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f2da3-102">Choosing a topology in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span data-ttu-id="f2da3-103">_**Tópico da última modificação:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="f2da3-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="f2da3-104">Ao escolher uma topologia, você pode usar uma das seguintes opções de topologia com suporte:</span><span class="sxs-lookup"><span data-stu-id="f2da3-104">When you choose a topology, you can use one the following supported topology options:</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="f2da3-105">A menos que indicado de outra forma, se você tiver experiência com o Microsoft Lync Server 2010, verá aqui que a orientação é totalmente inalterada.</span><span class="sxs-lookup"><span data-stu-id="f2da3-105">Unless otherwise noted, if you have experience with Microsoft Lync Server 2010, you will find the guidance here is largely unchanged.</span></span>



</div>

  - [<span data-ttu-id="f2da3-106">Única borda consolidada com endereços IP privados e NAT no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f2da3-106">Single consolidated edge with private IP addresses and NAT in Lync Server 2013</span></span>](lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md)

  - [<span data-ttu-id="f2da3-107">Única borda consolidada com endereços IP públicos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f2da3-107">Single consolidated edge with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md)

  - [<span data-ttu-id="f2da3-108">Borda consolidada em escala, balanceamento de carga de DNS com endereços IP privados usando NAT no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f2da3-108">Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

  - [<span data-ttu-id="f2da3-109">Borda consolidada em escala, balanceamento de carga de DNS com endereços IP públicos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f2da3-109">Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)

  - [<span data-ttu-id="f2da3-110">Borda consolidada em escala com balanceadores de carga de hardware no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f2da3-110">Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md)

<div>


> [!IMPORTANT]
> <span data-ttu-id="f2da3-111">As interfaces de Borda interna e externa precisam usar o mesmo tipo de balanceamento de carga.</span><span class="sxs-lookup"><span data-stu-id="f2da3-111">The internal Edge interface and external Edge interface must use the same type of load balancing.</span></span> <span data-ttu-id="f2da3-112">Não é possível usar balanceamento de carga DNS em uma interface de Borda e balanceamento de carga de hardware na outra interface de Borda.</span><span class="sxs-lookup"><span data-stu-id="f2da3-112">You cannot use DNS load balancing on one Edge interface and hardware load balancing on the other Edge interface.</span></span>



</div>

<span data-ttu-id="f2da3-113">A tabela a seguir resume a funcionalidade disponível com as topologias do Microsoft Lync Server 2013 com suporte.</span><span class="sxs-lookup"><span data-stu-id="f2da3-113">The following table summarizes the functionality available with the supported Microsoft Lync Server 2013 topologies.</span></span> <span data-ttu-id="f2da3-114">Os títulos de coluna indicam a funcionalidade disponível para uma determinada opção de configuração de borda.</span><span class="sxs-lookup"><span data-stu-id="f2da3-114">The column headings indicate the functionality available for a given Edge configuration option.</span></span> <span data-ttu-id="f2da3-115">Usando a opção de borda em escala (carga balanceada) como exemplo, você pode ver que ele dá suporte à alta disponibilidade, pode usar endereços IP privados não roteáveis (com NAT) ou endereços IP roteáveis roteáveis atribuídos às interfaces externas de Edge e reduz o custo porque um o balanceador de carga de hardware não é necessário.</span><span class="sxs-lookup"><span data-stu-id="f2da3-115">Using the Scaled Edge (DNS load balanced) option as an example, you can see that it supports high availability, can use non-routable private IP addresses (with NAT) or routable public IP addresses assigned to the Edge external interfaces, and reduces cost because a hardware load balancer is not required.</span></span>

<span data-ttu-id="f2da3-116">Cenários de failover de borda com suporte com balanceamento de carga de DNS são sessões ponto a ponto do Lync para Lync, sessões de conferência do Lync, sessões do Lync para PSTN e do Office 365.</span><span class="sxs-lookup"><span data-stu-id="f2da3-116">Edge failover scenarios supported with DNS Load Balancing are Lync-to-Lync point-to-point sessions, Lync conferencing sessions, Lync-to-PSTN sessions and Office 365.</span></span> <span data-ttu-id="f2da3-117">Cenários de failover de borda que não se beneficiam do balanceamento de carga de DNS são failover para a UM (de uma) (anterior ao Exchange 2010 SP1), a conectividade de mensagens instantâneas públicas (IM) e a Federação com servidores que executam o Office Communications Servidor.</span><span class="sxs-lookup"><span data-stu-id="f2da3-117">Edge failover scenarios that do not benefit from DNS Load Balancing are failover for remote user Exchange Unified Messaging (UM) (prior to Exchange 2010 SP1), public instant messaging (IM) connectivity, and federation with servers running Office Communications Server.</span></span>

### <a name="summary-of-edge-server-topology-options"></a><span data-ttu-id="f2da3-118">Resumo das opções de topologia do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="f2da3-118">Summary of Edge Server Topology Options</span></span>

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
<th><span data-ttu-id="f2da3-119">Topologia</span><span class="sxs-lookup"><span data-stu-id="f2da3-119">Topology</span></span></th>
<th><span data-ttu-id="f2da3-120">Alta disponibilidade</span><span class="sxs-lookup"><span data-stu-id="f2da3-120">High availability</span></span></th>
<th><span data-ttu-id="f2da3-121">Registros DNS adicionais necessários para o servidor de borda externo no pool de bordas</span><span class="sxs-lookup"><span data-stu-id="f2da3-121">Additional DNS A records required for external Edge Server in the Edge pool</span></span></th>
<th><span data-ttu-id="f2da3-122">Failover de borda para sessões do Lync para o Lync</span><span class="sxs-lookup"><span data-stu-id="f2da3-122">Edge Failover for Lync-to-Lync sessions</span></span></th>
<th><span data-ttu-id="f2da3-123">Failover de borda para sessões de Federação do Lync-to-Lync do EUM/PIC/OCS</span><span class="sxs-lookup"><span data-stu-id="f2da3-123">Edge Failover for Lync-to-Lync EUM/PIC/OCS Federation sessions</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f2da3-124">Borda única usando NAT</span><span class="sxs-lookup"><span data-stu-id="f2da3-124">Single Edge using NAT</span></span></p></td>
<td><p><span data-ttu-id="f2da3-125">Não</span><span class="sxs-lookup"><span data-stu-id="f2da3-125">No</span></span></p></td>
<td><p><span data-ttu-id="f2da3-126">Não</span><span class="sxs-lookup"><span data-stu-id="f2da3-126">No</span></span></p></td>
<td><p><span data-ttu-id="f2da3-127">Não</span><span class="sxs-lookup"><span data-stu-id="f2da3-127">No</span></span></p></td>
<td><p><span data-ttu-id="f2da3-128">Não</span><span class="sxs-lookup"><span data-stu-id="f2da3-128">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2da3-129">Borda única usando IP público</span><span class="sxs-lookup"><span data-stu-id="f2da3-129">Single Edge using Public IP</span></span></p></td>
<td><p><span data-ttu-id="f2da3-130">Não</span><span class="sxs-lookup"><span data-stu-id="f2da3-130">No</span></span></p></td>
<td><p><span data-ttu-id="f2da3-131">Não</span><span class="sxs-lookup"><span data-stu-id="f2da3-131">No</span></span></p></td>
<td><p><span data-ttu-id="f2da3-132">Não</span><span class="sxs-lookup"><span data-stu-id="f2da3-132">No</span></span></p></td>
<td><p><span data-ttu-id="f2da3-133">Não</span><span class="sxs-lookup"><span data-stu-id="f2da3-133">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2da3-134">Borda em escala (balanceamento de carga de DNS) usando NAT</span><span class="sxs-lookup"><span data-stu-id="f2da3-134">Scaled Edge (DNS Load Balanced) using NAT</span></span></p></td>
<td><p><span data-ttu-id="f2da3-135">Sim</span><span class="sxs-lookup"><span data-stu-id="f2da3-135">Yes</span></span></p></td>
<td><p><span data-ttu-id="f2da3-136">Sim</span><span class="sxs-lookup"><span data-stu-id="f2da3-136">Yes</span></span></p></td>
<td><p><span data-ttu-id="f2da3-137">Sim</span><span class="sxs-lookup"><span data-stu-id="f2da3-137">Yes</span></span></p></td>
<td><p>*</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2da3-138">Borda em escala (carga de DNS balanceada) usando o IP público</span><span class="sxs-lookup"><span data-stu-id="f2da3-138">Scaled Edge (DNS Load Balanced) using Public IP</span></span></p></td>
<td><p><span data-ttu-id="f2da3-139">Sim</span><span class="sxs-lookup"><span data-stu-id="f2da3-139">Yes</span></span></p></td>
<td><p><span data-ttu-id="f2da3-140">Sim</span><span class="sxs-lookup"><span data-stu-id="f2da3-140">Yes</span></span></p></td>
<td><p><span data-ttu-id="f2da3-141">Sim</span><span class="sxs-lookup"><span data-stu-id="f2da3-141">Yes</span></span></p></td>
<td><p>*</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2da3-142">Carga balanceada do hardware de borda em escala)</span><span class="sxs-lookup"><span data-stu-id="f2da3-142">Scaled Edge Hardware load balanced)</span></span></p></td>
<td><p><span data-ttu-id="f2da3-143">Sim</span><span class="sxs-lookup"><span data-stu-id="f2da3-143">Yes</span></span></p></td>
<td><p><span data-ttu-id="f2da3-144">Não (um registro DNS A por VIP)</span><span class="sxs-lookup"><span data-stu-id="f2da3-144">No (one DNS A record per VIP)</span></span></p></td>
<td><p><span data-ttu-id="f2da3-145">Sim</span><span class="sxs-lookup"><span data-stu-id="f2da3-145">Yes</span></span></p></td>
<td><p><span data-ttu-id="f2da3-146">Sim</span><span class="sxs-lookup"><span data-stu-id="f2da3-146">Yes</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="f2da3-147">**\*** O failover para conectividade de mensagens instantâneas públicas (IM) e Federação com servidores que executam o Office Communications Server não está disponível com balanceamento de carga de DNS.</span><span class="sxs-lookup"><span data-stu-id="f2da3-147">**\*** Failover for public instant messaging (IM) connectivity, and federation with servers running Office Communications Server is not available with DNS load balancing.</span></span> <span data-ttu-id="f2da3-148">O failover de UM (usuário remoto) do Exchange usando o balanceamento de carga de DNS exige o Exchange Server 2010 SP1 ou versão mais recente.</span><span class="sxs-lookup"><span data-stu-id="f2da3-148">Exchange UM (remote user) failover using DNS load balancing requires Exchange Server 2010 SP1 or newer.</span></span>



> [!NOTE]
> <span data-ttu-id="f2da3-149">As topologias de borda única e de borda em escala (carga DNS balanceada) podem usar:</span><span class="sxs-lookup"><span data-stu-id="f2da3-149">Single Edge and Scaled Edge (DNS load balanced) topologies can use:</span></span>
> <ul><li><p><span data-ttu-id="f2da3-150">Endereços IP públicos roteáveis</span><span class="sxs-lookup"><span data-stu-id="f2da3-150">Routable public IP addresses</span></span></p></li>
> <li><p><span data-ttu-id="f2da3-151">Endereço IP privado não roteável se a NAT (conversão de endereços de rede) simétrica for usada</span><span class="sxs-lookup"><span data-stu-id="f2da3-151">Non-routable private IP address if symmetric network address translation (NAT) is used</span></span></p></li>
>
> <ul><li> <span data-ttu-id="f2da3-152">Se você usar o endereço IP público ou o endereço IP privado com NAT, ainda usará o mesmo número de endereços IP com base em sua opção de configuração no construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="f2da3-152">If you use public IP address or private IP address with NAT, you will still use the same number of IP addresses based on your configuration choice in Topology Builder.</span></span> <span data-ttu-id="f2da3-153">Você pode configurar o servidor de borda para usar um único endereço IP com portas distintas por serviço ou usar endereços IP distintos por serviço, mas usar a mesma porta (por padrão, TCP 443).</span><span class="sxs-lookup"><span data-stu-id="f2da3-153">You can configure the Edge Server to use a single IP address with distinct ports per service, or use distinct IP addresses per service, but use the same port (by default, TCP 443).</span></span></li></ul>>
> <span data-ttu-id="f2da3-154">Se você decidir usar endereços IP privados não roteáveis com NAT:</span><span class="sxs-lookup"><span data-stu-id="f2da3-154">If you decide to use non-routable private IP addresses with NAT:</span></span>
> <ul><li><p><span data-ttu-id="f2da3-155">Você deve usar endereços IP particulares roteáveis em todas as três interfaces externas</span><span class="sxs-lookup"><span data-stu-id="f2da3-155">You must use routable private IP addresses on all three external interfaces</span></span></p></li>
> <li><p><span data-ttu-id="f2da3-156">Você deve configurar o NAT simétrico para tráfego de entrada e saída</span><span class="sxs-lookup"><span data-stu-id="f2da3-156">You must configure symmetric NAT for incoming and outgoing traffic</span></span></p></li></ul>>
> <span data-ttu-id="f2da3-157">A topologia de borda em escala (carga de hardware balanceada) deve usar endereços IP públicos.</span><span class="sxs-lookup"><span data-stu-id="f2da3-157">Scaled Edge (hardware load balanced) topology must use public IP addresses.</span></span>



<span data-ttu-id="f2da3-158">O Lync Server 2013 dá suporte à colocação de acesso, Webconferência e A/V de interfaces externas atrás de um roteador ou firewall que executa a NAT (conversão de endereços de rede) para topologias de servidor de borda consolidadas simples e em escala.</span><span class="sxs-lookup"><span data-stu-id="f2da3-158">Lync Server 2013 supports placing Access, Web Conferencing, and A/V Edge external interfaces behind a router or firewall that performs network address translation (NAT) for both single and scaled consolidated Edge Server topologies.</span></span>

<span data-ttu-id="f2da3-159">Usar NAT para todas as interfaces externas Edge requer o uso de balanceamento de carga de DNS.</span><span class="sxs-lookup"><span data-stu-id="f2da3-159">Using NAT for all Edge external interfaces requires the use of DNS load balancing.</span></span> <span data-ttu-id="f2da3-160">Quando comparado ao uso de balanceadores de carga de hardware, o uso de balanceamento de carga de DNS sem NAT permite reduzir o número de endereços IP públicos por servidor de borda em um pool de bordas conforme descrito na lista a seguir:</span><span class="sxs-lookup"><span data-stu-id="f2da3-160">When compared to using hardware load balancers, using DNS load balancing without NAT allows you to reduce the number of public IP address per Edge Server in an Edge pool as described in the following list:</span></span>

  - <span data-ttu-id="f2da3-161">O Lync Server 2013 a borda consolidada dimensionada (carga de DNS balanceada) requer três endereços IP públicos para cada servidor de borda em um pool de bordas.</span><span class="sxs-lookup"><span data-stu-id="f2da3-161">Lync Server 2013 Scaled Consolidated Edge (DNS load balanced) Requires three public IP addresses for each Edge Server in an Edge pool.</span></span>

  - <span data-ttu-id="f2da3-162">A borda consolidada do Lync Server 2013 redimensionada (carga de hardware balanceada) requer três endereços IP públicos para endereços IP virtuais do balanceador de carga (um requisito de tempo que não aumenta à medida que mais servidores de borda são adicionados ao pool) e três endereços IP públicos por Servidor de borda em um pool.</span><span class="sxs-lookup"><span data-stu-id="f2da3-162">Lync Server 2013 Scaled Consolidated Edge (hardware load balanced) Requires three public IP address for load balancer virtual IP addresses (one time requirement that does not increment as more Edge Servers are added to the pool) plus three public IP addresses per Edge Server in a pool.</span></span>

### <a name="ip-address-requirements-for-scaled-consolidated-edge-ip-address-per-role"></a><span data-ttu-id="f2da3-163">Requisitos de endereço IP para borda consolidada em escala (endereço IP por função)</span><span class="sxs-lookup"><span data-stu-id="f2da3-163">IP Address Requirements for Scaled Consolidated Edge (IP Address per role)</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f2da3-164">Número de servidores de borda por pool</span><span class="sxs-lookup"><span data-stu-id="f2da3-164">Number of Edge Servers per pool</span></span></th>
<th><span data-ttu-id="f2da3-165">Número de endereços IP necessários Lync Server 2013 (DNS Load Balanced)</span><span class="sxs-lookup"><span data-stu-id="f2da3-165">Number of required IP addresses Lync Server 2013 (DNS load balanced)</span></span></th>
<th><span data-ttu-id="f2da3-166">Número de endereços IP necessários Lync Server 2013 (hardware com balanceamento de carga)</span><span class="sxs-lookup"><span data-stu-id="f2da3-166">Number of required IP addresses Lync Server 2013 (hardware load balanced)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f2da3-167">2</span><span class="sxs-lookup"><span data-stu-id="f2da3-167">2</span></span></p></td>
<td><p><span data-ttu-id="f2da3-168">6</span><span class="sxs-lookup"><span data-stu-id="f2da3-168">6</span></span></p></td>
<td><p><span data-ttu-id="f2da3-169">3 (1 por VIP) + 6</span><span class="sxs-lookup"><span data-stu-id="f2da3-169">3 (1 per VIP) + 6</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2da3-170">3</span><span class="sxs-lookup"><span data-stu-id="f2da3-170">3</span></span></p></td>
<td><p><span data-ttu-id="f2da3-171">9</span><span class="sxs-lookup"><span data-stu-id="f2da3-171">9</span></span></p></td>
<td><p><span data-ttu-id="f2da3-172">3 (1 por VIP) + 9</span><span class="sxs-lookup"><span data-stu-id="f2da3-172">3 (1 per VIP) + 9</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2da3-173">4</span><span class="sxs-lookup"><span data-stu-id="f2da3-173">4</span></span></p></td>
<td><p><span data-ttu-id="f2da3-174">12</span><span class="sxs-lookup"><span data-stu-id="f2da3-174">12</span></span></p></td>
<td><p><span data-ttu-id="f2da3-175">3 (1 por VIP) + 12</span><span class="sxs-lookup"><span data-stu-id="f2da3-175">3 (1 per VIP) + 12</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2da3-176">5</span><span class="sxs-lookup"><span data-stu-id="f2da3-176">5</span></span></p></td>
<td><p><span data-ttu-id="f2da3-177">15</span><span class="sxs-lookup"><span data-stu-id="f2da3-177">15</span></span></p></td>
<td><p><span data-ttu-id="f2da3-178">3 (1 por VIP) + 15</span><span class="sxs-lookup"><span data-stu-id="f2da3-178">3 (1 per VIP) + 15</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="ip-address-requirements-for-scaled-consolidated-edge-single-ip-address-for-all-roles"></a><span data-ttu-id="f2da3-179">Requisitos de endereço IP para borda consolidada em escala (endereço IP único para todas as funções)</span><span class="sxs-lookup"><span data-stu-id="f2da3-179">IP Address Requirements for Scaled Consolidated Edge (Single IP address for all roles)</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f2da3-180">Número de servidores de borda por pool</span><span class="sxs-lookup"><span data-stu-id="f2da3-180">Number of Edge Servers per pool</span></span></th>
<th><span data-ttu-id="f2da3-181">Número de endereços IP necessários Lync Server 2013 (DNS Load Balanced)</span><span class="sxs-lookup"><span data-stu-id="f2da3-181">Number of required IP addresses Lync Server 2013 (DNS load balanced)</span></span></th>
<th><span data-ttu-id="f2da3-182">Número de endereços IP necessários Lync Server 2013 (hardware com balanceamento de carga)</span><span class="sxs-lookup"><span data-stu-id="f2da3-182">Number of required IP addresses Lync Server 2013 (hardware load balanced)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f2da3-183">2</span><span class="sxs-lookup"><span data-stu-id="f2da3-183">2</span></span></p></td>
<td><p><span data-ttu-id="f2da3-184">2</span><span class="sxs-lookup"><span data-stu-id="f2da3-184">2</span></span></p></td>
<td><p><span data-ttu-id="f2da3-185">1 (1 por VIP) + 2</span><span class="sxs-lookup"><span data-stu-id="f2da3-185">1 (1 per VIP) + 2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2da3-186">3</span><span class="sxs-lookup"><span data-stu-id="f2da3-186">3</span></span></p></td>
<td><p><span data-ttu-id="f2da3-187">3</span><span class="sxs-lookup"><span data-stu-id="f2da3-187">3</span></span></p></td>
<td><p><span data-ttu-id="f2da3-188">1 (1 por VIP) + 3</span><span class="sxs-lookup"><span data-stu-id="f2da3-188">1 (1 per VIP) + 3</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2da3-189">4</span><span class="sxs-lookup"><span data-stu-id="f2da3-189">4</span></span></p></td>
<td><p><span data-ttu-id="f2da3-190">4</span><span class="sxs-lookup"><span data-stu-id="f2da3-190">4</span></span></p></td>
<td><p><span data-ttu-id="f2da3-191">1 (1 por VIP) + 4</span><span class="sxs-lookup"><span data-stu-id="f2da3-191">1 (1 per VIP) + 4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2da3-192">5</span><span class="sxs-lookup"><span data-stu-id="f2da3-192">5</span></span></p></td>
<td><p><span data-ttu-id="f2da3-193">5</span><span class="sxs-lookup"><span data-stu-id="f2da3-193">5</span></span></p></td>
<td><p><span data-ttu-id="f2da3-194">1 (1 por VIP) + 5</span><span class="sxs-lookup"><span data-stu-id="f2da3-194">1 (1 per VIP) + 5</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="f2da3-195">Os principais pontos de decisão para a seleção de topologia são alta disponibilidade e balanceamento de carga.</span><span class="sxs-lookup"><span data-stu-id="f2da3-195">The primary decision points for topology selection are high availability and load balancing.</span></span> <span data-ttu-id="f2da3-196">O requisito para alta disponibilidade pode influenciar a decisão de balanceamento de carga.</span><span class="sxs-lookup"><span data-stu-id="f2da3-196">The requirement for high availability can influence the load balancing decision.</span></span>

  - <span data-ttu-id="f2da3-197">**Alta disponibilidade**   Se precisar de alta disponibilidade, implante pelo menos dois servidores de borda em um pool.</span><span class="sxs-lookup"><span data-stu-id="f2da3-197">**High availability**   If you need high availability, deploy at least two Edge Servers in a pool.</span></span> <span data-ttu-id="f2da3-198">Um único pool de bordas dará suporte a até doze servidores de borda.</span><span class="sxs-lookup"><span data-stu-id="f2da3-198">A single Edge pool will support up to twelve Edge Servers.</span></span> <span data-ttu-id="f2da3-199">Se for necessário mais capacidade, você poderá implantar vários pools de bordas.</span><span class="sxs-lookup"><span data-stu-id="f2da3-199">If more capacity is required, you can deploy multiple Edge pools.</span></span> <span data-ttu-id="f2da3-200">Como regra geral, 10% de uma determinada base de usuários precisará de acesso externo.</span><span class="sxs-lookup"><span data-stu-id="f2da3-200">As a general rule, 10% of a given user base will need external access.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="f2da3-201">O construtor de topologias permitirá configurar até vinte servidores de borda em um único pool de bordas.</span><span class="sxs-lookup"><span data-stu-id="f2da3-201">Topology Builder will allow you to configure up to twenty Edge Servers in a single Edge pool.</span></span> <span data-ttu-id="f2da3-202">O número máximo de servidores de borda testados e com suporte em um pool é de doze e o construtor de topologias que permite que um número maior que doze não seja interpretado como suporte implícito para mais de doze servidores de extremidade em um único pool de bordas.</span><span class="sxs-lookup"><span data-stu-id="f2da3-202">The tested and supported maximum number of Edge Servers in a pool is twelve and Topology Builder allowing for a number larger than twelve should not be construed as implied support for more than twelve Edge Servers in a single Edge pool.</span></span>

    
    </div>

  - <span data-ttu-id="f2da3-203">**Balanceamento de carga de hardware**   O balanceamento de carga de hardware tem suporte para os servidores de borda do Lync Server 2013 de balanceamento de carga ao usar endereços IP roteáveis publicamente para as interfaces externas de Edge.</span><span class="sxs-lookup"><span data-stu-id="f2da3-203">**Hardware load balancing**   Hardware load balancing is supported for load balancing Lync Server 2013 Edge Servers when using publicly routable IP addresses for the Edge external interfaces.</span></span> <span data-ttu-id="f2da3-204">Por exemplo, você usaria essa abordagem em situações em que o failover é necessário para qualquer um dos seguintes aplicativos:</span><span class="sxs-lookup"><span data-stu-id="f2da3-204">For example, you would use this approach in situations where failover is required for any of the following applications:</span></span>
    
      - <span data-ttu-id="f2da3-205">Conectividade de mensagem de chat Pública</span><span class="sxs-lookup"><span data-stu-id="f2da3-205">Public IM connectivity</span></span>
    
      - <span data-ttu-id="f2da3-206">Federação com empresas que executam o Microsoft Office Communications Server 2007 ou o Microsoft Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="f2da3-206">Federation with companies running Microsoft Office Communications Server 2007 or Microsoft Office Communications Server 2007 R2</span></span>
    
      - <span data-ttu-id="f2da3-207">Acesso externo ao Exchange 2007 Unified Messaging (UM) ou ao Exchange 2010 UM</span><span class="sxs-lookup"><span data-stu-id="f2da3-207">External access to Exchange 2007 Unified Messaging (UM) or Exchange 2010 UM</span></span>
        
        <div>
        

        > [!IMPORTANT]
        > <span data-ttu-id="f2da3-208">O balanceamento de carga de DNS para Exchange 2010 SP1 e versão mais recente tem suporte para o Exchange UM.</span><span class="sxs-lookup"><span data-stu-id="f2da3-208">DNS load balancing for Exchange 2010 SP1 and newer is supported for Exchange UM.</span></span>

        
        </div>
    
    <span data-ttu-id="f2da3-209">Esses três aplicativos continuarão funcionando, mas não são compatíveis com balanceamento de carga de DNS e só se conectam ao primeiro servidor de borda do pool.</span><span class="sxs-lookup"><span data-stu-id="f2da3-209">These three applications will continue to operate, but they are not DNS load balancing aware and will only connect to the first Edge Server in the pool.</span></span> <span data-ttu-id="f2da3-210">Se esse servidor estiver indisponível, a conexão não será bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="f2da3-210">If that server is unavailable, the connection will fail.</span></span> <span data-ttu-id="f2da3-211">Por exemplo, se vários servidores de borda forem implantados em um pool para manipular a carga de tráfego federado, apenas um proxy de acesso realmente receberá o tráfego enquanto as outras estiverem ociosas.</span><span class="sxs-lookup"><span data-stu-id="f2da3-211">For example, if multiple Edge Servers are deployed in a pool to handle the federated traffic load, only one access proxy actually receives traffic while the others are idle.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="f2da3-212">Usar o balanceamento de carga de DNS é recomendado se você estiver fazendo a Federação com empresas que usam o Lync Server 2010 e o Microsoft Office 365.</span><span class="sxs-lookup"><span data-stu-id="f2da3-212">Using DNS load balancing is recommended if you are federating with companies using Lync Server 2010 and Microsoft Office 365.</span></span> <span data-ttu-id="f2da3-213">Lembre-se de que há impactos significativos no desempenho se a maioria dos seus parceiros federados estiver usando o Office Communications Server 2007 ou o Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="f2da3-213">Be aware that there are significant performance impacts if most of your federated partners are using Office Communications Server 2007 or Office Communications Server 2007 R2.</span></span>



<span data-ttu-id="f2da3-214"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="f2da3-214"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

