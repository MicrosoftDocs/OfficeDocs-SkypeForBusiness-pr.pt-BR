---
title: Exclusões de verificação antivírus do Skype for Business Server
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
ms.openlocfilehash: b59a5c474a96d312ebe3a648536ebe827e684931
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832261"
---
# <a name="antivirus-scanning-exclusions-for-skype-for-business-server"></a><span data-ttu-id="ac208-103">Exclusões de verificação antivírus do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="ac208-103">Antivirus scanning exclusions for Skype for Business Server</span></span>

<span data-ttu-id="ac208-104">Visão geral da interoperação do scanner antivírus com o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="ac208-104">Overview of antivirus scanner interoperation with Skype for Business Server.</span></span>

<span data-ttu-id="ac208-105">Para garantir que o scanner antivírus não interfira com a operação do Skype for Business Server, você deve excluir processos e diretórios específicos para cada servidor ou função de servidor do Skype for Business Server no qual você executar um scanner antivírus.</span><span class="sxs-lookup"><span data-stu-id="ac208-105">To ensure that the antivirus scanner does not interfere with the operation of Skype for Business Server, you must exclude specific processes and directories for each Skype for Business Server server or server role on which you run an antivirus scanner.</span></span> <span data-ttu-id="ac208-106">Os seguintes processos e diretórios devem ser excluídos:</span><span class="sxs-lookup"><span data-stu-id="ac208-106">The following processes and directories should be excluded:</span></span>

> [!NOTE]
> <span data-ttu-id="ac208-107">Os locais de pasta e arquivo listados abaixo são os locais padrão do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="ac208-107">Folder and file locations listed below are the default locations for Skype for Business Server.</span></span> <span data-ttu-id="ac208-108">Para os locais nos quais você não usou o padrão, exclua os locais especificados para a sua organização em vez dos locais padrão especificados neste tópico.</span><span class="sxs-lookup"><span data-stu-id="ac208-108">For any locations for which you did not use the default, exclude the locations you specified for your organization instead of the default locations specified in this topic.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ac208-109">Observe que alguns programas antivírus podem precisar de caminhos absolutos, não relativos, para sua lista de exclusão.</span><span class="sxs-lookup"><span data-stu-id="ac208-109">Please note that some antivirus programs may need absolute, not relative paths, for their exclusion list.</span></span>

- <span data-ttu-id="ac208-110">Processos do Skype for Business Server:</span><span class="sxs-lookup"><span data-stu-id="ac208-110">Skype for Business Server processes:</span></span>

  - <span data-ttu-id="ac208-111">ABServer.exe</span><span class="sxs-lookup"><span data-stu-id="ac208-111">ABServer.exe</span></span>

  - <span data-ttu-id="ac208-112">ASMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="ac208-112">ASMCUSvc.exe</span></span>

  - <span data-ttu-id="ac208-113">AVMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="ac208-113">AVMCUSvc.exe</span></span>

  - <span data-ttu-id="ac208-114">ChannelService.exe</span><span class="sxs-lookup"><span data-stu-id="ac208-114">ChannelService.exe</span></span>

  - <span data-ttu-id="ac208-115">ClsAgent.exe</span><span class="sxs-lookup"><span data-stu-id="ac208-115">ClsAgent.exe</span></span>

  - <span data-ttu-id="ac208-116">ComplianceService.exe</span><span class="sxs-lookup"><span data-stu-id="ac208-116">ComplianceService.exe</span></span>

  - <span data-ttu-id="ac208-117">DataMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="ac208-117">DataMCUSvc.exe</span></span>

  - <span data-ttu-id="ac208-118">DataProxy.exe</span><span class="sxs-lookup"><span data-stu-id="ac208-118">DataProxy.exe</span></span>

  - <span data-ttu-id="ac208-119">FileTransferAgent.exe</span><span class="sxs-lookup"><span data-stu-id="ac208-119">FileTransferAgent.exe</span></span>

  - <span data-ttu-id="ac208-120">HealthAgent.exe</span><span class="sxs-lookup"><span data-stu-id="ac208-120">HealthAgent.exe</span></span>

  - <span data-ttu-id="ac208-121">IMMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="ac208-121">IMMCUSvc.exe</span></span>
  
  - <span data-ttu-id="ac208-122">LyncBackupService.exe</span><span class="sxs-lookup"><span data-stu-id="ac208-122">LyncBackupService.exe</span></span>

  - <span data-ttu-id="ac208-123">LysSvc.exe</span><span class="sxs-lookup"><span data-stu-id="ac208-123">LysSvc.exe</span></span>

  - <span data-ttu-id="ac208-124">MasterReplicatorAgent.exe</span><span class="sxs-lookup"><span data-stu-id="ac208-124">MasterReplicatorAgent.exe</span></span>

  - <span data-ttu-id="ac208-125">MediaRelaySvc.exe</span><span class="sxs-lookup"><span data-stu-id="ac208-125">MediaRelaySvc.exe</span></span>

  - <span data-ttu-id="ac208-126">MediationServerSvc.exe</span><span class="sxs-lookup"><span data-stu-id="ac208-126">MediationServerSvc.exe</span></span>

  - <span data-ttu-id="ac208-127">MRASSvc.exe</span><span class="sxs-lookup"><span data-stu-id="ac208-127">MRASSvc.exe</span></span>

  - <span data-ttu-id="ac208-128">OcsAppServerHost.exe</span><span class="sxs-lookup"><span data-stu-id="ac208-128">OcsAppServerHost.exe</span></span>

  - <span data-ttu-id="ac208-129">ReplicaReplicatorAgent.exe</span><span class="sxs-lookup"><span data-stu-id="ac208-129">ReplicaReplicatorAgent.exe</span></span>

  - <span data-ttu-id="ac208-130">ReplicationApp.exe</span><span class="sxs-lookup"><span data-stu-id="ac208-130">ReplicationApp.exe</span></span>

  - <span data-ttu-id="ac208-131">RtcHost.exe</span><span class="sxs-lookup"><span data-stu-id="ac208-131">RtcHost.exe</span></span>

  - <span data-ttu-id="ac208-132">RTCSrv.exe</span><span class="sxs-lookup"><span data-stu-id="ac208-132">RTCSrv.exe</span></span>

  - <span data-ttu-id="ac208-133">XmppProxy.exe</span><span class="sxs-lookup"><span data-stu-id="ac208-133">XmppProxy.exe</span></span>

  - <span data-ttu-id="ac208-134">XmppTGW.exe</span><span class="sxs-lookup"><span data-stu-id="ac208-134">XmppTGW.exe</span></span>

