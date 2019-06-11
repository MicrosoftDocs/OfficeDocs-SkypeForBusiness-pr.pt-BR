---
title: 'Lync Server 2013: Tabela Tenants'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Tenants table
ms:assetid: c1b070c1-2c59-4ca9-910b-43f673f97fda
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412950(v=OCS.15)
ms:contentKeyID: 48185309
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a7da863aa2b713f874aba00f5a4f481f45fb79b3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844721"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tenants-table-in-lync-server-2013"></a><span data-ttu-id="14eb7-102">Tabela Tenants no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="14eb7-102">Tenants table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="14eb7-103">_**Tópico da última modificação:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="14eb7-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="14eb7-104">A tabela locatários é uma tabela de suporte que armazena uma lista de vários locatários.</span><span class="sxs-lookup"><span data-stu-id="14eb7-104">The Tenants table is a supporting table that stores a list of the various tenants.</span></span> <span data-ttu-id="14eb7-105">Cada registro na tabela representa um locatário.</span><span class="sxs-lookup"><span data-stu-id="14eb7-105">Each record in the table represents one tenant.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="14eb7-106">Na implantação local, o CDR usa a ID de locatário de compilação para indicar um tipo de autenticação diferente, como conectividade de mensagem de chat pública, federada e anônima.</span><span class="sxs-lookup"><span data-stu-id="14eb7-106">In on-premises deployment, CDR uses the build-in Tenant ID to indicate different authentication type, such as public IM connectivity, Federated and Anonymous.</span></span>



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
<th><span data-ttu-id="14eb7-107">Coluna</span><span class="sxs-lookup"><span data-stu-id="14eb7-107">Column</span></span></th>
<th><span data-ttu-id="14eb7-108">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="14eb7-108">Data Type</span></span></th>
<th><span data-ttu-id="14eb7-109">Chave/índice</span><span class="sxs-lookup"><span data-stu-id="14eb7-109">Key/Index</span></span></th>
<th><span data-ttu-id="14eb7-110">Detalhes</span><span class="sxs-lookup"><span data-stu-id="14eb7-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="14eb7-111"><strong>Tenantid</strong></span><span class="sxs-lookup"><span data-stu-id="14eb7-111"><strong>TenantId</strong></span></span></p></td>
<td><p><span data-ttu-id="14eb7-112">int</span><span class="sxs-lookup"><span data-stu-id="14eb7-112">int</span></span></p></td>
<td><p><span data-ttu-id="14eb7-113">Primária</span><span class="sxs-lookup"><span data-stu-id="14eb7-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="14eb7-114">Número exclusivo que identifica esta ID de locatário.</span><span class="sxs-lookup"><span data-stu-id="14eb7-114">Unique number identifying this Tenant ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14eb7-115"><strong>TenantKey</strong></span><span class="sxs-lookup"><span data-stu-id="14eb7-115"><strong>TenantKey</strong></span></span></p></td>
<td><p><span data-ttu-id="14eb7-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="14eb7-116">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="14eb7-117">Valores permitidos:</span><span class="sxs-lookup"><span data-stu-id="14eb7-117">Allowed values:</span></span></p>
<ul>
<li><p><span data-ttu-id="14eb7-118">00000000-0000-0000-0000-000000000000 – empresa</span><span class="sxs-lookup"><span data-stu-id="14eb7-118">00000000-0000-0000-0000-000000000000 – Enterprise</span></span></p></li>
<li><p><span data-ttu-id="14eb7-119">00000000-0000-0000-0000-000000000001 – federado</span><span class="sxs-lookup"><span data-stu-id="14eb7-119">00000000-0000-0000-0000-000000000001 – Federated</span></span></p></li>
<li><p><span data-ttu-id="14eb7-120">00000000-0000-0000-0000-000000000002 – anônimo</span><span class="sxs-lookup"><span data-stu-id="14eb7-120">00000000-0000-0000-0000-000000000002 – Anonymous</span></span></p></li>
<li><p><span data-ttu-id="14eb7-121">00000000-0000-0000-0000-000000000003 – conectividade de IM pública</span><span class="sxs-lookup"><span data-stu-id="14eb7-121">00000000-0000-0000-0000-000000000003 – Public IM connectivity</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

