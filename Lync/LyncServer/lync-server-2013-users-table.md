---
title: 'Lync Server 2013: tabela Users'
description: 'Lync Server 2013: tabela users.'
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
ms.openlocfilehash: 9b1418e162a04e46ee0dfeca082aa66b0665fc77
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548627"
---
# <a name="users-table-in-lync-server-2013"></a><span data-ttu-id="02ae1-103">Tabela Users no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="02ae1-103">Users table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="02ae1-104">_**Última modificação do tópico:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="02ae1-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="02ae1-105">A tabela Users é uma tabela de suporte.</span><span class="sxs-lookup"><span data-stu-id="02ae1-105">The Users table is a supporting table.</span></span> <span data-ttu-id="02ae1-106">Cada registro da tabela armazena informações sobre um usuário envolvido em chamadas ou sessões que têm registros no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="02ae1-106">Each record in the table stores information about one user involved in calls or sessions that have records in the database.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="02ae1-107">Coluna</span><span class="sxs-lookup"><span data-stu-id="02ae1-107">Column</span></span></th>
<th><span data-ttu-id="02ae1-108">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="02ae1-108">Data Type</span></span></th>
<th><span data-ttu-id="02ae1-109">Chave/índice</span><span class="sxs-lookup"><span data-stu-id="02ae1-109">Key/Index</span></span></th>
<th><span data-ttu-id="02ae1-110">Detalhes</span><span class="sxs-lookup"><span data-stu-id="02ae1-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="02ae1-111"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="02ae1-111"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="02ae1-112">datetime</span><span class="sxs-lookup"><span data-stu-id="02ae1-112">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="02ae1-113">Carimbo de data/hora para uso interno.</span><span class="sxs-lookup"><span data-stu-id="02ae1-113">Time stamp for internal use.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="02ae1-114"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="02ae1-114"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="02ae1-115">int</span><span class="sxs-lookup"><span data-stu-id="02ae1-115">int</span></span></p></td>
<td><p><span data-ttu-id="02ae1-116">Primário</span><span class="sxs-lookup"><span data-stu-id="02ae1-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="02ae1-117">Número exclusivo identificando este usuário.</span><span class="sxs-lookup"><span data-stu-id="02ae1-117">Unique number identifying this user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="02ae1-118"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="02ae1-118"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="02ae1-119">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="02ae1-119">nvarchar(450)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="02ae1-120">URI do Usuário.</span><span class="sxs-lookup"><span data-stu-id="02ae1-120">User URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="02ae1-121"><strong>TenantId</strong></span><span class="sxs-lookup"><span data-stu-id="02ae1-121"><strong>TenantId</strong></span></span></p></td>
<td><p><span data-ttu-id="02ae1-122">int</span><span class="sxs-lookup"><span data-stu-id="02ae1-122">int</span></span></p></td>
<td><p><span data-ttu-id="02ae1-123">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="02ae1-123">Foreign</span></span></p></td>
<td><p><span data-ttu-id="02ae1-124">A ID de locatário do usuário.</span><span class="sxs-lookup"><span data-stu-id="02ae1-124">This user’s Tenant ID.</span></span> <span data-ttu-id="02ae1-125">Consulte a <a href="lync-server-2013-tenants-table.md">tabela locatários no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="02ae1-125">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="02ae1-126"><strong>UriTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="02ae1-126"><strong>UriTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="02ae1-127">int</span><span class="sxs-lookup"><span data-stu-id="02ae1-127">int</span></span></p></td>
<td><p><span data-ttu-id="02ae1-128">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="02ae1-128">Foreign</span></span></p></td>
<td><p><span data-ttu-id="02ae1-129">Este tipo de URI do usuário.</span><span class="sxs-lookup"><span data-stu-id="02ae1-129">This user’s URI type.</span></span> <span data-ttu-id="02ae1-130">Consulte a <a href="lync-server-2013-uritypes-table.md">tabela UriTypes no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="02ae1-130">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

