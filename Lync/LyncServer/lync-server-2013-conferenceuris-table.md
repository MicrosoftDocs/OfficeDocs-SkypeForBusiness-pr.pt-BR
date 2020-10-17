---
title: 'Lync Server 2013: tabela ConferenceUris'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ConferenceUris table
ms:assetid: b1721d52-3c65-45ea-8997-06af8fef93fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412854(v=OCS.15)
ms:contentKeyID: 48185160
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e9142be1b2d46a7d7634394970d07dfa450a22e1
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529168"
---
# <a name="conferenceuris-table-in-lync-server-2013"></a><span data-ttu-id="69041-102">Tabela ConferenceUris no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="69041-102">ConferenceUris table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="69041-103">_**Última modificação do tópico:** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="69041-103">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="69041-p101">A tabela ConferenceUris é uma tabela de suporte que armazena uma lista de diversos URIs de conferência que participaram de sessões de conferência gravadas no banco de dados. Cada registro da tabela representa um pool.</span><span class="sxs-lookup"><span data-stu-id="69041-p101">The ConfereneUris table is a supporting table that stores a list of the various conference URIs that have participated in conference sessions recorded in the database. Each record in the table represents one conference URI.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="69041-106">Coluna</span><span class="sxs-lookup"><span data-stu-id="69041-106">Column</span></span></th>
<th><span data-ttu-id="69041-107">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="69041-107">Data Type</span></span></th>
<th><span data-ttu-id="69041-108">Chave/índice</span><span class="sxs-lookup"><span data-stu-id="69041-108">Key/Index</span></span></th>
<th><span data-ttu-id="69041-109">Detalhes</span><span class="sxs-lookup"><span data-stu-id="69041-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="69041-110"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="69041-110"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="69041-111">datetime</span><span class="sxs-lookup"><span data-stu-id="69041-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="69041-112">Primário</span><span class="sxs-lookup"><span data-stu-id="69041-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="69041-113">Carimbo de hora, Interno usado.</span><span class="sxs-lookup"><span data-stu-id="69041-113">Time stamp, Internal used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69041-114"><strong>ConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="69041-114"><strong>ConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="69041-115">int</span><span class="sxs-lookup"><span data-stu-id="69041-115">int</span></span></p></td>
<td><p><span data-ttu-id="69041-116">Primário</span><span class="sxs-lookup"><span data-stu-id="69041-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="69041-117">Número exclusivo que identifica o URI desta conferência.</span><span class="sxs-lookup"><span data-stu-id="69041-117">Unique number identifying this conference URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69041-118"><strong>Conferenceui</strong></span><span class="sxs-lookup"><span data-stu-id="69041-118"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="69041-119">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="69041-119">nvarchar(450)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="69041-120">URI da conferência.</span><span class="sxs-lookup"><span data-stu-id="69041-120">Conference URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69041-121"><strong>Soma de verificação</strong></span><span class="sxs-lookup"><span data-stu-id="69041-121"><strong>Checksum</strong></span></span></p></td>
<td><p><span data-ttu-id="69041-122">int</span><span class="sxs-lookup"><span data-stu-id="69041-122">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="69041-p102">Soma de verificação do ConferenceUri. Usado para aumentar a velocidade de pesquisas no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="69041-p102">Checksum of ConferenceUri. Used to increases the speed of database searches.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69041-125"><strong>UriTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="69041-125"><strong>UriTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="69041-126">int</span><span class="sxs-lookup"><span data-stu-id="69041-126">int</span></span></p></td>
<td><p><span data-ttu-id="69041-127">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="69041-127">Foreign</span></span></p></td>
<td><p><span data-ttu-id="69041-128">Tipo de URI, por exemplo, conf:chat para conferência IM ou conf:audio-video para conferência de áudio/vídeo.</span><span class="sxs-lookup"><span data-stu-id="69041-128">URI type, such as conf:chat for IM conference, or conf:audio-video for audio/video conference.</span></span> <span data-ttu-id="69041-129">Consulte a <a href="lync-server-2013-uritypes-table.md">tabela UriTypes na tabela do Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="69041-129">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> table for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

