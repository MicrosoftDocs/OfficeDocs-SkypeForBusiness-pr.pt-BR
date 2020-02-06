---
title: Exclusões de verificação antivírus para o Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 5d742259-ef3b-417a-920b-e1fa0e48f043
description: Visão geral da interoperação do verificador de antivírus com o Skype for Business Server.
ms.openlocfilehash: 10d296e36324fdbc8bca8f7da48370d619774501
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815689"
---
# <a name="antivirus-scanning-exclusions-for-skype-for-business-server"></a><span data-ttu-id="cc900-103">Exclusões de verificação antivírus para o Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="cc900-103">Antivirus scanning exclusions for Skype for Business Server</span></span>

<span data-ttu-id="cc900-104">Visão geral da interoperação do verificador de antivírus com o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="cc900-104">Overview of antivirus scanner interoperation with Skype for Business Server.</span></span>

<span data-ttu-id="cc900-105">Para garantir que o verificador de vírus não interfira com a operação do Skype for Business Server, você deve excluir processos e diretórios específicos para cada função de servidor ou servidor do Skype for Business Server na qual você executa um scanner antivírus.</span><span class="sxs-lookup"><span data-stu-id="cc900-105">To ensure that the antivirus scanner does not interfere with the operation of Skype for Business Server, you must exclude specific processes and directories for each Skype for Business Server server or server role on which you run an antivirus scanner.</span></span> <span data-ttu-id="cc900-106">Os seguintes processos e diretórios devem ser excluídos:</span><span class="sxs-lookup"><span data-stu-id="cc900-106">The following processes and directories should be excluded:</span></span>

> [!NOTE]
> <span data-ttu-id="cc900-107">Os locais de pasta e arquivo listados abaixo são os locais padrão do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="cc900-107">Folder and file locations listed below are the default locations for Skype for Business Server.</span></span> <span data-ttu-id="cc900-108">Para quaisquer locais, para os quais você não usa o padrão, exclua os locais que você especificou para a sua organização em vez dos locais padrão especificados neste tópico.</span><span class="sxs-lookup"><span data-stu-id="cc900-108">For any locations for which you did not use the default, exclude the locations you specified for your organization instead of the default locations specified in this topic.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cc900-109">Observe que alguns programas antivírus podem precisar de caminhos absolutos e não relativos, para a sua lista de exclusão.</span><span class="sxs-lookup"><span data-stu-id="cc900-109">Please note that some antivirus programs may need absolute, not relative paths, for their exclusion list.</span></span>

- <span data-ttu-id="cc900-110">Processos do Skype for Business Server:</span><span class="sxs-lookup"><span data-stu-id="cc900-110">Skype for Business Server processes:</span></span>

  - <span data-ttu-id="cc900-111">ABServer.exe</span><span class="sxs-lookup"><span data-stu-id="cc900-111">ABServer.exe</span></span>

  - <span data-ttu-id="cc900-112">ASMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="cc900-112">ASMCUSvc.exe</span></span>

  - <span data-ttu-id="cc900-113">AVMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="cc900-113">AVMCUSvc.exe</span></span>

  - <span data-ttu-id="cc900-114">ChannelService.exe</span><span class="sxs-lookup"><span data-stu-id="cc900-114">ChannelService.exe</span></span>

  - <span data-ttu-id="cc900-115">ClsAgent.exe</span><span class="sxs-lookup"><span data-stu-id="cc900-115">ClsAgent.exe</span></span>

  - <span data-ttu-id="cc900-116">ComplianceService.exe</span><span class="sxs-lookup"><span data-stu-id="cc900-116">ComplianceService.exe</span></span>

  - <span data-ttu-id="cc900-117">DataMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="cc900-117">DataMCUSvc.exe</span></span>

  - <span data-ttu-id="cc900-118">DataProxy.exe</span><span class="sxs-lookup"><span data-stu-id="cc900-118">DataProxy.exe</span></span>

  - <span data-ttu-id="cc900-119">FileTransferAgent.exe</span><span class="sxs-lookup"><span data-stu-id="cc900-119">FileTransferAgent.exe</span></span>

  - <span data-ttu-id="cc900-120">HealthAgent.exe</span><span class="sxs-lookup"><span data-stu-id="cc900-120">HealthAgent.exe</span></span>

  - <span data-ttu-id="cc900-121">IMMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="cc900-121">IMMCUSvc.exe</span></span>
  
  - <span data-ttu-id="cc900-122">LyncBackupService. exe</span><span class="sxs-lookup"><span data-stu-id="cc900-122">LyncBackupService.exe</span></span>

  - <span data-ttu-id="cc900-123">LysSvc.exe</span><span class="sxs-lookup"><span data-stu-id="cc900-123">LysSvc.exe</span></span>

  - <span data-ttu-id="cc900-124">MasterReplicatorAgent.exe</span><span class="sxs-lookup"><span data-stu-id="cc900-124">MasterReplicatorAgent.exe</span></span>

  - <span data-ttu-id="cc900-125">MediaRelaySvc.exe</span><span class="sxs-lookup"><span data-stu-id="cc900-125">MediaRelaySvc.exe</span></span>

  - <span data-ttu-id="cc900-126">MediationServerSvc.exe</span><span class="sxs-lookup"><span data-stu-id="cc900-126">MediationServerSvc.exe</span></span>

  - <span data-ttu-id="cc900-127">MRASSvc.exe</span><span class="sxs-lookup"><span data-stu-id="cc900-127">MRASSvc.exe</span></span>

  - <span data-ttu-id="cc900-128">OcsAppServerHost.exe</span><span class="sxs-lookup"><span data-stu-id="cc900-128">OcsAppServerHost.exe</span></span>

  - <span data-ttu-id="cc900-129">ReplicaReplicatorAgent.exe</span><span class="sxs-lookup"><span data-stu-id="cc900-129">ReplicaReplicatorAgent.exe</span></span>

  - <span data-ttu-id="cc900-130">ReplicationApp.exe</span><span class="sxs-lookup"><span data-stu-id="cc900-130">ReplicationApp.exe</span></span>

  - <span data-ttu-id="cc900-131">RtcHost.exe</span><span class="sxs-lookup"><span data-stu-id="cc900-131">RtcHost.exe</span></span>

  - <span data-ttu-id="cc900-132">RTCSrv.exe</span><span class="sxs-lookup"><span data-stu-id="cc900-132">RTCSrv.exe</span></span>

  - <span data-ttu-id="cc900-133">XmppProxy.exe</span><span class="sxs-lookup"><span data-stu-id="cc900-133">XmppProxy.exe</span></span>

  - <span data-ttu-id="cc900-134">XmppTGW.exe</span><span class="sxs-lookup"><span data-stu-id="cc900-134">XmppTGW.exe</span></span>

