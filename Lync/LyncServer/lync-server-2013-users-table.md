---
title: 'Lync Server 2013: Tabela Users'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Users table
ms:assetid: a8d71373-4b57-4245-9f02-f7fc0d9fcd3c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412791(v=OCS.15)
ms:contentKeyID: 48185032
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c2be643f8a593af01ee47ad93d3910d44ee86e48
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744321"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="users-table-in-lync-server-2013"></a><span data-ttu-id="20472-102">Tabela Users no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="20472-102">Users table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="20472-103">_**Tópico da última modificação:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="20472-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="20472-104">A tabela usuários é uma tabela de suporte.</span><span class="sxs-lookup"><span data-stu-id="20472-104">The Users table is a supporting table.</span></span> <span data-ttu-id="20472-105">Cada registro na tabela armazena informações sobre um usuário envolvido em chamadas ou sessões que têm registros no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="20472-105">Each record in the table stores information about one user involved in calls or sessions that have records in the database.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="20472-106">Coluna</span><span class="sxs-lookup"><span data-stu-id="20472-106">Column</span></span></th>
<th><span data-ttu-id="20472-107">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="20472-107">Data Type</span></span></th>
<th><span data-ttu-id="20472-108">Chave/índice</span><span class="sxs-lookup"><span data-stu-id="20472-108">Key/Index</span></span></th>
<th><span data-ttu-id="20472-109">Detalhes</span><span class="sxs-lookup"><span data-stu-id="20472-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="20472-110"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="20472-110"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="20472-111">datetime</span><span class="sxs-lookup"><span data-stu-id="20472-111">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="20472-112">Carimbo de data/hora para uso interno.</span><span class="sxs-lookup"><span data-stu-id="20472-112">Time stamp for internal use.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="20472-113"><strong>ID</strong></span><span class="sxs-lookup"><span data-stu-id="20472-113"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="20472-114">int</span><span class="sxs-lookup"><span data-stu-id="20472-114">int</span></span></p></td>
<td><p><span data-ttu-id="20472-115">Primária</span><span class="sxs-lookup"><span data-stu-id="20472-115">Primary</span></span></p></td>
<td><p><span data-ttu-id="20472-116">Número exclusivo que identifica esse usuário.</span><span class="sxs-lookup"><span data-stu-id="20472-116">Unique number identifying this user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="20472-117"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="20472-117"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="20472-118">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="20472-118">nvarchar(450)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="20472-119">URI de usuário.</span><span class="sxs-lookup"><span data-stu-id="20472-119">User URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="20472-120"><strong>Tenantid</strong></span><span class="sxs-lookup"><span data-stu-id="20472-120"><strong>TenantId</strong></span></span></p></td>
<td><p><span data-ttu-id="20472-121">int</span><span class="sxs-lookup"><span data-stu-id="20472-121">int</span></span></p></td>
<td><p><span data-ttu-id="20472-122">Exterior</span><span class="sxs-lookup"><span data-stu-id="20472-122">Foreign</span></span></p></td>
<td><p><span data-ttu-id="20472-123">A ID de locatário deste usuário.</span><span class="sxs-lookup"><span data-stu-id="20472-123">This user’s Tenant ID.</span></span> <span data-ttu-id="20472-124">Consulte a <a href="lync-server-2013-tenants-table.md">tabela locatários no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="20472-124">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="20472-125"><strong>UriTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="20472-125"><strong>UriTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="20472-126">int</span><span class="sxs-lookup"><span data-stu-id="20472-126">int</span></span></p></td>
<td><p><span data-ttu-id="20472-127">Exterior</span><span class="sxs-lookup"><span data-stu-id="20472-127">Foreign</span></span></p></td>
<td><p><span data-ttu-id="20472-128">O tipo de URI deste usuário.</span><span class="sxs-lookup"><span data-stu-id="20472-128">This user’s URI type.</span></span> <span data-ttu-id="20472-129">Consulte a <a href="lync-server-2013-uritypes-table.md">tabela UriTypes no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="20472-129">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

