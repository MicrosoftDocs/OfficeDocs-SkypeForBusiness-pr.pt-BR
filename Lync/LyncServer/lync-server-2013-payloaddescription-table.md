---
title: 'Lync Server 2013: Tabela PayloadDescription'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: PayloadDescription table
ms:assetid: c49d61c0-305a-4770-a5d2-5d9f05decc6d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412971(v=OCS.15)
ms:contentKeyID: 48185353
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2fe905db80edae74e81cc496c9ad70ca3148854f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755385"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="payloaddescription-table-in-lync-server-2013"></a><span data-ttu-id="ee4f8-102">Tabela PayloadDescription no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ee4f8-102">PayloadDescription table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ee4f8-103">_**Tópico da última modificação:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="ee4f8-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="ee4f8-104">A tabela PayloadDescription é uma tabela de suporte.</span><span class="sxs-lookup"><span data-stu-id="ee4f8-104">The PayloadDescription table is a supporting table.</span></span> <span data-ttu-id="ee4f8-105">Cada registro representa um codec, que é usado em uma sessão de áudio ou de vídeo.</span><span class="sxs-lookup"><span data-stu-id="ee4f8-105">Each record represents one Codec, which is used in an audio or video session.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ee4f8-106"><strong>Coluna</strong></span><span class="sxs-lookup"><span data-stu-id="ee4f8-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="ee4f8-107"><strong>Tipo de dados</strong></span><span class="sxs-lookup"><span data-stu-id="ee4f8-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="ee4f8-108"><strong>Chave/índice</strong></span><span class="sxs-lookup"><span data-stu-id="ee4f8-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="ee4f8-109"><strong>Detalhes</strong></span><span class="sxs-lookup"><span data-stu-id="ee4f8-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ee4f8-110"><strong>PayloadDescriptionKey</strong></span><span class="sxs-lookup"><span data-stu-id="ee4f8-110"><strong>PayloadDescriptionKey</strong></span></span></p></td>
<td><p><span data-ttu-id="ee4f8-111">int</span><span class="sxs-lookup"><span data-stu-id="ee4f8-111">int</span></span></p></td>
<td><p><span data-ttu-id="ee4f8-112">Primária</span><span class="sxs-lookup"><span data-stu-id="ee4f8-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="ee4f8-113">Número exclusivo que identifica o codec.</span><span class="sxs-lookup"><span data-stu-id="ee4f8-113">Unique number identifying the Codec.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee4f8-114"><strong>PayloadDescription</strong></span><span class="sxs-lookup"><span data-stu-id="ee4f8-114"><strong>PayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="ee4f8-115">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="ee4f8-115">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ee4f8-116">Exclusividade</span><span class="sxs-lookup"><span data-stu-id="ee4f8-116">Unique</span></span></p></td>
<td><p><span data-ttu-id="ee4f8-117">Nome do codec.</span><span class="sxs-lookup"><span data-stu-id="ee4f8-117">Codec name.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

