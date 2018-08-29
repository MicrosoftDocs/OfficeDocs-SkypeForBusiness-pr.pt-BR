---
title: Exclusões de varredura Skype para Business Server de antivírus
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
ms.openlocfilehash: 1078b3c0a28573e84235cbd39a11a6aa84a58b47
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/28/2018
ms.locfileid: "23250021"
---
# <a name="antivirus-scanning-exclusions-for-skype-for-business-server"></a><span data-ttu-id="a1e40-103">Exclusões de varredura Skype para Business Server de antivírus</span><span class="sxs-lookup"><span data-stu-id="a1e40-103">Antivirus scanning exclusions for Skype for Business Server</span></span>

<span data-ttu-id="a1e40-104">Visão geral do interoperação de scanner antivírus com Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="a1e40-104">Overview of antivirus scanner interoperation with Skype for Business Server.</span></span>

<span data-ttu-id="a1e40-105">Este artigo contém recomendações que podem ajudar a um administrador determinar a causa do possível instabilidade em um computador que está executando uma versão compatível do Microsoft Windows quando ele é usado com o software antivírus em um domínio do Active Directory ambiente ou em um ambiente de negócios gerenciados.</span><span class="sxs-lookup"><span data-stu-id="a1e40-105">This article contains recommendations that may help an administrator determine the cause of potential instability on a computer that is running a supported version of Microsoft Windows when it is used with antivirus software in an Active Directory domain environment or in a managed business environment.</span></span>

<span data-ttu-id="a1e40-106">É recomendável que você aplique temporariamente estes procedimentos para avaliar um sistema.</span><span class="sxs-lookup"><span data-stu-id="a1e40-106">We recommend that you temporarily apply these procedures to evaluate a system.</span></span> <span data-ttu-id="a1e40-107">Se o desempenho do sistema ou a estabilidade é aprimorada pelas recomendações feitas neste artigo, entre em contato com seu fornecedor de software antivírus para obter instruções ou para uma versão atualizada do software antivírus.</span><span class="sxs-lookup"><span data-stu-id="a1e40-107">If your system performance or stability is improved by the recommendations that are made in this article, contact your antivirus software vendor for instructions or for an updated version of the antivirus software.</span></span>

<span data-ttu-id="a1e40-108">Este artigo contém informações que mostram como ajudar a diminuir as configurações de segurança ou como desativar temporariamente os recursos de segurança em um computador.</span><span class="sxs-lookup"><span data-stu-id="a1e40-108">This article contains information that shows how to help lower security settings or how to temporarily turn off security features on a computer.</span></span> <span data-ttu-id="a1e40-109">Você pode fazer essas alterações para entender a natureza de um problema específico.</span><span class="sxs-lookup"><span data-stu-id="a1e40-109">You can make these changes to understand the nature of a specific problem.</span></span> <span data-ttu-id="a1e40-110">Antes de fazer essas alterações, recomendamos que você avaliar os riscos associados à implementação dessa solução alternativa no ambiente específico.</span><span class="sxs-lookup"><span data-stu-id="a1e40-110">Before you make these changes, we recommend that you evaluate the risks that are associated with implementing this workaround in your particular environment.</span></span> <span data-ttu-id="a1e40-111">Se você implementar essa solução alternativa, execute quaisquer etapas apropriadas adicionais para ajudar a proteger os arquivos que não são mais estão sendo examinados pelo seu software antivírus no computador.</span><span class="sxs-lookup"><span data-stu-id="a1e40-111">If you implement this workaround, take any appropriate additional steps to help protect the computer for the files that are no longer being scanned by your antivirus software.</span></span>

<span data-ttu-id="a1e40-112">Para garantir que o scanner antivírus não interfere com a operação do Skype para Business Server, você deve excluir diretórios e processos específicos para cada Skype para servidor de Business Server ou função de servidor em que você executa um scanner antivírus.</span><span class="sxs-lookup"><span data-stu-id="a1e40-112">To ensure that the antivirus scanner does not interfere with the operation of Skype for Business Server, you must exclude specific processes and directories for each Skype for Business Server server or server role on which you run an antivirus scanner.</span></span> <span data-ttu-id="a1e40-113">Os seguintes processos e diretórios devem ser excluídos:</span><span class="sxs-lookup"><span data-stu-id="a1e40-113">The following processes and directories should be excluded:</span></span>

