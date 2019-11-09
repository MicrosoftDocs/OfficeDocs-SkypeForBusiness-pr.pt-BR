---
title: Exclusões de verificação antivírus para o Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 5d742259-ef3b-417a-920b-e1fa0e48f043
description: Visão geral da interoperação do verificador de antivírus com o Skype for Business Server.
ms.openlocfilehash: 69fb02d04f27b7444a3b8cadaacafc05654a1c9f
ms.sourcegitcommit: 1aa98e3865d5a0f7be5e1cba497dea4ac7b9c607
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2019
ms.locfileid: "38074623"
---
# <a name="antivirus-scanning-exclusions-for-skype-for-business-server"></a><span data-ttu-id="ebd9b-103">Exclusões de verificação antivírus para o Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="ebd9b-103">Antivirus scanning exclusions for Skype for Business Server</span></span>

<span data-ttu-id="ebd9b-104">Visão geral da interoperação do verificador de antivírus com o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="ebd9b-104">Overview of antivirus scanner interoperation with Skype for Business Server.</span></span>

<span data-ttu-id="ebd9b-105">Para garantir que o verificador de vírus não interfira com a operação do Skype for Business Server, você deve excluir processos e diretórios específicos para cada função de servidor ou servidor do Skype for Business Server na qual você executa um scanner antivírus.</span><span class="sxs-lookup"><span data-stu-id="ebd9b-105">To ensure that the antivirus scanner does not interfere with the operation of Skype for Business Server, you must exclude specific processes and directories for each Skype for Business Server server or server role on which you run an antivirus scanner.</span></span> <span data-ttu-id="ebd9b-106">Os seguintes processos e diretórios devem ser excluídos:</span><span class="sxs-lookup"><span data-stu-id="ebd9b-106">The following processes and directories should be excluded:</span></span>

> [!NOTE]
> <span data-ttu-id="ebd9b-107">Os locais de pasta e arquivo listados abaixo são os locais padrão do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="ebd9b-107">Folder and file locations listed below are the default locations for Skype for Business Server.</span></span> <span data-ttu-id="ebd9b-108">Para quaisquer locais, para os quais você não usa o padrão, exclua os locais que você especificou para a sua organização em vez dos locais padrão especificados neste tópico.</span><span class="sxs-lookup"><span data-stu-id="ebd9b-108">For any locations for which you did not use the default, exclude the locations you specified for your organization instead of the default locations specified in this topic.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ebd9b-109">Observe que alguns programas antivírus podem precisar de caminhos absolutos e não relativos, para a sua lista de exclusão.</span><span class="sxs-lookup"><span data-stu-id="ebd9b-109">Please note that some antivirus programs may need absolute, not relative paths, for their exclusion list.</span></span>

- <span data-ttu-id="ebd9b-110">Processos do Skype for Business Server:</span><span class="sxs-lookup"><span data-stu-id="ebd9b-110">Skype for Business Server processes:</span></span>

  - <span data-ttu-id="ebd9b-111">ABServer.exe</span><span class="sxs-lookup"><span data-stu-id="ebd9b-111">ABServer.exe</span></span>

  - <span data-ttu-id="ebd9b-112">ASMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="ebd9b-112">ASMCUSvc.exe</span></span>

  - <span data-ttu-id="ebd9b-113">AVMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="ebd9b-113">AVMCUSvc.exe</span></span>

  - <span data-ttu-id="ebd9b-114">ChannelService.exe</span><span class="sxs-lookup"><span data-stu-id="ebd9b-114">ChannelService.exe</span></span>

  - <span data-ttu-id="ebd9b-115">ClsAgent.exe</span><span class="sxs-lookup"><span data-stu-id="ebd9b-115">ClsAgent.exe</span></span>

  - <span data-ttu-id="ebd9b-116">ComplianceService.exe</span><span class="sxs-lookup"><span data-stu-id="ebd9b-116">ComplianceService.exe</span></span>

  - <span data-ttu-id="ebd9b-117">DataMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="ebd9b-117">DataMCUSvc.exe</span></span>

  - <span data-ttu-id="ebd9b-118">DataProxy.exe</span><span class="sxs-lookup"><span data-stu-id="ebd9b-118">DataProxy.exe</span></span>

  - <span data-ttu-id="ebd9b-119">FileTransferAgent.exe</span><span class="sxs-lookup"><span data-stu-id="ebd9b-119">FileTransferAgent.exe</span></span>

  - <span data-ttu-id="ebd9b-120">HealthAgent.exe</span><span class="sxs-lookup"><span data-stu-id="ebd9b-120">HealthAgent.exe</span></span>

  - <span data-ttu-id="ebd9b-121">IMMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="ebd9b-121">IMMCUSvc.exe</span></span>
  
  - <span data-ttu-id="ebd9b-122">LyncBackupService. exe</span><span class="sxs-lookup"><span data-stu-id="ebd9b-122">LyncBackupService.exe</span></span>

  - <span data-ttu-id="ebd9b-123">LysSvc.exe</span><span class="sxs-lookup"><span data-stu-id="ebd9b-123">LysSvc.exe</span></span>

  - <span data-ttu-id="ebd9b-124">MasterReplicatorAgent.exe</span><span class="sxs-lookup"><span data-stu-id="ebd9b-124">MasterReplicatorAgent.exe</span></span>

  - <span data-ttu-id="ebd9b-125">MediaRelaySvc.exe</span><span class="sxs-lookup"><span data-stu-id="ebd9b-125">MediaRelaySvc.exe</span></span>

  - <span data-ttu-id="ebd9b-126">MediationServerSvc.exe</span><span class="sxs-lookup"><span data-stu-id="ebd9b-126">MediationServerSvc.exe</span></span>

  - <span data-ttu-id="ebd9b-127">MRASSvc.exe</span><span class="sxs-lookup"><span data-stu-id="ebd9b-127">MRASSvc.exe</span></span>

  - <span data-ttu-id="ebd9b-128">OcsAppServerHost.exe</span><span class="sxs-lookup"><span data-stu-id="ebd9b-128">OcsAppServerHost.exe</span></span>

  - <span data-ttu-id="ebd9b-129">ReplicaReplicatorAgent.exe</span><span class="sxs-lookup"><span data-stu-id="ebd9b-129">ReplicaReplicatorAgent.exe</span></span>

  - <span data-ttu-id="ebd9b-130">ReplicationApp.exe</span><span class="sxs-lookup"><span data-stu-id="ebd9b-130">ReplicationApp.exe</span></span>

  - <span data-ttu-id="ebd9b-131">RtcHost.exe</span><span class="sxs-lookup"><span data-stu-id="ebd9b-131">RtcHost.exe</span></span>

  - <span data-ttu-id="ebd9b-132">RTCSrv.exe</span><span class="sxs-lookup"><span data-stu-id="ebd9b-132">RTCSrv.exe</span></span>

  - <span data-ttu-id="ebd9b-133">XmppProxy.exe</span><span class="sxs-lookup"><span data-stu-id="ebd9b-133">XmppProxy.exe</span></span>

  - <span data-ttu-id="ebd9b-134">XmppTGW.exe</span><span class="sxs-lookup"><span data-stu-id="ebd9b-134">XmppTGW.exe</span></span>

