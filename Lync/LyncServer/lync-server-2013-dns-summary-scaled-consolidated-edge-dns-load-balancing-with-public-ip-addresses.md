---
title: 'Lync Server 2013: Resumo de DNS-borda consolidada em escala, balanceamento de carga de DNS com endereços IP públicos'
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
ms.openlocfilehash: 4f2cd6350a74f4dd054d30d81ac13c15c829d122
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145880"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-summary---scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses-in-lync-server-2013"></a><span data-ttu-id="1dfdd-102">Resumo de DNS-borda consolidada em escala, balanceamento de carga de DNS com endereços IP públicos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1dfdd-102">DNS summary - Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1dfdd-103">_**Última modificação do tópico:** 2017-03-09_</span><span class="sxs-lookup"><span data-stu-id="1dfdd-103">_**Topic Last Modified:** 2017-03-09_</span></span>

<span data-ttu-id="1dfdd-104">Os requisitos de registro DNS para acesso remoto ao Lync Server 2013 são bem simples comparados com os de certificados e portas.</span><span class="sxs-lookup"><span data-stu-id="1dfdd-104">DNS record requirements for remote access to Lync Server 2013 are fairly straightforward compared to those for certificates and ports.</span></span> <span data-ttu-id="1dfdd-105">Além disso, muitos registros são opcionais, dependendo de como você configura os clientes que executam o Lync 2013 e se você habilita a Federação.</span><span class="sxs-lookup"><span data-stu-id="1dfdd-105">Also, many records are optional, depending on how you configure clients running Lync 2013 and whether you enable federation.</span></span>

