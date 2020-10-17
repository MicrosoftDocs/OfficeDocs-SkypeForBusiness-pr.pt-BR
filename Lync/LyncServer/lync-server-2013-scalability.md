---
title: Capacidade de expansão do Lync Server 2013
description: Lync Server 2013 escalabilidade.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scalability
ms:assetid: 46fa0cb5-1507-4a12-ad3f-ba64585e2dc4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg417160(v=OCS.15)
ms:contentKeyID: 48183995
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 28cd5820755ffd1eb863ed6f2369b5756a7ae3f5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543787"
---
# <a name="scalability-with-lync-server-2013"></a><span data-ttu-id="1f224-103">Escalabilidade com Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1f224-103">Scalability with Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1f224-104">_**Última modificação do tópico:** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="1f224-104">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="1f224-105">O Lync Server é oferecido em duas edições, Enterprise Edition e Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="1f224-105">Lync Server is offered in two editions, Enterprise Edition and Standard Edition.</span></span> <span data-ttu-id="1f224-106">As diferentes edições destinam-se principalmente a diferentes portes de organizações.</span><span class="sxs-lookup"><span data-stu-id="1f224-106">The different editions are intended primarily for different sizes of organizations.</span></span> <span data-ttu-id="1f224-107">Como é mostrado na tabela a seguir, ambas as edições dão suporte a toda a funcionalidade em todas as cargas de trabalho, exceto para alta disponibilidade e recuperação de desastres.</span><span class="sxs-lookup"><span data-stu-id="1f224-107">As shown in the following table, both editions support all functionality in all workloads, except for high availability and disaster recovery.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1f224-108">Recurso</span><span class="sxs-lookup"><span data-stu-id="1f224-108">Feature</span></span></th>
<th><span data-ttu-id="1f224-109">Aceito na Enterprise Edition?</span><span class="sxs-lookup"><span data-stu-id="1f224-109">Supported in Enterprise Edition?</span></span></th>
<th><span data-ttu-id="1f224-110">Aceito na Standard Edition?</span><span class="sxs-lookup"><span data-stu-id="1f224-110">Supported in Standard Edition?</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1f224-111">Mensagens instantâneas (IM) e presença</span><span class="sxs-lookup"><span data-stu-id="1f224-111">Instant messaging (IM) and presence</span></span></p></td>
<td><p><span data-ttu-id="1f224-112">Sim</span><span class="sxs-lookup"><span data-stu-id="1f224-112">Yes</span></span></p></td>
<td><p><span data-ttu-id="1f224-113">Sim</span><span class="sxs-lookup"><span data-stu-id="1f224-113">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1f224-114">Conferências</span><span class="sxs-lookup"><span data-stu-id="1f224-114">Conferencing</span></span></p></td>
<td><p><span data-ttu-id="1f224-115">Sim</span><span class="sxs-lookup"><span data-stu-id="1f224-115">Yes</span></span></p></td>
<td><p><span data-ttu-id="1f224-116">Sim</span><span class="sxs-lookup"><span data-stu-id="1f224-116">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1f224-117">Conferência A/V</span><span class="sxs-lookup"><span data-stu-id="1f224-117">A/V conferencing</span></span></p></td>
<td><p><span data-ttu-id="1f224-118">Sim</span><span class="sxs-lookup"><span data-stu-id="1f224-118">Yes</span></span></p></td>
<td><p><span data-ttu-id="1f224-119">Sim</span><span class="sxs-lookup"><span data-stu-id="1f224-119">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1f224-120">Conferência Discada</span><span class="sxs-lookup"><span data-stu-id="1f224-120">Dial-in conferencing</span></span></p></td>
<td><p><span data-ttu-id="1f224-121">Sim</span><span class="sxs-lookup"><span data-stu-id="1f224-121">Yes</span></span></p></td>
<td><p><span data-ttu-id="1f224-122">Sim</span><span class="sxs-lookup"><span data-stu-id="1f224-122">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1f224-123">Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="1f224-123">Enterprise Voice</span></span></p></td>
<td><p><span data-ttu-id="1f224-124">Sim</span><span class="sxs-lookup"><span data-stu-id="1f224-124">Yes</span></span></p></td>
<td><p><span data-ttu-id="1f224-125">Sim</span><span class="sxs-lookup"><span data-stu-id="1f224-125">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1f224-126">Virtualização</span><span class="sxs-lookup"><span data-stu-id="1f224-126">Virtualization</span></span></p></td>
<td><p><span data-ttu-id="1f224-127">Sim</span><span class="sxs-lookup"><span data-stu-id="1f224-127">Yes</span></span></p></td>
<td><p><span data-ttu-id="1f224-128">Sim</span><span class="sxs-lookup"><span data-stu-id="1f224-128">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1f224-129">Alta disponibilidade, failover e recuperação de desastres</span><span class="sxs-lookup"><span data-stu-id="1f224-129">High availability, failover, and disaster recovery</span></span></p></td>
<td><p><span data-ttu-id="1f224-130">Sim</span><span class="sxs-lookup"><span data-stu-id="1f224-130">Yes</span></span></p></td>
<td><p><span data-ttu-id="1f224-131">Não</span><span class="sxs-lookup"><span data-stu-id="1f224-131">No</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

