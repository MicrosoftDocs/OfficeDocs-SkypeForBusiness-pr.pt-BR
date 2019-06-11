---
title: 'Lync Server 2013: modo de exibição de transferência de fileviews'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: FileTransfers view
ms:assetid: e52c3ad0-152e-4a18-af1c-1aff0d205151
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721914(v=OCS.15)
ms:contentKeyID: 49733848
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4228bbe42f2e7bcf88b26f9147e514f09c106ac3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829153"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="filetransfers-view-in-lync-server-2013"></a><span data-ttu-id="51dbc-102">Modo de exibição de transferência de fileviews no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="51dbc-102">FileTransfers view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="51dbc-103">_**Tópico da última modificação:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="51dbc-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="51dbc-104">O modo de transferência de arquivo armazena informações sobre sessões de transferência de arquivos ponto a ponto.</span><span class="sxs-lookup"><span data-stu-id="51dbc-104">The FileTransfer view stores information about peer-to-peer file transfer sessions.</span></span> <span data-ttu-id="51dbc-105">Este modo de exibição foi apresentado no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="51dbc-105">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="51dbc-106">O modo de exibição filetransfers contém todas as colunas na <A href="lync-server-2013-sessiondetails-view.md">exibição SessionDetails no Lync Server 2013</A> , além das colunas listadas abaixo.</span><span class="sxs-lookup"><span data-stu-id="51dbc-106">The FileTransfers view contains all of the columns in the <A href="lync-server-2013-sessiondetails-view.md">SessionDetails view in Lync Server 2013</A> in addition the columns listed below.</span></span>



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="51dbc-107">Coluna</span><span class="sxs-lookup"><span data-stu-id="51dbc-107">Column</span></span></th>
<th><span data-ttu-id="51dbc-108">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="51dbc-108">Data Type</span></span></th>
<th><span data-ttu-id="51dbc-109">Detalhes</span><span class="sxs-lookup"><span data-stu-id="51dbc-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="51dbc-110"><strong>FileName</strong></span><span class="sxs-lookup"><span data-stu-id="51dbc-110"><strong>FileName</strong></span></span></p></td>
<td><p><span data-ttu-id="51dbc-111">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="51dbc-111">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="51dbc-112">Nome do arquivo transferido.</span><span class="sxs-lookup"><span data-stu-id="51dbc-112">Name of the file transferred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51dbc-113"><strong>Cookie</strong></span><span class="sxs-lookup"><span data-stu-id="51dbc-113"><strong>Cookie</strong></span></span></p></td>
<td><p><span data-ttu-id="51dbc-114">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="51dbc-114">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="51dbc-115">Usado para identificar todas as mensagens de acompanhamento como associadas a esta.</span><span class="sxs-lookup"><span data-stu-id="51dbc-115">Used to identify every follow-up message as being associated with this one.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51dbc-116"><strong>Fileidentity</strong></span><span class="sxs-lookup"><span data-stu-id="51dbc-116"><strong>FileIdentity</strong></span></span></p></td>
<td><p><span data-ttu-id="51dbc-117">identificador</span><span class="sxs-lookup"><span data-stu-id="51dbc-117">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="51dbc-118">Identificador exclusivo para distinguir entre as transferências de arquivo que envolvem o mesmo nome de arquivo.</span><span class="sxs-lookup"><span data-stu-id="51dbc-118">Unique identifier to distinguish between file transfers involving the same file name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51dbc-119"><strong>Aceite</strong></span><span class="sxs-lookup"><span data-stu-id="51dbc-119"><strong>Accept</strong></span></span></p></td>
<td><p><span data-ttu-id="51dbc-120">bit</span><span class="sxs-lookup"><span data-stu-id="51dbc-120">bit</span></span></p></td>
<td><p><span data-ttu-id="51dbc-121">Pode ser TRUE ou NULL.</span><span class="sxs-lookup"><span data-stu-id="51dbc-121">Can be TRUE or NULL.</span></span> <span data-ttu-id="51dbc-122">Se verdadeiro, rejeitar e cancelar será nulo.</span><span class="sxs-lookup"><span data-stu-id="51dbc-122">If TRUE, then Reject and Cancel will be NULL.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51dbc-123"><strong>Rejeitar</strong></span><span class="sxs-lookup"><span data-stu-id="51dbc-123"><strong>Reject</strong></span></span></p></td>
<td><p><span data-ttu-id="51dbc-124">bit</span><span class="sxs-lookup"><span data-stu-id="51dbc-124">bit</span></span></p></td>
<td><p><span data-ttu-id="51dbc-125">Pode ser TRUE ou NULL.</span><span class="sxs-lookup"><span data-stu-id="51dbc-125">Can be TRUE or NULL.</span></span> <span data-ttu-id="51dbc-126">Se verdadeiro, aceitar e cancelar será nulo.</span><span class="sxs-lookup"><span data-stu-id="51dbc-126">If TRUE, then Accept and Cancel will be NULL.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51dbc-127"><strong>Cancelar</strong></span><span class="sxs-lookup"><span data-stu-id="51dbc-127"><strong>Cancel</strong></span></span></p></td>
<td><p><span data-ttu-id="51dbc-128">bit</span><span class="sxs-lookup"><span data-stu-id="51dbc-128">bit</span></span></p></td>
<td><p><span data-ttu-id="51dbc-129">Pode ser TRUE ou NULL.</span><span class="sxs-lookup"><span data-stu-id="51dbc-129">Can be TRUE or NULL.</span></span> <span data-ttu-id="51dbc-130">Se verdadeiro, aceitar e rejeitar será nulo.</span><span class="sxs-lookup"><span data-stu-id="51dbc-130">If TRUE, then Accept and Reject will be NULL.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

