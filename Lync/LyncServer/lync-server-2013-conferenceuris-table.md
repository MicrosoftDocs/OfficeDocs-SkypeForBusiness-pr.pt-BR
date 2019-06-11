---
title: 'Lync Server 2013: Tabela ConferenceUris'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: ConferenceUris table
ms:assetid: b1721d52-3c65-45ea-8997-06af8fef93fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412854(v=OCS.15)
ms:contentKeyID: 48185160
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e2b1ab44b564d649b6c8fb812077645c6dc13093
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836482"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferenceuris-table-in-lync-server-2013"></a><span data-ttu-id="1fd90-102">Tabela ConferenceUris no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1fd90-102">ConferenceUris table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1fd90-103">_**Tópico da última modificação:** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="1fd90-103">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="1fd90-104">A tabela ConfereneUris é uma tabela de suporte que armazena uma lista de vários URIs de conferência que participaram de sessões de conferência registradas no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="1fd90-104">The ConfereneUris table is a supporting table that stores a list of the various conference URIs that have participated in conference sessions recorded in the database.</span></span> <span data-ttu-id="1fd90-105">Cada registro na tabela representa um URI de conferência.</span><span class="sxs-lookup"><span data-stu-id="1fd90-105">Each record in the table represents one conference URI.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1fd90-106">Coluna</span><span class="sxs-lookup"><span data-stu-id="1fd90-106">Column</span></span></th>
<th><span data-ttu-id="1fd90-107">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="1fd90-107">Data Type</span></span></th>
<th><span data-ttu-id="1fd90-108">Chave/índice</span><span class="sxs-lookup"><span data-stu-id="1fd90-108">Key/Index</span></span></th>
<th><span data-ttu-id="1fd90-109">Detalhes</span><span class="sxs-lookup"><span data-stu-id="1fd90-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1fd90-110"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="1fd90-110"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="1fd90-111">datetime</span><span class="sxs-lookup"><span data-stu-id="1fd90-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="1fd90-112">Primária</span><span class="sxs-lookup"><span data-stu-id="1fd90-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="1fd90-113">Carimbo de data/hora, usado internamente.</span><span class="sxs-lookup"><span data-stu-id="1fd90-113">Time stamp, Internal used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1fd90-114"><strong>ConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="1fd90-114"><strong>ConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="1fd90-115">int</span><span class="sxs-lookup"><span data-stu-id="1fd90-115">int</span></span></p></td>
<td><p><span data-ttu-id="1fd90-116">Primária</span><span class="sxs-lookup"><span data-stu-id="1fd90-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="1fd90-117">Número exclusivo que identifica esse URI de conferência.</span><span class="sxs-lookup"><span data-stu-id="1fd90-117">Unique number identifying this conference URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1fd90-118"><strong>ConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="1fd90-118"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="1fd90-119">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="1fd90-119">nvarchar(450)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1fd90-120">URL da conferência.</span><span class="sxs-lookup"><span data-stu-id="1fd90-120">Conference URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1fd90-121"><strong>Prova</strong></span><span class="sxs-lookup"><span data-stu-id="1fd90-121"><strong>Checksum</strong></span></span></p></td>
<td><p><span data-ttu-id="1fd90-122">int</span><span class="sxs-lookup"><span data-stu-id="1fd90-122">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1fd90-123">Soma de verificação de ConferenceUri.</span><span class="sxs-lookup"><span data-stu-id="1fd90-123">Checksum of ConferenceUri.</span></span> <span data-ttu-id="1fd90-124">Usado para aumentar a velocidade das pesquisas do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="1fd90-124">Used to increases the speed of database searches.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1fd90-125"><strong>UriTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="1fd90-125"><strong>UriTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="1fd90-126">int</span><span class="sxs-lookup"><span data-stu-id="1fd90-126">int</span></span></p></td>
<td><p><span data-ttu-id="1fd90-127">Exterior</span><span class="sxs-lookup"><span data-stu-id="1fd90-127">Foreign</span></span></p></td>
<td><p><span data-ttu-id="1fd90-128">Tipo de URI, como conf: chat para conferência de IM ou conf: áudio-vídeo para videoconferência/videoconferência.</span><span class="sxs-lookup"><span data-stu-id="1fd90-128">URI type, such as conf:chat for IM conference, or conf:audio-video for audio/video conference.</span></span> <span data-ttu-id="1fd90-129">Consulte a <a href="lync-server-2013-uritypes-table.md">tabela UriTypes na tabela do Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="1fd90-129">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> table for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

