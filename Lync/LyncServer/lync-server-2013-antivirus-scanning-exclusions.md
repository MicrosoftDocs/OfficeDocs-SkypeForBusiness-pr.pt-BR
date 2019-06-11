---
title: 'Lync Server 2013: Exclusões de verificação de antivírus'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Antivirus scanning exclusions for Lync Server 2013
ms:assetid: 71e1f1cc-2d16-4111-9864-9276bf24dfe0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440138(v=OCS.15)
ms:contentKeyID: 57793042
ms.date: 11/03/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e6f354b93bf21f054e9b5b24e3befd1787279bbe
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837038"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="antivirus-scanning-exclusions-for-lync-server-2013"></a><span data-ttu-id="b8939-102">Exclusões de verificação de antivírus para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b8939-102">Antivirus scanning exclusions for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b8939-103">_**Tópico da última modificação:** 2015-11-02_</span><span class="sxs-lookup"><span data-stu-id="b8939-103">_**Topic Last Modified:** 2015-11-02_</span></span>

<span data-ttu-id="b8939-104">Para garantir que o scanner antivírus não interfira com a operação do Lync Server 2013, você deve excluir processos e pastas específicos para cada função de servidor ou servidor do Lync Server 2013 na qual você executa um verificador de vírus.</span><span class="sxs-lookup"><span data-stu-id="b8939-104">To ensure that the antivirus scanner does not interfere with the operation of Lync Server 2013, you must exclude specific processes and directories for each Lync Server 2013 server or server role on which you run an antivirus scanner.</span></span> <span data-ttu-id="b8939-105">Os seguintes processos e diretórios devem ser excluídos:</span><span class="sxs-lookup"><span data-stu-id="b8939-105">The following processes and directories should be excluded:</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b8939-106">Os locais de pasta e arquivo listados abaixo são os locais padrão do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b8939-106">Folder and file locations listed below are the default locations for Lync Server 2013.</span></span> <span data-ttu-id="b8939-107">Para quaisquer locais, para os quais você não usa o padrão, exclua os locais que você especificou para a sua organização em vez dos locais padrão especificados neste tópico.</span><span class="sxs-lookup"><span data-stu-id="b8939-107">For any locations for which you did not use the default, exclude the locations you specified for your organization instead of the default locations specified in this topic.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="b8939-108">Observe que alguns programas antivírus podem precisar de caminhos absolutos e não relativos, para a sua lista de exclusão.</span><span class="sxs-lookup"><span data-stu-id="b8939-108">Please note that some antivirus programs may need absolute, not relative paths, for their exclusion list.</span></span>



