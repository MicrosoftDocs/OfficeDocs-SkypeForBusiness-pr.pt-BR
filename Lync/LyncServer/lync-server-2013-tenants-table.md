---
title: 'Lync Server 2013: tabela de locatários'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Tenants table
ms:assetid: c1b070c1-2c59-4ca9-910b-43f673f97fda
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412950(v=OCS.15)
ms:contentKeyID: 48185309
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b0d2459c169fb93520125ceef7a8076bd51343db
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006096"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tenants-table-in-lync-server-2013"></a><span data-ttu-id="a3ca9-102">Tabela de locatários no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a3ca9-102">Tenants table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a3ca9-103">_**Última modificação do tópico:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="a3ca9-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="a3ca9-p101">A tabela Tenants é uma tabela de suporte que armazena uma lista de vários locatários. Cada registro na tabela representa um locatário.</span><span class="sxs-lookup"><span data-stu-id="a3ca9-p101">The Tenants table is a supporting table that stores a list of the various tenants. Each record in the table represents one tenant.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a3ca9-106">Na implantação no local, o CDR usa o ID de Inquilino integrado para indicar um tipo de autenticação diferente, como conectividade de IM pública, Federada e Anônima.</span><span class="sxs-lookup"><span data-stu-id="a3ca9-106">In on-premises deployment, CDR uses the build-in Tenant ID to indicate different authentication type, such as public IM connectivity, Federated and Anonymous.</span></span>



</div>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a3ca9-107">Coluna</span><span class="sxs-lookup"><span data-stu-id="a3ca9-107">Column</span></span></th>
<th><span data-ttu-id="a3ca9-108">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="a3ca9-108">Data Type</span></span></th>
<th><span data-ttu-id="a3ca9-109">Chave/índice</span><span class="sxs-lookup"><span data-stu-id="a3ca9-109">Key/Index</span></span></th>
<th><span data-ttu-id="a3ca9-110">Detalhes</span><span class="sxs-lookup"><span data-stu-id="a3ca9-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a3ca9-111"><strong>TenantId</strong></span><span class="sxs-lookup"><span data-stu-id="a3ca9-111"><strong>TenantId</strong></span></span></p></td>
<td><p><span data-ttu-id="a3ca9-112">int</span><span class="sxs-lookup"><span data-stu-id="a3ca9-112">int</span></span></p></td>
<td><p><span data-ttu-id="a3ca9-113">Primário</span><span class="sxs-lookup"><span data-stu-id="a3ca9-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="a3ca9-114">Número exclusivo que identifica o ID desse inquilino.</span><span class="sxs-lookup"><span data-stu-id="a3ca9-114">Unique number identifying this Tenant ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3ca9-115"><strong>TenantKey</strong></span><span class="sxs-lookup"><span data-stu-id="a3ca9-115"><strong>TenantKey</strong></span></span></p></td>
<td><p><span data-ttu-id="a3ca9-116">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="a3ca9-116">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a3ca9-117">Valores permitidos:</span><span class="sxs-lookup"><span data-stu-id="a3ca9-117">Allowed values:</span></span></p>
<ul>
<li><p><span data-ttu-id="a3ca9-118">00000000-0000-0000-0000-000000000000 – Empresarial</span><span class="sxs-lookup"><span data-stu-id="a3ca9-118">00000000-0000-0000-0000-000000000000 – Enterprise</span></span></p></li>
<li><p><span data-ttu-id="a3ca9-119">00000000-0000-0000-0000-000000000001 – Federado</span><span class="sxs-lookup"><span data-stu-id="a3ca9-119">00000000-0000-0000-0000-000000000001 – Federated</span></span></p></li>
<li><p><span data-ttu-id="a3ca9-120">00000000-0000-0000-0000-000000000002 – Anônimo</span><span class="sxs-lookup"><span data-stu-id="a3ca9-120">00000000-0000-0000-0000-000000000002 – Anonymous</span></span></p></li>
<li><p><span data-ttu-id="a3ca9-121">00000000-0000-0000-0000-000000000003 – Conectividade de IM público</span><span class="sxs-lookup"><span data-stu-id="a3ca9-121">00000000-0000-0000-0000-000000000003 – Public IM connectivity</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

