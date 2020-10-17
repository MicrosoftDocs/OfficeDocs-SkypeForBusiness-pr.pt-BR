---
title: 'Lync Server 2013: configuração do IIS'
description: 'Lync Server 2013: configuração do IIS.'
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
ms.openlocfilehash: 901aca7bf5ff8824b54e93754569a6ef5defc10e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554867"
---
# <a name="iis-configuration-in-lync-server-2013"></a><span data-ttu-id="fcf68-103">Configuração do IIS no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fcf68-103">IIS configuration in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fcf68-104">_**Última modificação do tópico:** 2014-02-17_</span><span class="sxs-lookup"><span data-stu-id="fcf68-104">_**Topic Last Modified:** 2014-02-17_</span></span>

<span data-ttu-id="fcf68-105">Para concluir este procedimento com êxito, você deve estar conectado ao servidor no mínimo como um administrador local e como um usuário do domínio.</span><span class="sxs-lookup"><span data-stu-id="fcf68-105">To successfully complete this procedure, you should be logged on to the server minimally as a local administrator and a domain user.</span></span>

<span data-ttu-id="fcf68-106">Antes de configurar e instalar o servidor front-end para o Lync Server 2013, Standard Edition ou o primeiro servidor front-end em um pool, instale e configure a função de servidor e os serviços Web para o IIS (serviços de informações da Internet).</span><span class="sxs-lookup"><span data-stu-id="fcf68-106">Before you configure and install the Front End Server for Lync Server 2013, Standard Edition or the first Front End Server in a pool, you install and configure the server role and Web Services for Internet Information Services (IIS).</span></span>

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="fcf68-107">Se a sua organização exigir que você localize o IIS e todos os serviços Web em uma unidade diferente da unidade do sistema, você poderá alterar o caminho do local de instalação dos arquivos do Lync Server 2013 na caixa de diálogo Configurar ao instalar inicialmente as ferramentas administrativas do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fcf68-107">If your organization requires that you locate IIS and all Web Services on a drive other than the system drive, you can change the installation location path for the Lync Server 2013 files in the Setup dialog box when you initially install the Lync Server 2013 Administrative tools.</span></span> <span data-ttu-id="fcf68-108">Instale as ferramentas Administrativas antes de instalar o IIS.</span><span class="sxs-lookup"><span data-stu-id="fcf68-108">You install the Administrative tools before installing IIS.</span></span> <span data-ttu-id="fcf68-109">Se você instalar os arquivos de instalação nesse caminho, incluindo OCSCore.msi, o restante dos arquivos do Lync Server 2013 também será implantado nessa unidade.</span><span class="sxs-lookup"><span data-stu-id="fcf68-109">If you install the Setup files to this path, including OCSCore.msi, the rest of the Lync Server 2013 files will be deployed to this drive as well.</span></span> <span data-ttu-id="fcf68-110">Para o dtails, confira <A href="lync-server-2013-install-lync-server-administrative-tools.md">instalar as ferramentas administrativas do Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="fcf68-110">For dtails, see <A href="lync-server-2013-install-lync-server-administrative-tools.md">Install Lync Server 2013 administrative tools</A>.</span></span> <span data-ttu-id="fcf68-111">Para obter detalhes sobre como realocar o INETPUB implantado pelo Windows Server Manager ao instalar o IIS, consulte <A href="https://go.microsoft.com/fwlink/p/?linkid=216888">https://go.microsoft.com/fwlink/p/?linkId=216888</A> .</span><span class="sxs-lookup"><span data-stu-id="fcf68-111">For details about how to relocate the INETPUB deployed by Windows Server Manager when installing IIS, see <A href="https://go.microsoft.com/fwlink/p/?linkid=216888">https://go.microsoft.com/fwlink/p/?linkId=216888</A>.</span></span>



</div>

<span data-ttu-id="fcf68-112">A tabela a seguir indica os serviços de função do IIS 7,5 necessários.</span><span class="sxs-lookup"><span data-stu-id="fcf68-112">The following table indicates the required IIS 7.5 role services.</span></span>

