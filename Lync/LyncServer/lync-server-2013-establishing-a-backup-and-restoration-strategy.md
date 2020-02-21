---
title: 'Lync Server 2013: estabelecendo uma estratégia de backup e restauração'
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
ms.openlocfilehash: 8a65dd081cacd9952ce1b9a7f0917209532a28cf
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204787"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="establishing-a-backup-and-restoration-strategy-for-lync-server-2013"></a><span data-ttu-id="2902a-102">Estabelecendo uma estratégia de backup e restauração para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2902a-102">Establishing a backup and restoration strategy for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2902a-103">_**Última modificação do tópico:** 2013-03-26_</span><span class="sxs-lookup"><span data-stu-id="2902a-103">_**Topic Last Modified:** 2013-03-26_</span></span>

<span data-ttu-id="2902a-104">Antes de poder desenvolver um plano de backup e restauração para o Lync Server, você precisa desenvolver uma estratégia que se ajuste às metas da sua organização.</span><span class="sxs-lookup"><span data-stu-id="2902a-104">Before you can develop a backup and restoration plan for Lync Server, you need to develop a strategy that fits with your organization's goals.</span></span> <span data-ttu-id="2902a-105">Para desenvolver uma estratégia de backup e restauração eficaz, você precisará:</span><span class="sxs-lookup"><span data-stu-id="2902a-105">To develop an effective backup and restoration strategy, you will need to:</span></span>

  - <span data-ttu-id="2902a-106">Estabelecer prioridades de negócios.</span><span class="sxs-lookup"><span data-stu-id="2902a-106">Establish business priorities.</span></span>

  - <span data-ttu-id="2902a-107">Identificar os requisitos de backup e restauração.</span><span class="sxs-lookup"><span data-stu-id="2902a-107">Identify backup and restoration requirements.</span></span>

<div>

## <a name="establishing-business-priorities"></a><span data-ttu-id="2902a-108">Estabelecer as prioridades comerciais</span><span class="sxs-lookup"><span data-stu-id="2902a-108">Establishing Business Priorities</span></span>

<span data-ttu-id="2902a-p102">Avaliar as prioridades comerciais da sua organização. Geralmente, as prioridades comerciais primárias que afetam sua estratégia de backup e restauração são as seguintes:</span><span class="sxs-lookup"><span data-stu-id="2902a-p102">Evaluate the business priorities of your organization. Typically, the primary business priorities that affect your backup and restoration strategy are the following:</span></span>

  - <span data-ttu-id="2902a-111">Requisitos de continuidade comercial</span><span class="sxs-lookup"><span data-stu-id="2902a-111">Business continuity requirements</span></span>

  - <span data-ttu-id="2902a-112">Plenitude de dados</span><span class="sxs-lookup"><span data-stu-id="2902a-112">Data completeness</span></span>

  - <span data-ttu-id="2902a-113">Criticidade de dados</span><span class="sxs-lookup"><span data-stu-id="2902a-113">Data criticality</span></span>

  - <span data-ttu-id="2902a-114">Requisitos de portabilidade</span><span class="sxs-lookup"><span data-stu-id="2902a-114">Portability requirements</span></span>

  - <span data-ttu-id="2902a-115">Restrições de custo</span><span class="sxs-lookup"><span data-stu-id="2902a-115">Cost constraints</span></span>

<span data-ttu-id="2902a-116">Necessidades comerciais, como estas ajudam a determinar os contratos de nível de serviço (SLAs) que você desenvolve com seus clientes.</span><span class="sxs-lookup"><span data-stu-id="2902a-116">Business needs such as these help to determine the service level agreements (SLAs) that you develop with your customers.</span></span> <span data-ttu-id="2902a-117">Os contratos de nível de serviço influenciam muito sua estratégia de backup e recuperação.</span><span class="sxs-lookup"><span data-stu-id="2902a-117">Service level agreements greatly influence your backup and recovery strategy.</span></span>

</div>

<div>

## <a name="identifying-backup-and-restoration-requirements"></a><span data-ttu-id="2902a-118">Identificar os requisitos de backup e restauração</span><span class="sxs-lookup"><span data-stu-id="2902a-118">Identifying Backup and Restoration Requirements</span></span>

