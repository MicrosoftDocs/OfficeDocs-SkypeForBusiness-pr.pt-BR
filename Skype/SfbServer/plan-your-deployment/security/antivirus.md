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
ms.openlocfilehash: 9ec13b31328744bb154c9eb5e09dff7665c4b540
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296970"
---
# <a name="antivirus-scanning-exclusions-for-skype-for-business-server"></a><span data-ttu-id="dd7fb-103">Exclusões de verificação antivírus para o Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="dd7fb-103">Antivirus scanning exclusions for Skype for Business Server</span></span>

<span data-ttu-id="dd7fb-104">Visão geral da interoperação do verificador de antivírus com o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="dd7fb-104">Overview of antivirus scanner interoperation with Skype for Business Server.</span></span>

<span data-ttu-id="dd7fb-105">Este artigo contém recomendações que podem ajudar um administrador a determinar a causa de possível instabilidade em um computador que esteja executando uma versão com suporte do Microsoft Windows quando ele é usado com um software antivírus em um domínio do Active Directory ambiente ou em um ambiente de negócios gerenciado.</span><span class="sxs-lookup"><span data-stu-id="dd7fb-105">This article contains recommendations that may help an administrator determine the cause of potential instability on a computer that is running a supported version of Microsoft Windows when it is used with antivirus software in an Active Directory domain environment or in a managed business environment.</span></span>

<span data-ttu-id="dd7fb-106">Recomendamos que você aplique temporariamente esses procedimentos para avaliar um sistema.</span><span class="sxs-lookup"><span data-stu-id="dd7fb-106">We recommend that you temporarily apply these procedures to evaluate a system.</span></span> <span data-ttu-id="dd7fb-107">Se o desempenho do sistema ou a estabilidade forem aprimorados pelas recomendações feitas neste artigo, entre em contato com o fornecedor do software antivírus para obter instruções ou para obter uma versão atualizada do software antivírus.</span><span class="sxs-lookup"><span data-stu-id="dd7fb-107">If your system performance or stability is improved by the recommendations that are made in this article, contact your antivirus software vendor for instructions or for an updated version of the antivirus software.</span></span>

<span data-ttu-id="dd7fb-108">Este artigo contém informações que mostram como ajudar a reduzir as configurações de segurança ou como desativar temporariamente os recursos de segurança em um computador.</span><span class="sxs-lookup"><span data-stu-id="dd7fb-108">This article contains information that shows how to help lower security settings or how to temporarily turn off security features on a computer.</span></span> <span data-ttu-id="dd7fb-109">Você pode fazer essas alterações para compreender a natureza de um problema específico.</span><span class="sxs-lookup"><span data-stu-id="dd7fb-109">You can make these changes to understand the nature of a specific problem.</span></span> <span data-ttu-id="dd7fb-110">Antes de fazer essas alterações, recomendamos que avalie os riscos associados à implementação dessa solução alternativa em seu ambiente específico.</span><span class="sxs-lookup"><span data-stu-id="dd7fb-110">Before you make these changes, we recommend that you evaluate the risks that are associated with implementing this workaround in your particular environment.</span></span> <span data-ttu-id="dd7fb-111">Se você implementar esta solução alternativa, siga as etapas apropriadas adicionais para ajudar a proteger o computador para os arquivos que não estão mais sendo verificados pelo seu software antivírus.</span><span class="sxs-lookup"><span data-stu-id="dd7fb-111">If you implement this workaround, take any appropriate additional steps to help protect the computer for the files that are no longer being scanned by your antivirus software.</span></span>

<span data-ttu-id="dd7fb-112">Para garantir que o verificador de vírus não interfira com a operação do Skype for Business Server, você deve excluir processos e diretórios específicos para cada função de servidor ou servidor do Skype for Business Server na qual você executa um scanner antivírus.</span><span class="sxs-lookup"><span data-stu-id="dd7fb-112">To ensure that the antivirus scanner does not interfere with the operation of Skype for Business Server, you must exclude specific processes and directories for each Skype for Business Server server or server role on which you run an antivirus scanner.</span></span> <span data-ttu-id="dd7fb-113">Os seguintes processos e diretórios devem ser excluídos:</span><span class="sxs-lookup"><span data-stu-id="dd7fb-113">The following processes and directories should be excluded:</span></span>