> [!NOTE]
> <span data-ttu-id="a1e40-114">Locais de arquivo e pasta listadas a seguir são os locais de padrão do Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="a1e40-114">Folder and file locations listed below are the default locations for Skype for Business Server.</span></span> <span data-ttu-id="a1e40-115">Para quaisquer locais, para os quais você não usa o padrão, exclua os locais que você especificou para a sua organização em vez dos locais padrão especificados neste tópico.</span><span class="sxs-lookup"><span data-stu-id="a1e40-115">For any locations for which you did not use the default, exclude the locations you specified for your organization instead of the default locations specified in this topic.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a1e40-116">Observe que alguns programas antivírus podem precisar de caminhos absolutos e não relativos, para a sua lista de exclusão.</span><span class="sxs-lookup"><span data-stu-id="a1e40-116">Please note that some antivirus programs may need absolute, not relative paths, for their exclusion list.</span></span>

- <span data-ttu-id="a1e40-117">Skype para processos de negócios Server:</span><span class="sxs-lookup"><span data-stu-id="a1e40-117">Skype for Business Server processes:</span></span>

  - <span data-ttu-id="a1e40-118">ABServer.exe</span><span class="sxs-lookup"><span data-stu-id="a1e40-118">ABServer.exe</span></span>

  - <span data-ttu-id="a1e40-119">ASMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="a1e40-119">ASMCUSvc.exe</span></span>

  - <span data-ttu-id="a1e40-120">AVMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="a1e40-120">AVMCUSvc.exe</span></span>

  - <span data-ttu-id="a1e40-121">ChannelService.exe</span><span class="sxs-lookup"><span data-stu-id="a1e40-121">ChannelService.exe</span></span>

  - <span data-ttu-id="a1e40-122">ClsAgent.exe</span><span class="sxs-lookup"><span data-stu-id="a1e40-122">ClsAgent.exe</span></span>

  - <span data-ttu-id="a1e40-123">ComplianceService.exe</span><span class="sxs-lookup"><span data-stu-id="a1e40-123">ComplianceService.exe</span></span>

  - <span data-ttu-id="a1e40-124">DataMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="a1e40-124">DataMCUSvc.exe</span></span>

  - <span data-ttu-id="a1e40-125">DataProxy.exe</span><span class="sxs-lookup"><span data-stu-id="a1e40-125">DataProxy.exe</span></span>

  - <span data-ttu-id="a1e40-126">FileTransferAgent.exe</span><span class="sxs-lookup"><span data-stu-id="a1e40-126">FileTransferAgent.exe</span></span>

  - <span data-ttu-id="a1e40-127">HealthAgent.exe</span><span class="sxs-lookup"><span data-stu-id="a1e40-127">HealthAgent.exe</span></span>

  - <span data-ttu-id="a1e40-128">IMMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="a1e40-128">IMMCUSvc.exe</span></span>

  - <span data-ttu-id="a1e40-129">LysSvc.exe</span><span class="sxs-lookup"><span data-stu-id="a1e40-129">LysSvc.exe</span></span>

  - <span data-ttu-id="a1e40-130">MasterReplicatorAgent.exe</span><span class="sxs-lookup"><span data-stu-id="a1e40-130">MasterReplicatorAgent.exe</span></span>

  - <span data-ttu-id="a1e40-131">MediaRelaySvc.exe</span><span class="sxs-lookup"><span data-stu-id="a1e40-131">MediaRelaySvc.exe</span></span>

  - <span data-ttu-id="a1e40-132">MediationServerSvc.exe</span><span class="sxs-lookup"><span data-stu-id="a1e40-132">MediationServerSvc.exe</span></span>

  - <span data-ttu-id="a1e40-133">MRASSvc.exe</span><span class="sxs-lookup"><span data-stu-id="a1e40-133">MRASSvc.exe</span></span>

  - <span data-ttu-id="a1e40-134">OcsAppServerHost.exe</span><span class="sxs-lookup"><span data-stu-id="a1e40-134">OcsAppServerHost.exe</span></span>

  - <span data-ttu-id="a1e40-135">ReplicaReplicatorAgent.exe</span><span class="sxs-lookup"><span data-stu-id="a1e40-135">ReplicaReplicatorAgent.exe</span></span>

  - <span data-ttu-id="a1e40-136">ReplicationApp.exe</span><span class="sxs-lookup"><span data-stu-id="a1e40-136">ReplicationApp.exe</span></span>

  - <span data-ttu-id="a1e40-137">RtcHost.exe</span><span class="sxs-lookup"><span data-stu-id="a1e40-137">RtcHost.exe</span></span>

  - <span data-ttu-id="a1e40-138">RTCSrv.exe</span><span class="sxs-lookup"><span data-stu-id="a1e40-138">RTCSrv.exe</span></span>

  - <span data-ttu-id="a1e40-139">XmppProxy.exe</span><span class="sxs-lookup"><span data-stu-id="a1e40-139">XmppProxy.exe</span></span>

  - <span data-ttu-id="a1e40-140">XmppTGW.exe</span><span class="sxs-lookup"><span data-stu-id="a1e40-140">XmppTGW.exe</span></span>

