---
title: 'Lync Server 2013: Resumo de DNS - Borda consolidada em escala, balanceamento de carga de DNS com endereços IP públicos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Scaled consolidated edge, DNS load balancing with public IP addresses
ms:assetid: dc8f096a-a0a4-4f71-8930-88ff8fc089d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205319(v=OCS.15)
ms:contentKeyID: 48185594
ms.date: 03/09/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3f748f8107e4d1c0da41a07285eb61e4a3149551
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737181"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses-in-lync-server-2013"></a><span data-ttu-id="8aa18-102">Resumo de DNS - Borda consolidada em escala, balanceamento de carga de DNS com endereços IP públicos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8aa18-102">DNS summary - Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8aa18-103">_**Tópico da última modificação:** 2017-03-09_</span><span class="sxs-lookup"><span data-stu-id="8aa18-103">_**Topic Last Modified:** 2017-03-09_</span></span>

<span data-ttu-id="8aa18-104">Os requisitos de registro de DNS para acesso remoto ao Lync Server 2013 são bem simples em comparação com aqueles para certificados e portas.</span><span class="sxs-lookup"><span data-stu-id="8aa18-104">DNS record requirements for remote access to Lync Server 2013 are fairly straightforward compared to those for certificates and ports.</span></span> <span data-ttu-id="8aa18-105">Além disso, muitos registros são opcionais, dependendo de como você configura os clientes que executam o Lync 2013 e se você habilita a Federação.</span><span class="sxs-lookup"><span data-stu-id="8aa18-105">Also, many records are optional, depending on how you configure clients running Lync 2013 and whether you enable federation.</span></span>

