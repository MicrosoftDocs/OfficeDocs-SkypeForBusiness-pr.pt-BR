---
title: Requisitos de hardware e software para arquivamento no Skype for Business Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 896d60e2-be4b-462d-8357-4cd307ab7304
description: 'Resumo: Leia este tópico para conhecer os requisitos de hardware e software para arquivamento no Skype para Business Server 2015.'
ms.openlocfilehash: d8d8039e95a3b578551d0db6ff219fe8f3c1e5c5
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="hardware-and-software-requirements-for-archiving-in-skype-for-business-server-2015"></a><span data-ttu-id="e7490-103">Requisitos de hardware e software para arquivamento no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="e7490-103">Hardware and software requirements for archiving in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="e7490-104">**Resumo:** Leia este tópico para conhecer os requisitos de hardware e software para arquivamento no Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="e7490-104">**Summary:** Read this topic to learn about hardware and software requirements for archiving in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="e7490-105">Skype para arquivamento Business Server 2015 agora é parte da função de Front-End, você não precisará instalar um servidor separado.</span><span class="sxs-lookup"><span data-stu-id="e7490-105">Skype for Business Server 2015 archiving is now part of the Front End role, so you do not need to install a separate server.</span></span> <span data-ttu-id="e7490-106">No entanto, fazer, você precisa considerar os seguintes requisitos:</span><span class="sxs-lookup"><span data-stu-id="e7490-106">You do, however, need to consider the following requirements:</span></span>
  
- <span data-ttu-id="e7490-107">Requisitos de infraestrutura</span><span class="sxs-lookup"><span data-stu-id="e7490-107">Infrastructure requirements</span></span>
    
- <span data-ttu-id="e7490-108">Requisitos de software</span><span class="sxs-lookup"><span data-stu-id="e7490-108">Prerequisite software requirements</span></span>
    
- <span data-ttu-id="e7490-109">Requisitos de armazenamento de dados</span><span class="sxs-lookup"><span data-stu-id="e7490-109">Data storage requirements</span></span>
    
## <a name="infrastructure-requirements"></a><span data-ttu-id="e7490-110">Requisitos de infraestrutura</span><span class="sxs-lookup"><span data-stu-id="e7490-110">Infrastructure requirements</span></span>

<span data-ttu-id="e7490-111">Skype para requisitos de infraestrutura de arquivamento de servidor de negócios são iguais às propriedades de implantação do Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="e7490-111">Skype for Business Server Archiving infrastructure requirements are the same as for deployment of Skype for Business Server.</span></span> <span data-ttu-id="e7490-112">Para obter detalhes, consulte [Requirements for sua Skype para ambiente de negócios](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md).</span><span class="sxs-lookup"><span data-stu-id="e7490-112">For details, see [Requirements for your Skype for Business environment](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md).</span></span> 
  
## <a name="prerequisite-software-requirements"></a><span data-ttu-id="e7490-113">Requisitos de software</span><span class="sxs-lookup"><span data-stu-id="e7490-113">Prerequisite software requirements</span></span>

<span data-ttu-id="e7490-114">Pré-requisitos de arquivamento para Skype para Business Server são mais simples do que nas versões anteriores do Microsoft Lync Server devido a estes motivos:</span><span class="sxs-lookup"><span data-stu-id="e7490-114">Archiving prerequisites for Skype for Business Server are simpler than earlier versions of Lync Server because of the following:</span></span> 
  
- <span data-ttu-id="e7490-115">Como o arquivamento não é mais é uma função de servidor, você não precisará instalar um servidor separado para arquivamento.</span><span class="sxs-lookup"><span data-stu-id="e7490-115">Because archiving is no longer a server role, you do not need to install a separate server for archiving.</span></span> <span data-ttu-id="e7490-116">Em vez disso, Agentes de Coleta de Dados Unificados são instalados e ativados automaticamente em todos os Pools de Front-Ends do Enterprise Edition e em todos os Servidores Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="e7490-116">Instead, Unified Data Collection Agents are installed and activated automatically on every Enterprise Edition Front End pool and every Standard Edition Server.</span></span> <span data-ttu-id="e7490-117">Você precisa habilitar e publicar a topologia do seu arquivamento usando o Construtor de Topologias.</span><span class="sxs-lookup"><span data-stu-id="e7490-117">You will need to enable and publish your archiving topology by using Topology Builder.</span></span>
    
