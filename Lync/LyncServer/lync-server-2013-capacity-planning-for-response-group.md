---
title: 'Lync Server 2013: planejamento de capacidade para grupo de resposta'
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
ms.openlocfilehash: 9c9d43f6424a8d960ad5d0eee911b2f48455a39d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42191204"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="capacity-planning-for-response-group-in-lync-server-2013"></a><span data-ttu-id="74bf2-102">Planejamento de capacidade para grupo de resposta no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="74bf2-102">Capacity planning for Response Group in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="74bf2-103">_**Última modificação do tópico:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="74bf2-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<div id="sectionSection0" class="section">

<span data-ttu-id="74bf2-104">A tabela a seguir descreve o modelo de usuário do grupo de resposta que você pode usar como base para os requisitos de planejamento de capacidade.</span><span class="sxs-lookup"><span data-stu-id="74bf2-104">The following table describes the Response Group user model that you can use as the basis for capacity planning requirements.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="74bf2-p101">Os números na tabela a seguir assumem que arquivos de 16 kHz, mono, Wave (.wav) de 16 bits sejam usados para todos os arquivos de áudio do grupo de resposta. Se você usa outros formatos de arquivo, como Windows Media Audio (.wma), os números podem variar.</span><span class="sxs-lookup"><span data-stu-id="74bf2-p101">The numbers in the following table assume that you use 16 kHz, mono, 16-bit Wave (.wav) files for all response group audio files. If you use other file formats, such as Windows Media Audio (.wma), the numbers may vary.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="74bf2-107">Tenha em mente que para planejar a capacidade de recuperação de desastres, cada pool de um pool pareado deve poder lidar com cargas de trabalho de todos os grupos de resposta, em ambos os pools.</span><span class="sxs-lookup"><span data-stu-id="74bf2-107">Keep in mind that for disaster recovery capacity planning, each pool of a paired pool should be able to handle the workloads for all the response groups in both pools.</span></span>



</div>

### <a name="response-group-user-model"></a><span data-ttu-id="74bf2-108">Modelo de Usuário do Grupo de Resposta</span><span class="sxs-lookup"><span data-stu-id="74bf2-108">Response Group User Model</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="74bf2-109">Indicador</span><span class="sxs-lookup"><span data-stu-id="74bf2-109">Metric</span></span></th>
<th><span data-ttu-id="74bf2-110">Por pool Enterprise Edition (com 8 servidores front-end)</span><span class="sxs-lookup"><span data-stu-id="74bf2-110">Per Enterprise Edition pool (With 8 Front End Servers)</span></span></th>
<th><span data-ttu-id="74bf2-111">Por servidor Standard Edition</span><span class="sxs-lookup"><span data-stu-id="74bf2-111">Per Standard Edition server</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="74bf2-112">Chamadas de entrada por segundo</span><span class="sxs-lookup"><span data-stu-id="74bf2-112">Incoming calls per second</span></span></p></td>
<td><p><span data-ttu-id="74bf2-113">16 </span><span class="sxs-lookup"><span data-stu-id="74bf2-113">16</span></span></p></td>
<td><p><span data-ttu-id="74bf2-114">duas</span><span class="sxs-lookup"><span data-stu-id="74bf2-114">2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74bf2-115">Chamadas concorrentes conectadas ao IVR ou MoH</span><span class="sxs-lookup"><span data-stu-id="74bf2-115">Concurrent calls connected to IVR or MoH</span></span></p></td>
<td><p><span data-ttu-id="74bf2-116">480</span><span class="sxs-lookup"><span data-stu-id="74bf2-116">480</span></span></p></td>
<td><p><span data-ttu-id="74bf2-117">60</span><span class="sxs-lookup"><span data-stu-id="74bf2-117">60</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74bf2-118">Sessões anônimas concorrentes (sem IM)</span><span class="sxs-lookup"><span data-stu-id="74bf2-118">Concurrent anonymous sessions (without IM)</span></span></p></td>
<td><p><span data-ttu-id="74bf2-119">224</span><span class="sxs-lookup"><span data-stu-id="74bf2-119">224</span></span></p></td>
<td><p><span data-ttu-id="74bf2-120">28</span><span class="sxs-lookup"><span data-stu-id="74bf2-120">28</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74bf2-121">Sessões anônimas concorrentes (com IM)</span><span class="sxs-lookup"><span data-stu-id="74bf2-121">Concurrent anonymous sessions (with IM)</span></span></p></td>
<td><p><span data-ttu-id="74bf2-122">64</span><span class="sxs-lookup"><span data-stu-id="74bf2-122">64</span></span></p></td>
<td><p><span data-ttu-id="74bf2-123">8 </span><span class="sxs-lookup"><span data-stu-id="74bf2-123">8</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74bf2-124">Operadores ativos (formais e informais)</span><span class="sxs-lookup"><span data-stu-id="74bf2-124">Active agents (formal and informal)</span></span></p></td>
<td><p><span data-ttu-id="74bf2-125">1200</span><span class="sxs-lookup"><span data-stu-id="74bf2-125">1200</span></span></p></td>
<td><p><span data-ttu-id="74bf2-126">1200</span><span class="sxs-lookup"><span data-stu-id="74bf2-126">1200</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74bf2-127">Número de grupos de busca</span><span class="sxs-lookup"><span data-stu-id="74bf2-127">Number of hunt groups</span></span></p></td>
<td><p><span data-ttu-id="74bf2-128">400</span><span class="sxs-lookup"><span data-stu-id="74bf2-128">400</span></span></p></td>
<td><p><span data-ttu-id="74bf2-129">400</span><span class="sxs-lookup"><span data-stu-id="74bf2-129">400</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74bf2-130">Número de grupos IVR (usa reconhecimento de fala)</span><span class="sxs-lookup"><span data-stu-id="74bf2-130">Number of IVR groups (use speech recognition)</span></span></p></td>
<td><p><span data-ttu-id="74bf2-131">200</span><span class="sxs-lookup"><span data-stu-id="74bf2-131">200</span></span></p></td>
<td><p><span data-ttu-id="74bf2-132">200</span><span class="sxs-lookup"><span data-stu-id="74bf2-132">200</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

