---
title: 'Lync Server 2013: estabelecendo uma estratégia de backup e restauração'
description: 'Lync Server 2013: estabelecendo uma estratégia de backup e restauração.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Establishing a backup and restoration strategy
ms:assetid: f545a75f-bbc4-4968-b510-8f6f3920112b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202195(v=OCS.15)
ms:contentKeyID: 51541532
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f4fdefed873d1fd69d82f8ecebceeb92f06f65f7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555037"
---
# <a name="establishing-a-backup-and-restoration-strategy-for-lync-server-2013"></a><span data-ttu-id="eef6a-103">Estabelecendo uma estratégia de backup e restauração para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eef6a-103">Establishing a backup and restoration strategy for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eef6a-104">_**Última modificação do tópico:** 2013-03-26_</span><span class="sxs-lookup"><span data-stu-id="eef6a-104">_**Topic Last Modified:** 2013-03-26_</span></span>

<span data-ttu-id="eef6a-105">Antes de poder desenvolver um plano de backup e restauração para o Lync Server, você precisa desenvolver uma estratégia que se ajuste às metas da sua organização.</span><span class="sxs-lookup"><span data-stu-id="eef6a-105">Before you can develop a backup and restoration plan for Lync Server, you need to develop a strategy that fits with your organization's goals.</span></span> <span data-ttu-id="eef6a-106">Para desenvolver uma estratégia de backup e restauração eficaz, você precisará:</span><span class="sxs-lookup"><span data-stu-id="eef6a-106">To develop an effective backup and restoration strategy, you will need to:</span></span>

  - <span data-ttu-id="eef6a-107">Estabelecer prioridades de negócios.</span><span class="sxs-lookup"><span data-stu-id="eef6a-107">Establish business priorities.</span></span>

  - <span data-ttu-id="eef6a-108">Identificar os requisitos de backup e restauração.</span><span class="sxs-lookup"><span data-stu-id="eef6a-108">Identify backup and restoration requirements.</span></span>

<div>

## <a name="establishing-business-priorities"></a><span data-ttu-id="eef6a-109">Estabelecer as prioridades comerciais</span><span class="sxs-lookup"><span data-stu-id="eef6a-109">Establishing Business Priorities</span></span>

<span data-ttu-id="eef6a-p102">Avaliar as prioridades comerciais da sua organização. Geralmente, as prioridades comerciais primárias que afetam sua estratégia de backup e restauração são as seguintes:</span><span class="sxs-lookup"><span data-stu-id="eef6a-p102">Evaluate the business priorities of your organization. Typically, the primary business priorities that affect your backup and restoration strategy are the following:</span></span>

  - <span data-ttu-id="eef6a-112">Requisitos de continuidade comercial</span><span class="sxs-lookup"><span data-stu-id="eef6a-112">Business continuity requirements</span></span>

  - <span data-ttu-id="eef6a-113">Plenitude de dados</span><span class="sxs-lookup"><span data-stu-id="eef6a-113">Data completeness</span></span>

  - <span data-ttu-id="eef6a-114">Criticidade de dados</span><span class="sxs-lookup"><span data-stu-id="eef6a-114">Data criticality</span></span>

  - <span data-ttu-id="eef6a-115">Requisitos de portabilidade</span><span class="sxs-lookup"><span data-stu-id="eef6a-115">Portability requirements</span></span>

  - <span data-ttu-id="eef6a-116">Restrições de custo</span><span class="sxs-lookup"><span data-stu-id="eef6a-116">Cost constraints</span></span>

<span data-ttu-id="eef6a-117">Necessidades comerciais, como estas ajudam a determinar os contratos de nível de serviço (SLAs) que você desenvolve com seus clientes.</span><span class="sxs-lookup"><span data-stu-id="eef6a-117">Business needs such as these help to determine the service level agreements (SLAs) that you develop with your customers.</span></span> <span data-ttu-id="eef6a-118">Os contratos de nível de serviço influenciam muito sua estratégia de backup e recuperação.</span><span class="sxs-lookup"><span data-stu-id="eef6a-118">Service level agreements greatly influence your backup and recovery strategy.</span></span>

