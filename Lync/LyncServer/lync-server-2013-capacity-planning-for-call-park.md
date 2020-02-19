---
title: 'Lync Server 2013: planejamento de capacidade para estacionamento de chamada'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Capacity planning for Call Park
ms:assetid: 75520310-760a-4b1b-bcc1-4d724d13f87a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg416493(v=OCS.15)
ms:contentKeyID: 48184529
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4e3bdb6899ae92d8f4d5561bd81266922284d950
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137210"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="capacity-planning-for-call-park-in-lync-server-2013"></a><span data-ttu-id="2cdff-102">Planejamento de capacidade para estacionamento de chamadas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2cdff-102">Capacity planning for Call Park in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2cdff-103">_**Última modificação do tópico:** 2012-09-13_</span><span class="sxs-lookup"><span data-stu-id="2cdff-103">_**Topic Last Modified:** 2012-09-13_</span></span>

<div id="sectionSection0" class="section">

<span data-ttu-id="2cdff-104">A tabela a seguir descreve o modelo de usuário de estacionamento de chamada que você pode usar como base para os requisitos de planejamento de capacidade.</span><span class="sxs-lookup"><span data-stu-id="2cdff-104">The following table describes the Call Park user model that you can use as the basis for capacity planning requirements.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="2cdff-105">Tenha em mente que, para o planejamento da capacidade de recuperação de desastres, cada pool de um pool emparelhado deve ser capaz de lidar com as cargas de trabalho para serviços de estacionamento de chamadas nos dois pools.</span><span class="sxs-lookup"><span data-stu-id="2cdff-105">Keep in mind that, for disaster recovery capacity planning, each pool of a paired pool should be able to handle the workloads for Call Park services in both pools.</span></span>



</div>

### <a name="call-park-user-model"></a><span data-ttu-id="2cdff-106">Modelo de usuário do estacionamento de chamada Park</span><span class="sxs-lookup"><span data-stu-id="2cdff-106">Call Park User Model</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2cdff-107">Indicador</span><span class="sxs-lookup"><span data-stu-id="2cdff-107">Metric</span></span></th>
<th><span data-ttu-id="2cdff-108">Por pool de front-ends (com 8 servidores front-end)</span><span class="sxs-lookup"><span data-stu-id="2cdff-108">Per Front End pool (with 8 Front End Servers)</span></span></th>
<th><span data-ttu-id="2cdff-109">Por servidor Standard Edition</span><span class="sxs-lookup"><span data-stu-id="2cdff-109">Per Standard Edition server</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2cdff-110">Taxa de estacionamento</span><span class="sxs-lookup"><span data-stu-id="2cdff-110">Park rate</span></span></p></td>
<td><p><span data-ttu-id="2cdff-111">8 por minuto</span><span class="sxs-lookup"><span data-stu-id="2cdff-111">8 per minute</span></span></p></td>
<td><p><span data-ttu-id="2cdff-112">1 por minuto</span><span class="sxs-lookup"><span data-stu-id="2cdff-112">1 per minute</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cdff-113">Recuperar a taxa de chamada estacionada</span><span class="sxs-lookup"><span data-stu-id="2cdff-113">Retrieve parked call rate</span></span></p></td>
<td><p><span data-ttu-id="2cdff-114">8 por minuto</span><span class="sxs-lookup"><span data-stu-id="2cdff-114">8 per minute</span></span></p></td>
<td><p><span data-ttu-id="2cdff-115">1 por minuto</span><span class="sxs-lookup"><span data-stu-id="2cdff-115">1 per minute</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2cdff-116">Duração média do estacionamento</span><span class="sxs-lookup"><span data-stu-id="2cdff-116">Average park duration</span></span></p></td>
<td><p><span data-ttu-id="2cdff-117">60 segundos</span><span class="sxs-lookup"><span data-stu-id="2cdff-117">60 seconds</span></span></p></td>
<td><p><span data-ttu-id="2cdff-118">60 segundos</span><span class="sxs-lookup"><span data-stu-id="2cdff-118">60 seconds</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

