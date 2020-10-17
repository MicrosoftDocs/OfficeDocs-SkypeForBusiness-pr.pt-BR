---
title: 'Lync Server 2013: restaurando dados e configurações'
description: 'Lync Server 2013: restaurando dados e configurações.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring data and settings
ms:assetid: b07f5dd7-7bed-4819-8cb5-617f5acd478e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202185(v=OCS.15)
ms:contentKeyID: 51541503
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 694b1e362d729d354b08367d31c47e8ca866dd91
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560287"
---
# <a name="restoring-data-and-settings-in-lync-server-2013"></a><span data-ttu-id="5a54d-103">Restaurando dados e configurações no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5a54d-103">Restoring data and settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5a54d-104">_**Última modificação do tópico:** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="5a54d-104">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="5a54d-105">Se você tiver implementado uma topologia de recuperação de desastre com pools emparelhados, e um desses pools de front-ends tiver desaparecido e você precisar restaurar rapidamente o serviço para seus usuários, consulte [failover de um pool no Lync Server 2013](lync-server-2013-failing-over-a-pool.md).</span><span class="sxs-lookup"><span data-stu-id="5a54d-105">If you have implemented a disaster recovery topology with paired pools, and one of those Front End pools has gone down and you need to quickly restore service to your users, see [Failing over a pool in Lync Server 2013](lync-server-2013-failing-over-a-pool.md).</span></span> <span data-ttu-id="5a54d-106">Caso contrário, use as informações nos seguintes tópicos, juntamente com as planilhas em [planilhas de backup e restauração para o Lync server 2013](lync-server-2013-backup-and-restoration-worksheets.md), para restaurar o Lync Server após uma falha ou uma interrupção.</span><span class="sxs-lookup"><span data-stu-id="5a54d-106">Otherwise, use the information in the following topics, along with the worksheets in [Backup and restoration worksheets for Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md), to restore Lync Server after a failure or outage.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5a54d-107">Para reduzir o tempo de inatividade e a possível perda de dados, execute os procedimentos de restauração descritos neste documento somente se os procedimentos de solução de problemas não forem eficazes para identificar e corrigir o problema.</span><span class="sxs-lookup"><span data-stu-id="5a54d-107">To reduce downtime and potential data loss, perform the restoration procedures described in this document only if troubleshooting procedures are not effective in identifying and correcting the problem.</span></span> <span data-ttu-id="5a54d-108">Durante a solução de problemas, tente minimizar o impacto em outros servidores e componentes ao desligar e reiniciar os servidores.</span><span class="sxs-lookup"><span data-stu-id="5a54d-108">During troubleshooting, try to minimize the impact on other servers and components as you shut down and restart servers.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="5a54d-109">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="5a54d-109">In This Section</span></span>

  - [<span data-ttu-id="5a54d-110">Preparando para restaurar o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5a54d-110">Preparing to restore Lync Server 2013</span></span>](lync-server-2013-preparing-to-restore-lync-server.md)

  - [<span data-ttu-id="5a54d-111">Restaurando um servidor Standard Edition no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5a54d-111">Restoring a Standard Edition server in Lync Server 2013</span></span>](lync-server-2013-restoring-a-standard-edition-server.md)

  - [<span data-ttu-id="5a54d-112">Restaurando o servidor que hospeda o repositório de gerenciamento central no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5a54d-112">Restoring the server hosting the Central Management store in Lync Server 2013</span></span>](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md)

  - [<span data-ttu-id="5a54d-113">Restaurando um servidor back-end Enterprise Edition no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5a54d-113">Restoring an Enterprise Edition Back End Server in Lync Server 2013</span></span>](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md)

  - [<span data-ttu-id="5a54d-114">Restaurando um servidor membro Enterprise Edition no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5a54d-114">Restoring an Enterprise Edition member server in Lync Server 2013</span></span>](lync-server-2013-restoring-an-enterprise-edition-member-server.md)

  - [<span data-ttu-id="5a54d-115">Restaurando um pool do Lync Server no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5a54d-115">Restoring a Lync Server pool in Lync Server 2013</span></span>](lync-server-2013-restoring-a-lync-server-pool.md)

  - [<span data-ttu-id="5a54d-116">Executando um failover de pool de front-ends ABC no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5a54d-116">Performing an ABC Front End pool failover in Lync Server 2013</span></span>](lync-server-2013-performing-an-abc-front-end-pool-failover.md)

  - [<span data-ttu-id="5a54d-117">Restaurando um repositório de arquivos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5a54d-117">Restoring a file store in Lync Server 2013</span></span>](lync-server-2013-restoring-a-file-store.md)

  - [<span data-ttu-id="5a54d-118">Restauração de dados de monitoramento ou arquivamento no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5a54d-118">Restoring monitoring or archiving data in Lync Server 2013</span></span>](lync-server-2013-restoring-monitoring-or-archiving-data.md)

  - [<span data-ttu-id="5a54d-119">Restaurando dados de chat persistente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5a54d-119">Restoring Persistent Chat data in Lync Server 2013</span></span>](lync-server-2013-restoring-persistent-chat-data.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