> [!NOTE]
> <span data-ttu-id="dd7fb-114">Os locais de pasta e arquivo listados abaixo são os locais padrão do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="dd7fb-114">Folder and file locations listed below are the default locations for Skype for Business Server.</span></span> <span data-ttu-id="dd7fb-115">Para quaisquer locais, para os quais você não usa o padrão, exclua os locais que você especificou para a sua organização em vez dos locais padrão especificados neste tópico.</span><span class="sxs-lookup"><span data-stu-id="dd7fb-115">For any locations for which you did not use the default, exclude the locations you specified for your organization instead of the default locations specified in this topic.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="dd7fb-116">Observe que alguns programas antivírus podem precisar de caminhos absolutos e não relativos, para a sua lista de exclusão.</span><span class="sxs-lookup"><span data-stu-id="dd7fb-116">Please note that some antivirus programs may need absolute, not relative paths, for their exclusion list.</span></span>

- <span data-ttu-id="dd7fb-117">Processos do Skype for Business Server:</span><span class="sxs-lookup"><span data-stu-id="dd7fb-117">Skype for Business Server processes:</span></span>

  - <span data-ttu-id="dd7fb-118">ABServer.exe</span><span class="sxs-lookup"><span data-stu-id="dd7fb-118">ABServer.exe</span></span>

  - <span data-ttu-id="dd7fb-119">ASMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="dd7fb-119">ASMCUSvc.exe</span></span>

  - <span data-ttu-id="dd7fb-120">AVMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="dd7fb-120">AVMCUSvc.exe</span></span>

  - <span data-ttu-id="dd7fb-121">ChannelService.exe</span><span class="sxs-lookup"><span data-stu-id="dd7fb-121">ChannelService.exe</span></span>

  - <span data-ttu-id="dd7fb-122">ClsAgent.exe</span><span class="sxs-lookup"><span data-stu-id="dd7fb-122">ClsAgent.exe</span></span>

  - <span data-ttu-id="dd7fb-123">ComplianceService.exe</span><span class="sxs-lookup"><span data-stu-id="dd7fb-123">ComplianceService.exe</span></span>

  - <span data-ttu-id="dd7fb-124">DataMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="dd7fb-124">DataMCUSvc.exe</span></span>

  - <span data-ttu-id="dd7fb-125">DataProxy.exe</span><span class="sxs-lookup"><span data-stu-id="dd7fb-125">DataProxy.exe</span></span>

  - <span data-ttu-id="dd7fb-126">FileTransferAgent.exe</span><span class="sxs-lookup"><span data-stu-id="dd7fb-126">FileTransferAgent.exe</span></span>

  - <span data-ttu-id="dd7fb-127">HealthAgent.exe</span><span class="sxs-lookup"><span data-stu-id="dd7fb-127">HealthAgent.exe</span></span>

  - <span data-ttu-id="dd7fb-128">IMMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="dd7fb-128">IMMCUSvc.exe</span></span>
  
  - <span data-ttu-id="dd7fb-129">LyncBackupService. exe</span><span class="sxs-lookup"><span data-stu-id="dd7fb-129">LyncBackupService.exe</span></span>

  - <span data-ttu-id="dd7fb-130">LysSvc.exe</span><span class="sxs-lookup"><span data-stu-id="dd7fb-130">LysSvc.exe</span></span>

  - <span data-ttu-id="dd7fb-131">MasterReplicatorAgent.exe</span><span class="sxs-lookup"><span data-stu-id="dd7fb-131">MasterReplicatorAgent.exe</span></span>

  - <span data-ttu-id="dd7fb-132">MediaRelaySvc.exe</span><span class="sxs-lookup"><span data-stu-id="dd7fb-132">MediaRelaySvc.exe</span></span>

  - <span data-ttu-id="dd7fb-133">MediationServerSvc.exe</span><span class="sxs-lookup"><span data-stu-id="dd7fb-133">MediationServerSvc.exe</span></span>

  - <span data-ttu-id="dd7fb-134">MRASSvc.exe</span><span class="sxs-lookup"><span data-stu-id="dd7fb-134">MRASSvc.exe</span></span>

  - <span data-ttu-id="dd7fb-135">OcsAppServerHost.exe</span><span class="sxs-lookup"><span data-stu-id="dd7fb-135">OcsAppServerHost.exe</span></span>

  - <span data-ttu-id="dd7fb-136">ReplicaReplicatorAgent.exe</span><span class="sxs-lookup"><span data-stu-id="dd7fb-136">ReplicaReplicatorAgent.exe</span></span>

  - <span data-ttu-id="dd7fb-137">ReplicationApp.exe</span><span class="sxs-lookup"><span data-stu-id="dd7fb-137">ReplicationApp.exe</span></span>

  - <span data-ttu-id="dd7fb-138">RtcHost.exe</span><span class="sxs-lookup"><span data-stu-id="dd7fb-138">RtcHost.exe</span></span>

  - <span data-ttu-id="dd7fb-139">RTCSrv.exe</span><span class="sxs-lookup"><span data-stu-id="dd7fb-139">RTCSrv.exe</span></span>

  - <span data-ttu-id="dd7fb-140">XmppProxy.exe</span><span class="sxs-lookup"><span data-stu-id="dd7fb-140">XmppProxy.exe</span></span>

  - <span data-ttu-id="dd7fb-141">XmppTGW.exe</span><span class="sxs-lookup"><span data-stu-id="dd7fb-141">XmppTGW.exe</span></span>

