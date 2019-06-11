---
title: Requisitos de IIS para pools Front-End pools e servidores Standard Edition
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: IIS requirements for Front End pools and Standard Edition servers
ms:assetid: e8a6c7ac-b6d5-4c7e-abe9-d8ea5eedbc62
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399038(v=OCS.15)
ms:contentKeyID: 48185888
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9d804df614eab49eeabe82cca9d304e082d9ced3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829040"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="iis-requirements-for-front-end-pools-and-standard-edition-servers-in-lync-server-2013"></a><span data-ttu-id="cdd9a-102">Requisitos de IIS para pools Front-End pools e servidores Standard Edition no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cdd9a-102">IIS requirements for Front End pools and Standard Edition servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cdd9a-103">_**Tópico da última modificação:** 2012-06-19_</span><span class="sxs-lookup"><span data-stu-id="cdd9a-103">_**Topic Last Modified:** 2012-06-19_</span></span>

<span data-ttu-id="cdd9a-104">Para servidores padrão de edição e directors front-end, o instalador do Lync Server 2013 cria diretórios virtuais nos serviços de informações da Internet (IIS) para as seguintes finalidades:</span><span class="sxs-lookup"><span data-stu-id="cdd9a-104">For Standard Edition servers and Front End Servers, and Directors, the Lync Server 2013 installer creates virtual directories in Internet Information Services (IIS) for the following purposes:</span></span>

  - <span data-ttu-id="cdd9a-105">Para permitir que os usuários baixem arquivos do serviço de catálogo de endereços</span><span class="sxs-lookup"><span data-stu-id="cdd9a-105">To enable users to download files from the Address Book Service</span></span>

  - <span data-ttu-id="cdd9a-106">Para permitir que os clientes obtenham atualizações</span><span class="sxs-lookup"><span data-stu-id="cdd9a-106">To enable clients to obtain updates</span></span>

  - <span data-ttu-id="cdd9a-107">Para habilitar a conferência</span><span class="sxs-lookup"><span data-stu-id="cdd9a-107">To enable conferencing</span></span>

  - <span data-ttu-id="cdd9a-108">Para permitir que os usuários baixem o conteúdo da reunião</span><span class="sxs-lookup"><span data-stu-id="cdd9a-108">To enable users to download meeting content</span></span>

  - <span data-ttu-id="cdd9a-109">Para permitir que os usuários expandam os grupos de distribuição</span><span class="sxs-lookup"><span data-stu-id="cdd9a-109">To enable users to expand distribution groups</span></span>

  - <span data-ttu-id="cdd9a-110">Para habilitar a conferência telefônica</span><span class="sxs-lookup"><span data-stu-id="cdd9a-110">To enable phone conferencing</span></span>

  - <span data-ttu-id="cdd9a-111">Para habilitar os recursos do grupo de resposta</span><span class="sxs-lookup"><span data-stu-id="cdd9a-111">To enable response group features</span></span>

<span data-ttu-id="cdd9a-112">Além disso, a atualização cumulativa do Lync Server 2010: instalador de novembro de 2011 cria diretórios virtuais no IIS para as seguintes finalidades:</span><span class="sxs-lookup"><span data-stu-id="cdd9a-112">In addition, the cumulative update for Lync Server 2010: November 2011 installer creates virtual directories in IIS for the following purposes:</span></span>

  - <span data-ttu-id="cdd9a-113">Em servidores de front-end ou servidores Standard Edition para dar suporte à funcionalidade de mobilidade, como mensagens instantâneas (IM) e presença, em dispositivos móveis</span><span class="sxs-lookup"><span data-stu-id="cdd9a-113">On Front End Servers or Standard Edition servers to support mobility functionality, such as instant messaging (IM) and presence, on mobile devices</span></span>

  - <span data-ttu-id="cdd9a-114">Em servidores front-end ou servidores Standard Edition e em directors para permitir que dispositivos móveis descubram automaticamente os recursos de mobilidade</span><span class="sxs-lookup"><span data-stu-id="cdd9a-114">On Front End Servers or Standard Edition servers and on Directors to enable mobile devices to automatically discover mobility resources</span></span>



