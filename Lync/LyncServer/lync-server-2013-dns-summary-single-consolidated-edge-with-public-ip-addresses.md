---
title: Resumo de DNS-borda consolidada única com endereços IP públicos
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
ms.openlocfilehash: 3e0604a018b4b558612e2e2a3802ca97676b58b2
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48501228"
---
# <a name="dns-summary---single-consolidated-edge-with-public-ip-addresses-in-lync-server-2013"></a><span data-ttu-id="0f3d3-102">Resumo de DNS-borda consolidada única com endereços IP públicos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0f3d3-102">DNS summary - Single consolidated edge with public IP addresses in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0f3d3-103">_**Última modificação do tópico:** 2017-03-09_</span><span class="sxs-lookup"><span data-stu-id="0f3d3-103">_**Topic Last Modified:** 2017-03-09_</span></span>

<span data-ttu-id="0f3d3-104">Os requisitos de registro DNS para acesso remoto ao Lync Server 2013 são bem simples comparados com os de certificados e portas.</span><span class="sxs-lookup"><span data-stu-id="0f3d3-104">DNS record requirements for remote access to Lync Server 2013 are fairly straightforward compared to those for certificates and ports.</span></span> <span data-ttu-id="0f3d3-105">Além disso, muitos registros são opcionais, dependendo de como você configura os clientes que executam o Lync 2013 e se você habilita a Federação.</span><span class="sxs-lookup"><span data-stu-id="0f3d3-105">Also, many records are optional, depending on how you configure clients running Lync 2013 and whether you enable federation.</span></span>

