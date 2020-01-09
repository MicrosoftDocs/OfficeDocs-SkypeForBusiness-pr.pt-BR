---
title: 'Lync Server 2013: Configuração de IIS'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: IIS configuration
ms:assetid: b458babf-bf64-43f0-8a8e-612f5096b63c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412871(v=OCS.15)
ms:contentKeyID: 48185169
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 29b9803fdb6c4a048fdf072b5ba2e5722b863640
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992096"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="iis-configuration-in-lync-server-2013"></a><span data-ttu-id="d843b-102">Configuração de IIS no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d843b-102">IIS configuration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d843b-103">_**Tópico da última modificação:** 2014-02-17_</span><span class="sxs-lookup"><span data-stu-id="d843b-103">_**Topic Last Modified:** 2014-02-17_</span></span>

<span data-ttu-id="d843b-104">Para concluir esse procedimento com êxito, você deve estar conectado ao servidor minimamente como um administrador local e um usuário do domínio.</span><span class="sxs-lookup"><span data-stu-id="d843b-104">To successfully complete this procedure, you should be logged on to the server minimally as a local administrator and a domain user.</span></span>

<span data-ttu-id="d843b-105">Antes de configurar e instalar o servidor front-end para o Lync Server 2013, Standard Edition ou o primeiro servidor front-end em um pool, instale e configure a função do servidor e os serviços Web para serviços de informações da Internet (IIS).</span><span class="sxs-lookup"><span data-stu-id="d843b-105">Before you configure and install the Front End Server for Lync Server 2013, Standard Edition or the first Front End Server in a pool, you install and configure the server role and Web Services for Internet Information Services (IIS).</span></span>

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="d843b-106">Se a sua organização exigir que você localize o IIS e todos os serviços Web em uma unidade diferente da unidade do sistema, você poderá alterar o caminho do local de instalação dos arquivos do Lync Server 2013 na caixa de diálogo Configurar ao instalar inicialmente o Lync Server 2013 Ferramentas administrativas.</span><span class="sxs-lookup"><span data-stu-id="d843b-106">If your organization requires that you locate IIS and all Web Services on a drive other than the system drive, you can change the installation location path for the Lync Server 2013 files in the Setup dialog box when you initially install the Lync Server 2013 Administrative tools.</span></span> <span data-ttu-id="d843b-107">Instale as ferramentas administrativas antes de instalar o IIS.</span><span class="sxs-lookup"><span data-stu-id="d843b-107">You install the Administrative tools before installing IIS.</span></span> <span data-ttu-id="d843b-108">Se você instalar os arquivos de instalação nesse caminho, incluindo OCSCore. msi, o restante dos arquivos do Lync Server 2013 também será implantado nessa unidade.</span><span class="sxs-lookup"><span data-stu-id="d843b-108">If you install the Setup files to this path, including OCSCore.msi, the rest of the Lync Server 2013 files will be deployed to this drive as well.</span></span> <span data-ttu-id="d843b-109">Para o dtails, confira <A href="lync-server-2013-install-lync-server-administrative-tools.md">instalar as ferramentas administrativas do Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="d843b-109">For dtails, see <A href="lync-server-2013-install-lync-server-administrative-tools.md">Install Lync Server 2013 administrative tools</A>.</span></span> <span data-ttu-id="d843b-110">Para obter detalhes sobre como realocar o INETPUB implantado pelo Windows Server Manager ao instalar <A href="http://go.microsoft.com/fwlink/p/?linkid=216888">http://go.microsoft.com/fwlink/p/?linkId=216888</A>o IIS, consulte.</span><span class="sxs-lookup"><span data-stu-id="d843b-110">For details about how to relocate the INETPUB deployed by Windows Server Manager when installing IIS, see <A href="http://go.microsoft.com/fwlink/p/?linkid=216888">http://go.microsoft.com/fwlink/p/?linkId=216888</A>.</span></span>



</div>

<span data-ttu-id="d843b-111">A tabela a seguir indica os serviços de função do IIS 7,5 necessários.</span><span class="sxs-lookup"><span data-stu-id="d843b-111">The following table indicates the required IIS 7.5 role services.</span></span>

