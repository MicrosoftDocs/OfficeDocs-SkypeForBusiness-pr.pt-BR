---
title: 'Lync Server 2013: Tabela FileTransfers'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: FileTransfers table
ms:assetid: 5368e67c-d8a9-43a1-9472-a839950dedb3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398353(v=OCS.15)
ms:contentKeyID: 48184118
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 71e53e59e3ed1391adebff8b7c4046ef3c23aa21
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829151"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="filetransfers-table-in-lync-server-2013"></a><span data-ttu-id="f9e2a-102">Tabela FileTransfers no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f9e2a-102">FileTransfers table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f9e2a-103">_**Tópico da última modificação:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="f9e2a-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="f9e2a-104">Cada registro representa uma sessão de transferência de arquivo.</span><span class="sxs-lookup"><span data-stu-id="f9e2a-104">Each record represents one file transfer session.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f9e2a-105">Coluna</span><span class="sxs-lookup"><span data-stu-id="f9e2a-105">Column</span></span></th>
<th><span data-ttu-id="f9e2a-106">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="f9e2a-106">Data Type</span></span></th>
<th><span data-ttu-id="f9e2a-107">Chave/índice</span><span class="sxs-lookup"><span data-stu-id="f9e2a-107">Key/Index</span></span></th>
<th><span data-ttu-id="f9e2a-108">Detalhes</span><span class="sxs-lookup"><span data-stu-id="f9e2a-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f9e2a-109"><strong>Id_da_sessãotime</strong></span><span class="sxs-lookup"><span data-stu-id="f9e2a-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="f9e2a-110">datetime</span><span class="sxs-lookup"><span data-stu-id="f9e2a-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="f9e2a-111">Primário, estrangeiro</span><span class="sxs-lookup"><span data-stu-id="f9e2a-111">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="f9e2a-112">Tempo de solicitação de sessão.</span><span class="sxs-lookup"><span data-stu-id="f9e2a-112">Time of session request.</span></span> <span data-ttu-id="f9e2a-113">Usado em conjunto com o <strong>SessionIdSeq</strong> para identificar exclusivamente uma sessão.</span><span class="sxs-lookup"><span data-stu-id="f9e2a-113">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="f9e2a-114">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela de diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="f9e2a-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f9e2a-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="f9e2a-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="f9e2a-116">int</span><span class="sxs-lookup"><span data-stu-id="f9e2a-116">int</span></span></p></td>
<td><p><span data-ttu-id="f9e2a-117">Primário, estrangeiro</span><span class="sxs-lookup"><span data-stu-id="f9e2a-117">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="f9e2a-118">Número de identificação para identificar a sessão.</span><span class="sxs-lookup"><span data-stu-id="f9e2a-118">ID number to identify the session.</span></span> <span data-ttu-id="f9e2a-119">Usado em conjunto com <strong></strong> a identificação_da_sessãotime para identificar exclusivamente uma sessão.</span><span class="sxs-lookup"><span data-stu-id="f9e2a-119">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="f9e2a-120">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela de diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="f9e2a-120">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f9e2a-121"><strong>Nome do arquivo</strong></span><span class="sxs-lookup"><span data-stu-id="f9e2a-121"><strong>File Name</strong></span></span></p></td>
<td><p><span data-ttu-id="f9e2a-122">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="f9e2a-122">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f9e2a-123">Nome do arquivo.</span><span class="sxs-lookup"><span data-stu-id="f9e2a-123">Name of the file.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f9e2a-124"><strong>Fileidentity</strong></span><span class="sxs-lookup"><span data-stu-id="f9e2a-124"><strong>FileIdentity</strong></span></span></p></td>
<td><p><span data-ttu-id="f9e2a-125">identificador</span><span class="sxs-lookup"><span data-stu-id="f9e2a-125">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f9e2a-126">Identificador exclusivo para distinguir entre as transferências de arquivo que envolvem o mesmo nome de arquivo.</span><span class="sxs-lookup"><span data-stu-id="f9e2a-126">Unique identifier to distinguish between file transfers involving the same file name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f9e2a-127"><strong>Cookie</strong></span><span class="sxs-lookup"><span data-stu-id="f9e2a-127"><strong>Cookie</strong></span></span></p></td>
<td><p><span data-ttu-id="f9e2a-128">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="f9e2a-128">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="f9e2a-129">Primária</span><span class="sxs-lookup"><span data-stu-id="f9e2a-129">Primary</span></span></p></td>
<td><p><span data-ttu-id="f9e2a-130">Usado para identificar todas as mensagens de acompanhamento como associadas a esta.</span><span class="sxs-lookup"><span data-stu-id="f9e2a-130">Used to identify every follow-up message as being associated with this one.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f9e2a-131"><strong>Aceite</strong></span><span class="sxs-lookup"><span data-stu-id="f9e2a-131"><strong>Accept</strong></span></span></p></td>
<td><p><span data-ttu-id="f9e2a-132">bit</span><span class="sxs-lookup"><span data-stu-id="f9e2a-132">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f9e2a-133">Pode ser TRUE ou NULL.</span><span class="sxs-lookup"><span data-stu-id="f9e2a-133">Can be TRUE or NULL.</span></span> <span data-ttu-id="f9e2a-134">Se verdadeiro, rejeitar e cancelar será nulo.</span><span class="sxs-lookup"><span data-stu-id="f9e2a-134">If TRUE, then Reject and Cancel will be NULL.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f9e2a-135"><strong>Rejeitar</strong></span><span class="sxs-lookup"><span data-stu-id="f9e2a-135"><strong>Reject</strong></span></span></p></td>
<td><p><span data-ttu-id="f9e2a-136">bit</span><span class="sxs-lookup"><span data-stu-id="f9e2a-136">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f9e2a-137">Pode ser TRUE ou NULL.</span><span class="sxs-lookup"><span data-stu-id="f9e2a-137">Can be TRUE or NULL.</span></span> <span data-ttu-id="f9e2a-138">Se verdadeiro, aceitar e cancelar será nulo.</span><span class="sxs-lookup"><span data-stu-id="f9e2a-138">If TRUE, then Accept and Cancel will be NULL.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f9e2a-139"><strong>Cancelar</strong></span><span class="sxs-lookup"><span data-stu-id="f9e2a-139"><strong>Cancel</strong></span></span></p></td>
<td><p><span data-ttu-id="f9e2a-140">bit</span><span class="sxs-lookup"><span data-stu-id="f9e2a-140">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f9e2a-141">Pode ser TRUE ou NULL.</span><span class="sxs-lookup"><span data-stu-id="f9e2a-141">Can be TRUE or NULL.</span></span> <span data-ttu-id="f9e2a-142">Se verdadeiro, aceitar e rejeitar será nulo.</span><span class="sxs-lookup"><span data-stu-id="f9e2a-142">If TRUE, then Accept and Reject will be NULL.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

