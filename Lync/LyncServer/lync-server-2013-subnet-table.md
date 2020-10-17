---
title: 'Lync Server 2013: tabela de sub-rede'
description: 'Lync Server 2013: tabela de sub-redes.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Subnet table
ms:assetid: 76f5c995-96c8-4aa3-bc30-1d74991d7c42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398582(v=OCS.15)
ms:contentKeyID: 48184544
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d30c04ddf897e0a62551709b30211ba724a75cbf
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546307"
---
# <a name="subnet-table-in-lync-server-2013"></a><span data-ttu-id="d066b-103">Tabela de sub-rede no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d066b-103">Subnet table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d066b-104">_**Última modificação do tópico:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="d066b-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="d066b-p101">A tabela Subnet é uma tabela de suporte. Cada registro representa uma subrede definida em uma configuração de rede.</span><span class="sxs-lookup"><span data-stu-id="d066b-p101">The Subnet table is a supporting table. Each record represents one subnet defined in network configuration setting.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d066b-107"><strong>Coluna</strong></span><span class="sxs-lookup"><span data-stu-id="d066b-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="d066b-108"><strong>Tipo de dados</strong></span><span class="sxs-lookup"><span data-stu-id="d066b-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="d066b-109"><strong>Chave/índice</strong></span><span class="sxs-lookup"><span data-stu-id="d066b-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="d066b-110"><strong>Detalhes</strong></span><span class="sxs-lookup"><span data-stu-id="d066b-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d066b-111"><strong>SubnetIP</strong></span><span class="sxs-lookup"><span data-stu-id="d066b-111"><strong>SubnetIP</strong></span></span></p></td>
<td><p><span data-ttu-id="d066b-112">int</span><span class="sxs-lookup"><span data-stu-id="d066b-112">int</span></span></p></td>
<td><p><span data-ttu-id="d066b-113">Primária, estrangeira</span><span class="sxs-lookup"><span data-stu-id="d066b-113">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="d066b-114">Representação de inteiro para o IP da sub-rede.</span><span class="sxs-lookup"><span data-stu-id="d066b-114">Integer representation for the subnet IP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d066b-115"><strong>Máscara de sub-rede</strong></span><span class="sxs-lookup"><span data-stu-id="d066b-115"><strong>SubnetMask</strong></span></span></p></td>
<td><p><span data-ttu-id="d066b-116">int</span><span class="sxs-lookup"><span data-stu-id="d066b-116">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d066b-117">Máscara de sub-rede.</span><span class="sxs-lookup"><span data-stu-id="d066b-117">Subnet mask.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d066b-118"><strong>UserSiteKey</strong></span><span class="sxs-lookup"><span data-stu-id="d066b-118"><strong>UserSiteKey</strong></span></span></p></td>
<td><p><span data-ttu-id="d066b-119">int</span><span class="sxs-lookup"><span data-stu-id="d066b-119">int</span></span></p></td>
<td><p><span data-ttu-id="d066b-120">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="d066b-120">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d066b-121">Referenciado da <a href="lync-server-2013-usersite-table.md">tabela usersite no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="d066b-121">Referenced from the <a href="lync-server-2013-usersite-table.md">UserSite table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d066b-122"><strong>SubnetDescription</strong></span><span class="sxs-lookup"><span data-stu-id="d066b-122"><strong>SubnetDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="d066b-123">nvarchar (512)</span><span class="sxs-lookup"><span data-stu-id="d066b-123">nvarchar(512)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d066b-124">A descrição para a sub-rede.</span><span class="sxs-lookup"><span data-stu-id="d066b-124">The description for the subnet.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