- <span data-ttu-id="dd7fb-142">Processos de Serviço de Host do Windows Fabric:</span><span class="sxs-lookup"><span data-stu-id="dd7fb-142">Windows Fabric Host Service processes:</span></span>

  - <span data-ttu-id="dd7fb-143">Fabric.exe</span><span class="sxs-lookup"><span data-stu-id="dd7fb-143">Fabric.exe</span></span>

  - <span data-ttu-id="dd7fb-144">FabricDCA.exe</span><span class="sxs-lookup"><span data-stu-id="dd7fb-144">FabricDCA.exe</span></span>

  - <span data-ttu-id="dd7fb-145">FabricHost.exe</span><span class="sxs-lookup"><span data-stu-id="dd7fb-145">FabricHost.exe</span></span>

- <span data-ttu-id="dd7fb-146">Processos IIS:</span><span class="sxs-lookup"><span data-stu-id="dd7fb-146">IIS processes:</span></span>

  - <span data-ttu-id="dd7fb-147">%systemroot%\system32\inetsrv\w3wp.exe</span><span class="sxs-lookup"><span data-stu-id="dd7fb-147">%systemroot%\system32\inetsrv\w3wp.exe</span></span>

  - <span data-ttu-id="dd7fb-148">%systemroot%\SysWOW64\inetsrv\w3wp.exe</span><span class="sxs-lookup"><span data-stu-id="dd7fb-148">%systemroot%\SysWOW64\inetsrv\w3wp.exe</span></span>

- <span data-ttu-id="dd7fb-149">Processos SQL Server Back-End:</span><span class="sxs-lookup"><span data-stu-id="dd7fb-149">SQL Server Back-End processes:</span></span>

    > [!NOTE]
    > <span data-ttu-id="dd7fb-150">Observe que estes caminhos são específicos para versão do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="dd7fb-150">Note that these paths are specific to SQL Server version.</span></span>

  - <span data-ttu-id="dd7fb-151">%ProgramFiles%\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="dd7fb-151">%ProgramFiles%\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Binn\SQLServr.exe</span></span>

  - <span data-ttu-id="dd7fb-152">%ProgramFiles%\Microsoft SQL Server\MSRS11.MSSQLSERVER\Reporting Services\ReportServer\Bin\ReportingServicesService.exe</span><span class="sxs-lookup"><span data-stu-id="dd7fb-152">%ProgramFiles%\Microsoft SQL Server\MSRS11.MSSQLSERVER\Reporting Services\ReportServer\Bin\ReportingServicesService.exe</span></span>

  - <span data-ttu-id="dd7fb-153">%ProgramFiles%\Microsoft SQL Server\MSAS11.MSSQLSERVER\OLAP\Bin\MSMDSrv.exe</span><span class="sxs-lookup"><span data-stu-id="dd7fb-153">%ProgramFiles%\Microsoft SQL Server\MSAS11.MSSQLSERVER\OLAP\Bin\MSMDSrv.exe</span></span>

