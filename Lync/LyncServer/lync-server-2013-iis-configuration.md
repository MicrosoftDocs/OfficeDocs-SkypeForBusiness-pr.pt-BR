---
title: 'Lync Server 2013: configuração do IIS'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IIS configuration
ms:assetid: b458babf-bf64-43f0-8a8e-612f5096b63c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412871(v=OCS.15)
ms:contentKeyID: 48185169
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 65d9d4f61fabdca7a3f9cb4808efe952ec7ce3b2
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037873"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="iis-configuration-in-lync-server-2013"></a><span data-ttu-id="18389-102">Configuração do IIS no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="18389-102">IIS configuration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="18389-103">_**Última modificação do tópico:** 2014-02-17_</span><span class="sxs-lookup"><span data-stu-id="18389-103">_**Topic Last Modified:** 2014-02-17_</span></span>

<span data-ttu-id="18389-104">Para concluir este procedimento com êxito, você deve estar conectado ao servidor no mínimo como um administrador local e como um usuário do domínio.</span><span class="sxs-lookup"><span data-stu-id="18389-104">To successfully complete this procedure, you should be logged on to the server minimally as a local administrator and a domain user.</span></span>

<span data-ttu-id="18389-105">Antes de configurar e instalar o servidor front-end para o Lync Server 2013, Standard Edition ou o primeiro servidor front-end em um pool, instale e configure a função de servidor e os serviços Web para o IIS (serviços de informações da Internet).</span><span class="sxs-lookup"><span data-stu-id="18389-105">Before you configure and install the Front End Server for Lync Server 2013, Standard Edition or the first Front End Server in a pool, you install and configure the server role and Web Services for Internet Information Services (IIS).</span></span>

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="18389-106">Se sua organização exigir que você localize o IIS e todos os serviços Web em uma unidade diferente da unidade do sistema, você poderá alterar o caminho do local de instalação dos arquivos do Lync Server 2013 na caixa de diálogo de instalação ao instalar inicialmente o Lync Server 2013 Ferramentas administrativas.</span><span class="sxs-lookup"><span data-stu-id="18389-106">If your organization requires that you locate IIS and all Web Services on a drive other than the system drive, you can change the installation location path for the Lync Server 2013 files in the Setup dialog box when you initially install the Lync Server 2013 Administrative tools.</span></span> <span data-ttu-id="18389-107">Instale as ferramentas Administrativas antes de instalar o IIS.</span><span class="sxs-lookup"><span data-stu-id="18389-107">You install the Administrative tools before installing IIS.</span></span> <span data-ttu-id="18389-108">Se você instalar os arquivos de instalação nesse caminho, incluindo o OCSCore. msi, o restante dos arquivos do Lync Server 2013 também será implantado nessa unidade.</span><span class="sxs-lookup"><span data-stu-id="18389-108">If you install the Setup files to this path, including OCSCore.msi, the rest of the Lync Server 2013 files will be deployed to this drive as well.</span></span> <span data-ttu-id="18389-109">Para o dtails, confira <A href="lync-server-2013-install-lync-server-administrative-tools.md">instalar as ferramentas administrativas do Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="18389-109">For dtails, see <A href="lync-server-2013-install-lync-server-administrative-tools.md">Install Lync Server 2013 administrative tools</A>.</span></span> <span data-ttu-id="18389-110">Para obter detalhes sobre como realocar o INETPUB implantado pelo Windows Server Manager ao instalar <A href="http://go.microsoft.com/fwlink/p/?linkid=216888">http://go.microsoft.com/fwlink/p/?linkId=216888</A>o IIS, consulte.</span><span class="sxs-lookup"><span data-stu-id="18389-110">For details about how to relocate the INETPUB deployed by Windows Server Manager when installing IIS, see <A href="http://go.microsoft.com/fwlink/p/?linkid=216888">http://go.microsoft.com/fwlink/p/?linkId=216888</A>.</span></span>



</div>