- <span data-ttu-id="ac208-135">Processos do Windows Fabric Host Service:</span><span class="sxs-lookup"><span data-stu-id="ac208-135">Windows Fabric Host Service processes:</span></span>

  - <span data-ttu-id="ac208-136">Fabric.exe</span><span class="sxs-lookup"><span data-stu-id="ac208-136">Fabric.exe</span></span>

  - <span data-ttu-id="ac208-137">FabricDCA.exe</span><span class="sxs-lookup"><span data-stu-id="ac208-137">FabricDCA.exe</span></span>

  - <span data-ttu-id="ac208-138">FabricHost.exe</span><span class="sxs-lookup"><span data-stu-id="ac208-138">FabricHost.exe</span></span>

- <span data-ttu-id="ac208-139">Processos do IIS:</span><span class="sxs-lookup"><span data-stu-id="ac208-139">IIS processes:</span></span>

  - <span data-ttu-id="ac208-140">%systemroot%\system32\inetsrv\w3wp.exe</span><span class="sxs-lookup"><span data-stu-id="ac208-140">%systemroot%\system32\inetsrv\w3wp.exe</span></span>

  - <span data-ttu-id="ac208-141">%systemroot%\SysWOW64\inetsrv\w3wp.exe</span><span class="sxs-lookup"><span data-stu-id="ac208-141">%systemroot%\SysWOW64\inetsrv\w3wp.exe</span></span>

- <span data-ttu-id="ac208-142">Processos de Back-End SQL Server:</span><span class="sxs-lookup"><span data-stu-id="ac208-142">SQL Server Back-End processes:</span></span>

    > [!NOTE]
    > <span data-ttu-id="ac208-143">Observe que esses caminhos são específicos da versão do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ac208-143">Note that these paths are specific to SQL Server version.</span></span>

  - <span data-ttu-id="ac208-144">%ProgramFiles%\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="ac208-144">%ProgramFiles%\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Binn\SQLServr.exe</span></span>

  - <span data-ttu-id="ac208-145">%ProgramFiles%\Microsoft SQL Server\MSRS11. MSSQLSERVER\Relatórios Services\ReportServer\Bin\ReportingServicesService.exe</span><span class="sxs-lookup"><span data-stu-id="ac208-145">%ProgramFiles%\Microsoft SQL Server\MSRS11.MSSQLSERVER\Reporting Services\ReportServer\Bin\ReportingServicesService.exe</span></span>

  - <span data-ttu-id="ac208-146">%ProgramFiles%\Microsoft SQL Server\MSAS11.MSSQLSERVER\OLAP\Bin\MSMDSrv.exe</span><span class="sxs-lookup"><span data-stu-id="ac208-146">%ProgramFiles%\Microsoft SQL Server\MSAS11.MSSQLSERVER\OLAP\Bin\MSMDSrv.exe</span></span>

