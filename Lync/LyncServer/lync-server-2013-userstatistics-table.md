---
title: 'Lync Server 2013: tabela userstatistics'
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
ms.openlocfilehash: 2758b52b44a58095203deb7e70387934f723ee97
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140684"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="userstatistics-table-in-lync-server-2013"></a><span data-ttu-id="87c42-102">Tabela userstatistics no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="87c42-102">UserStatistics table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="87c42-103">_**Última modificação do tópico:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="87c42-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="87c42-104">A tabela UserStatistics é uma tabela de suporte.</span><span class="sxs-lookup"><span data-stu-id="87c42-104">The UserStatistics table is a supporting table.</span></span> <span data-ttu-id="87c42-105">Cada registro na tabela armazena informações sobre o uso individual do usuário no sistema.</span><span class="sxs-lookup"><span data-stu-id="87c42-105">Each record in the table stores information about an individual user’s usage of the system.</span></span> <span data-ttu-id="87c42-106">Esta tabela foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="87c42-106">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="87c42-107">Coluna</span><span class="sxs-lookup"><span data-stu-id="87c42-107">Column</span></span></th>
<th><span data-ttu-id="87c42-108">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="87c42-108">Data Type</span></span></th>
<th><span data-ttu-id="87c42-109">Chave/índice</span><span class="sxs-lookup"><span data-stu-id="87c42-109">Key/Index</span></span></th>
<th><span data-ttu-id="87c42-110">Detalhes</span><span class="sxs-lookup"><span data-stu-id="87c42-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="87c42-111"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="87c42-111"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="87c42-112">int</span><span class="sxs-lookup"><span data-stu-id="87c42-112">int</span></span></p></td>
<td><p><span data-ttu-id="87c42-113">Primário</span><span class="sxs-lookup"><span data-stu-id="87c42-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="87c42-114">Número único que identifica este usuário.</span><span class="sxs-lookup"><span data-stu-id="87c42-114">Unique number identifying this user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="87c42-115"><strong>LastLogInTime</strong></span><span class="sxs-lookup"><span data-stu-id="87c42-115"><strong>LastLogInTime</strong></span></span></p></td>
<td><p><span data-ttu-id="87c42-116">datetime</span><span class="sxs-lookup"><span data-stu-id="87c42-116">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="87c42-117">Última vez que o usuário fez o login.</span><span class="sxs-lookup"><span data-stu-id="87c42-117">Last time the user logged in.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="87c42-118"><strong>LastConfOrganizedTime</strong></span><span class="sxs-lookup"><span data-stu-id="87c42-118"><strong>LastConfOrganizedTime</strong></span></span></p></td>
<td><p><span data-ttu-id="87c42-119">datetime</span><span class="sxs-lookup"><span data-stu-id="87c42-119">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="87c42-120">Última vez que o usuário organizou uma conferência.</span><span class="sxs-lookup"><span data-stu-id="87c42-120">Last time the user organized a conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="87c42-121"><strong>LastCallOrganizerCallFailureTime</strong></span><span class="sxs-lookup"><span data-stu-id="87c42-121"><strong>LastCallOrganizerCallFailureTime</strong></span></span></p></td>
<td><p><span data-ttu-id="87c42-122">datetime</span><span class="sxs-lookup"><span data-stu-id="87c42-122">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="87c42-123">Última vez que o usuário enfrentou uma falha de ligação.</span><span class="sxs-lookup"><span data-stu-id="87c42-123">Last time the user experienced a call failure.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="87c42-124"><strong>LastConfOrganizerCallFailureTime</strong></span><span class="sxs-lookup"><span data-stu-id="87c42-124"><strong>LastConfOrganizerCallFailureTime</strong></span></span></p></td>
<td><p><span data-ttu-id="87c42-125">datetime</span><span class="sxs-lookup"><span data-stu-id="87c42-125">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="87c42-126">Última vez que o usuário enfrentou uma falha de ligação como um organização da conferência.</span><span class="sxs-lookup"><span data-stu-id="87c42-126">Last time the user experienced a call failure as a conference organizer.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

