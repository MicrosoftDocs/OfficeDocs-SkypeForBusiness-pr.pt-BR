---
title: 'Lync Server 2013: exclusões de verificação de antivírus'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Antivirus scanning exclusions for Lync Server 2013
ms:assetid: 71e1f1cc-2d16-4111-9864-9276bf24dfe0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440138(v=OCS.15)
ms:contentKeyID: 57793042
ms.date: 11/03/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d3a67d7777017c004b0cfcc59a46cd27baf5c209
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147064"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="antivirus-scanning-exclusions-for-lync-server-2013"></a><span data-ttu-id="4e6ab-102">Exclusões de verificação antivírus para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4e6ab-102">Antivirus scanning exclusions for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4e6ab-103">_**Última modificação do tópico:** 2015-11-02_</span><span class="sxs-lookup"><span data-stu-id="4e6ab-103">_**Topic Last Modified:** 2015-11-02_</span></span>

<span data-ttu-id="4e6ab-104">Para garantir que o verificador antivírus não interfira na operação do Lync Server 2013, você deve excluir processos e diretórios específicos para cada função de servidor ou servidor do Lync Server 2013 em que você execute um scanner antivírus.</span><span class="sxs-lookup"><span data-stu-id="4e6ab-104">To ensure that the antivirus scanner does not interfere with the operation of Lync Server 2013, you must exclude specific processes and directories for each Lync Server 2013 server or server role on which you run an antivirus scanner.</span></span> <span data-ttu-id="4e6ab-105">Os seguintes processos e diretórios devem ser excluídos:</span><span class="sxs-lookup"><span data-stu-id="4e6ab-105">The following processes and directories should be excluded:</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4e6ab-106">Os locais de pasta e arquivo listados abaixo são os locais padrão para o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4e6ab-106">Folder and file locations listed below are the default locations for Lync Server 2013.</span></span> <span data-ttu-id="4e6ab-107">Para os locais nos quais você não usou o padrão, exclua os locais especificados para a sua organização em vez dos locais padrão especificados neste tópico.</span><span class="sxs-lookup"><span data-stu-id="4e6ab-107">For any locations for which you did not use the default, exclude the locations you specified for your organization instead of the default locations specified in this topic.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="4e6ab-108">Observe que alguns programas antivírus podem precisar de caminhos absolutos e não relativos, para a lista de exclusão.</span><span class="sxs-lookup"><span data-stu-id="4e6ab-108">Please note that some antivirus programs may need absolute, not relative paths, for their exclusion list.</span></span>



