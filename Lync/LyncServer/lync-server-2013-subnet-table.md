---
title: 'Lync Server 2013: Tabela Subnet'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Subnet table
ms:assetid: 76f5c995-96c8-4aa3-bc30-1d74991d7c42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398582(v=OCS.15)
ms:contentKeyID: 48184544
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 20318d0ed2f487efccda81936b113044f75e2618
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844851"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="subnet-table-in-lync-server-2013"></a><span data-ttu-id="3791d-102">Tabela Subnet no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3791d-102">Subnet table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3791d-103">_**Tópico da última modificação:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="3791d-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="3791d-104">A tabela de sub-rede é uma tabela de suporte.</span><span class="sxs-lookup"><span data-stu-id="3791d-104">The Subnet table is a supporting table.</span></span> <span data-ttu-id="3791d-105">Cada registro representa uma sub-rede definida na configuração de rede.</span><span class="sxs-lookup"><span data-stu-id="3791d-105">Each record represents one subnet defined in network configuration setting.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3791d-106"><strong>Coluna</strong></span><span class="sxs-lookup"><span data-stu-id="3791d-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="3791d-107"><strong>Tipo de dados</strong></span><span class="sxs-lookup"><span data-stu-id="3791d-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="3791d-108"><strong>Chave/índice</strong></span><span class="sxs-lookup"><span data-stu-id="3791d-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="3791d-109"><strong>Detalhes</strong></span><span class="sxs-lookup"><span data-stu-id="3791d-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3791d-110"><strong>SubnetIP</strong></span><span class="sxs-lookup"><span data-stu-id="3791d-110"><strong>SubnetIP</strong></span></span></p></td>
<td><p><span data-ttu-id="3791d-111">int</span><span class="sxs-lookup"><span data-stu-id="3791d-111">int</span></span></p></td>
<td><p><span data-ttu-id="3791d-112">Primário, estrangeiro</span><span class="sxs-lookup"><span data-stu-id="3791d-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="3791d-113">Representação do inteiro para o IP da sub-rede.</span><span class="sxs-lookup"><span data-stu-id="3791d-113">Integer representation for the subnet IP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3791d-114"><strong>Máscara_de_Sub-rede</strong></span><span class="sxs-lookup"><span data-stu-id="3791d-114"><strong>SubnetMask</strong></span></span></p></td>
<td><p><span data-ttu-id="3791d-115">int</span><span class="sxs-lookup"><span data-stu-id="3791d-115">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3791d-116">Máscara de sub-rede.</span><span class="sxs-lookup"><span data-stu-id="3791d-116">Subnet mask.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3791d-117"><strong>UserSiteKey</strong></span><span class="sxs-lookup"><span data-stu-id="3791d-117"><strong>UserSiteKey</strong></span></span></p></td>
<td><p><span data-ttu-id="3791d-118">int</span><span class="sxs-lookup"><span data-stu-id="3791d-118">int</span></span></p></td>
<td><p><span data-ttu-id="3791d-119">Exterior</span><span class="sxs-lookup"><span data-stu-id="3791d-119">Foreign</span></span></p></td>
<td><p><span data-ttu-id="3791d-120">Referenciado da <a href="lync-server-2013-usersite-table.md">tabela usersite no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="3791d-120">Referenced from the <a href="lync-server-2013-usersite-table.md">UserSite table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3791d-121"><strong>SubnetDescription</strong></span><span class="sxs-lookup"><span data-stu-id="3791d-121"><strong>SubnetDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="3791d-122">nvarchar (512)</span><span class="sxs-lookup"><span data-stu-id="3791d-122">nvarchar(512)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3791d-123">A descrição da sub-rede.</span><span class="sxs-lookup"><span data-stu-id="3791d-123">The description for the subnet.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

