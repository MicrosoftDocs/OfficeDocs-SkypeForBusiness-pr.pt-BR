---
title: Resumo de DNS - Única borda consolidada com endereços IP públicos
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
ms.openlocfilehash: db3578bc7b1668bf8cb2268ed079e558e1cf1761
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733541"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---single-consolidated-edge-with-public-ip-addresses-in-lync-server-2013"></a><span data-ttu-id="17525-102">Resumo de DNS - Única borda consolidada com endereços IP públicos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="17525-102">DNS summary - Single consolidated edge with public IP addresses in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="17525-103">_**Tópico da última modificação:** 2017-03-09_</span><span class="sxs-lookup"><span data-stu-id="17525-103">_**Topic Last Modified:** 2017-03-09_</span></span>

<span data-ttu-id="17525-104">Os requisitos de registro de DNS para acesso remoto ao Lync Server 2013 são bem simples em comparação com aqueles para certificados e portas.</span><span class="sxs-lookup"><span data-stu-id="17525-104">DNS record requirements for remote access to Lync Server 2013 are fairly straightforward compared to those for certificates and ports.</span></span> <span data-ttu-id="17525-105">Além disso, muitos registros são opcionais, dependendo de como você configura os clientes que executam o Lync 2013 e se você habilita a Federação.</span><span class="sxs-lookup"><span data-stu-id="17525-105">Also, many records are optional, depending on how you configure clients running Lync 2013 and whether you enable federation.</span></span>

