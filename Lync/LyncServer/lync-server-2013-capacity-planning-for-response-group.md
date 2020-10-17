---
title: 'Lync Server 2013: planejamento de capacidade para grupo de resposta'
description: 'Lync Server 2013: planejamento de capacidade para grupo de resposta.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Capacity planning for Response Group
ms:assetid: a2459a69-1f45-4f2f-bca5-d4f442708e44
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412754(v=OCS.15)
ms:contentKeyID: 48184951
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 78c543f558f67deaaeb781b308aa5f68d39cd785
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544427"
---
# <a name="capacity-planning-for-response-group-in-lync-server-2013"></a><span data-ttu-id="80206-103">Planejamento de capacidade para grupo de resposta no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="80206-103">Capacity planning for Response Group in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="80206-104">_**Última modificação do tópico:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="80206-104">_**Topic Last Modified:** 2012-10-29_</span></span>

<div id="sectionSection0" class="section">

<span data-ttu-id="80206-105">A tabela a seguir descreve o modelo de usuário do grupo de resposta que você pode usar como base para os requisitos de planejamento de capacidade.</span><span class="sxs-lookup"><span data-stu-id="80206-105">The following table describes the Response Group user model that you can use as the basis for capacity planning requirements.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="80206-p101">Os números na tabela a seguir assumem que arquivos de 16 kHz, mono, Wave (.wav) de 16 bits sejam usados para todos os arquivos de áudio do grupo de resposta. Se você usa outros formatos de arquivo, como Windows Media Audio (.wma), os números podem variar.</span><span class="sxs-lookup"><span data-stu-id="80206-p101">The numbers in the following table assume that you use 16 kHz, mono, 16-bit Wave (.wav) files for all response group audio files. If you use other file formats, such as Windows Media Audio (.wma), the numbers may vary.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="80206-108">Tenha em mente que para planejar a capacidade de recuperação de desastres, cada pool de um pool pareado deve poder lidar com cargas de trabalho de todos os grupos de resposta, em ambos os pools.</span><span class="sxs-lookup"><span data-stu-id="80206-108">Keep in mind that for disaster recovery capacity planning, each pool of a paired pool should be able to handle the workloads for all the response groups in both pools.</span></span>



</div>

### <a name="response-group-user-model"></a><span data-ttu-id="80206-109">Modelo de Usuário do Grupo de Resposta</span><span class="sxs-lookup"><span data-stu-id="80206-109">Response Group User Model</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="80206-110">Indicador</span><span class="sxs-lookup"><span data-stu-id="80206-110">Metric</span></span></th>
<th><span data-ttu-id="80206-111">Por pool Enterprise Edition (com 8 servidores front-end)</span><span class="sxs-lookup"><span data-stu-id="80206-111">Per Enterprise Edition pool (With 8 Front End Servers)</span></span></th>
<th><span data-ttu-id="80206-112">Por servidor Standard Edition</span><span class="sxs-lookup"><span data-stu-id="80206-112">Per Standard Edition server</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="80206-113">Chamadas de entrada por segundo</span><span class="sxs-lookup"><span data-stu-id="80206-113">Incoming calls per second</span></span></p></td>
<td><p><span data-ttu-id="80206-114">16 </span><span class="sxs-lookup"><span data-stu-id="80206-114">16</span></span></p></td>
<td><p><span data-ttu-id="80206-115">duas</span><span class="sxs-lookup"><span data-stu-id="80206-115">2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80206-116">Chamadas concorrentes conectadas ao IVR ou MoH</span><span class="sxs-lookup"><span data-stu-id="80206-116">Concurrent calls connected to IVR or MoH</span></span></p></td>
<td><p><span data-ttu-id="80206-117">480</span><span class="sxs-lookup"><span data-stu-id="80206-117">480</span></span></p></td>
<td><p><span data-ttu-id="80206-118">60</span><span class="sxs-lookup"><span data-stu-id="80206-118">60</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80206-119">Sessões anônimas concorrentes (sem IM)</span><span class="sxs-lookup"><span data-stu-id="80206-119">Concurrent anonymous sessions (without IM)</span></span></p></td>
<td><p><span data-ttu-id="80206-120">224</span><span class="sxs-lookup"><span data-stu-id="80206-120">224</span></span></p></td>
<td><p><span data-ttu-id="80206-121">28</span><span class="sxs-lookup"><span data-stu-id="80206-121">28</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80206-122">Sessões anônimas concorrentes (com IM)</span><span class="sxs-lookup"><span data-stu-id="80206-122">Concurrent anonymous sessions (with IM)</span></span></p></td>
<td><p><span data-ttu-id="80206-123">64</span><span class="sxs-lookup"><span data-stu-id="80206-123">64</span></span></p></td>
<td><p><span data-ttu-id="80206-124">8 </span><span class="sxs-lookup"><span data-stu-id="80206-124">8</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80206-125">Operadores ativos (formais e informais)</span><span class="sxs-lookup"><span data-stu-id="80206-125">Active agents (formal and informal)</span></span></p></td>
<td><p><span data-ttu-id="80206-126">1200</span><span class="sxs-lookup"><span data-stu-id="80206-126">1200</span></span></p></td>
<td><p><span data-ttu-id="80206-127">1200</span><span class="sxs-lookup"><span data-stu-id="80206-127">1200</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80206-128">Número de grupos de busca</span><span class="sxs-lookup"><span data-stu-id="80206-128">Number of hunt groups</span></span></p></td>
<td><p><span data-ttu-id="80206-129">400</span><span class="sxs-lookup"><span data-stu-id="80206-129">400</span></span></p></td>
<td><p><span data-ttu-id="80206-130">400</span><span class="sxs-lookup"><span data-stu-id="80206-130">400</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80206-131">Número de grupos IVR (usa reconhecimento de fala)</span><span class="sxs-lookup"><span data-stu-id="80206-131">Number of IVR groups (use speech recognition)</span></span></p></td>
<td><p><span data-ttu-id="80206-132">200</span><span class="sxs-lookup"><span data-stu-id="80206-132">200</span></span></p></td>
<td><p><span data-ttu-id="80206-133">200</span><span class="sxs-lookup"><span data-stu-id="80206-133">200</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

