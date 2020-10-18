---
title: Resumo de DNS-borda consolidada única com endereços IP públicos
description: Resumo de DNS-borda consolidada única com endereços IP públicos.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Single consolidated edge with public IP addresses
ms:assetid: 7b83eae4-aa1a-4cc6-8077-42176d56cab5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205025(v=OCS.15)
ms:contentKeyID: 48184601
ms.date: 03/09/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 58f0787d894e741951fd220ef3b2a9fada8183b3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572787"
---
# <a name="dns-summary---single-consolidated-edge-with-public-ip-addresses-in-lync-server-2013"></a><span data-ttu-id="8562d-103">Resumo de DNS-borda consolidada única com endereços IP públicos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8562d-103">DNS summary - Single consolidated edge with public IP addresses in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8562d-104">_**Última modificação do tópico:** 2017-03-09_</span><span class="sxs-lookup"><span data-stu-id="8562d-104">_**Topic Last Modified:** 2017-03-09_</span></span>

<span data-ttu-id="8562d-105">Os requisitos de registro DNS para acesso remoto ao Lync Server 2013 são bem simples comparados com os de certificados e portas.</span><span class="sxs-lookup"><span data-stu-id="8562d-105">DNS record requirements for remote access to Lync Server 2013 are fairly straightforward compared to those for certificates and ports.</span></span> <span data-ttu-id="8562d-106">Além disso, muitos registros são opcionais, dependendo de como você configura os clientes que executam o Lync 2013 e se você habilita a Federação.</span><span class="sxs-lookup"><span data-stu-id="8562d-106">Also, many records are optional, depending on how you configure clients running Lync 2013 and whether you enable federation.</span></span>