<span data-ttu-id="18389-111">A tabela a seguir indica os serviços de função do IIS 7,5 necessários.</span><span class="sxs-lookup"><span data-stu-id="18389-111">The following table indicates the required IIS 7.5 role services.</span></span>

### <a name="iis-75-role-services"></a><span data-ttu-id="18389-112">Serviços de função do IIS 7,5</span><span class="sxs-lookup"><span data-stu-id="18389-112">IIS 7.5 Role Services</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="18389-113">Título da função</span><span class="sxs-lookup"><span data-stu-id="18389-113">Role Heading</span></span></th>
<th><span data-ttu-id="18389-114">Serviço de função</span><span class="sxs-lookup"><span data-stu-id="18389-114">Role Service</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="18389-115">Recursos HTTP comuns instalados</span><span class="sxs-lookup"><span data-stu-id="18389-115">Common HTTP features installed</span></span></p></td>
<td><p><span data-ttu-id="18389-116">Conteúdo estático</span><span class="sxs-lookup"><span data-stu-id="18389-116">Static content</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18389-117">Recursos HTTP comuns instalados</span><span class="sxs-lookup"><span data-stu-id="18389-117">Common HTTP features installed</span></span></p></td>
<td><p><span data-ttu-id="18389-118">Documento padrão</span><span class="sxs-lookup"><span data-stu-id="18389-118">Default document</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18389-119">Recursos HTTP comuns instalados</span><span class="sxs-lookup"><span data-stu-id="18389-119">Common HTTP features installed</span></span></p></td>
<td><p><span data-ttu-id="18389-120">Erros HTTP</span><span class="sxs-lookup"><span data-stu-id="18389-120">HTTP errors</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18389-121">Desenvolvimento de aplicativo</span><span class="sxs-lookup"><span data-stu-id="18389-121">Application development</span></span></p></td>
<td><p><span data-ttu-id="18389-122">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="18389-122">ASP.NET</span></span></p>
<p><span data-ttu-id="18389-123">O Windows Server 2012 também requer o ASP. NET 4.5</span><span class="sxs-lookup"><span data-stu-id="18389-123">Windows Server 2012 also requires ASP.NET4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18389-124">Desenvolvimento de aplicativo</span><span class="sxs-lookup"><span data-stu-id="18389-124">Application development</span></span></p></td>
<td><p><span data-ttu-id="18389-125">Extensibilidade .NET</span><span class="sxs-lookup"><span data-stu-id="18389-125">.NET extensibility</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18389-126">Desenvolvimento de aplicativo</span><span class="sxs-lookup"><span data-stu-id="18389-126">Application development</span></span></p></td>
<td><p><span data-ttu-id="18389-127">Extensões Internet Server API (ISAPI)</span><span class="sxs-lookup"><span data-stu-id="18389-127">Internet Server API (ISAPI) extensions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18389-128">Desenvolvimento de aplicativos</span><span class="sxs-lookup"><span data-stu-id="18389-128">Application development</span></span></p></td>
<td><p><span data-ttu-id="18389-129">Filtros ISAPI</span><span class="sxs-lookup"><span data-stu-id="18389-129">ISAPI filters</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18389-130">Integridade e diagnósticos</span><span class="sxs-lookup"><span data-stu-id="18389-130">Health and diagnostics</span></span></p></td>
<td><p><span data-ttu-id="18389-131">Log de HTTP</span><span class="sxs-lookup"><span data-stu-id="18389-131">HTTP logging</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18389-132">Integridade e diagnósticos</span><span class="sxs-lookup"><span data-stu-id="18389-132">Health and diagnostics</span></span></p></td>
<td><p><span data-ttu-id="18389-133">Ferramentas de log</span><span class="sxs-lookup"><span data-stu-id="18389-133">Logging tools</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18389-134">Integridade e diagnósticos</span><span class="sxs-lookup"><span data-stu-id="18389-134">Health and diagnostics</span></span></p></td>
<td><p><span data-ttu-id="18389-135">Rastreia</span><span class="sxs-lookup"><span data-stu-id="18389-135">Tracing</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18389-136">Segurança</span><span class="sxs-lookup"><span data-stu-id="18389-136">Security</span></span></p></td>
<td><p><span data-ttu-id="18389-137">Autenticação anônima (instalada e habilitada por padrão)</span><span class="sxs-lookup"><span data-stu-id="18389-137">Anonymous authentication (installed and enabled by default)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18389-138">Segurança</span><span class="sxs-lookup"><span data-stu-id="18389-138">Security</span></span></p></td>
<td><p><span data-ttu-id="18389-139">Autenticação do Windows</span><span class="sxs-lookup"><span data-stu-id="18389-139">Windows authentication</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18389-140">Segurança</span><span class="sxs-lookup"><span data-stu-id="18389-140">Security</span></span></p></td>
<td><p><span data-ttu-id="18389-141">Autenticação de mapeamento de certificado de cliente</span><span class="sxs-lookup"><span data-stu-id="18389-141">Client Certificate Mapping authentication</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18389-142">Segurança</span><span class="sxs-lookup"><span data-stu-id="18389-142">Security</span></span></p></td>
<td><p><span data-ttu-id="18389-143">Filtragem de solicitação</span><span class="sxs-lookup"><span data-stu-id="18389-143">Request filtering</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18389-144">Desempenho</span><span class="sxs-lookup"><span data-stu-id="18389-144">Performance</span></span></p></td>
<td><p><span data-ttu-id="18389-145">Compactação de conteúdo estático</span><span class="sxs-lookup"><span data-stu-id="18389-145">Static content compression</span></span></p>
<p><span data-ttu-id="18389-146">Compactação de conteúdo dinâmico</span><span class="sxs-lookup"><span data-stu-id="18389-146">Dynamic content compression</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18389-147">Ferramentas de gerenciamento</span><span class="sxs-lookup"><span data-stu-id="18389-147">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="18389-148">Console de gerenciamento IIS</span><span class="sxs-lookup"><span data-stu-id="18389-148">IIS Management Console</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18389-149">Ferramentas de gerenciamento</span><span class="sxs-lookup"><span data-stu-id="18389-149">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="18389-150">Ferramentas e scripts de gerenciamento IIS</span><span class="sxs-lookup"><span data-stu-id="18389-150">IIS Management Scripts and Tools</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="18389-151">No sistema operacional Windows Server 2008 R2 SP1 x64, você pode usar o Windows PowerShell 2,0.</span><span class="sxs-lookup"><span data-stu-id="18389-151">On the Windows Server 2008 R2 SP1 x64 operating system, you can use Windows PowerShell 2.0.</span></span> <span data-ttu-id="18389-152">Primeiro é necessário importar o módulo ServerManager e, em seguida, instalar a função e os serviços de função IIS 7.5.</span><span class="sxs-lookup"><span data-stu-id="18389-152">You must first import the ServerManager module, and then install the IIS 7.5 role and role services.</span></span>

   ```PowerShell
    Import-Module ServerManager
   ```

   ```PowerShell
    Add-WindowsFeature Web-Server, Web-Static-Content, Web-Default-Doc, Web-Scripting-Tools, Web-Windows-Auth, Web-Asp-Net, Web-Log-Libraries, Web-Http-Tracing, Web-Stat-Compression, Web-Dyn-Compression, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Errors, Web-Http-Logging, Web-Net-Ext, Web-Client-Auth, Web-Filtering, Web-Mgmt-Console
   ```