<span data-ttu-id="8aa18-106">Para obter detalhes sobre os requisitos de DNS do Lync 2013, consulte [determinar requisitos de DNS para o Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8aa18-106">For details about Lync 2013 DNS requirements, see [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="8aa18-107">Para obter detalhes sobre como configurar a configuração automática de clientes do Lync 2013 se a divisão do DNS não estiver configurada, consulte a seção "configuração automática sem DNS de Brain" em [determinar requisitos de DNS para o Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8aa18-107">For details about configuring automatic configuration of Lync 2013 clients if split-brain DNS is not configured, see the "Automatic Configuration without Split Brain DNS" section in [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="8aa18-108">A tabela a seguir contém um resumo dos registros DNS necessários para dar suporte à topologia de borda consolidada única mostrada na figura única de topologia de borda consolidada.</span><span class="sxs-lookup"><span data-stu-id="8aa18-108">The following table contains a summary of the DNS records that are required to support the single consolidated edge topology shown in the Single Consolidated Edge Topology figure.</span></span> <span data-ttu-id="8aa18-109">Observe que determinados registros DNS são necessários somente para a configuração automática de clientes do Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="8aa18-109">Note that certain DNS records are required only for automatic configuration of Lync 2013 clients.</span></span> <span data-ttu-id="8aa18-110">Se você pretende usar objetos de política de grupo (GPOs) para configurar os clientes do Lync, os registros associados não são necessários.</span><span class="sxs-lookup"><span data-stu-id="8aa18-110">If you plan to use group policy objects (GPOs) to configure Lync clients, the associated records are not necessary.</span></span>

<div>

## <a name="important-edge-server-network-adapter-requirements"></a><span data-ttu-id="8aa18-111">IMPORTANTE: requisitos do adaptador de rede do Edge Server</span><span class="sxs-lookup"><span data-stu-id="8aa18-111">IMPORTANT: Edge Server Network Adapter Requirements</span></span>

<span data-ttu-id="8aa18-112">Para evitar problemas de roteamento, verifique se há pelo menos dois adaptadores de rede em seus servidores de borda e se o gateway padrão está definido somente no adaptador de rede associado à interface externa.</span><span class="sxs-lookup"><span data-stu-id="8aa18-112">To avoid routing issues, verify that there are at least two network adapters in your Edge Servers and that the default gateway is set only on the network adapter associated with the external interface.</span></span> <span data-ttu-id="8aa18-113">Por exemplo, conforme mostrado na figura de cenário de borda consolidada dimensionada na [borda consolidada dimensionada, o balanceamento de carga de DNS com endereços IP públicos no Lync Server 2013](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md) , o gateway padrão apontaria para o firewall externo.</span><span class="sxs-lookup"><span data-stu-id="8aa18-113">For example, as shown in the Scaled Consolidated Edge Scenario figure in [Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md) , the default gateway would point to the external firewall.</span></span>

<span data-ttu-id="8aa18-114">Você pode configurar dois adaptadores de rede em cada um dos seus servidores de borda da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="8aa18-114">You can configure two network adapters in each of your Edge Server as follows:</span></span>

  - <span data-ttu-id="8aa18-115">**Adaptador de rede 1-nó 1 (interface interna)**</span><span class="sxs-lookup"><span data-stu-id="8aa18-115">**Network adapter 1 - Node 1 (Internal Interface)**</span></span>
    
    <span data-ttu-id="8aa18-116">Interface interna com 172.25.33.10 atribuído.</span><span class="sxs-lookup"><span data-stu-id="8aa18-116">Internal interface with 172.25.33.10 assigned.</span></span>
    
    <span data-ttu-id="8aa18-117">Não há nenhum gateway padrão definido.</span><span class="sxs-lookup"><span data-stu-id="8aa18-117">No default gateway is defined.</span></span>
    
    <span data-ttu-id="8aa18-118">Verifique se há uma rota da rede que contém a interface interna de borda para qualquer rede que contenha servidores que estejam executando o Lync Server 2013 ou o Lync Server 2013 clientes (por exemplo, de 172.25.33.0 para 192.168.10.0).</span><span class="sxs-lookup"><span data-stu-id="8aa18-118">Ensure that there is a route from the network containing the Edge internal interface to any networks that contain servers running Lync Server 2013 or Lync Server 2013 clients (for example, from 172.25.33.0 to 192.168.10.0).</span></span>

  - <span data-ttu-id="8aa18-119">**Adaptador de rede 1-nó 2 (interface interna)**</span><span class="sxs-lookup"><span data-stu-id="8aa18-119">**Network adapter 1 - Node 2 (Internal Interface)**</span></span>
    
    <span data-ttu-id="8aa18-120">Interface interna com 172.25.33.11 atribuído.</span><span class="sxs-lookup"><span data-stu-id="8aa18-120">Internal interface with 172.25.33.11 assigned.</span></span>
    
    <span data-ttu-id="8aa18-121">Não há nenhum gateway padrão definido.</span><span class="sxs-lookup"><span data-stu-id="8aa18-121">No default gateway is defined.</span></span>
    
    <span data-ttu-id="8aa18-122">Verifique se há uma rota da rede que contém a interface interna de borda para qualquer rede que contenha servidores que estejam executando o Lync Server 2013 ou o Lync Server 2013 clientes (por exemplo, de 172.25.33.0 para 192.168.10.0).</span><span class="sxs-lookup"><span data-stu-id="8aa18-122">Ensure that there is a route from the network containing the Edge internal interface to any networks that contain servers running Lync Server 2013 or Lync Server 2013 clients (for example, from 172.25.33.0 to 192.168.10.0).</span></span>

  - <span data-ttu-id="8aa18-123">**Adaptador de rede 2 nó 1 (interface externa)**</span><span class="sxs-lookup"><span data-stu-id="8aa18-123">**Network adapter 2 Node 1 (External Interface)**</span></span>
    
    <span data-ttu-id="8aa18-124">Três endereços IP privados são atribuídos a esse adaptador de rede, por exemplo, 131.107.155.10 para serviço de borda de acesso, 131.107.155.20 para serviço de borda de webconferência, 131.107.155.30 para o serviço de borda A/V.</span><span class="sxs-lookup"><span data-stu-id="8aa18-124">Three private IP addresses are assigned to this network adapter, for example 131.107.155.10 for Access Edge service, 131.107.155.20 for Web Conferencing Edge service, 131.107.155.30 for A/V Edge service.</span></span>
    
    <span data-ttu-id="8aa18-125">O endereço IP público do serviço de borda do Access é primário com o gateway padrão definido para o roteador público (131.107.155.1).</span><span class="sxs-lookup"><span data-stu-id="8aa18-125">The Access Edge service public IP address is primary with default gateway set to the public router (131.107.155.1).</span></span>
    
    <span data-ttu-id="8aa18-126">O serviço de borda de Webconferência e os endereços IP privados do serviço de borda a/V são endereços IP adicionais na seção **avançado** das propriedades de **protocolo de Internet versão 4 (TCP/IPv4)** e **protocolo IP versão 6 (TCP/IPv6)** das **Propriedades de conexão de área local** no Windows Server.</span><span class="sxs-lookup"><span data-stu-id="8aa18-126">Web Conferencing Edge service and A/V Edge service private IP addresses are additional IP addresses in the **Advanced** section of the properties of **Internet Protocol Version 4 (TCP/IPv4)** and **Internet Protocol Version 6 (TCP/IPv6)** of the **Local Area Connection Properties** in Windows Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="8aa18-127">É possível, mas não recomendado, usar um único endereço IP para todas as três interfaces de serviço de borda.</span><span class="sxs-lookup"><span data-stu-id="8aa18-127">It is possible, though not recommended, to use a single IP address for all three Edge service interfaces.</span></span> <span data-ttu-id="8aa18-128">Embora isso salve endereços IP, ele exige números de porta diferentes para cada serviço.</span><span class="sxs-lookup"><span data-stu-id="8aa18-128">Though this does save IP addresses, it requires different port numbers for each service.</span></span> <span data-ttu-id="8aa18-129">O número da porta padrão é 443/TCP, o que garante que os firewalls remotos permitam que o tráfego seja permitido.</span><span class="sxs-lookup"><span data-stu-id="8aa18-129">The default port number is 443/TCP, which ensures that most remote firewalls will allow the traffic.</span></span> <span data-ttu-id="8aa18-130">Alterar os valores de porta para (por exemplo) 5061/TCP para o serviço de borda de acesso, 444/TCP para o serviço de borda de Webconferência e 443/TCP para o serviço de borda A/V pode causar problemas para usuários remotos nos quais um firewall para os quais estão sendo atrasados não permite o tráfego sobre 5061/TCP e 444/TCP.</span><span class="sxs-lookup"><span data-stu-id="8aa18-130">Changing the port values to (for example) 5061/TCP for the Access Edge service, 444/TCP for the Web Conferencing Edge service and 443/TCP for the A/V Edge service might cause problems for remote users where a firewall that they are behind does not allow the traffic over 5061/TCP and 444/TCP.</span></span> <span data-ttu-id="8aa18-131">Além disso, três endereços IP distintos facilitam a solução de problemas devido à capacidade de filtrar por endereço IP.</span><span class="sxs-lookup"><span data-stu-id="8aa18-131">Additionally, three distinct IP addresses makes troubleshooting easier due to being able to filter on IP address.</span></span>

    
    </div>

  - <span data-ttu-id="8aa18-132">**Adaptador de rede 2 nó 2 (interface externa)**</span><span class="sxs-lookup"><span data-stu-id="8aa18-132">**Network adapter 2 Node 2 (External Interface)**</span></span>
    
    <span data-ttu-id="8aa18-133">Três endereços IP privados são atribuídos a esse adaptador de rede, por exemplo, 131.107.155.11 para serviço de borda de acesso, 131.107.155.21 para serviço de borda de webconferência, 131.107.155.31 para o serviço de borda A/V.</span><span class="sxs-lookup"><span data-stu-id="8aa18-133">Three private IP addresses are assigned to this network adapter, for example 131.107.155.11 for Access Edge service, 131.107.155.21 for Web Conferencing Edge service, 131.107.155.31 for A/V Edge service.</span></span>
    
    <span data-ttu-id="8aa18-134">O endereço IP público do serviço de borda do Access é primário com o gateway padrão definido para o roteador público (131.107.155.1).</span><span class="sxs-lookup"><span data-stu-id="8aa18-134">The Access Edge service public IP address is primary with default gateway set to the public router (131.107.155.1).</span></span>
    
    <span data-ttu-id="8aa18-135">O serviço de borda de Webconferência e os endereços IP privados do serviço de borda a/V são endereços IP adicionais na seção **avançado** das propriedades de **protocolo de Internet versão 4 (TCP/IPv4)** e **protocolo IP versão 6 (TCP/IPv6)** das **Propriedades de conexão de área local** no Windows Server.</span><span class="sxs-lookup"><span data-stu-id="8aa18-135">Web Conferencing Edge service and A/V Edge service private IP addresses are additional IP addresses in the **Advanced** section of the properties of **Internet Protocol Version 4 (TCP/IPv4)** and **Internet Protocol Version 6 (TCP/IPv6)** of the **Local Area Connection Properties** in Windows Server.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="8aa18-136">A configuração do servidor de borda com dois adaptadores de rede é uma das duas opções.</span><span class="sxs-lookup"><span data-stu-id="8aa18-136">Configuring the Edge Server with two network adapters is one of two options.</span></span> <span data-ttu-id="8aa18-137">A outra opção é usar um adaptador de rede para o lado interno e três adaptadores de rede para o lado externo do servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="8aa18-137">The other option is to use one network adapter for the internal side and three network adapters for the external side of the Edge Server.</span></span> <span data-ttu-id="8aa18-138">O principal benefício dessa opção é um adaptador de rede distinto por serviço de servidor de borda e uma coleta de dados possivelmente mais concisa quando a solução de problemas é necessária</span><span class="sxs-lookup"><span data-stu-id="8aa18-138">The main benefit of this option is a distinct network adapter per Edge Server service, and potentially more concise data collection when troubleshooting is necessary</span></span>



</div>

### <a name="dns-records-required-for-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses-example"></a><span data-ttu-id="8aa18-139">Registros DNS necessários para borda consolidada dimensionada, balanceamento de carga de DNS com endereços IP públicos (exemplo)</span><span class="sxs-lookup"><span data-stu-id="8aa18-139">DNS Records Required for Scaled Consolidated Edge, DNS Load Balancing with Public IP Addresses (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8aa18-140">Local/tipo/porta</span><span class="sxs-lookup"><span data-stu-id="8aa18-140">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="8aa18-141">Registro FQDN/DNS</span><span class="sxs-lookup"><span data-stu-id="8aa18-141">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="8aa18-142">Endereço IP/FQDN</span><span class="sxs-lookup"><span data-stu-id="8aa18-142">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="8aa18-143">Mapas para/comentários</span><span class="sxs-lookup"><span data-stu-id="8aa18-143">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8aa18-144">DNS/A externo</span><span class="sxs-lookup"><span data-stu-id="8aa18-144">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="8aa18-145">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8aa18-145">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="8aa18-146">131.107.155.10 e 131.107.155.11</span><span class="sxs-lookup"><span data-stu-id="8aa18-146">131.107.155.10 and 131.107.155.11</span></span></p></td>
<td><p><span data-ttu-id="8aa18-147">Interface externa do Access Edge Service (contoso) Repita conforme necessário para todos os domínios SIP com usuários habilitados para Lync</span><span class="sxs-lookup"><span data-stu-id="8aa18-147">Access Edge service external interface (Contoso) Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8aa18-148">DNS/A externo</span><span class="sxs-lookup"><span data-stu-id="8aa18-148">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="8aa18-149">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8aa18-149">webcon.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="8aa18-150">131.107.155.20 e 131.107.155.21</span><span class="sxs-lookup"><span data-stu-id="8aa18-150">131.107.155.20 and 131.107.155.21</span></span></p></td>
<td><p><span data-ttu-id="8aa18-151">Interface externa do serviço de borda de Webconferência</span><span class="sxs-lookup"><span data-stu-id="8aa18-151">Web Conferencing Edge service external interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8aa18-152">DNS/A externo</span><span class="sxs-lookup"><span data-stu-id="8aa18-152">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="8aa18-153">av.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8aa18-153">av.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="8aa18-154">131.107.155.30 e 131.107.155.31</span><span class="sxs-lookup"><span data-stu-id="8aa18-154">131.107.155.30 and 131.107.155.31</span></span></p></td>
<td><p><span data-ttu-id="8aa18-155">Interface externa de serviço de borda A/V</span><span class="sxs-lookup"><span data-stu-id="8aa18-155">A/V Edge service external interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8aa18-156">DNS/SRV/443 externos</span><span class="sxs-lookup"><span data-stu-id="8aa18-156">External DNS/SRV/443</span></span></p></td>
<td><p><span data-ttu-id="8aa18-157">_sip._tls.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8aa18-157">_sip._tls.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="8aa18-158">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8aa18-158">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="8aa18-159">Interface externa do serviço de borda do Access.</span><span class="sxs-lookup"><span data-stu-id="8aa18-159">Access Edge service external interface.</span></span> <span data-ttu-id="8aa18-160">Obrigatório para configurar automaticamente o Lync 2013 e os clientes do Lync 2010 para trabalhar externamente.</span><span class="sxs-lookup"><span data-stu-id="8aa18-160">Required for automatic configuration of Lync 2013 and Lync 2010 clients to work externally.</span></span> <span data-ttu-id="8aa18-161">Repita conforme necessário para todos os domínios SIP com usuários habilitados para o Lync.</span><span class="sxs-lookup"><span data-stu-id="8aa18-161">Repeat as necessary for all SIP domains with Lync enabled users.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8aa18-162">DNS/SRV/5061 externo</span><span class="sxs-lookup"><span data-stu-id="8aa18-162">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="8aa18-163">_sipfederationtls._tcp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8aa18-163">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="8aa18-164">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8aa18-164">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="8aa18-165">Interface externa do serviço de borda do Access necessária para descoberta automática de DNS de parceiros federados conhecidos como "domínio SIP permitido" (chamado de Federação aprimorada nas versões anteriores).</span><span class="sxs-lookup"><span data-stu-id="8aa18-165">Access Edge service external interface Required for automatic DNS discovery of federated partners known as “Allowed SIP Domain” (called enhanced federation in previous releases).</span></span> <span data-ttu-id="8aa18-166">Repita conforme necessário para todos os domínios SIP com usuários habilitados para Lync</span><span class="sxs-lookup"><span data-stu-id="8aa18-166">Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8aa18-167">DNS interno/A</span><span class="sxs-lookup"><span data-stu-id="8aa18-167">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="8aa18-168">lsedge.contoso.net</span><span class="sxs-lookup"><span data-stu-id="8aa18-168">lsedge.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="8aa18-169">172.25.33.10 e 172.25.33.11</span><span class="sxs-lookup"><span data-stu-id="8aa18-169">172.25.33.10 and 172.25.33.11</span></span></p></td>
<td><p><span data-ttu-id="8aa18-170">Interface interna de borda consolidada</span><span class="sxs-lookup"><span data-stu-id="8aa18-170">Consolidated Edge internal interface</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="records-required-for-federation"></a><span data-ttu-id="8aa18-171">Registros necessários para Federação</span><span class="sxs-lookup"><span data-stu-id="8aa18-171">Records Required for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8aa18-172">Local/tipo/porta</span><span class="sxs-lookup"><span data-stu-id="8aa18-172">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="8aa18-173">FQDN</span><span class="sxs-lookup"><span data-stu-id="8aa18-173">FQDN</span></span></th>
<th><span data-ttu-id="8aa18-174">Endereço IP/registro de host FQDN</span><span class="sxs-lookup"><span data-stu-id="8aa18-174">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="8aa18-175">Mapas para/comentários</span><span class="sxs-lookup"><span data-stu-id="8aa18-175">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8aa18-176">DNS/SRV/5061 externo</span><span class="sxs-lookup"><span data-stu-id="8aa18-176">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="8aa18-177">_sipfederationtls._tcp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8aa18-177">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="8aa18-178">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8aa18-178">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="8aa18-179">Interface externa do serviço de borda do acesso SIP necessária para a descoberta automática de DNS da sua Federação para outros parceiros de Federação potenciais e é conhecida como "domínios SIP permitidos" (chamado de Federação aprimorada nas versões anteriores).</span><span class="sxs-lookup"><span data-stu-id="8aa18-179">SIP Access Edge service external interface Required for automatic DNS discovery of your federation to other potential federation partners, and is known as “Allowed SIP Domains” (called enhanced federation in previous releases).</span></span></p>
<div>

> [!IMPORTANT]  
> <span data-ttu-id="8aa18-180">Repita conforme necessário para todos os domínios SIP com usuários habilitados para o Lync e clientes móveis do Microsoft Lync que usam o serviço de notificação por Push ou o serviço de notificação por push da Apple</span><span class="sxs-lookup"><span data-stu-id="8aa18-180">Repeat as necessary for all SIP domains with Lync enabled users and Microsoft Lync Mobile clients that use either the Push Notification Service or the Apple Push Notification service</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="8aa18-181">Resumo de DNS para o protocolo de mensagens extensíveis e de presença</span><span class="sxs-lookup"><span data-stu-id="8aa18-181">DNS Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8aa18-182">Local/tipo/porta</span><span class="sxs-lookup"><span data-stu-id="8aa18-182">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="8aa18-183">FQDN</span><span class="sxs-lookup"><span data-stu-id="8aa18-183">FQDN</span></span></th>
<th><span data-ttu-id="8aa18-184">Endereço IP/registro de host FQDN</span><span class="sxs-lookup"><span data-stu-id="8aa18-184">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="8aa18-185">Mapas para/comentários</span><span class="sxs-lookup"><span data-stu-id="8aa18-185">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8aa18-186">DNS/SRV/5269 externo</span><span class="sxs-lookup"><span data-stu-id="8aa18-186">External DNS/SRV/5269</span></span></p></td>
<td><p><span data-ttu-id="8aa18-187">_xmpp-server._tcp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8aa18-187">_xmpp-server._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="8aa18-188">xmpp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8aa18-188">xmpp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="8aa18-189">Interface externa de proxy XMPP no serviço de borda do Access ou no pool de bordas. Repita conforme necessário para todos os domínios SIP internos com usuários habilitados para Lync nos quais o contato com contatos do XMPP é permitido pela configuração da política de acesso externo por meio de uma política global, política de site onde o usuário está localizado ou política de usuário aplicada ao Usuário compatível com o Lync.</span><span class="sxs-lookup"><span data-stu-id="8aa18-189">XMPP proxy external interface on the Access Edge service or Edge pool.Repeat as necessary for all internal SIP domains with Lync enabled users where contact with XMPP contacts is allowed through the configuration of the External Access Policy through a global policy, site policy where the user is located, or user policy applied to the Lync-enabled user.</span></span> <span data-ttu-id="8aa18-190">Um domínio XMPP permitido também deve ser configurado na política de parceiros federados do XMPP.</span><span class="sxs-lookup"><span data-stu-id="8aa18-190">An allowed XMPP domain must also be configured in the XMPP Federated Partners policy.</span></span> <span data-ttu-id="8aa18-191">Consulte os tópicos em <strong>Consulte também</strong> para obter detalhes adicionais</span><span class="sxs-lookup"><span data-stu-id="8aa18-191">See topics in <strong>See Also</strong> for additional details</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8aa18-192">DNS/A externo</span><span class="sxs-lookup"><span data-stu-id="8aa18-192">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="8aa18-193">xmpp.contoso.com (por exemplo)</span><span class="sxs-lookup"><span data-stu-id="8aa18-193">xmpp.contoso.com (for example)</span></span></p></td>
<td><p><span data-ttu-id="8aa18-194">Endereço IP do serviço de borda de acesso em seu servidor de borda ou em um pool de bordas que hospeda o proxy XMPP</span><span class="sxs-lookup"><span data-stu-id="8aa18-194">IP address of Access Edge service on your Edge Server or Edge pool hosting XMPP proxy</span></span></p></td>
<td><p><span data-ttu-id="8aa18-195">Aponta para o serviço de borda de acesso ou o pool de bordas que hospeda o serviço de proxy XMPP.</span><span class="sxs-lookup"><span data-stu-id="8aa18-195">Points to the Access Edge service or Edge pool that hosts the XMPP proxy service.</span></span> <span data-ttu-id="8aa18-196">Geralmente, o registro SRV que você cria aponta para esse registro de host (A ou AAAA)</span><span class="sxs-lookup"><span data-stu-id="8aa18-196">Typically, the SRV record that you create will point to this host (A or AAAA) record</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

