---
title: 'Lync Server 2013: Tabela UserSite'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: UserSite table
ms:assetid: 1c2a3cf2-dc05-472e-8097-a31f3a1aafcb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398256(v=OCS.15)
ms:contentKeyID: 48183552
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7e316fe33ac77784a681a71b9cabd0613bb1cc1b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744261"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="usersite-table-in-lync-server-2013"></a><span data-ttu-id="97f69-102">Tabela UserSite no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="97f69-102">UserSite table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="97f69-103">_**Tópico da última modificação:** 2010-11-09_</span><span class="sxs-lookup"><span data-stu-id="97f69-103">_**Topic Last Modified:** 2010-11-09_</span></span>

<span data-ttu-id="97f69-104">A tabela de usersite é uma tabela de suporte.</span><span class="sxs-lookup"><span data-stu-id="97f69-104">The UserSite table is a supporting table.</span></span> <span data-ttu-id="97f69-105">Cada registro representa um site de usuário definido na configuração de rede.</span><span class="sxs-lookup"><span data-stu-id="97f69-105">Each record represents one user site defined in network configuration setting.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="97f69-106"><strong>Coluna</strong></span><span class="sxs-lookup"><span data-stu-id="97f69-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="97f69-107"><strong>Tipo de dados</strong></span><span class="sxs-lookup"><span data-stu-id="97f69-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="97f69-108"><strong>Chave/índice</strong></span><span class="sxs-lookup"><span data-stu-id="97f69-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="97f69-109"><strong>Detalhes</strong></span><span class="sxs-lookup"><span data-stu-id="97f69-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="97f69-110"><strong>UserSiteKey</strong></span><span class="sxs-lookup"><span data-stu-id="97f69-110"><strong>UserSiteKey</strong></span></span></p></td>
<td><p><span data-ttu-id="97f69-111">int</span><span class="sxs-lookup"><span data-stu-id="97f69-111">int</span></span></p></td>
<td><p><span data-ttu-id="97f69-112">Primária</span><span class="sxs-lookup"><span data-stu-id="97f69-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="97f69-113">Número exclusivo que identifica o site do usuário.</span><span class="sxs-lookup"><span data-stu-id="97f69-113">Unique number identifying the user site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97f69-114"><strong>Usersitename</strong></span><span class="sxs-lookup"><span data-stu-id="97f69-114"><strong>UserSiteName</strong></span></span></p></td>
<td><p><span data-ttu-id="97f69-115">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="97f69-115">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="97f69-116">Exclusividade</span><span class="sxs-lookup"><span data-stu-id="97f69-116">Unique</span></span></p></td>
<td><p><span data-ttu-id="97f69-117">Nome do site do usuário.</span><span class="sxs-lookup"><span data-stu-id="97f69-117">User site’s name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97f69-118"><strong>RegionKey</strong></span><span class="sxs-lookup"><span data-stu-id="97f69-118"><strong>RegionKey</strong></span></span></p></td>
<td><p><span data-ttu-id="97f69-119">int</span><span class="sxs-lookup"><span data-stu-id="97f69-119">int</span></span></p></td>
<td><p><span data-ttu-id="97f69-120">Exterior</span><span class="sxs-lookup"><span data-stu-id="97f69-120">Foreign</span></span></p></td>
<td><p><span data-ttu-id="97f69-121">Referenciado da <a href="lync-server-2013-region-table.md">tabela Region no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="97f69-121">Referenced from <a href="lync-server-2013-region-table.md">Region table in Lync Server 2013</a>.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