### <a name="iis-75-role-services"></a><span data-ttu-id="fcf68-113">Serviços de função do IIS 7,5</span><span class="sxs-lookup"><span data-stu-id="fcf68-113">IIS 7.5 Role Services</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fcf68-114">Título da função</span><span class="sxs-lookup"><span data-stu-id="fcf68-114">Role Heading</span></span></th>
<th><span data-ttu-id="fcf68-115">Serviço de função</span><span class="sxs-lookup"><span data-stu-id="fcf68-115">Role Service</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fcf68-116">Recursos HTTP comuns instalados</span><span class="sxs-lookup"><span data-stu-id="fcf68-116">Common HTTP features installed</span></span></p></td>
<td><p><span data-ttu-id="fcf68-117">Conteúdo estático</span><span class="sxs-lookup"><span data-stu-id="fcf68-117">Static content</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fcf68-118">Recursos HTTP comuns instalados</span><span class="sxs-lookup"><span data-stu-id="fcf68-118">Common HTTP features installed</span></span></p></td>
<td><p><span data-ttu-id="fcf68-119">Documento padrão</span><span class="sxs-lookup"><span data-stu-id="fcf68-119">Default document</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fcf68-120">Recursos HTTP comuns instalados</span><span class="sxs-lookup"><span data-stu-id="fcf68-120">Common HTTP features installed</span></span></p></td>
<td><p><span data-ttu-id="fcf68-121">Erros HTTP</span><span class="sxs-lookup"><span data-stu-id="fcf68-121">HTTP errors</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fcf68-122">Desenvolvimento de aplicativos</span><span class="sxs-lookup"><span data-stu-id="fcf68-122">Application development</span></span></p></td>
<td><p><span data-ttu-id="fcf68-123">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="fcf68-123">ASP.NET</span></span></p>
<p><span data-ttu-id="fcf68-124">O Windows Server 2012 também requer o ASP. NET 4.5</span><span class="sxs-lookup"><span data-stu-id="fcf68-124">Windows Server 2012 also requires ASP.NET4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fcf68-125">Desenvolvimento de aplicativos</span><span class="sxs-lookup"><span data-stu-id="fcf68-125">Application development</span></span></p></td>
<td><p><span data-ttu-id="fcf68-126">Extensibilidade .NET</span><span class="sxs-lookup"><span data-stu-id="fcf68-126">.NET extensibility</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fcf68-127">Desenvolvimento de aplicativos</span><span class="sxs-lookup"><span data-stu-id="fcf68-127">Application development</span></span></p></td>
<td><p><span data-ttu-id="fcf68-128">Extensões Internet Server API (ISAPI)</span><span class="sxs-lookup"><span data-stu-id="fcf68-128">Internet Server API (ISAPI) extensions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fcf68-129">Desenvolvimento de aplicativos</span><span class="sxs-lookup"><span data-stu-id="fcf68-129">Application development</span></span></p></td>
<td><p><span data-ttu-id="fcf68-130">Filtros ISAPI</span><span class="sxs-lookup"><span data-stu-id="fcf68-130">ISAPI filters</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fcf68-131">Integridade e diagnósticos</span><span class="sxs-lookup"><span data-stu-id="fcf68-131">Health and diagnostics</span></span></p></td>
<td><p><span data-ttu-id="fcf68-132">Log de HTTP</span><span class="sxs-lookup"><span data-stu-id="fcf68-132">HTTP logging</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fcf68-133">Integridade e diagnósticos</span><span class="sxs-lookup"><span data-stu-id="fcf68-133">Health and diagnostics</span></span></p></td>
<td><p><span data-ttu-id="fcf68-134">Ferramentas de log</span><span class="sxs-lookup"><span data-stu-id="fcf68-134">Logging tools</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fcf68-135">Integridade e diagnósticos</span><span class="sxs-lookup"><span data-stu-id="fcf68-135">Health and diagnostics</span></span></p></td>
<td><p><span data-ttu-id="fcf68-136">Rastreia</span><span class="sxs-lookup"><span data-stu-id="fcf68-136">Tracing</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fcf68-137">Segurança</span><span class="sxs-lookup"><span data-stu-id="fcf68-137">Security</span></span></p></td>
<td><p><span data-ttu-id="fcf68-138">Autenticação anônima (instalada e habilitada por padrão)</span><span class="sxs-lookup"><span data-stu-id="fcf68-138">Anonymous authentication (installed and enabled by default)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fcf68-139">Segurança</span><span class="sxs-lookup"><span data-stu-id="fcf68-139">Security</span></span></p></td>
<td><p><span data-ttu-id="fcf68-140">Autenticação do Windows</span><span class="sxs-lookup"><span data-stu-id="fcf68-140">Windows authentication</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fcf68-141">Segurança</span><span class="sxs-lookup"><span data-stu-id="fcf68-141">Security</span></span></p></td>
<td><p><span data-ttu-id="fcf68-142">Autenticação de mapeamento de certificado de cliente</span><span class="sxs-lookup"><span data-stu-id="fcf68-142">Client Certificate Mapping authentication</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fcf68-143">Segurança</span><span class="sxs-lookup"><span data-stu-id="fcf68-143">Security</span></span></p></td>
<td><p><span data-ttu-id="fcf68-144">Filtragem de solicitação</span><span class="sxs-lookup"><span data-stu-id="fcf68-144">Request filtering</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fcf68-145">Desempenho</span><span class="sxs-lookup"><span data-stu-id="fcf68-145">Performance</span></span></p></td>
<td><p><span data-ttu-id="fcf68-146">Compactação de conteúdo estático</span><span class="sxs-lookup"><span data-stu-id="fcf68-146">Static content compression</span></span></p>
<p><span data-ttu-id="fcf68-147">Compactação de conteúdo dinâmico</span><span class="sxs-lookup"><span data-stu-id="fcf68-147">Dynamic content compression</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fcf68-148">Ferramentas de gerenciamento</span><span class="sxs-lookup"><span data-stu-id="fcf68-148">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="fcf68-149">Console de gerenciamento IIS</span><span class="sxs-lookup"><span data-stu-id="fcf68-149">IIS Management Console</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fcf68-150">Ferramentas de gerenciamento</span><span class="sxs-lookup"><span data-stu-id="fcf68-150">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="fcf68-151">Ferramentas e scripts de gerenciamento IIS</span><span class="sxs-lookup"><span data-stu-id="fcf68-151">IIS Management Scripts and Tools</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="fcf68-152">No sistema operacional Windows Server 2008 R2 SP1 x64, você pode usar o Windows PowerShell 2,0.</span><span class="sxs-lookup"><span data-stu-id="fcf68-152">On the Windows Server 2008 R2 SP1 x64 operating system, you can use Windows PowerShell 2.0.</span></span> <span data-ttu-id="fcf68-153">Primeiro é necessário importar o módulo ServerManager e, em seguida, instalar a função e os serviços de função IIS 7.5.</span><span class="sxs-lookup"><span data-stu-id="fcf68-153">You must first import the ServerManager module, and then install the IIS 7.5 role and role services.</span></span>

   ```PowerShell
    Import-Module ServerManager
   ```

   ```PowerShell
    Add-WindowsFeature Web-Server, Web-Static-Content, Web-Default-Doc, Web-Scripting-Tools, Web-Windows-Auth, Web-Asp-Net, Web-Log-Libraries, Web-Http-Tracing, Web-Stat-Compression, Web-Dyn-Compression, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Errors, Web-Http-Logging, Web-Net-Ext, Web-Client-Auth, Web-Filtering, Web-Mgmt-Console
   ```