- <span data-ttu-id="cc900-135">Processos de Serviço de Host do Windows Fabric:</span><span class="sxs-lookup"><span data-stu-id="cc900-135">Windows Fabric Host Service processes:</span></span>

  - <span data-ttu-id="cc900-136">Fabric.exe</span><span class="sxs-lookup"><span data-stu-id="cc900-136">Fabric.exe</span></span>

  - <span data-ttu-id="cc900-137">FabricDCA.exe</span><span class="sxs-lookup"><span data-stu-id="cc900-137">FabricDCA.exe</span></span>

  - <span data-ttu-id="cc900-138">FabricHost.exe</span><span class="sxs-lookup"><span data-stu-id="cc900-138">FabricHost.exe</span></span>

- <span data-ttu-id="cc900-139">Processos IIS:</span><span class="sxs-lookup"><span data-stu-id="cc900-139">IIS processes:</span></span>

  - <span data-ttu-id="cc900-140">%systemroot%\system32\inetsrv\w3wp.exe</span><span class="sxs-lookup"><span data-stu-id="cc900-140">%systemroot%\system32\inetsrv\w3wp.exe</span></span>

  - <span data-ttu-id="cc900-141">%systemroot%\SysWOW64\inetsrv\w3wp.exe</span><span class="sxs-lookup"><span data-stu-id="cc900-141">%systemroot%\SysWOW64\inetsrv\w3wp.exe</span></span>

- <span data-ttu-id="cc900-142">Processos SQL Server Back-End:</span><span class="sxs-lookup"><span data-stu-id="cc900-142">SQL Server Back-End processes:</span></span>

    > [!NOTE]
    > <span data-ttu-id="cc900-143">Observe que estes caminhos são específicos para versão do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="cc900-143">Note that these paths are specific to SQL Server version.</span></span>

  - <span data-ttu-id="cc900-144">%ProgramFiles%\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="cc900-144">%ProgramFiles%\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Binn\SQLServr.exe</span></span>

  - <span data-ttu-id="cc900-145">%ProgramFiles%\Microsoft SQL Server\MSRS11.MSSQLSERVER\Reporting Services\ReportServer\Bin\ReportingServicesService.exe</span><span class="sxs-lookup"><span data-stu-id="cc900-145">%ProgramFiles%\Microsoft SQL Server\MSRS11.MSSQLSERVER\Reporting Services\ReportServer\Bin\ReportingServicesService.exe</span></span>

  - <span data-ttu-id="cc900-146">%ProgramFiles%\Microsoft SQL Server\MSAS11.MSSQLSERVER\OLAP\Bin\MSMDSrv.exe</span><span class="sxs-lookup"><span data-stu-id="cc900-146">%ProgramFiles%\Microsoft SQL Server\MSAS11.MSSQLSERVER\OLAP\Bin\MSMDSrv.exe</span></span>