- <span data-ttu-id="a1e40-141">Processos de Serviço de Host do Windows Fabric:</span><span class="sxs-lookup"><span data-stu-id="a1e40-141">Windows Fabric Host Service processes:</span></span>

  - <span data-ttu-id="a1e40-142">Fabric.exe</span><span class="sxs-lookup"><span data-stu-id="a1e40-142">Fabric.exe</span></span>

  - <span data-ttu-id="a1e40-143">FabricDCA.exe</span><span class="sxs-lookup"><span data-stu-id="a1e40-143">FabricDCA.exe</span></span>

  - <span data-ttu-id="a1e40-144">FabricHost.exe</span><span class="sxs-lookup"><span data-stu-id="a1e40-144">FabricHost.exe</span></span>

- <span data-ttu-id="a1e40-145">Processos IIS:</span><span class="sxs-lookup"><span data-stu-id="a1e40-145">IIS processes:</span></span>

  - <span data-ttu-id="a1e40-146">%systemroot%\system32\inetsrv\w3wp.exe</span><span class="sxs-lookup"><span data-stu-id="a1e40-146">%systemroot%\system32\inetsrv\w3wp.exe</span></span>

  - <span data-ttu-id="a1e40-147">%systemroot%\SysWOW64\inetsrv\w3wp.exe</span><span class="sxs-lookup"><span data-stu-id="a1e40-147">%systemroot%\SysWOW64\inetsrv\w3wp.exe</span></span>

- <span data-ttu-id="a1e40-148">Processos SQL Server Back-End:</span><span class="sxs-lookup"><span data-stu-id="a1e40-148">SQL Server Back-End processes:</span></span>

    > [!NOTE]
    > <span data-ttu-id="a1e40-149">Observe que estes caminhos são específicos para versão do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a1e40-149">Note that these paths are specific to SQL Server version.</span></span>

  - <span data-ttu-id="a1e40-150">%ProgramFiles%\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="a1e40-150">%ProgramFiles%\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Binn\SQLServr.exe</span></span>

  - <span data-ttu-id="a1e40-151">%ProgramFiles%\Microsoft SQL Server\MSRS11.MSSQLSERVER\Reporting Services\ReportServer\Bin\ReportingServicesService.exe</span><span class="sxs-lookup"><span data-stu-id="a1e40-151">%ProgramFiles%\Microsoft SQL Server\MSRS11.MSSQLSERVER\Reporting Services\ReportServer\Bin\ReportingServicesService.exe</span></span>

  - <span data-ttu-id="a1e40-152">%ProgramFiles%\Microsoft SQL Server\MSAS11.MSSQLSERVER\OLAP\Bin\MSMDSrv.exe</span><span class="sxs-lookup"><span data-stu-id="a1e40-152">%ProgramFiles%\Microsoft SQL Server\MSAS11.MSSQLSERVER\OLAP\Bin\MSMDSrv.exe</span></span>

- <span data-ttu-id="a1e40-153">Processos SQL Server Front-End:</span><span class="sxs-lookup"><span data-stu-id="a1e40-153">SQL Server Front-End processes:</span></span>

  - <span data-ttu-id="a1e40-154">%ProgramFiles%\Microsoft SQL Server\MSSQL12.LYNCLOCAL\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="a1e40-154">%ProgramFiles%\Microsoft SQL Server\MSSQL12.LYNCLOCAL\MSSQL\Binn\SQLServr.exe</span></span>

  - <span data-ttu-id="a1e40-155">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTCLOCAL\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="a1e40-155">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTCLOCAL\MSSQL\Binn\SQLServr.exe</span></span>

  - <span data-ttu-id="a1e40-156">Instância RTC de Instalação Padrão de Edição</span><span class="sxs-lookup"><span data-stu-id="a1e40-156">Standard Edition Installation RTC Instance</span></span>

  - <span data-ttu-id="a1e40-157">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTC\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="a1e40-157">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTC\MSSQL\Binn\SQLServr.exe</span></span>

