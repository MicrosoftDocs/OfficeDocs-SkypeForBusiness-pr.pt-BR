---
title: 'Lync Server 2013: tabela de transferência de filetransfers'
description: 'Lync Server 2013: tabela filetransfers.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: FileTransfers table
ms:assetid: 5368e67c-d8a9-43a1-9472-a839950dedb3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398353(v=OCS.15)
ms:contentKeyID: 48184118
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ccde45fa3743a809499273676d567846ef292ecc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573357"
---
# <a name="filetransfers-table-in-lync-server-2013"></a><span data-ttu-id="e3011-103">Tabela filetransfers no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e3011-103">FileTransfers table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e3011-104">_**Última modificação do tópico:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="e3011-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="e3011-105">Cada registro representa uma sessão de transferência de arquivos.</span><span class="sxs-lookup"><span data-stu-id="e3011-105">Each record represents one file transfer session.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e3011-106">Coluna</span><span class="sxs-lookup"><span data-stu-id="e3011-106">Column</span></span></th>
<th><span data-ttu-id="e3011-107">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="e3011-107">Data Type</span></span></th>
<th><span data-ttu-id="e3011-108">Chave/índice</span><span class="sxs-lookup"><span data-stu-id="e3011-108">Key/Index</span></span></th>
<th><span data-ttu-id="e3011-109">Detalhes</span><span class="sxs-lookup"><span data-stu-id="e3011-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e3011-110"><strong>Identificação_da_sessãotime</strong></span><span class="sxs-lookup"><span data-stu-id="e3011-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e3011-111">datetime</span><span class="sxs-lookup"><span data-stu-id="e3011-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="e3011-112">Primário, Estrangeiro</span><span class="sxs-lookup"><span data-stu-id="e3011-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="e3011-113">Tempo da solicitação de sessão.</span><span class="sxs-lookup"><span data-stu-id="e3011-113">Time of session request.</span></span> <span data-ttu-id="e3011-114">Usado em conjunto com <strong>SessionIdSeq</strong> para identificar exclusivamente uma sessão.</span><span class="sxs-lookup"><span data-stu-id="e3011-114">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="e3011-115">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="e3011-115">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3011-116"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="e3011-116"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="e3011-117">int</span><span class="sxs-lookup"><span data-stu-id="e3011-117">int</span></span></p></td>
<td><p><span data-ttu-id="e3011-118">Primário, Estrangeiro</span><span class="sxs-lookup"><span data-stu-id="e3011-118">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="e3011-119">O número de ID para identificar a sessão.</span><span class="sxs-lookup"><span data-stu-id="e3011-119">ID number to identify the session.</span></span> <span data-ttu-id="e3011-120">Usado em conjunto com <strong>SessionIdTime</strong> para identificar exclusivamente uma sessão.</span><span class="sxs-lookup"><span data-stu-id="e3011-120">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="e3011-121">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="e3011-121">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3011-122"><strong>Nome do arquivo</strong></span><span class="sxs-lookup"><span data-stu-id="e3011-122"><strong>File Name</strong></span></span></p></td>
<td><p><span data-ttu-id="e3011-123">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="e3011-123">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e3011-124">Nome do arquivo.</span><span class="sxs-lookup"><span data-stu-id="e3011-124">Name of the file.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3011-125"><strong>Fileidentity</strong></span><span class="sxs-lookup"><span data-stu-id="e3011-125"><strong>FileIdentity</strong></span></span></p></td>
<td><p><span data-ttu-id="e3011-126">identificador</span><span class="sxs-lookup"><span data-stu-id="e3011-126">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e3011-127">Identificador exclusivo para distinguir entre as transferências de arquivo envolvendo o mesmo nome do arquivo.</span><span class="sxs-lookup"><span data-stu-id="e3011-127">Unique identifier to distinguish between file transfers involving the same file name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3011-128"><strong>Cookie</strong></span><span class="sxs-lookup"><span data-stu-id="e3011-128"><strong>Cookie</strong></span></span></p></td>
<td><p><span data-ttu-id="e3011-129">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="e3011-129">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="e3011-130">Primário</span><span class="sxs-lookup"><span data-stu-id="e3011-130">Primary</span></span></p></td>
<td><p><span data-ttu-id="e3011-131">Usado para identificar cada mensagem de acompanhamento como sendo associado a este.</span><span class="sxs-lookup"><span data-stu-id="e3011-131">Used to identify every follow-up message as being associated with this one.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3011-132"><strong>Accept</strong></span><span class="sxs-lookup"><span data-stu-id="e3011-132"><strong>Accept</strong></span></span></p></td>
<td><p><span data-ttu-id="e3011-133">bits</span><span class="sxs-lookup"><span data-stu-id="e3011-133">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e3011-p103">Pode ser TRUE ou NULL. Se for TRUE, Rejeitar e Cancelar serão NULL.</span><span class="sxs-lookup"><span data-stu-id="e3011-p103">Can be TRUE or NULL. If TRUE, then Reject and Cancel will be NULL.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3011-136"><strong>Reject</strong></span><span class="sxs-lookup"><span data-stu-id="e3011-136"><strong>Reject</strong></span></span></p></td>
<td><p><span data-ttu-id="e3011-137">bits</span><span class="sxs-lookup"><span data-stu-id="e3011-137">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e3011-p104">Pode ser TRUE ou NULL. Se for TRUE, Aceitar e Cancelar serão NULL.</span><span class="sxs-lookup"><span data-stu-id="e3011-p104">Can be TRUE or NULL. If TRUE, then Accept and Cancel will be NULL.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3011-140"><strong>Cancel</strong></span><span class="sxs-lookup"><span data-stu-id="e3011-140"><strong>Cancel</strong></span></span></p></td>
<td><p><span data-ttu-id="e3011-141">bits</span><span class="sxs-lookup"><span data-stu-id="e3011-141">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e3011-p105">Pode ser TRUE ou NULL. Se for TRUE, Aceitar e Rejeitar serão NULL.</span><span class="sxs-lookup"><span data-stu-id="e3011-p105">Can be TRUE or NULL. If TRUE, then Accept and Reject will be NULL.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

