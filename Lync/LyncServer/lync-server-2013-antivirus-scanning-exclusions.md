---
title: 'Lync Server 2013: exclusões de verificação de antivírus'
description: 'Lync Server 2013: exclusões de verificação antivírus.'
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
ms.openlocfilehash: 20c395f529cad91993d003efdeb231bd66f4b9bc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561907"
---
# <a name="antivirus-scanning-exclusions-for-lync-server-2013"></a><span data-ttu-id="fa432-103">Exclusões de verificação antivírus para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fa432-103">Antivirus scanning exclusions for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fa432-104">_**Última modificação do tópico:** 2015-11-02_</span><span class="sxs-lookup"><span data-stu-id="fa432-104">_**Topic Last Modified:** 2015-11-02_</span></span>

<span data-ttu-id="fa432-105">Para garantir que o verificador antivírus não interfira na operação do Lync Server 2013, você deve excluir processos e diretórios específicos para cada função de servidor ou servidor do Lync Server 2013 em que você execute um scanner antivírus.</span><span class="sxs-lookup"><span data-stu-id="fa432-105">To ensure that the antivirus scanner does not interfere with the operation of Lync Server 2013, you must exclude specific processes and directories for each Lync Server 2013 server or server role on which you run an antivirus scanner.</span></span> <span data-ttu-id="fa432-106">Os seguintes processos e diretórios devem ser excluídos:</span><span class="sxs-lookup"><span data-stu-id="fa432-106">The following processes and directories should be excluded:</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="fa432-107">Os locais de pasta e arquivo listados abaixo são os locais padrão para o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fa432-107">Folder and file locations listed below are the default locations for Lync Server 2013.</span></span> <span data-ttu-id="fa432-108">Para os locais nos quais você não usou o padrão, exclua os locais especificados para a sua organização em vez dos locais padrão especificados neste tópico.</span><span class="sxs-lookup"><span data-stu-id="fa432-108">For any locations for which you did not use the default, exclude the locations you specified for your organization instead of the default locations specified in this topic.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="fa432-109">Observe que alguns programas antivírus podem precisar de caminhos absolutos e não relativos, para a lista de exclusão.</span><span class="sxs-lookup"><span data-stu-id="fa432-109">Please note that some antivirus programs may need absolute, not relative paths, for their exclusion list.</span></span>



