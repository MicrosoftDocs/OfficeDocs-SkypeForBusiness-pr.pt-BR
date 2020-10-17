---
title: 'Lync Server 2013: tabela de conferência'
description: 'Lync Server 2013: tabela de conferência.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conference table
ms:assetid: 2a2c327c-4719-42dc-a3bb-6dbc0864d9af
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425762(v=OCS.15)
ms:contentKeyID: 48183700
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 565725b527399cb3be55c649dfd74d8bcb5f13a2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550657"
---
# <a name="conference-table-in-lync-server-2013"></a><span data-ttu-id="abb4c-103">Tabela de conferência no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="abb4c-103">Conference table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="abb4c-104">_**Última modificação do tópico:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="abb4c-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="abb4c-p101">A tabela de Conferência é uma tabela de suporte. Cada registro representa uma conferência ou sessão ponto a ponto.</span><span class="sxs-lookup"><span data-stu-id="abb4c-p101">The Conference table is a supporting table. Each record represents one conference or peer-to-peer session.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="abb4c-107"><strong>Coluna</strong></span><span class="sxs-lookup"><span data-stu-id="abb4c-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="abb4c-108"><strong>Tipo de dados</strong></span><span class="sxs-lookup"><span data-stu-id="abb4c-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="abb4c-109"><strong>Chave/índice</strong></span><span class="sxs-lookup"><span data-stu-id="abb4c-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="abb4c-110"><strong>Detalhes</strong></span><span class="sxs-lookup"><span data-stu-id="abb4c-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="abb4c-111"><strong>ConferenceKey</strong></span><span class="sxs-lookup"><span data-stu-id="abb4c-111"><strong>ConferenceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="abb4c-112">int</span><span class="sxs-lookup"><span data-stu-id="abb4c-112">int</span></span></p></td>
<td><p><span data-ttu-id="abb4c-113">Primário</span><span class="sxs-lookup"><span data-stu-id="abb4c-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="abb4c-114">Número exclusivo que identifica o registro desta conferência.</span><span class="sxs-lookup"><span data-stu-id="abb4c-114">Unique number identifying this conference record.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="abb4c-115"><strong>ConfURI</strong></span><span class="sxs-lookup"><span data-stu-id="abb4c-115"><strong>ConfURI</strong></span></span></p></td>
<td><p><span data-ttu-id="abb4c-116">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="abb4c-116">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="abb4c-117">diferente</span><span class="sxs-lookup"><span data-stu-id="abb4c-117">unique</span></span></p></td>
<td><p><span data-ttu-id="abb4c-118">URI da conferência, se isso for uma conferência, ou DialogID se for uma sessão ponto a ponto.</span><span class="sxs-lookup"><span data-stu-id="abb4c-118">Conference URI if this is a conference, or DialogID if this is a peer-to-peer session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="abb4c-119"><strong>Soma de verificação</strong></span><span class="sxs-lookup"><span data-stu-id="abb4c-119"><strong>Checksum</strong></span></span></p></td>
<td><p><span data-ttu-id="abb4c-120">int</span><span class="sxs-lookup"><span data-stu-id="abb4c-120">int</span></span></p></td>
<td><p><span data-ttu-id="abb4c-121">index</span><span class="sxs-lookup"><span data-stu-id="abb4c-121">index</span></span></p></td>
<td><p><span data-ttu-id="abb4c-p102">Soma de verificação do URI de conferência. Isso é usado internamente.</span><span class="sxs-lookup"><span data-stu-id="abb4c-p102">Checksum of the conference URI. This is used internally.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="abb4c-124"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="abb4c-124"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="abb4c-125">datetime</span><span class="sxs-lookup"><span data-stu-id="abb4c-125">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="abb4c-126">Apenas para uso interno.</span><span class="sxs-lookup"><span data-stu-id="abb4c-126">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

