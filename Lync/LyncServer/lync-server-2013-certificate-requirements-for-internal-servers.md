---
title: 'Lync Server 2013: requisitos de certificado para servidores internos'
description: 'Lync Server 2013: requisitos de certificado para servidores internos.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate requirements for internal servers
ms:assetid: 0444cdbd-538c-43b1-b9a1-9d7d6cf818d6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398094(v=OCS.15)
ms:contentKeyID: 48183270
ms.date: 02/17/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dc1a627dd762c849b848087a96e00e19d320ef01
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575207"
---
# <a name="certificate-requirements-for-internal-servers-in-lync-server-2013"></a><span data-ttu-id="86f9a-103">Requisitos de certificado para servidores internos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="86f9a-103">Certificate requirements for internal servers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="86f9a-104">_**Última modificação do tópico:** 2017-02-17_</span><span class="sxs-lookup"><span data-stu-id="86f9a-104">_**Topic Last Modified:** 2017-02-17_</span></span>

<span data-ttu-id="86f9a-105">Servidores internos que estão executando o Lync Server e que exigem certificados incluem servidor Standard Edition, servidor front-end Enterprise Edition, servidor de mediação e diretor.</span><span class="sxs-lookup"><span data-stu-id="86f9a-105">Internal servers that are running Lync Server and that require certificates include Standard Edition server, Enterprise Edition Front End Server, Mediation Server, and Director.</span></span> <span data-ttu-id="86f9a-106">A tabela abaixo mostra os requisitos de certificado desses servidores.</span><span class="sxs-lookup"><span data-stu-id="86f9a-106">The following table shows the certificate requirements for these servers.</span></span> <span data-ttu-id="86f9a-107">Você pode usar o assistente de certificado do Lync Server para solicitar esses certificados.</span><span class="sxs-lookup"><span data-stu-id="86f9a-107">You can use the Lync Server certificate wizard to request these certificates.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="86f9a-108">Os certificados curinga são compatíveis com os nomes alternativos de entidade associados às URLs simples no pool de front-ends, servidor front-end ou diretor.</span><span class="sxs-lookup"><span data-stu-id="86f9a-108">Wildcard certificates are supported for the subject alternative names associated with the simple URLs on the Front End pool, Front End Server, or Director.</span></span> <span data-ttu-id="86f9a-109">Para obter detalhes sobre o suporte a certificados curinga, consulte <A href="lync-server-2013-wildcard-certificate-support.md">suporte a certificados curinga no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="86f9a-109">For details about wildcard certificate support, see <A href="lync-server-2013-wildcard-certificate-support.md">Wildcard certificate support in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="86f9a-110">Embora uma autoridade de certificação empresarial interna seja recomendada para servidores internos, você também pode usar uma autoridade de certificação pública.</span><span class="sxs-lookup"><span data-stu-id="86f9a-110">Although an internal enterprise certification authority (CA) is recommended for internal servers, you can also use a public CA.</span></span> <span data-ttu-id="86f9a-111">Para obter uma lista de autoridades de certificação públicas que oferecem certificados compatíveis com requisitos específicos para certificados de comunicações unificadas (UC) e que tenham parceria com a Microsoft para garantir que eles funcionem com o assistente de certificado do Lync Server, consulte o artigo Microsoft Knowledge Base 929395, "parceiros de certificado de comunicações unificadas para o Exchange Server e o Communications Server" em [https://go.microsoft.com/fwlink/p/?linkId=202834](https://go.microsoft.com/fwlink/p/?linkid=202834) .</span><span class="sxs-lookup"><span data-stu-id="86f9a-111">For a list of public CAs that provide certificates that comply with specific requirements for unified communications (UC) certificates and have partnered with Microsoft to ensure they work with the Lync Server Certificate Wizard, see article Microsoft Knowledge Base 929395, "Unified Communications Certificate Partners for Exchange Server and for Communications Server," at [https://go.microsoft.com/fwlink/p/?linkId=202834](https://go.microsoft.com/fwlink/p/?linkid=202834).</span></span>

<span data-ttu-id="86f9a-112">A comunicação com outros aplicativos e servidores, como o Exchange 2013, requer um certificado que seja compatível com outros aplicativos e produtos.</span><span class="sxs-lookup"><span data-stu-id="86f9a-112">Communication with other applications and servers, such as Exchange 2013, requires a certificate that is supported by the other applications and products.</span></span> <span data-ttu-id="86f9a-113">Para a versão 2013, Lync Server 2013 e outros produtos de servidor da Microsoft, incluindo o Exchange 2013 e o SharePoint Server, dão suporte ao protocolo de autorização aberta (OAuth) para autenticação e autorização de servidor para servidor.</span><span class="sxs-lookup"><span data-stu-id="86f9a-113">For the 2013 release, Lync Server 2013 and other Microsoft server products, including Exchange 2013 and SharePoint Server, support the Open Authorization (OAuth) protocol for server-to-server authentication and authorization.</span></span> <span data-ttu-id="86f9a-114">Para obter detalhes, consulte [Managing Server-to-Server Authentication (OAuth) and Partner Applications in Lync server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) na documentação de implantação ou a documentação de operações.</span><span class="sxs-lookup"><span data-stu-id="86f9a-114">For details, see [Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) in the Deployment documentation or the Operations documentation.</span></span>

<span data-ttu-id="86f9a-115">Para conexões de clientes que executam o sistema operacional Windows 7, o sistema operacional Windows Server 2008, o sistema operacional Windows Server 2008 R2, o sistema operacional Windows Vista e o Microsoft Lync Phone Edition, Lync Server 2013 inclui suporte para (mas não exige) certificados assinados usando a função de hash de criptografia SHA-256.</span><span class="sxs-lookup"><span data-stu-id="86f9a-115">For connections from clients running Windows 7 operating system, Windows Server 2008 operating system, Windows Server 2008 R2 operating system, Windows Vista operating system, and Microsoft Lync Phone Edition, Lync Server 2013 includes support for (but does not require) certificates signed using the SHA-256 cryptographic hash function.</span></span> <span data-ttu-id="86f9a-116">Para suportar acesso externo usando SHA-256, o certificado externo é emitido por um AC público usando SHA-256.</span><span class="sxs-lookup"><span data-stu-id="86f9a-116">To support external access using SHA-256, the external certificate is issued by a public CA using SHA-256.</span></span>

<span data-ttu-id="86f9a-p106">As tabelas a seguir mostram os requisitos de certificado por função de servidor para pools de Front-Ends e servidores Standard Edition. Todos são certificados padrão de servidores da web com chave privada e não exportáveis.</span><span class="sxs-lookup"><span data-stu-id="86f9a-p106">The following tables show certificate requirements by server role for Front End pools and Standard Edition servers. All these are standard web server certificates, private key, non-exportable.</span></span>

<span data-ttu-id="86f9a-119">Observe que o Uso Avançado de Chave (EKU) é automaticamente configurado quando o assistente de certificado é usado para solicitar certificados.</span><span class="sxs-lookup"><span data-stu-id="86f9a-119">Note that server enhanced key usage (EKU) is automatically configured when you use the certificate wizard to request certificates.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="86f9a-120">Cada nome amigável do certificado deve ser exclusivo no repositório do computador.</span><span class="sxs-lookup"><span data-stu-id="86f9a-120">Each certificate Friendly Name must be unique in the computer store.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="86f9a-121">Se você tiver configurado o sipinternal.contoso.com ou o sipexternal.contoso.com no seu DNS, será necessário adicioná-los ao nome alternativo da entidade do certificado.</span><span class="sxs-lookup"><span data-stu-id="86f9a-121">If you have configured sipinternal.contoso.com or sipexternal.contoso.com in your DNS, you will need to add them in the certificate’s Subject Alternative Name.</span></span>



</div>

### <a name="certificates-for-standard-edition-server"></a><span data-ttu-id="86f9a-122">Certificados para o servidor Standard Edition</span><span class="sxs-lookup"><span data-stu-id="86f9a-122">Certificates for Standard Edition Server</span></span>

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
<th><span data-ttu-id="86f9a-123">Certificado</span><span class="sxs-lookup"><span data-stu-id="86f9a-123">Certificate</span></span></th>
<th><span data-ttu-id="86f9a-124">Nome da entidade/nome comum</span><span class="sxs-lookup"><span data-stu-id="86f9a-124">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="86f9a-125">Nome da entidade alternativo</span><span class="sxs-lookup"><span data-stu-id="86f9a-125">Subject alternative name</span></span></th>
<th><span data-ttu-id="86f9a-126">Exemplo</span><span class="sxs-lookup"><span data-stu-id="86f9a-126">Example</span></span></th>
<th><span data-ttu-id="86f9a-127">Comments</span><span class="sxs-lookup"><span data-stu-id="86f9a-127">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="86f9a-128">Padrão</span><span class="sxs-lookup"><span data-stu-id="86f9a-128">Default</span></span></p></td>
<td><p><span data-ttu-id="86f9a-129">Nome de domínio totalmente qualificado (FQDN) do pool</span><span class="sxs-lookup"><span data-stu-id="86f9a-129">Fully qualified domain name (FQDN) of the pool</span></span></p></td>
<td><p><span data-ttu-id="86f9a-130">FQDN do pool e o FQDN do servidor</span><span class="sxs-lookup"><span data-stu-id="86f9a-130">FQDN of the pool and the FQDN of the server</span></span></p>
<p><span data-ttu-id="86f9a-131">Se você tiver vários domínios SIP e tiver habilitado a configuração automática do cliente, o assistente de certificados detectará e adicionará os FQDNs de cada domínio SIP aceito.</span><span class="sxs-lookup"><span data-stu-id="86f9a-131">If you have multiple SIP domains and have enabled automatic client configuration, the certificate wizard detects and adds each supported SIP domain FQDNs.</span></span></p>
<p><span data-ttu-id="86f9a-132">Se esse pool é o servidor de logon automático para clientes, e a combinação estrita do Sistema de Nome de Domínio (DNS) é exigida na política do grupo, também é preciso de entradas para o sip.sipdomain (para cada domínio de SIP que você tiver).</span><span class="sxs-lookup"><span data-stu-id="86f9a-132">If this pool is the auto-logon server for clients and strict Domain Name System (DNS) matching is required in group policy, you also need entries for sip.sipdomain (for each SIP domain you have).</span></span></p></td>
<td><p><span data-ttu-id="86f9a-133">SN = SE01. contoso. com; SAN = SE01. contoso. com</span><span class="sxs-lookup"><span data-stu-id="86f9a-133">SN=se01.contoso.com; SAN=se01.contoso.com</span></span></p>
<p><span data-ttu-id="86f9a-134">Se esse pool é o servidor de logon automático para clientes, e se a combinação estrita de DNS for exigida na política do grupo, também serão precisos: SAN=sip.contoso.com; SAN=sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="86f9a-134">If this pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need SAN=sip.contoso.com; SAN=sip.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="86f9a-135">No servidor Standard Edition, o servidor FQDN é o mesmo que o pool FQDN.</span><span class="sxs-lookup"><span data-stu-id="86f9a-135">On Standard Edition server, the server FQDN is the same as the pool FQDN.</span></span></p>
<p><span data-ttu-id="86f9a-136">O assistente detecta quaisquer domínios SIP especificados durante a instalação e os adiciona automaticamente ao nome alternativo para a entidade.</span><span class="sxs-lookup"><span data-stu-id="86f9a-136">The wizard detects any SIP domains you specified during setup and automatically adds them to the subject alternative name.</span></span></p>
<p><span data-ttu-id="86f9a-137">Você também pode usar esse certificado para autenticação de servidor para servidor.</span><span class="sxs-lookup"><span data-stu-id="86f9a-137">You can also use this certificate for Server-to-Server Authentication.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86f9a-138">Web interna</span><span class="sxs-lookup"><span data-stu-id="86f9a-138">Web internal</span></span></p></td>
<td><p><span data-ttu-id="86f9a-139">FQDN do servidor</span><span class="sxs-lookup"><span data-stu-id="86f9a-139">FQDN of the server</span></span></p></td>
<td><p><span data-ttu-id="86f9a-140">Cada um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="86f9a-140">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="86f9a-141">FQDN de web interna (que é o mesmo que o FQDN do servidor)</span><span class="sxs-lookup"><span data-stu-id="86f9a-141">Internal web FQDN (which is the same as the FQDN of the server)</span></span></p></li>
<li><p><span data-ttu-id="86f9a-142">Atender a URLs simples</span><span class="sxs-lookup"><span data-stu-id="86f9a-142">Meet simple URLs</span></span></p></li>
<li><p><span data-ttu-id="86f9a-143">Discar URL simples</span><span class="sxs-lookup"><span data-stu-id="86f9a-143">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="86f9a-144">Administrar URL simples</span><span class="sxs-lookup"><span data-stu-id="86f9a-144">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="86f9a-145">Ou, uma entrada coringa para os URLs simples</span><span class="sxs-lookup"><span data-stu-id="86f9a-145">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="86f9a-146">SN = SE01. contoso. com; SAN = SE01. contoso. com; SAN = reunião. contoso. com; SAN = atender. fabrikam. com; SAN = dialem. contoso. com; SAN = admin. contoso. com</span><span class="sxs-lookup"><span data-stu-id="86f9a-146">SN=se01.contoso.com; SAN=se01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com</span></span></p>
<p><span data-ttu-id="86f9a-147">Como usar um certificado curinga:</span><span class="sxs-lookup"><span data-stu-id="86f9a-147">Using a wildcard certificate:</span></span></p>
<p><span data-ttu-id="86f9a-148">SN = SE01. contoso. com; SAN = SE01. contoso. com; SAN = \*. contoso. com</span><span class="sxs-lookup"><span data-stu-id="86f9a-148">SN=se01.contoso.com; SAN=se01.contoso.com; SAN=\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="86f9a-149">Não é possível substituir o FQDN interno da Web no construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="86f9a-149">You cannot override the Internal web FQDN in Topology Builder.</span></span></p>
<p><span data-ttu-id="86f9a-150">Se possuir vários Atender a URLs simples, devem-se incluir todos eles como nomes alternativos de entidade.</span><span class="sxs-lookup"><span data-stu-id="86f9a-150">If you have multiple Meet simple URLs, you must include all of them as subject alternative names.</span></span></p>
<p><span data-ttu-id="86f9a-151">As entradas curinga são suportadas pelas entradas de URL simples.</span><span class="sxs-lookup"><span data-stu-id="86f9a-151">Wildcard entries are supported for the simple URL entries.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86f9a-152">Web externa</span><span class="sxs-lookup"><span data-stu-id="86f9a-152">Web external</span></span></p></td>
<td><p><span data-ttu-id="86f9a-153">FQDN do servidor</span><span class="sxs-lookup"><span data-stu-id="86f9a-153">FQDN of the server</span></span></p></td>
<td><p><span data-ttu-id="86f9a-154">Cada um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="86f9a-154">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="86f9a-155">FQDN da web externa</span><span class="sxs-lookup"><span data-stu-id="86f9a-155">External web FQDN</span></span></p></li>
<li><p><span data-ttu-id="86f9a-156">Discar URL simples</span><span class="sxs-lookup"><span data-stu-id="86f9a-156">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="86f9a-157">Atender URLs simples por domínio SIP</span><span class="sxs-lookup"><span data-stu-id="86f9a-157">Meet simple URLs per SIP domain</span></span></p></li>
<li><p><span data-ttu-id="86f9a-158">Ou, uma entrada curinga para os URLs simples</span><span class="sxs-lookup"><span data-stu-id="86f9a-158">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="86f9a-159">SN = SE01. contoso. com; SAN = webcon01. contoso. com; SAN = reunião. contoso. com; SAN = atender. fabrikam. com; SAN = dialem. contoso. com</span><span class="sxs-lookup"><span data-stu-id="86f9a-159">SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</span></span></p>
<p><span data-ttu-id="86f9a-160">Como usar um certificado coringa:</span><span class="sxs-lookup"><span data-stu-id="86f9a-160">Using a wildcard certificate:</span></span></p>
<p><span data-ttu-id="86f9a-161">SN = SE01. contoso. com; SAN = webcon01. contoso. com; SAN = \*. contoso. com</span><span class="sxs-lookup"><span data-stu-id="86f9a-161">SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN=\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="86f9a-162">Se possuir vários Atender a URLs simples, devem-se incluir todos eles como nomes alternativos de entidade.</span><span class="sxs-lookup"><span data-stu-id="86f9a-162">If you have multiple Meet simple URLs, you must include all of them as subject alternative names.</span></span></p>
<p><span data-ttu-id="86f9a-163">As entradas curinga são suportadas pelas entradas de URL simples.</span><span class="sxs-lookup"><span data-stu-id="86f9a-163">Wildcard entries are supported for the simple URL entries.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-front-end-server-in-a-front-end-pool"></a><span data-ttu-id="86f9a-164">Certificados de servidor Front-End eu um pool de Front-Ends</span><span class="sxs-lookup"><span data-stu-id="86f9a-164">Certificates for Front End Server in a Front End Pool</span></span>

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
<th><span data-ttu-id="86f9a-165">Certificado</span><span class="sxs-lookup"><span data-stu-id="86f9a-165">Certificate</span></span></th>
<th><span data-ttu-id="86f9a-166">Nome da entidade/nome comum</span><span class="sxs-lookup"><span data-stu-id="86f9a-166">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="86f9a-167">Nome da entidade alternativo</span><span class="sxs-lookup"><span data-stu-id="86f9a-167">Subject alternative name</span></span></th>
<th><span data-ttu-id="86f9a-168">Exemplo</span><span class="sxs-lookup"><span data-stu-id="86f9a-168">Example</span></span></th>
<th><span data-ttu-id="86f9a-169">Comments</span><span class="sxs-lookup"><span data-stu-id="86f9a-169">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="86f9a-170">Padrão</span><span class="sxs-lookup"><span data-stu-id="86f9a-170">Default</span></span></p></td>
<td><p><span data-ttu-id="86f9a-171">FQDN do pool</span><span class="sxs-lookup"><span data-stu-id="86f9a-171">FQDN of the pool</span></span></p></td>
<td><p><span data-ttu-id="86f9a-172">FQDN do pool e FQDN do servidor.</span><span class="sxs-lookup"><span data-stu-id="86f9a-172">FQDN of the pool and FQDN of the server.</span></span></p>
<p><span data-ttu-id="86f9a-173">Se você tiver vários domínios SIP e tiver habilitado a configuração automática do cliente, o assistente de certificados detectará e adicionará os FQDNs de cada domínio SIP aceito.</span><span class="sxs-lookup"><span data-stu-id="86f9a-173">If you have multiple SIP domains and have enabled automatic client configuration, the certificate wizard detects and adds each supported SIP domain FQDNs.</span></span></p>
<p><span data-ttu-id="86f9a-174">Se esse pool é o servidor de logon automático para clientes, e a combinação estrita do DNS é exigida na política do grupo, também é preciso de entradas para o sip.sipdomain (para cada domínio de SIP que você tiver).</span><span class="sxs-lookup"><span data-stu-id="86f9a-174">If this pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need entries for sip.sipdomain (for each SIP domain you have).</span></span></p></td>
<td><p><span data-ttu-id="86f9a-175">SN = EEpool. contoso. com; SAN = EEpool. contoso. com; SAN = ee01. contoso. com</span><span class="sxs-lookup"><span data-stu-id="86f9a-175">SN=eepool.contoso.com; SAN=eepool.contoso.com; SAN=ee01.contoso.com</span></span></p>
<p><span data-ttu-id="86f9a-176">Se esse pool é o servidor de logon automático para clientes, e se a combinação estrita de DNS for exigida na política do grupo, também serão precisos: SAN=sip.contoso.com; SAN=sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="86f9a-176">If this pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need SAN=sip.contoso.com; SAN=sip.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="86f9a-177">O assistente detecta quaisquer domínios SIP especificados durante a instalação e os adiciona automaticamente ao nome alternativo para a entidade.</span><span class="sxs-lookup"><span data-stu-id="86f9a-177">The wizard detects any SIP domains you specified during setup and automatically adds them to the subject alternative name.</span></span></p>
<p><span data-ttu-id="86f9a-178">Você também pode usar esse certificado para autenticação de servidor para servidor.</span><span class="sxs-lookup"><span data-stu-id="86f9a-178">You can also use this certificate for Server-to-Server Authentication.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86f9a-179">Web interna</span><span class="sxs-lookup"><span data-stu-id="86f9a-179">Web Internal</span></span></p></td>
<td><p><span data-ttu-id="86f9a-180">FQDN do pool</span><span class="sxs-lookup"><span data-stu-id="86f9a-180">FQDN of the pool</span></span></p></td>
<td><p><span data-ttu-id="86f9a-181">Cada um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="86f9a-181">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="86f9a-182">FQDN da Web interna (que não é o mesmo que o FQDN do servidor)</span><span class="sxs-lookup"><span data-stu-id="86f9a-182">Internal web FQDN (which is NOT the same as the FQDN of the server)</span></span></p></li>
<li><p><span data-ttu-id="86f9a-183">FQDN do servidor</span><span class="sxs-lookup"><span data-stu-id="86f9a-183">Server FQDN</span></span></p></li>
<li><p><span data-ttu-id="86f9a-184">FQDN do pool do Lync</span><span class="sxs-lookup"><span data-stu-id="86f9a-184">Lync pool FQDN</span></span></p></li>
<li><p><span data-ttu-id="86f9a-185">Atender a URLs simples</span><span class="sxs-lookup"><span data-stu-id="86f9a-185">Meet simple URLs</span></span></p></li>
<li><p><span data-ttu-id="86f9a-186">Discar URL simples</span><span class="sxs-lookup"><span data-stu-id="86f9a-186">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="86f9a-187">Administrar URL simples</span><span class="sxs-lookup"><span data-stu-id="86f9a-187">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="86f9a-188">Ou, uma entrada curinga para os URLs simples</span><span class="sxs-lookup"><span data-stu-id="86f9a-188">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="86f9a-189">SN = ee01. contoso. com; SAN = ee01. contoso. com; SAN = reunião. contoso. com; SAN = atender. fabrikam. com; SAN = dialem. contoso. com; SAN = admin. contoso. com</span><span class="sxs-lookup"><span data-stu-id="86f9a-189">SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com</span></span></p>
<p><span data-ttu-id="86f9a-190">Como usar um certificado curinga:</span><span class="sxs-lookup"><span data-stu-id="86f9a-190">Using a wildcard certificate:</span></span></p>
<p><span data-ttu-id="86f9a-191">SN = ee01. contoso. com; SAN = ee01. contoso. com; SAN = \*. contoso. com</span><span class="sxs-lookup"><span data-stu-id="86f9a-191">SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN=\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="86f9a-192">Se possuir vários Atender a URLs simples, devem-se incluir todos eles como nomes alternativos de entidade.</span><span class="sxs-lookup"><span data-stu-id="86f9a-192">If you have multiple Meet simple URLs, you must include all of them as subject alternative names.</span></span></p>
<p><span data-ttu-id="86f9a-193">As entradas curinga são suportadas pelas entradas de URL simples.</span><span class="sxs-lookup"><span data-stu-id="86f9a-193">Wildcard entries are supported for the simple URL entries.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86f9a-194">Web externa</span><span class="sxs-lookup"><span data-stu-id="86f9a-194">Web external</span></span></p></td>
<td><p><span data-ttu-id="86f9a-195">FQDN do pool</span><span class="sxs-lookup"><span data-stu-id="86f9a-195">FQDN of the pool</span></span></p></td>
<td><p><span data-ttu-id="86f9a-196">Cada um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="86f9a-196">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="86f9a-197">FQDN da web externa</span><span class="sxs-lookup"><span data-stu-id="86f9a-197">External web FQDN</span></span></p></li>
<li><p><span data-ttu-id="86f9a-198">Discar URL simples</span><span class="sxs-lookup"><span data-stu-id="86f9a-198">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="86f9a-199">Administrar URL simples</span><span class="sxs-lookup"><span data-stu-id="86f9a-199">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="86f9a-200">Ou, uma entrada curinga para os URLs simples</span><span class="sxs-lookup"><span data-stu-id="86f9a-200">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="86f9a-201">SN = ee01. contoso. com; SAN = webcon01. contoso. com; SAN = reunião. contoso. com; SAN = atender. fabrikam. com; SAN = dialem. contoso. com</span><span class="sxs-lookup"><span data-stu-id="86f9a-201">SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</span></span></p>
<p><span data-ttu-id="86f9a-202">Como usar um certificado curinga:</span><span class="sxs-lookup"><span data-stu-id="86f9a-202">Using a wildcard certificate:</span></span></p>
<p><span data-ttu-id="86f9a-203">SN = ee01. contoso. com; SAN = webcon01. contoso. com; SAN = \*. contoso. com</span><span class="sxs-lookup"><span data-stu-id="86f9a-203">SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN=\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="86f9a-204">Se possuir vários Atender a URLs simples, devem-se incluir todos eles como nomes alternativos de entidade.</span><span class="sxs-lookup"><span data-stu-id="86f9a-204">If you have multiple Meet simple URLs, you must include all of them as subject alternative names.</span></span></p>
<p><span data-ttu-id="86f9a-205">As entradas curinga são suportadas pelas entradas de URL simples.</span><span class="sxs-lookup"><span data-stu-id="86f9a-205">Wildcard entries are supported for the simple URL entries.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-director"></a><span data-ttu-id="86f9a-206">Certificados do diretor</span><span class="sxs-lookup"><span data-stu-id="86f9a-206">Certificates for Director</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="86f9a-207">Certificado</span><span class="sxs-lookup"><span data-stu-id="86f9a-207">Certificate</span></span></th>
<th><span data-ttu-id="86f9a-208">Nome da entidade/nome comum</span><span class="sxs-lookup"><span data-stu-id="86f9a-208">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="86f9a-209">Nome da entidade alternativo</span><span class="sxs-lookup"><span data-stu-id="86f9a-209">Subject alternative name</span></span></th>
<th><span data-ttu-id="86f9a-210">Exemplo</span><span class="sxs-lookup"><span data-stu-id="86f9a-210">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="86f9a-211">Padrão</span><span class="sxs-lookup"><span data-stu-id="86f9a-211">Default</span></span></p></td>
<td><p><span data-ttu-id="86f9a-212">FQDN do pool de Diretores</span><span class="sxs-lookup"><span data-stu-id="86f9a-212">FQDN of the Director pool</span></span></p></td>
<td><p><span data-ttu-id="86f9a-213">FQDN do Diretor, FQDN do pool de Diretores</span><span class="sxs-lookup"><span data-stu-id="86f9a-213">FQDN of the Director, FQDN of the Director pool</span></span></p>
<p><span data-ttu-id="86f9a-214">Se esse pool for o servidor de logon automático para clientes, e a combinação estrita do DNS é exigida na política do grupo, também é preciso de entradas para o sip.sipdomain (para cada domínio de SIP que você tiver).</span><span class="sxs-lookup"><span data-stu-id="86f9a-214">If this pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need entries for sip.sipdomain (for each SIP domain you have).</span></span></p></td>
<td><p><span data-ttu-id="86f9a-215">SN = dir-pool.contoso.com; SAN = dir-pool.contoso.com; SAN = dir01. contoso. com</span><span class="sxs-lookup"><span data-stu-id="86f9a-215">SN=dir-pool.contoso.com; SAN=dir-pool.contoso.com; SAN=dir01.contoso.com</span></span></p>
<p><span data-ttu-id="86f9a-216">Se esse pool de Diretor for o servidor de logon automático para clientes, e se a combinação estrita de DNS for exigida na política do grupo, também serão precisos: SAN=sip.contoso.com; SAN=sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="86f9a-216">If this Director pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need SAN=sip.contoso.com; SAN=sip.fabrikam.com</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86f9a-217">Web interna</span><span class="sxs-lookup"><span data-stu-id="86f9a-217">Web Internal</span></span></p></td>
<td><p><span data-ttu-id="86f9a-218">FQDN do servidor</span><span class="sxs-lookup"><span data-stu-id="86f9a-218">FQDN of the server</span></span></p></td>
<td><p><span data-ttu-id="86f9a-219">Cada um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="86f9a-219">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="86f9a-220">FQDN de web interna (que é o mesmo que o FQDN do servidor)</span><span class="sxs-lookup"><span data-stu-id="86f9a-220">Internal web FQDN (which is the same as the FQDN of the server)</span></span></p></li>
<li><p><span data-ttu-id="86f9a-221">FQDN do servidor</span><span class="sxs-lookup"><span data-stu-id="86f9a-221">Server FQDN</span></span></p></li>
<li><p><span data-ttu-id="86f9a-222">FQDN do pool do Lync</span><span class="sxs-lookup"><span data-stu-id="86f9a-222">Lync pool FQDN</span></span></p></li>
<li><p><span data-ttu-id="86f9a-223">Atender a URLs simples</span><span class="sxs-lookup"><span data-stu-id="86f9a-223">Meet simple URLs</span></span></p></li>
<li><p><span data-ttu-id="86f9a-224">Discar URL simples</span><span class="sxs-lookup"><span data-stu-id="86f9a-224">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="86f9a-225">Administrar URL simples</span><span class="sxs-lookup"><span data-stu-id="86f9a-225">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="86f9a-226">Ou, uma entrada curinga para os URLs simples</span><span class="sxs-lookup"><span data-stu-id="86f9a-226">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="86f9a-227">SN = dir01. contoso. com; SAN = dir01. contoso. com; SAN = reunião. contoso. com; SAN = atender. fabrikam. com; SAN = dialem. contoso. com; SAN = admin. contoso. com</span><span class="sxs-lookup"><span data-stu-id="86f9a-227">SN=dir01.contoso.com; SAN=dir01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com</span></span></p>
<p><span data-ttu-id="86f9a-228">SN = dir01. contoso. com; SAN = dir01. contoso. com SAN = \*. contoso. com</span><span class="sxs-lookup"><span data-stu-id="86f9a-228">SN=dir01.contoso.com; SAN=dir01.contoso.com SAN=\*.contoso.com</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86f9a-229">Web externa</span><span class="sxs-lookup"><span data-stu-id="86f9a-229">Web external</span></span></p></td>
<td><p><span data-ttu-id="86f9a-230">FQDN do servidor</span><span class="sxs-lookup"><span data-stu-id="86f9a-230">FQDN of the server</span></span></p></td>
<td><p><span data-ttu-id="86f9a-231">Cada um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="86f9a-231">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="86f9a-232">FQDN da web externa</span><span class="sxs-lookup"><span data-stu-id="86f9a-232">External web FQDN</span></span></p></li>
<li><p><span data-ttu-id="86f9a-233">Discar URL simples</span><span class="sxs-lookup"><span data-stu-id="86f9a-233">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="86f9a-234">Administrar URL simples</span><span class="sxs-lookup"><span data-stu-id="86f9a-234">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="86f9a-235">Ou, uma entrada curinga para os URLs simples</span><span class="sxs-lookup"><span data-stu-id="86f9a-235">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="86f9a-236">O FQDN da Web externa do diretor deve ser diferente do pool de front-ends ou servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="86f9a-236">The Director external web FQDN must be different from the Front End pool or Front End Server.</span></span></p>
<p><span data-ttu-id="86f9a-237">SN = dir01. contoso. com; SAN = directorwebcon01. contoso. com SAN = encontro. contoso. com; SAN = atender. fabrikam. com; SAN = dialem. contoso. com</span><span class="sxs-lookup"><span data-stu-id="86f9a-237">SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</span></span></p>
<p><span data-ttu-id="86f9a-238">SN = dir01. contoso. com; SAN = directorwebcon01. contoso. com SAN = \*. contoso. com</span><span class="sxs-lookup"><span data-stu-id="86f9a-238">SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN=\*.contoso.com</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="86f9a-p107">Se possuir um pool do Servidor de Mediação autônomo, os servidores presentes em cada um precisam dos certificados listados na tabela a seguir. Se um Servidor de Mediação for colocado junto aos Servidores Front-End, são suficientes os certificados listados na tabela “Certificados para Servidor Front-End no Pool do Front-End”, já apresentada neste tópico.</span><span class="sxs-lookup"><span data-stu-id="86f9a-p107">If you have a stand-alone Mediation Server pool, the Mediation Servers in it each need the certificates listed in the following table. If you collocate Mediation Server with the Front End Servers, the certificates listed in the “Certificates for Front End Server in Front End Pool” table earlier in this topic are sufficient.</span></span>

### <a name="certificates-for-stand-alone-mediation-server"></a><span data-ttu-id="86f9a-241">Certificados para um Servidor de Mediação Autônomo</span><span class="sxs-lookup"><span data-stu-id="86f9a-241">Certificates for Stand-alone Mediation Server</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="86f9a-242">Certificado</span><span class="sxs-lookup"><span data-stu-id="86f9a-242">Certificate</span></span></th>
<th><span data-ttu-id="86f9a-243">Nome da entidade/nome comum</span><span class="sxs-lookup"><span data-stu-id="86f9a-243">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="86f9a-244">Nome da entidade alternativo</span><span class="sxs-lookup"><span data-stu-id="86f9a-244">Subject alternative name</span></span></th>
<th><span data-ttu-id="86f9a-245">Exemplo</span><span class="sxs-lookup"><span data-stu-id="86f9a-245">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="86f9a-246">Padrão</span><span class="sxs-lookup"><span data-stu-id="86f9a-246">Default</span></span></p></td>
<td><p><span data-ttu-id="86f9a-247">FQDN do pool</span><span class="sxs-lookup"><span data-stu-id="86f9a-247">FQDN of the pool</span></span></p></td>
<td><p><span data-ttu-id="86f9a-248">FQDN do pool</span><span class="sxs-lookup"><span data-stu-id="86f9a-248">FQDN of the pool</span></span></p>
<p><span data-ttu-id="86f9a-249">FQDN do servidor membro do pool</span><span class="sxs-lookup"><span data-stu-id="86f9a-249">FQDN of pool member server</span></span></p></td>
<td><p><span data-ttu-id="86f9a-250">SN = medsvr-pool.contoso.net; SAN = medsvr-pool.contoso.net; SAN = medsvr01. contoso. net</span><span class="sxs-lookup"><span data-stu-id="86f9a-250">SN=medsvr-pool.contoso.net; SAN=medsvr-pool.contoso.net; SAN=medsvr01.contoso.net</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-survivable-branch-appliance"></a><span data-ttu-id="86f9a-251">Certificados para Aparelho de Filial Persistente</span><span class="sxs-lookup"><span data-stu-id="86f9a-251">Certificates for Survivable Branch Appliance</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="86f9a-252">Certificado</span><span class="sxs-lookup"><span data-stu-id="86f9a-252">Certificate</span></span></th>
<th><span data-ttu-id="86f9a-253">Nome da entidade/nome comum</span><span class="sxs-lookup"><span data-stu-id="86f9a-253">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="86f9a-254">Nome da entidade alternativo</span><span class="sxs-lookup"><span data-stu-id="86f9a-254">Subject alternative name</span></span></th>
<th><span data-ttu-id="86f9a-255">Exemplo</span><span class="sxs-lookup"><span data-stu-id="86f9a-255">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="86f9a-256">Padrão</span><span class="sxs-lookup"><span data-stu-id="86f9a-256">Default</span></span></p></td>
<td><p><span data-ttu-id="86f9a-257">FQDN do aplicativo</span><span class="sxs-lookup"><span data-stu-id="86f9a-257">FQDN of the appliance</span></span></p></td>
<td><p><span data-ttu-id="86f9a-258">SIP. &lt; sipdomain &gt; (precisa de uma entrada por domínio SIP)</span><span class="sxs-lookup"><span data-stu-id="86f9a-258">SIP.&lt;sipdomain&gt; (need one entry per SIP domain)</span></span></p></td>
<td><p><span data-ttu-id="86f9a-259">SN = sba01. contoso. net; SAN = SIP. contoso. com; SAN = SIP. fabrikam. com</span><span class="sxs-lookup"><span data-stu-id="86f9a-259">SN=sba01.contoso.net; SAN=sip.contoso.com; SAN=sip.fabrikam.com</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="86f9a-260">Confira também</span><span class="sxs-lookup"><span data-stu-id="86f9a-260">See Also</span></span>


[<span data-ttu-id="86f9a-261">Suporte a certificados curinga no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="86f9a-261">Wildcard certificate support in Lync Server 2013</span></span>](lync-server-2013-wildcard-certificate-support.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

