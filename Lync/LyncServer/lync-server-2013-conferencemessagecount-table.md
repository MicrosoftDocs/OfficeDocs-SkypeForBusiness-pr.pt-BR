---
title: 'Lync Server 2013: tabela ConferenceMessageCount'
description: 'Lync Server 2013: tabela ConferenceMessageCount.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ConferenceMessageCount table
ms:assetid: 78569dbf-5217-42fa-ba1a-4380f56e2a3d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398590(v=OCS.15)
ms:contentKeyID: 48184570
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 271b654c09ab1aef194eb613e660de208aea1534
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561617"
---
# <a name="conferencemessagecount-table-in-lync-server-2013"></a><span data-ttu-id="a663d-103">Tabela ConferenceMessageCount no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a663d-103">ConferenceMessageCount table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a663d-104">_**Última modificação do tópico:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="a663d-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="a663d-105">Cada registro desta tabela representa um usuário em uma conferência de mensagens instantâneas e inclui o número de mensagens enviadas por esse usuário.</span><span class="sxs-lookup"><span data-stu-id="a663d-105">Each record in this table represents one user in one IM conference and includes the number of messages sent by that user.</span></span> <span data-ttu-id="a663d-106">Cada conferência é representada por vários registros nesta tabela; um registro para cada usuário.</span><span class="sxs-lookup"><span data-stu-id="a663d-106">Each conference is represented by multiple records in this table; one record for each user.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a663d-107">Coluna</span><span class="sxs-lookup"><span data-stu-id="a663d-107">Column</span></span></th>
<th><span data-ttu-id="a663d-108">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="a663d-108">Data Type</span></span></th>
<th><span data-ttu-id="a663d-109">Chave/índice</span><span class="sxs-lookup"><span data-stu-id="a663d-109">Key/Index</span></span></th>
<th><span data-ttu-id="a663d-110">Detalhes</span><span class="sxs-lookup"><span data-stu-id="a663d-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a663d-111"><strong>Identificação_da_sessãotime</strong></span><span class="sxs-lookup"><span data-stu-id="a663d-111"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="a663d-112">datetime</span><span class="sxs-lookup"><span data-stu-id="a663d-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="a663d-113">Primário, externo</span><span class="sxs-lookup"><span data-stu-id="a663d-113">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="a663d-114">Hora da instância da conferência.</span><span class="sxs-lookup"><span data-stu-id="a663d-114">Time of conference instance.</span></span> <span data-ttu-id="a663d-115">Usado em conjunto com o <strong>SessionIdSeq</strong> para identificar exclusivamente uma instância de conferência.</span><span class="sxs-lookup"><span data-stu-id="a663d-115">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="a663d-116">Consulte a <a href="lync-server-2013-conferences-table.md">tabela conferências no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="a663d-116">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a663d-117"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="a663d-117"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="a663d-118">int</span><span class="sxs-lookup"><span data-stu-id="a663d-118">int</span></span></p></td>
<td><p><span data-ttu-id="a663d-119">Primário, externo</span><span class="sxs-lookup"><span data-stu-id="a663d-119">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="a663d-120">Número de ID para identificar a instância da conferência.</span><span class="sxs-lookup"><span data-stu-id="a663d-120">ID number to identify the conference instance.</span></span> <span data-ttu-id="a663d-121">Usado em conjunto com a <strong>identificação_da_sessãotime</strong> para identificar exclusivamente uma instância de conferência.</span><span class="sxs-lookup"><span data-stu-id="a663d-121">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="a663d-122">Consulte a <a href="lync-server-2013-conferences-table.md">tabela conferências no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="a663d-122">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a663d-123"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="a663d-123"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="a663d-124">int</span><span class="sxs-lookup"><span data-stu-id="a663d-124">int</span></span></p></td>
<td><p><span data-ttu-id="a663d-125">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="a663d-125">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a663d-126">Número exclusivo que identifica esse usuário, referenciado pela <a href="lync-server-2013-users-table.md">tabela Users no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="a663d-126">Unique number identifying this user, referenced from the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a663d-127"><strong>MessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="a663d-127"><strong>MessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="a663d-128">smallint</span><span class="sxs-lookup"><span data-stu-id="a663d-128">smallint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a663d-129">O número de mensagens enviadas por esse usuário durante esta conferência.</span><span class="sxs-lookup"><span data-stu-id="a663d-129">The number of messages sent by this user during this conference.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