- <span data-ttu-id="ebd9b-135">Processos de Serviço de Host do Windows Fabric:</span><span class="sxs-lookup"><span data-stu-id="ebd9b-135">Windows Fabric Host Service processes:</span></span>

  - <span data-ttu-id="ebd9b-136">Fabric.exe</span><span class="sxs-lookup"><span data-stu-id="ebd9b-136">Fabric.exe</span></span>

  - <span data-ttu-id="ebd9b-137">FabricDCA.exe</span><span class="sxs-lookup"><span data-stu-id="ebd9b-137">FabricDCA.exe</span></span>

  - <span data-ttu-id="ebd9b-138">FabricHost.exe</span><span class="sxs-lookup"><span data-stu-id="ebd9b-138">FabricHost.exe</span></span>

- <span data-ttu-id="ebd9b-139">Processos IIS:</span><span class="sxs-lookup"><span data-stu-id="ebd9b-139">IIS processes:</span></span>

  - <span data-ttu-id="ebd9b-140">%systemroot%\system32\inetsrv\w3wp.exe</span><span class="sxs-lookup"><span data-stu-id="ebd9b-140">%systemroot%\system32\inetsrv\w3wp.exe</span></span>

  - <span data-ttu-id="ebd9b-141">%systemroot%\SysWOW64\inetsrv\w3wp.exe</span><span class="sxs-lookup"><span data-stu-id="ebd9b-141">%systemroot%\SysWOW64\inetsrv\w3wp.exe</span></span>

- <span data-ttu-id="ebd9b-142">Processos SQL Server Back-End:</span><span class="sxs-lookup"><span data-stu-id="ebd9b-142">SQL Server Back-End processes:</span></span>

    > [!NOTE]
    > <span data-ttu-id="ebd9b-143">Observe que estes caminhos são específicos para versão do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ebd9b-143">Note that these paths are specific to SQL Server version.</span></span>

  - <span data-ttu-id="ebd9b-144">%ProgramFiles%\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="ebd9b-144">%ProgramFiles%\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Binn\SQLServr.exe</span></span>

  - <span data-ttu-id="ebd9b-145">%ProgramFiles%\Microsoft SQL Server\MSRS11.MSSQLSERVER\Reporting Services\ReportServer\Bin\ReportingServicesService.exe</span><span class="sxs-lookup"><span data-stu-id="ebd9b-145">%ProgramFiles%\Microsoft SQL Server\MSRS11.MSSQLSERVER\Reporting Services\ReportServer\Bin\ReportingServicesService.exe</span></span>

  - <span data-ttu-id="ebd9b-146">%ProgramFiles%\Microsoft SQL Server\MSAS11.MSSQLSERVER\OLAP\Bin\MSMDSrv.exe</span><span class="sxs-lookup"><span data-stu-id="ebd9b-146">%ProgramFiles%\Microsoft SQL Server\MSAS11.MSSQLSERVER\OLAP\Bin\MSMDSrv.exe</span></span>

