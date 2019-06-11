---
title: 'Lync Server 2013: Requisitos de certificado para servidores internos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Certificate requirements for internal servers
ms:assetid: 0444cdbd-538c-43b1-b9a1-9d7d6cf818d6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398094(v=OCS.15)
ms:contentKeyID: 48183270
ms.date: 02/17/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a4a3f1eb54321c6cac7548d282bd3cea31c3f24a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836667"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-requirements-for-internal-servers-in-lync-server-2013"></a><span data-ttu-id="20887-102">Requisitos de certificado para servidores internos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="20887-102">Certificate requirements for internal servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="20887-103">_**Tópico da última modificação:** 2017-02-17_</span><span class="sxs-lookup"><span data-stu-id="20887-103">_**Topic Last Modified:** 2017-02-17_</span></span>

<span data-ttu-id="20887-104">Os servidores internos que executam o Lync Server e que exigem certificados incluem o servidor Standard Edition, o servidor front-end do Enterprise Edition, o servidor de mediação e o diretor.</span><span class="sxs-lookup"><span data-stu-id="20887-104">Internal servers that are running Lync Server and that require certificates include Standard Edition server, Enterprise Edition Front End Server, Mediation Server, and Director.</span></span> <span data-ttu-id="20887-105">A tabela a seguir mostra os requisitos de certificado para esses servidores.</span><span class="sxs-lookup"><span data-stu-id="20887-105">The following table shows the certificate requirements for these servers.</span></span> <span data-ttu-id="20887-106">Você pode usar o assistente de certificado do Lync Server para solicitar esses certificados.</span><span class="sxs-lookup"><span data-stu-id="20887-106">You can use the Lync Server certificate wizard to request these certificates.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="20887-107">Os certificados curinga são compatíveis com os nomes alternativos de assunto associados às URLs simples no pool de front-end, servidor front-end ou diretor.</span><span class="sxs-lookup"><span data-stu-id="20887-107">Wildcard certificates are supported for the subject alternative names associated with the simple URLs on the Front End pool, Front End Server, or Director.</span></span> <span data-ttu-id="20887-108">Para obter detalhes sobre o suporte a certificados curinga, consulte <A href="lync-server-2013-wildcard-certificate-support.md">suporte a certificados curinga no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="20887-108">For details about wildcard certificate support, see <A href="lync-server-2013-wildcard-certificate-support.md">Wildcard certificate support in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="20887-109">Embora uma CA (autoridade de certificação) corporativa interna seja recomendada para servidores internos, você também pode usar uma CA pública.</span><span class="sxs-lookup"><span data-stu-id="20887-109">Although an internal enterprise certification authority (CA) is recommended for internal servers, you can also use a public CA.</span></span> <span data-ttu-id="20887-110">Para obter uma lista de CAs públicas que fornecem certificados compatíveis com requisitos específicos para certificados de comunicação unificada (UC) e que se associaram à Microsoft para garantir que elas funcionem com o assistente de certificado do Lync Server, consulte artigo conhecimento da Microsoft Base 929395, "parceiros do certificado de comunicação unificada para Exchange Server e para Communications Server" em [https://go.microsoft.com/fwlink/p/?linkId=202834](https://go.microsoft.com/fwlink/p/?linkid=202834).</span><span class="sxs-lookup"><span data-stu-id="20887-110">For a list of public CAs that provide certificates that comply with specific requirements for unified communications (UC) certificates and have partnered with Microsoft to ensure they work with the Lync Server Certificate Wizard, see article Microsoft Knowledge Base 929395, "Unified Communications Certificate Partners for Exchange Server and for Communications Server," at [https://go.microsoft.com/fwlink/p/?linkId=202834](https://go.microsoft.com/fwlink/p/?linkid=202834).</span></span>

<span data-ttu-id="20887-111">A comunicação com outros aplicativos e servidores, como o Exchange 2013, requer um certificado que seja compatível com outros aplicativos e produtos.</span><span class="sxs-lookup"><span data-stu-id="20887-111">Communication with other applications and servers, such as Exchange 2013, requires a certificate that is supported by the other applications and products.</span></span> <span data-ttu-id="20887-112">Para o lançamento do 2013, Lync Server 2013 e outros produtos do Microsoft Server, incluindo Exchange 2013 e SharePoint Server, suporte ao protocolo de autorização aberta (OAuth) para autenticação e autorização do servidor para servidor.</span><span class="sxs-lookup"><span data-stu-id="20887-112">For the 2013 release, Lync Server 2013 and other Microsoft server products, including Exchange 2013 and SharePoint Server, support the Open Authorization (OAuth) protocol for server-to-server authentication and authorization.</span></span> <span data-ttu-id="20887-113">Para obter detalhes, consulte Gerenciando a [autenticação de servidor para servidor (OAuth) e aplicativos de parceiros no Lync server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) na documentação de implantação ou na documentação de operações.</span><span class="sxs-lookup"><span data-stu-id="20887-113">For details, see [Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) in the Deployment documentation or the Operations documentation.</span></span>

<span data-ttu-id="20887-114">Para conexões de clientes que executam o sistema operacional Windows 7, sistema operacional Windows Server 2008, sistema operacional Windows Server 2008 R2, sistema operacional Windows Vista e Microsoft Lync Phone Edition, Lync Server 2013 inclui suporte para (mas não Requires) certificados assinados usando a função hash criptográfico SHA-256.</span><span class="sxs-lookup"><span data-stu-id="20887-114">For connections from clients running Windows 7 operating system, Windows Server 2008 operating system, Windows Server 2008 R2 operating system, Windows Vista operating system, and Microsoft Lync Phone Edition, Lync Server 2013 includes support for (but does not require) certificates signed using the SHA-256 cryptographic hash function.</span></span> <span data-ttu-id="20887-115">Para dar suporte ao acesso externo usando SHA-256, o certificado externo é emitido por uma autoridade de certificação pública que usa SHA-256.</span><span class="sxs-lookup"><span data-stu-id="20887-115">To support external access using SHA-256, the external certificate is issued by a public CA using SHA-256.</span></span>

<span data-ttu-id="20887-116">As tabelas a seguir mostram os requisitos de certificado por função de servidor para os pools front-end e os servidores Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="20887-116">The following tables show certificate requirements by server role for Front End pools and Standard Edition servers.</span></span> <span data-ttu-id="20887-117">Todos esses são certificados de servidor Web padrão, chave privada, não-exportável.</span><span class="sxs-lookup"><span data-stu-id="20887-117">All these are standard web server certificates, private key, non-exportable.</span></span>

<span data-ttu-id="20887-118">Observe que o uso avançado de chave do servidor (EKU) é automaticamente configurado quando você usa o assistente de certificado para solicitar certificados.</span><span class="sxs-lookup"><span data-stu-id="20887-118">Note that server enhanced key usage (EKU) is automatically configured when you use the certificate wizard to request certificates.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="20887-119">Cada nome amigável do certificado deve ser exclusivo na loja do computador.</span><span class="sxs-lookup"><span data-stu-id="20887-119">Each certificate Friendly Name must be unique in the computer store.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="20887-120">Se você tiver configurado o sipinternal.contoso.com ou o sipexternal.contoso.com no seu DNS, será necessário adicioná-los ao nome alternativo do requerente do certificado.</span><span class="sxs-lookup"><span data-stu-id="20887-120">If you have configured sipinternal.contoso.com or sipexternal.contoso.com in your DNS, you will need to add them in the certificate’s Subject Alternative Name.</span></span>



</div>

### <a name="certificates-for-standard-edition-server"></a><span data-ttu-id="20887-121">Certificados para o servidor Standard Edition</span><span class="sxs-lookup"><span data-stu-id="20887-121">Certificates for Standard Edition Server</span></span>

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
<th><span data-ttu-id="20887-122">Certificado</span><span class="sxs-lookup"><span data-stu-id="20887-122">Certificate</span></span></th>
<th><span data-ttu-id="20887-123">Nome do assunto/nome comum</span><span class="sxs-lookup"><span data-stu-id="20887-123">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="20887-124">Nome alternativo de entidade</span><span class="sxs-lookup"><span data-stu-id="20887-124">Subject alternative name</span></span></th>
<th><span data-ttu-id="20887-125">Exemplo</span><span class="sxs-lookup"><span data-stu-id="20887-125">Example</span></span></th>
<th><span data-ttu-id="20887-126">Comentários</span><span class="sxs-lookup"><span data-stu-id="20887-126">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="20887-127">Padrão</span><span class="sxs-lookup"><span data-stu-id="20887-127">Default</span></span></p></td>
<td><p><span data-ttu-id="20887-128">FQDN (nome de domínio totalmente qualificado) do pool</span><span class="sxs-lookup"><span data-stu-id="20887-128">Fully qualified domain name (FQDN) of the pool</span></span></p></td>
<td><p><span data-ttu-id="20887-129">FQDN do pool e do FQDN do servidor</span><span class="sxs-lookup"><span data-stu-id="20887-129">FQDN of the pool and the FQDN of the server</span></span></p>
<p><span data-ttu-id="20887-130">Se você tiver vários domínios SIP e tiver habilitado a configuração automática do cliente, o assistente de certificados detectará e adicionará os FQDNs de cada domínio SIP aceito.</span><span class="sxs-lookup"><span data-stu-id="20887-130">If you have multiple SIP domains and have enabled automatic client configuration, the certificate wizard detects and adds each supported SIP domain FQDNs.</span></span></p>
<p><span data-ttu-id="20887-131">Se esse pool for o servidor de logon automático para clientes, e a combinação estrita do Sistema de Nome de Domínio (DNS) for exigida na política do grupo, também serão necessárias entradas para o sip.sipdomain (para cada domínio de SIP que você tiver).</span><span class="sxs-lookup"><span data-stu-id="20887-131">If this pool is the auto-logon server for clients and strict Domain Name System (DNS) matching is required in group policy, you also need entries for sip.sipdomain (for each SIP domain you have).</span></span></p></td>
<td><p><span data-ttu-id="20887-132">SN=se01.contoso.com; SAN=se01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="20887-132">SN=se01.contoso.com; SAN=se01.contoso.com</span></span></p>
<p><span data-ttu-id="20887-133">Se esse pool for o servidor de logon automático para clientes, e se a combinação estrita de DNS for exigida na política do grupo, também serão necessários: SAN=sip.contoso.com; SAN=sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="20887-133">If this pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need SAN=sip.contoso.com; SAN=sip.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="20887-134">No servidor Standard Edition, o FQDN do servidor é o mesmo que o FQDN do pool.</span><span class="sxs-lookup"><span data-stu-id="20887-134">On Standard Edition server, the server FQDN is the same as the pool FQDN.</span></span></p>
<p><span data-ttu-id="20887-135">O assistente detecta quaisquer domínios SIP especificados durante a instalação e os adiciona automaticamente ao nome alternativo para a entidade.</span><span class="sxs-lookup"><span data-stu-id="20887-135">The wizard detects any SIP domains you specified during setup and automatically adds them to the subject alternative name.</span></span></p>
<p><span data-ttu-id="20887-136">Você também utiliza este certificado para Autenticação de Servidor para Servidor.</span><span class="sxs-lookup"><span data-stu-id="20887-136">You can also use this certificate for Server-to-Server Authentication.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="20887-137">Web interna</span><span class="sxs-lookup"><span data-stu-id="20887-137">Web internal</span></span></p></td>
<td><p><span data-ttu-id="20887-138">FQDN do servidor</span><span class="sxs-lookup"><span data-stu-id="20887-138">FQDN of the server</span></span></p></td>
<td><p><span data-ttu-id="20887-139">Cada um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="20887-139">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="20887-140">FQDN de web interna (que é o mesmo que o FQDN do servidor)</span><span class="sxs-lookup"><span data-stu-id="20887-140">Internal web FQDN (which is the same as the FQDN of the server)</span></span></p></li>
<li><p><span data-ttu-id="20887-141">Atender a URLs simples</span><span class="sxs-lookup"><span data-stu-id="20887-141">Meet simple URLs</span></span></p></li>
<li><p><span data-ttu-id="20887-142">URL simples de discagem</span><span class="sxs-lookup"><span data-stu-id="20887-142">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="20887-143">Administrar URL simples</span><span class="sxs-lookup"><span data-stu-id="20887-143">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="20887-144">Ou uma entrada curinga para as URLs simples</span><span class="sxs-lookup"><span data-stu-id="20887-144">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="20887-145">SN=se01.contoso.com; SAN=se01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="20887-145">SN=se01.contoso.com; SAN=se01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com</span></span></p>
<p><span data-ttu-id="20887-146">Como usar um certificado curinga:</span><span class="sxs-lookup"><span data-stu-id="20887-146">Using a wildcard certificate:</span></span></p>
<p><span data-ttu-id="20887-147">SN=se01.contoso.com; SAN=se01.contoso.com; SAN=\*.contoso.com</span><span class="sxs-lookup"><span data-stu-id="20887-147">SN=se01.contoso.com; SAN=se01.contoso.com; SAN=\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="20887-148">Não é possível substituir o FQDN da Web interna no construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="20887-148">You cannot override the Internal web FQDN in Topology Builder.</span></span></p>
<p><span data-ttu-id="20887-149">Se você tiver várias URLs que atendem a URLs simples, você deve incluir todas elas como nomes alternativos de assunto.</span><span class="sxs-lookup"><span data-stu-id="20887-149">If you have multiple Meet simple URLs, you must include all of them as subject alternative names.</span></span></p>
<p><span data-ttu-id="20887-150">As entradas curinga são suportadas pelas entradas de URL simples.</span><span class="sxs-lookup"><span data-stu-id="20887-150">Wildcard entries are supported for the simple URL entries.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="20887-151">Web externa</span><span class="sxs-lookup"><span data-stu-id="20887-151">Web external</span></span></p></td>
<td><p><span data-ttu-id="20887-152">FQDN do servidor</span><span class="sxs-lookup"><span data-stu-id="20887-152">FQDN of the server</span></span></p></td>
<td><p><span data-ttu-id="20887-153">Cada um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="20887-153">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="20887-154">FQDN da web externa</span><span class="sxs-lookup"><span data-stu-id="20887-154">External web FQDN</span></span></p></li>
<li><p><span data-ttu-id="20887-155">URL simples de discagem</span><span class="sxs-lookup"><span data-stu-id="20887-155">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="20887-156">Encontre URLs simples por domínio SIP</span><span class="sxs-lookup"><span data-stu-id="20887-156">Meet simple URLs per SIP domain</span></span></p></li>
<li><p><span data-ttu-id="20887-157">Ou uma entrada curinga para as URLs simples</span><span class="sxs-lookup"><span data-stu-id="20887-157">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="20887-158">SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="20887-158">SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</span></span></p>
<p><span data-ttu-id="20887-159">Como usar um certificado curinga:</span><span class="sxs-lookup"><span data-stu-id="20887-159">Using a wildcard certificate:</span></span></p>
<p><span data-ttu-id="20887-160">SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN=\*.contoso.com</span><span class="sxs-lookup"><span data-stu-id="20887-160">SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN=\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="20887-161">Se você tiver várias URLs que atendem a URLs simples, você deve incluir todas elas como nomes alternativos de assunto.</span><span class="sxs-lookup"><span data-stu-id="20887-161">If you have multiple Meet simple URLs, you must include all of them as subject alternative names.</span></span></p>
<p><span data-ttu-id="20887-162">As entradas curinga são suportadas pelas entradas de URL simples.</span><span class="sxs-lookup"><span data-stu-id="20887-162">Wildcard entries are supported for the simple URL entries.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-front-end-server-in-a-front-end-pool"></a><span data-ttu-id="20887-163">Certificados do servidor front-end em um pool de front-ends</span><span class="sxs-lookup"><span data-stu-id="20887-163">Certificates for Front End Server in a Front End Pool</span></span>

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
<th><span data-ttu-id="20887-164">Certificado</span><span class="sxs-lookup"><span data-stu-id="20887-164">Certificate</span></span></th>
<th><span data-ttu-id="20887-165">Nome do assunto/nome comum</span><span class="sxs-lookup"><span data-stu-id="20887-165">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="20887-166">Nome alternativo de entidade</span><span class="sxs-lookup"><span data-stu-id="20887-166">Subject alternative name</span></span></th>
<th><span data-ttu-id="20887-167">Exemplo</span><span class="sxs-lookup"><span data-stu-id="20887-167">Example</span></span></th>
<th><span data-ttu-id="20887-168">Comentários</span><span class="sxs-lookup"><span data-stu-id="20887-168">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="20887-169">Padrão</span><span class="sxs-lookup"><span data-stu-id="20887-169">Default</span></span></p></td>
<td><p><span data-ttu-id="20887-170">FQDN do pool</span><span class="sxs-lookup"><span data-stu-id="20887-170">FQDN of the pool</span></span></p></td>
<td><p><span data-ttu-id="20887-171">FQDN do pool e FQDN do servidor.</span><span class="sxs-lookup"><span data-stu-id="20887-171">FQDN of the pool and FQDN of the server.</span></span></p>
<p><span data-ttu-id="20887-172">Se você tiver vários domínios SIP e tiver habilitado a configuração automática do cliente, o assistente de certificados detectará e adicionará os FQDNs de cada domínio SIP aceito.</span><span class="sxs-lookup"><span data-stu-id="20887-172">If you have multiple SIP domains and have enabled automatic client configuration, the certificate wizard detects and adds each supported SIP domain FQDNs.</span></span></p>
<p><span data-ttu-id="20887-173">Se esse pool for o servidor de logon automático para clientes e a correspondência de DNS estrito for necessária na política de grupo, você também precisará de entradas para SIP. sipdomain (para cada domínio SIP que você tiver).</span><span class="sxs-lookup"><span data-stu-id="20887-173">If this pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need entries for sip.sipdomain (for each SIP domain you have).</span></span></p></td>
<td><p><span data-ttu-id="20887-174">SN=eepool.contoso.com; SAN=eepool.contoso.com; SAN=ee01.contoso.com </span><span class="sxs-lookup"><span data-stu-id="20887-174">SN=eepool.contoso.com; SAN=eepool.contoso.com; SAN=ee01.contoso.com</span></span></p>
<p><span data-ttu-id="20887-175">Se esse pool for o servidor de logon automático para clientes, e se a combinação estrita de DNS for exigida na política do grupo, também serão necessários: SAN=sip.contoso.com; SAN=sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="20887-175">If this pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need SAN=sip.contoso.com; SAN=sip.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="20887-176">O assistente detecta quaisquer domínios SIP especificados durante a instalação e os adiciona automaticamente ao nome alternativo para a entidade.</span><span class="sxs-lookup"><span data-stu-id="20887-176">The wizard detects any SIP domains you specified during setup and automatically adds them to the subject alternative name.</span></span></p>
<p><span data-ttu-id="20887-177">Você também utiliza este certificado para Autenticação de Servidor para Servidor.</span><span class="sxs-lookup"><span data-stu-id="20887-177">You can also use this certificate for Server-to-Server Authentication.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="20887-178">Web Internal</span><span class="sxs-lookup"><span data-stu-id="20887-178">Web Internal</span></span></p></td>
<td><p><span data-ttu-id="20887-179">FQDN do pool</span><span class="sxs-lookup"><span data-stu-id="20887-179">FQDN of the pool</span></span></p></td>
<td><p><span data-ttu-id="20887-180">Cada um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="20887-180">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="20887-181">FQDN da Web interna (que NÃO é igual ao FQDN do servidor)</span><span class="sxs-lookup"><span data-stu-id="20887-181">Internal web FQDN (which is NOT the same as the FQDN of the server)</span></span></p></li>
<li><p><span data-ttu-id="20887-182">FQDN do servidor</span><span class="sxs-lookup"><span data-stu-id="20887-182">Server FQDN</span></span></p></li>
<li><p><span data-ttu-id="20887-183">FQDN do pool do Lync</span><span class="sxs-lookup"><span data-stu-id="20887-183">Lync pool FQDN</span></span></p></li>
<li><p><span data-ttu-id="20887-184">Atender a URLs simples</span><span class="sxs-lookup"><span data-stu-id="20887-184">Meet simple URLs</span></span></p></li>
<li><p><span data-ttu-id="20887-185">URL simples de discagem</span><span class="sxs-lookup"><span data-stu-id="20887-185">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="20887-186">Administrar URL simples</span><span class="sxs-lookup"><span data-stu-id="20887-186">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="20887-187">Ou uma entrada curinga para as URLs simples</span><span class="sxs-lookup"><span data-stu-id="20887-187">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="20887-188">SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="20887-188">SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com</span></span></p>
<p><span data-ttu-id="20887-189">Como usar um certificado curinga:</span><span class="sxs-lookup"><span data-stu-id="20887-189">Using a wildcard certificate:</span></span></p>
<p><span data-ttu-id="20887-190">SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN=\*.contoso.com</span><span class="sxs-lookup"><span data-stu-id="20887-190">SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN=\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="20887-191">Se você tiver várias URLs que atendem a URLs simples, você deve incluir todas elas como nomes alternativos de assunto.</span><span class="sxs-lookup"><span data-stu-id="20887-191">If you have multiple Meet simple URLs, you must include all of them as subject alternative names.</span></span></p>
<p><span data-ttu-id="20887-192">As entradas curinga são suportadas pelas entradas de URL simples.</span><span class="sxs-lookup"><span data-stu-id="20887-192">Wildcard entries are supported for the simple URL entries.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="20887-193">Web externa</span><span class="sxs-lookup"><span data-stu-id="20887-193">Web external</span></span></p></td>
<td><p><span data-ttu-id="20887-194">FQDN do pool</span><span class="sxs-lookup"><span data-stu-id="20887-194">FQDN of the pool</span></span></p></td>
<td><p><span data-ttu-id="20887-195">Cada um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="20887-195">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="20887-196">FQDN da web externa</span><span class="sxs-lookup"><span data-stu-id="20887-196">External web FQDN</span></span></p></li>
<li><p><span data-ttu-id="20887-197">URL simples de discagem</span><span class="sxs-lookup"><span data-stu-id="20887-197">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="20887-198">Administrar URL simples</span><span class="sxs-lookup"><span data-stu-id="20887-198">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="20887-199">Ou uma entrada curinga para as URLs simples</span><span class="sxs-lookup"><span data-stu-id="20887-199">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="20887-200">SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="20887-200">SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</span></span></p>
<p><span data-ttu-id="20887-201">Como usar um certificado curinga:</span><span class="sxs-lookup"><span data-stu-id="20887-201">Using a wildcard certificate:</span></span></p>
<p><span data-ttu-id="20887-202">SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN=\*.contoso.com</span><span class="sxs-lookup"><span data-stu-id="20887-202">SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN=\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="20887-203">Se você tiver várias URLs que atendem a URLs simples, você deve incluir todas elas como nomes alternativos de assunto.</span><span class="sxs-lookup"><span data-stu-id="20887-203">If you have multiple Meet simple URLs, you must include all of them as subject alternative names.</span></span></p>
<p><span data-ttu-id="20887-204">As entradas curinga são suportadas pelas entradas de URL simples.</span><span class="sxs-lookup"><span data-stu-id="20887-204">Wildcard entries are supported for the simple URL entries.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-director"></a><span data-ttu-id="20887-205">Certificados para o diretor</span><span class="sxs-lookup"><span data-stu-id="20887-205">Certificates for Director</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="20887-206">Certificado</span><span class="sxs-lookup"><span data-stu-id="20887-206">Certificate</span></span></th>
<th><span data-ttu-id="20887-207">Nome do assunto/nome comum</span><span class="sxs-lookup"><span data-stu-id="20887-207">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="20887-208">Nome alternativo de entidade</span><span class="sxs-lookup"><span data-stu-id="20887-208">Subject alternative name</span></span></th>
<th><span data-ttu-id="20887-209">Exemplo</span><span class="sxs-lookup"><span data-stu-id="20887-209">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="20887-210">Padrão</span><span class="sxs-lookup"><span data-stu-id="20887-210">Default</span></span></p></td>
<td><p><span data-ttu-id="20887-211">FQDN do pool de diretor</span><span class="sxs-lookup"><span data-stu-id="20887-211">FQDN of the Director pool</span></span></p></td>
<td><p><span data-ttu-id="20887-212">FQDN do diretor, FQDN do pool de diretor</span><span class="sxs-lookup"><span data-stu-id="20887-212">FQDN of the Director, FQDN of the Director pool</span></span></p>
<p><span data-ttu-id="20887-213">Se esse pool for o servidor de logon automático para clientes e a correspondência de DNS estrito for necessária na política de grupo, você também precisará de entradas para SIP. sipdomain (para cada domínio SIP que você tiver).</span><span class="sxs-lookup"><span data-stu-id="20887-213">If this pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need entries for sip.sipdomain (for each SIP domain you have).</span></span></p></td>
<td><p><span data-ttu-id="20887-214">SN = dir-pool.contoso.com; SAN = dir-pool.contoso.com; SAN = dir01. contoso. com</span><span class="sxs-lookup"><span data-stu-id="20887-214">SN=dir-pool.contoso.com; SAN=dir-pool.contoso.com; SAN=dir01.contoso.com</span></span></p>
<p><span data-ttu-id="20887-215">Se esse pool de diretor for o servidor de logon automático para clientes e a correspondência de DNS estrito for necessária na política de grupo, você também precisará de SAN = SIP. contoso. com; SAN = SIP. fabrikam. com</span><span class="sxs-lookup"><span data-stu-id="20887-215">If this Director pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need SAN=sip.contoso.com; SAN=sip.fabrikam.com</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="20887-216">Web Internal</span><span class="sxs-lookup"><span data-stu-id="20887-216">Web Internal</span></span></p></td>
<td><p><span data-ttu-id="20887-217">FQDN do servidor</span><span class="sxs-lookup"><span data-stu-id="20887-217">FQDN of the server</span></span></p></td>
<td><p><span data-ttu-id="20887-218">Cada um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="20887-218">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="20887-219">FQDN de web interna (que é o mesmo que o FQDN do servidor)</span><span class="sxs-lookup"><span data-stu-id="20887-219">Internal web FQDN (which is the same as the FQDN of the server)</span></span></p></li>
<li><p><span data-ttu-id="20887-220">FQDN do servidor</span><span class="sxs-lookup"><span data-stu-id="20887-220">Server FQDN</span></span></p></li>
<li><p><span data-ttu-id="20887-221">FQDN do pool do Lync</span><span class="sxs-lookup"><span data-stu-id="20887-221">Lync pool FQDN</span></span></p></li>
<li><p><span data-ttu-id="20887-222">Atender a URLs simples</span><span class="sxs-lookup"><span data-stu-id="20887-222">Meet simple URLs</span></span></p></li>
<li><p><span data-ttu-id="20887-223">URL simples de discagem</span><span class="sxs-lookup"><span data-stu-id="20887-223">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="20887-224">Administrar URL simples</span><span class="sxs-lookup"><span data-stu-id="20887-224">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="20887-225">Ou uma entrada curinga para as URLs simples</span><span class="sxs-lookup"><span data-stu-id="20887-225">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="20887-226">SN=dir01.contoso.com; SAN=dir01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="20887-226">SN=dir01.contoso.com; SAN=dir01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com</span></span></p>
<p><span data-ttu-id="20887-227">SN=dir01.contoso.com; SAN=dir01.contoso.com SAN=\*.contoso.com</span><span class="sxs-lookup"><span data-stu-id="20887-227">SN=dir01.contoso.com; SAN=dir01.contoso.com SAN=\*.contoso.com</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="20887-228">Web externa</span><span class="sxs-lookup"><span data-stu-id="20887-228">Web external</span></span></p></td>
<td><p><span data-ttu-id="20887-229">FQDN do servidor</span><span class="sxs-lookup"><span data-stu-id="20887-229">FQDN of the server</span></span></p></td>
<td><p><span data-ttu-id="20887-230">Cada um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="20887-230">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="20887-231">FQDN da web externa</span><span class="sxs-lookup"><span data-stu-id="20887-231">External web FQDN</span></span></p></li>
<li><p><span data-ttu-id="20887-232">URL simples de discagem</span><span class="sxs-lookup"><span data-stu-id="20887-232">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="20887-233">Administrar URL simples</span><span class="sxs-lookup"><span data-stu-id="20887-233">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="20887-234">Ou uma entrada curinga para as URLs simples</span><span class="sxs-lookup"><span data-stu-id="20887-234">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="20887-235">O FQDN da Web externa do diretor deve ser diferente do pool de front-end ou do servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="20887-235">The Director external web FQDN must be different from the Front End pool or Front End Server.</span></span></p>
<p><span data-ttu-id="20887-236">SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="20887-236">SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</span></span></p>
<p><span data-ttu-id="20887-237">SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN=\*.contoso.com</span><span class="sxs-lookup"><span data-stu-id="20887-237">SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN=\*.contoso.com</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="20887-238">Se você tiver um pool autônomo do servidor de mediação, os servidores de mediação em cada um precisam dos certificados listados na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="20887-238">If you have a stand-alone Mediation Server pool, the Mediation Servers in it each need the certificates listed in the following table.</span></span> <span data-ttu-id="20887-239">Se você colocar o servidor de mediação com os servidores front end, os certificados listados na tabela "certificados para servidor front-end no pool Front-End", anteriormente neste tópico, serão suficientes.</span><span class="sxs-lookup"><span data-stu-id="20887-239">If you collocate Mediation Server with the Front End Servers, the certificates listed in the “Certificates for Front End Server in Front End Pool” table earlier in this topic are sufficient.</span></span>

### <a name="certificates-for-stand-alone-mediation-server"></a><span data-ttu-id="20887-240">Certificados para servidor de mediação autônomo</span><span class="sxs-lookup"><span data-stu-id="20887-240">Certificates for Stand-alone Mediation Server</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="20887-241">Certificado</span><span class="sxs-lookup"><span data-stu-id="20887-241">Certificate</span></span></th>
<th><span data-ttu-id="20887-242">Nome do assunto/nome comum</span><span class="sxs-lookup"><span data-stu-id="20887-242">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="20887-243">Nome alternativo de entidade</span><span class="sxs-lookup"><span data-stu-id="20887-243">Subject alternative name</span></span></th>
<th><span data-ttu-id="20887-244">Exemplo</span><span class="sxs-lookup"><span data-stu-id="20887-244">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="20887-245">Padrão</span><span class="sxs-lookup"><span data-stu-id="20887-245">Default</span></span></p></td>
<td><p><span data-ttu-id="20887-246">FQDN do pool</span><span class="sxs-lookup"><span data-stu-id="20887-246">FQDN of the pool</span></span></p></td>
<td><p><span data-ttu-id="20887-247">FQDN do pool</span><span class="sxs-lookup"><span data-stu-id="20887-247">FQDN of the pool</span></span></p>
<p><span data-ttu-id="20887-248">FQDN do servidor membro do pool</span><span class="sxs-lookup"><span data-stu-id="20887-248">FQDN of pool member server</span></span></p></td>
<td><p><span data-ttu-id="20887-249">SN=medsvr-pool.contoso.net; SAN=medsvr-pool.contoso.net; SAN=medsvr01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="20887-249">SN=medsvr-pool.contoso.net; SAN=medsvr-pool.contoso.net; SAN=medsvr01.contoso.net</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-survivable-branch-appliance"></a><span data-ttu-id="20887-250">Certificados para aparelho de ramificação sobreviventes</span><span class="sxs-lookup"><span data-stu-id="20887-250">Certificates for Survivable Branch Appliance</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="20887-251">Certificado</span><span class="sxs-lookup"><span data-stu-id="20887-251">Certificate</span></span></th>
<th><span data-ttu-id="20887-252">Nome do assunto/nome comum</span><span class="sxs-lookup"><span data-stu-id="20887-252">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="20887-253">Nome alternativo de entidade</span><span class="sxs-lookup"><span data-stu-id="20887-253">Subject alternative name</span></span></th>
<th><span data-ttu-id="20887-254">Exemplo</span><span class="sxs-lookup"><span data-stu-id="20887-254">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="20887-255">Padrão</span><span class="sxs-lookup"><span data-stu-id="20887-255">Default</span></span></p></td>
<td><p><span data-ttu-id="20887-256">FQDN do aplicativo</span><span class="sxs-lookup"><span data-stu-id="20887-256">FQDN of the appliance</span></span></p></td>
<td><p><span data-ttu-id="20887-257">SPI. &lt;sipdomain&gt; (precisa de uma entrada por domínio SIP)</span><span class="sxs-lookup"><span data-stu-id="20887-257">SIP.&lt;sipdomain&gt; (need one entry per SIP domain)</span></span></p></td>
<td><p><span data-ttu-id="20887-258">SN=sba01.contoso.net; SAN=sip.contoso.com; SAN=sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="20887-258">SN=sba01.contoso.net; SAN=sip.contoso.com; SAN=sip.fabrikam.com</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="20887-259">Confira também</span><span class="sxs-lookup"><span data-stu-id="20887-259">See Also</span></span>


[<span data-ttu-id="20887-260">Suporte a certificado curinga no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="20887-260">Wildcard certificate support in Lync Server 2013</span></span>](lync-server-2013-wildcard-certificate-support.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