<span data-ttu-id="8562d-107">Para obter detalhes sobre os requisitos de DNS do Lync 2013, consulte [determine DNS Requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8562d-107">For details about Lync 2013 DNS requirements, see [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="8562d-108">Para obter detalhes sobre a configuração automática de clientes que executam o Lync 2013 se o DNS de Split-Brain não estiver configurado, consulte "configuração automática sem Split-Brain DNS" em [determinar requisitos de DNS para o Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8562d-108">For details about automatic configuration of clients running Lync 2013 if split-brain DNS is not configured, see “Automatic Configuration without Split-Brain DNS” in [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="8562d-109">A tabela a seguir contém um resumo dos registros DNS requeridos para oferecer suporte à topologia de borda consolidada única exibida na imagem Topologia de Borda Consolidada Única.</span><span class="sxs-lookup"><span data-stu-id="8562d-109">The following table contains a summary of the DNS records that are required to support the single consolidated edge topology shown in the Single Consolidated Edge Topology figure.</span></span> <span data-ttu-id="8562d-110">Observe que determinados registros DNS são necessários apenas para a configuração automática dos clientes Lync 2013 e Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="8562d-110">Note that certain DNS records are required only for automatic configuration of Lync 2013 and Lync 2010 clients.</span></span> <span data-ttu-id="8562d-111">Se você planeja usar objetos de política de grupo (GPOs) para configurar os clientes do Lync, os registros de configuração automática associados não serão necessários.</span><span class="sxs-lookup"><span data-stu-id="8562d-111">If you plan to use group policy objects (GPOs) to configure Lync clients, the associated automatic configuration records are not necessary.</span></span>

<div>

## <a name="important-edge-server-network-adapter-requirements"></a><span data-ttu-id="8562d-112">IMPORTANTE: requisitos do adaptador de rede do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="8562d-112">IMPORTANT: Edge Server Network Adapter Requirements</span></span>

<span data-ttu-id="8562d-113">Para evitar problemas de roteamento, verifique se há pelo menos dois adaptadores de rede em seus servidores de borda e se o gateway padrão está definido somente no adaptador de rede associado à interface externa.</span><span class="sxs-lookup"><span data-stu-id="8562d-113">To avoid routing issues, verify that there are at least two network adapters in your Edge Servers and that the default gateway is set only on the network adapter associated with the external interface.</span></span> <span data-ttu-id="8562d-114">Por exemplo, conforme mostrado na topologia de borda consolidada única com endereços IP públicos em [uma única borda consolidada com endereços IP públicos no Lync Server 2013](lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md), o gateway padrão apontaria para o roteador externo no seu perímetro de Internet ou firewall que pode fornecer um endereço IP público.</span><span class="sxs-lookup"><span data-stu-id="8562d-114">For example, as shown in the Single Consolidated Edge Topology with Public IP Addresses figure in [Single consolidated edge with public IP addresses in Lync Server 2013](lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md), the default gateway would point to the external router at your Internet perimeter or firewall that can provide a public IP addresses.</span></span> <span data-ttu-id="8562d-115">A relação de rede para interfaces de servidor de borda é uma relação de rota em vez de uma relação NAT.</span><span class="sxs-lookup"><span data-stu-id="8562d-115">The network relationship for Edge Server interfaces is a route relationship instead of a NAT relationship.</span></span>

<span data-ttu-id="8562d-116">Você pode configurar dois adaptadores de rede em seu Servidor de Borda da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="8562d-116">You can configure two network adapters in your Edge Server as follows:</span></span>

  - <span data-ttu-id="8562d-117">**Adaptador de rede 1 (Interface Interna)**</span><span class="sxs-lookup"><span data-stu-id="8562d-117">**Network adapter 1 (Internal Interface)**</span></span>
    
    <span data-ttu-id="8562d-118">Interface interna com 172.25.33.10 atribuído.</span><span class="sxs-lookup"><span data-stu-id="8562d-118">Internal interface with 172.25.33.10 assigned.</span></span>
    
    <span data-ttu-id="8562d-119">Nenhum gateway padrão definido.</span><span class="sxs-lookup"><span data-stu-id="8562d-119">No default gateway is defined.</span></span>
    
    <span data-ttu-id="8562d-120">Certifique-se de que há uma rota da rede que contém a interface interna da borda para qualquer rede que contenha servidores que executam os clientes do Lync Server 2013 ou do Lync Server 2013 (por exemplo, de 172.25.33.0 para 192.168.10.0).</span><span class="sxs-lookup"><span data-stu-id="8562d-120">Ensure that there is a route from the network containing the Edge internal interface to any networks that contain servers running Lync Server 2013 or Lync Server 2013 clients (for example, from 172.25.33.0 to 192.168.10.0).</span></span>

  - <span data-ttu-id="8562d-121">**Adaptador de rede 2 (Interface Externa)**</span><span class="sxs-lookup"><span data-stu-id="8562d-121">**Network adapter 2 (External Interface)**</span></span>
    
    <span data-ttu-id="8562d-122">Três endereços IP públicos são atribuídos a este adaptador de rede, por exemplo, 131.107.155.10 para Borda de Acesso, 131.107.155.20 para Borda de Conferência da Web, 131.107.155.30 para Borda AV.</span><span class="sxs-lookup"><span data-stu-id="8562d-122">Three public IP addresses are assigned to this network adapter, for example 131.107.155.10 for Access Edge, 131.107.155.20 for Web Conferencing Edge, 131.107.155.30 for AV Edge.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="8562d-p104">É possível, embora não seja recomendado, usar um único endereço IP para as três interfaces de serviço de Borda. Embora isso não salve endereços IP, exige diferentes números de porta para cada serviço. O número de porta padrão é 443/TCP, que garante que a maioria dos firewalls remotos permitirão o tráfego. Mudar os valores de porta para (por exemplo) 5061/TCP para Borda de Acesso, 444/TCP para Borda de Conferência da Web e 443/TCP para Borda AV pode causar problemas para usuários remotos que estejam protegidos por um firewall que não permite tráfego além de 5061/TCP e 444/TCP. Além disso, três endereços IP distintos tornam a resolução de problemas mais fácil por poderem filtrar o endereço IP.</span><span class="sxs-lookup"><span data-stu-id="8562d-p104">It is possible, though not recommended, to use a single IP address for all three Edge service interfaces. Though this does save IP addresses, it requires different port numbers for each service. The default port number is 443/TCP, which ensures that most remote firewalls will allow the traffic. Changing the port values to (for example) 5061/TCP for the Access Edge, 444/TCP for the Web Conferencing Edge and 443/TCP for the AV Edge might cause problems for remote users where a firewall that they are behind does not allow the traffic over 5061/TCP and 444/TCP. Additionally, three distinct IP addresses makes troubleshooting easier due to being able to filter on IP address.</span></span>

    
    </div>
    
    <span data-ttu-id="8562d-128">O endereço IP público de Borda de Acesso é primário com gateway padrão definido para o roteador público (131.107.155.1).</span><span class="sxs-lookup"><span data-stu-id="8562d-128">The Access Edge public IP address is primary with default gateway set to the public router (131.107.155.1).</span></span>
    
    <span data-ttu-id="8562d-129">Endereços IP públicos de Webconferência e Borda A/V são endereços IP adicionais na seção **Avançado** das propriedades do **Protocolo de Internet Versão 4 (TCP/IPv4)** e **Protocolo de Internet Versão 6 (TCP/IPv6)** das \*\*Propriedades de Conexão de Área Local \*\* no Windows Server.</span><span class="sxs-lookup"><span data-stu-id="8562d-129">Web conferencing and A/V Edge public IP addresses are additional IP addresses in the **Advanced** section of the properties of **Internet Protocol Version 4 (TCP/IPv4)** and **Internet Protocol Version 6 (TCP/IPv6)** of the **Local Area Connection Properties** in Windows Server.</span></span>

<div>


> [!TIP]
> <span data-ttu-id="8562d-130">A configuração do servidor de borda com dois adaptadores de rede é uma das duas opções.</span><span class="sxs-lookup"><span data-stu-id="8562d-130">Configuring the Edge Server with two network adapters is one of two options.</span></span> <span data-ttu-id="8562d-131">A outra opção é usar um adaptador de rede para o lado interno e três adaptadores de rede para o lado externo do servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="8562d-131">The other option is to use one network adapter for the internal side and three network adapters for the external side of the Edge Server.</span></span> <span data-ttu-id="8562d-132">O principal benefício dessa opção é um adaptador de rede distinto por serviço de servidor de borda e coleta de dados potencialmente mais concisa quando a solução de problemas é necessária</span><span class="sxs-lookup"><span data-stu-id="8562d-132">The main benefit of this option is a distinct network adapter per Edge Server service, and potentially more concise data collection when troubleshooting is necessary</span></span>



</div>

### <a name="dns-records-required-for-single-consolidated-edge-with-public-ip-addresses-example"></a><span data-ttu-id="8562d-133">Registros DNS Exigidos para a Borda Única Consolidada com Endereços IP Únicos (Exemplo)</span><span class="sxs-lookup"><span data-stu-id="8562d-133">DNS Records Required for Single Consolidated Edge with Public IP Addresses (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8562d-134">Local/tipo/porta</span><span class="sxs-lookup"><span data-stu-id="8562d-134">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="8562d-135">Registro FQDN/DNS</span><span class="sxs-lookup"><span data-stu-id="8562d-135">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="8562d-136">Endereço IP/FQDN</span><span class="sxs-lookup"><span data-stu-id="8562d-136">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="8562d-137">Mapeia para/Comentários</span><span class="sxs-lookup"><span data-stu-id="8562d-137">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8562d-138">DNS Externo/A</span><span class="sxs-lookup"><span data-stu-id="8562d-138">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="8562d-139">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8562d-139">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="8562d-140">131.107.155.10</span><span class="sxs-lookup"><span data-stu-id="8562d-140">131.107.155.10</span></span></p></td>
<td><p><span data-ttu-id="8562d-141">Interface externa da borda de acesso (contoso) repete como necessário para todos os domínios SIP com usuários habilitados para Lync</span><span class="sxs-lookup"><span data-stu-id="8562d-141">Access Edge external interface (Contoso) Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8562d-142">DNS Externo/A</span><span class="sxs-lookup"><span data-stu-id="8562d-142">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="8562d-143">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8562d-143">webcon.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="8562d-144">131.107.155.20</span><span class="sxs-lookup"><span data-stu-id="8562d-144">131.107.155.20</span></span></p></td>
<td><p><span data-ttu-id="8562d-145">Interface externa da borda de webconferências</span><span class="sxs-lookup"><span data-stu-id="8562d-145">Web Conferencing Edge external interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8562d-146">DNS Externo/A</span><span class="sxs-lookup"><span data-stu-id="8562d-146">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="8562d-147">av.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8562d-147">av.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="8562d-148">131.107.155.30</span><span class="sxs-lookup"><span data-stu-id="8562d-148">131.107.155.30</span></span></p></td>
<td><p><span data-ttu-id="8562d-149">Interface externa da Borda de A/V</span><span class="sxs-lookup"><span data-stu-id="8562d-149">A/V Edge external interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8562d-150">DNS Externo/SRV/443</span><span class="sxs-lookup"><span data-stu-id="8562d-150">External DNS/SRV/443</span></span></p></td>
<td><p><span data-ttu-id="8562d-151">_sip _sip._tls. contoso. com</span><span class="sxs-lookup"><span data-stu-id="8562d-151">_sip._tls.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="8562d-152">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8562d-152">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="8562d-153">Interface externa de borda de acesso.</span><span class="sxs-lookup"><span data-stu-id="8562d-153">Access Edge external interface.</span></span> <span data-ttu-id="8562d-154">Necessário para a configuração automática dos clientes do Lync 2013 e Lync 2010 para trabalhar externamente.</span><span class="sxs-lookup"><span data-stu-id="8562d-154">Required for automatic configuration of Lync 2013 and Lync 2010 clients to work externally.</span></span> <span data-ttu-id="8562d-155">Repita conforme for necessário para todos os domínios SIP com usuários Lync.</span><span class="sxs-lookup"><span data-stu-id="8562d-155">Repeat as necessary for all SIP domains with Lync enabled users.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8562d-156">DNS Externo/SRV/5061</span><span class="sxs-lookup"><span data-stu-id="8562d-156">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="8562d-157">_sipfederationtls _sipfederationtls._tcp. contoso. com</span><span class="sxs-lookup"><span data-stu-id="8562d-157">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="8562d-158">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8562d-158">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="8562d-159">Interface externa de borda de acesso SIP. Requerido para descoberta de DNS automática de parceiros federados, conhecida como "Domínio SIP Permitido" (chamada de federação avançada em versões anteriores). Repita conforme necessário para todos os domínios SIP com usuários Lync</span><span class="sxs-lookup"><span data-stu-id="8562d-159">SIP Access Edge external interface Required for automatic DNS discovery of federated partners known as “Allowed SIP Domain” (called enhanced federation in previous releases).Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8562d-160">DNS/A interno</span><span class="sxs-lookup"><span data-stu-id="8562d-160">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="8562d-161">lsedge.contoso.net</span><span class="sxs-lookup"><span data-stu-id="8562d-161">lsedge.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="8562d-162">172.25.33.10</span><span class="sxs-lookup"><span data-stu-id="8562d-162">172.25.33.10</span></span></p></td>
<td><p><span data-ttu-id="8562d-163">Interface interna da Borda Consolidada</span><span class="sxs-lookup"><span data-stu-id="8562d-163">Consolidated Edge internal interface</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]
> <span data-ttu-id="8562d-164">Os registros listados na tabela anterior são exibidos com uma extensão <EM>.net</EM> ou <EM>.com</EM> para destacar em qual zona precisam residir caso você não esteja usando split-brain DNS.</span><span class="sxs-lookup"><span data-stu-id="8562d-164">The records listed in the previous table are shown with either a <EM>.net</EM> extension or a <EM>.com</EM> extension to highlight which zone they need to reside in if you are not using split-brain DNS.</span></span> <span data-ttu-id="8562d-165">Se você estiver usando split-brain DNS, todos os registros devem estar na mesma zona, com a única distinção sendo se estão na versão interna ou externa.</span><span class="sxs-lookup"><span data-stu-id="8562d-165">If you are using split-brain DNS, all records would be in the same zone, with the only distinction being whether they are in the internal or external version.</span></span> <span data-ttu-id="8562d-166">Para obter detalhes, consulte "split-brain DNS" em <A href="lync-server-2013-determine-dns-requirements.md">determine DNS Requirements for Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="8562d-166">For details, see “Split-Brain DNS” in <A href="lync-server-2013-determine-dns-requirements.md">Determine DNS requirements for Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="records-required-for-federation"></a><span data-ttu-id="8562d-167">Registros exigidos para Federação</span><span class="sxs-lookup"><span data-stu-id="8562d-167">Records Required for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8562d-168">Local/tipo/porta</span><span class="sxs-lookup"><span data-stu-id="8562d-168">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="8562d-169">FQDN</span><span class="sxs-lookup"><span data-stu-id="8562d-169">FQDN</span></span></th>
<th><span data-ttu-id="8562d-170">Endereço IP/registro de host FQDN</span><span class="sxs-lookup"><span data-stu-id="8562d-170">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="8562d-171">Mapeia para/Comentários</span><span class="sxs-lookup"><span data-stu-id="8562d-171">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8562d-172">DNS Externo/SRV/5061</span><span class="sxs-lookup"><span data-stu-id="8562d-172">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="8562d-173">_sipfederationtls _sipfederationtls._tcp. contoso. com</span><span class="sxs-lookup"><span data-stu-id="8562d-173">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="8562d-174">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8562d-174">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="8562d-175">Interface externa da Borda de Acesso SIP Exgido para requisitos da descoberta de DNS de sua federação a outros potenciais parceiros da federação e é conhecido como “domínios SIP permitidos” (chamado Federação avançada em lançamentos prévios).Repetir conforme necessário para todos os domínios SIP com usuários Lync</span><span class="sxs-lookup"><span data-stu-id="8562d-175">SIP Access Edge external interface Required for automatic DNS discovery of your federation to other potential federation partners, and is known as “Allowed SIP Domains” (called enhanced federation in previous releases).Repeat as necessary for all SIP domains with Lync enabled users</span></span></p>



> [!IMPORTANT]
> <span data-ttu-id="8562d-176">Este registro SRV é exigido para mobilidade e a notificação push para liberação de espaço</span><span class="sxs-lookup"><span data-stu-id="8562d-176">This SRV record is required for mobility and the push notification clearing house</span></span>

</td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="8562d-177">Resumo DNS para Mensagens Extensíveis e Protocolo de Presença</span><span class="sxs-lookup"><span data-stu-id="8562d-177">DNS Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8562d-178">Local/tipo/porta</span><span class="sxs-lookup"><span data-stu-id="8562d-178">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="8562d-179">FQDN</span><span class="sxs-lookup"><span data-stu-id="8562d-179">FQDN</span></span></th>
<th><span data-ttu-id="8562d-180">Endereço IP/registro de host FQDN</span><span class="sxs-lookup"><span data-stu-id="8562d-180">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="8562d-181">Mapeia para/Comentários</span><span class="sxs-lookup"><span data-stu-id="8562d-181">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8562d-182">DNS Externo/SRV/5269</span><span class="sxs-lookup"><span data-stu-id="8562d-182">External DNS/SRV/5269</span></span></p></td>
<td><p><span data-ttu-id="8562d-183">_xmpp-server._tcp. contoso. com</span><span class="sxs-lookup"><span data-stu-id="8562d-183">_xmpp-server._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="8562d-184">xmpp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8562d-184">xmpp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="8562d-185">XMPP interface externa do proxy no serviço de borda de acesso ou no pool de borda. Repita conforme necessário para todos os domínios SIP internos com usuários habilitados para Lync onde contato com contatos do XMPP é permitido por meio da configuração da política de acesso externo por meio de uma política global, política de site onde o usuário está localizado ou política de usuário aplicada ao usuário habilitado para Lync.</span><span class="sxs-lookup"><span data-stu-id="8562d-185">XMPP proxy external interface on the Access Edge service or Edge pool.Repeat as necessary for all internal SIP domains with Lync enabled users where contact with XMPP contacts is allowed through the configuration of the External Access Policy through a global policy, site policy where the user is located, or user policy applied to the Lync-enabled user.</span></span> <span data-ttu-id="8562d-186">Um domínio XMPP permitido também deve ser configurado na política de Parceiros Federados XMPP.</span><span class="sxs-lookup"><span data-stu-id="8562d-186">An allowed XMPP domain must also be configured in the XMPP Federated Partners policy.</span></span> <span data-ttu-id="8562d-187">Veja os tópicos em <strong>Consulte também </strong> para mais detalhes</span><span class="sxs-lookup"><span data-stu-id="8562d-187">See topics in <strong>See Also</strong> for additional details</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8562d-188">DNS Externo/A</span><span class="sxs-lookup"><span data-stu-id="8562d-188">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="8562d-189">xmpp.contoso.com (por exemplo)</span><span class="sxs-lookup"><span data-stu-id="8562d-189">xmpp.contoso.com (for example)</span></span></p></td>
<td><p><span data-ttu-id="8562d-190">Endereço IP do serviço de borda de acesso no servidor de borda ou no pool de borda que hospeda o proxy do XMPP</span><span class="sxs-lookup"><span data-stu-id="8562d-190">IP address of Access Edge service on your Edge Server or Edge pool hosting XMPP proxy</span></span></p></td>
<td><p><span data-ttu-id="8562d-191">Aponta para o serviço de borda de acesso ou o pool de borda que hospeda o serviço de proxy XMPP.</span><span class="sxs-lookup"><span data-stu-id="8562d-191">Points to the Access Edge service or Edge pool that hosts the XMPP proxy service.</span></span> <span data-ttu-id="8562d-192">Tipicamente, o registro SRV que você criar apontará para este host (A ou AAAA) record</span><span class="sxs-lookup"><span data-stu-id="8562d-192">Typically, the SRV record that you create will point to this host (A or AAAA) record</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