### <a name="iis-75-role-services"></a><span data-ttu-id="d843b-112">Serviços de função do IIS 7,5</span><span class="sxs-lookup"><span data-stu-id="d843b-112">IIS 7.5 Role Services</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d843b-113">Título da função</span><span class="sxs-lookup"><span data-stu-id="d843b-113">Role Heading</span></span></th>
<th><span data-ttu-id="d843b-114">Serviço de função</span><span class="sxs-lookup"><span data-stu-id="d843b-114">Role Service</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d843b-115">Recursos comuns de HTTP instalados</span><span class="sxs-lookup"><span data-stu-id="d843b-115">Common HTTP features installed</span></span></p></td>
<td><p><span data-ttu-id="d843b-116">Conteúdo estático</span><span class="sxs-lookup"><span data-stu-id="d843b-116">Static content</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d843b-117">Recursos comuns de HTTP instalados</span><span class="sxs-lookup"><span data-stu-id="d843b-117">Common HTTP features installed</span></span></p></td>
<td><p><span data-ttu-id="d843b-118">Documento padrão</span><span class="sxs-lookup"><span data-stu-id="d843b-118">Default document</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d843b-119">Recursos comuns de HTTP instalados</span><span class="sxs-lookup"><span data-stu-id="d843b-119">Common HTTP features installed</span></span></p></td>
<td><p><span data-ttu-id="d843b-120">Erros de HTTP</span><span class="sxs-lookup"><span data-stu-id="d843b-120">HTTP errors</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d843b-121">Desenvolvimento de aplicativos</span><span class="sxs-lookup"><span data-stu-id="d843b-121">Application development</span></span></p></td>
<td><p><span data-ttu-id="d843b-122">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="d843b-122">ASP.NET</span></span></p>
<p><span data-ttu-id="d843b-123">O Windows Server 2012 também requer o ASP. NET 4.5</span><span class="sxs-lookup"><span data-stu-id="d843b-123">Windows Server 2012 also requires ASP.NET4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d843b-124">Desenvolvimento de aplicativos</span><span class="sxs-lookup"><span data-stu-id="d843b-124">Application development</span></span></p></td>
<td><p><span data-ttu-id="d843b-125">Extensibilidade .NET</span><span class="sxs-lookup"><span data-stu-id="d843b-125">.NET extensibility</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d843b-126">Desenvolvimento de aplicativos</span><span class="sxs-lookup"><span data-stu-id="d843b-126">Application development</span></span></p></td>
<td><p><span data-ttu-id="d843b-127">Extensões da API de servidor da Internet (ISAPI)</span><span class="sxs-lookup"><span data-stu-id="d843b-127">Internet Server API (ISAPI) extensions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d843b-128">Desenvolvimento de aplicativos</span><span class="sxs-lookup"><span data-stu-id="d843b-128">Application development</span></span></p></td>
<td><p><span data-ttu-id="d843b-129">Filtros ISAPI</span><span class="sxs-lookup"><span data-stu-id="d843b-129">ISAPI filters</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d843b-130">Integridade e diagnóstico</span><span class="sxs-lookup"><span data-stu-id="d843b-130">Health and diagnostics</span></span></p></td>
<td><p><span data-ttu-id="d843b-131">Log HTTP</span><span class="sxs-lookup"><span data-stu-id="d843b-131">HTTP logging</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d843b-132">Integridade e diagnóstico</span><span class="sxs-lookup"><span data-stu-id="d843b-132">Health and diagnostics</span></span></p></td>
<td><p><span data-ttu-id="d843b-133">Ferramentas de log</span><span class="sxs-lookup"><span data-stu-id="d843b-133">Logging tools</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d843b-134">Integridade e diagnóstico</span><span class="sxs-lookup"><span data-stu-id="d843b-134">Health and diagnostics</span></span></p></td>
<td><p><span data-ttu-id="d843b-135">Rastreamento</span><span class="sxs-lookup"><span data-stu-id="d843b-135">Tracing</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d843b-136">Segurança</span><span class="sxs-lookup"><span data-stu-id="d843b-136">Security</span></span></p></td>
<td><p><span data-ttu-id="d843b-137">Autenticação anônima (instalada e habilitada por padrão)</span><span class="sxs-lookup"><span data-stu-id="d843b-137">Anonymous authentication (installed and enabled by default)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d843b-138">Segurança</span><span class="sxs-lookup"><span data-stu-id="d843b-138">Security</span></span></p></td>
<td><p><span data-ttu-id="d843b-139">Autenticação do Windows</span><span class="sxs-lookup"><span data-stu-id="d843b-139">Windows authentication</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d843b-140">Segurança</span><span class="sxs-lookup"><span data-stu-id="d843b-140">Security</span></span></p></td>
<td><p><span data-ttu-id="d843b-141">Autenticação de mapeamento de certificado do cliente</span><span class="sxs-lookup"><span data-stu-id="d843b-141">Client Certificate Mapping authentication</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d843b-142">Segurança</span><span class="sxs-lookup"><span data-stu-id="d843b-142">Security</span></span></p></td>
<td><p><span data-ttu-id="d843b-143">Filtragem de solicitações</span><span class="sxs-lookup"><span data-stu-id="d843b-143">Request filtering</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d843b-144">Desempenho</span><span class="sxs-lookup"><span data-stu-id="d843b-144">Performance</span></span></p></td>
<td><p><span data-ttu-id="d843b-145">Compactação de conteúdo estático</span><span class="sxs-lookup"><span data-stu-id="d843b-145">Static content compression</span></span></p>
<p><span data-ttu-id="d843b-146">Compactação de conteúdo dinâmico</span><span class="sxs-lookup"><span data-stu-id="d843b-146">Dynamic content compression</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d843b-147">Ferramentas de gerenciamento</span><span class="sxs-lookup"><span data-stu-id="d843b-147">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="d843b-148">Console de gerenciamento IIS</span><span class="sxs-lookup"><span data-stu-id="d843b-148">IIS Management Console</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d843b-149">Ferramentas de gerenciamento</span><span class="sxs-lookup"><span data-stu-id="d843b-149">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="d843b-150">Ferramentas e scripts de gerenciamento IIS</span><span class="sxs-lookup"><span data-stu-id="d843b-150">IIS Management Scripts and Tools</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="d843b-151">No sistema operacional Windows Server 2008 R2 SP1 x64, você pode usar o Windows PowerShell 2,0.</span><span class="sxs-lookup"><span data-stu-id="d843b-151">On the Windows Server 2008 R2 SP1 x64 operating system, you can use Windows PowerShell 2.0.</span></span> <span data-ttu-id="d843b-152">Primeiro, você deve importar o módulo ServerManager e instalar os serviços de função e função do IIS 7,5.</span><span class="sxs-lookup"><span data-stu-id="d843b-152">You must first import the ServerManager module, and then install the IIS 7.5 role and role services.</span></span>

   ```PowerShell
    Import-Module ServerManager
   ```

   ```PowerShell
    Add-WindowsFeature Web-Server, Web-Static-Content, Web-Default-Doc, Web-Scripting-Tools, Web-Windows-Auth, Web-Asp-Net, Web-Log-Libraries, Web-Http-Tracing, Web-Stat-Compression, Web-Dyn-Compression, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Errors, Web-Http-Logging, Web-Net-Ext, Web-Client-Auth, Web-Filtering, Web-Mgmt-Console
   ```

