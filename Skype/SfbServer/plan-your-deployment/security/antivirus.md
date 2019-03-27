---
title: Exclusões de varredura Skype para Business Server de antivírus
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 5d742259-ef3b-417a-920b-e1fa0e48f043
description: Visão geral do interoperação de scanner antivírus com Skype para Business Server.
ms.openlocfilehash: 377c9e8fb9de71187978fe541a23f43cc2282749
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30895962"
---
# <a name="antivirus-scanning-exclusions-for-skype-for-business-server"></a><span data-ttu-id="99375-103">Exclusões de varredura Skype para Business Server de antivírus</span><span class="sxs-lookup"><span data-stu-id="99375-103">Antivirus scanning exclusions for Skype for Business Server</span></span>

<span data-ttu-id="99375-104">Visão geral do interoperação de scanner antivírus com Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="99375-104">Overview of antivirus scanner interoperation with Skype for Business Server.</span></span>

<span data-ttu-id="99375-105">Este artigo contém recomendações que podem ajudar a um administrador determinar a causa do possível instabilidade em um computador que está executando uma versão compatível do Microsoft Windows quando ele é usado com o software antivírus em um domínio do Active Directory ambiente ou em um ambiente de negócios gerenciados.</span><span class="sxs-lookup"><span data-stu-id="99375-105">This article contains recommendations that may help an administrator determine the cause of potential instability on a computer that is running a supported version of Microsoft Windows when it is used with antivirus software in an Active Directory domain environment or in a managed business environment.</span></span>

<span data-ttu-id="99375-106">É recomendável que você aplique temporariamente estes procedimentos para avaliar um sistema.</span><span class="sxs-lookup"><span data-stu-id="99375-106">We recommend that you temporarily apply these procedures to evaluate a system.</span></span> <span data-ttu-id="99375-107">Se o desempenho do sistema ou a estabilidade é aprimorada pelas recomendações feitas neste artigo, entre em contato com seu fornecedor de software antivírus para obter instruções ou para uma versão atualizada do software antivírus.</span><span class="sxs-lookup"><span data-stu-id="99375-107">If your system performance or stability is improved by the recommendations that are made in this article, contact your antivirus software vendor for instructions or for an updated version of the antivirus software.</span></span>

<span data-ttu-id="99375-108">Este artigo contém informações que mostram como ajudar a diminuir as configurações de segurança ou como desativar temporariamente os recursos de segurança em um computador.</span><span class="sxs-lookup"><span data-stu-id="99375-108">This article contains information that shows how to help lower security settings or how to temporarily turn off security features on a computer.</span></span> <span data-ttu-id="99375-109">Você pode fazer essas alterações para entender a natureza de um problema específico.</span><span class="sxs-lookup"><span data-stu-id="99375-109">You can make these changes to understand the nature of a specific problem.</span></span> <span data-ttu-id="99375-110">Antes de fazer essas alterações, recomendamos que você avaliar os riscos associados à implementação dessa solução alternativa no ambiente específico.</span><span class="sxs-lookup"><span data-stu-id="99375-110">Before you make these changes, we recommend that you evaluate the risks that are associated with implementing this workaround in your particular environment.</span></span> <span data-ttu-id="99375-111">Se você implementar essa solução alternativa, execute quaisquer etapas apropriadas adicionais para ajudar a proteger os arquivos que não são mais estão sendo examinados pelo seu software antivírus no computador.</span><span class="sxs-lookup"><span data-stu-id="99375-111">If you implement this workaround, take any appropriate additional steps to help protect the computer for the files that are no longer being scanned by your antivirus software.</span></span>

<span data-ttu-id="99375-112">Para garantir que o scanner antivírus não interfere com a operação do Skype para Business Server, você deve excluir diretórios e processos específicos para cada Skype para servidor de Business Server ou função de servidor em que você executa um scanner antivírus.</span><span class="sxs-lookup"><span data-stu-id="99375-112">To ensure that the antivirus scanner does not interfere with the operation of Skype for Business Server, you must exclude specific processes and directories for each Skype for Business Server server or server role on which you run an antivirus scanner.</span></span> <span data-ttu-id="99375-113">Os seguintes processos e diretórios devem ser excluídos:</span><span class="sxs-lookup"><span data-stu-id="99375-113">The following processes and directories should be excluded:</span></span>

