---
title: 'Lync Server 2013: requisitos de DNS para pool de front-ends'
description: 'Lync Server 2013: requisitos de DNS para pool de front-ends.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for Front End pool
ms:assetid: 02d2aa6b-9e01-437b-a2df-00590280150d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398082(v=OCS.15)
ms:contentKeyID: 48183249
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bfce90eccb8c8dff94d4122c96c4ca68ea9150f1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574327"
---
# <a name="dns-requirements-for-front-end-pool-in-lync-server-2013"></a><span data-ttu-id="ab7dd-103">Requisitos de DNS para pool de front-ends no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ab7dd-103">DNS requirements for Front End pool in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ab7dd-104">_**Última modificação do tópico:** 2012-11-07_</span><span class="sxs-lookup"><span data-stu-id="ab7dd-104">_**Topic Last Modified:** 2012-11-07_</span></span>

<span data-ttu-id="ab7dd-105">To successfully complete this procedure, you should be logged on to the server or domain minimally as a member of the Domain Admins group or a member of the DnsAdmins group.</span><span class="sxs-lookup"><span data-stu-id="ab7dd-105">To successfully complete this procedure, you should be logged on to the server or domain minimally as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

<span data-ttu-id="ab7dd-106">Você precisa configurar os registros de DNS (sistema de nomes de domínio) necessários antes de publicar sua topologia no construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="ab7dd-106">You need to configure the required Domain Name System (DNS) records prior to publishing your topology in Topology Builder.</span></span> <span data-ttu-id="ab7dd-107">Além disso, alguns dos FQDNs (nomes de domínio totalmente qualificados) usados na configuração de uma implantação do Lync Server 2013 são FQDNs lógicos e não físicos do servidor, portanto, a configuração DNS adicional é necessária antes da publicação.</span><span class="sxs-lookup"><span data-stu-id="ab7dd-107">Additionally, some of the fully qualified domain names (FQDNs) used in the configuration of a Lync Server 2013 deployment are logical and not physical server FQDNs, so additional DNS configuration is required prior to publishing.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="ab7dd-108">O Lync Server 2013 não oferece suporte a domínios com rótulo único.</span><span class="sxs-lookup"><span data-stu-id="ab7dd-108">Lync Server 2013 does not support single-labeled domains.</span></span> <span data-ttu-id="ab7dd-109">Por exemplo, uma floresta com um domínio raiz chamado <STRONG>contoso.local</STRONG> é suportado, mas um domínio raiz chamado <STRONG>local</STRONG> não é suportado.</span><span class="sxs-lookup"><span data-stu-id="ab7dd-109">For example, a forest with a root domain named <STRONG>contoso.local</STRONG> is supported, but a root domain named <STRONG>local</STRONG> is not supported.</span></span> <span data-ttu-id="ab7dd-110">Para obter detalhes, consulte o artigo 300684 da base de dados de conhecimento da Microsoft, "informações sobre como configurar o Windows para domínios com nomes DNS de rótulo único" em <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=300684"> https://go.microsoft.com/fwlink/p/?linkid=3052&amp ; kbid = 300684</A>.</span><span class="sxs-lookup"><span data-stu-id="ab7dd-110">For details, see Microsoft Knowledge Base article 300684, “Information about configuring Windows for domains with single-label DNS names,” at <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=300684">https://go.microsoft.com/fwlink/p/?linkid=3052&amp;kbid=300684</A>.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="ab7dd-111">O nome especificado deve ser idêntico ao nome do computador configurado no servidor.</span><span class="sxs-lookup"><span data-stu-id="ab7dd-111">The name you specify must be identical to the computer name configured on the server.</span></span> <span data-ttu-id="ab7dd-112">Por padrão, o nome de um computador que não é atribuído a um domínio é um nome curto, não um FQDN.</span><span class="sxs-lookup"><span data-stu-id="ab7dd-112">By default the computer name of a computer that is not joined to a domain is a short name, not an FQDN.</span></span> <span data-ttu-id="ab7dd-113">O Construtor de Topologia utiliza FQDNs, não nomes curtos.</span><span class="sxs-lookup"><span data-stu-id="ab7dd-113">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="ab7dd-114"><STRONG>Use apenas caracteres padrão</STRONG> (incluindo a – z, A – z, 0 – 9 e hifens) ao atribuir FQDNs de seus servidores que executam o Lync Server, servidores de borda e pools.</span><span class="sxs-lookup"><span data-stu-id="ab7dd-114"><STRONG>Use only standard characters</STRONG> (including A–Z, a–z, 0–9, and hyphens) when assigning FQDNs of your servers running Lync Server, Edge Servers, and pools.</span></span> <span data-ttu-id="ab7dd-115">Não use caracteres Unicode nem sublinhados.</span><span class="sxs-lookup"><span data-stu-id="ab7dd-115">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="ab7dd-116">Caracteres não padrão em um FQDN normalmente não são suportados por um DNS externo e por autoridades de certificação (ACs) públicas (quando o FQDN deve ser atribuído ao SN no certificado).</span><span class="sxs-lookup"><span data-stu-id="ab7dd-116">Nonstandard characters in an FQDN are often not supported by external DNS and public certification authorities (CAs) (when the FQDN must be assigned to the SN in the certificate).</span></span>