- <span data-ttu-id="dd7fb-154">Processos SQL Server Front-End:</span><span class="sxs-lookup"><span data-stu-id="dd7fb-154">SQL Server Front-End processes:</span></span>

  - <span data-ttu-id="dd7fb-155">%ProgramFiles%\Microsoft SQL Server\MSSQL12.LYNCLOCAL\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="dd7fb-155">%ProgramFiles%\Microsoft SQL Server\MSSQL12.LYNCLOCAL\MSSQL\Binn\SQLServr.exe</span></span>

  - <span data-ttu-id="dd7fb-156">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTCLOCAL\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="dd7fb-156">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTCLOCAL\MSSQL\Binn\SQLServr.exe</span></span>

  - <span data-ttu-id="dd7fb-157">Instância RTC de Instalação Padrão de Edição</span><span class="sxs-lookup"><span data-stu-id="dd7fb-157">Standard Edition Installation RTC Instance</span></span>

  - <span data-ttu-id="dd7fb-158">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTC\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="dd7fb-158">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTC\MSSQL\Binn\SQLServr.exe</span></span>

- <span data-ttu-id="dd7fb-159">Diretórios e arquivos:</span><span class="sxs-lookup"><span data-stu-id="dd7fb-159">Directories and files:</span></span>

  - <span data-ttu-id="dd7fb-160">%systemroot%\System32\LogFiles</span><span class="sxs-lookup"><span data-stu-id="dd7fb-160">%systemroot%\System32\LogFiles</span></span>

  - <span data-ttu-id="dd7fb-161">%systemroot%\SysWow64\LogFiles</span><span class="sxs-lookup"><span data-stu-id="dd7fb-161">%systemroot%\SysWow64\LogFiles</span></span>

  - <span data-ttu-id="dd7fb-162">%systemroot%\Microsoft.NET\assembly\GAC_MSIL</span><span class="sxs-lookup"><span data-stu-id="dd7fb-162">%systemroot%\Microsoft.NET\assembly\GAC_MSIL</span></span>

    > [!NOTE]
    > <span data-ttu-id="dd7fb-163">Observe que esses caminhos são específicos para a versão do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="dd7fb-163">Note that these paths are specific to Skype for Business Server version.</span></span>

  - <span data-ttu-id="dd7fb-164">%programfiles%\Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="dd7fb-164">%programfiles%\Skype for Business Server 2015</span></span>

  - <span data-ttu-id="dd7fb-165">%programfiles%\Common Files\Skype for Business Server 2015\Watcher Node</span><span class="sxs-lookup"><span data-stu-id="dd7fb-165">%programfiles%\Common Files\Skype for Business Server 2015\Watcher Node</span></span>

  - <span data-ttu-id="dd7fb-166">%programfiles%\Common Files\Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="dd7fb-166">%programfiles%\Common Files\Skype for Business Server 2015</span></span>

  - <span data-ttu-id="dd7fb-167">%programfiles%\Common Files\Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="dd7fb-167">%programfiles%\Common Files\Skype for Business Online</span></span>

  - <span data-ttu-id="dd7fb-168">%SystemDrive%\RtcReplicaRoot</span><span class="sxs-lookup"><span data-stu-id="dd7fb-168">%SystemDrive%\RtcReplicaRoot</span></span>

  - <span data-ttu-id="dd7fb-p105">Repositório de compartilhamento de arquivo(específico no Construtor de Topologias). Os repositórios de arquivos são especificados no Construtor de Topologias.</span><span class="sxs-lookup"><span data-stu-id="dd7fb-p105">File share store (specified in Topology Builder). File stores are specified in Topology Builder.</span></span>

  - <span data-ttu-id="dd7fb-p106">Os arquivos de logs e dados do SQL Server, incluindo aqueles para o banco de dados de back-end, armazenamento de usuário, arquivamento, monitoramento, e repositório de application. Os arquivos da base de dados e os logs podem ser especificados no Construtor de Topologias. Para mais detalhes sobre os dados e arquivos de log para cada base de dados, incluindo os nomes padrão, consulte [SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) na Documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="dd7fb-p106">SQL Server data and log files, including those for the back-end database, user store, archiving store, monitoring store, and application store. Database and log files can be specified in Topology Builder. For details about the data and log files for each database, including default names, see [SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) in the Deployment documentation.</span></span>

  - <span data-ttu-id="dd7fb-174">Dados do SQL Server e arquivos de log, incluindo aqueles para o banco de dados front-end, a loja do Skype for Business e a loja do RtcDatabase.</span><span class="sxs-lookup"><span data-stu-id="dd7fb-174">SQL Server data and log files, including those for the Front-end database, Skype for Business store, and RtcDatabase store.</span></span> <span data-ttu-id="dd7fb-175">Normalmente, eles estão sob %localdrive%\CSData.</span><span class="sxs-lookup"><span data-stu-id="dd7fb-175">They are normally under %localdrive%\CSData.</span></span>


