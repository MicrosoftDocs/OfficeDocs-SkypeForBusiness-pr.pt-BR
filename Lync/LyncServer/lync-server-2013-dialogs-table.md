---
title: 'Lync Server 2013: tabela de caixas de diálogo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Dialogs table
ms:assetid: 487a430b-af66-4ea6-b28e-4e33cfdb7f9e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425954(v=OCS.15)
ms:contentKeyID: 48184001
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: be0bb5a603f856aa0faa02074962618fcb82448e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036721"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dialogs-table-in-lync-server-2013"></a><span data-ttu-id="ce673-102">Tabela Dialogs no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ce673-102">Dialogs table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ce673-103">_**Última modificação do tópico:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="ce673-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="ce673-104">A tabela de caixas de diálogo é uma tabela de suporte que armazena as informações sobre o DialogIDs para sessões ponto a ponto.</span><span class="sxs-lookup"><span data-stu-id="ce673-104">The Dialogs table is a supporting table that stores the information about DialogIDs for peer-to-peer sessions.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ce673-105">Coluna</span><span class="sxs-lookup"><span data-stu-id="ce673-105">Column</span></span></th>
<th><span data-ttu-id="ce673-106">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="ce673-106">Data Type</span></span></th>
<th><span data-ttu-id="ce673-107">Chave/índice</span><span class="sxs-lookup"><span data-stu-id="ce673-107">Key/Index</span></span></th>
<th><span data-ttu-id="ce673-108">Detalhes</span><span class="sxs-lookup"><span data-stu-id="ce673-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ce673-109"><strong>Identificação_da_sessãotime</strong></span><span class="sxs-lookup"><span data-stu-id="ce673-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="ce673-110">datetime</span><span class="sxs-lookup"><span data-stu-id="ce673-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="ce673-111">Primário</span><span class="sxs-lookup"><span data-stu-id="ce673-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="ce673-112">Hora da solicitação de sessão; usado em conjunto com o SessionIDSeq para identificar exclusivamente uma sessão.</span><span class="sxs-lookup"><span data-stu-id="ce673-112">Time of session request; used in conjunction with SessionIDSeq to uniquely identify a session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce673-113"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="ce673-113"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="ce673-114">int</span><span class="sxs-lookup"><span data-stu-id="ce673-114">int</span></span></p></td>
<td><p><span data-ttu-id="ce673-115">Primário</span><span class="sxs-lookup"><span data-stu-id="ce673-115">Primary</span></span></p></td>
<td><p><span data-ttu-id="ce673-116">O número de ID para identificar a sessão.</span><span class="sxs-lookup"><span data-stu-id="ce673-116">ID number to identify the session.</span></span> <span data-ttu-id="ce673-117">Usado em conjunto com a Identificação_da_sessãotime para identificar exclusivamente uma sessão.</span><span class="sxs-lookup"><span data-stu-id="ce673-117">Used in conjunction with SessionIDTime to uniquely identify a session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ce673-118"><strong>ExternalChecksum</strong></span><span class="sxs-lookup"><span data-stu-id="ce673-118"><strong>ExternalChecksum</strong></span></span></p></td>
<td><p><span data-ttu-id="ce673-119">int</span><span class="sxs-lookup"><span data-stu-id="ce673-119">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ce673-120">Checksum da externalId.</span><span class="sxs-lookup"><span data-stu-id="ce673-120">Checksum of the ExternalID.</span></span> <span data-ttu-id="ce673-121">Este campo é usado para aumentar a velocidade das pesquisas de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="ce673-121">This field is used to increase the speed of database searches.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce673-122"><strong>ExternalId</strong></span><span class="sxs-lookup"><span data-stu-id="ce673-122"><strong>ExternalId</strong></span></span></p></td>
<td><p><span data-ttu-id="ce673-123">varbinary (775)</span><span class="sxs-lookup"><span data-stu-id="ce673-123">varbinary(775)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ce673-124">ID da caixa de diálogo SIP, armazenado como um binário.</span><span class="sxs-lookup"><span data-stu-id="ce673-124">SIP dialog ID, stored as a binary.</span></span> <span data-ttu-id="ce673-125">O formato do binário é:</span><span class="sxs-lookup"><span data-stu-id="ce673-125">The format of the binary is:</span></span></p>
<p><span data-ttu-id="ce673-126">caixa de diálogo; de-tag; to-tag</span><span class="sxs-lookup"><span data-stu-id="ce673-126">dialog;from-tag;to-tag</span></span></p>
<p><span data-ttu-id="ce673-127">Esses dados podem ser convertidos em formato de texto usando esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="ce673-127">This data can be converted to text format by using this syntax:</span></span></p>
<p><code>cast(cast(ExternalId as varbinary(max)) as varchar(max))</code></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