<div class=" ">


> [!NOTE]  
> <span data-ttu-id="18389-153">A autenticação anônima está instalada por padrão com a função de servidor do IIS.</span><span class="sxs-lookup"><span data-stu-id="18389-153">Anonymous authentication is installed by default with the IIS server role.</span></span> <span data-ttu-id="18389-154">É possível gerenciar a autenticação anônima após a instalação do IIS.</span><span class="sxs-lookup"><span data-stu-id="18389-154">You can manage anonymous authentication after the installation of IIS.</span></span> <span data-ttu-id="18389-155">Para obter detalhes, consulte "habilitar autenticação anônima (IIS 7)" <A href="http://go.microsoft.com/fwlink/p/?linkid=203935">http://go.microsoft.com/fwlink/p/?linkId=203935</A>em.</span><span class="sxs-lookup"><span data-stu-id="18389-155">For details, see “Enable Anonymous Authentication (IIS 7)” at <A href="http://go.microsoft.com/fwlink/p/?linkid=203935">http://go.microsoft.com/fwlink/p/?linkId=203935</A>.</span></span>



</div>

<span data-ttu-id="18389-156">A tabela a seguir indica os serviços de função do IIS 8,0 e IIS 8,5 necessários para o Windows Server 2012 e o Windows Server 2012 R2.</span><span class="sxs-lookup"><span data-stu-id="18389-156">The following table indicates the required IIS 8.0 and IIS 8.5 role services for Windows Server 2012 and Windows Server 2012 R2.</span></span>

