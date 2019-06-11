---
title: 'Lync Server 2013: Escalabilidade'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Scalability
ms:assetid: 46fa0cb5-1507-4a12-ad3f-ba64585e2dc4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg417160(v=OCS.15)
ms:contentKeyID: 48183995
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0dfdc96934871fd2e73af30507288c734e786cc0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822164"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scalability-with-lync-server-2013"></a><span data-ttu-id="d0a24-102">Escalabilidade com Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d0a24-102">Scalability with Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d0a24-103">_**Tópico da última modificação:** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="d0a24-103">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="d0a24-104">O Lync Server é oferecido em duas edições, Enterprise Edition e Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="d0a24-104">Lync Server is offered in two editions, Enterprise Edition and Standard Edition.</span></span> <span data-ttu-id="d0a24-105">As diferentes edições são direcionadas principalmente para diferentes tamanhos de organizações.</span><span class="sxs-lookup"><span data-stu-id="d0a24-105">The different editions are intended primarily for different sizes of organizations.</span></span> <span data-ttu-id="d0a24-106">Conforme mostrado na tabela a seguir, ambas as edições dão suporte a toda a funcionalidade em todas as cargas de trabalho, exceto para alta disponibilidade e recuperação de desastres.</span><span class="sxs-lookup"><span data-stu-id="d0a24-106">As shown in the following table, both editions support all functionality in all workloads, except for high availability and disaster recovery.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d0a24-107">Recurso</span><span class="sxs-lookup"><span data-stu-id="d0a24-107">Feature</span></span></th>
<th><span data-ttu-id="d0a24-108">Tem suporte na Enterprise Edition?</span><span class="sxs-lookup"><span data-stu-id="d0a24-108">Supported in Enterprise Edition?</span></span></th>
<th><span data-ttu-id="d0a24-109">Compatível com a Standard Edition?</span><span class="sxs-lookup"><span data-stu-id="d0a24-109">Supported in Standard Edition?</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d0a24-110">Mensagens instantâneas (IM) e presença</span><span class="sxs-lookup"><span data-stu-id="d0a24-110">Instant messaging (IM) and presence</span></span></p></td>
<td><p><span data-ttu-id="d0a24-111">Sim </span><span class="sxs-lookup"><span data-stu-id="d0a24-111">Yes</span></span></p></td>
<td><p><span data-ttu-id="d0a24-112">Sim</span><span class="sxs-lookup"><span data-stu-id="d0a24-112">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0a24-113">Conferência</span><span class="sxs-lookup"><span data-stu-id="d0a24-113">Conferencing</span></span></p></td>
<td><p><span data-ttu-id="d0a24-114">Sim </span><span class="sxs-lookup"><span data-stu-id="d0a24-114">Yes</span></span></p></td>
<td><p><span data-ttu-id="d0a24-115">Sim</span><span class="sxs-lookup"><span data-stu-id="d0a24-115">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0a24-116">Conferências de áudio/vídeo</span><span class="sxs-lookup"><span data-stu-id="d0a24-116">A/V conferencing</span></span></p></td>
<td><p><span data-ttu-id="d0a24-117">Sim </span><span class="sxs-lookup"><span data-stu-id="d0a24-117">Yes</span></span></p></td>
<td><p><span data-ttu-id="d0a24-118">Sim</span><span class="sxs-lookup"><span data-stu-id="d0a24-118">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0a24-119">Conferência discada</span><span class="sxs-lookup"><span data-stu-id="d0a24-119">Dial-in conferencing</span></span></p></td>
<td><p><span data-ttu-id="d0a24-120">Sim </span><span class="sxs-lookup"><span data-stu-id="d0a24-120">Yes</span></span></p></td>
<td><p><span data-ttu-id="d0a24-121">Sim</span><span class="sxs-lookup"><span data-stu-id="d0a24-121">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0a24-122">Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="d0a24-122">Enterprise Voice</span></span></p></td>
<td><p><span data-ttu-id="d0a24-123">Sim </span><span class="sxs-lookup"><span data-stu-id="d0a24-123">Yes</span></span></p></td>
<td><p><span data-ttu-id="d0a24-124">Sim</span><span class="sxs-lookup"><span data-stu-id="d0a24-124">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0a24-125">Visualização</span><span class="sxs-lookup"><span data-stu-id="d0a24-125">Virtualization</span></span></p></td>
<td><p><span data-ttu-id="d0a24-126">Sim </span><span class="sxs-lookup"><span data-stu-id="d0a24-126">Yes</span></span></p></td>
<td><p><span data-ttu-id="d0a24-127">Sim</span><span class="sxs-lookup"><span data-stu-id="d0a24-127">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0a24-128">Alta disponibilidade, failover e recuperação de desastres</span><span class="sxs-lookup"><span data-stu-id="d0a24-128">High availability, failover, and disaster recovery</span></span></p></td>
<td><p><span data-ttu-id="d0a24-129">Sim</span><span class="sxs-lookup"><span data-stu-id="d0a24-129">Yes</span></span></p></td>
<td><p><span data-ttu-id="d0a24-130">Não</span><span class="sxs-lookup"><span data-stu-id="d0a24-130">No</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

