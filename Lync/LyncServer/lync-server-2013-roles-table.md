---
title: 'Lync Server 2013: tabela de funções'
description: 'Lync Server 2013: tabela de funções.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Roles table
ms:assetid: e8eb8a10-26b5-488b-bc8c-f9ef93f98bdb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399043(v=OCS.15)
ms:contentKeyID: 48185893
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d16f9483fc97145d82faf7e8f1175772f10f9a4b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576567"
---
# <a name="roles-table-in-lync-server-2013"></a><span data-ttu-id="33b25-103">Tabela de funções no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="33b25-103">Roles table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="33b25-104">_**Última modificação do tópico:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="33b25-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="33b25-105">A tabela Roles é uma tabela estática que armazena a lista de possíveis funções de conferência, como participante e apresentador.</span><span class="sxs-lookup"><span data-stu-id="33b25-105">The Roles table is a static table that stores the list of possible conference roles, such as attendee and presenter.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="33b25-106">Coluna</span><span class="sxs-lookup"><span data-stu-id="33b25-106">Column</span></span></th>
<th><span data-ttu-id="33b25-107">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="33b25-107">Data Type</span></span></th>
<th><span data-ttu-id="33b25-108">Chave/índice</span><span class="sxs-lookup"><span data-stu-id="33b25-108">Key/Index</span></span></th>
<th><span data-ttu-id="33b25-109">Detalhes</span><span class="sxs-lookup"><span data-stu-id="33b25-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="33b25-110"><strong>RoleId</strong></span><span class="sxs-lookup"><span data-stu-id="33b25-110"><strong>RoleId</strong></span></span></p></td>
<td><p><span data-ttu-id="33b25-111">tinyint</span><span class="sxs-lookup"><span data-stu-id="33b25-111">tinyint</span></span></p></td>
<td><p><span data-ttu-id="33b25-112">Primário</span><span class="sxs-lookup"><span data-stu-id="33b25-112">Primary</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33b25-113"><strong>Função</strong></span><span class="sxs-lookup"><span data-stu-id="33b25-113"><strong>Role</strong></span></span></p></td>
<td><p><span data-ttu-id="33b25-114">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="33b25-114">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="33b25-115">Valores permitidos:</span><span class="sxs-lookup"><span data-stu-id="33b25-115">Allowed values:</span></span></p>
<ul>
<li><p><span data-ttu-id="33b25-116">0 - Desconhecido</span><span class="sxs-lookup"><span data-stu-id="33b25-116">0 - Unknown</span></span></p></li>
<li><p><span data-ttu-id="33b25-117">1 - Apresentador</span><span class="sxs-lookup"><span data-stu-id="33b25-117">1 - Presenter</span></span></p></li>
<li><p><span data-ttu-id="33b25-118">2 - Participante</span><span class="sxs-lookup"><span data-stu-id="33b25-118">2 - Attendee</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

