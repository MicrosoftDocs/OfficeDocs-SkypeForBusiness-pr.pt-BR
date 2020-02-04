---
title: 'Lync Server 2013: Escalabilidade'
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
ms.openlocfilehash: e6ff4828bdfddbfca7734836fdfdbe24f0b90c4a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765009"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scalability-with-lync-server-2013"></a><span data-ttu-id="39ec1-102">Escalabilidade com Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="39ec1-102">Scalability with Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="39ec1-103">_**Tópico da última modificação:** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="39ec1-103">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="39ec1-104">O Lync Server é oferecido em duas edições, Enterprise Edition e Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="39ec1-104">Lync Server is offered in two editions, Enterprise Edition and Standard Edition.</span></span> <span data-ttu-id="39ec1-105">As diferentes edições são direcionadas principalmente para diferentes tamanhos de organizações.</span><span class="sxs-lookup"><span data-stu-id="39ec1-105">The different editions are intended primarily for different sizes of organizations.</span></span> <span data-ttu-id="39ec1-106">Conforme mostrado na tabela a seguir, ambas as edições dão suporte a toda a funcionalidade em todas as cargas de trabalho, exceto para alta disponibilidade e recuperação de desastres.</span><span class="sxs-lookup"><span data-stu-id="39ec1-106">As shown in the following table, both editions support all functionality in all workloads, except for high availability and disaster recovery.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="39ec1-107">Recurso</span><span class="sxs-lookup"><span data-stu-id="39ec1-107">Feature</span></span></th>
<th><span data-ttu-id="39ec1-108">Tem suporte na Enterprise Edition?</span><span class="sxs-lookup"><span data-stu-id="39ec1-108">Supported in Enterprise Edition?</span></span></th>
<th><span data-ttu-id="39ec1-109">Compatível com a Standard Edition?</span><span class="sxs-lookup"><span data-stu-id="39ec1-109">Supported in Standard Edition?</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="39ec1-110">Mensagens instantâneas (IM) e presença</span><span class="sxs-lookup"><span data-stu-id="39ec1-110">Instant messaging (IM) and presence</span></span></p></td>
<td><p><span data-ttu-id="39ec1-111">Sim</span><span class="sxs-lookup"><span data-stu-id="39ec1-111">Yes</span></span></p></td>
<td><p><span data-ttu-id="39ec1-112">Sim</span><span class="sxs-lookup"><span data-stu-id="39ec1-112">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="39ec1-113">Conferência</span><span class="sxs-lookup"><span data-stu-id="39ec1-113">Conferencing</span></span></p></td>
<td><p><span data-ttu-id="39ec1-114">Sim</span><span class="sxs-lookup"><span data-stu-id="39ec1-114">Yes</span></span></p></td>
<td><p><span data-ttu-id="39ec1-115">Sim</span><span class="sxs-lookup"><span data-stu-id="39ec1-115">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="39ec1-116">Conferências de áudio/vídeo</span><span class="sxs-lookup"><span data-stu-id="39ec1-116">A/V conferencing</span></span></p></td>
<td><p><span data-ttu-id="39ec1-117">Sim</span><span class="sxs-lookup"><span data-stu-id="39ec1-117">Yes</span></span></p></td>
<td><p><span data-ttu-id="39ec1-118">Sim</span><span class="sxs-lookup"><span data-stu-id="39ec1-118">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="39ec1-119">Conferência discada</span><span class="sxs-lookup"><span data-stu-id="39ec1-119">Dial-in conferencing</span></span></p></td>
<td><p><span data-ttu-id="39ec1-120">Sim</span><span class="sxs-lookup"><span data-stu-id="39ec1-120">Yes</span></span></p></td>
<td><p><span data-ttu-id="39ec1-121">Sim</span><span class="sxs-lookup"><span data-stu-id="39ec1-121">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="39ec1-122">Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="39ec1-122">Enterprise Voice</span></span></p></td>
<td><p><span data-ttu-id="39ec1-123">Sim</span><span class="sxs-lookup"><span data-stu-id="39ec1-123">Yes</span></span></p></td>
<td><p><span data-ttu-id="39ec1-124">Sim</span><span class="sxs-lookup"><span data-stu-id="39ec1-124">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="39ec1-125">Visualização</span><span class="sxs-lookup"><span data-stu-id="39ec1-125">Virtualization</span></span></p></td>
<td><p><span data-ttu-id="39ec1-126">Sim</span><span class="sxs-lookup"><span data-stu-id="39ec1-126">Yes</span></span></p></td>
<td><p><span data-ttu-id="39ec1-127">Sim</span><span class="sxs-lookup"><span data-stu-id="39ec1-127">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="39ec1-128">Alta disponibilidade, failover e recuperação de desastres</span><span class="sxs-lookup"><span data-stu-id="39ec1-128">High availability, failover, and disaster recovery</span></span></p></td>
<td><p><span data-ttu-id="39ec1-129">Sim</span><span class="sxs-lookup"><span data-stu-id="39ec1-129">Yes</span></span></p></td>
<td><p><span data-ttu-id="39ec1-130">Não</span><span class="sxs-lookup"><span data-stu-id="39ec1-130">No</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