<div class=" ">


> [!NOTE]  
> <span data-ttu-id="18389-157">Para o Windows Server 2012 e o Windows Server 2012 R2, o cmdlet Add-WindowsFeature foi substituído pelo cmdlet Install-WindowsFeature.</span><span class="sxs-lookup"><span data-stu-id="18389-157">For Windows Server 2012 and Windows Server 2012 R2, the Add-WindowsFeature cmdlet has been replaced by the Install-WindowsFeature cmdlet.</span></span> <span data-ttu-id="18389-158">Para obter detalhes, consulte <A href="http://go.microsoft.com/fwlink/p/?linkid=392274">install-WindowsFeature</A>.</span><span class="sxs-lookup"><span data-stu-id="18389-158">For details, see <A href="http://go.microsoft.com/fwlink/p/?linkid=392274">Install-WindowsFeature</A>.</span></span>



</div>

### <a name="iis-80-and-iis-85-role-services"></a><span data-ttu-id="18389-159">Serviços de função do IIS 8,0 e IIS 8,5</span><span class="sxs-lookup"><span data-stu-id="18389-159">IIS 8.0 and IIS 8.5 Role Services</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="18389-160">Título da função</span><span class="sxs-lookup"><span data-stu-id="18389-160">Role Heading</span></span></th>
<th><span data-ttu-id="18389-161">Serviço de função</span><span class="sxs-lookup"><span data-stu-id="18389-161">Role Service</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="18389-162">Servidor Web (IIS)</span><span class="sxs-lookup"><span data-stu-id="18389-162">Web Server (IIS)</span></span></p></td>
<td><p><span data-ttu-id="18389-163">Servidor Web</span><span class="sxs-lookup"><span data-stu-id="18389-163">Web Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18389-164">Recursos HTTP Comuns</span><span class="sxs-lookup"><span data-stu-id="18389-164">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="18389-165">Documento Padrão</span><span class="sxs-lookup"><span data-stu-id="18389-165">Default Document</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18389-166">Recursos HTTP Comuns</span><span class="sxs-lookup"><span data-stu-id="18389-166">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="18389-167">Pesquisa no diretório</span><span class="sxs-lookup"><span data-stu-id="18389-167">Directory Browsing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18389-168">Recursos HTTP Comuns</span><span class="sxs-lookup"><span data-stu-id="18389-168">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="18389-169">Erros de HTTP</span><span class="sxs-lookup"><span data-stu-id="18389-169">HTTP Errors</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18389-170">Recursos HTTP Comuns</span><span class="sxs-lookup"><span data-stu-id="18389-170">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="18389-171">Conteúdo estático</span><span class="sxs-lookup"><span data-stu-id="18389-171">Static content</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18389-172">Recursos de HTTP comuns</span><span class="sxs-lookup"><span data-stu-id="18389-172">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="18389-173">Redirecionamento HTTP</span><span class="sxs-lookup"><span data-stu-id="18389-173">HTTP Redirection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18389-174">Manutenção e diagnóstico</span><span class="sxs-lookup"><span data-stu-id="18389-174">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="18389-175">Log HTTP</span><span class="sxs-lookup"><span data-stu-id="18389-175">HTTP Logging</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18389-176">Manutenção e diagnóstico</span><span class="sxs-lookup"><span data-stu-id="18389-176">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="18389-177">Ferramentas de log</span><span class="sxs-lookup"><span data-stu-id="18389-177">Logging Tools</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18389-178">Integridade e Diagnósticos</span><span class="sxs-lookup"><span data-stu-id="18389-178">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="18389-179">Monitor de solicitações</span><span class="sxs-lookup"><span data-stu-id="18389-179">Request Monitor</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18389-180">Integridade e Diagnósticos</span><span class="sxs-lookup"><span data-stu-id="18389-180">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="18389-181">Rastreia</span><span class="sxs-lookup"><span data-stu-id="18389-181">Tracing</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18389-182">Segurança</span><span class="sxs-lookup"><span data-stu-id="18389-182">Security</span></span></p></td>
<td><p><span data-ttu-id="18389-183">Filtragem de Solicitações</span><span class="sxs-lookup"><span data-stu-id="18389-183">Request Filtering</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18389-184">Segurança</span><span class="sxs-lookup"><span data-stu-id="18389-184">Security</span></span></p></td>
<td><p><span data-ttu-id="18389-185">Autenticação básica</span><span class="sxs-lookup"><span data-stu-id="18389-185">Basic Authentication</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18389-186">Segurança</span><span class="sxs-lookup"><span data-stu-id="18389-186">Security</span></span></p></td>
<td><p><span data-ttu-id="18389-187">Autenticação de mapeamento de certificado de cliente</span><span class="sxs-lookup"><span data-stu-id="18389-187">Client Certificate Mapping Authentication</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18389-188">Segurança</span><span class="sxs-lookup"><span data-stu-id="18389-188">Security</span></span></p></td>
<td><p><span data-ttu-id="18389-189">Autenticação do Windows</span><span class="sxs-lookup"><span data-stu-id="18389-189">Windows Authentication</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18389-190">Desenvolvimento de aplicativo</span><span class="sxs-lookup"><span data-stu-id="18389-190">Application Development</span></span></p></td>
<td><p><span data-ttu-id="18389-191">Extensibilidade do .net 3,5</span><span class="sxs-lookup"><span data-stu-id="18389-191">.Net Extensibility 3.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18389-192">Desenvolvimento de aplicativo</span><span class="sxs-lookup"><span data-stu-id="18389-192">Application Development</span></span></p></td>
<td><p><span data-ttu-id="18389-193">Extensibilidade do .NET 4,5</span><span class="sxs-lookup"><span data-stu-id="18389-193">.Net Extensibility 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18389-194">Desenvolvimento de aplicativo</span><span class="sxs-lookup"><span data-stu-id="18389-194">Application Development</span></span></p></td>
<td><p><span data-ttu-id="18389-195">ASP.Net 3,5</span><span class="sxs-lookup"><span data-stu-id="18389-195">ASP.Net 3.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18389-196">Desenvolvimento de aplicativo</span><span class="sxs-lookup"><span data-stu-id="18389-196">Application Development</span></span></p></td>
<td><p><span data-ttu-id="18389-197">ASP.Net 4,5</span><span class="sxs-lookup"><span data-stu-id="18389-197">ASP.Net 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18389-198">Desenvolvimento de aplicativo</span><span class="sxs-lookup"><span data-stu-id="18389-198">Application Development</span></span></p></td>
<td><p><span data-ttu-id="18389-199">Extensões ISAPI</span><span class="sxs-lookup"><span data-stu-id="18389-199">ISAPI Extensions</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18389-200">Desenvolvimento do aplicativo</span><span class="sxs-lookup"><span data-stu-id="18389-200">Application Development</span></span></p></td>
<td><p><span data-ttu-id="18389-201">Filtros ISAPI</span><span class="sxs-lookup"><span data-stu-id="18389-201">ISAPI Filters</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18389-202">Desenvolvimento de aplicativo</span><span class="sxs-lookup"><span data-stu-id="18389-202">Application Development</span></span></p></td>
<td><p><span data-ttu-id="18389-203">Server Side Includes</span><span class="sxs-lookup"><span data-stu-id="18389-203">Server Side Includes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18389-204">Ferramentas de gerenciamento</span><span class="sxs-lookup"><span data-stu-id="18389-204">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="18389-205">Console de gerenciamento IIS</span><span class="sxs-lookup"><span data-stu-id="18389-205">IIS Management Console</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18389-206">Ferramentas de gerenciamento</span><span class="sxs-lookup"><span data-stu-id="18389-206">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="18389-207">Compatibilidade de metabase do IIS 6</span><span class="sxs-lookup"><span data-stu-id="18389-207">IIS 6 Metabase compatibility</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18389-208">Ferramentas de gerenciamento</span><span class="sxs-lookup"><span data-stu-id="18389-208">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="18389-209">Ferramentas e scripts de gerenciamento IIS</span><span class="sxs-lookup"><span data-stu-id="18389-209">IIS Management Scripts and Tools</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18389-210">Recursos da estrutura do .net 3,5</span><span class="sxs-lookup"><span data-stu-id="18389-210">.Net 3.5 Framework Features</span></span></p></td>
<td><p><span data-ttu-id="18389-211">Estrutura do .net 3,5</span><span class="sxs-lookup"><span data-stu-id="18389-211">.Net 3.5 Framework</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18389-212">Recursos da estrutura do .NET 4,5</span><span class="sxs-lookup"><span data-stu-id="18389-212">.Net 4.5 Framework Features</span></span></p></td>
<td><p><span data-ttu-id="18389-213">.NET Framework 4,5</span><span class="sxs-lookup"><span data-stu-id="18389-213">.Net Framework 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18389-214">Recursos da estrutura do .NET 4,5</span><span class="sxs-lookup"><span data-stu-id="18389-214">.Net 4.5 Framework Features</span></span></p></td>
<td><p><span data-ttu-id="18389-215">ASP.Net 4,5</span><span class="sxs-lookup"><span data-stu-id="18389-215">ASP.Net 4.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18389-216">Recursos da estrutura do .NET 4,5</span><span class="sxs-lookup"><span data-stu-id="18389-216">.Net 4.5 Framework Features</span></span></p></td>
<td><p><span data-ttu-id="18389-217">Ativação de HTTP</span><span class="sxs-lookup"><span data-stu-id="18389-217">HTTP Activation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18389-218">Recursos da estrutura do .NET 4,5</span><span class="sxs-lookup"><span data-stu-id="18389-218">.Net 4.5 Framework Features</span></span></p></td>
<td><p><span data-ttu-id="18389-219">Compartilhamento de porta TCP</span><span class="sxs-lookup"><span data-stu-id="18389-219">TCP Port Sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18389-220">Serviço de transferência inteligente em segundo plano</span><span class="sxs-lookup"><span data-stu-id="18389-220">Background Intelligent Transfer Service</span></span></p></td>
<td><p><span data-ttu-id="18389-221">Extensões de servidor IIS</span><span class="sxs-lookup"><span data-stu-id="18389-221">IIS Server Extensions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18389-222">Serviços de Reconhecimento de Manuscrito</span><span class="sxs-lookup"><span data-stu-id="18389-222">Ink and Handwriting Services</span></span></p></td>
<td><p><span data-ttu-id="18389-223">Serviços de Reconhecimento de Manuscrito</span><span class="sxs-lookup"><span data-stu-id="18389-223">Ink and Handwriting Services</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18389-224">Media Foundation</span><span class="sxs-lookup"><span data-stu-id="18389-224">Media Foundation</span></span></p></td>
<td><p><span data-ttu-id="18389-225">Media Foundation</span><span class="sxs-lookup"><span data-stu-id="18389-225">Media Foundation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18389-226">Infraestrutura e interfaces de usuário</span><span class="sxs-lookup"><span data-stu-id="18389-226">User Interfaces and Infrastructure</span></span></p></td>
<td><p><span data-ttu-id="18389-227">Infraestrutura e ferramentas de gerenciamento gráfico</span><span class="sxs-lookup"><span data-stu-id="18389-227">Graphical Management Tools and Infrastructure</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18389-228">Infraestrutura e interfaces de usuário</span><span class="sxs-lookup"><span data-stu-id="18389-228">User Interfaces and Infrastructure</span></span></p></td>
<td><p><span data-ttu-id="18389-229">Experiência Desktop</span><span class="sxs-lookup"><span data-stu-id="18389-229">Desktop Experience</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18389-230">Infraestrutura e interfaces de usuário</span><span class="sxs-lookup"><span data-stu-id="18389-230">User Interfaces and Infrastructure</span></span></p></td>
<td><p><span data-ttu-id="18389-231">Shell gráfico de servidor</span><span class="sxs-lookup"><span data-stu-id="18389-231">Server Graphical Shell</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18389-232">Windows Identity Foundation 3,5</span><span class="sxs-lookup"><span data-stu-id="18389-232">Windows Identity Foundation 3.5</span></span></p></td>
<td><p><span data-ttu-id="18389-233">Windows Identity Foundation 3,5</span><span class="sxs-lookup"><span data-stu-id="18389-233">Windows Identity Foundation 3.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18389-234">Serviço de ativação de processos do Windows</span><span class="sxs-lookup"><span data-stu-id="18389-234">Windows Process Activation Service</span></span></p></td>
<td><p><span data-ttu-id="18389-235">Modelo de processo</span><span class="sxs-lookup"><span data-stu-id="18389-235">Process Model</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18389-236">Serviço de ativação de processos do Windows</span><span class="sxs-lookup"><span data-stu-id="18389-236">Windows Process Activation Service</span></span></p></td>
<td><p><span data-ttu-id="18389-237">APIs de configuração</span><span class="sxs-lookup"><span data-stu-id="18389-237">Configuration APIs</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="18389-238">No Windows Server 2012 e no Windows Server 2012 R2, você pode usar o Windows PowerShell 3,0 para instalar os requisitos do IIS.</span><span class="sxs-lookup"><span data-stu-id="18389-238">In Windows Server 2012 and Windows Server 2012 R2, you can use Windows PowerShell 3.0 to install the IIS Requirements.</span></span> <span data-ttu-id="18389-239">Usando o módulo ServerManager no Windows PowerShell 3,0, digite:</span><span class="sxs-lookup"><span data-stu-id="18389-239">Using the ServerManager module in Windows PowerShell 3.0, type:</span></span>

   ```PowerShell
    Import-Module ServerManager
   ```

   ```PowerShell
    Add-WindowsFeature Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-Framework-45-Core, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Console, Web-Mgmt-Compat, Windows-Identity-Foundation, Server-Media-Foundation, BITS -Source D:\sources\sxs
   ```

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="18389-240">Novo com o Windows Server 2012 é o parâmetro – source que define onde a mídia de origem do Windows Server 2012 pode ser encontrada.</span><span class="sxs-lookup"><span data-stu-id="18389-240">New with Windows Server 2012 is the –Source parameter that defines where the Windows Server 2012 source media can be found.</span></span> <span data-ttu-id="18389-241">A mídia pode ser definida como uma unidade de DVD (por exemplo, D:\Sources\Sxs) ou para um compartilhamento de rede que os arquivos de mídia foram copiados (por \\exemplo, fileserver\windows2012\sources\Sxs).</span><span class="sxs-lookup"><span data-stu-id="18389-241">The media can be defined as a DVD drive (for example, D:\Sources\Sxs), or to a network share that the media files have been copied (for example, \\fileserver\windows2012\sources\Sxs).</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="18389-242">Confira também</span><span class="sxs-lookup"><span data-stu-id="18389-242">See Also</span></span>


[<span data-ttu-id="18389-243">Requisitos de IIS para pools front-end e servidores Standard Edition no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="18389-243">IIS requirements for Front End pools and Standard Edition servers in Lync Server 2013</span></span>](lync-server-2013-iis-requirements-for-front-end-pools-and-standard-edition-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

