---
title: 'Lync Server 2013: tabela Locations'
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
ms.openlocfilehash: accab39d1f1f7cb1855ba651ea217aa3b0a4bd8d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42033350"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="locations-table-in-lync-server-2013"></a><span data-ttu-id="282da-102">Tabela Locations no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="282da-102">Locations table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="282da-103">_**Última modificação do tópico:** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="282da-103">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="282da-104">Cada registro representa uma referência de local em uma chamada de emergência, como uma chamada do tipo 9-1-1 Avançado.</span><span class="sxs-lookup"><span data-stu-id="282da-104">Each record represents one location reference in an emergency call, like an E9-1-1 call.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="282da-105">Coluna</span><span class="sxs-lookup"><span data-stu-id="282da-105">Column</span></span></th>
<th><span data-ttu-id="282da-106">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="282da-106">Data Type</span></span></th>
<th><span data-ttu-id="282da-107">Chave/índice</span><span class="sxs-lookup"><span data-stu-id="282da-107">Key/Index</span></span></th>
<th><span data-ttu-id="282da-108">Detalhes</span><span class="sxs-lookup"><span data-stu-id="282da-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="282da-109"><strong>Identificação_da_sessãotime</strong></span><span class="sxs-lookup"><span data-stu-id="282da-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="282da-110">datetime</span><span class="sxs-lookup"><span data-stu-id="282da-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="282da-111">Primária, Estrangeira</span><span class="sxs-lookup"><span data-stu-id="282da-111">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="282da-112">Tempo da solicitação de sessão.</span><span class="sxs-lookup"><span data-stu-id="282da-112">Time of session request.</span></span> <span data-ttu-id="282da-113">Usado em conjunto com <strong>SessionIdSeq</strong> para identificar exclusivamente uma sessão.</span><span class="sxs-lookup"><span data-stu-id="282da-113">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="282da-114">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="282da-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="282da-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="282da-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="282da-116">int</span><span class="sxs-lookup"><span data-stu-id="282da-116">int</span></span></p></td>
<td><p><span data-ttu-id="282da-117">Primário, Estrangeiro</span><span class="sxs-lookup"><span data-stu-id="282da-117">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="282da-118">O número de ID para identificar a sessão.</span><span class="sxs-lookup"><span data-stu-id="282da-118">ID number to identify the session.</span></span> <span data-ttu-id="282da-119">Usado em conjunto com <strong>SessionIdTime</strong> para identificar exclusivamente uma sessão.</span><span class="sxs-lookup"><span data-stu-id="282da-119">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="282da-120">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="282da-120">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="282da-121"><strong>Localização</strong></span><span class="sxs-lookup"><span data-stu-id="282da-121"><strong>Location</strong></span></span></p></td>
<td><p><span data-ttu-id="282da-122">nvarchar (máx.)</span><span class="sxs-lookup"><span data-stu-id="282da-122">nvarchar(max)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="282da-123">Local da chamada de emergência.</span><span class="sxs-lookup"><span data-stu-id="282da-123">Location of emergency call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

