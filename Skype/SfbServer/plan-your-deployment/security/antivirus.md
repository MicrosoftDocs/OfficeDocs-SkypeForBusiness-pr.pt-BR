---
title: Exclusões de verificação de antivírus para o Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 5d742259-ef3b-417a-920b-e1fa0e48f043
description: Visão geral da interoperação do scanner antivírus com o Skype for Business Server.
ms.openlocfilehash: 64646304b98de075fd9af0a82096da8c0bff2f12
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51104237"
---
# <a name="antivirus-scanning-exclusions-for-skype-for-business-server"></a><span data-ttu-id="cc09f-103">Exclusões de verificação de antivírus para o Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="cc09f-103">Antivirus scanning exclusions for Skype for Business Server</span></span>

<span data-ttu-id="cc09f-104">Visão geral da interoperação do scanner antivírus com o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="cc09f-104">Overview of antivirus scanner interoperation with Skype for Business Server.</span></span>

<span data-ttu-id="cc09f-105">Para garantir que o scanner antivírus não interfira na operação do Skype for Business Server, você deve excluir processos e diretórios específicos para cada servidor do Skype for Business Server ou função de servidor na qual você execute um scanner antivírus.</span><span class="sxs-lookup"><span data-stu-id="cc09f-105">To ensure that the antivirus scanner does not interfere with the operation of Skype for Business Server, you must exclude specific processes and directories for each Skype for Business Server server or server role on which you run an antivirus scanner.</span></span> <span data-ttu-id="cc09f-106">Os seguintes processos e diretórios devem ser excluídos:</span><span class="sxs-lookup"><span data-stu-id="cc09f-106">The following processes and directories should be excluded:</span></span>

> [!NOTE]
> <span data-ttu-id="cc09f-107">Os locais de pasta e arquivo listados abaixo são os locais padrão para o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="cc09f-107">Folder and file locations listed below are the default locations for Skype for Business Server.</span></span> <span data-ttu-id="cc09f-108">Para os locais nos quais você não usou o padrão, exclua os locais especificados para a sua organização em vez dos locais padrão especificados neste tópico.</span><span class="sxs-lookup"><span data-stu-id="cc09f-108">For any locations for which you did not use the default, exclude the locations you specified for your organization instead of the default locations specified in this topic.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cc09f-109">Observe que alguns programas antivírus podem precisar de caminhos absolutos, não relativos, para sua lista de exclusão.</span><span class="sxs-lookup"><span data-stu-id="cc09f-109">Please note that some antivirus programs may need absolute, not relative paths, for their exclusion list.</span></span>

- <span data-ttu-id="cc09f-110">Processos do Skype for Business Server:</span><span class="sxs-lookup"><span data-stu-id="cc09f-110">Skype for Business Server processes:</span></span>

  - <span data-ttu-id="cc09f-111">ABServer.exe</span><span class="sxs-lookup"><span data-stu-id="cc09f-111">ABServer.exe</span></span>

  - <span data-ttu-id="cc09f-112">ASMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="cc09f-112">ASMCUSvc.exe</span></span>

  - <span data-ttu-id="cc09f-113">AVMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="cc09f-113">AVMCUSvc.exe</span></span>

  - <span data-ttu-id="cc09f-114">ChannelService.exe</span><span class="sxs-lookup"><span data-stu-id="cc09f-114">ChannelService.exe</span></span>

  - <span data-ttu-id="cc09f-115">ClsAgent.exe</span><span class="sxs-lookup"><span data-stu-id="cc09f-115">ClsAgent.exe</span></span>

  - <span data-ttu-id="cc09f-116">ComplianceService.exe</span><span class="sxs-lookup"><span data-stu-id="cc09f-116">ComplianceService.exe</span></span>

  - <span data-ttu-id="cc09f-117">DataMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="cc09f-117">DataMCUSvc.exe</span></span>

  - <span data-ttu-id="cc09f-118">DataProxy.exe</span><span class="sxs-lookup"><span data-stu-id="cc09f-118">DataProxy.exe</span></span>

  - <span data-ttu-id="cc09f-119">FileTransferAgent.exe</span><span class="sxs-lookup"><span data-stu-id="cc09f-119">FileTransferAgent.exe</span></span>

  - <span data-ttu-id="cc09f-120">HealthAgent.exe</span><span class="sxs-lookup"><span data-stu-id="cc09f-120">HealthAgent.exe</span></span>

  - <span data-ttu-id="cc09f-121">IMMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="cc09f-121">IMMCUSvc.exe</span></span>
  
  - <span data-ttu-id="cc09f-122">LyncBackupService.exe</span><span class="sxs-lookup"><span data-stu-id="cc09f-122">LyncBackupService.exe</span></span>

  - <span data-ttu-id="cc09f-123">LysSvc.exe</span><span class="sxs-lookup"><span data-stu-id="cc09f-123">LysSvc.exe</span></span>

  - <span data-ttu-id="cc09f-124">MasterReplicatorAgent.exe</span><span class="sxs-lookup"><span data-stu-id="cc09f-124">MasterReplicatorAgent.exe</span></span>

  - <span data-ttu-id="cc09f-125">MediaRelaySvc.exe</span><span class="sxs-lookup"><span data-stu-id="cc09f-125">MediaRelaySvc.exe</span></span>

  - <span data-ttu-id="cc09f-126">MediationServerSvc.exe</span><span class="sxs-lookup"><span data-stu-id="cc09f-126">MediationServerSvc.exe</span></span>

  - <span data-ttu-id="cc09f-127">MRASSvc.exe</span><span class="sxs-lookup"><span data-stu-id="cc09f-127">MRASSvc.exe</span></span>

  - <span data-ttu-id="cc09f-128">OcsAppServerHost.exe</span><span class="sxs-lookup"><span data-stu-id="cc09f-128">OcsAppServerHost.exe</span></span>

  - <span data-ttu-id="cc09f-129">ReplicaReplicatorAgent.exe</span><span class="sxs-lookup"><span data-stu-id="cc09f-129">ReplicaReplicatorAgent.exe</span></span>

  - <span data-ttu-id="cc09f-130">ReplicationApp.exe</span><span class="sxs-lookup"><span data-stu-id="cc09f-130">ReplicationApp.exe</span></span>

  - <span data-ttu-id="cc09f-131">RtcHost.exe</span><span class="sxs-lookup"><span data-stu-id="cc09f-131">RtcHost.exe</span></span>

  - <span data-ttu-id="cc09f-132">RTCSrv.exe</span><span class="sxs-lookup"><span data-stu-id="cc09f-132">RTCSrv.exe</span></span>

  - <span data-ttu-id="cc09f-133">XmppProxy.exe</span><span class="sxs-lookup"><span data-stu-id="cc09f-133">XmppProxy.exe</span></span>

  - <span data-ttu-id="cc09f-134">XmppTGW.exe</span><span class="sxs-lookup"><span data-stu-id="cc09f-134">XmppTGW.exe</span></span>