> [!NOTE]
> <span data-ttu-id="cdd9a-115">Se você estiver implantando a mobilidade, recomendamos que use o IIS 7,5.</span><span class="sxs-lookup"><span data-stu-id="cdd9a-115">If you are deploying mobility, we recommend that you use IIS 7.5.</span></span> <span data-ttu-id="cdd9a-116">O instalador do serviço de mobilidade do Lync Server define alguns sinalizadores ASP.NET para melhorar o desempenho.</span><span class="sxs-lookup"><span data-stu-id="cdd9a-116">The Lync Server Mobility Service installer sets some ASP.NET flags to improve performance.</span></span> <span data-ttu-id="cdd9a-117">O IIS 7,5 é instalado por padrão no Windows Server 2008 R2, e o instalador do serviço de mobilidade altera automaticamente as configurações do ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="cdd9a-117">IIS 7.5 is installed by default on Windows Server 2008 R2, and the Mobility Service installer automatically changes the ASP.NET settings.</span></span> <span data-ttu-id="cdd9a-118">Se você usa o IIS 7,0 no Windows Server 2008, é necessário alterar manualmente essas configurações.</span><span class="sxs-lookup"><span data-stu-id="cdd9a-118">If you use IIS 7.0 on Windows Server 2008, you need to manually change these settings.</span></span>



<span data-ttu-id="cdd9a-119">O Lync Server exige a instalação dos seguintes módulos do IIS:</span><span class="sxs-lookup"><span data-stu-id="cdd9a-119">Lync Server requires the following IIS modules to be installed:</span></span>


> [!IMPORTANT]
> <span data-ttu-id="cdd9a-120">Se a sua organização exigir que você localize o IIS e todos os serviços Web em uma unidade diferente da unidade do sistema, você poderá alterar o caminho do local de instalação dos arquivos do Lync Server na caixa de diálogo Configurar.</span><span class="sxs-lookup"><span data-stu-id="cdd9a-120">If your organization requires that you locate IIS and all Web Services on a drive other than the system drive, you can change the installation location path for the Lync Server files in the Setup dialog box.</span></span> <span data-ttu-id="cdd9a-121">Se você instalar os arquivos de instalação nesse caminho, incluindo OCSCore. msi, o restante dos arquivos do Lync Server também será implantado nessa unidade.</span><span class="sxs-lookup"><span data-stu-id="cdd9a-121">If you install the Setup files to this path, including OCSCore.msi, the rest of the Lync Server files will be deployed to this drive as well.</span></span> <span data-ttu-id="cdd9a-122">Para obter detalhes sobre como realocar o INETPUB implantado pelo Windows Server Manager ao instalar <A href="http://go.microsoft.com/fwlink/p/?linkid=216888">http://go.microsoft.com/fwlink/p/?linkId=216888</A>o IIS, consulte.</span><span class="sxs-lookup"><span data-stu-id="cdd9a-122">For details about how to relocate the INETPUB deployed by Windows Server Manager when installing IIS, see <A href="http://go.microsoft.com/fwlink/p/?linkid=216888">http://go.microsoft.com/fwlink/p/?linkId=216888</A>.</span></span>


  - <span data-ttu-id="cdd9a-123">Conteúdo estático</span><span class="sxs-lookup"><span data-stu-id="cdd9a-123">Static Content</span></span>

  - <span data-ttu-id="cdd9a-124">Documento padrão</span><span class="sxs-lookup"><span data-stu-id="cdd9a-124">Default Document</span></span>

  - <span data-ttu-id="cdd9a-125">Erros HTTP</span><span class="sxs-lookup"><span data-stu-id="cdd9a-125">HTTP Errors</span></span>

  - <span data-ttu-id="cdd9a-126">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="cdd9a-126">ASP.NET</span></span>

  - <span data-ttu-id="cdd9a-127">Extensibilidade .NET</span><span class="sxs-lookup"><span data-stu-id="cdd9a-127">.NET Extensibility</span></span>

  - <span data-ttu-id="cdd9a-128">Extensões da API de servidor da Internet (ISAPI)</span><span class="sxs-lookup"><span data-stu-id="cdd9a-128">Internet Server API (ISAPI) Extensions</span></span>

  - <span data-ttu-id="cdd9a-129">Filtros ISAPI</span><span class="sxs-lookup"><span data-stu-id="cdd9a-129">ISAPI Filters</span></span>

  - <span data-ttu-id="cdd9a-130">Log HTTP</span><span class="sxs-lookup"><span data-stu-id="cdd9a-130">HTTP Logging</span></span>

  - <span data-ttu-id="cdd9a-131">Ferramentas de log</span><span class="sxs-lookup"><span data-stu-id="cdd9a-131">Logging Tools</span></span>

  - <span data-ttu-id="cdd9a-132">Rastreamento</span><span class="sxs-lookup"><span data-stu-id="cdd9a-132">Tracing</span></span>

  - <span data-ttu-id="cdd9a-133">Autenticação do Windows</span><span class="sxs-lookup"><span data-stu-id="cdd9a-133">Windows Authentication</span></span>

  - <span data-ttu-id="cdd9a-134">Requisição de filtro</span><span class="sxs-lookup"><span data-stu-id="cdd9a-134">Request Filtering</span></span>

  - <span data-ttu-id="cdd9a-135">Compressão de conteúdo estático</span><span class="sxs-lookup"><span data-stu-id="cdd9a-135">Static Content Compression</span></span>

  - <span data-ttu-id="cdd9a-136">Compactação de conteúdo dinâmico</span><span class="sxs-lookup"><span data-stu-id="cdd9a-136">Dynamic Content Compression</span></span>

  - <span data-ttu-id="cdd9a-137">Console de gerenciamento IIS</span><span class="sxs-lookup"><span data-stu-id="cdd9a-137">IIS Management Console</span></span>

  - <span data-ttu-id="cdd9a-138">Ferramentas e scripts de gerenciamento IIS</span><span class="sxs-lookup"><span data-stu-id="cdd9a-138">IIS Management Scripts and Tools</span></span>

  - <span data-ttu-id="cdd9a-139">Autenticação anônima (instalada por padrão quando o IIS é instalado)</span><span class="sxs-lookup"><span data-stu-id="cdd9a-139">Anonymous Authentication (installed by default when IIS is installed)</span></span>

  - <span data-ttu-id="cdd9a-140">Autenticação de mapeamento de certificado de cliente</span><span class="sxs-lookup"><span data-stu-id="cdd9a-140">Client Certificate Mapping Authentication</span></span>