<div class=" ">


> [!NOTE]  
> <span data-ttu-id="d843b-153">A autenticação anônima é instalada por padrão com a função de servidor IIS.</span><span class="sxs-lookup"><span data-stu-id="d843b-153">Anonymous authentication is installed by default with the IIS server role.</span></span> <span data-ttu-id="d843b-154">Você pode gerenciar a autenticação anônima após a instalação do IIS.</span><span class="sxs-lookup"><span data-stu-id="d843b-154">You can manage anonymous authentication after the installation of IIS.</span></span> <span data-ttu-id="d843b-155">Para obter detalhes, consulte "habilitar autenticação anônima (IIS 7)" <A href="http://go.microsoft.com/fwlink/p/?linkid=203935">http://go.microsoft.com/fwlink/p/?linkId=203935</A>em.</span><span class="sxs-lookup"><span data-stu-id="d843b-155">For details, see “Enable Anonymous Authentication (IIS 7)” at <A href="http://go.microsoft.com/fwlink/p/?linkid=203935">http://go.microsoft.com/fwlink/p/?linkId=203935</A>.</span></span>



</div>

<span data-ttu-id="d843b-156">A tabela a seguir indica os serviços de função do IIS 8,0 e do IIS 8,5 necessários para o Windows Server 2012 e o Windows Server 2012 R2.</span><span class="sxs-lookup"><span data-stu-id="d843b-156">The following table indicates the required IIS 8.0 and IIS 8.5 role services for Windows Server 2012 and Windows Server 2012 R2.</span></span>