- <span data-ttu-id="cc09f-135">Processos do Windows Fabric Host Service:</span><span class="sxs-lookup"><span data-stu-id="cc09f-135">Windows Fabric Host Service processes:</span></span>

  - <span data-ttu-id="cc09f-136">Fabric.exe</span><span class="sxs-lookup"><span data-stu-id="cc09f-136">Fabric.exe</span></span>

  - <span data-ttu-id="cc09f-137">FabricDCA.exe</span><span class="sxs-lookup"><span data-stu-id="cc09f-137">FabricDCA.exe</span></span>

  - <span data-ttu-id="cc09f-138">FabricHost.exe</span><span class="sxs-lookup"><span data-stu-id="cc09f-138">FabricHost.exe</span></span>

- <span data-ttu-id="cc09f-139">Processos do IIS:</span><span class="sxs-lookup"><span data-stu-id="cc09f-139">IIS processes:</span></span>

  - <span data-ttu-id="cc09f-140">%systemroot%\system32\inetsrv\w3wp.exe</span><span class="sxs-lookup"><span data-stu-id="cc09f-140">%systemroot%\system32\inetsrv\w3wp.exe</span></span>

  - <span data-ttu-id="cc09f-141">%systemroot%\SysWOW64\inetsrv\w3wp.exe</span><span class="sxs-lookup"><span data-stu-id="cc09f-141">%systemroot%\SysWOW64\inetsrv\w3wp.exe</span></span>

- <span data-ttu-id="cc09f-142">SQL Server Back-End processos:</span><span class="sxs-lookup"><span data-stu-id="cc09f-142">SQL Server Back-End processes:</span></span>

    > [!NOTE]
    > <span data-ttu-id="cc09f-143">Observe que esses caminhos são específicos para SQL Server versão.</span><span class="sxs-lookup"><span data-stu-id="cc09f-143">Note that these paths are specific to SQL Server version.</span></span>

  - <span data-ttu-id="cc09f-144">%ProgramFiles%\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="cc09f-144">%ProgramFiles%\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Binn\SQLServr.exe</span></span>

  - <span data-ttu-id="cc09f-145">%ProgramFiles%\Microsoft SQL Server\MSRS11. MSSQLSERVER\Reporting Services\ReportServer\Bin\ReportingServicesService.exe</span><span class="sxs-lookup"><span data-stu-id="cc09f-145">%ProgramFiles%\Microsoft SQL Server\MSRS11.MSSQLSERVER\Reporting Services\ReportServer\Bin\ReportingServicesService.exe</span></span>

  - <span data-ttu-id="cc09f-146">%ProgramFiles%\Microsoft SQL Server\MSAS11.MSSQLSERVER\OLAP\Bin\MSMDSrv.exe</span><span class="sxs-lookup"><span data-stu-id="cc09f-146">%ProgramFiles%\Microsoft SQL Server\MSAS11.MSSQLSERVER\OLAP\Bin\MSMDSrv.exe</span></span>

