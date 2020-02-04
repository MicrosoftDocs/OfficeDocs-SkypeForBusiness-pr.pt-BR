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
ms.openlocfilehash: 5ee1a13667e28ad374f538d61f6cfd941d31fade
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735252"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="establishing-a-backup-and-restoration-strategy-for-lync-server-2013"></a><span data-ttu-id="3d0a9-102">Como estabelecer uma estratégia de backup e restauração para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3d0a9-102">Establishing a backup and restoration strategy for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3d0a9-103">_**Tópico da última modificação:** 2013-03-26_</span><span class="sxs-lookup"><span data-stu-id="3d0a9-103">_**Topic Last Modified:** 2013-03-26_</span></span>

<span data-ttu-id="3d0a9-104">Antes de poder desenvolver um plano de backup e restauração para o Lync Server, você precisará desenvolver uma estratégia que se adapte às metas da sua organização.</span><span class="sxs-lookup"><span data-stu-id="3d0a9-104">Before you can develop a backup and restoration plan for Lync Server, you need to develop a strategy that fits with your organization's goals.</span></span> <span data-ttu-id="3d0a9-105">Para desenvolver uma estratégia eficaz de backup e restauração, será necessário:</span><span class="sxs-lookup"><span data-stu-id="3d0a9-105">To develop an effective backup and restoration strategy, you will need to:</span></span>

  - <span data-ttu-id="3d0a9-106">Estabeleça prioridades de negócios.</span><span class="sxs-lookup"><span data-stu-id="3d0a9-106">Establish business priorities.</span></span>

  - <span data-ttu-id="3d0a9-107">Identifique os requisitos de backup e restauração.</span><span class="sxs-lookup"><span data-stu-id="3d0a9-107">Identify backup and restoration requirements.</span></span>

<div>

## <a name="establishing-business-priorities"></a><span data-ttu-id="3d0a9-108">Estabelecendo prioridades de negócios</span><span class="sxs-lookup"><span data-stu-id="3d0a9-108">Establishing Business Priorities</span></span>

<span data-ttu-id="3d0a9-109">Avaliar as prioridades comerciais da sua organização.</span><span class="sxs-lookup"><span data-stu-id="3d0a9-109">Evaluate the business priorities of your organization.</span></span> <span data-ttu-id="3d0a9-110">Geralmente, as principais prioridades de negócios que afetam a estratégia de backup e restauração são as seguintes:</span><span class="sxs-lookup"><span data-stu-id="3d0a9-110">Typically, the primary business priorities that affect your backup and restoration strategy are the following:</span></span>

  - <span data-ttu-id="3d0a9-111">Requisitos de continuidade de negócios</span><span class="sxs-lookup"><span data-stu-id="3d0a9-111">Business continuity requirements</span></span>

  - <span data-ttu-id="3d0a9-112">Integridade dos dados</span><span class="sxs-lookup"><span data-stu-id="3d0a9-112">Data completeness</span></span>

  - <span data-ttu-id="3d0a9-113">Criticalidade de dados</span><span class="sxs-lookup"><span data-stu-id="3d0a9-113">Data criticality</span></span>

  - <span data-ttu-id="3d0a9-114">Requisitos de portabilidade</span><span class="sxs-lookup"><span data-stu-id="3d0a9-114">Portability requirements</span></span>

  - <span data-ttu-id="3d0a9-115">Restrições de custo</span><span class="sxs-lookup"><span data-stu-id="3d0a9-115">Cost constraints</span></span>

<span data-ttu-id="3d0a9-116">Necessidades comerciais, como estes ajudam a determinar os contratos de nível de serviço (SLAs) que você desenvolve com seus clientes.</span><span class="sxs-lookup"><span data-stu-id="3d0a9-116">Business needs such as these help to determine the service level agreements (SLAs) that you develop with your customers.</span></span> <span data-ttu-id="3d0a9-117">Contratos de nível de serviço influenciam bastante sua estratégia de backup e recuperação.</span><span class="sxs-lookup"><span data-stu-id="3d0a9-117">Service level agreements greatly influence your backup and recovery strategy.</span></span>