- <span data-ttu-id="a1e40-158">Diretórios e arquivos:</span><span class="sxs-lookup"><span data-stu-id="a1e40-158">Directories and files:</span></span>

  - <span data-ttu-id="a1e40-159">%systemroot%\system32\LogFiles</span><span class="sxs-lookup"><span data-stu-id="a1e40-159">%systemroot%\System32\LogFiles</span></span>

  - <span data-ttu-id="a1e40-160">%systemroot%\SysWow64\LogFiles</span><span class="sxs-lookup"><span data-stu-id="a1e40-160">%systemroot%\SysWow64\LogFiles</span></span>

  - <span data-ttu-id="a1e40-161">%systemroot%\Microsoft.NET\assembly\GAC_MSIL</span><span class="sxs-lookup"><span data-stu-id="a1e40-161">%systemroot%\Microsoft.NET\assembly\GAC_MSIL</span></span>

    > [!NOTE]
    > <span data-ttu-id="a1e40-162">Observe que esses caminhos são específicos para Skype para a versão do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="a1e40-162">Note that these paths are specific to Skype for Business Server version.</span></span>

  - <span data-ttu-id="a1e40-163">%programfiles%\Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="a1e40-163">%programfiles%\Skype for Business Server 2015</span></span>

  - <span data-ttu-id="a1e40-164">%programfiles%\Common Files\Skype for Business Server 2015\Watcher Node</span><span class="sxs-lookup"><span data-stu-id="a1e40-164">%programfiles%\Common Files\Skype for Business Server 2015\Watcher Node</span></span>

  - <span data-ttu-id="a1e40-165">%programfiles%\Common Files\Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="a1e40-165">%programfiles%\Common Files\Skype for Business Server 2015</span></span>

  - <span data-ttu-id="a1e40-166">%programfiles%\Common Files\Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="a1e40-166">%programfiles%\Common Files\Skype for Business Online</span></span>

  - <span data-ttu-id="a1e40-167">%SystemDrive%\RtcReplicaRoot</span><span class="sxs-lookup"><span data-stu-id="a1e40-167">%SystemDrive%\RtcReplicaRoot</span></span>

  - <span data-ttu-id="a1e40-p105">Repositório de compartilhamento de arquivo(específico no Construtor de Topologias). Os repositórios de arquivos são especificados no Construtor de Topologias.</span><span class="sxs-lookup"><span data-stu-id="a1e40-p105">File share store (specified in Topology Builder). File stores are specified in Topology Builder.</span></span>

  - <span data-ttu-id="a1e40-170">Os arquivos de logs e dados do SQL Server, incluindo aqueles para o banco de dados de back-end, armazenamento de usuário, arquivamento, monitoramento, e repositório de application.</span><span class="sxs-lookup"><span data-stu-id="a1e40-170">SQL Server data and log files, including those for the back-end database, user store, archiving store, monitoring store, and application store.</span></span> <span data-ttu-id="a1e40-171">Os arquivos da base de dados e os logs podem ser especificados no Construtor de Topologias.</span><span class="sxs-lookup"><span data-stu-id="a1e40-171">Database and log files can be specified in Topology Builder.</span></span> <span data-ttu-id="a1e40-172">Para obter detalhes sobre os arquivos de dados e log para cada banco de dados, incluindo nomes padrão, consulte a [localização do arquivo de Log e de dados do SQL Server](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="a1e40-172">For details about the data and log files for each database, including default names, see [SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) in the Deployment documentation.</span></span>

  - <span data-ttu-id="a1e40-173">Arquivos do SQL Server dados e log, incluindo aqueles para o banco de dados front-end, Skype para repositório corporativo e RtcDatabase repositório.</span><span class="sxs-lookup"><span data-stu-id="a1e40-173">SQL Server data and log files, including those for the Front-end database, Skype for Business store, and RtcDatabase store.</span></span> <span data-ttu-id="a1e40-174">Normalmente, eles estão sob %localdrive%\CSData.</span><span class="sxs-lookup"><span data-stu-id="a1e40-174">They are normally under %localdrive%\CSData.</span></span>


