---
title: 'Lync Server 2013: Resumo de DNS-borda consolidada em escala, balanceamento de carga de DNS com endereços IP privados usando NAT'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT
ms:assetid: 11bc7b84-91cf-48f9-ad0e-06ad30b46a2e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398201(v=OCS.15)
ms:contentKeyID: 48183447
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 269d5a687baba53ed0bd60d4854b79643f23f0e0
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532118"
---
# <a name="dns-summary---scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-in-lync-server-2013"></a><span data-ttu-id="ed8d0-102">Resumo de DNS-borda consolidada em escala, balanceamento de carga de DNS com endereços IP privados usando NAT no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ed8d0-102">DNS summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ed8d0-103">_**Última modificação do tópico:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="ed8d0-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="ed8d0-104">Os requisitos de registro DNS para acesso remoto ao Lync Server 2013 são bem simples comparados com os de certificados e portas.</span><span class="sxs-lookup"><span data-stu-id="ed8d0-104">DNS record requirements for remote access to Lync Server 2013 are fairly straightforward compared to those for certificates and ports.</span></span> <span data-ttu-id="ed8d0-105">Além disso, muitos registros são opcionais, dependendo de como você configura os clientes que executam o Lync 2013 e se você habilita a Federação.</span><span class="sxs-lookup"><span data-stu-id="ed8d0-105">Also, many records are optional, depending on how you configure clients running Lync 2013 and whether you enable federation.</span></span>

