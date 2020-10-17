---
title: Lync Server 2013 failover do repositório de gerenciamento central
description: Lync Server 2013 failover do repositório de gerenciamento central.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Central Management store failover
ms:assetid: f464d715-68a4-462c-9584-00f41ab10db0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205376(v=OCS.15)
ms:contentKeyID: 48185809
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d2960a55d6bdc49e00bf22997bc53946d4770fde
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544367"
---
# <a name="central-management-store-failover-in-lync-server-2013"></a><span data-ttu-id="33431-103">Failover do repositório de gerenciamento central no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="33431-103">Central Management store failover in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="33431-104">_**Última modificação do tópico:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="33431-104">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="33431-105">O repositório de gerenciamento central contém dados de configuração sobre servidores e serviços em sua implantação do Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="33431-105">The Central Management store contains configuration data about servers and services in your Lync 2013 deployment.</span></span> <span data-ttu-id="33431-106">Ele fornece um armazenamento robusto, esquematizado dos dados necessários para definir, configurar, manter, administrar, descrever e operar uma implantação do Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="33431-106">It provides a robust, schematized storage of the data needed to define, set up, maintain, administer, describe, and operate a Lync 2013 deployment.</span></span> <span data-ttu-id="33431-107">Também valida os dados para garantir a consistência da configuração.</span><span class="sxs-lookup"><span data-stu-id="33431-107">It also validates the data to ensure configuration consistency.</span></span>

<span data-ttu-id="33431-108">Cada implantação do Lync inclui um repositório de gerenciamento central, que é hospedado pelo servidor back-end de um pool de front-ends.</span><span class="sxs-lookup"><span data-stu-id="33431-108">Each Lync deployment includes one Central Management store, which is hosted by the Back End Server of one Front End pool.</span></span>

<span data-ttu-id="33431-109">Quando você estabelece um emparelhamento de pool que inclui o pool que hospeda o repositório de gerenciamento central, um banco de dados do repositório de gerenciamento central de backup é configurado no pool de backup e os serviços do repositório de gerenciamento central estão instalados nos dois pools.</span><span class="sxs-lookup"><span data-stu-id="33431-109">When you establish a pool pairing that includes the pool hosting the Central Management store, a backup Central Management store database is set up in the backup pool, and Central Management store services are installed in both pools.</span></span> <span data-ttu-id="33431-110">A qualquer momento, um dos dois bancos de dados do repositório de gerenciamento central é o mestre ativo e o outro é um standby.</span><span class="sxs-lookup"><span data-stu-id="33431-110">At any point in time, one of the two Central Management store databases is the active master, and the other is a standby.</span></span> <span data-ttu-id="33431-111">O conteúdo é replicado pelo Serviço de Backup do mestre ativo para o em espera.</span><span class="sxs-lookup"><span data-stu-id="33431-111">The content is replicated by the Backup Service from the active master to the standby.</span></span>

<span data-ttu-id="33431-112">Durante um failover de pool que envolve os pools que hospedam o repositório de gerenciamento central, o administrador deve fazer failover do repositório de gerenciamento central antes de falhar sobre o pool de front-ends.</span><span class="sxs-lookup"><span data-stu-id="33431-112">During a pool failover that involves the pools hosting the Central Management store, the administrator must fail over the Central Management store before failing over the Front End pool.</span></span>

<span data-ttu-id="33431-113">Após o desastre ser reparado, não é necessário fazer failback do repositório de gerenciamento central.</span><span class="sxs-lookup"><span data-stu-id="33431-113">After the disaster is repaired, it is not necessary to fail back the Central Management store.</span></span> <span data-ttu-id="33431-114">Após o reparo, o repositório de gerenciamento central no pool de backup original pode permanecer como o mestre ativo.</span><span class="sxs-lookup"><span data-stu-id="33431-114">After repair, the Central Management store in the original backup pool can remain as the active master.</span></span>

<span data-ttu-id="33431-115">Os destinos de engenharia para failover do repositório de gerenciamento central são 5 minutos para o objetivo de tempo de recuperação (RTO) e 5 minutos para o objetivo de ponto de recuperação (RPO).</span><span class="sxs-lookup"><span data-stu-id="33431-115">The engineering targets for Central Management store failover are 5 minutes for recovery time objective (RTO) and 5 minutes for recovery point objective (RPO).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

