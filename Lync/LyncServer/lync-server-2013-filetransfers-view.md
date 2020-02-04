---
title: 'Lync Server 2013: modo de exibição de transferência de fileviews'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: FileTransfers view
ms:assetid: e52c3ad0-152e-4a18-af1c-1aff0d205151
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721914(v=OCS.15)
ms:contentKeyID: 49733848
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fc4469140f7f92c563a594c883d02f3add1e65c5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743371"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="filetransfers-view-in-lync-server-2013"></a><span data-ttu-id="e2322-102">Modo de exibição de transferência de fileviews no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e2322-102">FileTransfers view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e2322-103">_**Tópico da última modificação:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="e2322-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="e2322-104">O modo de transferência de arquivo armazena informações sobre sessões de transferência de arquivos ponto a ponto.</span><span class="sxs-lookup"><span data-stu-id="e2322-104">The FileTransfer view stores information about peer-to-peer file transfer sessions.</span></span> <span data-ttu-id="e2322-105">Este modo de exibição foi apresentado no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e2322-105">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e2322-106">O modo de exibição filetransfers contém todas as colunas na <A href="lync-server-2013-sessiondetails-view.md">exibição SessionDetails no Lync Server 2013</A> , além das colunas listadas abaixo.</span><span class="sxs-lookup"><span data-stu-id="e2322-106">The FileTransfers view contains all of the columns in the <A href="lync-server-2013-sessiondetails-view.md">SessionDetails view in Lync Server 2013</A> in addition the columns listed below.</span></span>



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e2322-107">Coluna</span><span class="sxs-lookup"><span data-stu-id="e2322-107">Column</span></span></th>
<th><span data-ttu-id="e2322-108">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="e2322-108">Data Type</span></span></th>
<th><span data-ttu-id="e2322-109">Detalhes</span><span class="sxs-lookup"><span data-stu-id="e2322-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e2322-110"><strong>FileName</strong></span><span class="sxs-lookup"><span data-stu-id="e2322-110"><strong>FileName</strong></span></span></p></td>
<td><p><span data-ttu-id="e2322-111">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e2322-111">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e2322-112">Nome do arquivo transferido.</span><span class="sxs-lookup"><span data-stu-id="e2322-112">Name of the file transferred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2322-113"><strong>Cookie</strong></span><span class="sxs-lookup"><span data-stu-id="e2322-113"><strong>Cookie</strong></span></span></p></td>
<td><p><span data-ttu-id="e2322-114">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="e2322-114">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="e2322-115">Usado para identificar todas as mensagens de acompanhamento como associadas a esta.</span><span class="sxs-lookup"><span data-stu-id="e2322-115">Used to identify every follow-up message as being associated with this one.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2322-116"><strong>Fileidentity</strong></span><span class="sxs-lookup"><span data-stu-id="e2322-116"><strong>FileIdentity</strong></span></span></p></td>
<td><p><span data-ttu-id="e2322-117">identificador</span><span class="sxs-lookup"><span data-stu-id="e2322-117">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="e2322-118">Identificador exclusivo para distinguir entre as transferências de arquivo que envolvem o mesmo nome de arquivo.</span><span class="sxs-lookup"><span data-stu-id="e2322-118">Unique identifier to distinguish between file transfers involving the same file name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2322-119"><strong>Aceite</strong></span><span class="sxs-lookup"><span data-stu-id="e2322-119"><strong>Accept</strong></span></span></p></td>
<td><p><span data-ttu-id="e2322-120">bit</span><span class="sxs-lookup"><span data-stu-id="e2322-120">bit</span></span></p></td>
<td><p><span data-ttu-id="e2322-121">Pode ser TRUE ou NULL.</span><span class="sxs-lookup"><span data-stu-id="e2322-121">Can be TRUE or NULL.</span></span> <span data-ttu-id="e2322-122">Se verdadeiro, rejeitar e cancelar será nulo.</span><span class="sxs-lookup"><span data-stu-id="e2322-122">If TRUE, then Reject and Cancel will be NULL.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2322-123"><strong>Rejeitar</strong></span><span class="sxs-lookup"><span data-stu-id="e2322-123"><strong>Reject</strong></span></span></p></td>
<td><p><span data-ttu-id="e2322-124">bit</span><span class="sxs-lookup"><span data-stu-id="e2322-124">bit</span></span></p></td>
<td><p><span data-ttu-id="e2322-125">Pode ser TRUE ou NULL.</span><span class="sxs-lookup"><span data-stu-id="e2322-125">Can be TRUE or NULL.</span></span> <span data-ttu-id="e2322-126">Se verdadeiro, aceitar e cancelar será nulo.</span><span class="sxs-lookup"><span data-stu-id="e2322-126">If TRUE, then Accept and Cancel will be NULL.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2322-127"><strong>Cancelar</strong></span><span class="sxs-lookup"><span data-stu-id="e2322-127"><strong>Cancel</strong></span></span></p></td>
<td><p><span data-ttu-id="e2322-128">bit</span><span class="sxs-lookup"><span data-stu-id="e2322-128">bit</span></span></p></td>
<td><p><span data-ttu-id="e2322-129">Pode ser TRUE ou NULL.</span><span class="sxs-lookup"><span data-stu-id="e2322-129">Can be TRUE or NULL.</span></span> <span data-ttu-id="e2322-130">Se verdadeiro, aceitar e rejeitar será nulo.</span><span class="sxs-lookup"><span data-stu-id="e2322-130">If TRUE, then Accept and Reject will be NULL.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