- <span data-ttu-id="ac208-147">Processos de Front-End SQL Server:</span><span class="sxs-lookup"><span data-stu-id="ac208-147">SQL Server Front-End processes:</span></span>

  - <span data-ttu-id="ac208-148">%ProgramFiles%\Microsoft SQL Server\MSSQL12.LYNCLOCAL\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="ac208-148">%ProgramFiles%\Microsoft SQL Server\MSSQL12.LYNCLOCAL\MSSQL\Binn\SQLServr.exe</span></span>

  - <span data-ttu-id="ac208-149">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTCLOCAL\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="ac208-149">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTCLOCAL\MSSQL\Binn\SQLServr.exe</span></span>

  - <span data-ttu-id="ac208-150">Instância RTC de Instalação Standard Edition</span><span class="sxs-lookup"><span data-stu-id="ac208-150">Standard Edition Installation RTC Instance</span></span>

  - <span data-ttu-id="ac208-151">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTC\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="ac208-151">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTC\MSSQL\Binn\SQLServr.exe</span></span>

- <span data-ttu-id="ac208-152">Arquivos e diretórios:</span><span class="sxs-lookup"><span data-stu-id="ac208-152">Directories and files:</span></span>

  - <span data-ttu-id="ac208-153">%systemroot%\System32\LogFiles</span><span class="sxs-lookup"><span data-stu-id="ac208-153">%systemroot%\System32\LogFiles</span></span>

  - <span data-ttu-id="ac208-154">%systemroot%\SysWow64\LogFiles</span><span class="sxs-lookup"><span data-stu-id="ac208-154">%systemroot%\SysWow64\LogFiles</span></span>

  - <span data-ttu-id="ac208-155">%systemroot%\Microsoft.NET\assembly\GAC_MSIL</span><span class="sxs-lookup"><span data-stu-id="ac208-155">%systemroot%\Microsoft.NET\assembly\GAC_MSIL</span></span>

    > [!NOTE]
    > <span data-ttu-id="ac208-156">Observe que esses caminhos são específicos da versão do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="ac208-156">Note that these paths are specific to Skype for Business Server version.</span></span>

  - <span data-ttu-id="ac208-157">%programfiles%\Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="ac208-157">%programfiles%\Skype for Business Server 2015</span></span>

  - <span data-ttu-id="ac208-158">%programfiles%\Common Files\Skype for Business Server 2015\Watcher Node</span><span class="sxs-lookup"><span data-stu-id="ac208-158">%programfiles%\Common Files\Skype for Business Server 2015\Watcher Node</span></span>

  - <span data-ttu-id="ac208-159">%programfiles%\Common Files\Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="ac208-159">%programfiles%\Common Files\Skype for Business Server 2015</span></span>

  - <span data-ttu-id="ac208-160">%programfiles%\Common Files\Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="ac208-160">%programfiles%\Common Files\Skype for Business Online</span></span>

  - <span data-ttu-id="ac208-161">%SystemDrive%\RtcReplicaRoot</span><span class="sxs-lookup"><span data-stu-id="ac208-161">%SystemDrive%\RtcReplicaRoot</span></span>

  - <span data-ttu-id="ac208-p103">O repositório de compartilhamento de arquivo (especificado no Construtor de Topologias). Os repositórios de arquivo estão especificados no Construtor de Topologias.</span><span class="sxs-lookup"><span data-stu-id="ac208-p103">File share store (specified in Topology Builder). File stores are specified in Topology Builder.</span></span>

  - <span data-ttu-id="ac208-164">Os dados e arquivos de log do  SQL Server, incluindo para o banco de dados de Back-End, repositório de usuários, repositório de arquivamento, repositório de monitoramento e repositório do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="ac208-164">SQL Server data and log files, including those for the back-end database, user store, archiving store, monitoring store, and application store.</span></span> <span data-ttu-id="ac208-165">Os arquivos de log e banco de dados podem ser especificados no Construtor de Topologias.</span><span class="sxs-lookup"><span data-stu-id="ac208-165">Database and log files can be specified in Topology Builder.</span></span> <span data-ttu-id="ac208-166">Para obter detalhes sobre os arquivos de dados e de log para cada banco de dados, incluindo nomes padrão, consulte [SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) na documentação de Implantação.</span><span class="sxs-lookup"><span data-stu-id="ac208-166">For details about the data and log files for each database, including default names, see [SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) in the Deployment documentation.</span></span>

  - <span data-ttu-id="ac208-167">Arquivos de log e dados do SQL Server, incluindo aqueles para o banco de dados front-end, o armazenamento do Skype for Business e o armazenamento RtcDatabase.</span><span class="sxs-lookup"><span data-stu-id="ac208-167">SQL Server data and log files, including those for the Front-end database, Skype for Business store, and RtcDatabase store.</span></span> <span data-ttu-id="ac208-168">Normalmente, eles estão em %localdrive%\CSData.</span><span class="sxs-lookup"><span data-stu-id="ac208-168">They are normally under %localdrive%\CSData.</span></span>


