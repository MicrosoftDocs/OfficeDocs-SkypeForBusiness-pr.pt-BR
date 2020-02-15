---
title: 'Lync Server 2013: tabela CodecDescription'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: CodecDescription table
ms:assetid: 3598acb8-7ea6-4748-8417-149c971c32a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204797(v=OCS.15)
ms:contentKeyID: 48183802
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4be7b878d3d9b6457fbda7a081db9b6b6cb80314
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045833"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="codecdescription-table-in-lync-server-2013"></a><span data-ttu-id="864e9-102">Tabela CodecDescription no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="864e9-102">CodecDescription table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="864e9-103">_**Última modificação do tópico:** 2012-10-17_</span><span class="sxs-lookup"><span data-stu-id="864e9-103">_**Topic Last Modified:** 2012-10-17_</span></span>

<span data-ttu-id="864e9-104">A tabela CodecDescription associa identificadores exclusivos de codec a seus codecs correspondentes.</span><span class="sxs-lookup"><span data-stu-id="864e9-104">The CodecDescription table maps unique codec identifiers to their corresponding codec.</span></span> <span data-ttu-id="864e9-105">Os codecs são usados para codificar sinais digitais para transmissão e divulgação e, depois, para decodificar esses sinais para reprodução.</span><span class="sxs-lookup"><span data-stu-id="864e9-105">Codecs are used to encode digital signals for transmission and broadcast, and then to decode those signals for playback.</span></span> <span data-ttu-id="864e9-106">Esta tabela foi introduzida no Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="864e9-106">This table was introduced in Microsoft Lync Server 2013</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="864e9-107"><strong>Coluna</strong></span><span class="sxs-lookup"><span data-stu-id="864e9-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="864e9-108"><strong>Tipo de dados</strong></span><span class="sxs-lookup"><span data-stu-id="864e9-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="864e9-109"><strong>Chave/índice</strong></span><span class="sxs-lookup"><span data-stu-id="864e9-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="864e9-110"><strong>Detalhes</strong></span><span class="sxs-lookup"><span data-stu-id="864e9-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="864e9-111"><strong>CodecDescriptionKey</strong></span><span class="sxs-lookup"><span data-stu-id="864e9-111"><strong>CodecDescriptionKey</strong></span></span></p></td>
<td><p><span data-ttu-id="864e9-112">smallint</span><span class="sxs-lookup"><span data-stu-id="864e9-112">smallint</span></span></p></td>
<td><p><span data-ttu-id="864e9-113">Primário</span><span class="sxs-lookup"><span data-stu-id="864e9-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="864e9-114">Identificador exclusivo atribuído ao codec.</span><span class="sxs-lookup"><span data-stu-id="864e9-114">Unique identifier assigned to the codec.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="864e9-115"><strong>CodecDescription</strong></span><span class="sxs-lookup"><span data-stu-id="864e9-115"><strong>CodecDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="864e9-116">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="864e9-116">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="864e9-117">Diferente</span><span class="sxs-lookup"><span data-stu-id="864e9-117">Unique</span></span></p></td>
<td><p><span data-ttu-id="864e9-118">Descrição exclusiva do codec correspondendo à chave de descrição do codec.</span><span class="sxs-lookup"><span data-stu-id="864e9-118">Unique description of the codec corresponding to the CodecDescriptionKey.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

