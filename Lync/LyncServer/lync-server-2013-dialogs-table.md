---
title: 'Lync Server 2013: tabela de caixas de diálogo'
description: 'Lync Server 2013: tabela de caixas de diálogo.'
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
ms.openlocfilehash: 8c2c9cf9ec59fc48f7f5ffc6232980e3f8aa68c1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559697"
---
# <a name="dialogs-table-in-lync-server-2013"></a><span data-ttu-id="93f85-103">Tabela Dialogs no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="93f85-103">Dialogs table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="93f85-104">_**Última modificação do tópico:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="93f85-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="93f85-105">A tabela de caixas de diálogo é uma tabela de suporte que armazena as informações sobre o DialogIDs para sessões ponto a ponto.</span><span class="sxs-lookup"><span data-stu-id="93f85-105">The Dialogs table is a supporting table that stores the information about DialogIDs for peer-to-peer sessions.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="93f85-106">Coluna</span><span class="sxs-lookup"><span data-stu-id="93f85-106">Column</span></span></th>
<th><span data-ttu-id="93f85-107">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="93f85-107">Data Type</span></span></th>
<th><span data-ttu-id="93f85-108">Chave/índice</span><span class="sxs-lookup"><span data-stu-id="93f85-108">Key/Index</span></span></th>
<th><span data-ttu-id="93f85-109">Detalhes</span><span class="sxs-lookup"><span data-stu-id="93f85-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="93f85-110"><strong>Identificação_da_sessãotime</strong></span><span class="sxs-lookup"><span data-stu-id="93f85-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="93f85-111">datetime</span><span class="sxs-lookup"><span data-stu-id="93f85-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="93f85-112">Primário</span><span class="sxs-lookup"><span data-stu-id="93f85-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="93f85-113">Hora da solicitação de sessão; usado em conjunto com o SessionIDSeq para identificar exclusivamente uma sessão.</span><span class="sxs-lookup"><span data-stu-id="93f85-113">Time of session request; used in conjunction with SessionIDSeq to uniquely identify a session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93f85-114"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="93f85-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="93f85-115">int</span><span class="sxs-lookup"><span data-stu-id="93f85-115">int</span></span></p></td>
<td><p><span data-ttu-id="93f85-116">Primário</span><span class="sxs-lookup"><span data-stu-id="93f85-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="93f85-117">O número de ID para identificar a sessão.</span><span class="sxs-lookup"><span data-stu-id="93f85-117">ID number to identify the session.</span></span> <span data-ttu-id="93f85-118">Usado em conjunto com a Identificação_da_sessãotime para identificar exclusivamente uma sessão.</span><span class="sxs-lookup"><span data-stu-id="93f85-118">Used in conjunction with SessionIDTime to uniquely identify a session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93f85-119"><strong>ExternalChecksum</strong></span><span class="sxs-lookup"><span data-stu-id="93f85-119"><strong>ExternalChecksum</strong></span></span></p></td>
<td><p><span data-ttu-id="93f85-120">int</span><span class="sxs-lookup"><span data-stu-id="93f85-120">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="93f85-121">Checksum da externalId.</span><span class="sxs-lookup"><span data-stu-id="93f85-121">Checksum of the ExternalID.</span></span> <span data-ttu-id="93f85-122">Este campo é usado para aumentar a velocidade das pesquisas de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="93f85-122">This field is used to increase the speed of database searches.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93f85-123"><strong>ExternalId</strong></span><span class="sxs-lookup"><span data-stu-id="93f85-123"><strong>ExternalId</strong></span></span></p></td>
<td><p><span data-ttu-id="93f85-124">varbinary (775)</span><span class="sxs-lookup"><span data-stu-id="93f85-124">varbinary(775)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="93f85-125">ID da caixa de diálogo SIP, armazenado como um binário.</span><span class="sxs-lookup"><span data-stu-id="93f85-125">SIP dialog ID, stored as a binary.</span></span> <span data-ttu-id="93f85-126">O formato do binário é:</span><span class="sxs-lookup"><span data-stu-id="93f85-126">The format of the binary is:</span></span></p>
<p><span data-ttu-id="93f85-127">caixa de diálogo; de-tag; to-tag</span><span class="sxs-lookup"><span data-stu-id="93f85-127">dialog;from-tag;to-tag</span></span></p>
<p><span data-ttu-id="93f85-128">Esses dados podem ser convertidos em formato de texto usando esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="93f85-128">This data can be converted to text format by using this syntax:</span></span></p>
<p><code>cast(cast(ExternalId as varbinary(max)) as varchar(max))</code></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

