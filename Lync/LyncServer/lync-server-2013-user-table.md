---
title: 'Lync Server 2013: tabela de usuário'
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
ms.openlocfilehash: 98a34028ebec126c8d5fc5ec838a22180ccb0fa7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007640"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-table-in-lync-server-2013"></a><span data-ttu-id="82df5-102">Tabela de usuário no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="82df5-102">User table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="82df5-103">_**Última modificação do tópico:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="82df5-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="82df5-p101">A tabela de Usuário é uma tabela de suporte que armazena uma lista de vários usuários que participaram das sessões registradas no banco de dados. Cada registro da tabela representa um usuário.</span><span class="sxs-lookup"><span data-stu-id="82df5-p101">The User table is a supporting table that stores a list of the various users who have participated in sessions recorded in the database. Each record in the table represents one user.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="82df5-106"><strong>Coluna</strong></span><span class="sxs-lookup"><span data-stu-id="82df5-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="82df5-107"><strong>Tipo de dados</strong></span><span class="sxs-lookup"><span data-stu-id="82df5-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="82df5-108"><strong>Chave/índice</strong></span><span class="sxs-lookup"><span data-stu-id="82df5-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="82df5-109"><strong>Detalhes</strong></span><span class="sxs-lookup"><span data-stu-id="82df5-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="82df5-110"><strong>UserKey</strong></span><span class="sxs-lookup"><span data-stu-id="82df5-110"><strong>UserKey</strong></span></span></p></td>
<td><p><span data-ttu-id="82df5-111">int</span><span class="sxs-lookup"><span data-stu-id="82df5-111">int</span></span></p></td>
<td><p><span data-ttu-id="82df5-112">Primário</span><span class="sxs-lookup"><span data-stu-id="82df5-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="82df5-113">Número exclusivo identificando este usuário.</span><span class="sxs-lookup"><span data-stu-id="82df5-113">Unique number identifying this user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="82df5-114"><strong>URI</strong></span><span class="sxs-lookup"><span data-stu-id="82df5-114"><strong>URI</strong></span></span></p></td>
<td><p><span data-ttu-id="82df5-115">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="82df5-115">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="82df5-116">Diferente</span><span class="sxs-lookup"><span data-stu-id="82df5-116">Unique</span></span></p></td>
<td><p><span data-ttu-id="82df5-117">Cadeia de caracteres URI.</span><span class="sxs-lookup"><span data-stu-id="82df5-117">URI string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="82df5-118"><strong>URIType</strong></span><span class="sxs-lookup"><span data-stu-id="82df5-118"><strong>URIType</strong></span></span></p></td>
<td><p><span data-ttu-id="82df5-119">int</span><span class="sxs-lookup"><span data-stu-id="82df5-119">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="82df5-120">1 é o tipo de URI desconhecido.</span><span class="sxs-lookup"><span data-stu-id="82df5-120">1 is unknown URI type.</span></span></p>
<p><span data-ttu-id="82df5-121">2 é o URI do usuário.</span><span class="sxs-lookup"><span data-stu-id="82df5-121">2 is user URI.</span></span></p>
<p><span data-ttu-id="82df5-122">4 é o URI de conferência.</span><span class="sxs-lookup"><span data-stu-id="82df5-122">4 is conference URI.</span></span></p>
<p><span data-ttu-id="82df5-123">8 é o URI do telefone.</span><span class="sxs-lookup"><span data-stu-id="82df5-123">8 is phone URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="82df5-124"><strong>TenantKey</strong></span><span class="sxs-lookup"><span data-stu-id="82df5-124"><strong>TenantKey</strong></span></span></p></td>
<td><p><span data-ttu-id="82df5-125">int</span><span class="sxs-lookup"><span data-stu-id="82df5-125">int</span></span></p></td>
<td><p><span data-ttu-id="82df5-126">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="82df5-126">Foreign</span></span></p></td>
<td><p><span data-ttu-id="82df5-127">Locatário do usuário, referenciado da tabela do locatário.</span><span class="sxs-lookup"><span data-stu-id="82df5-127">Tenant of the user, referenced from tenant table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="82df5-128"><strong>LastPoorCallTime</strong></span><span class="sxs-lookup"><span data-stu-id="82df5-128"><strong>LastPoorCallTime</strong></span></span></p></td>
<td><p><span data-ttu-id="82df5-129">datetime</span><span class="sxs-lookup"><span data-stu-id="82df5-129">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="82df5-130">Carimbo de data e hora da última vez em que o usuário teve uma chamada de áudio ruim.</span><span class="sxs-lookup"><span data-stu-id="82df5-130">Latest time stamp when the user had a poor audio call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="82df5-131"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="82df5-131"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="82df5-132">datetime</span><span class="sxs-lookup"><span data-stu-id="82df5-132">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="82df5-133">Apenas para uso interno.</span><span class="sxs-lookup"><span data-stu-id="82df5-133">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