- <span data-ttu-id="e7490-118">Arquivamento usa o Skype para armazenamento de arquivos do servidor de negócios para armazenamento temporário de reunião arquivos de conteúdo, de modo que você não configurar um repositório de arquivos para arquivamento.</span><span class="sxs-lookup"><span data-stu-id="e7490-118">Archiving uses the Skype for Business Server file storage for temporary storage of meeting content files, so you do not set up a separate file store for archiving.</span></span>
    
- <span data-ttu-id="e7490-119">No Skype para Business Server, Microsoft Message Queuing não é necessária.</span><span class="sxs-lookup"><span data-stu-id="e7490-119">In Skype for Business Server, Microsoft Message Queuing is not required.</span></span>
    
## <a name="data-storage-requirements"></a><span data-ttu-id="e7490-120">Requisitos de Armazenamento de Dados</span><span class="sxs-lookup"><span data-stu-id="e7490-120">Data Storage requirements</span></span>

<span data-ttu-id="e7490-p104">Além disso, você deve configurar a infraestrutura para o armazenamento de arquivamento. Isso inclui selecionar uma ou ambas as opções abaixo:</span><span class="sxs-lookup"><span data-stu-id="e7490-p104">You will need to set up the infrastructure for archiving storage. This includes choosing one or both of the following options:</span></span>
  
- <span data-ttu-id="e7490-123">**Armazenamento do Microsoft Exchange**.</span><span class="sxs-lookup"><span data-stu-id="e7490-123">**Microsoft Exchange storage**.</span></span> <span data-ttu-id="e7490-124">Arquivos de conteúdo das reuniões, tais como apresentações em PowerPoint, são arquivados como anexo.</span><span class="sxs-lookup"><span data-stu-id="e7490-124">Meeting content files, such as PowerPoint presentations, are archived as attachments.</span></span> <span data-ttu-id="e7490-125">Se você deseja armazenar Skype para dados de arquivo morto de negócios com os dados de conformidade do Exchange, você deve usar o Exchange para sua implantação do Exchange e certifique-se de que o tamanho máximo de armazenamento suporta o armazenamento dos arquivos de conteúdo de reunião.</span><span class="sxs-lookup"><span data-stu-id="e7490-125">If you want to store Skype for Business archive data with Exchange compliance data, you must use Exchange for your Exchange deployment and ensure that the maximum storage size supports storage of the meeting content files.</span></span> <span data-ttu-id="e7490-126">Você deve implantar o Exchange antes de implantar e habilitar o arquivamento usando a opção de integração do Microsoft Exchange.</span><span class="sxs-lookup"><span data-stu-id="e7490-126">You must deploy Exchange prior to deploying and enabling archiving using the Microsoft Exchange integration option.</span></span> 
    
    <span data-ttu-id="e7490-127">Se você optar por usar o armazenamento do Exchange, você não precisará implantar bancos de dados do SQL Server separados para arquivamento, a menos que tenha Skype para usuários corporativos que não esteja hospedados em seus servidores Exchange.</span><span class="sxs-lookup"><span data-stu-id="e7490-127">If you choose to use Exchange storage, you do not need to deploy separate SQL Server databases for archiving, unless you have Skype for Business users who are not homed on your Exchange servers.</span></span> <span data-ttu-id="e7490-128">Se você implantar o arquivamento usando a opção de integração do Microsoft Exchange, Skype para dados de arquivo morto corporativos será armazenado com dados de conformidade do Exchange apenas para os usuários que estão hospedados em seus servidores Exchange.</span><span class="sxs-lookup"><span data-stu-id="e7490-128">If you deploy archiving using the Microsoft Exchange integration option, Skype for Business archive data is stored with Exchange compliance data only for the users who are homed on your Exchange servers.</span></span> 
    
