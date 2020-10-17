---
title: 'Lync Server 2013: modo de exibição do usuário'
description: 'Lync Server 2013: modo de exibição do usuário.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User view
ms:assetid: 796f77e6-1da6-4969-b18b-3537209a1fe4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688100(v=OCS.15)
ms:contentKeyID: 49733699
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aa606887e8050a51f1e5a87656bb74a7cd58bbc3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558907"
---
# <a name="user-view-in-lync-server-2013"></a><span data-ttu-id="c55b3-103">Exibição de usuário no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c55b3-103">User view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c55b3-104">_**Última modificação do tópico:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="c55b3-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="c55b3-105">A exibição de Usuário armazena informações sobre usuários envolvidos em chamadas ou sessões com registros no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="c55b3-105">The User view stores information about users who have been involved in calls or sessions that have records in the database.</span></span> <span data-ttu-id="c55b3-106">Este modo de exibição foi introduzido no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c55b3-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c55b3-107">Coluna</span><span class="sxs-lookup"><span data-stu-id="c55b3-107">Column</span></span></th>
<th><span data-ttu-id="c55b3-108">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="c55b3-108">Data Type</span></span></th>
<th><span data-ttu-id="c55b3-109">Detalhes</span><span class="sxs-lookup"><span data-stu-id="c55b3-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c55b3-110">UserId</span><span class="sxs-lookup"><span data-stu-id="c55b3-110">UserId</span></span></p></td>
<td><p><span data-ttu-id="c55b3-111">int</span><span class="sxs-lookup"><span data-stu-id="c55b3-111">int</span></span></p></td>
<td><p><span data-ttu-id="c55b3-112">Número exclusivo que identifica este usuário.</span><span class="sxs-lookup"><span data-stu-id="c55b3-112">Unique number identifying this user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c55b3-113">UserUri</span><span class="sxs-lookup"><span data-stu-id="c55b3-113">UserUri</span></span></p></td>
<td><p><span data-ttu-id="c55b3-114">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="c55b3-114">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="c55b3-115">Uri do usuário.</span><span class="sxs-lookup"><span data-stu-id="c55b3-115">Uri of the user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c55b3-116">TenantKey</span><span class="sxs-lookup"><span data-stu-id="c55b3-116">TenantKey</span></span></p></td>
<td><p><span data-ttu-id="c55b3-117">identificador</span><span class="sxs-lookup"><span data-stu-id="c55b3-117">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="c55b3-118">Locatário do usuário.</span><span class="sxs-lookup"><span data-stu-id="c55b3-118">Tenant of user.</span></span> <span data-ttu-id="c55b3-119">Consulte a <a href="lync-server-2013-tenants-table.md">tabela locatários no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="c55b3-119">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c55b3-120">UriType</span><span class="sxs-lookup"><span data-stu-id="c55b3-120">UriType</span></span></p></td>
<td><p><span data-ttu-id="c55b3-121">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="c55b3-121">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c55b3-122">Tipo de URI do usuário.</span><span class="sxs-lookup"><span data-stu-id="c55b3-122">Type of user URI.</span></span> <span data-ttu-id="c55b3-123">Consulte a <a href="lync-server-2013-uritypes-table.md">tabela UriTypes no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="c55b3-123">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

