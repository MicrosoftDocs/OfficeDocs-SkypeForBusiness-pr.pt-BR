---
title: 'Lync Server 2013: tabela de telefones'
description: 'Lync Server 2013: tabela de telefones.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Phones table
ms:assetid: 41cb356d-9cc8-42b6-ac23-98a61b25aadc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425923(v=OCS.15)
ms:contentKeyID: 48183996
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9c62fffecd2442b79aefde77eb037dca4bffc9d4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554807"
---
# <a name="phones-table-in-lync-server-2013"></a><span data-ttu-id="6ce40-103">Tabela phones no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6ce40-103">Phones table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6ce40-104">_**Última modificação do tópico:** 2012-08-20_</span><span class="sxs-lookup"><span data-stu-id="6ce40-104">_**Topic Last Modified:** 2012-08-20_</span></span>

<span data-ttu-id="6ce40-105">A tabela telefones é uma tabela de suporte.</span><span class="sxs-lookup"><span data-stu-id="6ce40-105">The Phones table is a supporting table.</span></span> <span data-ttu-id="6ce40-106">Cada registro na tabela armazena informações sobre um número de telefone envolvido em chamadas VoIP que têm registros no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="6ce40-106">Each record in the table stores information about one phone number involved in VoIP calls that have records in the database.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6ce40-107">Coluna</span><span class="sxs-lookup"><span data-stu-id="6ce40-107">Column</span></span></th>
<th><span data-ttu-id="6ce40-108">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="6ce40-108">Data Type</span></span></th>
<th><span data-ttu-id="6ce40-109">Chave/índice</span><span class="sxs-lookup"><span data-stu-id="6ce40-109">Key/Index</span></span></th>
<th><span data-ttu-id="6ce40-110">Detalhes</span><span class="sxs-lookup"><span data-stu-id="6ce40-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6ce40-111"><strong>PHONEID</strong></span><span class="sxs-lookup"><span data-stu-id="6ce40-111"><strong>PhoneId</strong></span></span></p></td>
<td><p><span data-ttu-id="6ce40-112">int</span><span class="sxs-lookup"><span data-stu-id="6ce40-112">int</span></span></p></td>
<td><p><span data-ttu-id="6ce40-113">Primário</span><span class="sxs-lookup"><span data-stu-id="6ce40-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="6ce40-114">Número exclusivo que identifica esse telefone.</span><span class="sxs-lookup"><span data-stu-id="6ce40-114">Unique number identifying this phone.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ce40-115"><strong>PhoneUri</strong></span><span class="sxs-lookup"><span data-stu-id="6ce40-115"><strong>PhoneUri</strong></span></span></p></td>
<td><p><span data-ttu-id="6ce40-116">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="6ce40-116">nvarchar(450)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="6ce40-117">Número de telefone.</span><span class="sxs-lookup"><span data-stu-id="6ce40-117">Phone number.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6ce40-118"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="6ce40-118"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="6ce40-119">dateTime</span><span class="sxs-lookup"><span data-stu-id="6ce40-119">dateTime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6ce40-120">Carimbo de data/hora (somente para uso interno).</span><span class="sxs-lookup"><span data-stu-id="6ce40-120">Time stamp (for internal use only).</span></span></p>
<p><span data-ttu-id="6ce40-121">Este campo foi introduzido no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6ce40-121">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

