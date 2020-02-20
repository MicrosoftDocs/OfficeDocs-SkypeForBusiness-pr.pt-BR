---
title: Capacidade de expansão do Lync Server 2013
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
ms.openlocfilehash: 3bd340d46855f01e8ff43dc9f66b527e5df1967c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144387"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="scalability-with-lync-server-2013"></a><span data-ttu-id="2d2da-102">Escalabilidade com Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2d2da-102">Scalability with Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2d2da-103">_**Última modificação do tópico:** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="2d2da-103">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="2d2da-104">O Lync Server é oferecido em duas edições, Enterprise Edition e Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="2d2da-104">Lync Server is offered in two editions, Enterprise Edition and Standard Edition.</span></span> <span data-ttu-id="2d2da-105">As diferentes edições destinam-se principalmente a diferentes portes de organizações.</span><span class="sxs-lookup"><span data-stu-id="2d2da-105">The different editions are intended primarily for different sizes of organizations.</span></span> <span data-ttu-id="2d2da-106">Como é mostrado na tabela a seguir, ambas as edições dão suporte a toda a funcionalidade em todas as cargas de trabalho, exceto para alta disponibilidade e recuperação de desastres.</span><span class="sxs-lookup"><span data-stu-id="2d2da-106">As shown in the following table, both editions support all functionality in all workloads, except for high availability and disaster recovery.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2d2da-107">Recurso</span><span class="sxs-lookup"><span data-stu-id="2d2da-107">Feature</span></span></th>
<th><span data-ttu-id="2d2da-108">Aceito na Enterprise Edition?</span><span class="sxs-lookup"><span data-stu-id="2d2da-108">Supported in Enterprise Edition?</span></span></th>
<th><span data-ttu-id="2d2da-109">Aceito na Standard Edition?</span><span class="sxs-lookup"><span data-stu-id="2d2da-109">Supported in Standard Edition?</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2d2da-110">Mensagens instantâneas (IM) e presença</span><span class="sxs-lookup"><span data-stu-id="2d2da-110">Instant messaging (IM) and presence</span></span></p></td>
<td><p><span data-ttu-id="2d2da-111">Sim</span><span class="sxs-lookup"><span data-stu-id="2d2da-111">Yes</span></span></p></td>
<td><p><span data-ttu-id="2d2da-112">Sim</span><span class="sxs-lookup"><span data-stu-id="2d2da-112">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2d2da-113">Conferências</span><span class="sxs-lookup"><span data-stu-id="2d2da-113">Conferencing</span></span></p></td>
<td><p><span data-ttu-id="2d2da-114">Sim</span><span class="sxs-lookup"><span data-stu-id="2d2da-114">Yes</span></span></p></td>
<td><p><span data-ttu-id="2d2da-115">Sim</span><span class="sxs-lookup"><span data-stu-id="2d2da-115">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2d2da-116">Conferência A/V</span><span class="sxs-lookup"><span data-stu-id="2d2da-116">A/V conferencing</span></span></p></td>
<td><p><span data-ttu-id="2d2da-117">Sim</span><span class="sxs-lookup"><span data-stu-id="2d2da-117">Yes</span></span></p></td>
<td><p><span data-ttu-id="2d2da-118">Sim</span><span class="sxs-lookup"><span data-stu-id="2d2da-118">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2d2da-119">Conferência Discada</span><span class="sxs-lookup"><span data-stu-id="2d2da-119">Dial-in conferencing</span></span></p></td>
<td><p><span data-ttu-id="2d2da-120">Sim</span><span class="sxs-lookup"><span data-stu-id="2d2da-120">Yes</span></span></p></td>
<td><p><span data-ttu-id="2d2da-121">Sim</span><span class="sxs-lookup"><span data-stu-id="2d2da-121">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2d2da-122">Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="2d2da-122">Enterprise Voice</span></span></p></td>
<td><p><span data-ttu-id="2d2da-123">Sim</span><span class="sxs-lookup"><span data-stu-id="2d2da-123">Yes</span></span></p></td>
<td><p><span data-ttu-id="2d2da-124">Sim</span><span class="sxs-lookup"><span data-stu-id="2d2da-124">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2d2da-125">Virtualização</span><span class="sxs-lookup"><span data-stu-id="2d2da-125">Virtualization</span></span></p></td>
<td><p><span data-ttu-id="2d2da-126">Sim</span><span class="sxs-lookup"><span data-stu-id="2d2da-126">Yes</span></span></p></td>
<td><p><span data-ttu-id="2d2da-127">Sim</span><span class="sxs-lookup"><span data-stu-id="2d2da-127">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2d2da-128">Alta disponibilidade, failover e recuperação de desastres</span><span class="sxs-lookup"><span data-stu-id="2d2da-128">High availability, failover, and disaster recovery</span></span></p></td>
<td><p><span data-ttu-id="2d2da-129">Sim</span><span class="sxs-lookup"><span data-stu-id="2d2da-129">Yes</span></span></p></td>
<td><p><span data-ttu-id="2d2da-130">Não</span><span class="sxs-lookup"><span data-stu-id="2d2da-130">No</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