- <span data-ttu-id="cc09f-147">SQL Server Front-End processos:</span><span class="sxs-lookup"><span data-stu-id="cc09f-147">SQL Server Front-End processes:</span></span>

  - <span data-ttu-id="cc09f-148">%ProgramFiles%\Microsoft SQL Server\MSSQL12.LYNCLOCAL\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="cc09f-148">%ProgramFiles%\Microsoft SQL Server\MSSQL12.LYNCLOCAL\MSSQL\Binn\SQLServr.exe</span></span>

  - <span data-ttu-id="cc09f-149">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTCLOCAL\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="cc09f-149">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTCLOCAL\MSSQL\Binn\SQLServr.exe</span></span>

  - <span data-ttu-id="cc09f-150">Instância RTC de Instalação standard Edition</span><span class="sxs-lookup"><span data-stu-id="cc09f-150">Standard Edition Installation RTC Instance</span></span>

  - <span data-ttu-id="cc09f-151">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTC\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="cc09f-151">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTC\MSSQL\Binn\SQLServr.exe</span></span>

- <span data-ttu-id="cc09f-152">Arquivos e diretórios:</span><span class="sxs-lookup"><span data-stu-id="cc09f-152">Directories and files:</span></span>

  - <span data-ttu-id="cc09f-153">%systemroot%\System32\LogFiles</span><span class="sxs-lookup"><span data-stu-id="cc09f-153">%systemroot%\System32\LogFiles</span></span>

  - <span data-ttu-id="cc09f-154">%systemroot%\SysWow64\LogFiles</span><span class="sxs-lookup"><span data-stu-id="cc09f-154">%systemroot%\SysWow64\LogFiles</span></span>

  - <span data-ttu-id="cc09f-155">%systemroot%\Microsoft.NET\assembly\GAC_MSIL</span><span class="sxs-lookup"><span data-stu-id="cc09f-155">%systemroot%\Microsoft.NET\assembly\GAC_MSIL</span></span>

    > [!NOTE]
    > <span data-ttu-id="cc09f-156">Observe que esses caminhos são específicos da versão do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="cc09f-156">Note that these paths are specific to Skype for Business Server version.</span></span>

  - <span data-ttu-id="cc09f-157">%programfiles%\Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="cc09f-157">%programfiles%\Skype for Business Server 2015</span></span>

  - <span data-ttu-id="cc09f-158">%programfiles%\Common Files\Skype for Business Server 2015\Nó do Watcher</span><span class="sxs-lookup"><span data-stu-id="cc09f-158">%programfiles%\Common Files\Skype for Business Server 2015\Watcher Node</span></span>

  - <span data-ttu-id="cc09f-159">%programfiles%\Common Files\Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="cc09f-159">%programfiles%\Common Files\Skype for Business Server 2015</span></span>

  - <span data-ttu-id="cc09f-160">%programfiles%\Common Files\Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="cc09f-160">%programfiles%\Common Files\Skype for Business Online</span></span>

  - <span data-ttu-id="cc09f-161">%SystemDrive%\RtcReplicaRoot</span><span class="sxs-lookup"><span data-stu-id="cc09f-161">%SystemDrive%\RtcReplicaRoot</span></span>

  - <span data-ttu-id="cc09f-p103">O repositório de compartilhamento de arquivo (especificado no Construtor de Topologias). Os repositórios de arquivo estão especificados no Construtor de Topologias.</span><span class="sxs-lookup"><span data-stu-id="cc09f-p103">File share store (specified in Topology Builder). File stores are specified in Topology Builder.</span></span>

  - <span data-ttu-id="cc09f-164">Os dados e arquivos de log do  SQL Server, incluindo para o banco de dados de Back-End, repositório de usuários, repositório de arquivamento, repositório de monitoramento e repositório do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="cc09f-164">SQL Server data and log files, including those for the back-end database, user store, archiving store, monitoring store, and application store.</span></span> <span data-ttu-id="cc09f-165">Os arquivos de log e banco de dados podem ser especificados no Construtor de Topologias.</span><span class="sxs-lookup"><span data-stu-id="cc09f-165">Database and log files can be specified in Topology Builder.</span></span> <span data-ttu-id="cc09f-166">Para obter detalhes sobre os arquivos de dados e de log para cada banco de dados, incluindo nomes padrão, consulte [SQL Server Data and Log File Placement](/previous-versions/office/lync-server-2013/lync-server-2013-sql-server-data-and-log-file-placement) na documentação de Implantação.</span><span class="sxs-lookup"><span data-stu-id="cc09f-166">For details about the data and log files for each database, including default names, see [SQL Server Data and Log File Placement](/previous-versions/office/lync-server-2013/lync-server-2013-sql-server-data-and-log-file-placement) in the Deployment documentation.</span></span>

  - <span data-ttu-id="cc09f-167">SQL Server dados e arquivos de log, incluindo aqueles para o banco de dados front-end, o armazenamento do Skype for Business e o armazenamento RtcDatabase.</span><span class="sxs-lookup"><span data-stu-id="cc09f-167">SQL Server data and log files, including those for the Front-end database, Skype for Business store, and RtcDatabase store.</span></span> <span data-ttu-id="cc09f-168">Eles normalmente estão em %localdrive%\CSData.</span><span class="sxs-lookup"><span data-stu-id="cc09f-168">They are normally under %localdrive%\CSData.</span></span>