<span data-ttu-id="1dfdd-106">Para obter detalhes sobre os requisitos de DNS do Lync 2013, consulte [determine DNS Requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1dfdd-106">For details about Lync 2013 DNS requirements, see [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="1dfdd-107">Para obter detalhes sobre como configurar a configuração automática dos clientes do Lync 2013 se o DNS de Split-Brain não estiver configurado, consulte a seção "configuração automática sem DNS de Split Brain" em [determinar requisitos de DNS para o Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1dfdd-107">For details about configuring automatic configuration of Lync 2013 clients if split-brain DNS is not configured, see the "Automatic Configuration without Split Brain DNS" section in [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="1dfdd-108">A tabela a seguir contém um resumo dos registros DNS requeridos para oferecer suporte à topologia de borda consolidada única exibida na imagem Topologia de Borda Consolidada Única.</span><span class="sxs-lookup"><span data-stu-id="1dfdd-108">The following table contains a summary of the DNS records that are required to support the single consolidated edge topology shown in the Single Consolidated Edge Topology figure.</span></span> <span data-ttu-id="1dfdd-109">Observe que determinados registros DNS são necessários apenas para a configuração automática dos clientes do Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="1dfdd-109">Note that certain DNS records are required only for automatic configuration of Lync 2013 clients.</span></span> <span data-ttu-id="1dfdd-110">Se você planeja usar objetos de política de grupo (GPOs) para configurar os clientes do Lync, os registros associados não são necessários.</span><span class="sxs-lookup"><span data-stu-id="1dfdd-110">If you plan to use group policy objects (GPOs) to configure Lync clients, the associated records are not necessary.</span></span>

<div>

## <a name="important-edge-server-network-adapter-requirements"></a><span data-ttu-id="1dfdd-111">IMPORTANTE: requisitos do adaptador de rede do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="1dfdd-111">IMPORTANT: Edge Server Network Adapter Requirements</span></span>

<span data-ttu-id="1dfdd-112">Para evitar problemas de roteamento, verifique se há pelo menos dois adaptadores de rede em seus servidores de borda e se o gateway padrão está definido somente no adaptador de rede associado à interface externa.</span><span class="sxs-lookup"><span data-stu-id="1dfdd-112">To avoid routing issues, verify that there are at least two network adapters in your Edge Servers and that the default gateway is set only on the network adapter associated with the external interface.</span></span> <span data-ttu-id="1dfdd-113">Por exemplo, conforme mostrado na figura de cenário de borda consolidada em escala em [borda consolidada em escala, balanceamento de carga de DNS com endereços IP públicos no Lync Server 2013](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md) , o gateway padrão apontaria para o firewall externo.</span><span class="sxs-lookup"><span data-stu-id="1dfdd-113">For example, as shown in the Scaled Consolidated Edge Scenario figure in [Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md) , the default gateway would point to the external firewall.</span></span>

<span data-ttu-id="1dfdd-114">Você pode configurar os dois adaptadores de rede em seu Servidor de Borda conforme a seguir:</span><span class="sxs-lookup"><span data-stu-id="1dfdd-114">You can configure two network adapters in each of your Edge Server as follows:</span></span>

  - <span data-ttu-id="1dfdd-115">**Adaptador de rede 1 - Nó 1 (Interface interna)**</span><span class="sxs-lookup"><span data-stu-id="1dfdd-115">**Network adapter 1 - Node 1 (Internal Interface)**</span></span>
    
    <span data-ttu-id="1dfdd-116">Interface interna com 172.25.33.10 designados.</span><span class="sxs-lookup"><span data-stu-id="1dfdd-116">Internal interface with 172.25.33.10 assigned.</span></span>
    
    <span data-ttu-id="1dfdd-117">Nenhum gateway padrão definido.</span><span class="sxs-lookup"><span data-stu-id="1dfdd-117">No default gateway is defined.</span></span>
    
    <span data-ttu-id="1dfdd-118">Certifique-se de que há uma rota da rede que contém a interface interna da borda para qualquer rede que contenha servidores que executam os clientes do Lync Server 2013 ou do Lync Server 2013 (por exemplo, de 172.25.33.0 para 192.168.10.0).</span><span class="sxs-lookup"><span data-stu-id="1dfdd-118">Ensure that there is a route from the network containing the Edge internal interface to any networks that contain servers running Lync Server 2013 or Lync Server 2013 clients (for example, from 172.25.33.0 to 192.168.10.0).</span></span>

  - <span data-ttu-id="1dfdd-119">**Adaptador de rede 2 - Nó 2 (Interface externa)**</span><span class="sxs-lookup"><span data-stu-id="1dfdd-119">**Network adapter 1 - Node 2 (Internal Interface)**</span></span>
    
    <span data-ttu-id="1dfdd-120">Interface interna com 172.25.33.40 designados.</span><span class="sxs-lookup"><span data-stu-id="1dfdd-120">Internal interface with 172.25.33.11 assigned.</span></span>
    
    <span data-ttu-id="1dfdd-121">Nenhum gateway padrão está definido.</span><span class="sxs-lookup"><span data-stu-id="1dfdd-121">No default gateway is defined.</span></span>
    
    <span data-ttu-id="1dfdd-122">Certifique-se de que há uma rota da rede que contém a interface interna da borda para qualquer rede que contenha servidores que executam os clientes do Lync Server 2013 ou do Lync Server 2013 (por exemplo, de 172.25.33.0 para 192.168.10.0).</span><span class="sxs-lookup"><span data-stu-id="1dfdd-122">Ensure that there is a route from the network containing the Edge internal interface to any networks that contain servers running Lync Server 2013 or Lync Server 2013 clients (for example, from 172.25.33.0 to 192.168.10.0).</span></span>

  - <span data-ttu-id="1dfdd-123">**Adaptador de rede 1 (Interface interna)**</span><span class="sxs-lookup"><span data-stu-id="1dfdd-123">**Network adapter 2 Node 1 (External Interface)**</span></span>
    
    <span data-ttu-id="1dfdd-124">Três endereços IP privados são atribuídos a este adaptador de rede, por exemplo, 131.107.155.10 para serviço de borda de acesso, 131.107.155.20 para serviço de borda de webconferência, 131.107.155.30 para o serviço de borda A/V.</span><span class="sxs-lookup"><span data-stu-id="1dfdd-124">Three private IP addresses are assigned to this network adapter, for example 131.107.155.10 for Access Edge service, 131.107.155.20 for Web Conferencing Edge service, 131.107.155.30 for A/V Edge service.</span></span>
    
    <span data-ttu-id="1dfdd-125">O endereço IP público do serviço de borda de acesso é o principal com o gateway padrão definido para o roteador público (131.107.155.1).</span><span class="sxs-lookup"><span data-stu-id="1dfdd-125">The Access Edge service public IP address is primary with default gateway set to the public router (131.107.155.1).</span></span>
    
    <span data-ttu-id="1dfdd-126">Serviço de borda de Webconferência e endereços IP privados de serviço de borda A/V são endereços IP adicionais na seção **avançado** das propriedades do **Internet Protocol versão 4 (TCP/IPv4)** e **Internet Protocol version 6 (TCP/IPv6)** das **Propriedades de conexão de área local** no Windows Server.</span><span class="sxs-lookup"><span data-stu-id="1dfdd-126">Web Conferencing Edge service and A/V Edge service private IP addresses are additional IP addresses in the **Advanced** section of the properties of **Internet Protocol Version 4 (TCP/IPv4)** and **Internet Protocol Version 6 (TCP/IPv6)** of the **Local Area Connection Properties** in Windows Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1dfdd-127">É possível, embora não seja recomendado, usar um único endereço IP para as três interfaces de serviço de Borda.</span><span class="sxs-lookup"><span data-stu-id="1dfdd-127">It is possible, though not recommended, to use a single IP address for all three Edge service interfaces.</span></span> <span data-ttu-id="1dfdd-128">Embora isso não salve endereços IP, exige diferentes números de porta para cada serviço.</span><span class="sxs-lookup"><span data-stu-id="1dfdd-128">Though this does save IP addresses, it requires different port numbers for each service.</span></span> <span data-ttu-id="1dfdd-129">O número de porta padrão é 443/TCP, que garante que a maioria dos firewalls remotos permitirão o tráfego.</span><span class="sxs-lookup"><span data-stu-id="1dfdd-129">The default port number is 443/TCP, which ensures that most remote firewalls will allow the traffic.</span></span> <span data-ttu-id="1dfdd-130">Alterar os valores de porta para (por exemplo) 5061/TCP para o serviço de borda de acesso, 444/TCP para o serviço de borda de Webconferência e 443/TCP para o serviço de borda A/V pode causar problemas para usuários remotos em que um firewall que estão por trás não permite o tráfego sobre 5061/TCP e 444/TCP.</span><span class="sxs-lookup"><span data-stu-id="1dfdd-130">Changing the port values to (for example) 5061/TCP for the Access Edge service, 444/TCP for the Web Conferencing Edge service and 443/TCP for the A/V Edge service might cause problems for remote users where a firewall that they are behind does not allow the traffic over 5061/TCP and 444/TCP.</span></span> <span data-ttu-id="1dfdd-131">Além disso, três endereços IP distintos tornam a resolução de problemas mais fácil por poderem filtrar o endereço IP.</span><span class="sxs-lookup"><span data-stu-id="1dfdd-131">Additionally, three distinct IP addresses makes troubleshooting easier due to being able to filter on IP address.</span></span>

    
    </div>

  - <span data-ttu-id="1dfdd-132">**Adaptador de rede 2 Nó 2 (Interface externa)**</span><span class="sxs-lookup"><span data-stu-id="1dfdd-132">**Network adapter 2 Node 2 (External Interface)**</span></span>
    
    <span data-ttu-id="1dfdd-133">Três endereços IP privados são atribuídos a este adaptador de rede, por exemplo, 131.107.155.11 para serviço de borda de acesso, 131.107.155.21 para serviço de borda de webconferência, 131.107.155.31 para o serviço de borda A/V.</span><span class="sxs-lookup"><span data-stu-id="1dfdd-133">Three private IP addresses are assigned to this network adapter, for example 131.107.155.11 for Access Edge service, 131.107.155.21 for Web Conferencing Edge service, 131.107.155.31 for A/V Edge service.</span></span>
    
    <span data-ttu-id="1dfdd-134">O endereço IP público do serviço de borda de acesso é o principal com o gateway padrão definido para o roteador público (131.107.155.1).</span><span class="sxs-lookup"><span data-stu-id="1dfdd-134">The Access Edge service public IP address is primary with default gateway set to the public router (131.107.155.1).</span></span>
    
    <span data-ttu-id="1dfdd-135">Serviço de borda de Webconferência e endereços IP privados de serviço de borda A/V são endereços IP adicionais na seção **avançado** das propriedades do **Internet Protocol versão 4 (TCP/IPv4)** e **Internet Protocol version 6 (TCP/IPv6)** das **Propriedades de conexão de área local** no Windows Server.</span><span class="sxs-lookup"><span data-stu-id="1dfdd-135">Web Conferencing Edge service and A/V Edge service private IP addresses are additional IP addresses in the **Advanced** section of the properties of **Internet Protocol Version 4 (TCP/IPv4)** and **Internet Protocol Version 6 (TCP/IPv6)** of the **Local Area Connection Properties** in Windows Server.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="1dfdd-136">A configuração do servidor de borda com dois adaptadores de rede é uma das duas opções.</span><span class="sxs-lookup"><span data-stu-id="1dfdd-136">Configuring the Edge Server with two network adapters is one of two options.</span></span> <span data-ttu-id="1dfdd-137">A outra opção é usar um adaptador de rede para o lado interno e três adaptadores de rede para o lado externo do servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="1dfdd-137">The other option is to use one network adapter for the internal side and three network adapters for the external side of the Edge Server.</span></span> <span data-ttu-id="1dfdd-138">O principal benefício dessa opção é um adaptador de rede distinto por serviço de servidor de borda e coleta de dados potencialmente mais concisa quando a solução de problemas é necessária</span><span class="sxs-lookup"><span data-stu-id="1dfdd-138">The main benefit of this option is a distinct network adapter per Edge Server service, and potentially more concise data collection when troubleshooting is necessary</span></span>



</div>

### <a name="dns-records-required-for-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses-example"></a><span data-ttu-id="1dfdd-139">Registros DNS necessários para borda consolidada em escala, balanceamento de carga de DNS com endereços IP públicos (exemplo)</span><span class="sxs-lookup"><span data-stu-id="1dfdd-139">DNS Records Required for Scaled Consolidated Edge, DNS Load Balancing with Public IP Addresses (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1dfdd-140">Local/tipo/porta</span><span class="sxs-lookup"><span data-stu-id="1dfdd-140">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="1dfdd-141">Registro FQDN/DNS</span><span class="sxs-lookup"><span data-stu-id="1dfdd-141">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="1dfdd-142">Endereço IP/FQDN</span><span class="sxs-lookup"><span data-stu-id="1dfdd-142">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="1dfdd-143">Mapeia para/Comentários</span><span class="sxs-lookup"><span data-stu-id="1dfdd-143">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1dfdd-144">DNS Externo/A</span><span class="sxs-lookup"><span data-stu-id="1dfdd-144">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="1dfdd-145">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1dfdd-145">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1dfdd-146">131.107.155.10 e 131.107.155.11</span><span class="sxs-lookup"><span data-stu-id="1dfdd-146">131.107.155.10 and 131.107.155.11</span></span></p></td>
<td><p><span data-ttu-id="1dfdd-147">Interface externa do serviço de borda de acesso (contoso) Repita conforme necessário para todos os domínios SIP com usuários habilitados para Lync</span><span class="sxs-lookup"><span data-stu-id="1dfdd-147">Access Edge service external interface (Contoso) Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dfdd-148">DNS Externo/A</span><span class="sxs-lookup"><span data-stu-id="1dfdd-148">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="1dfdd-149">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1dfdd-149">webcon.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1dfdd-150">131.107.155.20 e 131.107.155.21</span><span class="sxs-lookup"><span data-stu-id="1dfdd-150">131.107.155.20 and 131.107.155.21</span></span></p></td>
<td><p><span data-ttu-id="1dfdd-151">Interface externa do serviço de borda de Webconferência</span><span class="sxs-lookup"><span data-stu-id="1dfdd-151">Web Conferencing Edge service external interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1dfdd-152">DNS Externo/A</span><span class="sxs-lookup"><span data-stu-id="1dfdd-152">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="1dfdd-153">av.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1dfdd-153">av.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1dfdd-154">131.107.155.30 e 131.107.155.31</span><span class="sxs-lookup"><span data-stu-id="1dfdd-154">131.107.155.30 and 131.107.155.31</span></span></p></td>
<td><p><span data-ttu-id="1dfdd-155">Interface externa do serviço de borda A/V</span><span class="sxs-lookup"><span data-stu-id="1dfdd-155">A/V Edge service external interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dfdd-156">DNS Externo/SRV/443</span><span class="sxs-lookup"><span data-stu-id="1dfdd-156">External DNS/SRV/443</span></span></p></td>
<td><p><span data-ttu-id="1dfdd-157">_sip. _tls. contoso. com</span><span class="sxs-lookup"><span data-stu-id="1dfdd-157">_sip._tls.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1dfdd-158">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1dfdd-158">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1dfdd-159">Interface externa do serviço de borda de acesso.</span><span class="sxs-lookup"><span data-stu-id="1dfdd-159">Access Edge service external interface.</span></span> <span data-ttu-id="1dfdd-160">Necessário para a configuração automática dos clientes do Lync 2013 e Lync 2010 para trabalhar externamente.</span><span class="sxs-lookup"><span data-stu-id="1dfdd-160">Required for automatic configuration of Lync 2013 and Lync 2010 clients to work externally.</span></span> <span data-ttu-id="1dfdd-161">Repita conforme for necessário para todos os domínios SIP com usuários Lync.</span><span class="sxs-lookup"><span data-stu-id="1dfdd-161">Repeat as necessary for all SIP domains with Lync enabled users.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1dfdd-162">DNS/A externo</span><span class="sxs-lookup"><span data-stu-id="1dfdd-162">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="1dfdd-163">_sipfederationtls. _tcp. contoso. com</span><span class="sxs-lookup"><span data-stu-id="1dfdd-163">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1dfdd-164">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1dfdd-164">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1dfdd-165">Interface externa do serviço de borda de acesso necessária para a descoberta automática de DNS de parceiros federados conhecidos como "domínio SIP permitido" (chamado de Federação avançada em versões anteriores).</span><span class="sxs-lookup"><span data-stu-id="1dfdd-165">Access Edge service external interface Required for automatic DNS discovery of federated partners known as “Allowed SIP Domain” (called enhanced federation in previous releases).</span></span> <span data-ttu-id="1dfdd-166">Repetir conforme o necessário para todos os domínios SIP com usuários habilitados para o Lync</span><span class="sxs-lookup"><span data-stu-id="1dfdd-166">Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dfdd-167">DNS Interno/A</span><span class="sxs-lookup"><span data-stu-id="1dfdd-167">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="1dfdd-168">lsedge.contoso.net</span><span class="sxs-lookup"><span data-stu-id="1dfdd-168">lsedge.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="1dfdd-169">172.25.33.10 e 172.25.33.11</span><span class="sxs-lookup"><span data-stu-id="1dfdd-169">172.25.33.10 and 172.25.33.11</span></span></p></td>
<td><p><span data-ttu-id="1dfdd-170">Interface interna da Borda Consolidada</span><span class="sxs-lookup"><span data-stu-id="1dfdd-170">Consolidated Edge internal interface</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="records-required-for-federation"></a><span data-ttu-id="1dfdd-171">Registros requeridos para federação</span><span class="sxs-lookup"><span data-stu-id="1dfdd-171">Records Required for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1dfdd-172">Local/tipo/porta</span><span class="sxs-lookup"><span data-stu-id="1dfdd-172">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="1dfdd-173">FQDN</span><span class="sxs-lookup"><span data-stu-id="1dfdd-173">FQDN</span></span></th>
<th><span data-ttu-id="1dfdd-174">Endereço IP/registro de host FQDN</span><span class="sxs-lookup"><span data-stu-id="1dfdd-174">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="1dfdd-175">Mapeia para/Comentários</span><span class="sxs-lookup"><span data-stu-id="1dfdd-175">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1dfdd-176">DNS Externo/SRV/5061</span><span class="sxs-lookup"><span data-stu-id="1dfdd-176">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="1dfdd-177">_sipfederationtls. _tcp. contoso. com</span><span class="sxs-lookup"><span data-stu-id="1dfdd-177">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1dfdd-178">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1dfdd-178">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1dfdd-179">Interface externa do serviço de borda de acesso SIP necessária para a descoberta automática de DNS da sua Federação para outros parceiros de Federação em potencial e é conhecido como "domínios SIP permitidos" (chamado de Federação avançada em versões anteriores).</span><span class="sxs-lookup"><span data-stu-id="1dfdd-179">SIP Access Edge service external interface Required for automatic DNS discovery of your federation to other potential federation partners, and is known as “Allowed SIP Domains” (called enhanced federation in previous releases).</span></span></p>
<div>

> [!IMPORTANT]  
> <span data-ttu-id="1dfdd-180">Repita conforme necessário para todos os domínios SIP com usuários habilitados para Lync e clientes móveis do Microsoft Lync que usam o serviço de notificação por Push ou o serviço de notificação por push da Apple</span><span class="sxs-lookup"><span data-stu-id="1dfdd-180">Repeat as necessary for all SIP domains with Lync enabled users and Microsoft Lync Mobile clients that use either the Push Notification Service or the Apple Push Notification service</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="1dfdd-181">Resumo DNS para Mensagens Extensíveis e Protocolo de Presença</span><span class="sxs-lookup"><span data-stu-id="1dfdd-181">DNS Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1dfdd-182">Local/tipo/porta</span><span class="sxs-lookup"><span data-stu-id="1dfdd-182">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="1dfdd-183">FQDN</span><span class="sxs-lookup"><span data-stu-id="1dfdd-183">FQDN</span></span></th>
<th><span data-ttu-id="1dfdd-184">Endereço IP/registro de host FQDN</span><span class="sxs-lookup"><span data-stu-id="1dfdd-184">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="1dfdd-185">Mapeia para/comentários</span><span class="sxs-lookup"><span data-stu-id="1dfdd-185">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1dfdd-186">DNS Externo/SRV/5269</span><span class="sxs-lookup"><span data-stu-id="1dfdd-186">External DNS/SRV/5269</span></span></p></td>
<td><p><span data-ttu-id="1dfdd-187">_xmpp-Server. _tcp. contoso. com</span><span class="sxs-lookup"><span data-stu-id="1dfdd-187">_xmpp-server._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1dfdd-188">xmpp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1dfdd-188">xmpp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1dfdd-189">XMPP interface externa do proxy no serviço de borda de acesso ou no pool de borda. Repita conforme necessário para todos os domínios SIP internos com usuários habilitados para Lync onde contato com contatos do XMPP é permitido por meio da configuração da política de acesso externo por meio de uma política global, política de site onde o usuário está localizado ou política de usuário aplicada ao Usuário habilitado para Lync.</span><span class="sxs-lookup"><span data-stu-id="1dfdd-189">XMPP proxy external interface on the Access Edge service or Edge pool.Repeat as necessary for all internal SIP domains with Lync enabled users where contact with XMPP contacts is allowed through the configuration of the External Access Policy through a global policy, site policy where the user is located, or user policy applied to the Lync-enabled user.</span></span> <span data-ttu-id="1dfdd-190">Um domínio XMPP permitido também deve ser configurado na política de Parceiros Federados XMPP.</span><span class="sxs-lookup"><span data-stu-id="1dfdd-190">An allowed XMPP domain must also be configured in the XMPP Federated Partners policy.</span></span> <span data-ttu-id="1dfdd-191">Veja os tópicos em <strong>Consulte também </strong> para mais detalhes</span><span class="sxs-lookup"><span data-stu-id="1dfdd-191">See topics in <strong>See Also</strong> for additional details</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dfdd-192">DNS/A externo</span><span class="sxs-lookup"><span data-stu-id="1dfdd-192">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="1dfdd-193">xmpp.contoso.com (por exemplo)</span><span class="sxs-lookup"><span data-stu-id="1dfdd-193">xmpp.contoso.com (for example)</span></span></p></td>
<td><p><span data-ttu-id="1dfdd-194">Endereço IP do serviço de borda de acesso no servidor de borda ou no pool de borda que hospeda o proxy do XMPP</span><span class="sxs-lookup"><span data-stu-id="1dfdd-194">IP address of Access Edge service on your Edge Server or Edge pool hosting XMPP proxy</span></span></p></td>
<td><p><span data-ttu-id="1dfdd-195">Aponta para o serviço de borda de acesso ou o pool de borda que hospeda o serviço de proxy XMPP.</span><span class="sxs-lookup"><span data-stu-id="1dfdd-195">Points to the Access Edge service or Edge pool that hosts the XMPP proxy service.</span></span> <span data-ttu-id="1dfdd-196">Tipicamente, o registro SRV que você criar apontará para este host (A ou AAAA) record</span><span class="sxs-lookup"><span data-stu-id="1dfdd-196">Typically, the SRV record that you create will point to this host (A or AAAA) record</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

