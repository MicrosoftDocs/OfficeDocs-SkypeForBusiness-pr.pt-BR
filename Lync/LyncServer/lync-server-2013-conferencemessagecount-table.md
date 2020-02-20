---
title: 'Lync Server 2013: tabela ConferenceMessageCount'
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
ms.openlocfilehash: e862209d384cd3927b6f8136b1a0d04b378e00c2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145129"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="conferencemessagecount-table-in-lync-server-2013"></a><span data-ttu-id="f12d3-102">Tabela ConferenceMessageCount no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f12d3-102">ConferenceMessageCount table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f12d3-103">_**Última modificação do tópico:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="f12d3-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="f12d3-104">Cada registro desta tabela representa um usuário em uma conferência de mensagens instantâneas e inclui o número de mensagens enviadas por esse usuário.</span><span class="sxs-lookup"><span data-stu-id="f12d3-104">Each record in this table represents one user in one IM conference and includes the number of messages sent by that user.</span></span> <span data-ttu-id="f12d3-105">Cada conferência é representada por vários registros nesta tabela; um registro para cada usuário.</span><span class="sxs-lookup"><span data-stu-id="f12d3-105">Each conference is represented by multiple records in this table; one record for each user.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f12d3-106">Coluna</span><span class="sxs-lookup"><span data-stu-id="f12d3-106">Column</span></span></th>
<th><span data-ttu-id="f12d3-107">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="f12d3-107">Data Type</span></span></th>
<th><span data-ttu-id="f12d3-108">Chave/índice</span><span class="sxs-lookup"><span data-stu-id="f12d3-108">Key/Index</span></span></th>
<th><span data-ttu-id="f12d3-109">Detalhes</span><span class="sxs-lookup"><span data-stu-id="f12d3-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f12d3-110"><strong>Identificação_da_sessãotime</strong></span><span class="sxs-lookup"><span data-stu-id="f12d3-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="f12d3-111">datetime</span><span class="sxs-lookup"><span data-stu-id="f12d3-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="f12d3-112">Primária, estrangeira</span><span class="sxs-lookup"><span data-stu-id="f12d3-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="f12d3-113">Hora da instância da conferência.</span><span class="sxs-lookup"><span data-stu-id="f12d3-113">Time of conference instance.</span></span> <span data-ttu-id="f12d3-114">Usado em conjunto com o <strong>SessionIdSeq</strong> para identificar exclusivamente uma instância de conferência.</span><span class="sxs-lookup"><span data-stu-id="f12d3-114">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="f12d3-115">Consulte a <a href="lync-server-2013-conferences-table.md">tabela conferências no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="f12d3-115">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f12d3-116"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="f12d3-116"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="f12d3-117">int</span><span class="sxs-lookup"><span data-stu-id="f12d3-117">int</span></span></p></td>
<td><p><span data-ttu-id="f12d3-118">Primário, externo</span><span class="sxs-lookup"><span data-stu-id="f12d3-118">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="f12d3-119">Número de ID para identificar a instância da conferência.</span><span class="sxs-lookup"><span data-stu-id="f12d3-119">ID number to identify the conference instance.</span></span> <span data-ttu-id="f12d3-120">Usado em conjunto com a <strong>identificação_da_sessãotime</strong> para identificar exclusivamente uma instância de conferência.</span><span class="sxs-lookup"><span data-stu-id="f12d3-120">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="f12d3-121">Consulte a <a href="lync-server-2013-conferences-table.md">tabela conferências no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="f12d3-121">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f12d3-122"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="f12d3-122"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="f12d3-123">int</span><span class="sxs-lookup"><span data-stu-id="f12d3-123">int</span></span></p></td>
<td><p><span data-ttu-id="f12d3-124">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="f12d3-124">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f12d3-125">Número exclusivo que identifica esse usuário, referenciado pela <a href="lync-server-2013-users-table.md">tabela Users no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="f12d3-125">Unique number identifying this user, referenced from the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f12d3-126"><strong>MessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="f12d3-126"><strong>MessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="f12d3-127">smallint</span><span class="sxs-lookup"><span data-stu-id="f12d3-127">smallint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f12d3-128">O número de mensagens enviadas por esse usuário durante esta conferência.</span><span class="sxs-lookup"><span data-stu-id="f12d3-128">The number of messages sent by this user during this conference.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

