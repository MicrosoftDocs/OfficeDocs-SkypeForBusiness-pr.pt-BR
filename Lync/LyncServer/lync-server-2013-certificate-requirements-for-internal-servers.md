---
title: 'Lync Server 2013: requisitos de certificado para servidores internos'
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
ms.openlocfilehash: f5b3da640ca4aa9f7b53c072802a2f7f727759dc
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038423"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-requirements-for-internal-servers-in-lync-server-2013"></a><span data-ttu-id="87809-102">Requisitos de certificado para servidores internos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="87809-102">Certificate requirements for internal servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="87809-103">_**Última modificação do tópico:** 2017-02-17_</span><span class="sxs-lookup"><span data-stu-id="87809-103">_**Topic Last Modified:** 2017-02-17_</span></span>

<span data-ttu-id="87809-104">Servidores internos que estão executando o Lync Server e que exigem certificados incluem servidor Standard Edition, servidor front-end Enterprise Edition, servidor de mediação e diretor.</span><span class="sxs-lookup"><span data-stu-id="87809-104">Internal servers that are running Lync Server and that require certificates include Standard Edition server, Enterprise Edition Front End Server, Mediation Server, and Director.</span></span> <span data-ttu-id="87809-105">A tabela abaixo mostra os requisitos de certificado desses servidores.</span><span class="sxs-lookup"><span data-stu-id="87809-105">The following table shows the certificate requirements for these servers.</span></span> <span data-ttu-id="87809-106">Você pode usar o assistente de certificado do Lync Server para solicitar esses certificados.</span><span class="sxs-lookup"><span data-stu-id="87809-106">You can use the Lync Server certificate wizard to request these certificates.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="87809-107">Os certificados curinga são compatíveis com os nomes alternativos de entidade associados às URLs simples no pool de front-ends, servidor front-end ou diretor.</span><span class="sxs-lookup"><span data-stu-id="87809-107">Wildcard certificates are supported for the subject alternative names associated with the simple URLs on the Front End pool, Front End Server, or Director.</span></span> <span data-ttu-id="87809-108">Para obter detalhes sobre o suporte a certificados curinga, consulte <A href="lync-server-2013-wildcard-certificate-support.md">suporte a certificados curinga no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="87809-108">For details about wildcard certificate support, see <A href="lync-server-2013-wildcard-certificate-support.md">Wildcard certificate support in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="87809-109">Embora uma autoridade de certificação empresarial interna seja recomendada para servidores internos, você também pode usar uma autoridade de certificação pública.</span><span class="sxs-lookup"><span data-stu-id="87809-109">Although an internal enterprise certification authority (CA) is recommended for internal servers, you can also use a public CA.</span></span> <span data-ttu-id="87809-110">Para obter uma lista de autoridades de certificação públicas que oferecem certificados compatíveis com requisitos específicos para certificados de comunicações unificadas (UC) e que tenham parceria com a Microsoft para garantir que eles funcionem com o assistente de certificado do Lync Server, consulte o artigo Microsoft Knowledge Base 929395, "parceiros de certificado de [https://go.microsoft.com/fwlink/p/?linkId=202834](https://go.microsoft.com/fwlink/p/?linkid=202834)comunicações unificadas para o Exchange Server e o Communications Server" em.</span><span class="sxs-lookup"><span data-stu-id="87809-110">For a list of public CAs that provide certificates that comply with specific requirements for unified communications (UC) certificates and have partnered with Microsoft to ensure they work with the Lync Server Certificate Wizard, see article Microsoft Knowledge Base 929395, "Unified Communications Certificate Partners for Exchange Server and for Communications Server," at [https://go.microsoft.com/fwlink/p/?linkId=202834](https://go.microsoft.com/fwlink/p/?linkid=202834).</span></span>

<span data-ttu-id="87809-111">A comunicação com outros aplicativos e servidores, como o Exchange 2013, requer um certificado que seja compatível com outros aplicativos e produtos.</span><span class="sxs-lookup"><span data-stu-id="87809-111">Communication with other applications and servers, such as Exchange 2013, requires a certificate that is supported by the other applications and products.</span></span> <span data-ttu-id="87809-112">Para a versão 2013, Lync Server 2013 e outros produtos de servidor da Microsoft, incluindo o Exchange 2013 e o SharePoint Server, dão suporte ao protocolo de autorização aberta (OAuth) para autenticação e autorização de servidor para servidor.</span><span class="sxs-lookup"><span data-stu-id="87809-112">For the 2013 release, Lync Server 2013 and other Microsoft server products, including Exchange 2013 and SharePoint Server, support the Open Authorization (OAuth) protocol for server-to-server authentication and authorization.</span></span> <span data-ttu-id="87809-113">Para obter detalhes, consulte [Managing Server-to-Server Authentication (OAuth) and Partner Applications in Lync server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) na documentação de implantação ou a documentação de operações.</span><span class="sxs-lookup"><span data-stu-id="87809-113">For details, see [Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) in the Deployment documentation or the Operations documentation.</span></span>

<span data-ttu-id="87809-114">Para conexões de clientes que executam o sistema operacional Windows 7, o sistema operacional Windows Server 2008, o sistema operacional Windows Server 2008 R2, o sistema operacional Windows Vista e o Microsoft Lync Phone Edition, Lync Server 2013 inclui suporte para (mas não require) certificados assinados usando a função de hash criptográfico SHA-256.</span><span class="sxs-lookup"><span data-stu-id="87809-114">For connections from clients running Windows 7 operating system, Windows Server 2008 operating system, Windows Server 2008 R2 operating system, Windows Vista operating system, and Microsoft Lync Phone Edition, Lync Server 2013 includes support for (but does not require) certificates signed using the SHA-256 cryptographic hash function.</span></span> <span data-ttu-id="87809-115">Para suportar acesso externo usando SHA-256, o certificado externo é emitido por um AC público usando SHA-256.</span><span class="sxs-lookup"><span data-stu-id="87809-115">To support external access using SHA-256, the external certificate is issued by a public CA using SHA-256.</span></span>

<span data-ttu-id="87809-p106">As tabelas a seguir mostram os requisitos de certificado por função de servidor para pools de Front-Ends e servidores Standard Edition. Todos são certificados padrão de servidores da web com chave privada e não exportáveis.</span><span class="sxs-lookup"><span data-stu-id="87809-p106">The following tables show certificate requirements by server role for Front End pools and Standard Edition servers. All these are standard web server certificates, private key, non-exportable.</span></span>

<span data-ttu-id="87809-118">Observe que o Uso Avançado de Chave (EKU) é automaticamente configurado quando o assistente de certificado é usado para solicitar certificados.</span><span class="sxs-lookup"><span data-stu-id="87809-118">Note that server enhanced key usage (EKU) is automatically configured when you use the certificate wizard to request certificates.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="87809-119">Cada nome amigável do certificado deve ser exclusivo no repositório do computador.</span><span class="sxs-lookup"><span data-stu-id="87809-119">Each certificate Friendly Name must be unique in the computer store.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="87809-120">Se você tiver configurado o sipinternal.contoso.com ou o sipexternal.contoso.com no seu DNS, será necessário adicioná-los ao nome alternativo da entidade do certificado.</span><span class="sxs-lookup"><span data-stu-id="87809-120">If you have configured sipinternal.contoso.com or sipexternal.contoso.com in your DNS, you will need to add them in the certificate’s Subject Alternative Name.</span></span>



</div>

### <a name="certificates-for-standard-edition-server"></a><span data-ttu-id="87809-121">Certificados para o servidor Standard Edition</span><span class="sxs-lookup"><span data-stu-id="87809-121">Certificates for Standard Edition Server</span></span>

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
<th><span data-ttu-id="87809-122">Certificado</span><span class="sxs-lookup"><span data-stu-id="87809-122">Certificate</span></span></th>
<th><span data-ttu-id="87809-123">Nome da entidade/nome comum</span><span class="sxs-lookup"><span data-stu-id="87809-123">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="87809-124">Nome da entidade alternativo</span><span class="sxs-lookup"><span data-stu-id="87809-124">Subject alternative name</span></span></th>
<th><span data-ttu-id="87809-125">Exemplo</span><span class="sxs-lookup"><span data-stu-id="87809-125">Example</span></span></th>
<th><span data-ttu-id="87809-126">Comentários</span><span class="sxs-lookup"><span data-stu-id="87809-126">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="87809-127">Padrão</span><span class="sxs-lookup"><span data-stu-id="87809-127">Default</span></span></p></td>
<td><p><span data-ttu-id="87809-128">Nome de domínio totalmente qualificado (FQDN) do pool</span><span class="sxs-lookup"><span data-stu-id="87809-128">Fully qualified domain name (FQDN) of the pool</span></span></p></td>
<td><p><span data-ttu-id="87809-129">FQDN do pool e o FQDN do servidor</span><span class="sxs-lookup"><span data-stu-id="87809-129">FQDN of the pool and the FQDN of the server</span></span></p>
<p><span data-ttu-id="87809-130">Se você tiver vários domínios SIP e tiver habilitado a configuração automática do cliente, o assistente de certificados detectará e adicionará os FQDNs de cada domínio SIP aceito.</span><span class="sxs-lookup"><span data-stu-id="87809-130">If you have multiple SIP domains and have enabled automatic client configuration, the certificate wizard detects and adds each supported SIP domain FQDNs.</span></span></p>
<p><span data-ttu-id="87809-131">Se esse pool é o servidor de logon automático para clientes, e a combinação estrita do Sistema de Nome de Domínio (DNS) é exigida na política do grupo, também é preciso de entradas para o sip.sipdomain (para cada domínio de SIP que você tiver).</span><span class="sxs-lookup"><span data-stu-id="87809-131">If this pool is the auto-logon server for clients and strict Domain Name System (DNS) matching is required in group policy, you also need entries for sip.sipdomain (for each SIP domain you have).</span></span></p></td>
<td><p><span data-ttu-id="87809-132">SN = SE01. contoso. com; SAN = SE01. contoso. com</span><span class="sxs-lookup"><span data-stu-id="87809-132">SN=se01.contoso.com; SAN=se01.contoso.com</span></span></p>
<p><span data-ttu-id="87809-133">Se esse pool é o servidor de logon automático para clientes, e se a combinação estrita de DNS for exigida na política do grupo, também serão precisos: SAN=sip.contoso.com; SAN=sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="87809-133">If this pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need SAN=sip.contoso.com; SAN=sip.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="87809-134">No servidor Standard Edition, o servidor FQDN é o mesmo que o pool FQDN.</span><span class="sxs-lookup"><span data-stu-id="87809-134">On Standard Edition server, the server FQDN is the same as the pool FQDN.</span></span></p>
<p><span data-ttu-id="87809-135">O assistente detecta quaisquer domínios SIP especificados durante a instalação e os adiciona automaticamente ao nome alternativo para a entidade.</span><span class="sxs-lookup"><span data-stu-id="87809-135">The wizard detects any SIP domains you specified during setup and automatically adds them to the subject alternative name.</span></span></p>
<p><span data-ttu-id="87809-136">Você também pode usar esse certificado para autenticação de servidor para servidor.</span><span class="sxs-lookup"><span data-stu-id="87809-136">You can also use this certificate for Server-to-Server Authentication.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="87809-137">Web interna</span><span class="sxs-lookup"><span data-stu-id="87809-137">Web internal</span></span></p></td>
<td><p><span data-ttu-id="87809-138">FQDN do servidor</span><span class="sxs-lookup"><span data-stu-id="87809-138">FQDN of the server</span></span></p></td>
<td><p><span data-ttu-id="87809-139">Cada um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="87809-139">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="87809-140">FQDN de web interna (que é o mesmo que o FQDN do servidor)</span><span class="sxs-lookup"><span data-stu-id="87809-140">Internal web FQDN (which is the same as the FQDN of the server)</span></span></p></li>
<li><p><span data-ttu-id="87809-141">Atender a URLs simples</span><span class="sxs-lookup"><span data-stu-id="87809-141">Meet simple URLs</span></span></p></li>
<li><p><span data-ttu-id="87809-142">Discar URL simples</span><span class="sxs-lookup"><span data-stu-id="87809-142">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="87809-143">Administrar URL simples</span><span class="sxs-lookup"><span data-stu-id="87809-143">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="87809-144">Ou, uma entrada coringa para os URLs simples</span><span class="sxs-lookup"><span data-stu-id="87809-144">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="87809-145">SN = SE01. contoso. com; SAN = SE01. contoso. com; SAN = reunião. contoso. com; SAN = atender. fabrikam. com; SAN = dialem. contoso. com; SAN = admin. contoso. com</span><span class="sxs-lookup"><span data-stu-id="87809-145">SN=se01.contoso.com; SAN=se01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com</span></span></p>
<p><span data-ttu-id="87809-146">Como usar um certificado curinga:</span><span class="sxs-lookup"><span data-stu-id="87809-146">Using a wildcard certificate:</span></span></p>
<p><span data-ttu-id="87809-147">SN = SE01. contoso. com; SAN = SE01. contoso. com; SAN = \*. contoso. com</span><span class="sxs-lookup"><span data-stu-id="87809-147">SN=se01.contoso.com; SAN=se01.contoso.com; SAN=\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="87809-148">Não é possível substituir o FQDN interno da Web no construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="87809-148">You cannot override the Internal web FQDN in Topology Builder.</span></span></p>
<p><span data-ttu-id="87809-149">Se possuir vários Atender a URLs simples, devem-se incluir todos eles como nomes alternativos de entidade.</span><span class="sxs-lookup"><span data-stu-id="87809-149">If you have multiple Meet simple URLs, you must include all of them as subject alternative names.</span></span></p>
<p><span data-ttu-id="87809-150">As entradas curinga são suportadas pelas entradas de URL simples.</span><span class="sxs-lookup"><span data-stu-id="87809-150">Wildcard entries are supported for the simple URL entries.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="87809-151">Web externa</span><span class="sxs-lookup"><span data-stu-id="87809-151">Web external</span></span></p></td>
<td><p><span data-ttu-id="87809-152">FQDN do servidor</span><span class="sxs-lookup"><span data-stu-id="87809-152">FQDN of the server</span></span></p></td>
<td><p><span data-ttu-id="87809-153">Cada um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="87809-153">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="87809-154">FQDN da web externa</span><span class="sxs-lookup"><span data-stu-id="87809-154">External web FQDN</span></span></p></li>
<li><p><span data-ttu-id="87809-155">Discar URL simples</span><span class="sxs-lookup"><span data-stu-id="87809-155">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="87809-156">Atender URLs simples por domínio SIP</span><span class="sxs-lookup"><span data-stu-id="87809-156">Meet simple URLs per SIP domain</span></span></p></li>
<li><p><span data-ttu-id="87809-157">Ou uma entrada curinga para os URLs simples</span><span class="sxs-lookup"><span data-stu-id="87809-157">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="87809-158">SN = SE01. contoso. com; SAN = webcon01. contoso. com; SAN = reunião. contoso. com; SAN = atender. fabrikam. com; SAN = dialem. contoso. com</span><span class="sxs-lookup"><span data-stu-id="87809-158">SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</span></span></p>
<p><span data-ttu-id="87809-159">Como usar um certificado coringa:</span><span class="sxs-lookup"><span data-stu-id="87809-159">Using a wildcard certificate:</span></span></p>
<p><span data-ttu-id="87809-160">SN = SE01. contoso. com; SAN = webcon01. contoso. com; SAN = \*. contoso. com</span><span class="sxs-lookup"><span data-stu-id="87809-160">SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN=\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="87809-161">Se possuir vários Atender a URLs simples, devem-se incluir todos eles como nomes alternativos de entidade.</span><span class="sxs-lookup"><span data-stu-id="87809-161">If you have multiple Meet simple URLs, you must include all of them as subject alternative names.</span></span></p>
<p><span data-ttu-id="87809-162">As entradas curinga são suportadas pelas entradas de URL simples.</span><span class="sxs-lookup"><span data-stu-id="87809-162">Wildcard entries are supported for the simple URL entries.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-front-end-server-in-a-front-end-pool"></a><span data-ttu-id="87809-163">Certificados de servidor Front-End eu um pool de Front-Ends</span><span class="sxs-lookup"><span data-stu-id="87809-163">Certificates for Front End Server in a Front End Pool</span></span>

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
<th><span data-ttu-id="87809-164">Certificado</span><span class="sxs-lookup"><span data-stu-id="87809-164">Certificate</span></span></th>
<th><span data-ttu-id="87809-165">Nome da entidade/nome comum</span><span class="sxs-lookup"><span data-stu-id="87809-165">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="87809-166">Nome da entidade alternativo</span><span class="sxs-lookup"><span data-stu-id="87809-166">Subject alternative name</span></span></th>
<th><span data-ttu-id="87809-167">Exemplo</span><span class="sxs-lookup"><span data-stu-id="87809-167">Example</span></span></th>
<th><span data-ttu-id="87809-168">Comentários</span><span class="sxs-lookup"><span data-stu-id="87809-168">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="87809-169">Padrão</span><span class="sxs-lookup"><span data-stu-id="87809-169">Default</span></span></p></td>
<td><p><span data-ttu-id="87809-170">FQDN do pool</span><span class="sxs-lookup"><span data-stu-id="87809-170">FQDN of the pool</span></span></p></td>
<td><p><span data-ttu-id="87809-171">FQDN do pool e FQDN do servidor.</span><span class="sxs-lookup"><span data-stu-id="87809-171">FQDN of the pool and FQDN of the server.</span></span></p>
<p><span data-ttu-id="87809-172">Se você tiver vários domínios SIP e tiver habilitado a configuração automática do cliente, o assistente de certificados detectará e adicionará os FQDNs de cada domínio SIP aceito.</span><span class="sxs-lookup"><span data-stu-id="87809-172">If you have multiple SIP domains and have enabled automatic client configuration, the certificate wizard detects and adds each supported SIP domain FQDNs.</span></span></p>
<p><span data-ttu-id="87809-173">Se esse pool é o servidor de logon automático para clientes, e a combinação estrita do DNS é exigida na política do grupo, também é preciso de entradas para o sip.sipdomain (para cada domínio de SIP que você tiver).</span><span class="sxs-lookup"><span data-stu-id="87809-173">If this pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need entries for sip.sipdomain (for each SIP domain you have).</span></span></p></td>
<td><p><span data-ttu-id="87809-174">SN = EEpool. contoso. com; SAN = EEpool. contoso. com; SAN = ee01. contoso. com</span><span class="sxs-lookup"><span data-stu-id="87809-174">SN=eepool.contoso.com; SAN=eepool.contoso.com; SAN=ee01.contoso.com</span></span></p>
<p><span data-ttu-id="87809-175">Se esse pool é o servidor de logon automático para clientes, e se a combinação estrita de DNS for exigida na política do grupo, também serão precisos: SAN=sip.contoso.com; SAN=sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="87809-175">If this pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need SAN=sip.contoso.com; SAN=sip.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="87809-176">O assistente detecta quaisquer domínios SIP especificados durante a instalação e os adiciona automaticamente ao nome alternativo para a entidade.</span><span class="sxs-lookup"><span data-stu-id="87809-176">The wizard detects any SIP domains you specified during setup and automatically adds them to the subject alternative name.</span></span></p>
<p><span data-ttu-id="87809-177">Você também pode usar esse certificado para autenticação de servidor para servidor.</span><span class="sxs-lookup"><span data-stu-id="87809-177">You can also use this certificate for Server-to-Server Authentication.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="87809-178">Web interna</span><span class="sxs-lookup"><span data-stu-id="87809-178">Web Internal</span></span></p></td>
<td><p><span data-ttu-id="87809-179">FQDN do pool</span><span class="sxs-lookup"><span data-stu-id="87809-179">FQDN of the pool</span></span></p></td>
<td><p><span data-ttu-id="87809-180">Cada um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="87809-180">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="87809-181">FQDN da Web interna (que não é o mesmo que o FQDN do servidor)</span><span class="sxs-lookup"><span data-stu-id="87809-181">Internal web FQDN (which is NOT the same as the FQDN of the server)</span></span></p></li>
<li><p><span data-ttu-id="87809-182">FQDN do servidor</span><span class="sxs-lookup"><span data-stu-id="87809-182">Server FQDN</span></span></p></li>
<li><p><span data-ttu-id="87809-183">FQDN do pool do Lync</span><span class="sxs-lookup"><span data-stu-id="87809-183">Lync pool FQDN</span></span></p></li>
<li><p><span data-ttu-id="87809-184">Atender a URLs simples</span><span class="sxs-lookup"><span data-stu-id="87809-184">Meet simple URLs</span></span></p></li>
<li><p><span data-ttu-id="87809-185">Discar URL simples</span><span class="sxs-lookup"><span data-stu-id="87809-185">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="87809-186">Administrar URL simples</span><span class="sxs-lookup"><span data-stu-id="87809-186">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="87809-187">Ou, uma entrada curinga para os URLs simples</span><span class="sxs-lookup"><span data-stu-id="87809-187">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="87809-188">SN = ee01. contoso. com; SAN = ee01. contoso. com; SAN = reunião. contoso. com; SAN = atender. fabrikam. com; SAN = dialem. contoso. com; SAN = admin. contoso. com</span><span class="sxs-lookup"><span data-stu-id="87809-188">SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com</span></span></p>
<p><span data-ttu-id="87809-189">Como usar um certificado curinga:</span><span class="sxs-lookup"><span data-stu-id="87809-189">Using a wildcard certificate:</span></span></p>
<p><span data-ttu-id="87809-190">SN = ee01. contoso. com; SAN = ee01. contoso. com; SAN = \*. contoso. com</span><span class="sxs-lookup"><span data-stu-id="87809-190">SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN=\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="87809-191">Se possuir vários Atender a URLs simples, devem-se incluir todos eles como nomes alternativos de entidade.</span><span class="sxs-lookup"><span data-stu-id="87809-191">If you have multiple Meet simple URLs, you must include all of them as subject alternative names.</span></span></p>
<p><span data-ttu-id="87809-192">As entradas curinga são suportadas pelas entradas de URL simples.</span><span class="sxs-lookup"><span data-stu-id="87809-192">Wildcard entries are supported for the simple URL entries.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="87809-193">Web externa</span><span class="sxs-lookup"><span data-stu-id="87809-193">Web external</span></span></p></td>
<td><p><span data-ttu-id="87809-194">FQDN do pool</span><span class="sxs-lookup"><span data-stu-id="87809-194">FQDN of the pool</span></span></p></td>
<td><p><span data-ttu-id="87809-195">Cada um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="87809-195">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="87809-196">FQDN da web externa</span><span class="sxs-lookup"><span data-stu-id="87809-196">External web FQDN</span></span></p></li>
<li><p><span data-ttu-id="87809-197">Discar URL simples</span><span class="sxs-lookup"><span data-stu-id="87809-197">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="87809-198">Administrar URL simples</span><span class="sxs-lookup"><span data-stu-id="87809-198">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="87809-199">Ou, uma entrada curinga para os URLs simples</span><span class="sxs-lookup"><span data-stu-id="87809-199">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="87809-200">SN = ee01. contoso. com; SAN = webcon01. contoso. com; SAN = reunião. contoso. com; SAN = atender. fabrikam. com; SAN = dialem. contoso. com</span><span class="sxs-lookup"><span data-stu-id="87809-200">SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</span></span></p>
<p><span data-ttu-id="87809-201">Como usar um certificado curinga:</span><span class="sxs-lookup"><span data-stu-id="87809-201">Using a wildcard certificate:</span></span></p>
<p><span data-ttu-id="87809-202">SN = ee01. contoso. com; SAN = webcon01. contoso. com; SAN = \*. contoso. com</span><span class="sxs-lookup"><span data-stu-id="87809-202">SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN=\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="87809-203">Se possuir vários Atender a URLs simples, devem-se incluir todos eles como nomes alternativos de entidade.</span><span class="sxs-lookup"><span data-stu-id="87809-203">If you have multiple Meet simple URLs, you must include all of them as subject alternative names.</span></span></p>
<p><span data-ttu-id="87809-204">As entradas curinga são suportadas pelas entradas de URL simples.</span><span class="sxs-lookup"><span data-stu-id="87809-204">Wildcard entries are supported for the simple URL entries.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-director"></a><span data-ttu-id="87809-205">Certificados do diretor</span><span class="sxs-lookup"><span data-stu-id="87809-205">Certificates for Director</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="87809-206">Certificado</span><span class="sxs-lookup"><span data-stu-id="87809-206">Certificate</span></span></th>
<th><span data-ttu-id="87809-207">Nome da entidade/nome comum</span><span class="sxs-lookup"><span data-stu-id="87809-207">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="87809-208">Nome da entidade alternativo</span><span class="sxs-lookup"><span data-stu-id="87809-208">Subject alternative name</span></span></th>
<th><span data-ttu-id="87809-209">Exemplo</span><span class="sxs-lookup"><span data-stu-id="87809-209">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="87809-210">Padrão</span><span class="sxs-lookup"><span data-stu-id="87809-210">Default</span></span></p></td>
<td><p><span data-ttu-id="87809-211">FQDN do pool de Diretores</span><span class="sxs-lookup"><span data-stu-id="87809-211">FQDN of the Director pool</span></span></p></td>
<td><p><span data-ttu-id="87809-212">FQDN do Diretor, FQDN do pool de Diretores</span><span class="sxs-lookup"><span data-stu-id="87809-212">FQDN of the Director, FQDN of the Director pool</span></span></p>
<p><span data-ttu-id="87809-213">Se esse pool for o servidor de logon automático para clientes, e a combinação estrita do DNS é exigida na política do grupo, também é preciso de entradas para o sip.sipdomain (para cada domínio de SIP que você tiver).</span><span class="sxs-lookup"><span data-stu-id="87809-213">If this pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need entries for sip.sipdomain (for each SIP domain you have).</span></span></p></td>
<td><p><span data-ttu-id="87809-214">SN = dir-pool.contoso.com; SAN = dir-pool.contoso.com; SAN = dir01. contoso. com</span><span class="sxs-lookup"><span data-stu-id="87809-214">SN=dir-pool.contoso.com; SAN=dir-pool.contoso.com; SAN=dir01.contoso.com</span></span></p>
<p><span data-ttu-id="87809-215">Se esse pool de Diretor for o servidor de logon automático para clientes, e se a combinação estrita de DNS for exigida na política do grupo, também serão precisos: SAN=sip.contoso.com; SAN=sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="87809-215">If this Director pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need SAN=sip.contoso.com; SAN=sip.fabrikam.com</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="87809-216">Web interna</span><span class="sxs-lookup"><span data-stu-id="87809-216">Web Internal</span></span></p></td>
<td><p><span data-ttu-id="87809-217">FQDN do servidor</span><span class="sxs-lookup"><span data-stu-id="87809-217">FQDN of the server</span></span></p></td>
<td><p><span data-ttu-id="87809-218">Cada um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="87809-218">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="87809-219">FQDN de web interna (que é o mesmo que o FQDN do servidor)</span><span class="sxs-lookup"><span data-stu-id="87809-219">Internal web FQDN (which is the same as the FQDN of the server)</span></span></p></li>
<li><p><span data-ttu-id="87809-220">FQDN do servidor</span><span class="sxs-lookup"><span data-stu-id="87809-220">Server FQDN</span></span></p></li>
<li><p><span data-ttu-id="87809-221">FQDN do pool do Lync</span><span class="sxs-lookup"><span data-stu-id="87809-221">Lync pool FQDN</span></span></p></li>
<li><p><span data-ttu-id="87809-222">Atender a URLs simples</span><span class="sxs-lookup"><span data-stu-id="87809-222">Meet simple URLs</span></span></p></li>
<li><p><span data-ttu-id="87809-223">Discar URL simples</span><span class="sxs-lookup"><span data-stu-id="87809-223">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="87809-224">Administrar URL simples</span><span class="sxs-lookup"><span data-stu-id="87809-224">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="87809-225">Ou, uma entrada curinga para os URLs simples</span><span class="sxs-lookup"><span data-stu-id="87809-225">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="87809-226">SN = dir01. contoso. com; SAN = dir01. contoso. com; SAN = reunião. contoso. com; SAN = atender. fabrikam. com; SAN = dialem. contoso. com; SAN = admin. contoso. com</span><span class="sxs-lookup"><span data-stu-id="87809-226">SN=dir01.contoso.com; SAN=dir01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com</span></span></p>
<p><span data-ttu-id="87809-227">SN = dir01. contoso. com; SAN = dir01. contoso. com SAN = \*. contoso. com</span><span class="sxs-lookup"><span data-stu-id="87809-227">SN=dir01.contoso.com; SAN=dir01.contoso.com SAN=\*.contoso.com</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="87809-228">Web externa</span><span class="sxs-lookup"><span data-stu-id="87809-228">Web external</span></span></p></td>
<td><p><span data-ttu-id="87809-229">FQDN do servidor</span><span class="sxs-lookup"><span data-stu-id="87809-229">FQDN of the server</span></span></p></td>
<td><p><span data-ttu-id="87809-230">Cada um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="87809-230">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="87809-231">FQDN da web externa</span><span class="sxs-lookup"><span data-stu-id="87809-231">External web FQDN</span></span></p></li>
<li><p><span data-ttu-id="87809-232">Discar URL simples</span><span class="sxs-lookup"><span data-stu-id="87809-232">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="87809-233">Administrar URL simples</span><span class="sxs-lookup"><span data-stu-id="87809-233">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="87809-234">Ou, uma entrada curinga para os URLs simples</span><span class="sxs-lookup"><span data-stu-id="87809-234">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="87809-235">O FQDN da Web externa do diretor deve ser diferente do pool de front-ends ou servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="87809-235">The Director external web FQDN must be different from the Front End pool or Front End Server.</span></span></p>
<p><span data-ttu-id="87809-236">SN = dir01. contoso. com; SAN = directorwebcon01. contoso. com SAN = encontro. contoso. com; SAN = atender. fabrikam. com; SAN = dialem. contoso. com</span><span class="sxs-lookup"><span data-stu-id="87809-236">SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</span></span></p>
<p><span data-ttu-id="87809-237">SN = dir01. contoso. com; SAN = directorwebcon01. contoso. com SAN = \*. contoso. com</span><span class="sxs-lookup"><span data-stu-id="87809-237">SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN=\*.contoso.com</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="87809-p107">Se possuir um pool do Servidor de Mediação autônomo, os servidores presentes em cada um precisam dos certificados listados na tabela a seguir. Se um Servidor de Mediação for colocado junto aos Servidores Front-End, são suficientes os certificados listados na tabela “Certificados para Servidor Front-End no Pool do Front-End”, já apresentada neste tópico.</span><span class="sxs-lookup"><span data-stu-id="87809-p107">If you have a stand-alone Mediation Server pool, the Mediation Servers in it each need the certificates listed in the following table. If you collocate Mediation Server with the Front End Servers, the certificates listed in the “Certificates for Front End Server in Front End Pool” table earlier in this topic are sufficient.</span></span>

### <a name="certificates-for-stand-alone-mediation-server"></a><span data-ttu-id="87809-240">Certificados para um Servidor de Mediação Autônomo</span><span class="sxs-lookup"><span data-stu-id="87809-240">Certificates for Stand-alone Mediation Server</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="87809-241">Certificado</span><span class="sxs-lookup"><span data-stu-id="87809-241">Certificate</span></span></th>
<th><span data-ttu-id="87809-242">Nome da entidade/nome comum</span><span class="sxs-lookup"><span data-stu-id="87809-242">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="87809-243">Nome da entidade alternativo</span><span class="sxs-lookup"><span data-stu-id="87809-243">Subject alternative name</span></span></th>
<th><span data-ttu-id="87809-244">Exemplo</span><span class="sxs-lookup"><span data-stu-id="87809-244">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="87809-245">Padrão</span><span class="sxs-lookup"><span data-stu-id="87809-245">Default</span></span></p></td>
<td><p><span data-ttu-id="87809-246">FQDN do pool</span><span class="sxs-lookup"><span data-stu-id="87809-246">FQDN of the pool</span></span></p></td>
<td><p><span data-ttu-id="87809-247">FQDN do pool</span><span class="sxs-lookup"><span data-stu-id="87809-247">FQDN of the pool</span></span></p>
<p><span data-ttu-id="87809-248">FQDN do servidor membro do pool</span><span class="sxs-lookup"><span data-stu-id="87809-248">FQDN of pool member server</span></span></p></td>
<td><p><span data-ttu-id="87809-249">SN = medsvr-pool.contoso.net; SAN = medsvr-pool.contoso.net; SAN = medsvr01. contoso. net</span><span class="sxs-lookup"><span data-stu-id="87809-249">SN=medsvr-pool.contoso.net; SAN=medsvr-pool.contoso.net; SAN=medsvr01.contoso.net</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-survivable-branch-appliance"></a><span data-ttu-id="87809-250">Certificados para Aparelho de Filial Persistente</span><span class="sxs-lookup"><span data-stu-id="87809-250">Certificates for Survivable Branch Appliance</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="87809-251">Certificado</span><span class="sxs-lookup"><span data-stu-id="87809-251">Certificate</span></span></th>
<th><span data-ttu-id="87809-252">Nome da entidade/nome comum</span><span class="sxs-lookup"><span data-stu-id="87809-252">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="87809-253">Nome da entidade alternativo</span><span class="sxs-lookup"><span data-stu-id="87809-253">Subject alternative name</span></span></th>
<th><span data-ttu-id="87809-254">Exemplo</span><span class="sxs-lookup"><span data-stu-id="87809-254">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="87809-255">Padrão</span><span class="sxs-lookup"><span data-stu-id="87809-255">Default</span></span></p></td>
<td><p><span data-ttu-id="87809-256">FQDN do aplicativo</span><span class="sxs-lookup"><span data-stu-id="87809-256">FQDN of the appliance</span></span></p></td>
<td><p><span data-ttu-id="87809-257">SIP. &lt;sipdomain&gt; (precisa de uma entrada por domínio SIP)</span><span class="sxs-lookup"><span data-stu-id="87809-257">SIP.&lt;sipdomain&gt; (need one entry per SIP domain)</span></span></p></td>
<td><p><span data-ttu-id="87809-258">SN = sba01. contoso. net; SAN = SIP. contoso. com; SAN = SIP. fabrikam. com</span><span class="sxs-lookup"><span data-stu-id="87809-258">SN=sba01.contoso.net; SAN=sip.contoso.com; SAN=sip.fabrikam.com</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="87809-259">Confira também</span><span class="sxs-lookup"><span data-stu-id="87809-259">See Also</span></span>


[<span data-ttu-id="87809-260">Suporte a certificados curinga no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="87809-260">Wildcard certificate support in Lync Server 2013</span></span>](lync-server-2013-wildcard-certificate-support.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

