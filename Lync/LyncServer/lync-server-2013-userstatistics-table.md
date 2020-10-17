---
title: 'Lync Server 2013: tabela userstatistics'
description: 'Lync Server 2013: tabela userstatistics.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: UserStatistics table
ms:assetid: cfaf803b-1679-4169-92d3-533fad3e56ed
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721893(v=OCS.15)
ms:contentKeyID: 49733827
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 75b34fa3c34af4cc9cf2cacc6ae7feb4d217114c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548527"
---
# <a name="userstatistics-table-in-lync-server-2013"></a><span data-ttu-id="ab127-103">Tabela userstatistics no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ab127-103">UserStatistics table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ab127-104">_**Última modificação do tópico:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="ab127-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="ab127-105">A tabela UserStatistics é uma tabela de suporte.</span><span class="sxs-lookup"><span data-stu-id="ab127-105">The UserStatistics table is a supporting table.</span></span> <span data-ttu-id="ab127-106">Cada registro na tabela armazena informações sobre o uso individual do usuário no sistema.</span><span class="sxs-lookup"><span data-stu-id="ab127-106">Each record in the table stores information about an individual user’s usage of the system.</span></span> <span data-ttu-id="ab127-107">Esta tabela foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ab127-107">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ab127-108">Coluna</span><span class="sxs-lookup"><span data-stu-id="ab127-108">Column</span></span></th>
<th><span data-ttu-id="ab127-109">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="ab127-109">Data Type</span></span></th>
<th><span data-ttu-id="ab127-110">Chave/índice</span><span class="sxs-lookup"><span data-stu-id="ab127-110">Key/Index</span></span></th>
<th><span data-ttu-id="ab127-111">Detalhes</span><span class="sxs-lookup"><span data-stu-id="ab127-111">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ab127-112"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="ab127-112"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="ab127-113">int</span><span class="sxs-lookup"><span data-stu-id="ab127-113">int</span></span></p></td>
<td><p><span data-ttu-id="ab127-114">Primário</span><span class="sxs-lookup"><span data-stu-id="ab127-114">Primary</span></span></p></td>
<td><p><span data-ttu-id="ab127-115">Número único que identifica este usuário.</span><span class="sxs-lookup"><span data-stu-id="ab127-115">Unique number identifying this user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab127-116"><strong>LastLogInTime</strong></span><span class="sxs-lookup"><span data-stu-id="ab127-116"><strong>LastLogInTime</strong></span></span></p></td>
<td><p><span data-ttu-id="ab127-117">datetime</span><span class="sxs-lookup"><span data-stu-id="ab127-117">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab127-118">Última vez que o usuário fez o login.</span><span class="sxs-lookup"><span data-stu-id="ab127-118">Last time the user logged in.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab127-119"><strong>LastConfOrganizedTime</strong></span><span class="sxs-lookup"><span data-stu-id="ab127-119"><strong>LastConfOrganizedTime</strong></span></span></p></td>
<td><p><span data-ttu-id="ab127-120">datetime</span><span class="sxs-lookup"><span data-stu-id="ab127-120">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab127-121">Última vez que o usuário organizou uma conferência.</span><span class="sxs-lookup"><span data-stu-id="ab127-121">Last time the user organized a conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab127-122"><strong>LastCallOrganizerCallFailureTime</strong></span><span class="sxs-lookup"><span data-stu-id="ab127-122"><strong>LastCallOrganizerCallFailureTime</strong></span></span></p></td>
<td><p><span data-ttu-id="ab127-123">datetime</span><span class="sxs-lookup"><span data-stu-id="ab127-123">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab127-124">Última vez que o usuário enfrentou uma falha de ligação.</span><span class="sxs-lookup"><span data-stu-id="ab127-124">Last time the user experienced a call failure.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab127-125"><strong>LastConfOrganizerCallFailureTime</strong></span><span class="sxs-lookup"><span data-stu-id="ab127-125"><strong>LastConfOrganizerCallFailureTime</strong></span></span></p></td>
<td><p><span data-ttu-id="ab127-126">datetime</span><span class="sxs-lookup"><span data-stu-id="ab127-126">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab127-127">Última vez que o usuário enfrentou uma falha de ligação como um organização da conferência.</span><span class="sxs-lookup"><span data-stu-id="ab127-127">Last time the user experienced a call failure as a conference organizer.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

