---
title: Exclusões de escaneamento de antivírus para Skype for Business Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/24/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 5d742259-ef3b-417a-920b-e1fa0e48f043
description: Visão geral do interoperação de scanner antivírus com Skype para Business Server 2015.
ms.openlocfilehash: bb188b25c61269ee7c38829e1887a3443a0f77c4
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="antivirus-scanning-exclusions-for-skype-for-business-server-2015"></a><span data-ttu-id="5f62c-103">Exclusões de escaneamento de antivírus para Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="5f62c-103">Antivirus scanning exclusions for Skype for Business Server 2015</span></span>
 
<span data-ttu-id="5f62c-104">Visão geral do interoperação de scanner antivírus com Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="5f62c-104">Overview of antivirus scanner interoperation with Skype for Business Server 2015.</span></span> 
  
<span data-ttu-id="5f62c-105">Para garantir que o scanner antivírus não interfere com a operação do Skype para Business Server 2015, você deve excluir diretórios e processos específicos para cada Skype para Business Server 2015 server ou função de servidor em que você executa um scanner antivírus.</span><span class="sxs-lookup"><span data-stu-id="5f62c-105">To ensure that the antivirus scanner does not interfere with the operation of Skype for Business Server 2015, you must exclude specific processes and directories for each Skype for Business Server 2015 server or server role on which you run an antivirus scanner.</span></span> <span data-ttu-id="5f62c-106">Os seguintes processos e diretórios devem ser excluídos:</span><span class="sxs-lookup"><span data-stu-id="5f62c-106">The following processes and directories should be excluded:</span></span>
  
> [!NOTE]
> <span data-ttu-id="5f62c-107">Locais de arquivo e pasta listadas a seguir são os locais de padrão do Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="5f62c-107">Folder and file locations listed below are the default locations for Skype for Business Server 2015.</span></span> <span data-ttu-id="5f62c-108">Para quaisquer locais, para os quais você não usa o padrão, exclua os locais que você especificou para a sua organização em vez dos locais padrão especificados neste tópico.</span><span class="sxs-lookup"><span data-stu-id="5f62c-108">For any locations for which you did not use the default, exclude the locations you specified for your organization instead of the default locations specified in this topic.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="5f62c-109">Observe que alguns programas antivírus podem precisar de caminhos absolutos e não relativos, para a sua lista de exclusão.</span><span class="sxs-lookup"><span data-stu-id="5f62c-109">Please note that some antivirus programs may need absolute, not relative paths, for their exclusion list.</span></span> 
  
- <span data-ttu-id="5f62c-110">Skype para processos de negócios Server 2015:</span><span class="sxs-lookup"><span data-stu-id="5f62c-110">Skype for Business Server 2015 processes:</span></span>
    
  - <span data-ttu-id="5f62c-111">ABServer.exe</span><span class="sxs-lookup"><span data-stu-id="5f62c-111">ABServer.exe</span></span>
    
  - <span data-ttu-id="5f62c-112">ASMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="5f62c-112">ASMCUSvc.exe</span></span>
    
  - <span data-ttu-id="5f62c-113">AVMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="5f62c-113">AVMCUSvc.exe</span></span>
    
  - <span data-ttu-id="5f62c-114">ChannelService.exe</span><span class="sxs-lookup"><span data-stu-id="5f62c-114">ChannelService.exe</span></span>
    
  - <span data-ttu-id="5f62c-115">ClsAgent.exe</span><span class="sxs-lookup"><span data-stu-id="5f62c-115">ClsAgent.exe</span></span>
    
  - <span data-ttu-id="5f62c-116">ComplianceService.exe</span><span class="sxs-lookup"><span data-stu-id="5f62c-116">ComplianceService.exe</span></span>
    
  - <span data-ttu-id="5f62c-117">DataMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="5f62c-117">DataMCUSvc.exe</span></span>
    
  - <span data-ttu-id="5f62c-118">DataProxy.exe</span><span class="sxs-lookup"><span data-stu-id="5f62c-118">DataProxy.exe</span></span>
    
  - <span data-ttu-id="5f62c-119">FileTransferAgent.exe</span><span class="sxs-lookup"><span data-stu-id="5f62c-119">FileTransferAgent.exe</span></span>
    
  - <span data-ttu-id="5f62c-120">HealthAgent.exe</span><span class="sxs-lookup"><span data-stu-id="5f62c-120">HealthAgent.exe</span></span>
    
  - <span data-ttu-id="5f62c-121">IMMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="5f62c-121">IMMCUSvc.exe</span></span>
    
  - <span data-ttu-id="5f62c-122">LysSvc.exe</span><span class="sxs-lookup"><span data-stu-id="5f62c-122">LysSvc.exe</span></span>
    
  - <span data-ttu-id="5f62c-123">MasterReplicatorAgent.exe</span><span class="sxs-lookup"><span data-stu-id="5f62c-123">MasterReplicatorAgent.exe</span></span>
    
  - <span data-ttu-id="5f62c-124">MediaRelaySvc.exe</span><span class="sxs-lookup"><span data-stu-id="5f62c-124">MediaRelaySvc.exe</span></span>
    
  - <span data-ttu-id="5f62c-125">MediationServerSvc.exe</span><span class="sxs-lookup"><span data-stu-id="5f62c-125">MediationServerSvc.exe</span></span>
    
  - <span data-ttu-id="5f62c-126">MRASSvc.exe</span><span class="sxs-lookup"><span data-stu-id="5f62c-126">MRASSvc.exe</span></span>
    
  - <span data-ttu-id="5f62c-127">OcsAppServerHost.exe</span><span class="sxs-lookup"><span data-stu-id="5f62c-127">OcsAppServerHost.exe</span></span>
    
  - <span data-ttu-id="5f62c-128">ReplicaReplicatorAgent.exe</span><span class="sxs-lookup"><span data-stu-id="5f62c-128">ReplicaReplicatorAgent.exe</span></span>
    
  - <span data-ttu-id="5f62c-129">ReplicationApp.exe</span><span class="sxs-lookup"><span data-stu-id="5f62c-129">ReplicationApp.exe</span></span>
    
  - <span data-ttu-id="5f62c-130">RtcHost.exe</span><span class="sxs-lookup"><span data-stu-id="5f62c-130">RtcHost.exe</span></span>
    
  - <span data-ttu-id="5f62c-131">RTCSrv.exe</span><span class="sxs-lookup"><span data-stu-id="5f62c-131">RTCSrv.exe</span></span>
    
  - <span data-ttu-id="5f62c-132">XmppProxy.exe</span><span class="sxs-lookup"><span data-stu-id="5f62c-132">XmppProxy.exe</span></span>
    
  - <span data-ttu-id="5f62c-133">XmppTGW.exe</span><span class="sxs-lookup"><span data-stu-id="5f62c-133">XmppTGW.exe</span></span>
    
