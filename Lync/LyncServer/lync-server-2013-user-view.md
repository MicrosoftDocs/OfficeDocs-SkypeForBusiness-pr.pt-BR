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
ms.openlocfilehash: 12499f63e262d681297b8289231f58262ba75999
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42212987"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="user-view-in-lync-server-2013"></a><span data-ttu-id="8a2ff-102">Exibição de usuário no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8a2ff-102">User view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8a2ff-103">_**Última modificação do tópico:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="8a2ff-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="8a2ff-104">A exibição de Usuário armazena informações sobre usuários envolvidos em chamadas ou sessões com registros no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="8a2ff-104">The User view stores information about users who have been involved in calls or sessions that have records in the database.</span></span> <span data-ttu-id="8a2ff-105">Este modo de exibição foi introduzido no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8a2ff-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8a2ff-106">Coluna</span><span class="sxs-lookup"><span data-stu-id="8a2ff-106">Column</span></span></th>
<th><span data-ttu-id="8a2ff-107">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="8a2ff-107">Data Type</span></span></th>
<th><span data-ttu-id="8a2ff-108">Detalhes</span><span class="sxs-lookup"><span data-stu-id="8a2ff-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8a2ff-109">UserId</span><span class="sxs-lookup"><span data-stu-id="8a2ff-109">UserId</span></span></p></td>
<td><p><span data-ttu-id="8a2ff-110">int</span><span class="sxs-lookup"><span data-stu-id="8a2ff-110">int</span></span></p></td>
<td><p><span data-ttu-id="8a2ff-111">Número exclusivo que identifica este usuário.</span><span class="sxs-lookup"><span data-stu-id="8a2ff-111">Unique number identifying this user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8a2ff-112">UserUri</span><span class="sxs-lookup"><span data-stu-id="8a2ff-112">UserUri</span></span></p></td>
<td><p><span data-ttu-id="8a2ff-113">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="8a2ff-113">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="8a2ff-114">Uri do usuário.</span><span class="sxs-lookup"><span data-stu-id="8a2ff-114">Uri of the user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8a2ff-115">TenantKey</span><span class="sxs-lookup"><span data-stu-id="8a2ff-115">TenantKey</span></span></p></td>
<td><p><span data-ttu-id="8a2ff-116">identificador</span><span class="sxs-lookup"><span data-stu-id="8a2ff-116">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="8a2ff-117">Locatário do usuário.</span><span class="sxs-lookup"><span data-stu-id="8a2ff-117">Tenant of user.</span></span> <span data-ttu-id="8a2ff-118">Consulte a <a href="lync-server-2013-tenants-table.md">tabela locatários no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="8a2ff-118">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8a2ff-119">UriType</span><span class="sxs-lookup"><span data-stu-id="8a2ff-119">UriType</span></span></p></td>
<td><p><span data-ttu-id="8a2ff-120">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="8a2ff-120">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="8a2ff-121">Tipo de URI do usuário.</span><span class="sxs-lookup"><span data-stu-id="8a2ff-121">Type of user URI.</span></span> <span data-ttu-id="8a2ff-122">Consulte a <a href="lync-server-2013-uritypes-table.md">tabela UriTypes no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="8a2ff-122">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

