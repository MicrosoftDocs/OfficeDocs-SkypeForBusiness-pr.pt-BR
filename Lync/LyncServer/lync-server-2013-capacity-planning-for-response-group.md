---
title: 'Lync Server 2013: Planejamento de capacidade para Grupo de Resposta'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Capacity planning for Response Group
ms:assetid: a2459a69-1f45-4f2f-bca5-d4f442708e44
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412754(v=OCS.15)
ms:contentKeyID: 48184951
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 72f3e49806dc573a4e17bc917834deba97a74ca2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836671"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="capacity-planning-for-response-group-in-lync-server-2013"></a><span data-ttu-id="a0f85-102">Planejamento de capacidade para Grupo de Resposta no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a0f85-102">Capacity planning for Response Group in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a0f85-103">_**Tópico da última modificação:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="a0f85-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<div id="sectionSection0" class="section">

<span data-ttu-id="a0f85-104">A tabela a seguir descreve o modelo de usuário do grupo de resposta que você pode usar como base para requisitos de planejamento de capacidade.</span><span class="sxs-lookup"><span data-stu-id="a0f85-104">The following table describes the Response Group user model that you can use as the basis for capacity planning requirements.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a0f85-105">Os números na tabela a seguir pressupõem que você use arquivos Wave de 16 bits (. wav) de 16 bits para todos os arquivos de áudio do grupo de resposta.</span><span class="sxs-lookup"><span data-stu-id="a0f85-105">The numbers in the following table assume that you use 16 kHz, mono, 16-bit Wave (.wav) files for all response group audio files.</span></span> <span data-ttu-id="a0f85-106">Se você usar outros formatos de arquivo, como o áudio do Windows Media (. WMA), os números podem variar.</span><span class="sxs-lookup"><span data-stu-id="a0f85-106">If you use other file formats, such as Windows Media Audio (.wma), the numbers may vary.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="a0f85-107">Lembre-se de que, para o planejamento da capacidade de recuperação de desastres, cada pool de um pool emparelhado deve ser capaz de manipular as cargas de trabalho para todos os grupos de resposta em ambos os pools.</span><span class="sxs-lookup"><span data-stu-id="a0f85-107">Keep in mind that for disaster recovery capacity planning, each pool of a paired pool should be able to handle the workloads for all the response groups in both pools.</span></span>



</div>

### <a name="response-group-user-model"></a><span data-ttu-id="a0f85-108">Modelo de usuário do grupo de resposta</span><span class="sxs-lookup"><span data-stu-id="a0f85-108">Response Group User Model</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a0f85-109">Indicador</span><span class="sxs-lookup"><span data-stu-id="a0f85-109">Metric</span></span></th>
<th><span data-ttu-id="a0f85-110">Por pool de edição para empresas (com 8 servidores front end)</span><span class="sxs-lookup"><span data-stu-id="a0f85-110">Per Enterprise Edition pool (With 8 Front End Servers)</span></span></th>
<th><span data-ttu-id="a0f85-111">Por servidor padrão da edição</span><span class="sxs-lookup"><span data-stu-id="a0f85-111">Per Standard Edition server</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a0f85-112">Chamadas recebidas por segundo</span><span class="sxs-lookup"><span data-stu-id="a0f85-112">Incoming calls per second</span></span></p></td>
<td><p><span data-ttu-id="a0f85-113">16</span><span class="sxs-lookup"><span data-stu-id="a0f85-113">16</span></span></p></td>
<td><p><span data-ttu-id="a0f85-114">2</span><span class="sxs-lookup"><span data-stu-id="a0f85-114">2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0f85-115">Chamadas simultâneas conectadas ao IVR ou MoH</span><span class="sxs-lookup"><span data-stu-id="a0f85-115">Concurrent calls connected to IVR or MoH</span></span></p></td>
<td><p><span data-ttu-id="a0f85-116">480</span><span class="sxs-lookup"><span data-stu-id="a0f85-116">480</span></span></p></td>
<td><p><span data-ttu-id="a0f85-117">60</span><span class="sxs-lookup"><span data-stu-id="a0f85-117">60</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a0f85-118">Sessões anônimas simultâneas (sem mensagens instantâneas)</span><span class="sxs-lookup"><span data-stu-id="a0f85-118">Concurrent anonymous sessions (without IM)</span></span></p></td>
<td><p><span data-ttu-id="a0f85-119">224</span><span class="sxs-lookup"><span data-stu-id="a0f85-119">224</span></span></p></td>
<td><p><span data-ttu-id="a0f85-120">28</span><span class="sxs-lookup"><span data-stu-id="a0f85-120">28</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0f85-121">Sessões anônimas simultâneas (com mensagens instantâneas)</span><span class="sxs-lookup"><span data-stu-id="a0f85-121">Concurrent anonymous sessions (with IM)</span></span></p></td>
<td><p><span data-ttu-id="a0f85-122">64</span><span class="sxs-lookup"><span data-stu-id="a0f85-122">64</span></span></p></td>
<td><p><span data-ttu-id="a0f85-123">08</span><span class="sxs-lookup"><span data-stu-id="a0f85-123">8</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a0f85-124">Agentes ativos (formais e informais)</span><span class="sxs-lookup"><span data-stu-id="a0f85-124">Active agents (formal and informal)</span></span></p></td>
<td><p><span data-ttu-id="a0f85-125">1200</span><span class="sxs-lookup"><span data-stu-id="a0f85-125">1200</span></span></p></td>
<td><p><span data-ttu-id="a0f85-126">1200</span><span class="sxs-lookup"><span data-stu-id="a0f85-126">1200</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0f85-127">Número de grupos de busca</span><span class="sxs-lookup"><span data-stu-id="a0f85-127">Number of hunt groups</span></span></p></td>
<td><p><span data-ttu-id="a0f85-128">400</span><span class="sxs-lookup"><span data-stu-id="a0f85-128">400</span></span></p></td>
<td><p><span data-ttu-id="a0f85-129">400</span><span class="sxs-lookup"><span data-stu-id="a0f85-129">400</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a0f85-130">Número de grupos IVR (usar reconhecimento de fala)</span><span class="sxs-lookup"><span data-stu-id="a0f85-130">Number of IVR groups (use speech recognition)</span></span></p></td>
<td><p><span data-ttu-id="a0f85-131">200</span><span class="sxs-lookup"><span data-stu-id="a0f85-131">200</span></span></p></td>
<td><p><span data-ttu-id="a0f85-132">200</span><span class="sxs-lookup"><span data-stu-id="a0f85-132">200</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