- <span data-ttu-id="5f62c-134">Processos de Serviço de Host do Windows Fabric:</span><span class="sxs-lookup"><span data-stu-id="5f62c-134">Windows Fabric Host Service processes:</span></span>
    
  - <span data-ttu-id="5f62c-135">Fabric.exe</span><span class="sxs-lookup"><span data-stu-id="5f62c-135">Fabric.exe</span></span>
    
  - <span data-ttu-id="5f62c-136">FabricDCA.exe</span><span class="sxs-lookup"><span data-stu-id="5f62c-136">FabricDCA.exe</span></span>
    
  - <span data-ttu-id="5f62c-137">FabricHost.exe</span><span class="sxs-lookup"><span data-stu-id="5f62c-137">FabricHost.exe</span></span>
    
- <span data-ttu-id="5f62c-138">Processos IIS:</span><span class="sxs-lookup"><span data-stu-id="5f62c-138">IIS processes:</span></span>
    
  - <span data-ttu-id="5f62c-139">%systemroot%\system32\inetsrv\w3wp.exe</span><span class="sxs-lookup"><span data-stu-id="5f62c-139">%systemroot%\system32\inetsrv\w3wp.exe</span></span>
    
  - <span data-ttu-id="5f62c-140">%systemroot%\SysWOW64\inetsrv\w3wp.exe</span><span class="sxs-lookup"><span data-stu-id="5f62c-140">%systemroot%\SysWOW64\inetsrv\w3wp.exe</span></span>
    
- <span data-ttu-id="5f62c-141">Processos SQL Server Back-End:</span><span class="sxs-lookup"><span data-stu-id="5f62c-141">SQL Server Back-End processes:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="5f62c-142">Observe que estes caminhos são específicos para versão do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="5f62c-142">Note that these paths are specific to SQL Server version.</span></span> 
  
  - <span data-ttu-id="5f62c-143">%ProgramFiles%\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="5f62c-143">%ProgramFiles%\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Binn\SQLServr.exe</span></span>
    
  - <span data-ttu-id="5f62c-144">%ProgramFiles%\Microsoft SQL Server\MSRS11.MSSQLSERVER\Reporting Services\ReportServer\Bin\ReportingServicesService.exe</span><span class="sxs-lookup"><span data-stu-id="5f62c-144">%ProgramFiles%\Microsoft SQL Server\MSRS11.MSSQLSERVER\Reporting Services\ReportServer\Bin\ReportingServicesService.exe</span></span>
    
  - <span data-ttu-id="5f62c-145">%ProgramFiles%\Microsoft SQL Server\MSAS11.MSSQLSERVER\OLAP\Bin\MSMDSrv.exe</span><span class="sxs-lookup"><span data-stu-id="5f62c-145">%ProgramFiles%\Microsoft SQL Server\MSAS11.MSSQLSERVER\OLAP\Bin\MSMDSrv.exe</span></span>
    