</div>

<div>

## <a name="identifying-backup-and-restoration-requirements"></a><span data-ttu-id="3d0a9-118">Identificar requisitos de backup e restauração</span><span class="sxs-lookup"><span data-stu-id="3d0a9-118">Identifying Backup and Restoration Requirements</span></span>

<span data-ttu-id="3d0a9-119">Suas prioridades de negócios e contratos de nível de serviço atuam para determinar os requisitos da sua organização para o backup e a restauração do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3d0a9-119">Your business priorities and service level agreements act in determining your organizations' requirements for backing up and restoring Lync Server.</span></span> <span data-ttu-id="3d0a9-120">Identifique e documente seus requisitos para o seguinte:</span><span class="sxs-lookup"><span data-stu-id="3d0a9-120">Identify and document your requirements for the following:</span></span>

  - <span data-ttu-id="3d0a9-121">**Frequência de backups**   para obter detalhes sobre as práticas recomendadas para a frequência de backup, consulte [práticas recomendadas de backup e restauração do Lync Server 2013](lync-server-2013-best-practices-for-backup-and-restoration.md).</span><span class="sxs-lookup"><span data-stu-id="3d0a9-121">**Frequency of backups**   For details about best practices for backup frequency, see [Best practices for backup and restoration for Lync Server 2013](lync-server-2013-best-practices-for-backup-and-restoration.md).</span></span>

  - <span data-ttu-id="3d0a9-122">**As ferramentas**   de backup e restauração incluem quem deve usar as ferramentas e em quais computadores.</span><span class="sxs-lookup"><span data-stu-id="3d0a9-122">**Backup and restoration tools**   Include who is to use the tools, and on which computers.</span></span> <span data-ttu-id="3d0a9-123">Para obter detalhes sobre as ferramentas discutidas neste tópico e as permissões necessárias, consulte [requisitos de backup e restauração no Lync Server 2013: ferramentas e permissões](lync-server-2013-backup-and-restoration-requirements-tools-and-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="3d0a9-123">For details about the tools discussed in this topic and necessary permissions, see [Backup and restoration requirements in Lync Server 2013: tools and permissions](lync-server-2013-backup-and-restoration-requirements-tools-and-permissions.md).</span></span>

  - <span data-ttu-id="3d0a9-124">**Local de backup**   identifique se os backups são mantidos localmente ou remotamente, levando a segurança e acessibilidade em consideração.</span><span class="sxs-lookup"><span data-stu-id="3d0a9-124">**Backup location**   Identify whether the backups are kept locally or remotely, taking security and accessibility into consideration.</span></span> <span data-ttu-id="3d0a9-125">Especifique a mídia a ser usada para os backups.</span><span class="sxs-lookup"><span data-stu-id="3d0a9-125">Specify the media to be used for the backups.</span></span>

  - <span data-ttu-id="3d0a9-126">**Os requisitos**   de hardware e software identificam e documentam os requisitos específicos de hardware e software, incluindo o hardware para armazenamento de backup e restauração de componentes específicos e qualquer software e conectividade de rede necessária para dar suporte a backup e restauração.</span><span class="sxs-lookup"><span data-stu-id="3d0a9-126">**Hardware and software requirements**   Identify and document your specific hardware and software requirements, including the hardware for backup storage and restoration of specific components and any software and network connectivity required to support backup and restoration.</span></span> <span data-ttu-id="3d0a9-127">Ao desenvolver seus requisitos de hardware e software, tenha em mente os vários cenários de restauração que se seguem.</span><span class="sxs-lookup"><span data-stu-id="3d0a9-127">As you develop your hardware and software requirements, keep in mind the various restoration scenarios that follow.</span></span>

  - <span data-ttu-id="3d0a9-128">**Cenários de restauração**   aqui estão os processos de restauração dos seguintes cenários:</span><span class="sxs-lookup"><span data-stu-id="3d0a9-128">**Restoration scenarios**   Here are the restoration processes for the following scenarios:</span></span>
    
      - <span data-ttu-id="3d0a9-129">Um pool de servidores do Lync falha.</span><span class="sxs-lookup"><span data-stu-id="3d0a9-129">A Lync Server pool fails.</span></span> <span data-ttu-id="3d0a9-130">Esse cenário requer a recriação de cada servidor no pool.</span><span class="sxs-lookup"><span data-stu-id="3d0a9-130">This scenario requires rebuilding each server in the pool.</span></span>
    
      - <span data-ttu-id="3d0a9-131">Um servidor Standard Edition falha.</span><span class="sxs-lookup"><span data-stu-id="3d0a9-131">A Standard Edition server fails.</span></span> <span data-ttu-id="3d0a9-132">Esse cenário requer a recriação do servidor em um computador novo ou limpo e a restauração de bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="3d0a9-132">This scenario requires rebuilding the server on a new or clean computer and restoring databases.</span></span>
    
      - <span data-ttu-id="3d0a9-133">Perda do repositório de gerenciamento central.</span><span class="sxs-lookup"><span data-stu-id="3d0a9-133">Loss of the Central Management store.</span></span> <span data-ttu-id="3d0a9-134">No mínimo, esse cenário exige a restauração e a publicação do repositório de gerenciamento central.</span><span class="sxs-lookup"><span data-stu-id="3d0a9-134">At a minimum, this scenario requires restoring and publishing the Central Management store.</span></span>
    
      - <span data-ttu-id="3d0a9-135">Perda de um servidor back-end quando o repositório de gerenciamento central ainda estiver funcionando normalmente.</span><span class="sxs-lookup"><span data-stu-id="3d0a9-135">Loss of a Back End Server when the Central Management store is still functioning normally.</span></span> <span data-ttu-id="3d0a9-136">Esse cenário requer a recriação do servidor em um computador novo ou limpo e a restauração de bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="3d0a9-136">This scenario requires rebuilding the server on a new or clean computer and restoring databases.</span></span>
    
      - <span data-ttu-id="3d0a9-137">Um servidor que é membro de um pool do Lync Server falha.</span><span class="sxs-lookup"><span data-stu-id="3d0a9-137">A server that is a member of a Lync Server pool fails.</span></span> <span data-ttu-id="3d0a9-138">Esse cenário requer a recriação do servidor em um computador novo ou limpo.</span><span class="sxs-lookup"><span data-stu-id="3d0a9-138">This scenario requires rebuilding the server on a new or clean computer.</span></span>
    
      - <span data-ttu-id="3d0a9-139">Um repositório de arquivos falha.</span><span class="sxs-lookup"><span data-stu-id="3d0a9-139">A File Store fails.</span></span> <span data-ttu-id="3d0a9-140">Esse cenário requer a restauração do servidor de arquivos ou do cluster de arquivos.</span><span class="sxs-lookup"><span data-stu-id="3d0a9-140">This scenario requires restoring the file server or file cluster.</span></span>
    
      - <span data-ttu-id="3d0a9-141">Falha em um banco de dados de arquivamento, monitoramento ou de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="3d0a9-141">An Archiving, Monitoring, or Persistent Chat database fails.</span></span> <span data-ttu-id="3d0a9-142">Esse cenário exige a recriação de bancos de dados e, se os dados forem críticos para a sua organização, a restauração dos dados.</span><span class="sxs-lookup"><span data-stu-id="3d0a9-142">This scenario requires recreating the databases, and, if the data is critical to your organization, restoring the data.</span></span> <span data-ttu-id="3d0a9-143">O arquivamento, o monitoramento e os dados de chat persistentes não são necessários para ter backup e execução do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3d0a9-143">Archiving, Monitoring, and Persistent Chat data is not required to get Lync Server back up and running.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