</div>

  - <span data-ttu-id="4e6ab-109">Processos do Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="4e6ab-109">Lync Server 2013 processes:</span></span>
    
      - <span data-ttu-id="4e6ab-110">ABServer. exe</span><span class="sxs-lookup"><span data-stu-id="4e6ab-110">ABServer.exe</span></span>
    
      - <span data-ttu-id="4e6ab-111">AcpMcuSvc. exe</span><span class="sxs-lookup"><span data-stu-id="4e6ab-111">AcpMcuSvc.exe</span></span>
    
      - <span data-ttu-id="4e6ab-112">ASMCUSvc. exe</span><span class="sxs-lookup"><span data-stu-id="4e6ab-112">ASMCUSvc.exe</span></span>
    
      - <span data-ttu-id="4e6ab-113">AVMCUSvc. exe</span><span class="sxs-lookup"><span data-stu-id="4e6ab-113">AVMCUSvc.exe</span></span>
    
      - <span data-ttu-id="4e6ab-114">ChannelService. exe</span><span class="sxs-lookup"><span data-stu-id="4e6ab-114">ChannelService.exe</span></span>
    
      - <span data-ttu-id="4e6ab-115">ClsAgent. exe</span><span class="sxs-lookup"><span data-stu-id="4e6ab-115">ClsAgent.exe</span></span>
    
      - <span data-ttu-id="4e6ab-116">ComplianceService. exe</span><span class="sxs-lookup"><span data-stu-id="4e6ab-116">ComplianceService.exe</span></span>
    
      - <span data-ttu-id="4e6ab-117">DataMCUSvc. exe</span><span class="sxs-lookup"><span data-stu-id="4e6ab-117">DataMCUSvc.exe</span></span>
    
      - <span data-ttu-id="4e6ab-118">Dataproxy. exe</span><span class="sxs-lookup"><span data-stu-id="4e6ab-118">DataProxy.exe</span></span>
    
      - <span data-ttu-id="4e6ab-119">FileTransferAgent. exe</span><span class="sxs-lookup"><span data-stu-id="4e6ab-119">FileTransferAgent.exe</span></span>
    
      - <span data-ttu-id="4e6ab-120">IMMCUSvc. exe</span><span class="sxs-lookup"><span data-stu-id="4e6ab-120">IMMCUSvc.exe</span></span>
    
      - <span data-ttu-id="4e6ab-121">LysSvc. exe</span><span class="sxs-lookup"><span data-stu-id="4e6ab-121">LysSvc.exe</span></span>
    
      - <span data-ttu-id="4e6ab-122">MasterReplicatorAgent. exe</span><span class="sxs-lookup"><span data-stu-id="4e6ab-122">MasterReplicatorAgent.exe</span></span>
    
      - <span data-ttu-id="4e6ab-123">MediaRelaySvc. exe</span><span class="sxs-lookup"><span data-stu-id="4e6ab-123">MediaRelaySvc.exe</span></span>
    
      - <span data-ttu-id="4e6ab-124">MediationServerSvc. exe</span><span class="sxs-lookup"><span data-stu-id="4e6ab-124">MediationServerSvc.exe</span></span>
    
      - <span data-ttu-id="4e6ab-125">MRASSvc. exe</span><span class="sxs-lookup"><span data-stu-id="4e6ab-125">MRASSvc.exe</span></span>
    
      - <span data-ttu-id="4e6ab-126">OcsAppServerHost. exe</span><span class="sxs-lookup"><span data-stu-id="4e6ab-126">OcsAppServerHost.exe</span></span>
    
      - <span data-ttu-id="4e6ab-127">ReplicaReplicatorAgent. exe</span><span class="sxs-lookup"><span data-stu-id="4e6ab-127">ReplicaReplicatorAgent.exe</span></span>
    
      - <span data-ttu-id="4e6ab-128">ReplicationApp. exe</span><span class="sxs-lookup"><span data-stu-id="4e6ab-128">ReplicationApp.exe</span></span>
    
      - <span data-ttu-id="4e6ab-129">RtcHost. exe</span><span class="sxs-lookup"><span data-stu-id="4e6ab-129">RtcHost.exe</span></span>
    
      - <span data-ttu-id="4e6ab-130">RTCSrv. exe</span><span class="sxs-lookup"><span data-stu-id="4e6ab-130">RTCSrv.exe</span></span>
    
      - <span data-ttu-id="4e6ab-131">XmppProxy. exe</span><span class="sxs-lookup"><span data-stu-id="4e6ab-131">XmppProxy.exe</span></span>
    
      - <span data-ttu-id="4e6ab-132">XmppTGW. exe</span><span class="sxs-lookup"><span data-stu-id="4e6ab-132">XmppTGW.exe</span></span>

  - <span data-ttu-id="4e6ab-133">Processos do serviço de host do Windows Fabric:</span><span class="sxs-lookup"><span data-stu-id="4e6ab-133">Windows Fabric Host Service processes:</span></span>
    
      - <span data-ttu-id="4e6ab-134">Fabric. exe</span><span class="sxs-lookup"><span data-stu-id="4e6ab-134">Fabric.exe</span></span>
    
      - <span data-ttu-id="4e6ab-135">FabricDCA. exe</span><span class="sxs-lookup"><span data-stu-id="4e6ab-135">FabricDCA.exe</span></span>
    
      - <span data-ttu-id="4e6ab-136">FabricHost. exe</span><span class="sxs-lookup"><span data-stu-id="4e6ab-136">FabricHost.exe</span></span>

  - <span data-ttu-id="4e6ab-137">Processos do IIS:</span><span class="sxs-lookup"><span data-stu-id="4e6ab-137">IIS processes:</span></span>
    
      - <span data-ttu-id="4e6ab-138">% SystemRoot%\\system32\\inetsrv\\w3wp. exe</span><span class="sxs-lookup"><span data-stu-id="4e6ab-138">%systemroot%\\system32\\inetsrv\\w3wp.exe</span></span>
    
      - <span data-ttu-id="4e6ab-139">% SystemRoot%\\SysWOW64\\inetsrv\\w3wp. exe</span><span class="sxs-lookup"><span data-stu-id="4e6ab-139">%systemroot%\\SysWOW64\\inetsrv\\w3wp.exe</span></span>

  - <span data-ttu-id="4e6ab-140">Processos de back-end do SQL Server:</span><span class="sxs-lookup"><span data-stu-id="4e6ab-140">SQL Server Back-End processes:</span></span>
    
      - <span data-ttu-id="4e6ab-141">% ProgramFiles\\% Microsoft SQL\\Server MSSQL11. MSSQLSERVER\\MSSQL\\Binn\\sqlservr. exe</span><span class="sxs-lookup"><span data-stu-id="4e6ab-141">%ProgramFiles%\\Microsoft SQL Server\\MSSQL11.MSSQLSERVER\\MSSQL\\Binn\\SQLServr.exe</span></span>
    
      - <span data-ttu-id="4e6ab-142">% ProgramFiles\\% Microsoft SQL\\Server MSRS11. MSSQLSERVER\\Reporting\\Services\\\\ReportServer bin ReportingServicesService. exe</span><span class="sxs-lookup"><span data-stu-id="4e6ab-142">%ProgramFiles%\\Microsoft SQL Server\\MSRS11.MSSQLSERVER\\Reporting Services\\ReportServer\\Bin\\ReportingServicesService.exe</span></span>
    
      - <span data-ttu-id="4e6ab-143">% ProgramFiles\\% Microsoft SQL\\Server MSAS11. Compartimento\\\\do\\MSSQLSERVER OLAP MSMDSrv. exe</span><span class="sxs-lookup"><span data-stu-id="4e6ab-143">%ProgramFiles%\\Microsoft SQL Server\\MSAS11.MSSQLSERVER\\OLAP\\Bin\\MSMDSrv.exe</span></span>

  - <span data-ttu-id="4e6ab-144">Processos de front-end do SQL Server:</span><span class="sxs-lookup"><span data-stu-id="4e6ab-144">SQL Server Front-End processes:</span></span>
    
      - <span data-ttu-id="4e6ab-145">% ProgramFiles\\% Microsoft SQL\\Server MSSQL11. LYNCLOCAL\\MSSQL\\Binn\\sqlservr. exe</span><span class="sxs-lookup"><span data-stu-id="4e6ab-145">%ProgramFiles%\\Microsoft SQL Server\\MSSQL11.LYNCLOCAL\\MSSQL\\Binn\\SQLServr.exe</span></span>
    
      - <span data-ttu-id="4e6ab-146">% ProgramFiles\\% Microsoft SQL\\Server MSSQL11. RTCLOCAL\\MSSQL\\Binn\\sqlservr. exe</span><span class="sxs-lookup"><span data-stu-id="4e6ab-146">%ProgramFiles%\\Microsoft SQL Server\\MSSQL11.RTCLOCAL\\MSSQL\\Binn\\SQLServr.exe</span></span>

  - <span data-ttu-id="4e6ab-147">Arquivos e diretórios:</span><span class="sxs-lookup"><span data-stu-id="4e6ab-147">Directories and files:</span></span>
    
      - <span data-ttu-id="4e6ab-148">% SystemRoot%\\system32\\LogFiles</span><span class="sxs-lookup"><span data-stu-id="4e6ab-148">%systemroot%\\System32\\LogFiles</span></span>
    
      - <span data-ttu-id="4e6ab-149">% de\\\\LogFiles da raiz_do_sistema%</span><span class="sxs-lookup"><span data-stu-id="4e6ab-149">%systemroot%\\SysWow64\\LogFiles</span></span>
    
      - <span data-ttu-id="4e6ab-150">% de%\\Microsoft.NET\\assembly\\do\_GAC</span><span class="sxs-lookup"><span data-stu-id="4e6ab-150">%systemroot%\\Microsoft.NET\\assembly\\GAC\_MSIL</span></span>
    
      - <span data-ttu-id="4e6ab-151">% ProgramFiles\\% Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4e6ab-151">%programfiles%\\Microsoft Lync Server 2013</span></span>
    
      - <span data-ttu-id="4e6ab-152">% ProgramFiles\\% arquivos\\comuns nó do Inspetor\\do Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4e6ab-152">%programfiles%\\Common Files\\Microsoft Lync Server 2013\\Watcher Node</span></span>
    
      - <span data-ttu-id="4e6ab-153">% ProgramFiles\\% arquivos\\comuns Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4e6ab-153">%programfiles%\\Common Files\\Microsoft Lync Server 2013</span></span>
    
      - <span data-ttu-id="4e6ab-154">% SystemDrive%\\RtcReplicaRoot</span><span class="sxs-lookup"><span data-stu-id="4e6ab-154">%SystemDrive%\\RtcReplicaRoot</span></span>
    
      - <span data-ttu-id="4e6ab-155">O repositório de compartilhamento de arquivo (especificado no Construtor de Topologias).</span><span class="sxs-lookup"><span data-stu-id="4e6ab-155">File share store (specified in Topology Builder).</span></span> <span data-ttu-id="4e6ab-156">Os repositórios de arquivo estão especificados no Construtor de Topologias.</span><span class="sxs-lookup"><span data-stu-id="4e6ab-156">File stores are specified in Topology Builder.</span></span>
    
      - <span data-ttu-id="4e6ab-157">Os dados e arquivos de log do  SQL Server, incluindo para o banco de dados de Back-End, repositório de usuários, repositório de arquivamento, repositório de monitoramento e repositório do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="4e6ab-157">SQL Server data and log files, including those for the back-end database, user store, archiving store, monitoring store, and application store.</span></span> <span data-ttu-id="4e6ab-158">Os arquivos de log e banco de dados podem ser especificados no Construtor de Topologias.</span><span class="sxs-lookup"><span data-stu-id="4e6ab-158">Database and log files can be specified in Topology Builder.</span></span> <span data-ttu-id="4e6ab-159">Para obter detalhes sobre os dados e arquivos de log para cada banco de dados, incluindo nomes padrão, confira [dados do SQL Server e posicionamento de arquivos de log para o Lync Server 2013](lync-server-2013-sql-server-data-and-log-file-placement.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="4e6ab-159">For details about the data and log files for each database, including default names, see [SQL Server data and log file placement for Lync Server 2013](lync-server-2013-sql-server-data-and-log-file-placement.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="4e6ab-160">Dados do SQL Server e arquivos de log, incluindo aqueles para o banco de dados front-end, o repositório do Lync e o repositório do RtcDatabase.</span><span class="sxs-lookup"><span data-stu-id="4e6ab-160">SQL Server data and log files, including those for the Front-end database, Lync store, and RtcDatabase store.</span></span> <span data-ttu-id="4e6ab-161">Eles estão normalmente em% Unidade_Local%\\CSData.</span><span class="sxs-lookup"><span data-stu-id="4e6ab-161">They are normally under %localdrive%\\CSData.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