> [!NOTE]
> <span data-ttu-id="99375-114">Locais de arquivo e pasta listadas a seguir são os locais de padrão do Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="99375-114">Folder and file locations listed below are the default locations for Skype for Business Server.</span></span> <span data-ttu-id="99375-115">Para quaisquer locais, para os quais você não usa o padrão, exclua os locais que você especificou para a sua organização em vez dos locais padrão especificados neste tópico.</span><span class="sxs-lookup"><span data-stu-id="99375-115">For any locations for which you did not use the default, exclude the locations you specified for your organization instead of the default locations specified in this topic.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="99375-116">Observe que alguns programas antivírus podem precisar de caminhos absolutos e não relativos, para a sua lista de exclusão.</span><span class="sxs-lookup"><span data-stu-id="99375-116">Please note that some antivirus programs may need absolute, not relative paths, for their exclusion list.</span></span>

- <span data-ttu-id="99375-117">Skype para processos de negócios Server:</span><span class="sxs-lookup"><span data-stu-id="99375-117">Skype for Business Server processes:</span></span>

  - <span data-ttu-id="99375-118">ABServer.exe</span><span class="sxs-lookup"><span data-stu-id="99375-118">ABServer.exe</span></span>

  - <span data-ttu-id="99375-119">ASMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="99375-119">ASMCUSvc.exe</span></span>

  - <span data-ttu-id="99375-120">AVMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="99375-120">AVMCUSvc.exe</span></span>

  - <span data-ttu-id="99375-121">ChannelService.exe</span><span class="sxs-lookup"><span data-stu-id="99375-121">ChannelService.exe</span></span>

  - <span data-ttu-id="99375-122">ClsAgent.exe</span><span class="sxs-lookup"><span data-stu-id="99375-122">ClsAgent.exe</span></span>

  - <span data-ttu-id="99375-123">ComplianceService.exe</span><span class="sxs-lookup"><span data-stu-id="99375-123">ComplianceService.exe</span></span>

  - <span data-ttu-id="99375-124">DataMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="99375-124">DataMCUSvc.exe</span></span>

  - <span data-ttu-id="99375-125">DataProxy.exe</span><span class="sxs-lookup"><span data-stu-id="99375-125">DataProxy.exe</span></span>

  - <span data-ttu-id="99375-126">FileTransferAgent.exe</span><span class="sxs-lookup"><span data-stu-id="99375-126">FileTransferAgent.exe</span></span>

  - <span data-ttu-id="99375-127">HealthAgent.exe</span><span class="sxs-lookup"><span data-stu-id="99375-127">HealthAgent.exe</span></span>

  - <span data-ttu-id="99375-128">IMMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="99375-128">IMMCUSvc.exe</span></span>
  
  - <span data-ttu-id="99375-129">LyncBackupService.exe</span><span class="sxs-lookup"><span data-stu-id="99375-129">LyncBackupService.exe</span></span>

  - <span data-ttu-id="99375-130">LysSvc.exe</span><span class="sxs-lookup"><span data-stu-id="99375-130">LysSvc.exe</span></span>

  - <span data-ttu-id="99375-131">MasterReplicatorAgent.exe</span><span class="sxs-lookup"><span data-stu-id="99375-131">MasterReplicatorAgent.exe</span></span>

  - <span data-ttu-id="99375-132">MediaRelaySvc.exe</span><span class="sxs-lookup"><span data-stu-id="99375-132">MediaRelaySvc.exe</span></span>

  - <span data-ttu-id="99375-133">MediationServerSvc.exe</span><span class="sxs-lookup"><span data-stu-id="99375-133">MediationServerSvc.exe</span></span>

  - <span data-ttu-id="99375-134">MRASSvc.exe</span><span class="sxs-lookup"><span data-stu-id="99375-134">MRASSvc.exe</span></span>

  - <span data-ttu-id="99375-135">OcsAppServerHost.exe</span><span class="sxs-lookup"><span data-stu-id="99375-135">OcsAppServerHost.exe</span></span>

  - <span data-ttu-id="99375-136">ReplicaReplicatorAgent.exe</span><span class="sxs-lookup"><span data-stu-id="99375-136">ReplicaReplicatorAgent.exe</span></span>

  - <span data-ttu-id="99375-137">ReplicationApp.exe</span><span class="sxs-lookup"><span data-stu-id="99375-137">ReplicationApp.exe</span></span>

  - <span data-ttu-id="99375-138">RtcHost.exe</span><span class="sxs-lookup"><span data-stu-id="99375-138">RtcHost.exe</span></span>

  - <span data-ttu-id="99375-139">RTCSrv.exe</span><span class="sxs-lookup"><span data-stu-id="99375-139">RTCSrv.exe</span></span>

  - <span data-ttu-id="99375-140">XmppProxy.exe</span><span class="sxs-lookup"><span data-stu-id="99375-140">XmppProxy.exe</span></span>

  - <span data-ttu-id="99375-141">XmppTGW.exe</span><span class="sxs-lookup"><span data-stu-id="99375-141">XmppTGW.exe</span></span>