<span data-ttu-id="17525-106">Para obter detalhes sobre os requisitos de DNS do Lync 2013, consulte [determinar requisitos de DNS para o Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="17525-106">For details about Lync 2013 DNS requirements, see [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="17525-107">Para obter detalhes sobre a configuração automática de clientes que executam o Lync 2013 se a divisão do DNS não estiver configurada, consulte "configuração automática sem DNS Split-Brain" em [determinar requisitos de DNS para o Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="17525-107">For details about automatic configuration of clients running Lync 2013 if split-brain DNS is not configured, see “Automatic Configuration without Split-Brain DNS” in [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="17525-108">A tabela a seguir contém um resumo dos registros DNS necessários para dar suporte à topologia de borda consolidada única mostrada na figura única de topologia de borda consolidada.</span><span class="sxs-lookup"><span data-stu-id="17525-108">The following table contains a summary of the DNS records that are required to support the single consolidated edge topology shown in the Single Consolidated Edge Topology figure.</span></span> <span data-ttu-id="17525-109">Observe que determinados registros DNS são necessários somente para a configuração automática dos clientes Lync 2013 e Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="17525-109">Note that certain DNS records are required only for automatic configuration of Lync 2013 and Lync 2010 clients.</span></span> <span data-ttu-id="17525-110">Se você pretende usar objetos de política de grupo (GPOs) para configurar os clientes do Lync, os registros de configuração automática associados não são necessários.</span><span class="sxs-lookup"><span data-stu-id="17525-110">If you plan to use group policy objects (GPOs) to configure Lync clients, the associated automatic configuration records are not necessary.</span></span>

<div>

## <a name="important-edge-server-network-adapter-requirements"></a><span data-ttu-id="17525-111">IMPORTANTE: requisitos do adaptador de rede do Edge Server</span><span class="sxs-lookup"><span data-stu-id="17525-111">IMPORTANT: Edge Server Network Adapter Requirements</span></span>

<span data-ttu-id="17525-112">Para evitar problemas de roteamento, verifique se há pelo menos dois adaptadores de rede em seus servidores de borda e se o gateway padrão está definido somente no adaptador de rede associado à interface externa.</span><span class="sxs-lookup"><span data-stu-id="17525-112">To avoid routing issues, verify that there are at least two network adapters in your Edge Servers and that the default gateway is set only on the network adapter associated with the external interface.</span></span> <span data-ttu-id="17525-113">Por exemplo, conforme mostrado na topologia de borda única consolidada com endereços IP públicos configurados em [uma única aresta consolidada com endereços IP públicos no Lync Server 2013](lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md), o gateway padrão apontaria para o roteador externo no seu perímetro da Internet ou firewall que pode fornecer um endereço IP público.</span><span class="sxs-lookup"><span data-stu-id="17525-113">For example, as shown in the Single Consolidated Edge Topology with Public IP Addresses figure in [Single consolidated edge with public IP addresses in Lync Server 2013](lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md), the default gateway would point to the external router at your Internet perimeter or firewall that can provide a public IP addresses.</span></span> <span data-ttu-id="17525-114">A relação de rede para interfaces do servidor de borda é uma relação de rota em vez de uma relação NAT.</span><span class="sxs-lookup"><span data-stu-id="17525-114">The network relationship for Edge Server interfaces is a route relationship instead of a NAT relationship.</span></span>

<span data-ttu-id="17525-115">Você pode configurar dois adaptadores de rede em seu servidor de borda da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="17525-115">You can configure two network adapters in your Edge Server as follows:</span></span>

  - <span data-ttu-id="17525-116">**Adaptador de rede 1 (interface interna)**</span><span class="sxs-lookup"><span data-stu-id="17525-116">**Network adapter 1 (Internal Interface)**</span></span>
    
    <span data-ttu-id="17525-117">Interface interna com 172.25.33.10 atribuído.</span><span class="sxs-lookup"><span data-stu-id="17525-117">Internal interface with 172.25.33.10 assigned.</span></span>
    
    <span data-ttu-id="17525-118">Não há nenhum gateway padrão definido.</span><span class="sxs-lookup"><span data-stu-id="17525-118">No default gateway is defined.</span></span>
    
    <span data-ttu-id="17525-119">Verifique se há uma rota da rede que contém a interface interna de borda para qualquer rede que contenha servidores que estejam executando o Lync Server 2013 ou o Lync Server 2013 clientes (por exemplo, de 172.25.33.0 para 192.168.10.0).</span><span class="sxs-lookup"><span data-stu-id="17525-119">Ensure that there is a route from the network containing the Edge internal interface to any networks that contain servers running Lync Server 2013 or Lync Server 2013 clients (for example, from 172.25.33.0 to 192.168.10.0).</span></span>

  - <span data-ttu-id="17525-120">**Adaptador de rede 2 (interface externa)**</span><span class="sxs-lookup"><span data-stu-id="17525-120">**Network adapter 2 (External Interface)**</span></span>
    
    <span data-ttu-id="17525-121">Três endereços IP públicos são atribuídos a esse adaptador de rede, por exemplo 131.107.155.10 para Edge do Access, 131.107.155.20 para Edge de webconferência, 131.107.155.30 para Edge do AV.</span><span class="sxs-lookup"><span data-stu-id="17525-121">Three public IP addresses are assigned to this network adapter, for example 131.107.155.10 for Access Edge, 131.107.155.20 for Web Conferencing Edge, 131.107.155.30 for AV Edge.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="17525-122">É possível, mas não recomendado, usar um único endereço IP para todas as três interfaces de serviço de borda.</span><span class="sxs-lookup"><span data-stu-id="17525-122">It is possible, though not recommended, to use a single IP address for all three Edge service interfaces.</span></span> <span data-ttu-id="17525-123">Embora isso salve endereços IP, ele exige números de porta diferentes para cada serviço.</span><span class="sxs-lookup"><span data-stu-id="17525-123">Though this does save IP addresses, it requires different port numbers for each service.</span></span> <span data-ttu-id="17525-124">O número da porta padrão é 443/TCP, o que garante que os firewalls remotos permitam que o tráfego seja permitido.</span><span class="sxs-lookup"><span data-stu-id="17525-124">The default port number is 443/TCP, which ensures that most remote firewalls will allow the traffic.</span></span> <span data-ttu-id="17525-125">Alterar os valores de porta para (por exemplo) 5061/TCP para a borda de acesso, 444/TCP para a Web de Webconferência e 443/TCP para a borda do AV pode causar problemas para usuários remotos nos quais um firewall para os quais estejam atrás não permite o tráfego sobre 5061/TCP e 444/TCP.</span><span class="sxs-lookup"><span data-stu-id="17525-125">Changing the port values to (for example) 5061/TCP for the Access Edge, 444/TCP for the Web Conferencing Edge and 443/TCP for the AV Edge might cause problems for remote users where a firewall that they are behind does not allow the traffic over 5061/TCP and 444/TCP.</span></span> <span data-ttu-id="17525-126">Além disso, três endereços IP distintos facilitam a solução de problemas devido à capacidade de filtrar por endereço IP.</span><span class="sxs-lookup"><span data-stu-id="17525-126">Additionally, three distinct IP addresses makes troubleshooting easier due to being able to filter on IP address.</span></span>

    
    </div>
    
    <span data-ttu-id="17525-127">O endereço IP público da borda do Access é primário com o gateway padrão definido para o roteador público (131.107.155.1).</span><span class="sxs-lookup"><span data-stu-id="17525-127">The Access Edge public IP address is primary with default gateway set to the public router (131.107.155.1).</span></span>
    
    <span data-ttu-id="17525-128">Os endereços IP de borda da Web e de borda A/V são endereços IP adicionais na seção **avançado** das propriedades de **protocolo de Internet versão 4 (TCP/IPv4)** e **protocolo IP versão 6 (TCP/IPv6)** das **Propriedades de conexão de área local** no Windows Server.</span><span class="sxs-lookup"><span data-stu-id="17525-128">Web conferencing and A/V Edge public IP addresses are additional IP addresses in the **Advanced** section of the properties of **Internet Protocol Version 4 (TCP/IPv4)** and **Internet Protocol Version 6 (TCP/IPv6)** of the **Local Area Connection Properties** in Windows Server.</span></span>

<div>


> [!TIP]
> <span data-ttu-id="17525-129">A configuração do servidor de borda com dois adaptadores de rede é uma das duas opções.</span><span class="sxs-lookup"><span data-stu-id="17525-129">Configuring the Edge Server with two network adapters is one of two options.</span></span> <span data-ttu-id="17525-130">A outra opção é usar um adaptador de rede para o lado interno e três adaptadores de rede para o lado externo do servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="17525-130">The other option is to use one network adapter for the internal side and three network adapters for the external side of the Edge Server.</span></span> <span data-ttu-id="17525-131">O principal benefício dessa opção é um adaptador de rede distinto por serviço de servidor de borda e uma coleta de dados possivelmente mais concisa quando a solução de problemas é necessária</span><span class="sxs-lookup"><span data-stu-id="17525-131">The main benefit of this option is a distinct network adapter per Edge Server service, and potentially more concise data collection when troubleshooting is necessary</span></span>



</div>

### <a name="dns-records-required-for-single-consolidated-edge-with-public-ip-addresses-example"></a><span data-ttu-id="17525-132">Registros DNS necessários para a aresta consolidada única com endereços IP públicos (exemplo)</span><span class="sxs-lookup"><span data-stu-id="17525-132">DNS Records Required for Single Consolidated Edge with Public IP Addresses (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="17525-133">Local/tipo/porta</span><span class="sxs-lookup"><span data-stu-id="17525-133">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="17525-134">Registro FQDN/DNS</span><span class="sxs-lookup"><span data-stu-id="17525-134">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="17525-135">Endereço IP/FQDN</span><span class="sxs-lookup"><span data-stu-id="17525-135">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="17525-136">Mapas para/comentários</span><span class="sxs-lookup"><span data-stu-id="17525-136">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="17525-137">DNS/A externo</span><span class="sxs-lookup"><span data-stu-id="17525-137">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="17525-138">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="17525-138">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="17525-139">131.107.155.10</span><span class="sxs-lookup"><span data-stu-id="17525-139">131.107.155.10</span></span></p></td>
<td><p><span data-ttu-id="17525-140">Interface externa da borda do Access (contoso) Repita conforme necessário para todos os domínios SIP com usuários habilitados para Lync</span><span class="sxs-lookup"><span data-stu-id="17525-140">Access Edge external interface (Contoso) Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="17525-141">DNS/A externo</span><span class="sxs-lookup"><span data-stu-id="17525-141">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="17525-142">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="17525-142">webcon.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="17525-143">131.107.155.20</span><span class="sxs-lookup"><span data-stu-id="17525-143">131.107.155.20</span></span></p></td>
<td><p><span data-ttu-id="17525-144">Interface externa da borda de Webconferência</span><span class="sxs-lookup"><span data-stu-id="17525-144">Web Conferencing Edge external interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="17525-145">DNS/A externo</span><span class="sxs-lookup"><span data-stu-id="17525-145">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="17525-146">av.contoso.com</span><span class="sxs-lookup"><span data-stu-id="17525-146">av.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="17525-147">131.107.155.30</span><span class="sxs-lookup"><span data-stu-id="17525-147">131.107.155.30</span></span></p></td>
<td><p><span data-ttu-id="17525-148">Interface externa de borda A/V</span><span class="sxs-lookup"><span data-stu-id="17525-148">A/V Edge external interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="17525-149">DNS/SRV/443 externos</span><span class="sxs-lookup"><span data-stu-id="17525-149">External DNS/SRV/443</span></span></p></td>
<td><p><span data-ttu-id="17525-150">_sip._tls.contoso.com</span><span class="sxs-lookup"><span data-stu-id="17525-150">_sip._tls.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="17525-151">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="17525-151">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="17525-152">Interface externa do Access Edge.</span><span class="sxs-lookup"><span data-stu-id="17525-152">Access Edge external interface.</span></span> <span data-ttu-id="17525-153">Obrigatório para configurar automaticamente o Lync 2013 e os clientes do Lync 2010 para trabalhar externamente.</span><span class="sxs-lookup"><span data-stu-id="17525-153">Required for automatic configuration of Lync 2013 and Lync 2010 clients to work externally.</span></span> <span data-ttu-id="17525-154">Repita conforme necessário para todos os domínios SIP com usuários habilitados para o Lync.</span><span class="sxs-lookup"><span data-stu-id="17525-154">Repeat as necessary for all SIP domains with Lync enabled users.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="17525-155">DNS/SRV/5061 externo</span><span class="sxs-lookup"><span data-stu-id="17525-155">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="17525-156">_sipfederationtls._tcp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="17525-156">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="17525-157">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="17525-157">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="17525-158">Borda de acesso SIP interface externa necessária para a descoberta automática de DNS de parceiros federados conhecidos como "domínio SIP permitido" (chamada de Federação aprimorada nas versões anteriores). Repita conforme necessário para todos os domínios SIP com usuários habilitados para Lync</span><span class="sxs-lookup"><span data-stu-id="17525-158">SIP Access Edge external interface Required for automatic DNS discovery of federated partners known as “Allowed SIP Domain” (called enhanced federation in previous releases).Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="17525-159">DNS interno/A</span><span class="sxs-lookup"><span data-stu-id="17525-159">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="17525-160">lsedge.contoso.net</span><span class="sxs-lookup"><span data-stu-id="17525-160">lsedge.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="17525-161">172.25.33.10</span><span class="sxs-lookup"><span data-stu-id="17525-161">172.25.33.10</span></span></p></td>
<td><p><span data-ttu-id="17525-162">Interface interna de borda consolidada</span><span class="sxs-lookup"><span data-stu-id="17525-162">Consolidated Edge internal interface</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]
> <span data-ttu-id="17525-163">Os registros listados na tabela anterior são mostrados com uma extensão <EM>.net</EM> ou uma extensão <EM>. com</EM> para realçar em qual zona eles precisam residir, se você não estiver usando o DNS Split-Brain.</span><span class="sxs-lookup"><span data-stu-id="17525-163">The records listed in the previous table are shown with either a <EM>.net</EM> extension or a <EM>.com</EM> extension to highlight which zone they need to reside in if you are not using split-brain DNS.</span></span> <span data-ttu-id="17525-164">Se você estiver usando DNS Split-Brain, todos os registros ficarão na mesma zona, com a única distinção se eles estiverem na versão interna ou externa.</span><span class="sxs-lookup"><span data-stu-id="17525-164">If you are using split-brain DNS, all records would be in the same zone, with the only distinction being whether they are in the internal or external version.</span></span> <span data-ttu-id="17525-165">Para obter detalhes, consulte "split-brain DNS" em <A href="lync-server-2013-determine-dns-requirements.md">determinar requisitos de DNS para o Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="17525-165">For details, see “Split-Brain DNS” in <A href="lync-server-2013-determine-dns-requirements.md">Determine DNS requirements for Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="records-required-for-federation"></a><span data-ttu-id="17525-166">Registros necessários para Federação</span><span class="sxs-lookup"><span data-stu-id="17525-166">Records Required for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="17525-167">Local/tipo/porta</span><span class="sxs-lookup"><span data-stu-id="17525-167">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="17525-168">FQDN</span><span class="sxs-lookup"><span data-stu-id="17525-168">FQDN</span></span></th>
<th><span data-ttu-id="17525-169">Endereço IP/registro de host FQDN</span><span class="sxs-lookup"><span data-stu-id="17525-169">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="17525-170">Mapas para/comentários</span><span class="sxs-lookup"><span data-stu-id="17525-170">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="17525-171">DNS/SRV/5061 externo</span><span class="sxs-lookup"><span data-stu-id="17525-171">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="17525-172">_sipfederationtls._tcp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="17525-172">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="17525-173">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="17525-173">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="17525-174">Borda de acesso SIP interface externa necessária para a descoberta automática de DNS da sua Federação para outros parceiros de Federação potenciais e é conhecida como "domínios SIP permitidos" (chamado de Federação aprimorada nas versões anteriores). Repita conforme necessário para todos os domínios SIP com usuários habilitados para Lync</span><span class="sxs-lookup"><span data-stu-id="17525-174">SIP Access Edge external interface Required for automatic DNS discovery of your federation to other potential federation partners, and is known as “Allowed SIP Domains” (called enhanced federation in previous releases).Repeat as necessary for all SIP domains with Lync enabled users</span></span></p>



> [!IMPORTANT]
> <span data-ttu-id="17525-175">Esse registro SRV é necessário para a mobilidade e a equipe de compensação da notificação por push</span><span class="sxs-lookup"><span data-stu-id="17525-175">This SRV record is required for mobility and the push notification clearing house</span></span>

</td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="17525-176">Resumo de DNS para o protocolo de mensagens extensíveis e de presença</span><span class="sxs-lookup"><span data-stu-id="17525-176">DNS Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="17525-177">Local/tipo/porta</span><span class="sxs-lookup"><span data-stu-id="17525-177">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="17525-178">FQDN</span><span class="sxs-lookup"><span data-stu-id="17525-178">FQDN</span></span></th>
<th><span data-ttu-id="17525-179">Endereço IP/registro de host FQDN</span><span class="sxs-lookup"><span data-stu-id="17525-179">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="17525-180">Mapas para/comentários</span><span class="sxs-lookup"><span data-stu-id="17525-180">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="17525-181">DNS/SRV/5269 externo</span><span class="sxs-lookup"><span data-stu-id="17525-181">External DNS/SRV/5269</span></span></p></td>
<td><p><span data-ttu-id="17525-182">_xmpp-server._tcp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="17525-182">_xmpp-server._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="17525-183">xmpp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="17525-183">xmpp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="17525-184">Interface externa de proxy XMPP no serviço de borda do Access ou no pool de bordas. Repita conforme necessário para todos os domínios SIP internos com usuários habilitados para Lync nos quais o contato com contatos do XMPP é permitido pela configuração da política de acesso externo por meio de uma política global, política de site onde o usuário está localizado ou política de usuário aplicada ao Usuário compatível com o Lync.</span><span class="sxs-lookup"><span data-stu-id="17525-184">XMPP proxy external interface on the Access Edge service or Edge pool.Repeat as necessary for all internal SIP domains with Lync enabled users where contact with XMPP contacts is allowed through the configuration of the External Access Policy through a global policy, site policy where the user is located, or user policy applied to the Lync-enabled user.</span></span> <span data-ttu-id="17525-185">Um domínio XMPP permitido também deve ser configurado na política de parceiros federados do XMPP.</span><span class="sxs-lookup"><span data-stu-id="17525-185">An allowed XMPP domain must also be configured in the XMPP Federated Partners policy.</span></span> <span data-ttu-id="17525-186">Consulte os tópicos em <strong>Consulte também</strong> para obter detalhes adicionais</span><span class="sxs-lookup"><span data-stu-id="17525-186">See topics in <strong>See Also</strong> for additional details</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="17525-187">DNS/A externo</span><span class="sxs-lookup"><span data-stu-id="17525-187">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="17525-188">xmpp.contoso.com (por exemplo)</span><span class="sxs-lookup"><span data-stu-id="17525-188">xmpp.contoso.com (for example)</span></span></p></td>
<td><p><span data-ttu-id="17525-189">Endereço IP do serviço de borda de acesso em seu servidor de borda ou em um pool de bordas que hospeda o proxy XMPP</span><span class="sxs-lookup"><span data-stu-id="17525-189">IP address of Access Edge service on your Edge Server or Edge pool hosting XMPP proxy</span></span></p></td>
<td><p><span data-ttu-id="17525-190">Aponta para o serviço de borda de acesso ou o pool de bordas que hospeda o serviço de proxy XMPP.</span><span class="sxs-lookup"><span data-stu-id="17525-190">Points to the Access Edge service or Edge pool that hosts the XMPP proxy service.</span></span> <span data-ttu-id="17525-191">Geralmente, o registro SRV que você cria aponta para esse registro de host (A ou AAAA)</span><span class="sxs-lookup"><span data-stu-id="17525-191">Typically, the SRV record that you create will point to this host (A or AAAA) record</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