<div class=" ">


> [!NOTE]  
> <span data-ttu-id="fcf68-154">A autenticação anônima está instalada por padrão com a função de servidor do IIS.</span><span class="sxs-lookup"><span data-stu-id="fcf68-154">Anonymous authentication is installed by default with the IIS server role.</span></span> <span data-ttu-id="fcf68-155">É possível gerenciar a autenticação anônima após a instalação do IIS.</span><span class="sxs-lookup"><span data-stu-id="fcf68-155">You can manage anonymous authentication after the installation of IIS.</span></span> <span data-ttu-id="fcf68-156">Para obter detalhes, consulte "habilitar autenticação anônima (IIS 7)" em <A href="https://go.microsoft.com/fwlink/p/?linkid=203935">https://go.microsoft.com/fwlink/p/?linkId=203935</A> .</span><span class="sxs-lookup"><span data-stu-id="fcf68-156">For details, see “Enable Anonymous Authentication (IIS 7)” at <A href="https://go.microsoft.com/fwlink/p/?linkid=203935">https://go.microsoft.com/fwlink/p/?linkId=203935</A>.</span></span>



</div>

<span data-ttu-id="fcf68-157">A tabela a seguir indica os serviços de função do IIS 8,0 e IIS 8,5 necessários para o Windows Server 2012 e o Windows Server 2012 R2.</span><span class="sxs-lookup"><span data-stu-id="fcf68-157">The following table indicates the required IIS 8.0 and IIS 8.5 role services for Windows Server 2012 and Windows Server 2012 R2.</span></span>