- <span data-ttu-id="99375-142">Processos de Serviço de Host do Windows Fabric:</span><span class="sxs-lookup"><span data-stu-id="99375-142">Windows Fabric Host Service processes:</span></span>

  - <span data-ttu-id="99375-143">Fabric.exe</span><span class="sxs-lookup"><span data-stu-id="99375-143">Fabric.exe</span></span>

  - <span data-ttu-id="99375-144">FabricDCA.exe</span><span class="sxs-lookup"><span data-stu-id="99375-144">FabricDCA.exe</span></span>

  - <span data-ttu-id="99375-145">FabricHost.exe</span><span class="sxs-lookup"><span data-stu-id="99375-145">FabricHost.exe</span></span>

- <span data-ttu-id="99375-146">Processos IIS:</span><span class="sxs-lookup"><span data-stu-id="99375-146">IIS processes:</span></span>

  - <span data-ttu-id="99375-147">%systemroot%\system32\inetsrv\w3wp.exe</span><span class="sxs-lookup"><span data-stu-id="99375-147">%systemroot%\system32\inetsrv\w3wp.exe</span></span>

  - <span data-ttu-id="99375-148">%systemroot%\SysWOW64\inetsrv\w3wp.exe</span><span class="sxs-lookup"><span data-stu-id="99375-148">%systemroot%\SysWOW64\inetsrv\w3wp.exe</span></span>

- <span data-ttu-id="99375-149">Processos SQL Server Back-End:</span><span class="sxs-lookup"><span data-stu-id="99375-149">SQL Server Back-End processes:</span></span>

    > [!NOTE]
    > <span data-ttu-id="99375-150">Observe que estes caminhos são específicos para versão do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="99375-150">Note that these paths are specific to SQL Server version.</span></span>

  - <span data-ttu-id="99375-151">%ProgramFiles%\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="99375-151">%ProgramFiles%\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Binn\SQLServr.exe</span></span>

  - <span data-ttu-id="99375-152">%ProgramFiles%\Microsoft SQL Server\MSRS11.MSSQLSERVER\Reporting Services\ReportServer\Bin\ReportingServicesService.exe</span><span class="sxs-lookup"><span data-stu-id="99375-152">%ProgramFiles%\Microsoft SQL Server\MSRS11.MSSQLSERVER\Reporting Services\ReportServer\Bin\ReportingServicesService.exe</span></span>

  - <span data-ttu-id="99375-153">%ProgramFiles%\Microsoft SQL Server\MSAS11.MSSQLSERVER\OLAP\Bin\MSMDSrv.exe</span><span class="sxs-lookup"><span data-stu-id="99375-153">%ProgramFiles%\Microsoft SQL Server\MSAS11.MSSQLSERVER\OLAP\Bin\MSMDSrv.exe</span></span>