</div>

<span data-ttu-id="ab7dd-117">Antes de operar a topologia após ela ter sido implantada, verifique se os seguintes registros DNS e do Active Directory foram criados (conforme suas necessidades de recursos específicos ditam):</span><span class="sxs-lookup"><span data-stu-id="ab7dd-117">Prior to operating the topology after it has been deployed, ensure that the following Active Directory and DNS records are created (as your needs for specific features dictate):</span></span>

  - <span data-ttu-id="ab7dd-118">Cada função de servidor que existirá na topologia será publicada como um objeto do Active Directory (ingressar no computador no domínio realizará isso).</span><span class="sxs-lookup"><span data-stu-id="ab7dd-118">Each server role that will exist in the topology is published as an Active Directory object (joining the computer to the domain will accomplish this).</span></span>

  - <span data-ttu-id="ab7dd-119">Um Registro DNS A existe para cada servidor.</span><span class="sxs-lookup"><span data-stu-id="ab7dd-119">A DNS A Record exists for each server.</span></span>

  - <span data-ttu-id="ab7dd-120">Existe um registro SRV DNS para cada domínio SIP se você planeja usar o logon automático para clientes no formato de \_ sipinternaltls \_ TCP. \<SIP domain\> .</span><span class="sxs-lookup"><span data-stu-id="ab7dd-120">A DNS SRV Record exists for each SIP domain if you plan to use automatic logon for clients in the form of \_sipinternaltls\_tcp.\<SIP domain\>.</span></span> <span data-ttu-id="ab7dd-121">Este registro não é necessário se você utilizará configuração manual para clientes.</span><span class="sxs-lookup"><span data-stu-id="ab7dd-121">If you will use manual configuration for clients, this record is not necessary.</span></span>

  - <span data-ttu-id="ab7dd-122">Um Registro DNS A para cada URL simples configurada, da qual normalmente existem quatro: meet, dialin, lwa e scheduler.</span><span class="sxs-lookup"><span data-stu-id="ab7dd-122">A DNS A Record for each configured simple URL, of which there are typically four: meet, dialin, lwa, and scheduler.</span></span> <span data-ttu-id="ab7dd-123">Além disso, há a URL simples do administrador, que é uma URL especial para acessar o painel de controle do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ab7dd-123">Additionally, there is the admin simple URL which is a special URL for access to the Lync Server 2013 Control Panel.</span></span>

  - <span data-ttu-id="ab7dd-124">O servidor que executa o SQL Server deve ser associado ao domínio e alcançável pelo computador a partir do qual o construtor de topologias está publicando.</span><span class="sxs-lookup"><span data-stu-id="ab7dd-124">The server running SQL Server must be joined to the domain, and reachable by the computer that Topology Builder is publishing from.</span></span>

