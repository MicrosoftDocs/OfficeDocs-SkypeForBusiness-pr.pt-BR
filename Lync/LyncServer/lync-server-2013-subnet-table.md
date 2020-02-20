---
title: 'Lync Server 2013: tabela de sub-rede'
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
ms.openlocfilehash: 9cdf1ded3a63d790db78476b91a458d07921200a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142487"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="subnet-table-in-lync-server-2013"></a><span data-ttu-id="da510-102">Tabela de sub-rede no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="da510-102">Subnet table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="da510-103">_**Última modificação do tópico:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="da510-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="da510-p101">A tabela Subnet é uma tabela de suporte. Cada registro representa uma subrede definida em uma configuração de rede.</span><span class="sxs-lookup"><span data-stu-id="da510-p101">The Subnet table is a supporting table. Each record represents one subnet defined in network configuration setting.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="da510-106"><strong>Coluna</strong></span><span class="sxs-lookup"><span data-stu-id="da510-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="da510-107"><strong>Tipo de dados</strong></span><span class="sxs-lookup"><span data-stu-id="da510-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="da510-108"><strong>Chave/índice</strong></span><span class="sxs-lookup"><span data-stu-id="da510-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="da510-109"><strong>Detalhes</strong></span><span class="sxs-lookup"><span data-stu-id="da510-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="da510-110"><strong>SubnetIP</strong></span><span class="sxs-lookup"><span data-stu-id="da510-110"><strong>SubnetIP</strong></span></span></p></td>
<td><p><span data-ttu-id="da510-111">int</span><span class="sxs-lookup"><span data-stu-id="da510-111">int</span></span></p></td>
<td><p><span data-ttu-id="da510-112">Primária, estrangeira</span><span class="sxs-lookup"><span data-stu-id="da510-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="da510-113">Representação de inteiro para o IP da sub-rede.</span><span class="sxs-lookup"><span data-stu-id="da510-113">Integer representation for the subnet IP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="da510-114"><strong>Máscara de sub-rede</strong></span><span class="sxs-lookup"><span data-stu-id="da510-114"><strong>SubnetMask</strong></span></span></p></td>
<td><p><span data-ttu-id="da510-115">int</span><span class="sxs-lookup"><span data-stu-id="da510-115">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="da510-116">Máscara de sub-rede.</span><span class="sxs-lookup"><span data-stu-id="da510-116">Subnet mask.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="da510-117"><strong>UserSiteKey</strong></span><span class="sxs-lookup"><span data-stu-id="da510-117"><strong>UserSiteKey</strong></span></span></p></td>
<td><p><span data-ttu-id="da510-118">int</span><span class="sxs-lookup"><span data-stu-id="da510-118">int</span></span></p></td>
<td><p><span data-ttu-id="da510-119">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="da510-119">Foreign</span></span></p></td>
<td><p><span data-ttu-id="da510-120">Referenciado da <a href="lync-server-2013-usersite-table.md">tabela usersite no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="da510-120">Referenced from the <a href="lync-server-2013-usersite-table.md">UserSite table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="da510-121"><strong>SubnetDescription</strong></span><span class="sxs-lookup"><span data-stu-id="da510-121"><strong>SubnetDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="da510-122">nvarchar (512)</span><span class="sxs-lookup"><span data-stu-id="da510-122">nvarchar(512)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="da510-123">A descrição para a sub-rede.</span><span class="sxs-lookup"><span data-stu-id="da510-123">The description for the subnet.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