- <span data-ttu-id="99375-154">Processos SQL Server Front-End:</span><span class="sxs-lookup"><span data-stu-id="99375-154">SQL Server Front-End processes:</span></span>

  - <span data-ttu-id="99375-155">%ProgramFiles%\Microsoft SQL Server\MSSQL12.LYNCLOCAL\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="99375-155">%ProgramFiles%\Microsoft SQL Server\MSSQL12.LYNCLOCAL\MSSQL\Binn\SQLServr.exe</span></span>

  - <span data-ttu-id="99375-156">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTCLOCAL\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="99375-156">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTCLOCAL\MSSQL\Binn\SQLServr.exe</span></span>

  - <span data-ttu-id="99375-157">Instância RTC de Instalação Padrão de Edição</span><span class="sxs-lookup"><span data-stu-id="99375-157">Standard Edition Installation RTC Instance</span></span>

  - <span data-ttu-id="99375-158">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTC\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="99375-158">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTC\MSSQL\Binn\SQLServr.exe</span></span>

- <span data-ttu-id="99375-159">Diretórios e arquivos:</span><span class="sxs-lookup"><span data-stu-id="99375-159">Directories and files:</span></span>

  - <span data-ttu-id="99375-160">%systemroot%\System32\LogFiles</span><span class="sxs-lookup"><span data-stu-id="99375-160">%systemroot%\System32\LogFiles</span></span>

  - <span data-ttu-id="99375-161">%systemroot%\SysWow64\LogFiles</span><span class="sxs-lookup"><span data-stu-id="99375-161">%systemroot%\SysWow64\LogFiles</span></span>

  - <span data-ttu-id="99375-162">%systemroot%\Microsoft.NET\assembly\GAC_MSIL</span><span class="sxs-lookup"><span data-stu-id="99375-162">%systemroot%\Microsoft.NET\assembly\GAC_MSIL</span></span>

    > [!NOTE]
    > <span data-ttu-id="99375-163">Observe que esses caminhos são específicos para Skype para a versão do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="99375-163">Note that these paths are specific to Skype for Business Server version.</span></span>

  - <span data-ttu-id="99375-164">%programfiles%\Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="99375-164">%programfiles%\Skype for Business Server 2015</span></span>

  - <span data-ttu-id="99375-165">%programfiles%\Common Files\Skype for Business Server 2015\Watcher Node</span><span class="sxs-lookup"><span data-stu-id="99375-165">%programfiles%\Common Files\Skype for Business Server 2015\Watcher Node</span></span>

  - <span data-ttu-id="99375-166">%programfiles%\Common Files\Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="99375-166">%programfiles%\Common Files\Skype for Business Server 2015</span></span>

  - <span data-ttu-id="99375-167">%programfiles%\Common Files\Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="99375-167">%programfiles%\Common Files\Skype for Business Online</span></span>

  - <span data-ttu-id="99375-168">%SystemDrive%\RtcReplicaRoot</span><span class="sxs-lookup"><span data-stu-id="99375-168">%SystemDrive%\RtcReplicaRoot</span></span>

  - <span data-ttu-id="99375-p105">Repositório de compartilhamento de arquivo(específico no Construtor de Topologias). Os repositórios de arquivos são especificados no Construtor de Topologias.</span><span class="sxs-lookup"><span data-stu-id="99375-p105">File share store (specified in Topology Builder). File stores are specified in Topology Builder.</span></span>

  - <span data-ttu-id="99375-p106">Os arquivos de logs e dados do SQL Server, incluindo aqueles para o banco de dados de back-end, armazenamento de usuário, arquivamento, monitoramento, e repositório de application. Os arquivos da base de dados e os logs podem ser especificados no Construtor de Topologias. Para mais detalhes sobre os dados e arquivos de log para cada base de dados, incluindo os nomes padrão, consulte [SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) na Documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="99375-p106">SQL Server data and log files, including those for the back-end database, user store, archiving store, monitoring store, and application store. Database and log files can be specified in Topology Builder. For details about the data and log files for each database, including default names, see [SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) in the Deployment documentation.</span></span>

  - <span data-ttu-id="99375-174">Arquivos do SQL Server dados e log, incluindo aqueles para o banco de dados front-end, Skype para repositório corporativo e RtcDatabase repositório.</span><span class="sxs-lookup"><span data-stu-id="99375-174">SQL Server data and log files, including those for the Front-end database, Skype for Business store, and RtcDatabase store.</span></span> <span data-ttu-id="99375-175">Normalmente, eles estão sob %localdrive%\CSData.</span><span class="sxs-lookup"><span data-stu-id="99375-175">They are normally under %localdrive%\CSData.</span></span>


