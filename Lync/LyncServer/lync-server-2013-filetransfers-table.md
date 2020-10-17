---
title: 'Lync Server 2013: tabela de transferência de filetransfers'
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
ms.openlocfilehash: cacd637caec827a87008c3a6554750b7e5b61719
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48500918"
---
# <a name="filetransfers-table-in-lync-server-2013"></a><span data-ttu-id="14866-102">Tabela filetransfers no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="14866-102">FileTransfers table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="14866-103">_**Última modificação do tópico:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="14866-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="14866-104">Cada registro representa uma sessão de transferência de arquivos.</span><span class="sxs-lookup"><span data-stu-id="14866-104">Each record represents one file transfer session.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="14866-105">Coluna</span><span class="sxs-lookup"><span data-stu-id="14866-105">Column</span></span></th>
<th><span data-ttu-id="14866-106">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="14866-106">Data Type</span></span></th>
<th><span data-ttu-id="14866-107">Chave/índice</span><span class="sxs-lookup"><span data-stu-id="14866-107">Key/Index</span></span></th>
<th><span data-ttu-id="14866-108">Detalhes</span><span class="sxs-lookup"><span data-stu-id="14866-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="14866-109"><strong>Identificação_da_sessãotime</strong></span><span class="sxs-lookup"><span data-stu-id="14866-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="14866-110">datetime</span><span class="sxs-lookup"><span data-stu-id="14866-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="14866-111">Primário, Estrangeiro</span><span class="sxs-lookup"><span data-stu-id="14866-111">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="14866-112">Tempo da solicitação de sessão.</span><span class="sxs-lookup"><span data-stu-id="14866-112">Time of session request.</span></span> <span data-ttu-id="14866-113">Usado em conjunto com <strong>SessionIdSeq</strong> para identificar exclusivamente uma sessão.</span><span class="sxs-lookup"><span data-stu-id="14866-113">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="14866-114">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="14866-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14866-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="14866-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="14866-116">int</span><span class="sxs-lookup"><span data-stu-id="14866-116">int</span></span></p></td>
<td><p><span data-ttu-id="14866-117">Primário, Estrangeiro</span><span class="sxs-lookup"><span data-stu-id="14866-117">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="14866-118">O número de ID para identificar a sessão.</span><span class="sxs-lookup"><span data-stu-id="14866-118">ID number to identify the session.</span></span> <span data-ttu-id="14866-119">Usado em conjunto com <strong>SessionIdTime</strong> para identificar exclusivamente uma sessão.</span><span class="sxs-lookup"><span data-stu-id="14866-119">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="14866-120">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="14866-120">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14866-121"><strong>Nome do arquivo</strong></span><span class="sxs-lookup"><span data-stu-id="14866-121"><strong>File Name</strong></span></span></p></td>
<td><p><span data-ttu-id="14866-122">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="14866-122">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="14866-123">Nome do arquivo.</span><span class="sxs-lookup"><span data-stu-id="14866-123">Name of the file.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14866-124"><strong>Fileidentity</strong></span><span class="sxs-lookup"><span data-stu-id="14866-124"><strong>FileIdentity</strong></span></span></p></td>
<td><p><span data-ttu-id="14866-125">identificador</span><span class="sxs-lookup"><span data-stu-id="14866-125">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="14866-126">Identificador exclusivo para distinguir entre as transferências de arquivo envolvendo o mesmo nome do arquivo.</span><span class="sxs-lookup"><span data-stu-id="14866-126">Unique identifier to distinguish between file transfers involving the same file name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14866-127"><strong>Cookie</strong></span><span class="sxs-lookup"><span data-stu-id="14866-127"><strong>Cookie</strong></span></span></p></td>
<td><p><span data-ttu-id="14866-128">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="14866-128">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="14866-129">Primário</span><span class="sxs-lookup"><span data-stu-id="14866-129">Primary</span></span></p></td>
<td><p><span data-ttu-id="14866-130">Usado para identificar cada mensagem de acompanhamento como sendo associado a este.</span><span class="sxs-lookup"><span data-stu-id="14866-130">Used to identify every follow-up message as being associated with this one.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14866-131"><strong>Accept</strong></span><span class="sxs-lookup"><span data-stu-id="14866-131"><strong>Accept</strong></span></span></p></td>
<td><p><span data-ttu-id="14866-132">bits</span><span class="sxs-lookup"><span data-stu-id="14866-132">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="14866-p103">Pode ser TRUE ou NULL. Se for TRUE, Rejeitar e Cancelar serão NULL.</span><span class="sxs-lookup"><span data-stu-id="14866-p103">Can be TRUE or NULL. If TRUE, then Reject and Cancel will be NULL.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14866-135"><strong>Reject</strong></span><span class="sxs-lookup"><span data-stu-id="14866-135"><strong>Reject</strong></span></span></p></td>
<td><p><span data-ttu-id="14866-136">bits</span><span class="sxs-lookup"><span data-stu-id="14866-136">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="14866-p104">Pode ser TRUE ou NULL. Se for TRUE, Aceitar e Cancelar serão NULL.</span><span class="sxs-lookup"><span data-stu-id="14866-p104">Can be TRUE or NULL. If TRUE, then Accept and Cancel will be NULL.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14866-139"><strong>Cancel</strong></span><span class="sxs-lookup"><span data-stu-id="14866-139"><strong>Cancel</strong></span></span></p></td>
<td><p><span data-ttu-id="14866-140">bits</span><span class="sxs-lookup"><span data-stu-id="14866-140">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="14866-p105">Pode ser TRUE ou NULL. Se for TRUE, Aceitar e Rejeitar serão NULL.</span><span class="sxs-lookup"><span data-stu-id="14866-p105">Can be TRUE or NULL. If TRUE, then Accept and Reject will be NULL.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