</div>

  - <span data-ttu-id="fa432-110">Processos do Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="fa432-110">Lync Server 2013 processes:</span></span>
    
      - <span data-ttu-id="fa432-111">ABServer.exe</span><span class="sxs-lookup"><span data-stu-id="fa432-111">ABServer.exe</span></span>
    
      - <span data-ttu-id="fa432-112">AcpMcuSvc.exe</span><span class="sxs-lookup"><span data-stu-id="fa432-112">AcpMcuSvc.exe</span></span>
    
      - <span data-ttu-id="fa432-113">ASMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="fa432-113">ASMCUSvc.exe</span></span>
    
      - <span data-ttu-id="fa432-114">AVMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="fa432-114">AVMCUSvc.exe</span></span>
    
      - <span data-ttu-id="fa432-115">ChannelService.exe</span><span class="sxs-lookup"><span data-stu-id="fa432-115">ChannelService.exe</span></span>
    
      - <span data-ttu-id="fa432-116">ClsAgent.exe</span><span class="sxs-lookup"><span data-stu-id="fa432-116">ClsAgent.exe</span></span>
    
      - <span data-ttu-id="fa432-117">ComplianceService.exe</span><span class="sxs-lookup"><span data-stu-id="fa432-117">ComplianceService.exe</span></span>
    
      - <span data-ttu-id="fa432-118">DataMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="fa432-118">DataMCUSvc.exe</span></span>
    
      - <span data-ttu-id="fa432-119">DataProxy.exe</span><span class="sxs-lookup"><span data-stu-id="fa432-119">DataProxy.exe</span></span>
    
      - <span data-ttu-id="fa432-120">FileTransferAgent.exe</span><span class="sxs-lookup"><span data-stu-id="fa432-120">FileTransferAgent.exe</span></span>
    
      - <span data-ttu-id="fa432-121">IMMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="fa432-121">IMMCUSvc.exe</span></span>
    
      - <span data-ttu-id="fa432-122">LysSvc.exe</span><span class="sxs-lookup"><span data-stu-id="fa432-122">LysSvc.exe</span></span>
    
      - <span data-ttu-id="fa432-123">MasterReplicatorAgent.exe</span><span class="sxs-lookup"><span data-stu-id="fa432-123">MasterReplicatorAgent.exe</span></span>
    
      - <span data-ttu-id="fa432-124">MediaRelaySvc.exe</span><span class="sxs-lookup"><span data-stu-id="fa432-124">MediaRelaySvc.exe</span></span>
    
      - <span data-ttu-id="fa432-125">MediationServerSvc.exe</span><span class="sxs-lookup"><span data-stu-id="fa432-125">MediationServerSvc.exe</span></span>
    
      - <span data-ttu-id="fa432-126">MRASSvc.exe</span><span class="sxs-lookup"><span data-stu-id="fa432-126">MRASSvc.exe</span></span>
    
      - <span data-ttu-id="fa432-127">OcsAppServerHost.exe</span><span class="sxs-lookup"><span data-stu-id="fa432-127">OcsAppServerHost.exe</span></span>
    
      - <span data-ttu-id="fa432-128">ReplicaReplicatorAgent.exe</span><span class="sxs-lookup"><span data-stu-id="fa432-128">ReplicaReplicatorAgent.exe</span></span>
    
      - <span data-ttu-id="fa432-129">ReplicationApp.exe</span><span class="sxs-lookup"><span data-stu-id="fa432-129">ReplicationApp.exe</span></span>
    
      - <span data-ttu-id="fa432-130">RtcHost.exe</span><span class="sxs-lookup"><span data-stu-id="fa432-130">RtcHost.exe</span></span>
    
      - <span data-ttu-id="fa432-131">RTCSrv.exe</span><span class="sxs-lookup"><span data-stu-id="fa432-131">RTCSrv.exe</span></span>
    
      - <span data-ttu-id="fa432-132">XmppProxy.exe</span><span class="sxs-lookup"><span data-stu-id="fa432-132">XmppProxy.exe</span></span>
    
      - <span data-ttu-id="fa432-133">XmppTGW.exe</span><span class="sxs-lookup"><span data-stu-id="fa432-133">XmppTGW.exe</span></span>

  - <span data-ttu-id="fa432-134">Processos do serviço de host do Windows Fabric:</span><span class="sxs-lookup"><span data-stu-id="fa432-134">Windows Fabric Host Service processes:</span></span>
    
      - <span data-ttu-id="fa432-135">Fabric.exe</span><span class="sxs-lookup"><span data-stu-id="fa432-135">Fabric.exe</span></span>
    
      - <span data-ttu-id="fa432-136">FabricDCA.exe</span><span class="sxs-lookup"><span data-stu-id="fa432-136">FabricDCA.exe</span></span>
    
      - <span data-ttu-id="fa432-137">FabricHost.exe</span><span class="sxs-lookup"><span data-stu-id="fa432-137">FabricHost.exe</span></span>

  - <span data-ttu-id="fa432-138">Processos do IIS:</span><span class="sxs-lookup"><span data-stu-id="fa432-138">IIS processes:</span></span>
    
      - <span data-ttu-id="fa432-139">% SystemRoot% \\ System32 \\ inetsrv \\w3wp.exe</span><span class="sxs-lookup"><span data-stu-id="fa432-139">%systemroot%\\system32\\inetsrv\\w3wp.exe</span></span>
    
      - <span data-ttu-id="fa432-140">% SystemRoot% \\ SysWOW64 \\ inetsrv \\w3wp.exe</span><span class="sxs-lookup"><span data-stu-id="fa432-140">%systemroot%\\SysWOW64\\inetsrv\\w3wp.exe</span></span>

  - <span data-ttu-id="fa432-141">Processos de Back-End do SQL Server:</span><span class="sxs-lookup"><span data-stu-id="fa432-141">SQL Server Back-End processes:</span></span>
    
      - <span data-ttu-id="fa432-142">% ProgramFiles% \\ Microsoft SQL Server \\ MSSQL11. MSSQLSERVER \\ MSSQL \\ Binn \\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="fa432-142">%ProgramFiles%\\Microsoft SQL Server\\MSSQL11.MSSQLSERVER\\MSSQL\\Binn\\SQLServr.exe</span></span>
    
      - <span data-ttu-id="fa432-143">% ProgramFiles% \\ Microsoft SQL Server \\ MSRS11. O MSSQLSERVER \\ Reporting Services \\ ReportServer \\ bin \\ReportingServicesService.exe</span><span class="sxs-lookup"><span data-stu-id="fa432-143">%ProgramFiles%\\Microsoft SQL Server\\MSRS11.MSSQLSERVER\\Reporting Services\\ReportServer\\Bin\\ReportingServicesService.exe</span></span>
    
      - <span data-ttu-id="fa432-144">% ProgramFiles% \\ Microsoft SQL Server \\ MSAS11. \\ \\MSMDSrv.exe bin OLAP \\</span><span class="sxs-lookup"><span data-stu-id="fa432-144">%ProgramFiles%\\Microsoft SQL Server\\MSAS11.MSSQLSERVER\\OLAP\\Bin\\MSMDSrv.exe</span></span>

  - <span data-ttu-id="fa432-145">Processos de Front-End do SQL Server:</span><span class="sxs-lookup"><span data-stu-id="fa432-145">SQL Server Front-End processes:</span></span>
    
      - <span data-ttu-id="fa432-146">% ProgramFiles% \\ Microsoft SQL Server \\ MSSQL11. LYNCLOCAL \\ MSSQL \\ Binn \\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="fa432-146">%ProgramFiles%\\Microsoft SQL Server\\MSSQL11.LYNCLOCAL\\MSSQL\\Binn\\SQLServr.exe</span></span>
    
      - <span data-ttu-id="fa432-147">% ProgramFiles% \\ Microsoft SQL Server \\ MSSQL11. RTCLOCAL \\ MSSQL \\ Binn \\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="fa432-147">%ProgramFiles%\\Microsoft SQL Server\\MSSQL11.RTCLOCAL\\MSSQL\\Binn\\SQLServr.exe</span></span>

  - <span data-ttu-id="fa432-148">Arquivos e diretórios:</span><span class="sxs-lookup"><span data-stu-id="fa432-148">Directories and files:</span></span>
    
      - <span data-ttu-id="fa432-149">% SystemRoot% \\ System32 \\ LogFiles</span><span class="sxs-lookup"><span data-stu-id="fa432-149">%systemroot%\\System32\\LogFiles</span></span>
    
      - <span data-ttu-id="fa432-150">% de \\ LogFiles da raiz_do_sistema% \\</span><span class="sxs-lookup"><span data-stu-id="fa432-150">%systemroot%\\SysWow64\\LogFiles</span></span>
    
      - <span data-ttu-id="fa432-151">% de% \\ Microsoft.NET \\ assembly do \\ GAC \_</span><span class="sxs-lookup"><span data-stu-id="fa432-151">%systemroot%\\Microsoft.NET\\assembly\\GAC\_MSIL</span></span>
    
      - <span data-ttu-id="fa432-152">% ProgramFiles% \\ Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fa432-152">%programfiles%\\Microsoft Lync Server 2013</span></span>
    
      - <span data-ttu-id="fa432-153">% ProgramFiles% \\ Arquivos comuns \\ \\ nó do Inspetor do Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fa432-153">%programfiles%\\Common Files\\Microsoft Lync Server 2013\\Watcher Node</span></span>
    
      - <span data-ttu-id="fa432-154">% ProgramFiles% \\ Arquivos comuns \\ Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fa432-154">%programfiles%\\Common Files\\Microsoft Lync Server 2013</span></span>
    
      - <span data-ttu-id="fa432-155">% SystemDrive% \\ RtcReplicaRoot</span><span class="sxs-lookup"><span data-stu-id="fa432-155">%SystemDrive%\\RtcReplicaRoot</span></span>
    
      - <span data-ttu-id="fa432-156">O repositório de compartilhamento de arquivo (especificado no Construtor de Topologias).</span><span class="sxs-lookup"><span data-stu-id="fa432-156">File share store (specified in Topology Builder).</span></span> <span data-ttu-id="fa432-157">Os repositórios de arquivo estão especificados no Construtor de Topologias.</span><span class="sxs-lookup"><span data-stu-id="fa432-157">File stores are specified in Topology Builder.</span></span>
    
      - <span data-ttu-id="fa432-158">Os dados e arquivos de log do  SQL Server, incluindo para o banco de dados de Back-End, repositório de usuários, repositório de arquivamento, repositório de monitoramento e repositório do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="fa432-158">SQL Server data and log files, including those for the back-end database, user store, archiving store, monitoring store, and application store.</span></span> <span data-ttu-id="fa432-159">Os arquivos de log e banco de dados podem ser especificados no Construtor de Topologias.</span><span class="sxs-lookup"><span data-stu-id="fa432-159">Database and log files can be specified in Topology Builder.</span></span> <span data-ttu-id="fa432-160">Para obter detalhes sobre os dados e arquivos de log para cada banco de dados, incluindo nomes padrão, confira [dados do SQL Server e posicionamento de arquivos de log para o Lync Server 2013](lync-server-2013-sql-server-data-and-log-file-placement.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="fa432-160">For details about the data and log files for each database, including default names, see [SQL Server data and log file placement for Lync Server 2013](lync-server-2013-sql-server-data-and-log-file-placement.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="fa432-161">Dados do SQL Server e arquivos de log, incluindo aqueles para o banco de dados front-end, o repositório do Lync e o repositório do RtcDatabase.</span><span class="sxs-lookup"><span data-stu-id="fa432-161">SQL Server data and log files, including those for the Front-end database, Lync store, and RtcDatabase store.</span></span> <span data-ttu-id="fa432-162">Eles estão normalmente em% Unidade_Local% \\ CSData.</span><span class="sxs-lookup"><span data-stu-id="fa432-162">They are normally under %localdrive%\\CSData.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