<span data-ttu-id="ed8d0-106">Para obter detalhes sobre os requisitos de DNS do Lync 2013, consulte [determine DNS Requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ed8d0-106">For details about Lync 2013 DNS requirements, see [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="ed8d0-107">Para obter detalhes sobre como configurar a configuração automática dos clientes do Lync 2013 se o DNS de Split-Brain não estiver configurado, consulte a seção "configuração automática sem DNS de Split Brain" em [determinar requisitos de DNS para o Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ed8d0-107">For details about configuring automatic configuration of Lync 2013 clients if split-brain DNS is not configured, see the "Automatic Configuration without Split Brain DNS" section in [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="ed8d0-108">A tabela a seguir contém um resumo dos registros DNS requeridos para oferecer suporte à topologia de borda consolidada única exibida na imagem Topologia de Borda Consolidada Única.</span><span class="sxs-lookup"><span data-stu-id="ed8d0-108">The following table contains a summary of the DNS records that are required to support the single consolidated edge topology shown in the Single Consolidated Edge Topology figure.</span></span> <span data-ttu-id="ed8d0-109">Observe que determinados registros DNS são necessários apenas para a configuração automática dos clientes do Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="ed8d0-109">Note that certain DNS records are required only for automatic configuration of Lync 2013 clients.</span></span> <span data-ttu-id="ed8d0-110">Se você planeja usar objetos de política de grupo (GPOs) para configurar os clientes do Lync, os registros associados não são necessários.</span><span class="sxs-lookup"><span data-stu-id="ed8d0-110">If you plan to use group policy objects (GPOs) to configure Lync clients, the associated records are not necessary.</span></span>

<div>

## <a name="important-edge-server-network-adapter-requirements"></a><span data-ttu-id="ed8d0-111">IMPORTANTE: requisitos do adaptador de rede do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="ed8d0-111">IMPORTANT: Edge Server Network Adapter Requirements</span></span>

<span data-ttu-id="ed8d0-112">Para evitar problemas de roteamento, verifique se há pelo menos dois adaptadores de rede em seus servidores de borda e se o gateway padrão está definido somente no adaptador de rede associado à interface externa.</span><span class="sxs-lookup"><span data-stu-id="ed8d0-112">To avoid routing issues, verify that there are at least two network adapters in your Edge Servers and that the default gateway is set only on the network adapter associated with the external interface.</span></span> <span data-ttu-id="ed8d0-113">Por exemplo, conforme mostrado na figura de cenário de borda consolidada em escala na [borda consolidada em escala, o balanceamento de carga de DNS com endereços IP privados usando NAT no Lync Server 2013](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md), o gateway padrão apontaria para o firewall externo.</span><span class="sxs-lookup"><span data-stu-id="ed8d0-113">For example, as shown in the Scaled Consolidated Edge Scenario figure in [Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md), the default gateway would point to the external firewall.</span></span>

<span data-ttu-id="ed8d0-114">Você pode configurar os dois adaptadores de rede em seu Servidor de Borda conforme a seguir:</span><span class="sxs-lookup"><span data-stu-id="ed8d0-114">You can configure two network adapters in each of your Edge Server as follows:</span></span>

  - <span data-ttu-id="ed8d0-115">**Adaptador de rede 1 - Nó 1 (Interface interna)**</span><span class="sxs-lookup"><span data-stu-id="ed8d0-115">**Network adapter 1 - Node 1 (Internal Interface)**</span></span>
    
    <span data-ttu-id="ed8d0-116">Interface interna com 172.25.33.10 designados.</span><span class="sxs-lookup"><span data-stu-id="ed8d0-116">Internal interface with 172.25.33.10 assigned.</span></span>
    
    <span data-ttu-id="ed8d0-117">Nenhum gateway padrão definido.</span><span class="sxs-lookup"><span data-stu-id="ed8d0-117">No default gateway is defined.</span></span>
    
    <span data-ttu-id="ed8d0-118">Certifique-se de que há uma rota da rede que contém a interface interna da borda para qualquer rede que contenha servidores que executam os clientes do Lync Server 2013 ou do Lync Server 2013 (por exemplo, de 172.25.33.0 para 192.168.10.0).</span><span class="sxs-lookup"><span data-stu-id="ed8d0-118">Ensure that there is a route from the network containing the Edge internal interface to any networks that contain servers running Lync Server 2013 or Lync Server 2013 clients (for example, from 172.25.33.0 to 192.168.10.0).</span></span>

  - <span data-ttu-id="ed8d0-119">**Adaptador de rede 2 - Nó 2 (Interface externa)**</span><span class="sxs-lookup"><span data-stu-id="ed8d0-119">**Network adapter 1 - Node 2 (Internal Interface)**</span></span>
    
    <span data-ttu-id="ed8d0-120">Interface interna com 172.25.33.40 designados.</span><span class="sxs-lookup"><span data-stu-id="ed8d0-120">Internal interface with 172.25.33.11 assigned.</span></span>
    
    <span data-ttu-id="ed8d0-121">Nenhum gateway padrão está definido.</span><span class="sxs-lookup"><span data-stu-id="ed8d0-121">No default gateway is defined.</span></span>
    
    <span data-ttu-id="ed8d0-122">Certifique-se de que há uma rota da rede que contém a interface interna da borda para qualquer rede que contenha servidores que executam os clientes do Lync Server 2013 ou do Lync Server 2013 (por exemplo, de 172.25.33.0 para 192.168.10.0).</span><span class="sxs-lookup"><span data-stu-id="ed8d0-122">Ensure that there is a route from the network containing the Edge internal interface to any networks that contain servers running Lync Server 2013 or Lync Server 2013 clients (for example, from 172.25.33.0 to 192.168.10.0).</span></span>

  - <span data-ttu-id="ed8d0-123">**Adaptador de rede 1 (Interface interna)**</span><span class="sxs-lookup"><span data-stu-id="ed8d0-123">**Network adapter 2 Node 1 (External Interface)**</span></span>
    
    <span data-ttu-id="ed8d0-124">Três endereços IP privados são atribuídos a este adaptador de rede, por exemplo, 10.45.16.10 para Borda de Acesso, 10.45.16.20 para Borda de Webconferência e 10.45.16.30 para Borda de AV.</span><span class="sxs-lookup"><span data-stu-id="ed8d0-124">Three private IP addresses are assigned to this network adapter, for example 10.45.16.10 for Access Edge, 10.45.16.20 for Web Conferencing Edge, 10.45.16.30 for AV Edge.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ed8d0-p104">É possível, embora não recomendável, usar um único endereço IP para todas as três interfaces de serviço de Borda. Apesar de economizar endereços IP, isso requer números de porta diferentes para cada serviço. O número de porta padrão é 443/TCP, o que garante que a maior parte dos firewalls remotos permita o tráfego. Alterar os valores de porta para (por exemplo) 5061/TCP para Borda de Acesso, 444/TCP para Borda de Webconferência e 443/TCP para Borda de AV pode causar problemas para usuários remotos cujo firewall atrás do qual estão não permitir o tráfego sobre as portas 5061/TCP e 444/TCP. Além disso, três endereços IP distintos facilita a solução de problemas pois permite filtragem por endereço IP.</span><span class="sxs-lookup"><span data-stu-id="ed8d0-p104">It is possible, though not recommended, to use a single IP address for all three Edge service interfaces. Though this does save IP addresses, it requires different port numbers for each service. The default port number is 443/TCP, which ensures that most remote firewalls will allow the traffic. Changing the port values to (for example) 5061/TCP for the Access Edge, 444/TCP for the Web Conferencing Edge and 443/TCP for the AV Edge might cause problems for remote users where a firewall that they are behind does not allow the traffic over 5061/TCP and 444/TCP. Additionally, three distinct IP addresses makes troubleshooting easier due to being able to filter on IP address.</span></span>

    
    </div>
    
    <span data-ttu-id="ed8d0-130">O endereço IP público da Borda de Acesso é o principal com o gateway padrão definido como o roteador integrado (10.45.16.1).</span><span class="sxs-lookup"><span data-stu-id="ed8d0-130">The Access Edge public IP address is primary with default gateway set to the integrated router (10.45.16.1).</span></span>
    
    <span data-ttu-id="ed8d0-131">Endereços IP privados de Borda de Webconferências e de A/V são endereços IP adicionais na seção **Avançado** das propriedades do **Protocolo IP versão 4 (TCP/IPv4)** e do **Protocolo IP versão 6 (TCP/IPv6)** das **Propriedades da Conexão Local** no Windows Server.</span><span class="sxs-lookup"><span data-stu-id="ed8d0-131">Web conferencing and A/V Edge private IP addresses are additional IP addresses in the **Advanced** section of the properties of **Internet Protocol Version 4 (TCP/IPv4)** and **Internet Protocol Version 6 (TCP/IPv6)** of the **Local Area Connection Properties** in Windows Server.</span></span>

  - <span data-ttu-id="ed8d0-132">**Adaptador de rede 2 Nó 2 (Interface externa)**</span><span class="sxs-lookup"><span data-stu-id="ed8d0-132">**Network adapter 2 Node 2 (External Interface)**</span></span>
    
    <span data-ttu-id="ed8d0-133">Três endereços IP privados são atribuídos a este adaptador de rede, por exemplo, 10.45.16.11 para Borda de Acesso, 10.45.16.21 para Borda de Webconferência e 10.45.16.31 para Borda de AV.</span><span class="sxs-lookup"><span data-stu-id="ed8d0-133">Three private IP addresses are assigned to this network adapter, for example 10.45.16.11 for Access Edge, 10.45.16.21 for Web Conferencing Edge, 10.45.16.31 for AV Edge.</span></span>
    
    <span data-ttu-id="ed8d0-134">O endereço IP público da Borda de Acesso é o principal com o gateway padrão definido como roteador integrado (10.45.16.1).</span><span class="sxs-lookup"><span data-stu-id="ed8d0-134">The Access Edge public IP address is primary with default gateway set to the integrated router (10.45.16.1).</span></span>
    
    <span data-ttu-id="ed8d0-135">Endereços IP privados de Borda de Webconferências e de A/V são endereços IP adicionais na seção **Avançado** das propriedades do **Protocolo IP versão 4 (TCP/IPv4)** e do **Protocolo IP versão 6 (TCP/IPv6)** das **Propriedades da Conexão Local** no Windows Server.</span><span class="sxs-lookup"><span data-stu-id="ed8d0-135">Web conferencing and A/V Edge private IP addresses are additional IP addresses in the **Advanced** section of the properties of **Internet Protocol Version 4 (TCP/IPv4)** and **Internet Protocol Version 6 (TCP/IPv6)** of the **Local Area Connection Properties** in Windows Server.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="ed8d0-136">A configuração do servidor de borda com dois adaptadores de rede é uma das duas opções.</span><span class="sxs-lookup"><span data-stu-id="ed8d0-136">Configuring the Edge Server with two network adapters is one of two options.</span></span> <span data-ttu-id="ed8d0-137">A outra opção é usar um adaptador de rede para o lado interno e três adaptadores de rede para o lado externo do servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="ed8d0-137">The other option is to use one network adapter for the internal side and three network adapters for the external side of the Edge Server.</span></span> <span data-ttu-id="ed8d0-138">O principal benefício dessa opção é um adaptador de rede distinto por serviço de servidor de borda e coleta de dados potencialmente mais concisa quando a solução de problemas é necessária</span><span class="sxs-lookup"><span data-stu-id="ed8d0-138">The main benefit of this option is a distinct network adapter per Edge Server service, and potentially more concise data collection when troubleshooting is necessary</span></span>



</div>

### <a name="dns-records-required-for-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-example"></a><span data-ttu-id="ed8d0-139">Registros de DNS necessários para a Topologia de borda consolidada em escala (DNS com balanceamento de carga): Borda Consolidada</span><span class="sxs-lookup"><span data-stu-id="ed8d0-139">DNS Records Required for Scaled Consolidated Edge, DNS Load Balancing with Private IP Addresses Using NAT (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ed8d0-140">Local/tipo/porta</span><span class="sxs-lookup"><span data-stu-id="ed8d0-140">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="ed8d0-141">Registro FQDN/DNS</span><span class="sxs-lookup"><span data-stu-id="ed8d0-141">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="ed8d0-142">Endereço IP/FQDN</span><span class="sxs-lookup"><span data-stu-id="ed8d0-142">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="ed8d0-143">Mapeia para/Comentários</span><span class="sxs-lookup"><span data-stu-id="ed8d0-143">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ed8d0-144">DNS Externo/A</span><span class="sxs-lookup"><span data-stu-id="ed8d0-144">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="ed8d0-145">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ed8d0-145">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="ed8d0-146">131.107.155.10 e 131.107.155.11</span><span class="sxs-lookup"><span data-stu-id="ed8d0-146">131.107.155.10 and 131.107.155.11</span></span></p></td>
<td><p><span data-ttu-id="ed8d0-147">Interface externa da Borda de Acesso (Contoso). Repetir conforme o necessário para todos os domínios SIP com usuários habilitados para o Lync</span><span class="sxs-lookup"><span data-stu-id="ed8d0-147">Access Edge external interface (Contoso) Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed8d0-148">DNS Externo/A</span><span class="sxs-lookup"><span data-stu-id="ed8d0-148">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="ed8d0-149">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ed8d0-149">webcon.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="ed8d0-150">131.107.155.20 e 131.107.155.21</span><span class="sxs-lookup"><span data-stu-id="ed8d0-150">131.107.155.20 and 131.107.155.21</span></span></p></td>
<td><p><span data-ttu-id="ed8d0-151">Interface externa da Borda de Webconferência</span><span class="sxs-lookup"><span data-stu-id="ed8d0-151">Web Conferencing Edge external interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed8d0-152">DNS Externo/A</span><span class="sxs-lookup"><span data-stu-id="ed8d0-152">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="ed8d0-153">av.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ed8d0-153">av.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="ed8d0-154">131.107.155.30 e 131.107.155.31</span><span class="sxs-lookup"><span data-stu-id="ed8d0-154">131.107.155.30 and 131.107.155.31</span></span></p></td>
<td><p><span data-ttu-id="ed8d0-155">Interface externa da Borda de A/V.</span><span class="sxs-lookup"><span data-stu-id="ed8d0-155">A/V Edge external interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed8d0-156">DNS Externo/SRV/443</span><span class="sxs-lookup"><span data-stu-id="ed8d0-156">External DNS/SRV/443</span></span></p></td>
<td><p><span data-ttu-id="ed8d0-157">_sip _sip._tls. contoso. com</span><span class="sxs-lookup"><span data-stu-id="ed8d0-157">_sip._tls.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="ed8d0-158">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ed8d0-158">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="ed8d0-159">Interface externa de borda de acesso.</span><span class="sxs-lookup"><span data-stu-id="ed8d0-159">Access Edge external interface.</span></span> <span data-ttu-id="ed8d0-160">Necessário para a configuração automática dos clientes do Lync 2013 e Lync 2010 para trabalhar externamente.</span><span class="sxs-lookup"><span data-stu-id="ed8d0-160">Required for automatic configuration of Lync 2013 and Lync 2010 clients to work externally.</span></span> <span data-ttu-id="ed8d0-161">Repita conforme for necessário para todos os domínios SIP com usuários Lync.</span><span class="sxs-lookup"><span data-stu-id="ed8d0-161">Repeat as necessary for all SIP domains with Lync enabled users.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed8d0-162">DNS Externo/SRV/5061</span><span class="sxs-lookup"><span data-stu-id="ed8d0-162">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="ed8d0-163">_sipfederationtls _sipfederationtls._tcp. contoso. com</span><span class="sxs-lookup"><span data-stu-id="ed8d0-163">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="ed8d0-164">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ed8d0-164">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="ed8d0-p107">Interface externa da Borda de Acesso SIP. Requerida para descoberta automática de DNS de parceiros federados conhecidos como "Domínio SIP Permitido" (chamado de federação aprimorada em versões anteriores). Repetir conforme o necessário para todos os domínios SIP com usuários habilitados para o Lync</span><span class="sxs-lookup"><span data-stu-id="ed8d0-p107">SIP Access Edge external interface. Required for automatic DNS discovery of federated partners known as “Allowed SIP Domain” (called enhanced federation in previous releases). Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed8d0-168">DNS Interno/A</span><span class="sxs-lookup"><span data-stu-id="ed8d0-168">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="ed8d0-169">lsedge.contoso.net</span><span class="sxs-lookup"><span data-stu-id="ed8d0-169">lsedge.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="ed8d0-170">172.25.33.10 e 172.25.33.11</span><span class="sxs-lookup"><span data-stu-id="ed8d0-170">172.25.33.10 and 172.25.33.11</span></span></p></td>
<td><p><span data-ttu-id="ed8d0-171">Interface interna da Borda Consolidada</span><span class="sxs-lookup"><span data-stu-id="ed8d0-171">Consolidated Edge internal interface</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="records-required-for-federation"></a><span data-ttu-id="ed8d0-172">Registros requeridos para federação</span><span class="sxs-lookup"><span data-stu-id="ed8d0-172">Records Required for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ed8d0-173">Local/tipo/porta</span><span class="sxs-lookup"><span data-stu-id="ed8d0-173">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="ed8d0-174">FQDN</span><span class="sxs-lookup"><span data-stu-id="ed8d0-174">FQDN</span></span></th>
<th><span data-ttu-id="ed8d0-175">Endereço IP/registro de host FQDN</span><span class="sxs-lookup"><span data-stu-id="ed8d0-175">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="ed8d0-176">Mapeia para/Comentários</span><span class="sxs-lookup"><span data-stu-id="ed8d0-176">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ed8d0-177">DNS Externo/SRV/5061</span><span class="sxs-lookup"><span data-stu-id="ed8d0-177">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="ed8d0-178">_sipfederationtls _sipfederationtls._tcp. contoso. com</span><span class="sxs-lookup"><span data-stu-id="ed8d0-178">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="ed8d0-179">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ed8d0-179">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="ed8d0-180">Interface externa da Borda de Acesso SIP Exgido para requisitos da descoberta de DNS de sua federação a outros potenciais parceiros da federação e é conhecido como “domínios SIP permitidos” (chamado Federação avançada em lançamentos prévios).Repetir conforme necessário para todos os domínios SIP com usuários Lync</span><span class="sxs-lookup"><span data-stu-id="ed8d0-180">SIP Access Edge external interface Required for automatic DNS discovery of your federation to other potential federation partners, and is known as “Allowed SIP Domains” (called enhanced federation in previous releases).Repeat as necessary for all SIP domains with Lync enabled users</span></span></p>
<div>

> [!IMPORTANT]  
> <span data-ttu-id="ed8d0-181">Este registro SRV é exigido para mobilidade e a notificação push para liberação de espaço</span><span class="sxs-lookup"><span data-stu-id="ed8d0-181">This SRV record is required for mobility and the push notification clearing house</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="ed8d0-182">Resumo DNS – Public Instant Messaging Connectivity</span><span class="sxs-lookup"><span data-stu-id="ed8d0-182">DNS Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ed8d0-183">Local/tipo/porta</span><span class="sxs-lookup"><span data-stu-id="ed8d0-183">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="ed8d0-184">Registro FQDN/DNS</span><span class="sxs-lookup"><span data-stu-id="ed8d0-184">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="ed8d0-185">Endereço IP/FQDN</span><span class="sxs-lookup"><span data-stu-id="ed8d0-185">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="ed8d0-186">Mapeia para/Comentários</span><span class="sxs-lookup"><span data-stu-id="ed8d0-186">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ed8d0-187">DNS Externo/A</span><span class="sxs-lookup"><span data-stu-id="ed8d0-187">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="ed8d0-188">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ed8d0-188">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="ed8d0-189">Interface de serviço de borda de acesso</span><span class="sxs-lookup"><span data-stu-id="ed8d0-189">Access Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="ed8d0-190">Interface externa da borda de acesso (Contoso)Repetir conforme necessário para todos os domínios SIP com usuários Lync</span><span class="sxs-lookup"><span data-stu-id="ed8d0-190">Access Edge external interface (Contoso)Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="ed8d0-191">Resumo DNS para Mensagens Extensíveis e Protocolo de Presença</span><span class="sxs-lookup"><span data-stu-id="ed8d0-191">DNS Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ed8d0-192">Local/tipo/porta</span><span class="sxs-lookup"><span data-stu-id="ed8d0-192">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="ed8d0-193">FQDN</span><span class="sxs-lookup"><span data-stu-id="ed8d0-193">FQDN</span></span></th>
<th><span data-ttu-id="ed8d0-194">Endereço IP/registro de host FQDN</span><span class="sxs-lookup"><span data-stu-id="ed8d0-194">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="ed8d0-195">Mapeia para/Comentários</span><span class="sxs-lookup"><span data-stu-id="ed8d0-195">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ed8d0-196">DNS Externo/SRV/5269</span><span class="sxs-lookup"><span data-stu-id="ed8d0-196">External DNS/SRV/5269</span></span></p></td>
<td><p><span data-ttu-id="ed8d0-197">_xmpp-server._tcp. contoso. com</span><span class="sxs-lookup"><span data-stu-id="ed8d0-197">_xmpp-server._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="ed8d0-198">xmpp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ed8d0-198">xmpp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="ed8d0-199">XMPP interface externa do proxy no serviço de borda de acesso ou no pool de borda. Repita conforme necessário para todos os domínios SIP internos com usuários habilitados para Lync onde contato com contatos do XMPP é permitido por meio da configuração da política de acesso externo por meio de uma política global, política de site onde o usuário está localizado ou política de usuário aplicada ao usuário habilitado para Lync.</span><span class="sxs-lookup"><span data-stu-id="ed8d0-199">XMPP proxy external interface on the Access Edge service or Edge pool.Repeat as necessary for all internal SIP domains with Lync enabled users where contact with XMPP contacts is allowed through the configuration of the External Access Policy through a global policy, site policy where the user is located, or user policy applied to the Lync-enabled user.</span></span> <span data-ttu-id="ed8d0-200">Um domínio XMPP permitido também deve ser configurado na política de Parceiros Federados XMPP.</span><span class="sxs-lookup"><span data-stu-id="ed8d0-200">An allowed XMPP domain must also be configured in the XMPP Federated Partners policy.</span></span> <span data-ttu-id="ed8d0-201">Veja os tópicos em <strong>Consulte também </strong> para mais detalhes</span><span class="sxs-lookup"><span data-stu-id="ed8d0-201">See topics in <strong>See Also</strong> for additional details</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed8d0-202">DNS Externo/A</span><span class="sxs-lookup"><span data-stu-id="ed8d0-202">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="ed8d0-203">xmpp.contoso.com (por exemplo)</span><span class="sxs-lookup"><span data-stu-id="ed8d0-203">xmpp.contoso.com (for example)</span></span></p></td>
<td><p><span data-ttu-id="ed8d0-204">Endereço IP do serviço de borda de acesso no servidor de borda ou no pool de borda que hospeda o proxy do XMPP</span><span class="sxs-lookup"><span data-stu-id="ed8d0-204">IP address of Access Edge service on your Edge Server or Edge pool hosting XMPP proxy</span></span></p></td>
<td><p><span data-ttu-id="ed8d0-205">Aponta para o serviço de borda de acesso ou o pool de borda que hospeda o serviço de proxy XMPP.</span><span class="sxs-lookup"><span data-stu-id="ed8d0-205">Points to the Access Edge service or Edge pool that hosts the XMPP proxy service.</span></span> <span data-ttu-id="ed8d0-206">Tipicamente, o registro SRV que você criar apontará para este host (A ou AAAA) record</span><span class="sxs-lookup"><span data-stu-id="ed8d0-206">Typically, the SRV record that you create will point to this host (A or AAAA) record</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

