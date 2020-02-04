---
title: 'Lync Server 2013: Tabela Locations'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Locations table
ms:assetid: 78dc1b14-5394-4f8e-89d3-4ba593272a04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398596(v=OCS.15)
ms:contentKeyID: 48184579
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e2d16ffd08184a650f993d175239f5aff72b8b3b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762129"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="locations-table-in-lync-server-2013"></a><span data-ttu-id="2e729-102">Tabela Locations no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2e729-102">Locations table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2e729-103">_**Tópico da última modificação:** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="2e729-103">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="2e729-104">Cada registro representa uma referência de localização em uma chamada de emergência, como uma chamada E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="2e729-104">Each record represents one location reference in an emergency call, like an E9-1-1 call.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2e729-105">Coluna</span><span class="sxs-lookup"><span data-stu-id="2e729-105">Column</span></span></th>
<th><span data-ttu-id="2e729-106">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="2e729-106">Data Type</span></span></th>
<th><span data-ttu-id="2e729-107">Chave/índice</span><span class="sxs-lookup"><span data-stu-id="2e729-107">Key/Index</span></span></th>
<th><span data-ttu-id="2e729-108">Detalhes</span><span class="sxs-lookup"><span data-stu-id="2e729-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2e729-109"><strong>Id_da_sessãotime</strong></span><span class="sxs-lookup"><span data-stu-id="2e729-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="2e729-110">datetime</span><span class="sxs-lookup"><span data-stu-id="2e729-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="2e729-111">Primário, estrangeiro</span><span class="sxs-lookup"><span data-stu-id="2e729-111">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="2e729-112">Tempo de solicitação de sessão.</span><span class="sxs-lookup"><span data-stu-id="2e729-112">Time of session request.</span></span> <span data-ttu-id="2e729-113">Usado em conjunto com o <strong>SessionIdSeq</strong> para identificar exclusivamente uma sessão.</span><span class="sxs-lookup"><span data-stu-id="2e729-113">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="2e729-114">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela de diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="2e729-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2e729-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="2e729-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="2e729-116">int</span><span class="sxs-lookup"><span data-stu-id="2e729-116">int</span></span></p></td>
<td><p><span data-ttu-id="2e729-117">Primário, estrangeiro</span><span class="sxs-lookup"><span data-stu-id="2e729-117">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="2e729-118">Número de identificação para identificar a sessão.</span><span class="sxs-lookup"><span data-stu-id="2e729-118">ID number to identify the session.</span></span> <span data-ttu-id="2e729-119">Usado em conjunto com a <strong>identificação_da_sessãotime</strong> para identificar exclusivamente uma sessão.</span><span class="sxs-lookup"><span data-stu-id="2e729-119">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="2e729-120">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela de diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="2e729-120">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2e729-121"><strong>Local</strong></span><span class="sxs-lookup"><span data-stu-id="2e729-121"><strong>Location</strong></span></span></p></td>
<td><p><span data-ttu-id="2e729-122">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="2e729-122">nvarchar(max)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2e729-123">Local de chamada de emergência.</span><span class="sxs-lookup"><span data-stu-id="2e729-123">Location of emergency call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