- <span data-ttu-id="5f62c-146">Processos SQL Server Front-End:</span><span class="sxs-lookup"><span data-stu-id="5f62c-146">SQL Server Front-End processes:</span></span>
    
  - <span data-ttu-id="5f62c-147">%ProgramFiles%\Microsoft SQL Server\MSSQL12.LYNCLOCAL\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="5f62c-147">%ProgramFiles%\Microsoft SQL Server\MSSQL12.LYNCLOCAL\MSSQL\Binn\SQLServr.exe</span></span>
    
  - <span data-ttu-id="5f62c-148">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTCLOCAL\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="5f62c-148">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTCLOCAL\MSSQL\Binn\SQLServr.exe</span></span>
    
  - <span data-ttu-id="5f62c-149">Instância RTC de Instalação Padrão de Edição</span><span class="sxs-lookup"><span data-stu-id="5f62c-149">Standard Edition Installation RTC Instance</span></span> 
    
  - <span data-ttu-id="5f62c-150">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTC\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="5f62c-150">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTC\MSSQL\Binn\SQLServr.exe</span></span>
    
- <span data-ttu-id="5f62c-151">Diretórios e arquivos:</span><span class="sxs-lookup"><span data-stu-id="5f62c-151">Directories and files:</span></span>
    
  - <span data-ttu-id="5f62c-152">%systemroot%\system32\LogFiles</span><span class="sxs-lookup"><span data-stu-id="5f62c-152">%systemroot%\System32\LogFiles</span></span>
    
  - <span data-ttu-id="5f62c-153">%systemroot%\SysWow64\LogFiles</span><span class="sxs-lookup"><span data-stu-id="5f62c-153">%systemroot%\SysWow64\LogFiles</span></span>
    
  - <span data-ttu-id="5f62c-154">%systemroot%\Microsoft.NET\assembly\GAC_MSIL</span><span class="sxs-lookup"><span data-stu-id="5f62c-154">%systemroot%\Microsoft.NET\assembly\GAC_MSIL</span></span>
    
  - <span data-ttu-id="5f62c-155">%programfiles%\Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="5f62c-155">%programfiles%\Skype for Business Server 2015</span></span>
    
  - <span data-ttu-id="5f62c-156">%programfiles%\Common Files\Skype for Business Server 2015\Watcher Node</span><span class="sxs-lookup"><span data-stu-id="5f62c-156">%programfiles%\Common Files\Skype for Business Server 2015\Watcher Node</span></span>
    
  - <span data-ttu-id="5f62c-157">%programfiles%\Common Files\Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="5f62c-157">%programfiles%\Common Files\Skype for Business Server 2015</span></span>
    
  - <span data-ttu-id="5f62c-158">%programfiles%\Common Files\Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="5f62c-158">%programfiles%\Common Files\Skype for Business Online</span></span>
    
  - <span data-ttu-id="5f62c-159">%SystemDrive%\RtcReplicaRoot</span><span class="sxs-lookup"><span data-stu-id="5f62c-159">%SystemDrive%\RtcReplicaRoot</span></span>
    
  - <span data-ttu-id="5f62c-p103">Repositório de compartilhamento de arquivo(específico no Construtor de Topologias). Os repositórios de arquivos são especificados no Construtor de Topologias.</span><span class="sxs-lookup"><span data-stu-id="5f62c-p103">File share store (specified in Topology Builder). File stores are specified in Topology Builder.</span></span>
    
  - <span data-ttu-id="5f62c-162">Os arquivos de logs e dados do SQL Server, incluindo aqueles para o banco de dados de back-end, armazenamento de usuário, arquivamento, monitoramento, e repositório de application.</span><span class="sxs-lookup"><span data-stu-id="5f62c-162">SQL Server data and log files, including those for the back-end database, user store, archiving store, monitoring store, and application store.</span></span> <span data-ttu-id="5f62c-163">Os arquivos da base de dados e os logs podem ser especificados no Construtor de Topologias.</span><span class="sxs-lookup"><span data-stu-id="5f62c-163">Database and log files can be specified in Topology Builder.</span></span> <span data-ttu-id="5f62c-164">Para obter detalhes sobre os arquivos de dados e log para cada banco de dados, incluindo nomes padrão, consulte a [localização do arquivo de Log e de dados do SQL Server](http://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="5f62c-164">For details about the data and log files for each database, including default names, see [SQL Server Data and Log File Placement](http://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) in the Deployment documentation.</span></span>
    
  - <span data-ttu-id="5f62c-165">Arquivos do SQL Server dados e log, incluindo aqueles para o banco de dados front-end, Skype para repositório corporativo e RtcDatabase repositório.</span><span class="sxs-lookup"><span data-stu-id="5f62c-165">SQL Server data and log files, including those for the Front-end database, Skype for Business store, and RtcDatabase store.</span></span> <span data-ttu-id="5f62c-166">Normalmente, eles estão sob %localdrive%\CSData.</span><span class="sxs-lookup"><span data-stu-id="5f62c-166">They are normally under %localdrive%\CSData.</span></span>
    