<span data-ttu-id="ab7dd-125">A tabela segue as arquiteturas de referência apresentadas na seção Planejamento.</span><span class="sxs-lookup"><span data-stu-id="ab7dd-125">The table follows the reference architectures presented in the Planning section.</span></span> <span data-ttu-id="ab7dd-126">Para obter detalhes, consulte [cenários para acesso de usuário externo no Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md) na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="ab7dd-126">For details, see [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md) in the Planning documentation.</span></span>

<div id="sectionSection0" class="section">

### <a name="dns-records-required-for-the-front-end-pool"></a><span data-ttu-id="ab7dd-127">Registros DNS necessários para o pool de front-ends</span><span class="sxs-lookup"><span data-stu-id="ab7dd-127">DNS Records Required for the Front End pool</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ab7dd-128">Local</span><span class="sxs-lookup"><span data-stu-id="ab7dd-128">Location</span></span></th>
<th><span data-ttu-id="ab7dd-129">Tipo</span><span class="sxs-lookup"><span data-stu-id="ab7dd-129">Type</span></span></th>
<th><span data-ttu-id="ab7dd-130">FQDN</span><span class="sxs-lookup"><span data-stu-id="ab7dd-130">FQDN</span></span></th>
<th><span data-ttu-id="ab7dd-131">Relacionado a/Comentários</span><span class="sxs-lookup"><span data-stu-id="ab7dd-131">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ab7dd-132">DNS Interno</span><span class="sxs-lookup"><span data-stu-id="ab7dd-132">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="ab7dd-133">A</span><span class="sxs-lookup"><span data-stu-id="ab7dd-133">A</span></span></p></td>
<td><p><span data-ttu-id="ab7dd-134">pool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="ab7dd-134">pool01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="ab7dd-135">Pool01 (balanceamento de carga DNS).</span><span class="sxs-lookup"><span data-stu-id="ab7dd-135">Pool01 (DNS load balancing).</span></span> <span data-ttu-id="ab7dd-136">Requer um registro A de DNS para o endereço IP de cada servidor de front-end dentro do pool, mapeamento para o FQDN do pool.</span><span class="sxs-lookup"><span data-stu-id="ab7dd-136">Requires a DNS A record for the IP address of each Front End Server within the pool, mapping to the pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab7dd-137">DNS Interno</span><span class="sxs-lookup"><span data-stu-id="ab7dd-137">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="ab7dd-138">A</span><span class="sxs-lookup"><span data-stu-id="ab7dd-138">A</span></span></p></td>
<td><p><span data-ttu-id="ab7dd-139">pool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="ab7dd-139">pool01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="ab7dd-140">Pool01 (IP virtual (VIP) de balanceamento de carga de hardware).</span><span class="sxs-lookup"><span data-stu-id="ab7dd-140">Pool01 (virtual IP (VIP) of hardware load balancer).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab7dd-141">DNS Interno</span><span class="sxs-lookup"><span data-stu-id="ab7dd-141">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="ab7dd-142">A</span><span class="sxs-lookup"><span data-stu-id="ab7dd-142">A</span></span></p></td>
<td><p><span data-ttu-id="ab7dd-143">fe01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="ab7dd-143">fe01.contoso.net</span></span></p>
<p><span data-ttu-id="ab7dd-144">fe02.contoso.net</span><span class="sxs-lookup"><span data-stu-id="ab7dd-144">fe02.contoso.net</span></span></p>
<p><span data-ttu-id="ab7dd-145">fe03.contoso.net</span><span class="sxs-lookup"><span data-stu-id="ab7dd-145">fe03.contoso.net</span></span></p>
<p><span data-ttu-id="ab7dd-146">…</span><span class="sxs-lookup"><span data-stu-id="ab7dd-146">…</span></span></p></td>
<td><p><span data-ttu-id="ab7dd-147">Servidor front-end do Pool01 (nó 1).</span><span class="sxs-lookup"><span data-stu-id="ab7dd-147">Pool01 Front End Server (NODE 1).</span></span></p>
<p><span data-ttu-id="ab7dd-148">Servidor front-end do Pool01 (nó 2).</span><span class="sxs-lookup"><span data-stu-id="ab7dd-148">Pool01 Front End Server (NODE 2).</span></span></p>
<p><span data-ttu-id="ab7dd-149">Servidor front-end do Pool01 (nó 3).</span><span class="sxs-lookup"><span data-stu-id="ab7dd-149">Pool01 Front End Server (NODE 3).</span></span></p>
<p><span data-ttu-id="ab7dd-150">…</span><span class="sxs-lookup"><span data-stu-id="ab7dd-150">…</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab7dd-151">DNS Interno</span><span class="sxs-lookup"><span data-stu-id="ab7dd-151">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="ab7dd-152">A</span><span class="sxs-lookup"><span data-stu-id="ab7dd-152">A</span></span></p></td>
<td><p><span data-ttu-id="ab7dd-153">fe02.contoso.net</span><span class="sxs-lookup"><span data-stu-id="ab7dd-153">fe02.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="ab7dd-154">Servidor front-end do Pool01 (nó 2).</span><span class="sxs-lookup"><span data-stu-id="ab7dd-154">Pool01 Front End Server (NODE 2).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab7dd-155">DNS Interno</span><span class="sxs-lookup"><span data-stu-id="ab7dd-155">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="ab7dd-156">A</span><span class="sxs-lookup"><span data-stu-id="ab7dd-156">A</span></span></p></td>
<td><p><span data-ttu-id="ab7dd-157">lsweb.contoso.net</span><span class="sxs-lookup"><span data-stu-id="ab7dd-157">lsweb.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="ab7dd-158">Pool01 (VIP) para tráfego de web de cliente para servidor.</span><span class="sxs-lookup"><span data-stu-id="ab7dd-158">Pool01 (VIP) for client-to-server web traffic.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab7dd-159">DNS Interno</span><span class="sxs-lookup"><span data-stu-id="ab7dd-159">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="ab7dd-160">A</span><span class="sxs-lookup"><span data-stu-id="ab7dd-160">A</span></span></p></td>
<td><p><span data-ttu-id="ab7dd-161">sqlbe.contoso.net</span><span class="sxs-lookup"><span data-stu-id="ab7dd-161">sqlbe.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="ab7dd-162">Servidor back-end do Pool01 executando o SQL Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="ab7dd-162">Pool01 Back End Server running SQL Server 2008 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab7dd-163">DNS Interno</span><span class="sxs-lookup"><span data-stu-id="ab7dd-163">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="ab7dd-164">A</span><span class="sxs-lookup"><span data-stu-id="ab7dd-164">A</span></span></p></td>
<td><p><span data-ttu-id="ab7dd-165">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ab7dd-165">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="ab7dd-166">Necessário para o Lync Phone Edition ou o logon automático de clientes sem registros SRV DNS e para correspondência de domínio estrito.</span><span class="sxs-lookup"><span data-stu-id="ab7dd-166">Required for Lync Phone Edition, or automatic logon of clients without DNS SRV records, and for strict domain matching.</span></span> <span data-ttu-id="ab7dd-167">Não é obrigatório em todos os casos.</span><span class="sxs-lookup"><span data-stu-id="ab7dd-167">Not required in all cases.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab7dd-168">DNS Interno</span><span class="sxs-lookup"><span data-stu-id="ab7dd-168">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="ab7dd-169">A</span><span class="sxs-lookup"><span data-stu-id="ab7dd-169">A</span></span></p></td>
<td><p><span data-ttu-id="ab7dd-170">sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="ab7dd-170">sip.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="ab7dd-171">Presume um segundo domínio SIP.</span><span class="sxs-lookup"><span data-stu-id="ab7dd-171">Assumes a second SIP domain.</span></span> <span data-ttu-id="ab7dd-172">Necessário para o Lync Phone Edition, o logon automático de clientes sem registros SRV DNS e para correspondência de domínio estrito.</span><span class="sxs-lookup"><span data-stu-id="ab7dd-172">Required for Lync Phone Edition, automatic logon of clients without DNS SRV records, and for strict domain matching.</span></span> <span data-ttu-id="ab7dd-173">Não é obrigatório em todos os casos.</span><span class="sxs-lookup"><span data-stu-id="ab7dd-173">Not required in all cases.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab7dd-174">DNS Interno</span><span class="sxs-lookup"><span data-stu-id="ab7dd-174">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="ab7dd-175">A</span><span class="sxs-lookup"><span data-stu-id="ab7dd-175">A</span></span></p></td>
<td><p><span data-ttu-id="ab7dd-176">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ab7dd-176">dialin.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="ab7dd-177">URL simples para conferência discada publicada internamente – o servidor front-end (ou diretor, se instalado) responde a consultas de URL simples.</span><span class="sxs-lookup"><span data-stu-id="ab7dd-177">Simple URL for dial-in conferencing published internally – Front End Server (or Director, if installed) responds to simple URL queries.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab7dd-178">DNS Interno</span><span class="sxs-lookup"><span data-stu-id="ab7dd-178">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="ab7dd-179">A</span><span class="sxs-lookup"><span data-stu-id="ab7dd-179">A</span></span></p></td>
<td><p><span data-ttu-id="ab7dd-180">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ab7dd-180">meet.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="ab7dd-181">URL simples para conferências publicadas internamente – o servidor front-end (ou diretor, se instalado) responde a consultas de URL simples.</span><span class="sxs-lookup"><span data-stu-id="ab7dd-181">Simple URL for conferences published internally – Front End Server (or Director, if installed) responds to simple URL queries.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab7dd-182">DNS Interno</span><span class="sxs-lookup"><span data-stu-id="ab7dd-182">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="ab7dd-183">A</span><span class="sxs-lookup"><span data-stu-id="ab7dd-183">A</span></span></p></td>
<td><p><span data-ttu-id="ab7dd-184">admin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ab7dd-184">admin.contoso.com</span></span></p>
<p><span data-ttu-id="ab7dd-185">Administração</span><span class="sxs-lookup"><span data-stu-id="ab7dd-185">admin</span></span></p></td>
<td><p><span data-ttu-id="ab7dd-186">Registro opcional, URL simples para o painel de controle do Lync Server 2013 publicado internamente-o servidor front-end (ou diretor, se instalado) responde a consultas de URL simples.</span><span class="sxs-lookup"><span data-stu-id="ab7dd-186">Optional record, simple URL for Lync Server 2013 Control Panel published internally - Front End Server (or Director, if installed) responds to simple URL queries.</span></span> <span data-ttu-id="ab7dd-187">Apenas o nome do host (não o de domínio) é exigido.</span><span class="sxs-lookup"><span data-stu-id="ab7dd-187">Host name only (no domain name) is recommended.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="ab7dd-188">VIP = Endereço IP virtual para balanceador de carga de hardware</span><span class="sxs-lookup"><span data-stu-id="ab7dd-188">VIP = Virtual IP address for hardware load balancer</span></span>