- <span data-ttu-id="ebd9b-147">Processos SQL Server Front-End:</span><span class="sxs-lookup"><span data-stu-id="ebd9b-147">SQL Server Front-End processes:</span></span>

  - <span data-ttu-id="ebd9b-148">%ProgramFiles%\Microsoft SQL Server\MSSQL12.LYNCLOCAL\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="ebd9b-148">%ProgramFiles%\Microsoft SQL Server\MSSQL12.LYNCLOCAL\MSSQL\Binn\SQLServr.exe</span></span>

  - <span data-ttu-id="ebd9b-149">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTCLOCAL\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="ebd9b-149">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTCLOCAL\MSSQL\Binn\SQLServr.exe</span></span>

  - <span data-ttu-id="ebd9b-150">Instância RTC de Instalação Padrão de Edição</span><span class="sxs-lookup"><span data-stu-id="ebd9b-150">Standard Edition Installation RTC Instance</span></span>

  - <span data-ttu-id="ebd9b-151">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTC\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="ebd9b-151">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTC\MSSQL\Binn\SQLServr.exe</span></span>

- <span data-ttu-id="ebd9b-152">Diretórios e arquivos:</span><span class="sxs-lookup"><span data-stu-id="ebd9b-152">Directories and files:</span></span>

  - <span data-ttu-id="ebd9b-153">%systemroot%\System32\LogFiles</span><span class="sxs-lookup"><span data-stu-id="ebd9b-153">%systemroot%\System32\LogFiles</span></span>

  - <span data-ttu-id="ebd9b-154">%systemroot%\SysWow64\LogFiles</span><span class="sxs-lookup"><span data-stu-id="ebd9b-154">%systemroot%\SysWow64\LogFiles</span></span>

  - <span data-ttu-id="ebd9b-155">%systemroot%\Microsoft.NET\assembly\GAC_MSIL</span><span class="sxs-lookup"><span data-stu-id="ebd9b-155">%systemroot%\Microsoft.NET\assembly\GAC_MSIL</span></span>

    > [!NOTE]
    > <span data-ttu-id="ebd9b-156">Observe que esses caminhos são específicos para a versão do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="ebd9b-156">Note that these paths are specific to Skype for Business Server version.</span></span>

  - <span data-ttu-id="ebd9b-157">%programfiles%\Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="ebd9b-157">%programfiles%\Skype for Business Server 2015</span></span>

  - <span data-ttu-id="ebd9b-158">%programfiles%\Common Files\Skype for Business Server 2015\Watcher Node</span><span class="sxs-lookup"><span data-stu-id="ebd9b-158">%programfiles%\Common Files\Skype for Business Server 2015\Watcher Node</span></span>

  - <span data-ttu-id="ebd9b-159">%programfiles%\Common Files\Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="ebd9b-159">%programfiles%\Common Files\Skype for Business Server 2015</span></span>

  - <span data-ttu-id="ebd9b-160">%programfiles%\Common Files\Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="ebd9b-160">%programfiles%\Common Files\Skype for Business Online</span></span>

  - <span data-ttu-id="ebd9b-161">%SystemDrive%\RtcReplicaRoot</span><span class="sxs-lookup"><span data-stu-id="ebd9b-161">%SystemDrive%\RtcReplicaRoot</span></span>

  - <span data-ttu-id="ebd9b-p103">Repositório de compartilhamento de arquivo(específico no Construtor de Topologias). Os repositórios de arquivos são especificados no Construtor de Topologias.</span><span class="sxs-lookup"><span data-stu-id="ebd9b-p103">File share store (specified in Topology Builder). File stores are specified in Topology Builder.</span></span>

  - <span data-ttu-id="ebd9b-p104">Os arquivos de logs e dados do SQL Server, incluindo aqueles para o banco de dados de back-end, armazenamento de usuário, arquivamento, monitoramento, e repositório de application. Os arquivos da base de dados e os logs podem ser especificados no Construtor de Topologias. Para mais detalhes sobre os dados e arquivos de log para cada base de dados, incluindo os nomes padrão, consulte [SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) na Documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="ebd9b-p104">SQL Server data and log files, including those for the back-end database, user store, archiving store, monitoring store, and application store. Database and log files can be specified in Topology Builder. For details about the data and log files for each database, including default names, see [SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) in the Deployment documentation.</span></span>

  - <span data-ttu-id="ebd9b-167">Dados do SQL Server e arquivos de log, incluindo aqueles para o banco de dados front-end, a loja do Skype for Business e a loja do RtcDatabase.</span><span class="sxs-lookup"><span data-stu-id="ebd9b-167">SQL Server data and log files, including those for the Front-end database, Skype for Business store, and RtcDatabase store.</span></span> <span data-ttu-id="ebd9b-168">Normalmente, eles estão sob %localdrive%\CSData.</span><span class="sxs-lookup"><span data-stu-id="ebd9b-168">They are normally under %localdrive%\CSData.</span></span>


