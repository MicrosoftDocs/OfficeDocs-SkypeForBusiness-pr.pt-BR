---
title: 'Lync Server 2013: Tabela User'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User table
ms:assetid: 6b52047e-286d-47ab-b7bc-a9b266f62d82
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398505(v=OCS.15)
ms:contentKeyID: 48184437
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8256dec91c93ca6e8f0fd3cfff65280a417324e4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744441"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-table-in-lync-server-2013"></a><span data-ttu-id="ae311-102">Tabela User no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ae311-102">User table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ae311-103">_**Tópico da última modificação:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="ae311-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="ae311-104">A tabela do usuário é uma tabela de suporte que armazena uma lista de vários usuários que participaram de sessões registradas no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="ae311-104">The User table is a supporting table that stores a list of the various users who have participated in sessions recorded in the database.</span></span> <span data-ttu-id="ae311-105">Cada registro na tabela representa um usuário.</span><span class="sxs-lookup"><span data-stu-id="ae311-105">Each record in the table represents one user.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ae311-106"><strong>Coluna</strong></span><span class="sxs-lookup"><span data-stu-id="ae311-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="ae311-107"><strong>Tipo de dados</strong></span><span class="sxs-lookup"><span data-stu-id="ae311-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="ae311-108"><strong>Chave/índice</strong></span><span class="sxs-lookup"><span data-stu-id="ae311-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="ae311-109"><strong>Detalhes</strong></span><span class="sxs-lookup"><span data-stu-id="ae311-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ae311-110"><strong>UserKey</strong></span><span class="sxs-lookup"><span data-stu-id="ae311-110"><strong>UserKey</strong></span></span></p></td>
<td><p><span data-ttu-id="ae311-111">int</span><span class="sxs-lookup"><span data-stu-id="ae311-111">int</span></span></p></td>
<td><p><span data-ttu-id="ae311-112">Primária</span><span class="sxs-lookup"><span data-stu-id="ae311-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="ae311-113">Número exclusivo que identifica esse usuário.</span><span class="sxs-lookup"><span data-stu-id="ae311-113">Unique number identifying this user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ae311-114"><strong>SOLICITAÇÃO</strong></span><span class="sxs-lookup"><span data-stu-id="ae311-114"><strong>URI</strong></span></span></p></td>
<td><p><span data-ttu-id="ae311-115">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="ae311-115">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="ae311-116">Exclusividade</span><span class="sxs-lookup"><span data-stu-id="ae311-116">Unique</span></span></p></td>
<td><p><span data-ttu-id="ae311-117">Cadeia de caracteres de URI.</span><span class="sxs-lookup"><span data-stu-id="ae311-117">URI string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ae311-118"><strong>URIType</strong></span><span class="sxs-lookup"><span data-stu-id="ae311-118"><strong>URIType</strong></span></span></p></td>
<td><p><span data-ttu-id="ae311-119">int</span><span class="sxs-lookup"><span data-stu-id="ae311-119">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ae311-120">1 é um tipo de URI desconhecido.</span><span class="sxs-lookup"><span data-stu-id="ae311-120">1 is unknown URI type.</span></span></p>
<p><span data-ttu-id="ae311-121">2 é o URI do usuário.</span><span class="sxs-lookup"><span data-stu-id="ae311-121">2 is user URI.</span></span></p>
<p><span data-ttu-id="ae311-122">4 é o URI da conferência.</span><span class="sxs-lookup"><span data-stu-id="ae311-122">4 is conference URI.</span></span></p>
<p><span data-ttu-id="ae311-123">8 é o URI do telefone.</span><span class="sxs-lookup"><span data-stu-id="ae311-123">8 is phone URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ae311-124"><strong>TenantKey</strong></span><span class="sxs-lookup"><span data-stu-id="ae311-124"><strong>TenantKey</strong></span></span></p></td>
<td><p><span data-ttu-id="ae311-125">int</span><span class="sxs-lookup"><span data-stu-id="ae311-125">int</span></span></p></td>
<td><p><span data-ttu-id="ae311-126">Exterior</span><span class="sxs-lookup"><span data-stu-id="ae311-126">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ae311-127">Locatário do usuário, referenciado da tabela de locatários.</span><span class="sxs-lookup"><span data-stu-id="ae311-127">Tenant of the user, referenced from tenant table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ae311-128"><strong>LastPoorCallTime</strong></span><span class="sxs-lookup"><span data-stu-id="ae311-128"><strong>LastPoorCallTime</strong></span></span></p></td>
<td><p><span data-ttu-id="ae311-129">datetime</span><span class="sxs-lookup"><span data-stu-id="ae311-129">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ae311-130">Carimbo de data/hora mais recente quando o usuário tiver uma chamada de áudio ruim.</span><span class="sxs-lookup"><span data-stu-id="ae311-130">Latest time stamp when the user had a poor audio call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ae311-131"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="ae311-131"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="ae311-132">datetime</span><span class="sxs-lookup"><span data-stu-id="ae311-132">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ae311-133">Somente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="ae311-133">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