<span data-ttu-id="cdd9a-141">A tabela a seguir lista os URIs dos diretórios virtuais para acesso interno e os recursos do sistema de arquivos aos quais eles se referem.</span><span class="sxs-lookup"><span data-stu-id="cdd9a-141">The following table lists the URIs for the virtual directories for internal access and the file system resources to which they refer.</span></span>

### <a name="virtual-directories-for-internal-access"></a><span data-ttu-id="cdd9a-142">Diretórios virtuais para acesso interno</span><span class="sxs-lookup"><span data-stu-id="cdd9a-142">Virtual Directories for Internal Access</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cdd9a-143">Recurso</span><span class="sxs-lookup"><span data-stu-id="cdd9a-143">Feature</span></span></th>
<th><span data-ttu-id="cdd9a-144">URI do diretório virtual</span><span class="sxs-lookup"><span data-stu-id="cdd9a-144">Virtual directory URI</span></span></th>
<th><span data-ttu-id="cdd9a-145">Refere-se a</span><span class="sxs-lookup"><span data-stu-id="cdd9a-145">Refers to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cdd9a-146">Servidor de Catálogo de Endereços</span><span class="sxs-lookup"><span data-stu-id="cdd9a-146">Address Book Server</span></span></p></td>
<td><p><span data-ttu-id="cdd9a-147">https://&lt;interno FQDN&gt;/ABS/int/Handler</span><span class="sxs-lookup"><span data-stu-id="cdd9a-147">https://&lt;Internal FQDN&gt;/ABS/int/Handler</span></span></p></td>
<td><p><span data-ttu-id="cdd9a-148">Local do servidor de catálogo de endereços baixar arquivos para usuários internos.</span><span class="sxs-lookup"><span data-stu-id="cdd9a-148">Location of Address Book Server download files for internal users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cdd9a-149">Serviço de descoberta automática</span><span class="sxs-lookup"><span data-stu-id="cdd9a-149">Autodiscover Service</span></span></p></td>
<td><p><span data-ttu-id="cdd9a-150">https://&lt;interno FQDN&gt;/autodiscover</span><span class="sxs-lookup"><span data-stu-id="cdd9a-150">https://&lt;Internal FQDN&gt;/Autodiscover</span></span></p></td>
<td><p><span data-ttu-id="cdd9a-151">Localização do serviço de descoberta automática do Lync Server que localiza recursos de mobilidade para usuários de dispositivos móveis internos.</span><span class="sxs-lookup"><span data-stu-id="cdd9a-151">Location of the Lync Server Autodiscover Service that locates mobility resources for internal mobile device users.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cdd9a-152">Atualizações de cliente</span><span class="sxs-lookup"><span data-stu-id="cdd9a-152">Client updates</span></span></p></td>
<td><p><span data-ttu-id="cdd9a-153">http://&lt;interno FQDN&gt;/AutoUpdate/int</span><span class="sxs-lookup"><span data-stu-id="cdd9a-153">http://&lt;Internal FQDN&gt;/AutoUpdate/Int</span></span></p></td>
<td><p><span data-ttu-id="cdd9a-154">Localização de arquivos de atualização para clientes internos baseados em computador.</span><span class="sxs-lookup"><span data-stu-id="cdd9a-154">Location of update files for internal computer-based clients.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cdd9a-155">Conferência</span><span class="sxs-lookup"><span data-stu-id="cdd9a-155">Conf</span></span></p></td>
<td><p><span data-ttu-id="cdd9a-156">http://&lt;interno FQDN&gt;/conf/int</span><span class="sxs-lookup"><span data-stu-id="cdd9a-156">http://&lt;Internal FQDN&gt;/Conf/Int</span></span></p></td>
<td><p><span data-ttu-id="cdd9a-157">Localização de recursos de conferência para usuários internos.</span><span class="sxs-lookup"><span data-stu-id="cdd9a-157">Location of conferencing resources for internal users.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cdd9a-158">Atualizações de dispositivo</span><span class="sxs-lookup"><span data-stu-id="cdd9a-158">Device updates</span></span></p></td>
<td><p><span data-ttu-id="cdd9a-159">http://&lt;interno FQDN&gt;/DeviceUpdateFiles_Int</span><span class="sxs-lookup"><span data-stu-id="cdd9a-159">http://&lt;Internal FQDN&gt;/DeviceUpdateFiles_Int</span></span></p></td>
<td><p><span data-ttu-id="cdd9a-160">Localização de arquivos de atualização de dispositivos de comunicação unificada (UC) para dispositivos de comunicação unificada.</span><span class="sxs-lookup"><span data-stu-id="cdd9a-160">Location of unified communications (UC) device update files for internal UC devices.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cdd9a-161">Reunião</span><span class="sxs-lookup"><span data-stu-id="cdd9a-161">Meeting</span></span></p></td>
<td><p><span data-ttu-id="cdd9a-162">http://&lt;interno FQDN&gt;/etc/Place/NULL</span><span class="sxs-lookup"><span data-stu-id="cdd9a-162">http://&lt;Internal FQDN&gt;/etc/place/null</span></span></p></td>
<td><p><span data-ttu-id="cdd9a-163">Local do conteúdo da reunião para usuários internos.</span><span class="sxs-lookup"><span data-stu-id="cdd9a-163">Location of meeting content for internal users.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cdd9a-164">Serviço de mobilidade</span><span class="sxs-lookup"><span data-stu-id="cdd9a-164">Mobility Service</span></span></p></td>
<td><p><span data-ttu-id="cdd9a-165">https://&lt;interno FQDN&gt;/MCX</span><span class="sxs-lookup"><span data-stu-id="cdd9a-165">https://&lt;Internal FQDN&gt;/Mcx</span></span></p></td>
<td><p><span data-ttu-id="cdd9a-166">Localização de recursos de serviço de mobilidade para usuários de dispositivos móveis internos.</span><span class="sxs-lookup"><span data-stu-id="cdd9a-166">Location of Mobility Service resources for internal mobile device users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cdd9a-167">Serviço de consulta na Web de expansão de grupo e de catálogo de endereços</span><span class="sxs-lookup"><span data-stu-id="cdd9a-167">Group Expansion and Address Book Web Query service</span></span></p></td>
<td><p><span data-ttu-id="cdd9a-168">http://&lt;interno FQDN&gt;/GroupExpansion/int/Service.asmx</span><span class="sxs-lookup"><span data-stu-id="cdd9a-168">http://&lt;Internal FQDN&gt;/GroupExpansion/int/service.asmx</span></span></p></td>
<td><p><span data-ttu-id="cdd9a-169">Localização do serviço Web que permite a expansão de grupo para usuários internos.</span><span class="sxs-lookup"><span data-stu-id="cdd9a-169">Location of the Web service that enables group expansion for internal users.</span></span> <span data-ttu-id="cdd9a-170">Além disso, o local do serviço de consulta à Web do catálogo de endereços que fornece informações da lista de endereços global para clientes móveis internos do Lync móvel Microsoft Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="cdd9a-170">Also, the location of the Address Book Web Query service that provides global address list information to internal Lync Mobile Microsoft Lync 2010 Mobile clients.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cdd9a-171">Conferência telefônica</span><span class="sxs-lookup"><span data-stu-id="cdd9a-171">Phone Conferencing</span></span></p></td>
<td><p><span data-ttu-id="cdd9a-172">http://&lt;interno FQDN&gt;/PhoneConferencing/int</span><span class="sxs-lookup"><span data-stu-id="cdd9a-172">http://&lt;Internal FQDN&gt;/PhoneConferencing/Int</span></span></p></td>
<td><p><span data-ttu-id="cdd9a-173">Local dos dados de conferência telefônica para usuários internos.</span><span class="sxs-lookup"><span data-stu-id="cdd9a-173">Location of phone conferencing data for internal users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cdd9a-174">Atualizações de dispositivo</span><span class="sxs-lookup"><span data-stu-id="cdd9a-174">Device updates</span></span></p></td>
<td><p><span data-ttu-id="cdd9a-175">http://&lt;interno FQDN&gt;/RequestHandler</span><span class="sxs-lookup"><span data-stu-id="cdd9a-175">http://&lt;Internal FQDN&gt;/RequestHandler</span></span></p></td>
<td><p><span data-ttu-id="cdd9a-176">Localização do manipulador de solicitação de serviço Web de atualização de dispositivo que permite que dispositivos de comunicação unificada internos carreguem logs e verifiquem se há atualizações.</span><span class="sxs-lookup"><span data-stu-id="cdd9a-176">Location of the Device Update Web service Request Handler that enables internal UC devices to upload logs and check for updates.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cdd9a-177">Aplicativo Grupo de Resposta</span><span class="sxs-lookup"><span data-stu-id="cdd9a-177">Response Group application</span></span></p></td>
<td><p><span data-ttu-id="cdd9a-178">http://&lt;interno FQDN&gt;/RgsConfig</span><span class="sxs-lookup"><span data-stu-id="cdd9a-178">http://&lt;Internal FQDN&gt;/RgsConfig</span></span></p>
<p><span data-ttu-id="cdd9a-179">http://&lt;interno FQDN&gt;/RgsClients</span><span class="sxs-lookup"><span data-stu-id="cdd9a-179">http://&lt;Internal FQDN&gt;/RgsClients</span></span></p></td>
<td><p><span data-ttu-id="cdd9a-180">Local da ferramenta de configuração de grupo de resposta.</span><span class="sxs-lookup"><span data-stu-id="cdd9a-180">Location of Response Group Configuration Tool.</span></span></p></td>
</tr>
</tbody>
</table>


> [!NOTE]
> <span data-ttu-id="cdd9a-181">Para pools front-ends em uma configuração consolidada, você deve implantar o IIS antes de adicionar servidores ao pool.</span><span class="sxs-lookup"><span data-stu-id="cdd9a-181">For Front End pools in a consolidated configuration, you must deploy IIS before you can add servers to the pool.</span></span>


<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="segurança" alt="security" /><span data-ttu-id="cdd9a-183">Observação de segurança:</span><span class="sxs-lookup"><span data-stu-id="cdd9a-183">Security Note:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="cdd9a-184">Você deve usar o snap-in administrativo do IIS para atribuir o certificado usado pelo servidor do componente da Web do IIS.</span><span class="sxs-lookup"><span data-stu-id="cdd9a-184">You must use the IIS administrative snap-in to assign the certificate used by the IIS web component server.</span></span></td>
</tr>
</tbody>
</table>



</div>

<span> </span>

</div>

</div>

</div>