</div>

</div>

<div>

## <a name="dns-srv-records-for-the-front-end-pool"></a><span data-ttu-id="ab7dd-189">Registros SRV DNS para o pool de front-ends</span><span class="sxs-lookup"><span data-stu-id="ab7dd-189">DNS SRV Records for the Front End pool</span></span>


<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ab7dd-190">Local</span><span class="sxs-lookup"><span data-stu-id="ab7dd-190">Location</span></span></th>
<th><span data-ttu-id="ab7dd-191">Tipo</span><span class="sxs-lookup"><span data-stu-id="ab7dd-191">Type</span></span></th>
<th><span data-ttu-id="ab7dd-192">FQDN</span><span class="sxs-lookup"><span data-stu-id="ab7dd-192">FQDN</span></span></th>
<th><span data-ttu-id="ab7dd-193">FQDN Alvo</span><span class="sxs-lookup"><span data-stu-id="ab7dd-193">Target FQDN</span></span></th>
<th><span data-ttu-id="ab7dd-194">Porta</span><span class="sxs-lookup"><span data-stu-id="ab7dd-194">Port</span></span></th>
<th><span data-ttu-id="ab7dd-195">Relacionado a/Comentários</span><span class="sxs-lookup"><span data-stu-id="ab7dd-195">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ab7dd-196">DNS Interno</span><span class="sxs-lookup"><span data-stu-id="ab7dd-196">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="ab7dd-197">SRV</span><span class="sxs-lookup"><span data-stu-id="ab7dd-197">SRV</span></span></p></td>
<td><p><span data-ttu-id="ab7dd-198">_sipinternaltls _sipinternaltls._tcp. contoso. com</span><span class="sxs-lookup"><span data-stu-id="ab7dd-198">_sipinternaltls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="ab7dd-199">pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ab7dd-199">pool01.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="ab7dd-200">5061</span><span class="sxs-lookup"><span data-stu-id="ab7dd-200">5061</span></span></p></td>
<td><p><span data-ttu-id="ab7dd-201">Necessário para a configuração automática dos clientes do Lync 2013 para trabalhar internamente.</span><span class="sxs-lookup"><span data-stu-id="ab7dd-201">Required for automatic configuration of Lync 2013 clients to work internally.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab7dd-202">DNS Interno</span><span class="sxs-lookup"><span data-stu-id="ab7dd-202">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="ab7dd-203">SRV</span><span class="sxs-lookup"><span data-stu-id="ab7dd-203">SRV</span></span></p></td>
<td><p><span data-ttu-id="ab7dd-204">_sipinternaltls _sipinternaltls._tcp. fabrikam. com</span><span class="sxs-lookup"><span data-stu-id="ab7dd-204">_sipinternaltls._tcp.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="ab7dd-205">pool01.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="ab7dd-205">pool01.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="ab7dd-206">5061</span><span class="sxs-lookup"><span data-stu-id="ab7dd-206">5061</span></span></p></td>
<td><p><span data-ttu-id="ab7dd-207">Necessário para a configuração automática dos clientes do Lync 2013 para trabalhar internamente.</span><span class="sxs-lookup"><span data-stu-id="ab7dd-207">Required for automatic configuration of Lync 2013 clients to work internally.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab7dd-208">DNS Interno</span><span class="sxs-lookup"><span data-stu-id="ab7dd-208">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="ab7dd-209">SRV</span><span class="sxs-lookup"><span data-stu-id="ab7dd-209">SRV</span></span></p></td>
<td><p><span data-ttu-id="ab7dd-210">_ntp _ntp._udp. contoso. com</span><span class="sxs-lookup"><span data-stu-id="ab7dd-210">_ntp._udp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="ab7dd-211">dc01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ab7dd-211">dc01.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="ab7dd-212">123</span><span class="sxs-lookup"><span data-stu-id="ab7dd-212">123</span></span></p></td>
<td><p><span data-ttu-id="ab7dd-213">Origem do protocolo de tempo de rede (NTP) necessária para dispositivos que executam o Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="ab7dd-213">Network Time Protocol (NTP) source required for devices running Lync Phone Edition.</span></span> <span data-ttu-id="ab7dd-214">Isso deve indicar o controlador de domínio, internamente.</span><span class="sxs-lookup"><span data-stu-id="ab7dd-214">Internally, this should point to the domain controller.</span></span> <span data-ttu-id="ab7dd-215">Caso o controlador de domínio não esteja definido, tentará usar o servidor NTP time.windows.com</span><span class="sxs-lookup"><span data-stu-id="ab7dd-215">If the domain controller is not defined, it will try to use the NTP server time.windows.com.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

