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
ms.openlocfilehash: 130b1958b418aa2b09e572f137598487dc2c3401
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049863"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scalability-with-lync-server-2013"></a><span data-ttu-id="79c41-102">Escalabilidade com Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="79c41-102">Scalability with Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="79c41-103">_**Última modificação do tópico:** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="79c41-103">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="79c41-104">O Lync Server é oferecido em duas edições, Enterprise Edition e Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="79c41-104">Lync Server is offered in two editions, Enterprise Edition and Standard Edition.</span></span> <span data-ttu-id="79c41-105">As diferentes edições destinam-se principalmente a diferentes portes de organizações.</span><span class="sxs-lookup"><span data-stu-id="79c41-105">The different editions are intended primarily for different sizes of organizations.</span></span> <span data-ttu-id="79c41-106">Como é mostrado na tabela a seguir, ambas as edições dão suporte a toda a funcionalidade em todas as cargas de trabalho, exceto para alta disponibilidade e recuperação de desastres.</span><span class="sxs-lookup"><span data-stu-id="79c41-106">As shown in the following table, both editions support all functionality in all workloads, except for high availability and disaster recovery.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="79c41-107">Recurso</span><span class="sxs-lookup"><span data-stu-id="79c41-107">Feature</span></span></th>
<th><span data-ttu-id="79c41-108">Aceito na Enterprise Edition?</span><span class="sxs-lookup"><span data-stu-id="79c41-108">Supported in Enterprise Edition?</span></span></th>
<th><span data-ttu-id="79c41-109">Aceito na Standard Edition?</span><span class="sxs-lookup"><span data-stu-id="79c41-109">Supported in Standard Edition?</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="79c41-110">Mensagens instantâneas (IM) e presença</span><span class="sxs-lookup"><span data-stu-id="79c41-110">Instant messaging (IM) and presence</span></span></p></td>
<td><p><span data-ttu-id="79c41-111">Sim</span><span class="sxs-lookup"><span data-stu-id="79c41-111">Yes</span></span></p></td>
<td><p><span data-ttu-id="79c41-112">Sim</span><span class="sxs-lookup"><span data-stu-id="79c41-112">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="79c41-113">Conferências</span><span class="sxs-lookup"><span data-stu-id="79c41-113">Conferencing</span></span></p></td>
<td><p><span data-ttu-id="79c41-114">Sim</span><span class="sxs-lookup"><span data-stu-id="79c41-114">Yes</span></span></p></td>
<td><p><span data-ttu-id="79c41-115">Sim</span><span class="sxs-lookup"><span data-stu-id="79c41-115">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="79c41-116">Conferência A/V</span><span class="sxs-lookup"><span data-stu-id="79c41-116">A/V conferencing</span></span></p></td>
<td><p><span data-ttu-id="79c41-117">Sim</span><span class="sxs-lookup"><span data-stu-id="79c41-117">Yes</span></span></p></td>
<td><p><span data-ttu-id="79c41-118">Sim</span><span class="sxs-lookup"><span data-stu-id="79c41-118">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="79c41-119">Conferência Discada</span><span class="sxs-lookup"><span data-stu-id="79c41-119">Dial-in conferencing</span></span></p></td>
<td><p><span data-ttu-id="79c41-120">Sim</span><span class="sxs-lookup"><span data-stu-id="79c41-120">Yes</span></span></p></td>
<td><p><span data-ttu-id="79c41-121">Sim</span><span class="sxs-lookup"><span data-stu-id="79c41-121">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="79c41-122">Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="79c41-122">Enterprise Voice</span></span></p></td>
<td><p><span data-ttu-id="79c41-123">Sim</span><span class="sxs-lookup"><span data-stu-id="79c41-123">Yes</span></span></p></td>
<td><p><span data-ttu-id="79c41-124">Sim</span><span class="sxs-lookup"><span data-stu-id="79c41-124">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="79c41-125">Virtualização</span><span class="sxs-lookup"><span data-stu-id="79c41-125">Virtualization</span></span></p></td>
<td><p><span data-ttu-id="79c41-126">Sim</span><span class="sxs-lookup"><span data-stu-id="79c41-126">Yes</span></span></p></td>
<td><p><span data-ttu-id="79c41-127">Sim</span><span class="sxs-lookup"><span data-stu-id="79c41-127">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="79c41-128">Alta disponibilidade, failover e recuperação de desastres</span><span class="sxs-lookup"><span data-stu-id="79c41-128">High availability, failover, and disaster recovery</span></span></p></td>
<td><p><span data-ttu-id="79c41-129">Sim</span><span class="sxs-lookup"><span data-stu-id="79c41-129">Yes</span></span></p></td>
<td><p><span data-ttu-id="79c41-130">Não</span><span class="sxs-lookup"><span data-stu-id="79c41-130">No</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