<div class=" ">


> [!NOTE]  
> <span data-ttu-id="d843b-157">Para o Windows Server 2012 e o Windows Server 2012 R2, o cmdlet Add-WindowsFeature foi substituído pelo cmdlet Install-WindowsFeature.</span><span class="sxs-lookup"><span data-stu-id="d843b-157">For Windows Server 2012 and Windows Server 2012 R2, the Add-WindowsFeature cmdlet has been replaced by the Install-WindowsFeature cmdlet.</span></span> <span data-ttu-id="d843b-158">Para obter detalhes, consulte <A href="http://go.microsoft.com/fwlink/p/?linkid=392274">install-WindowsFeature</A>.</span><span class="sxs-lookup"><span data-stu-id="d843b-158">For details, see <A href="http://go.microsoft.com/fwlink/p/?linkid=392274">Install-WindowsFeature</A>.</span></span>



</div>

### <a name="iis-80-and-iis-85-role-services"></a><span data-ttu-id="d843b-159">Serviços de função do IIS 8,0 e do IIS 8,5</span><span class="sxs-lookup"><span data-stu-id="d843b-159">IIS 8.0 and IIS 8.5 Role Services</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d843b-160">Título da função</span><span class="sxs-lookup"><span data-stu-id="d843b-160">Role Heading</span></span></th>
<th><span data-ttu-id="d843b-161">Serviço de função</span><span class="sxs-lookup"><span data-stu-id="d843b-161">Role Service</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d843b-162">Servidor Web (IIS)</span><span class="sxs-lookup"><span data-stu-id="d843b-162">Web Server (IIS)</span></span></p></td>
<td><p><span data-ttu-id="d843b-163">Servidor Web</span><span class="sxs-lookup"><span data-stu-id="d843b-163">Web Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d843b-164">Recursos HTTP Comuns</span><span class="sxs-lookup"><span data-stu-id="d843b-164">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="d843b-165">Documento padrão</span><span class="sxs-lookup"><span data-stu-id="d843b-165">Default Document</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d843b-166">Recursos HTTP Comuns</span><span class="sxs-lookup"><span data-stu-id="d843b-166">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="d843b-167">Pesquisa de diretório</span><span class="sxs-lookup"><span data-stu-id="d843b-167">Directory Browsing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d843b-168">Recursos HTTP Comuns</span><span class="sxs-lookup"><span data-stu-id="d843b-168">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="d843b-169">Erros HTTP</span><span class="sxs-lookup"><span data-stu-id="d843b-169">HTTP Errors</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d843b-170">Recursos HTTP Comuns</span><span class="sxs-lookup"><span data-stu-id="d843b-170">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="d843b-171">Conteúdo estático</span><span class="sxs-lookup"><span data-stu-id="d843b-171">Static content</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d843b-172">Recursos HTTP Comuns</span><span class="sxs-lookup"><span data-stu-id="d843b-172">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="d843b-173">Redirecionamento de HTTP</span><span class="sxs-lookup"><span data-stu-id="d843b-173">HTTP Redirection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d843b-174">Integridade e Diagnósticos</span><span class="sxs-lookup"><span data-stu-id="d843b-174">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="d843b-175">Log HTTP</span><span class="sxs-lookup"><span data-stu-id="d843b-175">HTTP Logging</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d843b-176">Integridade e Diagnósticos</span><span class="sxs-lookup"><span data-stu-id="d843b-176">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="d843b-177">Ferramentas de log</span><span class="sxs-lookup"><span data-stu-id="d843b-177">Logging Tools</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d843b-178">Integridade e Diagnósticos</span><span class="sxs-lookup"><span data-stu-id="d843b-178">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="d843b-179">Monitor de solicitação</span><span class="sxs-lookup"><span data-stu-id="d843b-179">Request Monitor</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d843b-180">Integridade e Diagnósticos</span><span class="sxs-lookup"><span data-stu-id="d843b-180">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="d843b-181">Rastreamento</span><span class="sxs-lookup"><span data-stu-id="d843b-181">Tracing</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d843b-182">Segurança</span><span class="sxs-lookup"><span data-stu-id="d843b-182">Security</span></span></p></td>
<td><p><span data-ttu-id="d843b-183">Requisição de filtro</span><span class="sxs-lookup"><span data-stu-id="d843b-183">Request Filtering</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d843b-184">Segurança</span><span class="sxs-lookup"><span data-stu-id="d843b-184">Security</span></span></p></td>
<td><p><span data-ttu-id="d843b-185">Autenticação básica</span><span class="sxs-lookup"><span data-stu-id="d843b-185">Basic Authentication</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d843b-186">Segurança</span><span class="sxs-lookup"><span data-stu-id="d843b-186">Security</span></span></p></td>
<td><p><span data-ttu-id="d843b-187">Autenticação de mapeamento de certificado de cliente</span><span class="sxs-lookup"><span data-stu-id="d843b-187">Client Certificate Mapping Authentication</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d843b-188">Segurança</span><span class="sxs-lookup"><span data-stu-id="d843b-188">Security</span></span></p></td>
<td><p><span data-ttu-id="d843b-189">Autenticação do Windows</span><span class="sxs-lookup"><span data-stu-id="d843b-189">Windows Authentication</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d843b-190">Desenvolvimento do aplicativo</span><span class="sxs-lookup"><span data-stu-id="d843b-190">Application Development</span></span></p></td>
<td><p><span data-ttu-id="d843b-191">.Net Extensibility 3,5</span><span class="sxs-lookup"><span data-stu-id="d843b-191">.Net Extensibility 3.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d843b-192">Desenvolvimento do aplicativo</span><span class="sxs-lookup"><span data-stu-id="d843b-192">Application Development</span></span></p></td>
<td><p><span data-ttu-id="d843b-193">.Net Extensibility 4,5</span><span class="sxs-lookup"><span data-stu-id="d843b-193">.Net Extensibility 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d843b-194">Desenvolvimento do aplicativo</span><span class="sxs-lookup"><span data-stu-id="d843b-194">Application Development</span></span></p></td>
<td><p><span data-ttu-id="d843b-195">ASP.Net 3,5</span><span class="sxs-lookup"><span data-stu-id="d843b-195">ASP.Net 3.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d843b-196">Desenvolvimento do aplicativo</span><span class="sxs-lookup"><span data-stu-id="d843b-196">Application Development</span></span></p></td>
<td><p><span data-ttu-id="d843b-197">ASP.Net 4,5</span><span class="sxs-lookup"><span data-stu-id="d843b-197">ASP.Net 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d843b-198">Desenvolvimento do aplicativo</span><span class="sxs-lookup"><span data-stu-id="d843b-198">Application Development</span></span></p></td>
<td><p><span data-ttu-id="d843b-199">Extensões ISAPI</span><span class="sxs-lookup"><span data-stu-id="d843b-199">ISAPI Extensions</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d843b-200">Desenvolvimento do aplicativo</span><span class="sxs-lookup"><span data-stu-id="d843b-200">Application Development</span></span></p></td>
<td><p><span data-ttu-id="d843b-201">Filtros ISAPI</span><span class="sxs-lookup"><span data-stu-id="d843b-201">ISAPI Filters</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d843b-202">Desenvolvimento do aplicativo</span><span class="sxs-lookup"><span data-stu-id="d843b-202">Application Development</span></span></p></td>
<td><p><span data-ttu-id="d843b-203">Inclusões do lado do servidor</span><span class="sxs-lookup"><span data-stu-id="d843b-203">Server Side Includes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d843b-204">Ferramentas de gerenciamento</span><span class="sxs-lookup"><span data-stu-id="d843b-204">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="d843b-205">Console de gerenciamento IIS</span><span class="sxs-lookup"><span data-stu-id="d843b-205">IIS Management Console</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d843b-206">Ferramentas de gerenciamento</span><span class="sxs-lookup"><span data-stu-id="d843b-206">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="d843b-207">Compatibilidade de metabase do IIS 6</span><span class="sxs-lookup"><span data-stu-id="d843b-207">IIS 6 Metabase compatibility</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d843b-208">Ferramentas de gerenciamento</span><span class="sxs-lookup"><span data-stu-id="d843b-208">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="d843b-209">Ferramentas e scripts de gerenciamento IIS</span><span class="sxs-lookup"><span data-stu-id="d843b-209">IIS Management Scripts and Tools</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d843b-210">Recursos da .net 3,5 Framework</span><span class="sxs-lookup"><span data-stu-id="d843b-210">.Net 3.5 Framework Features</span></span></p></td>
<td><p><span data-ttu-id="d843b-211">.Net 3,5 Framework</span><span class="sxs-lookup"><span data-stu-id="d843b-211">.Net 3.5 Framework</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d843b-212">Recursos da .NET 4,5 Framework</span><span class="sxs-lookup"><span data-stu-id="d843b-212">.Net 4.5 Framework Features</span></span></p></td>
<td><p><span data-ttu-id="d843b-213">.NET Framework 4,5</span><span class="sxs-lookup"><span data-stu-id="d843b-213">.Net Framework 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d843b-214">Recursos da .NET 4,5 Framework</span><span class="sxs-lookup"><span data-stu-id="d843b-214">.Net 4.5 Framework Features</span></span></p></td>
<td><p><span data-ttu-id="d843b-215">ASP.Net 4,5</span><span class="sxs-lookup"><span data-stu-id="d843b-215">ASP.Net 4.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d843b-216">Recursos da .NET 4,5 Framework</span><span class="sxs-lookup"><span data-stu-id="d843b-216">.Net 4.5 Framework Features</span></span></p></td>
<td><p><span data-ttu-id="d843b-217">Ativação HTTP</span><span class="sxs-lookup"><span data-stu-id="d843b-217">HTTP Activation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d843b-218">Recursos da .NET 4,5 Framework</span><span class="sxs-lookup"><span data-stu-id="d843b-218">.Net 4.5 Framework Features</span></span></p></td>
<td><p><span data-ttu-id="d843b-219">Compartilhamento de porta TCP</span><span class="sxs-lookup"><span data-stu-id="d843b-219">TCP Port Sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d843b-220">Serviço de transferência inteligente em segundo plano</span><span class="sxs-lookup"><span data-stu-id="d843b-220">Background Intelligent Transfer Service</span></span></p></td>
<td><p><span data-ttu-id="d843b-221">Extensões de servidor IIS</span><span class="sxs-lookup"><span data-stu-id="d843b-221">IIS Server Extensions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d843b-222">Serviços de tinta e manuscrito</span><span class="sxs-lookup"><span data-stu-id="d843b-222">Ink and Handwriting Services</span></span></p></td>
<td><p><span data-ttu-id="d843b-223">Serviços de tinta e manuscrito</span><span class="sxs-lookup"><span data-stu-id="d843b-223">Ink and Handwriting Services</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d843b-224">Media Foundation</span><span class="sxs-lookup"><span data-stu-id="d843b-224">Media Foundation</span></span></p></td>
<td><p><span data-ttu-id="d843b-225">Media Foundation</span><span class="sxs-lookup"><span data-stu-id="d843b-225">Media Foundation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d843b-226">Interfaces do usuário e infraestrutura</span><span class="sxs-lookup"><span data-stu-id="d843b-226">User Interfaces and Infrastructure</span></span></p></td>
<td><p><span data-ttu-id="d843b-227">Infraestrutura e ferramentas de gerenciamento gráfico</span><span class="sxs-lookup"><span data-stu-id="d843b-227">Graphical Management Tools and Infrastructure</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d843b-228">Interfaces do usuário e infraestrutura</span><span class="sxs-lookup"><span data-stu-id="d843b-228">User Interfaces and Infrastructure</span></span></p></td>
<td><p><span data-ttu-id="d843b-229">Experiência Desktop</span><span class="sxs-lookup"><span data-stu-id="d843b-229">Desktop Experience</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d843b-230">Interfaces do usuário e infraestrutura</span><span class="sxs-lookup"><span data-stu-id="d843b-230">User Interfaces and Infrastructure</span></span></p></td>
<td><p><span data-ttu-id="d843b-231">Shell gráfico do servidor</span><span class="sxs-lookup"><span data-stu-id="d843b-231">Server Graphical Shell</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d843b-232">Windows Identity Foundation 3.5</span><span class="sxs-lookup"><span data-stu-id="d843b-232">Windows Identity Foundation 3.5</span></span></p></td>
<td><p><span data-ttu-id="d843b-233">Windows Identity Foundation 3.5</span><span class="sxs-lookup"><span data-stu-id="d843b-233">Windows Identity Foundation 3.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d843b-234">Serviço de ativação de processos do Windows</span><span class="sxs-lookup"><span data-stu-id="d843b-234">Windows Process Activation Service</span></span></p></td>
<td><p><span data-ttu-id="d843b-235">Modelo de processo</span><span class="sxs-lookup"><span data-stu-id="d843b-235">Process Model</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d843b-236">Serviço de ativação de processos do Windows</span><span class="sxs-lookup"><span data-stu-id="d843b-236">Windows Process Activation Service</span></span></p></td>
<td><p><span data-ttu-id="d843b-237">APIs de configuração</span><span class="sxs-lookup"><span data-stu-id="d843b-237">Configuration APIs</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="d843b-238">No Windows Server 2012 e no Windows Server 2012 R2, você pode usar o Windows PowerShell 3,0 para instalar os requisitos do IIS.</span><span class="sxs-lookup"><span data-stu-id="d843b-238">In Windows Server 2012 and Windows Server 2012 R2, you can use Windows PowerShell 3.0 to install the IIS Requirements.</span></span> <span data-ttu-id="d843b-239">Usando o módulo ServerManager no Windows PowerShell 3,0, digite:</span><span class="sxs-lookup"><span data-stu-id="d843b-239">Using the ServerManager module in Windows PowerShell 3.0, type:</span></span>

   ```PowerShell
    Import-Module ServerManager
   ```

   ```PowerShell
    Add-WindowsFeature Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-Framework-45-Core, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Console, Web-Mgmt-Compat, Windows-Identity-Foundation, Server-Media-Foundation, BITS -Source D:\sources\sxs
   ```

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="d843b-240">Novo com o Windows Server 2012 é o parâmetro-source que define onde a mídia de origem do Windows Server 2012 pode ser encontrada.</span><span class="sxs-lookup"><span data-stu-id="d843b-240">New with Windows Server 2012 is the –Source parameter that defines where the Windows Server 2012 source media can be found.</span></span> <span data-ttu-id="d843b-241">A mídia pode ser definida como uma unidade de DVD (por exemplo, D:\Sources\Sxs) ou em um compartilhamento de rede em que os arquivos de mídia foram copiados ( \\por exemplo, fileserver\windows2012\sources\Sxs).</span><span class="sxs-lookup"><span data-stu-id="d843b-241">The media can be defined as a DVD drive (for example, D:\Sources\Sxs), or to a network share that the media files have been copied (for example, \\fileserver\windows2012\sources\Sxs).</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d843b-242">Confira também</span><span class="sxs-lookup"><span data-stu-id="d843b-242">See Also</span></span>


[<span data-ttu-id="d843b-243">Requisitos de IIS para pools Front-End pools e servidores Standard Edition no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d843b-243">IIS requirements for Front End pools and Standard Edition servers in Lync Server 2013</span></span>](lync-server-2013-iis-requirements-for-front-end-pools-and-standard-edition-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

