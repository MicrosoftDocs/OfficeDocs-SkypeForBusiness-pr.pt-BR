---
title: 'Lync Server 2013: modo de exibição do usuário'
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
ms.openlocfilehash: c8e88d7a9fa66f309bbd64ab064ec95adafc40b8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744381"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-view-in-lync-server-2013"></a><span data-ttu-id="22f52-102">Modo de exibição de usuário no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="22f52-102">User view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="22f52-103">_**Tópico da última modificação:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="22f52-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="22f52-104">A exibição do usuário armazena informações sobre os usuários que estiveram envolvidos em chamadas ou sessões que têm registros no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="22f52-104">The User view stores information about users who have been involved in calls or sessions that have records in the database.</span></span> <span data-ttu-id="22f52-105">Este modo de exibição foi apresentado no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="22f52-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="22f52-106">Coluna</span><span class="sxs-lookup"><span data-stu-id="22f52-106">Column</span></span></th>
<th><span data-ttu-id="22f52-107">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="22f52-107">Data Type</span></span></th>
<th><span data-ttu-id="22f52-108">Detalhes</span><span class="sxs-lookup"><span data-stu-id="22f52-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="22f52-109">ID</span><span class="sxs-lookup"><span data-stu-id="22f52-109">UserId</span></span></p></td>
<td><p><span data-ttu-id="22f52-110">int</span><span class="sxs-lookup"><span data-stu-id="22f52-110">int</span></span></p></td>
<td><p><span data-ttu-id="22f52-111">Número exclusivo que identifica esse usuário.</span><span class="sxs-lookup"><span data-stu-id="22f52-111">Unique number identifying this user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="22f52-112">UserUri</span><span class="sxs-lookup"><span data-stu-id="22f52-112">UserUri</span></span></p></td>
<td><p><span data-ttu-id="22f52-113">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="22f52-113">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="22f52-114">URL do usuário.</span><span class="sxs-lookup"><span data-stu-id="22f52-114">Uri of the user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="22f52-115">TenantKey</span><span class="sxs-lookup"><span data-stu-id="22f52-115">TenantKey</span></span></p></td>
<td><p><span data-ttu-id="22f52-116">identificador</span><span class="sxs-lookup"><span data-stu-id="22f52-116">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="22f52-117">Locatário do usuário.</span><span class="sxs-lookup"><span data-stu-id="22f52-117">Tenant of user.</span></span> <span data-ttu-id="22f52-118">Consulte a <a href="lync-server-2013-tenants-table.md">tabela locatários no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="22f52-118">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="22f52-119">UriType</span><span class="sxs-lookup"><span data-stu-id="22f52-119">UriType</span></span></p></td>
<td><p><span data-ttu-id="22f52-120">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="22f52-120">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="22f52-121">Tipo de URI de usuário.</span><span class="sxs-lookup"><span data-stu-id="22f52-121">Type of user URI.</span></span> <span data-ttu-id="22f52-122">Consulte a <a href="lync-server-2013-uritypes-table.md">tabela UriTypes no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="22f52-122">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

