---
title: 'Lync Server 2013: tabela Locations'
description: 'Lync Server 2013: tabela Locations.'
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
ms.openlocfilehash: 9d07b6d3d3820f4efb3310adf0734a7e10c53e6d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570577"
---
# <a name="locations-table-in-lync-server-2013"></a><span data-ttu-id="85e63-103">Tabela Locations no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="85e63-103">Locations table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="85e63-104">_**Última modificação do tópico:** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="85e63-104">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="85e63-105">Cada registro representa uma referência de local em uma chamada de emergência, como uma chamada do tipo 9-1-1 Avançado.</span><span class="sxs-lookup"><span data-stu-id="85e63-105">Each record represents one location reference in an emergency call, like an E9-1-1 call.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="85e63-106">Coluna</span><span class="sxs-lookup"><span data-stu-id="85e63-106">Column</span></span></th>
<th><span data-ttu-id="85e63-107">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="85e63-107">Data Type</span></span></th>
<th><span data-ttu-id="85e63-108">Chave/índice</span><span class="sxs-lookup"><span data-stu-id="85e63-108">Key/Index</span></span></th>
<th><span data-ttu-id="85e63-109">Detalhes</span><span class="sxs-lookup"><span data-stu-id="85e63-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="85e63-110"><strong>Identificação_da_sessãotime</strong></span><span class="sxs-lookup"><span data-stu-id="85e63-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="85e63-111">datetime</span><span class="sxs-lookup"><span data-stu-id="85e63-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="85e63-112">Primário, Estrangeiro</span><span class="sxs-lookup"><span data-stu-id="85e63-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="85e63-113">Tempo da solicitação de sessão.</span><span class="sxs-lookup"><span data-stu-id="85e63-113">Time of session request.</span></span> <span data-ttu-id="85e63-114">Usado em conjunto com <strong>SessionIdSeq</strong> para identificar exclusivamente uma sessão.</span><span class="sxs-lookup"><span data-stu-id="85e63-114">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="85e63-115">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="85e63-115">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="85e63-116"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="85e63-116"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="85e63-117">int</span><span class="sxs-lookup"><span data-stu-id="85e63-117">int</span></span></p></td>
<td><p><span data-ttu-id="85e63-118">Primário, Estrangeiro</span><span class="sxs-lookup"><span data-stu-id="85e63-118">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="85e63-119">O número de ID para identificar a sessão.</span><span class="sxs-lookup"><span data-stu-id="85e63-119">ID number to identify the session.</span></span> <span data-ttu-id="85e63-120">Usado em conjunto com <strong>SessionIdTime</strong> para identificar exclusivamente uma sessão.</span><span class="sxs-lookup"><span data-stu-id="85e63-120">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="85e63-121">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="85e63-121">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="85e63-122"><strong>Location</strong></span><span class="sxs-lookup"><span data-stu-id="85e63-122"><strong>Location</strong></span></span></p></td>
<td><p><span data-ttu-id="85e63-123">nvarchar (máx.)</span><span class="sxs-lookup"><span data-stu-id="85e63-123">nvarchar(max)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="85e63-124">Local da chamada de emergência.</span><span class="sxs-lookup"><span data-stu-id="85e63-124">Location of emergency call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