<span data-ttu-id="0f3d3-106">Para obter detalhes sobre os requisitos de DNS do Lync 2013, consulte [determine DNS Requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0f3d3-106">For details about Lync 2013 DNS requirements, see [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="0f3d3-107">Para obter detalhes sobre a configuração automática de clientes que executam o Lync 2013 se o DNS de Split-Brain não estiver configurado, consulte "configuração automática sem Split-Brain DNS" em [determinar requisitos de DNS para o Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0f3d3-107">For details about automatic configuration of clients running Lync 2013 if split-brain DNS is not configured, see “Automatic Configuration without Split-Brain DNS” in [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="0f3d3-108">A tabela a seguir contém um resumo dos registros DNS requeridos para oferecer suporte à topologia de borda consolidada única exibida na imagem Topologia de Borda Consolidada Única.</span><span class="sxs-lookup"><span data-stu-id="0f3d3-108">The following table contains a summary of the DNS records that are required to support the single consolidated edge topology shown in the Single Consolidated Edge Topology figure.</span></span> <span data-ttu-id="0f3d3-109">Observe que determinados registros DNS são necessários apenas para a configuração automática dos clientes Lync 2013 e Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="0f3d3-109">Note that certain DNS records are required only for automatic configuration of Lync 2013 and Lync 2010 clients.</span></span> <span data-ttu-id="0f3d3-110">Se você planeja usar objetos de política de grupo (GPOs) para configurar os clientes do Lync, os registros de configuração automática associados não serão necessários.</span><span class="sxs-lookup"><span data-stu-id="0f3d3-110">If you plan to use group policy objects (GPOs) to configure Lync clients, the associated automatic configuration records are not necessary.</span></span>

<div>

## <a name="important-edge-server-network-adapter-requirements"></a><span data-ttu-id="0f3d3-111">IMPORTANTE: requisitos do adaptador de rede do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="0f3d3-111">IMPORTANT: Edge Server Network Adapter Requirements</span></span>

<span data-ttu-id="0f3d3-112">Para evitar problemas de roteamento, verifique se há pelo menos dois adaptadores de rede em seus servidores de borda e se o gateway padrão está definido somente no adaptador de rede associado à interface externa.</span><span class="sxs-lookup"><span data-stu-id="0f3d3-112">To avoid routing issues, verify that there are at least two network adapters in your Edge Servers and that the default gateway is set only on the network adapter associated with the external interface.</span></span> <span data-ttu-id="0f3d3-113">Por exemplo, conforme mostrado na topologia de borda consolidada única com endereços IP públicos em [uma única borda consolidada com endereços IP públicos no Lync Server 2013](lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md), o gateway padrão apontaria para o roteador externo no seu perímetro de Internet ou firewall que pode fornecer um endereço IP público.</span><span class="sxs-lookup"><span data-stu-id="0f3d3-113">For example, as shown in the Single Consolidated Edge Topology with Public IP Addresses figure in [Single consolidated edge with public IP addresses in Lync Server 2013](lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md), the default gateway would point to the external router at your Internet perimeter or firewall that can provide a public IP addresses.</span></span> <span data-ttu-id="0f3d3-114">A relação de rede para interfaces de servidor de borda é uma relação de rota em vez de uma relação NAT.</span><span class="sxs-lookup"><span data-stu-id="0f3d3-114">The network relationship for Edge Server interfaces is a route relationship instead of a NAT relationship.</span></span>

<span data-ttu-id="0f3d3-115">Você pode configurar dois adaptadores de rede em seu Servidor de Borda da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="0f3d3-115">You can configure two network adapters in your Edge Server as follows:</span></span>

  - <span data-ttu-id="0f3d3-116">**Adaptador de rede 1 (Interface Interna)**</span><span class="sxs-lookup"><span data-stu-id="0f3d3-116">**Network adapter 1 (Internal Interface)**</span></span>
    
    <span data-ttu-id="0f3d3-117">Interface interna com 172.25.33.10 atribuído.</span><span class="sxs-lookup"><span data-stu-id="0f3d3-117">Internal interface with 172.25.33.10 assigned.</span></span>
    
    <span data-ttu-id="0f3d3-118">Nenhum gateway padrão definido.</span><span class="sxs-lookup"><span data-stu-id="0f3d3-118">No default gateway is defined.</span></span>
    
    <span data-ttu-id="0f3d3-119">Certifique-se de que há uma rota da rede que contém a interface interna da borda para qualquer rede que contenha servidores que executam os clientes do Lync Server 2013 ou do Lync Server 2013 (por exemplo, de 172.25.33.0 para 192.168.10.0).</span><span class="sxs-lookup"><span data-stu-id="0f3d3-119">Ensure that there is a route from the network containing the Edge internal interface to any networks that contain servers running Lync Server 2013 or Lync Server 2013 clients (for example, from 172.25.33.0 to 192.168.10.0).</span></span>

  - <span data-ttu-id="0f3d3-120">**Adaptador de rede 2 (Interface Externa)**</span><span class="sxs-lookup"><span data-stu-id="0f3d3-120">**Network adapter 2 (External Interface)**</span></span>
    
    <span data-ttu-id="0f3d3-121">Três endereços IP públicos são atribuídos a este adaptador de rede, por exemplo, 131.107.155.10 para Borda de Acesso, 131.107.155.20 para Borda de Conferência da Web, 131.107.155.30 para Borda AV.</span><span class="sxs-lookup"><span data-stu-id="0f3d3-121">Three public IP addresses are assigned to this network adapter, for example 131.107.155.10 for Access Edge, 131.107.155.20 for Web Conferencing Edge, 131.107.155.30 for AV Edge.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="0f3d3-p104">É possível, embora não seja recomendado, usar um único endereço IP para as três interfaces de serviço de Borda. Embora isso não salve endereços IP, exige diferentes números de porta para cada serviço. O número de porta padrão é 443/TCP, que garante que a maioria dos firewalls remotos permitirão o tráfego. Mudar os valores de porta para (por exemplo) 5061/TCP para Borda de Acesso, 444/TCP para Borda de Conferência da Web e 443/TCP para Borda AV pode causar problemas para usuários remotos que estejam protegidos por um firewall que não permite tráfego além de 5061/TCP e 444/TCP. Além disso, três endereços IP distintos tornam a resolução de problemas mais fácil por poderem filtrar o endereço IP.</span><span class="sxs-lookup"><span data-stu-id="0f3d3-p104">It is possible, though not recommended, to use a single IP address for all three Edge service interfaces. Though this does save IP addresses, it requires different port numbers for each service. The default port number is 443/TCP, which ensures that most remote firewalls will allow the traffic. Changing the port values to (for example) 5061/TCP for the Access Edge, 444/TCP for the Web Conferencing Edge and 443/TCP for the AV Edge might cause problems for remote users where a firewall that they are behind does not allow the traffic over 5061/TCP and 444/TCP. Additionally, three distinct IP addresses makes troubleshooting easier due to being able to filter on IP address.</span></span>

    
    </div>
    
    <span data-ttu-id="0f3d3-127">O endereço IP público de Borda de Acesso é primário com gateway padrão definido para o roteador público (131.107.155.1).</span><span class="sxs-lookup"><span data-stu-id="0f3d3-127">The Access Edge public IP address is primary with default gateway set to the public router (131.107.155.1).</span></span>
    
    <span data-ttu-id="0f3d3-128">Endereços IP públicos de Webconferência e Borda A/V são endereços IP adicionais na seção **Avançado** das propriedades do **Protocolo de Internet Versão 4 (TCP/IPv4)** e **Protocolo de Internet Versão 6 (TCP/IPv6)** das \*\*Propriedades de Conexão de Área Local \*\* no Windows Server.</span><span class="sxs-lookup"><span data-stu-id="0f3d3-128">Web conferencing and A/V Edge public IP addresses are additional IP addresses in the **Advanced** section of the properties of **Internet Protocol Version 4 (TCP/IPv4)** and **Internet Protocol Version 6 (TCP/IPv6)** of the **Local Area Connection Properties** in Windows Server.</span></span>

<div>


> [!TIP]
> <span data-ttu-id="0f3d3-129">A configuração do servidor de borda com dois adaptadores de rede é uma das duas opções.</span><span class="sxs-lookup"><span data-stu-id="0f3d3-129">Configuring the Edge Server with two network adapters is one of two options.</span></span> <span data-ttu-id="0f3d3-130">A outra opção é usar um adaptador de rede para o lado interno e três adaptadores de rede para o lado externo do servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="0f3d3-130">The other option is to use one network adapter for the internal side and three network adapters for the external side of the Edge Server.</span></span> <span data-ttu-id="0f3d3-131">O principal benefício dessa opção é um adaptador de rede distinto por serviço de servidor de borda e coleta de dados potencialmente mais concisa quando a solução de problemas é necessária</span><span class="sxs-lookup"><span data-stu-id="0f3d3-131">The main benefit of this option is a distinct network adapter per Edge Server service, and potentially more concise data collection when troubleshooting is necessary</span></span>



</div>

### <a name="dns-records-required-for-single-consolidated-edge-with-public-ip-addresses-example"></a><span data-ttu-id="0f3d3-132">Registros DNS Exigidos para a Borda Única Consolidada com Endereços IP Únicos (Exemplo)</span><span class="sxs-lookup"><span data-stu-id="0f3d3-132">DNS Records Required for Single Consolidated Edge with Public IP Addresses (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0f3d3-133">Local/tipo/porta</span><span class="sxs-lookup"><span data-stu-id="0f3d3-133">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="0f3d3-134">Registro FQDN/DNS</span><span class="sxs-lookup"><span data-stu-id="0f3d3-134">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="0f3d3-135">Endereço IP/FQDN</span><span class="sxs-lookup"><span data-stu-id="0f3d3-135">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="0f3d3-136">Mapeia para/Comentários</span><span class="sxs-lookup"><span data-stu-id="0f3d3-136">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0f3d3-137">DNS Externo/A</span><span class="sxs-lookup"><span data-stu-id="0f3d3-137">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="0f3d3-138">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0f3d3-138">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="0f3d3-139">131.107.155.10</span><span class="sxs-lookup"><span data-stu-id="0f3d3-139">131.107.155.10</span></span></p></td>
<td><p><span data-ttu-id="0f3d3-140">Interface externa da borda de acesso (contoso) repete como necessário para todos os domínios SIP com usuários habilitados para Lync</span><span class="sxs-lookup"><span data-stu-id="0f3d3-140">Access Edge external interface (Contoso) Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0f3d3-141">DNS Externo/A</span><span class="sxs-lookup"><span data-stu-id="0f3d3-141">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="0f3d3-142">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0f3d3-142">webcon.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="0f3d3-143">131.107.155.20</span><span class="sxs-lookup"><span data-stu-id="0f3d3-143">131.107.155.20</span></span></p></td>
<td><p><span data-ttu-id="0f3d3-144">Interface externa da borda de webconferências</span><span class="sxs-lookup"><span data-stu-id="0f3d3-144">Web Conferencing Edge external interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0f3d3-145">DNS Externo/A</span><span class="sxs-lookup"><span data-stu-id="0f3d3-145">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="0f3d3-146">av.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0f3d3-146">av.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="0f3d3-147">131.107.155.30</span><span class="sxs-lookup"><span data-stu-id="0f3d3-147">131.107.155.30</span></span></p></td>
<td><p><span data-ttu-id="0f3d3-148">Interface externa da Borda de A/V</span><span class="sxs-lookup"><span data-stu-id="0f3d3-148">A/V Edge external interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0f3d3-149">DNS Externo/SRV/443</span><span class="sxs-lookup"><span data-stu-id="0f3d3-149">External DNS/SRV/443</span></span></p></td>
<td><p><span data-ttu-id="0f3d3-150">_sip _sip._tls. contoso. com</span><span class="sxs-lookup"><span data-stu-id="0f3d3-150">_sip._tls.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="0f3d3-151">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0f3d3-151">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="0f3d3-152">Interface externa de borda de acesso.</span><span class="sxs-lookup"><span data-stu-id="0f3d3-152">Access Edge external interface.</span></span> <span data-ttu-id="0f3d3-153">Necessário para a configuração automática dos clientes do Lync 2013 e Lync 2010 para trabalhar externamente.</span><span class="sxs-lookup"><span data-stu-id="0f3d3-153">Required for automatic configuration of Lync 2013 and Lync 2010 clients to work externally.</span></span> <span data-ttu-id="0f3d3-154">Repita conforme for necessário para todos os domínios SIP com usuários Lync.</span><span class="sxs-lookup"><span data-stu-id="0f3d3-154">Repeat as necessary for all SIP domains with Lync enabled users.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0f3d3-155">DNS Externo/SRV/5061</span><span class="sxs-lookup"><span data-stu-id="0f3d3-155">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="0f3d3-156">_sipfederationtls _sipfederationtls._tcp. contoso. com</span><span class="sxs-lookup"><span data-stu-id="0f3d3-156">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="0f3d3-157">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0f3d3-157">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="0f3d3-158">Interface externa de borda de acesso SIP. Requerido para descoberta de DNS automática de parceiros federados, conhecida como "Domínio SIP Permitido" (chamada de federação avançada em versões anteriores). Repita conforme necessário para todos os domínios SIP com usuários Lync</span><span class="sxs-lookup"><span data-stu-id="0f3d3-158">SIP Access Edge external interface Required for automatic DNS discovery of federated partners known as “Allowed SIP Domain” (called enhanced federation in previous releases).Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0f3d3-159">DNS/A interno</span><span class="sxs-lookup"><span data-stu-id="0f3d3-159">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="0f3d3-160">lsedge.contoso.net</span><span class="sxs-lookup"><span data-stu-id="0f3d3-160">lsedge.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="0f3d3-161">172.25.33.10</span><span class="sxs-lookup"><span data-stu-id="0f3d3-161">172.25.33.10</span></span></p></td>
<td><p><span data-ttu-id="0f3d3-162">Interface interna da Borda Consolidada</span><span class="sxs-lookup"><span data-stu-id="0f3d3-162">Consolidated Edge internal interface</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]
> <span data-ttu-id="0f3d3-163">Os registros listados na tabela anterior são exibidos com uma extensão <EM>.net</EM> ou <EM>.com</EM> para destacar em qual zona precisam residir caso você não esteja usando split-brain DNS.</span><span class="sxs-lookup"><span data-stu-id="0f3d3-163">The records listed in the previous table are shown with either a <EM>.net</EM> extension or a <EM>.com</EM> extension to highlight which zone they need to reside in if you are not using split-brain DNS.</span></span> <span data-ttu-id="0f3d3-164">Se você estiver usando split-brain DNS, todos os registros devem estar na mesma zona, com a única distinção sendo se estão na versão interna ou externa.</span><span class="sxs-lookup"><span data-stu-id="0f3d3-164">If you are using split-brain DNS, all records would be in the same zone, with the only distinction being whether they are in the internal or external version.</span></span> <span data-ttu-id="0f3d3-165">Para obter detalhes, consulte "split-brain DNS" em <A href="lync-server-2013-determine-dns-requirements.md">determine DNS Requirements for Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="0f3d3-165">For details, see “Split-Brain DNS” in <A href="lync-server-2013-determine-dns-requirements.md">Determine DNS requirements for Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="records-required-for-federation"></a><span data-ttu-id="0f3d3-166">Registros exigidos para Federação</span><span class="sxs-lookup"><span data-stu-id="0f3d3-166">Records Required for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0f3d3-167">Local/tipo/porta</span><span class="sxs-lookup"><span data-stu-id="0f3d3-167">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="0f3d3-168">FQDN</span><span class="sxs-lookup"><span data-stu-id="0f3d3-168">FQDN</span></span></th>
<th><span data-ttu-id="0f3d3-169">Endereço IP/registro de host FQDN</span><span class="sxs-lookup"><span data-stu-id="0f3d3-169">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="0f3d3-170">Mapeia para/Comentários</span><span class="sxs-lookup"><span data-stu-id="0f3d3-170">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0f3d3-171">DNS Externo/SRV/5061</span><span class="sxs-lookup"><span data-stu-id="0f3d3-171">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="0f3d3-172">_sipfederationtls _sipfederationtls._tcp. contoso. com</span><span class="sxs-lookup"><span data-stu-id="0f3d3-172">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="0f3d3-173">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0f3d3-173">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="0f3d3-174">Interface externa da Borda de Acesso SIP Exgido para requisitos da descoberta de DNS de sua federação a outros potenciais parceiros da federação e é conhecido como “domínios SIP permitidos” (chamado Federação avançada em lançamentos prévios).Repetir conforme necessário para todos os domínios SIP com usuários Lync</span><span class="sxs-lookup"><span data-stu-id="0f3d3-174">SIP Access Edge external interface Required for automatic DNS discovery of your federation to other potential federation partners, and is known as “Allowed SIP Domains” (called enhanced federation in previous releases).Repeat as necessary for all SIP domains with Lync enabled users</span></span></p>



> [!IMPORTANT]
> <span data-ttu-id="0f3d3-175">Este registro SRV é exigido para mobilidade e a notificação push para liberação de espaço</span><span class="sxs-lookup"><span data-stu-id="0f3d3-175">This SRV record is required for mobility and the push notification clearing house</span></span>

</td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="0f3d3-176">Resumo DNS para Mensagens Extensíveis e Protocolo de Presença</span><span class="sxs-lookup"><span data-stu-id="0f3d3-176">DNS Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0f3d3-177">Local/tipo/porta</span><span class="sxs-lookup"><span data-stu-id="0f3d3-177">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="0f3d3-178">FQDN</span><span class="sxs-lookup"><span data-stu-id="0f3d3-178">FQDN</span></span></th>
<th><span data-ttu-id="0f3d3-179">Endereço IP/registro de host FQDN</span><span class="sxs-lookup"><span data-stu-id="0f3d3-179">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="0f3d3-180">Mapeia para/Comentários</span><span class="sxs-lookup"><span data-stu-id="0f3d3-180">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0f3d3-181">DNS Externo/SRV/5269</span><span class="sxs-lookup"><span data-stu-id="0f3d3-181">External DNS/SRV/5269</span></span></p></td>
<td><p><span data-ttu-id="0f3d3-182">_xmpp-server._tcp. contoso. com</span><span class="sxs-lookup"><span data-stu-id="0f3d3-182">_xmpp-server._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="0f3d3-183">xmpp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0f3d3-183">xmpp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="0f3d3-184">XMPP interface externa do proxy no serviço de borda de acesso ou no pool de borda. Repita conforme necessário para todos os domínios SIP internos com usuários habilitados para Lync onde contato com contatos do XMPP é permitido por meio da configuração da política de acesso externo por meio de uma política global, política de site onde o usuário está localizado ou política de usuário aplicada ao usuário habilitado para Lync.</span><span class="sxs-lookup"><span data-stu-id="0f3d3-184">XMPP proxy external interface on the Access Edge service or Edge pool.Repeat as necessary for all internal SIP domains with Lync enabled users where contact with XMPP contacts is allowed through the configuration of the External Access Policy through a global policy, site policy where the user is located, or user policy applied to the Lync-enabled user.</span></span> <span data-ttu-id="0f3d3-185">Um domínio XMPP permitido também deve ser configurado na política de Parceiros Federados XMPP.</span><span class="sxs-lookup"><span data-stu-id="0f3d3-185">An allowed XMPP domain must also be configured in the XMPP Federated Partners policy.</span></span> <span data-ttu-id="0f3d3-186">Veja os tópicos em <strong>Consulte também </strong> para mais detalhes</span><span class="sxs-lookup"><span data-stu-id="0f3d3-186">See topics in <strong>See Also</strong> for additional details</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0f3d3-187">DNS Externo/A</span><span class="sxs-lookup"><span data-stu-id="0f3d3-187">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="0f3d3-188">xmpp.contoso.com (por exemplo)</span><span class="sxs-lookup"><span data-stu-id="0f3d3-188">xmpp.contoso.com (for example)</span></span></p></td>
<td><p><span data-ttu-id="0f3d3-189">Endereço IP do serviço de borda de acesso no servidor de borda ou no pool de borda que hospeda o proxy do XMPP</span><span class="sxs-lookup"><span data-stu-id="0f3d3-189">IP address of Access Edge service on your Edge Server or Edge pool hosting XMPP proxy</span></span></p></td>
<td><p><span data-ttu-id="0f3d3-190">Aponta para o serviço de borda de acesso ou o pool de borda que hospeda o serviço de proxy XMPP.</span><span class="sxs-lookup"><span data-stu-id="0f3d3-190">Points to the Access Edge service or Edge pool that hosts the XMPP proxy service.</span></span> <span data-ttu-id="0f3d3-191">Tipicamente, o registro SRV que você criar apontará para este host (A ou AAAA) record</span><span class="sxs-lookup"><span data-stu-id="0f3d3-191">Typically, the SRV record that you create will point to this host (A or AAAA) record</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