- <span data-ttu-id="cc900-147">Processos SQL Server Front-End:</span><span class="sxs-lookup"><span data-stu-id="cc900-147">SQL Server Front-End processes:</span></span>

  - <span data-ttu-id="cc900-148">%ProgramFiles%\Microsoft SQL Server\MSSQL12.LYNCLOCAL\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="cc900-148">%ProgramFiles%\Microsoft SQL Server\MSSQL12.LYNCLOCAL\MSSQL\Binn\SQLServr.exe</span></span>

  - <span data-ttu-id="cc900-149">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTCLOCAL\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="cc900-149">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTCLOCAL\MSSQL\Binn\SQLServr.exe</span></span>

  - <span data-ttu-id="cc900-150">Instância RTC de Instalação Padrão de Edição</span><span class="sxs-lookup"><span data-stu-id="cc900-150">Standard Edition Installation RTC Instance</span></span>

  - <span data-ttu-id="cc900-151">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTC\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="cc900-151">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTC\MSSQL\Binn\SQLServr.exe</span></span>

- <span data-ttu-id="cc900-152">Diretórios e arquivos:</span><span class="sxs-lookup"><span data-stu-id="cc900-152">Directories and files:</span></span>

  - <span data-ttu-id="cc900-153">%systemroot%\System32\LogFiles</span><span class="sxs-lookup"><span data-stu-id="cc900-153">%systemroot%\System32\LogFiles</span></span>

  - <span data-ttu-id="cc900-154">%systemroot%\SysWow64\LogFiles</span><span class="sxs-lookup"><span data-stu-id="cc900-154">%systemroot%\SysWow64\LogFiles</span></span>

  - <span data-ttu-id="cc900-155">%systemroot%\Microsoft.NET\assembly\GAC_MSIL</span><span class="sxs-lookup"><span data-stu-id="cc900-155">%systemroot%\Microsoft.NET\assembly\GAC_MSIL</span></span>

    > [!NOTE]
    > <span data-ttu-id="cc900-156">Observe que esses caminhos são específicos para a versão do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="cc900-156">Note that these paths are specific to Skype for Business Server version.</span></span>

  - <span data-ttu-id="cc900-157">%programfiles%\Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="cc900-157">%programfiles%\Skype for Business Server 2015</span></span>

  - <span data-ttu-id="cc900-158">%programfiles%\Common Files\Skype for Business Server 2015\Watcher Node</span><span class="sxs-lookup"><span data-stu-id="cc900-158">%programfiles%\Common Files\Skype for Business Server 2015\Watcher Node</span></span>

  - <span data-ttu-id="cc900-159">%programfiles%\Common Files\Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="cc900-159">%programfiles%\Common Files\Skype for Business Server 2015</span></span>

  - <span data-ttu-id="cc900-160">%programfiles%\Common Files\Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="cc900-160">%programfiles%\Common Files\Skype for Business Online</span></span>

  - <span data-ttu-id="cc900-161">%SystemDrive%\RtcReplicaRoot</span><span class="sxs-lookup"><span data-stu-id="cc900-161">%SystemDrive%\RtcReplicaRoot</span></span>

  - <span data-ttu-id="cc900-p103">Repositório de compartilhamento de arquivo(específico no Construtor de Topologias). Os repositórios de arquivos são especificados no Construtor de Topologias.</span><span class="sxs-lookup"><span data-stu-id="cc900-p103">File share store (specified in Topology Builder). File stores are specified in Topology Builder.</span></span>

  - <span data-ttu-id="cc900-p104">Os arquivos de logs e dados do SQL Server, incluindo aqueles para o banco de dados de back-end, armazenamento de usuário, arquivamento, monitoramento, e repositório de application. Os arquivos da base de dados e os logs podem ser especificados no Construtor de Topologias. Para mais detalhes sobre os dados e arquivos de log para cada base de dados, incluindo os nomes padrão, consulte [SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) na Documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="cc900-p104">SQL Server data and log files, including those for the back-end database, user store, archiving store, monitoring store, and application store. Database and log files can be specified in Topology Builder. For details about the data and log files for each database, including default names, see [SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) in the Deployment documentation.</span></span>

  - <span data-ttu-id="cc900-167">Dados do SQL Server e arquivos de log, incluindo aqueles para o banco de dados front-end, a loja do Skype for Business e a loja do RtcDatabase.</span><span class="sxs-lookup"><span data-stu-id="cc900-167">SQL Server data and log files, including those for the Front-end database, Skype for Business store, and RtcDatabase store.</span></span> <span data-ttu-id="cc900-168">Normalmente, eles estão sob %localdrive%\CSData.</span><span class="sxs-lookup"><span data-stu-id="cc900-168">They are normally under %localdrive%\CSData.</span></span>