</div>

  - <span data-ttu-id="b8939-109">Processos do Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="b8939-109">Lync Server 2013 processes:</span></span>
    
      - <span data-ttu-id="b8939-110">ABServer.exe</span><span class="sxs-lookup"><span data-stu-id="b8939-110">ABServer.exe</span></span>
    
      - <span data-ttu-id="b8939-111">AcpMcuSvc. exe</span><span class="sxs-lookup"><span data-stu-id="b8939-111">AcpMcuSvc.exe</span></span>
    
      - <span data-ttu-id="b8939-112">ASMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="b8939-112">ASMCUSvc.exe</span></span>
    
      - <span data-ttu-id="b8939-113">AVMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="b8939-113">AVMCUSvc.exe</span></span>
    
      - <span data-ttu-id="b8939-114">ChannelService.exe</span><span class="sxs-lookup"><span data-stu-id="b8939-114">ChannelService.exe</span></span>
    
      - <span data-ttu-id="b8939-115">ClsAgent.exe</span><span class="sxs-lookup"><span data-stu-id="b8939-115">ClsAgent.exe</span></span>
    
      - <span data-ttu-id="b8939-116">ComplianceService.exe</span><span class="sxs-lookup"><span data-stu-id="b8939-116">ComplianceService.exe</span></span>
    
      - <span data-ttu-id="b8939-117">DataMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="b8939-117">DataMCUSvc.exe</span></span>
    
      - <span data-ttu-id="b8939-118">DataProxy.exe</span><span class="sxs-lookup"><span data-stu-id="b8939-118">DataProxy.exe</span></span>
    
      - <span data-ttu-id="b8939-119">FileTransferAgent.exe</span><span class="sxs-lookup"><span data-stu-id="b8939-119">FileTransferAgent.exe</span></span>
    
      - <span data-ttu-id="b8939-120">IMMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="b8939-120">IMMCUSvc.exe</span></span>
    
      - <span data-ttu-id="b8939-121">LysSvc.exe</span><span class="sxs-lookup"><span data-stu-id="b8939-121">LysSvc.exe</span></span>
    
      - <span data-ttu-id="b8939-122">MasterReplicatorAgent.exe</span><span class="sxs-lookup"><span data-stu-id="b8939-122">MasterReplicatorAgent.exe</span></span>
    
      - <span data-ttu-id="b8939-123">MediaRelaySvc.exe</span><span class="sxs-lookup"><span data-stu-id="b8939-123">MediaRelaySvc.exe</span></span>
    
      - <span data-ttu-id="b8939-124">MediationServerSvc.exe</span><span class="sxs-lookup"><span data-stu-id="b8939-124">MediationServerSvc.exe</span></span>
    
      - <span data-ttu-id="b8939-125">MRASSvc.exe</span><span class="sxs-lookup"><span data-stu-id="b8939-125">MRASSvc.exe</span></span>
    
      - <span data-ttu-id="b8939-126">OcsAppServerHost.exe</span><span class="sxs-lookup"><span data-stu-id="b8939-126">OcsAppServerHost.exe</span></span>
    
      - <span data-ttu-id="b8939-127">ReplicaReplicatorAgent.exe</span><span class="sxs-lookup"><span data-stu-id="b8939-127">ReplicaReplicatorAgent.exe</span></span>
    
      - <span data-ttu-id="b8939-128">ReplicationApp.exe</span><span class="sxs-lookup"><span data-stu-id="b8939-128">ReplicationApp.exe</span></span>
    
      - <span data-ttu-id="b8939-129">RtcHost.exe</span><span class="sxs-lookup"><span data-stu-id="b8939-129">RtcHost.exe</span></span>
    
      - <span data-ttu-id="b8939-130">RTCSrv.exe</span><span class="sxs-lookup"><span data-stu-id="b8939-130">RTCSrv.exe</span></span>
    
      - <span data-ttu-id="b8939-131">XmppProxy.exe</span><span class="sxs-lookup"><span data-stu-id="b8939-131">XmppProxy.exe</span></span>
    
      - <span data-ttu-id="b8939-132">XmppTGW.exe</span><span class="sxs-lookup"><span data-stu-id="b8939-132">XmppTGW.exe</span></span>

  - <span data-ttu-id="b8939-133">Processos de Serviço de Host do Windows Fabric:</span><span class="sxs-lookup"><span data-stu-id="b8939-133">Windows Fabric Host Service processes:</span></span>
    
      - <span data-ttu-id="b8939-134">Fabric.exe</span><span class="sxs-lookup"><span data-stu-id="b8939-134">Fabric.exe</span></span>
    
      - <span data-ttu-id="b8939-135">FabricDCA.exe</span><span class="sxs-lookup"><span data-stu-id="b8939-135">FabricDCA.exe</span></span>
    
      - <span data-ttu-id="b8939-136">FabricHost.exe</span><span class="sxs-lookup"><span data-stu-id="b8939-136">FabricHost.exe</span></span>

  - <span data-ttu-id="b8939-137">Processos IIS:</span><span class="sxs-lookup"><span data-stu-id="b8939-137">IIS processes:</span></span>
    
      - <span data-ttu-id="b8939-138">% SystemRoot%\\system32\\inetsrv\\w3wp. exe</span><span class="sxs-lookup"><span data-stu-id="b8939-138">%systemroot%\\system32\\inetsrv\\w3wp.exe</span></span>
    
      - <span data-ttu-id="b8939-139">% SystemRoot%\\SysWOW64\\inetsrv\\w3wp. exe</span><span class="sxs-lookup"><span data-stu-id="b8939-139">%systemroot%\\SysWOW64\\inetsrv\\w3wp.exe</span></span>

  - <span data-ttu-id="b8939-140">Processos SQL Server Back-End:</span><span class="sxs-lookup"><span data-stu-id="b8939-140">SQL Server Back-End processes:</span></span>
    
      - <span data-ttu-id="b8939-141">% ProgramFiles\\% Microsoft SQL\\Server MSSQL11. MSSQLSERVER\\MSSQL\\Binn\\sqlservr. exe</span><span class="sxs-lookup"><span data-stu-id="b8939-141">%ProgramFiles%\\Microsoft SQL Server\\MSSQL11.MSSQLSERVER\\MSSQL\\Binn\\SQLServr.exe</span></span>
    
      - <span data-ttu-id="b8939-142">% ProgramFiles\\% Microsoft SQL\\Server MSRS11. MSSQLSERVER\\Reporting\\Services\\\\ReportServer bin ReportingServicesService. exe</span><span class="sxs-lookup"><span data-stu-id="b8939-142">%ProgramFiles%\\Microsoft SQL Server\\MSRS11.MSSQLSERVER\\Reporting Services\\ReportServer\\Bin\\ReportingServicesService.exe</span></span>
    
      - <span data-ttu-id="b8939-143">% ProgramFiles\\% Microsoft SQL\\Server MSAS11. Compartimento\\\\OLAP\\MSSQLSERVER. exe</span><span class="sxs-lookup"><span data-stu-id="b8939-143">%ProgramFiles%\\Microsoft SQL Server\\MSAS11.MSSQLSERVER\\OLAP\\Bin\\MSMDSrv.exe</span></span>

  - <span data-ttu-id="b8939-144">Processos SQL Server Front-End:</span><span class="sxs-lookup"><span data-stu-id="b8939-144">SQL Server Front-End processes:</span></span>
    
      - <span data-ttu-id="b8939-145">% ProgramFiles\\% Microsoft SQL\\Server MSSQL11. LYNCLOCAL\\MSSQL\\Binn\\sqlservr. exe</span><span class="sxs-lookup"><span data-stu-id="b8939-145">%ProgramFiles%\\Microsoft SQL Server\\MSSQL11.LYNCLOCAL\\MSSQL\\Binn\\SQLServr.exe</span></span>
    
      - <span data-ttu-id="b8939-146">% ProgramFiles\\% Microsoft SQL\\Server MSSQL11. RTCLOCAL\\MSSQL\\Binn\\sqlservr. exe</span><span class="sxs-lookup"><span data-stu-id="b8939-146">%ProgramFiles%\\Microsoft SQL Server\\MSSQL11.RTCLOCAL\\MSSQL\\Binn\\SQLServr.exe</span></span>

  - <span data-ttu-id="b8939-147">Diretórios e arquivos:</span><span class="sxs-lookup"><span data-stu-id="b8939-147">Directories and files:</span></span>
    
      - <span data-ttu-id="b8939-148">% SystemRoot%\\system32\\LogFiles</span><span class="sxs-lookup"><span data-stu-id="b8939-148">%systemroot%\\System32\\LogFiles</span></span>
    
      - <span data-ttu-id="b8939-149">% SystemRoot%\\SysWOW64\\LogFiles</span><span class="sxs-lookup"><span data-stu-id="b8939-149">%systemroot%\\SysWow64\\LogFiles</span></span>
    
      - <span data-ttu-id="b8939-150">% SystemRoot%\\Microsoft.NET\\assembly\\GAC\_MSIL</span><span class="sxs-lookup"><span data-stu-id="b8939-150">%systemroot%\\Microsoft.NET\\assembly\\GAC\_MSIL</span></span>
    
      - <span data-ttu-id="b8939-151">% ProgramFiles\\% Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b8939-151">%programfiles%\\Microsoft Lync Server 2013</span></span>
    
      - <span data-ttu-id="b8939-152">% ProgramFiles\\% arquivos\\comuns nó do Inspetor\\do Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b8939-152">%programfiles%\\Common Files\\Microsoft Lync Server 2013\\Watcher Node</span></span>
    
      - <span data-ttu-id="b8939-153">% ProgramFiles\\% arquivos\\comuns Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b8939-153">%programfiles%\\Common Files\\Microsoft Lync Server 2013</span></span>
    
      - <span data-ttu-id="b8939-154">% SystemDrive%\\RtcReplicaRoot</span><span class="sxs-lookup"><span data-stu-id="b8939-154">%SystemDrive%\\RtcReplicaRoot</span></span>
    
      - <span data-ttu-id="b8939-155">Repositório de compartilhamento de arquivo(específico no Construtor de Topologias).</span><span class="sxs-lookup"><span data-stu-id="b8939-155">File share store (specified in Topology Builder).</span></span> <span data-ttu-id="b8939-156">Os repositórios de arquivos são especificados no Construtor de Topologias.</span><span class="sxs-lookup"><span data-stu-id="b8939-156">File stores are specified in Topology Builder.</span></span>
    
      - <span data-ttu-id="b8939-157">Os arquivos de logs e dados do SQL Server, incluindo aqueles para o banco de dados de back-end, armazenamento de usuário, arquivamento, monitoramento, e repositório de application.</span><span class="sxs-lookup"><span data-stu-id="b8939-157">SQL Server data and log files, including those for the back-end database, user store, archiving store, monitoring store, and application store.</span></span> <span data-ttu-id="b8939-158">Os arquivos da base de dados e os logs podem ser especificados no Construtor de Topologias.</span><span class="sxs-lookup"><span data-stu-id="b8939-158">Database and log files can be specified in Topology Builder.</span></span> <span data-ttu-id="b8939-159">Para obter detalhes sobre os dados e arquivos de log para cada banco de dados, incluindo nomes padrão, consulte [dados do SQL Server e posicionamento do arquivo de log para o Lync Server 2013](lync-server-2013-sql-server-data-and-log-file-placement.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="b8939-159">For details about the data and log files for each database, including default names, see [SQL Server data and log file placement for Lync Server 2013](lync-server-2013-sql-server-data-and-log-file-placement.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="b8939-160">Dados e arquivos de log do SQL Server, incluindo aqueles para o banco de dados front-end, a loja do Lync e a loja do RtcDatabase.</span><span class="sxs-lookup"><span data-stu-id="b8939-160">SQL Server data and log files, including those for the Front-end database, Lync store, and RtcDatabase store.</span></span> <span data-ttu-id="b8939-161">Eles estão normalmente em% Unidade_Local%\\CSData.</span><span class="sxs-lookup"><span data-stu-id="b8939-161">They are normally under %localdrive%\\CSData.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

