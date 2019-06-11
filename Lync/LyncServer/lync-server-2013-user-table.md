---
title: 'Lync Server 2013: Tabela User'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: User table
ms:assetid: 6b52047e-286d-47ab-b7bc-a9b266f62d82
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398505(v=OCS.15)
ms:contentKeyID: 48184437
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4baaf8b8dea0f9e5aa77986791c82051fc00e90b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844527"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-table-in-lync-server-2013"></a><span data-ttu-id="8e22d-102">Tabela User no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8e22d-102">User table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8e22d-103">_**Tópico da última modificação:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="8e22d-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="8e22d-104">A tabela do usuário é uma tabela de suporte que armazena uma lista de vários usuários que participaram de sessões registradas no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="8e22d-104">The User table is a supporting table that stores a list of the various users who have participated in sessions recorded in the database.</span></span> <span data-ttu-id="8e22d-105">Cada registro na tabela representa um usuário.</span><span class="sxs-lookup"><span data-stu-id="8e22d-105">Each record in the table represents one user.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8e22d-106"><strong>Coluna</strong></span><span class="sxs-lookup"><span data-stu-id="8e22d-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="8e22d-107"><strong>Tipo de dados</strong></span><span class="sxs-lookup"><span data-stu-id="8e22d-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="8e22d-108"><strong>Chave/índice</strong></span><span class="sxs-lookup"><span data-stu-id="8e22d-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="8e22d-109"><strong>Detalhes</strong></span><span class="sxs-lookup"><span data-stu-id="8e22d-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8e22d-110"><strong>UserKey</strong></span><span class="sxs-lookup"><span data-stu-id="8e22d-110"><strong>UserKey</strong></span></span></p></td>
<td><p><span data-ttu-id="8e22d-111">int</span><span class="sxs-lookup"><span data-stu-id="8e22d-111">int</span></span></p></td>
<td><p><span data-ttu-id="8e22d-112">Primária</span><span class="sxs-lookup"><span data-stu-id="8e22d-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="8e22d-113">Número exclusivo que identifica esse usuário.</span><span class="sxs-lookup"><span data-stu-id="8e22d-113">Unique number identifying this user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e22d-114"><strong>SOLICITAÇÃO</strong></span><span class="sxs-lookup"><span data-stu-id="8e22d-114"><strong>URI</strong></span></span></p></td>
<td><p><span data-ttu-id="8e22d-115">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="8e22d-115">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="8e22d-116">Exclusividade</span><span class="sxs-lookup"><span data-stu-id="8e22d-116">Unique</span></span></p></td>
<td><p><span data-ttu-id="8e22d-117">Cadeia de caracteres de URI.</span><span class="sxs-lookup"><span data-stu-id="8e22d-117">URI string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8e22d-118"><strong>URIType</strong></span><span class="sxs-lookup"><span data-stu-id="8e22d-118"><strong>URIType</strong></span></span></p></td>
<td><p><span data-ttu-id="8e22d-119">int</span><span class="sxs-lookup"><span data-stu-id="8e22d-119">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8e22d-120">1 é um tipo de URI desconhecido.</span><span class="sxs-lookup"><span data-stu-id="8e22d-120">1 is unknown URI type.</span></span></p>
<p><span data-ttu-id="8e22d-121">2 é o URI do usuário.</span><span class="sxs-lookup"><span data-stu-id="8e22d-121">2 is user URI.</span></span></p>
<p><span data-ttu-id="8e22d-122">4 é o URI da conferência.</span><span class="sxs-lookup"><span data-stu-id="8e22d-122">4 is conference URI.</span></span></p>
<p><span data-ttu-id="8e22d-123">8 é o URI do telefone.</span><span class="sxs-lookup"><span data-stu-id="8e22d-123">8 is phone URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e22d-124"><strong>TenantKey</strong></span><span class="sxs-lookup"><span data-stu-id="8e22d-124"><strong>TenantKey</strong></span></span></p></td>
<td><p><span data-ttu-id="8e22d-125">int</span><span class="sxs-lookup"><span data-stu-id="8e22d-125">int</span></span></p></td>
<td><p><span data-ttu-id="8e22d-126">Exterior</span><span class="sxs-lookup"><span data-stu-id="8e22d-126">Foreign</span></span></p></td>
<td><p><span data-ttu-id="8e22d-127">Locatário do usuário, referenciado da tabela de locatários.</span><span class="sxs-lookup"><span data-stu-id="8e22d-127">Tenant of the user, referenced from tenant table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8e22d-128"><strong>LastPoorCallTime</strong></span><span class="sxs-lookup"><span data-stu-id="8e22d-128"><strong>LastPoorCallTime</strong></span></span></p></td>
<td><p><span data-ttu-id="8e22d-129">datetime</span><span class="sxs-lookup"><span data-stu-id="8e22d-129">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8e22d-130">Carimbo de data/hora mais recente quando o usuário tiver uma chamada de áudio ruim.</span><span class="sxs-lookup"><span data-stu-id="8e22d-130">Latest time stamp when the user had a poor audio call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e22d-131"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="8e22d-131"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="8e22d-132">datetime</span><span class="sxs-lookup"><span data-stu-id="8e22d-132">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8e22d-133">Somente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="8e22d-133">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