</div>

<div>

## <a name="identifying-backup-and-restoration-requirements"></a><span data-ttu-id="eef6a-119">Identificar os requisitos de backup e restauração</span><span class="sxs-lookup"><span data-stu-id="eef6a-119">Identifying Backup and Restoration Requirements</span></span>

<span data-ttu-id="eef6a-120">Suas prioridades de negócios e contratos de nível de serviço atuam na determinação dos requisitos de sua organização para o backup e a restauração do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="eef6a-120">Your business priorities and service level agreements act in determining your organizations' requirements for backing up and restoring Lync Server.</span></span> <span data-ttu-id="eef6a-121">Identifique e documente seus requisitos para o seguinte:</span><span class="sxs-lookup"><span data-stu-id="eef6a-121">Identify and document your requirements for the following:</span></span>

  - <span data-ttu-id="eef6a-122">**Frequência de backups**     Para obter detalhes sobre as práticas recomendadas para frequência de backup, consulte [práticas recomendadas para backup e restauração do Lync Server 2013](lync-server-2013-best-practices-for-backup-and-restoration.md).</span><span class="sxs-lookup"><span data-stu-id="eef6a-122">**Frequency of backups**   For details about best practices for backup frequency, see [Best practices for backup and restoration for Lync Server 2013](lync-server-2013-best-practices-for-backup-and-restoration.md).</span></span>

  - <span data-ttu-id="eef6a-123">Ferramentas de backup **e restauração**     Inclua quem deve usar as ferramentas e em quais computadores.</span><span class="sxs-lookup"><span data-stu-id="eef6a-123">**Backup and restoration tools**   Include who is to use the tools, and on which computers.</span></span> <span data-ttu-id="eef6a-124">Para obter detalhes sobre as ferramentas discutidas neste tópico e permissões necessárias, consulte [requisitos de backup e restauração no Lync Server 2013: ferramentas e permissões](lync-server-2013-backup-and-restoration-requirements-tools-and-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="eef6a-124">For details about the tools discussed in this topic and necessary permissions, see [Backup and restoration requirements in Lync Server 2013: tools and permissions](lync-server-2013-backup-and-restoration-requirements-tools-and-permissions.md).</span></span>

  - <span data-ttu-id="eef6a-125">**Local**     do backup Identifique se os backups são mantidos local ou remotamente, levando a segurança e acessibilidade em consideração.</span><span class="sxs-lookup"><span data-stu-id="eef6a-125">**Backup location**   Identify whether the backups are kept locally or remotely, taking security and accessibility into consideration.</span></span> <span data-ttu-id="eef6a-126">Especifique a mídia a ser usada para os backups.</span><span class="sxs-lookup"><span data-stu-id="eef6a-126">Specify the media to be used for the backups.</span></span>

  - <span data-ttu-id="eef6a-127">Requisitos de hardware **e software**     Identificar e documentar seus requisitos específicos de hardware e software, incluindo o hardware para o armazenamento de backup e a restauração de componentes específicos e qualquer software e conectividade de rede necessário para dar suporte a backup e restauração.</span><span class="sxs-lookup"><span data-stu-id="eef6a-127">**Hardware and software requirements**   Identify and document your specific hardware and software requirements, including the hardware for backup storage and restoration of specific components and any software and network connectivity required to support backup and restoration.</span></span> <span data-ttu-id="eef6a-128">Conforme você desenvolve seus requisitos de hardware e software, lembre-se dos vários cenários de restauração a seguir.</span><span class="sxs-lookup"><span data-stu-id="eef6a-128">As you develop your hardware and software requirements, keep in mind the various restoration scenarios that follow.</span></span>

  - <span data-ttu-id="eef6a-129">**Cenários**     de restauração Estes são os processos de restauração para os seguintes cenários:</span><span class="sxs-lookup"><span data-stu-id="eef6a-129">**Restoration scenarios**   Here are the restoration processes for the following scenarios:</span></span>
    
      - <span data-ttu-id="eef6a-130">Um pool do Lync Server falha.</span><span class="sxs-lookup"><span data-stu-id="eef6a-130">A Lync Server pool fails.</span></span> <span data-ttu-id="eef6a-131">Este cenário exige a recompilação de cada servidor no pool.</span><span class="sxs-lookup"><span data-stu-id="eef6a-131">This scenario requires rebuilding each server in the pool.</span></span>
    
      - <span data-ttu-id="eef6a-132">Um servidor Standard Edition falha.</span><span class="sxs-lookup"><span data-stu-id="eef6a-132">A Standard Edition server fails.</span></span> <span data-ttu-id="eef6a-133">Este cenário exige a recompilação do servidor em um computador novo ou limpo e a restauração dos bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="eef6a-133">This scenario requires rebuilding the server on a new or clean computer and restoring databases.</span></span>
    
      - <span data-ttu-id="eef6a-134">Perda do repositório de gerenciamento central.</span><span class="sxs-lookup"><span data-stu-id="eef6a-134">Loss of the Central Management store.</span></span> <span data-ttu-id="eef6a-135">No mínimo, esse cenário requer a restauração e publicação do repositório de gerenciamento central.</span><span class="sxs-lookup"><span data-stu-id="eef6a-135">At a minimum, this scenario requires restoring and publishing the Central Management store.</span></span>
    
      - <span data-ttu-id="eef6a-136">Perda de um servidor back-end quando o repositório de gerenciamento central ainda está funcionando normalmente.</span><span class="sxs-lookup"><span data-stu-id="eef6a-136">Loss of a Back End Server when the Central Management store is still functioning normally.</span></span> <span data-ttu-id="eef6a-137">Este cenário exige a recompilação do servidor em um computador novo ou limpo e a restauração dos bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="eef6a-137">This scenario requires rebuilding the server on a new or clean computer and restoring databases.</span></span>
    
      - <span data-ttu-id="eef6a-138">Um servidor que é membro de um pool do Lync Server falha.</span><span class="sxs-lookup"><span data-stu-id="eef6a-138">A server that is a member of a Lync Server pool fails.</span></span> <span data-ttu-id="eef6a-139">Este cenário exige a recompilação do servidor em um computador novo ou limpo.</span><span class="sxs-lookup"><span data-stu-id="eef6a-139">This scenario requires rebuilding the server on a new or clean computer.</span></span>
    
      - <span data-ttu-id="eef6a-140">Um repositório de arquivos falha.</span><span class="sxs-lookup"><span data-stu-id="eef6a-140">A File Store fails.</span></span> <span data-ttu-id="eef6a-141">Este cenário exige a restauração do servidor de arquivos ou cluster de arquivos.</span><span class="sxs-lookup"><span data-stu-id="eef6a-141">This scenario requires restoring the file server or file cluster.</span></span>
    
      - <span data-ttu-id="eef6a-142">Um banco de dados de chat de arquivamento, monitoramento ou persistente falha.</span><span class="sxs-lookup"><span data-stu-id="eef6a-142">An Archiving, Monitoring, or Persistent Chat database fails.</span></span> <span data-ttu-id="eef6a-143">Este cenário exige a recriação dos bancos de dados e, se os dados são fundamentais para sua organização, restaurar os dados.</span><span class="sxs-lookup"><span data-stu-id="eef6a-143">This scenario requires recreating the databases, and, if the data is critical to your organization, restoring the data.</span></span> <span data-ttu-id="eef6a-144">Os dados de arquivamento, monitoramento e chat persistente não são necessários para fazer o backup e a execução do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="eef6a-144">Archiving, Monitoring, and Persistent Chat data is not required to get Lync Server back up and running.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