- <span data-ttu-id="e7490-129">**Skype para armazenamento de arquivamento Business Server**.</span><span class="sxs-lookup"><span data-stu-id="e7490-129">**Skype for Business Server archiving storage**.</span></span> <span data-ttu-id="e7490-130">Para suportar usuários que não esteja hospedados nos servidores do Exchange, ou se você não quiser usar a opção de integração do Microsoft Exchange, você deve implantar o armazenamento de arquivamento usando um banco de dados do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e7490-130">To support users who are not homed on Exchange servers, or if you do not want to use the Microsoft Exchange integration option, you must deploy archiving storage using a SQL Server database.</span></span> <span data-ttu-id="e7490-131">Skype para Business Server suporta as seguintes versões de 64 bits do SQL Server:</span><span class="sxs-lookup"><span data-stu-id="e7490-131">Skype for Business Server supports the following 64-bit versions of SQL Server:</span></span>
    
  - <span data-ttu-id="e7490-132">Microsoft SQL Server 2008 R2 Enterprise</span><span class="sxs-lookup"><span data-stu-id="e7490-132">Microsoft SQL Server 2008 R2 Enterprise</span></span>
    
  - <span data-ttu-id="e7490-133">Microsoft SQL Server 2008 R2 Standard</span><span class="sxs-lookup"><span data-stu-id="e7490-133">Microsoft SQL Server 2008 R2 Standard</span></span>
    
  - <span data-ttu-id="e7490-134">Enterprise do Microsoft SQL Server 2012</span><span class="sxs-lookup"><span data-stu-id="e7490-134">Microsoft SQL Server 2012 Enterprise</span></span>
    
  - <span data-ttu-id="e7490-135">Microsoft SQL Server 2012 Standard</span><span class="sxs-lookup"><span data-stu-id="e7490-135">Microsoft SQL Server 2012 Standard</span></span>
    
  - <span data-ttu-id="e7490-136">Microsoft SQL Server 2014 Enterprise</span><span class="sxs-lookup"><span data-stu-id="e7490-136">Microsoft SQL Server 2014 Enterprise</span></span>
    
  - <span data-ttu-id="e7490-137">Microsoft SQL Server 2014 Standard</span><span class="sxs-lookup"><span data-stu-id="e7490-137">Microsoft SQL Server 2014 Standard</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="e7490-138">Versões do Microsoft SQL Server Express não são suportadas para arquivamento.</span><span class="sxs-lookup"><span data-stu-id="e7490-138">Microsoft SQL Server Express versions are not supported for archiving.</span></span> <span data-ttu-id="e7490-139">versões de 32 bits do SQL Server não são suportadas.</span><span class="sxs-lookup"><span data-stu-id="e7490-139">32-bit versions of SQL Server are not supported.</span></span> <span data-ttu-id="e7490-140">Para requisitos do SQL Server e restrições adicionais, consulte [Requirements for sua Skype para ambiente de negócios](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md).</span><span class="sxs-lookup"><span data-stu-id="e7490-140">For additional SQL Server requirements and restrictions, see [Requirements for your Skype for Business environment](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md).</span></span> 
  
    <span data-ttu-id="e7490-141">Você deve configurar as plataformas do SQL Server antes de implantar e habilitar o arquivamento.</span><span class="sxs-lookup"><span data-stu-id="e7490-141">You must set up the SQL Server platforms prior to deploying and enabling archiving.</span></span> <span data-ttu-id="e7490-142">Se a conta utilizada para publicar a topologia tiver os direitos e permissões apropriados, é possível criar o banco de dados de arquivamento (LcsLog) ao publicar a topologia.</span><span class="sxs-lookup"><span data-stu-id="e7490-142">If the account to be used to publish the topology has the appropriate administrator rights and permissions, you can create the Archiving database (LcsLog) when you publish your topology.</span></span> <span data-ttu-id="e7490-143">Também é possível criar o banco de dados posteriormente, incluindo-o como parte do procedimento de instalação.</span><span class="sxs-lookup"><span data-stu-id="e7490-143">You can also create the database later, included as part of the installation procedure.</span></span> <span data-ttu-id="e7490-144">Para obter detalhes sobre o SQL Server, consulte o [TechCenter do SQL Server](https://go.microsoft.com/fwlink/p/?linkID=129045).</span><span class="sxs-lookup"><span data-stu-id="e7490-144">For details about SQL Server, see the [SQL Server TechCenter](https://go.microsoft.com/fwlink/p/?linkID=129045).</span></span>
    
    <span data-ttu-id="e7490-145">O aumento de carga para arquivamento pode ser significativo.</span><span class="sxs-lookup"><span data-stu-id="e7490-145">The load increase for archiving can be significant.</span></span> <span data-ttu-id="e7490-146">Portanto, você deve assegurar que o espaço em disco é adequado para servidores Front-End no qual o arquivamento estiver habilitado.</span><span class="sxs-lookup"><span data-stu-id="e7490-146">Therefore, you should ensure that disk space is adequate for Front End Servers on which archiving is enabled.</span></span>
    

