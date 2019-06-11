---
title: 'Lync Server 2013: tabela userstatistics'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: UserStatistics table
ms:assetid: cfaf803b-1679-4169-92d3-533fad3e56ed
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721893(v=OCS.15)
ms:contentKeyID: 49733827
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f0f684850625f61ca72bbcc9c4bc53b56fcc6b38
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844510"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="userstatistics-table-in-lync-server-2013"></a><span data-ttu-id="c3858-102">Tabela userstatistics no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c3858-102">UserStatistics table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c3858-103">_**Tópico da última modificação:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="c3858-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="c3858-104">A tabela userstatistics é uma tabela de suporte.</span><span class="sxs-lookup"><span data-stu-id="c3858-104">The UserStatistics table is a supporting table.</span></span> <span data-ttu-id="c3858-105">Cada registro na tabela armazena informações sobre o uso de um usuário individual do sistema.</span><span class="sxs-lookup"><span data-stu-id="c3858-105">Each record in the table stores information about an individual user’s usage of the system.</span></span> <span data-ttu-id="c3858-106">Esta tabela foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c3858-106">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c3858-107">Coluna</span><span class="sxs-lookup"><span data-stu-id="c3858-107">Column</span></span></th>
<th><span data-ttu-id="c3858-108">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="c3858-108">Data Type</span></span></th>
<th><span data-ttu-id="c3858-109">Chave/índice</span><span class="sxs-lookup"><span data-stu-id="c3858-109">Key/Index</span></span></th>
<th><span data-ttu-id="c3858-110">Detalhes</span><span class="sxs-lookup"><span data-stu-id="c3858-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c3858-111"><strong>ID</strong></span><span class="sxs-lookup"><span data-stu-id="c3858-111"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="c3858-112">int</span><span class="sxs-lookup"><span data-stu-id="c3858-112">int</span></span></p></td>
<td><p><span data-ttu-id="c3858-113">Primária</span><span class="sxs-lookup"><span data-stu-id="c3858-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="c3858-114">Número exclusivo que identifica esse usuário.</span><span class="sxs-lookup"><span data-stu-id="c3858-114">Unique number identifying this user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3858-115"><strong>LastLogInTime</strong></span><span class="sxs-lookup"><span data-stu-id="c3858-115"><strong>LastLogInTime</strong></span></span></p></td>
<td><p><span data-ttu-id="c3858-116">datetime</span><span class="sxs-lookup"><span data-stu-id="c3858-116">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c3858-117">Última vez em que o usuário se conectou.</span><span class="sxs-lookup"><span data-stu-id="c3858-117">Last time the user logged in.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c3858-118"><strong>LastConfOrganizedTime</strong></span><span class="sxs-lookup"><span data-stu-id="c3858-118"><strong>LastConfOrganizedTime</strong></span></span></p></td>
<td><p><span data-ttu-id="c3858-119">datetime</span><span class="sxs-lookup"><span data-stu-id="c3858-119">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c3858-120">Última vez em que o usuário organizou uma conferência.</span><span class="sxs-lookup"><span data-stu-id="c3858-120">Last time the user organized a conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3858-121"><strong>LastCallOrganizerCallFailureTime</strong></span><span class="sxs-lookup"><span data-stu-id="c3858-121"><strong>LastCallOrganizerCallFailureTime</strong></span></span></p></td>
<td><p><span data-ttu-id="c3858-122">datetime</span><span class="sxs-lookup"><span data-stu-id="c3858-122">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c3858-123">Última vez que o usuário experimentou uma falha na chamada.</span><span class="sxs-lookup"><span data-stu-id="c3858-123">Last time the user experienced a call failure.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c3858-124"><strong>LastConfOrganizerCallFailureTime</strong></span><span class="sxs-lookup"><span data-stu-id="c3858-124"><strong>LastConfOrganizerCallFailureTime</strong></span></span></p></td>
<td><p><span data-ttu-id="c3858-125">datetime</span><span class="sxs-lookup"><span data-stu-id="c3858-125">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c3858-126">Última vez que o usuário experimentou uma falha na chamada como um organizador de conferências.</span><span class="sxs-lookup"><span data-stu-id="c3858-126">Last time the user experienced a call failure as a conference organizer.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