<span data-ttu-id="2902a-119">Suas prioridades de negócios e contratos de nível de serviço atuam na determinação dos requisitos de sua organização para o backup e a restauração do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2902a-119">Your business priorities and service level agreements act in determining your organizations' requirements for backing up and restoring Lync Server.</span></span> <span data-ttu-id="2902a-120">Identifique e documente seus requisitos para o seguinte:</span><span class="sxs-lookup"><span data-stu-id="2902a-120">Identify and document your requirements for the following:</span></span>

  - <span data-ttu-id="2902a-121">**Frequência de backups**   para obter detalhes sobre as práticas recomendadas para frequência de backup, consulte [práticas recomendadas de backup e restauração para o Lync Server 2013](lync-server-2013-best-practices-for-backup-and-restoration.md).</span><span class="sxs-lookup"><span data-stu-id="2902a-121">**Frequency of backups**   For details about best practices for backup frequency, see [Best practices for backup and restoration for Lync Server 2013](lync-server-2013-best-practices-for-backup-and-restoration.md).</span></span>

  - <span data-ttu-id="2902a-122">**As ferramentas**   de backup e restauração incluem quem é usar as ferramentas e em quais computadores.</span><span class="sxs-lookup"><span data-stu-id="2902a-122">**Backup and restoration tools**   Include who is to use the tools, and on which computers.</span></span> <span data-ttu-id="2902a-123">Para obter detalhes sobre as ferramentas discutidas neste tópico e permissões necessárias, consulte [requisitos de backup e restauração no Lync Server 2013: ferramentas e permissões](lync-server-2013-backup-and-restoration-requirements-tools-and-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="2902a-123">For details about the tools discussed in this topic and necessary permissions, see [Backup and restoration requirements in Lync Server 2013: tools and permissions](lync-server-2013-backup-and-restoration-requirements-tools-and-permissions.md).</span></span>

  - <span data-ttu-id="2902a-124">**Local de backup**   identifique se os backups são mantidos local ou remotamente, levando a segurança e acessibilidade em consideração.</span><span class="sxs-lookup"><span data-stu-id="2902a-124">**Backup location**   Identify whether the backups are kept locally or remotely, taking security and accessibility into consideration.</span></span> <span data-ttu-id="2902a-125">Especifique a mídia a ser usada para os backups.</span><span class="sxs-lookup"><span data-stu-id="2902a-125">Specify the media to be used for the backups.</span></span>

  - <span data-ttu-id="2902a-126">**Os requisitos**   de hardware e software identificam e documentam os requisitos específicos de hardware e software, incluindo o hardware para o armazenamento de backup e a restauração de componentes específicos e qualquer software e conectividade de rede necessários para dar suporte a backup e restauração.</span><span class="sxs-lookup"><span data-stu-id="2902a-126">**Hardware and software requirements**   Identify and document your specific hardware and software requirements, including the hardware for backup storage and restoration of specific components and any software and network connectivity required to support backup and restoration.</span></span> <span data-ttu-id="2902a-127">Conforme você desenvolve seus requisitos de hardware e software, lembre-se dos vários cenários de restauração a seguir.</span><span class="sxs-lookup"><span data-stu-id="2902a-127">As you develop your hardware and software requirements, keep in mind the various restoration scenarios that follow.</span></span>

  - <span data-ttu-id="2902a-128">**Cenários de restauração**   aqui estão os processos de restauração para os seguintes cenários:</span><span class="sxs-lookup"><span data-stu-id="2902a-128">**Restoration scenarios**   Here are the restoration processes for the following scenarios:</span></span>
    
      - <span data-ttu-id="2902a-129">Um pool do Lync Server falha.</span><span class="sxs-lookup"><span data-stu-id="2902a-129">A Lync Server pool fails.</span></span> <span data-ttu-id="2902a-130">Este cenário exige a recompilação de cada servidor no pool.</span><span class="sxs-lookup"><span data-stu-id="2902a-130">This scenario requires rebuilding each server in the pool.</span></span>
    
      - <span data-ttu-id="2902a-131">Um servidor Standard Edition falha.</span><span class="sxs-lookup"><span data-stu-id="2902a-131">A Standard Edition server fails.</span></span> <span data-ttu-id="2902a-132">Este cenário exige a recompilação do servidor em um computador novo ou limpo e a restauração dos bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="2902a-132">This scenario requires rebuilding the server on a new or clean computer and restoring databases.</span></span>
    
      - <span data-ttu-id="2902a-133">Perda do repositório de gerenciamento central.</span><span class="sxs-lookup"><span data-stu-id="2902a-133">Loss of the Central Management store.</span></span> <span data-ttu-id="2902a-134">No mínimo, esse cenário requer a restauração e publicação do repositório de gerenciamento central.</span><span class="sxs-lookup"><span data-stu-id="2902a-134">At a minimum, this scenario requires restoring and publishing the Central Management store.</span></span>
    
      - <span data-ttu-id="2902a-135">Perda de um servidor back-end quando o repositório de gerenciamento central ainda está funcionando normalmente.</span><span class="sxs-lookup"><span data-stu-id="2902a-135">Loss of a Back End Server when the Central Management store is still functioning normally.</span></span> <span data-ttu-id="2902a-136">Este cenário exige a recompilação do servidor em um computador novo ou limpo e a restauração dos bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="2902a-136">This scenario requires rebuilding the server on a new or clean computer and restoring databases.</span></span>
    
      - <span data-ttu-id="2902a-137">Um servidor que é membro de um pool do Lync Server falha.</span><span class="sxs-lookup"><span data-stu-id="2902a-137">A server that is a member of a Lync Server pool fails.</span></span> <span data-ttu-id="2902a-138">Este cenário exige a recompilação do servidor em um computador novo ou limpo.</span><span class="sxs-lookup"><span data-stu-id="2902a-138">This scenario requires rebuilding the server on a new or clean computer.</span></span>
    
      - <span data-ttu-id="2902a-139">Um repositório de arquivos falha.</span><span class="sxs-lookup"><span data-stu-id="2902a-139">A File Store fails.</span></span> <span data-ttu-id="2902a-140">Este cenário exige a restauração do servidor de arquivos ou cluster de arquivos.</span><span class="sxs-lookup"><span data-stu-id="2902a-140">This scenario requires restoring the file server or file cluster.</span></span>
    
      - <span data-ttu-id="2902a-141">Um banco de dados de chat de arquivamento, monitoramento ou persistente falha.</span><span class="sxs-lookup"><span data-stu-id="2902a-141">An Archiving, Monitoring, or Persistent Chat database fails.</span></span> <span data-ttu-id="2902a-142">Este cenário exige a recriação dos bancos de dados e, se os dados são fundamentais para sua organização, restaurar os dados.</span><span class="sxs-lookup"><span data-stu-id="2902a-142">This scenario requires recreating the databases, and, if the data is critical to your organization, restoring the data.</span></span> <span data-ttu-id="2902a-143">Os dados de arquivamento, monitoramento e chat persistente não são necessários para fazer o backup e a execução do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2902a-143">Archiving, Monitoring, and Persistent Chat data is not required to get Lync Server back up and running.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