<div class=" ">


> [!NOTE]  
> <span data-ttu-id="fcf68-158">Para o Windows Server 2012 e o Windows Server 2012 R2, o cmdlet Add-WindowsFeature foi substituído pelo cmdlet Install-WindowsFeature.</span><span class="sxs-lookup"><span data-stu-id="fcf68-158">For Windows Server 2012 and Windows Server 2012 R2, the Add-WindowsFeature cmdlet has been replaced by the Install-WindowsFeature cmdlet.</span></span> <span data-ttu-id="fcf68-159">Para obter detalhes, consulte <A href="https://go.microsoft.com/fwlink/p/?linkid=392274">install-WindowsFeature</A>.</span><span class="sxs-lookup"><span data-stu-id="fcf68-159">For details, see <A href="https://go.microsoft.com/fwlink/p/?linkid=392274">Install-WindowsFeature</A>.</span></span>



</div>

### <a name="iis-80-and-iis-85-role-services"></a><span data-ttu-id="fcf68-160">Serviços de função do IIS 8,0 e IIS 8,5</span><span class="sxs-lookup"><span data-stu-id="fcf68-160">IIS 8.0 and IIS 8.5 Role Services</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fcf68-161">Título da função</span><span class="sxs-lookup"><span data-stu-id="fcf68-161">Role Heading</span></span></th>
<th><span data-ttu-id="fcf68-162">Serviço de função</span><span class="sxs-lookup"><span data-stu-id="fcf68-162">Role Service</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fcf68-163">Servidor Web (IIS)</span><span class="sxs-lookup"><span data-stu-id="fcf68-163">Web Server (IIS)</span></span></p></td>
<td><p><span data-ttu-id="fcf68-164">Servidor Web</span><span class="sxs-lookup"><span data-stu-id="fcf68-164">Web Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fcf68-165">Recursos HTTP Comuns</span><span class="sxs-lookup"><span data-stu-id="fcf68-165">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="fcf68-166">Documento Padrão</span><span class="sxs-lookup"><span data-stu-id="fcf68-166">Default Document</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fcf68-167">Recursos HTTP Comuns</span><span class="sxs-lookup"><span data-stu-id="fcf68-167">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="fcf68-168">Pesquisa no diretório</span><span class="sxs-lookup"><span data-stu-id="fcf68-168">Directory Browsing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fcf68-169">Recursos HTTP Comuns</span><span class="sxs-lookup"><span data-stu-id="fcf68-169">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="fcf68-170">Erros de HTTP</span><span class="sxs-lookup"><span data-stu-id="fcf68-170">HTTP Errors</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fcf68-171">Recursos HTTP Comuns</span><span class="sxs-lookup"><span data-stu-id="fcf68-171">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="fcf68-172">Conteúdo estático</span><span class="sxs-lookup"><span data-stu-id="fcf68-172">Static content</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fcf68-173">Recursos de HTTP comuns</span><span class="sxs-lookup"><span data-stu-id="fcf68-173">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="fcf68-174">Redirecionamento HTTP</span><span class="sxs-lookup"><span data-stu-id="fcf68-174">HTTP Redirection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fcf68-175">Manutenção e diagnóstico</span><span class="sxs-lookup"><span data-stu-id="fcf68-175">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="fcf68-176">Log HTTP</span><span class="sxs-lookup"><span data-stu-id="fcf68-176">HTTP Logging</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fcf68-177">Integridade e Diagnósticos</span><span class="sxs-lookup"><span data-stu-id="fcf68-177">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="fcf68-178">Ferramentas de log</span><span class="sxs-lookup"><span data-stu-id="fcf68-178">Logging Tools</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fcf68-179">Integridade e Diagnósticos</span><span class="sxs-lookup"><span data-stu-id="fcf68-179">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="fcf68-180">Monitor de solicitações</span><span class="sxs-lookup"><span data-stu-id="fcf68-180">Request Monitor</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fcf68-181">Integridade e Diagnósticos</span><span class="sxs-lookup"><span data-stu-id="fcf68-181">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="fcf68-182">Rastreia</span><span class="sxs-lookup"><span data-stu-id="fcf68-182">Tracing</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fcf68-183">Segurança</span><span class="sxs-lookup"><span data-stu-id="fcf68-183">Security</span></span></p></td>
<td><p><span data-ttu-id="fcf68-184">Filtragem de Solicitações</span><span class="sxs-lookup"><span data-stu-id="fcf68-184">Request Filtering</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fcf68-185">Segurança</span><span class="sxs-lookup"><span data-stu-id="fcf68-185">Security</span></span></p></td>
<td><p><span data-ttu-id="fcf68-186">Autenticação básica</span><span class="sxs-lookup"><span data-stu-id="fcf68-186">Basic Authentication</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fcf68-187">Segurança</span><span class="sxs-lookup"><span data-stu-id="fcf68-187">Security</span></span></p></td>
<td><p><span data-ttu-id="fcf68-188">Autenticação de mapeamento de certificado de cliente</span><span class="sxs-lookup"><span data-stu-id="fcf68-188">Client Certificate Mapping Authentication</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fcf68-189">Segurança</span><span class="sxs-lookup"><span data-stu-id="fcf68-189">Security</span></span></p></td>
<td><p><span data-ttu-id="fcf68-190">Autenticação do Windows</span><span class="sxs-lookup"><span data-stu-id="fcf68-190">Windows Authentication</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fcf68-191">Desenvolvimento de aplicativo</span><span class="sxs-lookup"><span data-stu-id="fcf68-191">Application Development</span></span></p></td>
<td><p><span data-ttu-id="fcf68-192">Extensibilidade do .net 3,5</span><span class="sxs-lookup"><span data-stu-id="fcf68-192">.Net Extensibility 3.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fcf68-193">Desenvolvimento de aplicativo</span><span class="sxs-lookup"><span data-stu-id="fcf68-193">Application Development</span></span></p></td>
<td><p><span data-ttu-id="fcf68-194">Extensibilidade do .NET 4,5</span><span class="sxs-lookup"><span data-stu-id="fcf68-194">.Net Extensibility 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fcf68-195">Desenvolvimento de aplicativo</span><span class="sxs-lookup"><span data-stu-id="fcf68-195">Application Development</span></span></p></td>
<td><p><span data-ttu-id="fcf68-196">ASP.Net 3,5</span><span class="sxs-lookup"><span data-stu-id="fcf68-196">ASP.Net 3.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fcf68-197">Desenvolvimento de aplicativo</span><span class="sxs-lookup"><span data-stu-id="fcf68-197">Application Development</span></span></p></td>
<td><p><span data-ttu-id="fcf68-198">ASP.Net 4,5</span><span class="sxs-lookup"><span data-stu-id="fcf68-198">ASP.Net 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fcf68-199">Desenvolvimento do aplicativo</span><span class="sxs-lookup"><span data-stu-id="fcf68-199">Application Development</span></span></p></td>
<td><p><span data-ttu-id="fcf68-200">Extensões ISAPI</span><span class="sxs-lookup"><span data-stu-id="fcf68-200">ISAPI Extensions</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fcf68-201">Desenvolvimento do aplicativo</span><span class="sxs-lookup"><span data-stu-id="fcf68-201">Application Development</span></span></p></td>
<td><p><span data-ttu-id="fcf68-202">Filtros ISAPI</span><span class="sxs-lookup"><span data-stu-id="fcf68-202">ISAPI Filters</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fcf68-203">Desenvolvimento de aplicativo</span><span class="sxs-lookup"><span data-stu-id="fcf68-203">Application Development</span></span></p></td>
<td><p><span data-ttu-id="fcf68-204">Server Side Includes</span><span class="sxs-lookup"><span data-stu-id="fcf68-204">Server Side Includes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fcf68-205">Ferramentas de gerenciamento</span><span class="sxs-lookup"><span data-stu-id="fcf68-205">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="fcf68-206">Console de gerenciamento IIS</span><span class="sxs-lookup"><span data-stu-id="fcf68-206">IIS Management Console</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fcf68-207">Ferramentas de gerenciamento</span><span class="sxs-lookup"><span data-stu-id="fcf68-207">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="fcf68-208">Compatibilidade de metabase do IIS 6</span><span class="sxs-lookup"><span data-stu-id="fcf68-208">IIS 6 Metabase compatibility</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fcf68-209">Ferramentas de gerenciamento</span><span class="sxs-lookup"><span data-stu-id="fcf68-209">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="fcf68-210">Ferramentas e scripts de gerenciamento IIS</span><span class="sxs-lookup"><span data-stu-id="fcf68-210">IIS Management Scripts and Tools</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fcf68-211">Recursos da estrutura do .net 3,5</span><span class="sxs-lookup"><span data-stu-id="fcf68-211">.Net 3.5 Framework Features</span></span></p></td>
<td><p><span data-ttu-id="fcf68-212">Estrutura do .net 3,5</span><span class="sxs-lookup"><span data-stu-id="fcf68-212">.Net 3.5 Framework</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fcf68-213">Recursos da estrutura do .NET 4,5</span><span class="sxs-lookup"><span data-stu-id="fcf68-213">.Net 4.5 Framework Features</span></span></p></td>
<td><p><span data-ttu-id="fcf68-214">.NET Framework 4,5</span><span class="sxs-lookup"><span data-stu-id="fcf68-214">.Net Framework 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fcf68-215">Recursos da estrutura do .NET 4,5</span><span class="sxs-lookup"><span data-stu-id="fcf68-215">.Net 4.5 Framework Features</span></span></p></td>
<td><p><span data-ttu-id="fcf68-216">ASP.Net 4,5</span><span class="sxs-lookup"><span data-stu-id="fcf68-216">ASP.Net 4.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fcf68-217">Recursos da estrutura do .NET 4,5</span><span class="sxs-lookup"><span data-stu-id="fcf68-217">.Net 4.5 Framework Features</span></span></p></td>
<td><p><span data-ttu-id="fcf68-218">Ativação de HTTP</span><span class="sxs-lookup"><span data-stu-id="fcf68-218">HTTP Activation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fcf68-219">Recursos da estrutura do .NET 4,5</span><span class="sxs-lookup"><span data-stu-id="fcf68-219">.Net 4.5 Framework Features</span></span></p></td>
<td><p><span data-ttu-id="fcf68-220">Compartilhamento de porta TCP</span><span class="sxs-lookup"><span data-stu-id="fcf68-220">TCP Port Sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fcf68-221">Serviço de transferência inteligente em segundo plano</span><span class="sxs-lookup"><span data-stu-id="fcf68-221">Background Intelligent Transfer Service</span></span></p></td>
<td><p><span data-ttu-id="fcf68-222">Extensões de servidor IIS</span><span class="sxs-lookup"><span data-stu-id="fcf68-222">IIS Server Extensions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fcf68-223">Serviços de Reconhecimento de Manuscrito</span><span class="sxs-lookup"><span data-stu-id="fcf68-223">Ink and Handwriting Services</span></span></p></td>
<td><p><span data-ttu-id="fcf68-224">Serviços de Reconhecimento de Manuscrito</span><span class="sxs-lookup"><span data-stu-id="fcf68-224">Ink and Handwriting Services</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fcf68-225">Media Foundation</span><span class="sxs-lookup"><span data-stu-id="fcf68-225">Media Foundation</span></span></p></td>
<td><p><span data-ttu-id="fcf68-226">Media Foundation</span><span class="sxs-lookup"><span data-stu-id="fcf68-226">Media Foundation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fcf68-227">Infraestrutura e interfaces de usuário</span><span class="sxs-lookup"><span data-stu-id="fcf68-227">User Interfaces and Infrastructure</span></span></p></td>
<td><p><span data-ttu-id="fcf68-228">Infraestrutura e ferramentas de gerenciamento gráfico</span><span class="sxs-lookup"><span data-stu-id="fcf68-228">Graphical Management Tools and Infrastructure</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fcf68-229">Infraestrutura e interfaces de usuário</span><span class="sxs-lookup"><span data-stu-id="fcf68-229">User Interfaces and Infrastructure</span></span></p></td>
<td><p><span data-ttu-id="fcf68-230">Experiência Desktop</span><span class="sxs-lookup"><span data-stu-id="fcf68-230">Desktop Experience</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fcf68-231">Infraestrutura e interfaces de usuário</span><span class="sxs-lookup"><span data-stu-id="fcf68-231">User Interfaces and Infrastructure</span></span></p></td>
<td><p><span data-ttu-id="fcf68-232">Shell gráfico de servidor</span><span class="sxs-lookup"><span data-stu-id="fcf68-232">Server Graphical Shell</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fcf68-233">Windows Identity Foundation 3,5</span><span class="sxs-lookup"><span data-stu-id="fcf68-233">Windows Identity Foundation 3.5</span></span></p></td>
<td><p><span data-ttu-id="fcf68-234">Windows Identity Foundation 3,5</span><span class="sxs-lookup"><span data-stu-id="fcf68-234">Windows Identity Foundation 3.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fcf68-235">Serviço de ativação de processos do Windows</span><span class="sxs-lookup"><span data-stu-id="fcf68-235">Windows Process Activation Service</span></span></p></td>
<td><p><span data-ttu-id="fcf68-236">Modelo de processo</span><span class="sxs-lookup"><span data-stu-id="fcf68-236">Process Model</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fcf68-237">Serviço de ativação de processos do Windows</span><span class="sxs-lookup"><span data-stu-id="fcf68-237">Windows Process Activation Service</span></span></p></td>
<td><p><span data-ttu-id="fcf68-238">APIs de configuração</span><span class="sxs-lookup"><span data-stu-id="fcf68-238">Configuration APIs</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="fcf68-239">No Windows Server 2012 e no Windows Server 2012 R2, você pode usar o Windows PowerShell 3,0 para instalar os requisitos do IIS.</span><span class="sxs-lookup"><span data-stu-id="fcf68-239">In Windows Server 2012 and Windows Server 2012 R2, you can use Windows PowerShell 3.0 to install the IIS Requirements.</span></span> <span data-ttu-id="fcf68-240">Usando o módulo ServerManager no Windows PowerShell 3,0, digite:</span><span class="sxs-lookup"><span data-stu-id="fcf68-240">Using the ServerManager module in Windows PowerShell 3.0, type:</span></span>

   ```PowerShell
    Import-Module ServerManager
   ```

   ```PowerShell
    Add-WindowsFeature Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-Framework-45-Core, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Console, Web-Mgmt-Compat, Windows-Identity-Foundation, Server-Media-Foundation, BITS -Source D:\sources\sxs
   ```

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="fcf68-241">Novo com o Windows Server 2012 é o parâmetro – source que define onde a mídia de origem do Windows Server 2012 pode ser encontrada.</span><span class="sxs-lookup"><span data-stu-id="fcf68-241">New with Windows Server 2012 is the –Source parameter that defines where the Windows Server 2012 source media can be found.</span></span> <span data-ttu-id="fcf68-242">A mídia pode ser definida como uma unidade de DVD (por exemplo, D:\Sources\Sxs) ou para um compartilhamento de rede que os arquivos de mídia foram copiados (por exemplo, \\ fileserver\windows2012\sources\Sxs).</span><span class="sxs-lookup"><span data-stu-id="fcf68-242">The media can be defined as a DVD drive (for example, D:\Sources\Sxs), or to a network share that the media files have been copied (for example, \\fileserver\windows2012\sources\Sxs).</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="fcf68-243">Confira também</span><span class="sxs-lookup"><span data-stu-id="fcf68-243">See Also</span></span>


[<span data-ttu-id="fcf68-244">Requisitos de IIS para pools front-end e servidores Standard Edition no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fcf68-244">IIS requirements for Front End pools and Standard Edition servers in Lync Server 2013</span></span>](lync-server-2013-iis-requirements-for-front-end-pools-and-standard-edition-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

