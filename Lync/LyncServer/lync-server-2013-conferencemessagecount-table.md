---
title: 'Lync Server 2013: Tabela ConferenceMessageCount'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: ConferenceMessageCount table
ms:assetid: 78569dbf-5217-42fa-ba1a-4380f56e2a3d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398590(v=OCS.15)
ms:contentKeyID: 48184570
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0d2994f02bf087ef55edff6b2153e7504f881b03
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836483"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencemessagecount-table-in-lync-server-2013"></a><span data-ttu-id="fd3e0-102">Tabela ConferenceMessageCount no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fd3e0-102">ConferenceMessageCount table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fd3e0-103">_**Tópico da última modificação:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="fd3e0-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="fd3e0-104">Cada registro nessa tabela representa um usuário em uma conferência de mensagem instantânea e inclui o número de mensagens enviadas por esse usuário.</span><span class="sxs-lookup"><span data-stu-id="fd3e0-104">Each record in this table represents one user in one IM conference and includes the number of messages sent by that user.</span></span> <span data-ttu-id="fd3e0-105">Cada conferência é representada por vários registros nesta tabela; um registro para cada usuário.</span><span class="sxs-lookup"><span data-stu-id="fd3e0-105">Each conference is represented by multiple records in this table; one record for each user.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fd3e0-106">Coluna</span><span class="sxs-lookup"><span data-stu-id="fd3e0-106">Column</span></span></th>
<th><span data-ttu-id="fd3e0-107">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="fd3e0-107">Data Type</span></span></th>
<th><span data-ttu-id="fd3e0-108">Chave/índice</span><span class="sxs-lookup"><span data-stu-id="fd3e0-108">Key/Index</span></span></th>
<th><span data-ttu-id="fd3e0-109">Detalhes</span><span class="sxs-lookup"><span data-stu-id="fd3e0-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fd3e0-110"><strong>Id_da_sessãotime</strong></span><span class="sxs-lookup"><span data-stu-id="fd3e0-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="fd3e0-111">datetime</span><span class="sxs-lookup"><span data-stu-id="fd3e0-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="fd3e0-112">Primário, estrangeiro</span><span class="sxs-lookup"><span data-stu-id="fd3e0-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="fd3e0-113">Hora da ocorrência da conferência.</span><span class="sxs-lookup"><span data-stu-id="fd3e0-113">Time of conference instance.</span></span> <span data-ttu-id="fd3e0-114">Usado em conjunto com <strong>SessionIdSeq</strong> para identificar uma instância de conferência de maneira exclusiva.</span><span class="sxs-lookup"><span data-stu-id="fd3e0-114">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="fd3e0-115">Consulte a <a href="lync-server-2013-conferences-table.md">tabela conferências no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="fd3e0-115">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd3e0-116"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="fd3e0-116"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="fd3e0-117">int</span><span class="sxs-lookup"><span data-stu-id="fd3e0-117">int</span></span></p></td>
<td><p><span data-ttu-id="fd3e0-118">Primário, estrangeiro</span><span class="sxs-lookup"><span data-stu-id="fd3e0-118">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="fd3e0-119">Número de identificação para identificar a instância de conferência.</span><span class="sxs-lookup"><span data-stu-id="fd3e0-119">ID number to identify the conference instance.</span></span> <span data-ttu-id="fd3e0-120">Usado em conjunto com <strong></strong> a identificação_da_sessãotime para identificar exclusivamente uma instância de conferência.</span><span class="sxs-lookup"><span data-stu-id="fd3e0-120">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="fd3e0-121">Consulte a <a href="lync-server-2013-conferences-table.md">tabela conferências no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="fd3e0-121">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd3e0-122"><strong>ID</strong></span><span class="sxs-lookup"><span data-stu-id="fd3e0-122"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="fd3e0-123">int</span><span class="sxs-lookup"><span data-stu-id="fd3e0-123">int</span></span></p></td>
<td><p><span data-ttu-id="fd3e0-124">Exterior</span><span class="sxs-lookup"><span data-stu-id="fd3e0-124">Foreign</span></span></p></td>
<td><p><span data-ttu-id="fd3e0-125">Número exclusivo que identifica esse usuário, referenciado pela <a href="lync-server-2013-users-table.md">tabela usuários no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="fd3e0-125">Unique number identifying this user, referenced from the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd3e0-126"><strong>MessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="fd3e0-126"><strong>MessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="fd3e0-127">smallint</span><span class="sxs-lookup"><span data-stu-id="fd3e0-127">smallint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fd3e0-128">O número de mensagens enviadas por este usuário durante esta conferência.</span><span class="sxs-lookup"><span data-stu-id="fd3e0-128">The number of messages sent by this user during this conference.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

