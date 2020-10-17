---
title: 'Lync Server 2013: tblPreference'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPreference
ms:assetid: f94eb128-f782-42ff-a568-ed3529573bc8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615052(v=OCS.15)
ms:contentKeyID: 48185913
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ef0ee11cd780037410ea1d7e0d94c83e139d8418
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48523768"
---
# <a name="tblpreference-in-lync-server-2013"></a><span data-ttu-id="2927c-102">tblPreference no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2927c-102">tblPreference in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2927c-103">_**Última modificação do tópico:** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="2927c-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="2927c-104">tblPreference contém as preferências de cliente do usuário.</span><span class="sxs-lookup"><span data-stu-id="2927c-104">tblPreference contains the users’ client preferences.</span></span> <span data-ttu-id="2927c-105">Isso geralmente é usado por clientes anteriores ao Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="2927c-105">This is generally used by clients previous to Lync 2013.</span></span>

### <a name="columns"></a><span data-ttu-id="2927c-106">Colunas</span><span class="sxs-lookup"><span data-stu-id="2927c-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2927c-107">Coluna</span><span class="sxs-lookup"><span data-stu-id="2927c-107">Column</span></span></th>
<th><span data-ttu-id="2927c-108">Tipo</span><span class="sxs-lookup"><span data-stu-id="2927c-108">Type</span></span></th>
<th><span data-ttu-id="2927c-109">Descrição</span><span class="sxs-lookup"><span data-stu-id="2927c-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2927c-110">prefLabel</span><span class="sxs-lookup"><span data-stu-id="2927c-110">prefLabel</span></span></p></td>
<td><p><span data-ttu-id="2927c-111">nvarchar (255), não nulo</span><span class="sxs-lookup"><span data-stu-id="2927c-111">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="2927c-112">Rótulo com um formato como: &lt; User SIP URI &gt; | username. &lt; definição de preferência &gt; .</span><span class="sxs-lookup"><span data-stu-id="2927c-112">Label with a format such as: &lt;user sip uri&gt;|username.&lt;preference set&gt;.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2927c-113">prefSeqID</span><span class="sxs-lookup"><span data-stu-id="2927c-113">prefSeqID</span></span></p></td>
<td><p><span data-ttu-id="2927c-114">int, not null</span><span class="sxs-lookup"><span data-stu-id="2927c-114">int, not null</span></span></p></td>
<td><p><span data-ttu-id="2927c-115">Um número sequencial (por rótulo) para fins de controle de versão.</span><span class="sxs-lookup"><span data-stu-id="2927c-115">A sequential number (per label) for versioning purposes.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2927c-116">prefContent</span><span class="sxs-lookup"><span data-stu-id="2927c-116">prefContent</span></span></p></td>
<td><p><span data-ttu-id="2927c-117">nvarchar (máx.)</span><span class="sxs-lookup"><span data-stu-id="2927c-117">nvarchar (max)</span></span></p></td>
<td><p><span data-ttu-id="2927c-118">Conteúdo codificado.</span><span class="sxs-lookup"><span data-stu-id="2927c-118">Encoded content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2927c-119">lastModifiedBy</span><span class="sxs-lookup"><span data-stu-id="2927c-119">lastModifiedBy</span></span></p></td>
<td><p><span data-ttu-id="2927c-120">int, not null</span><span class="sxs-lookup"><span data-stu-id="2927c-120">int, not null</span></span></p></td>
<td><p><span data-ttu-id="2927c-121">ID da entidade de segurança que atualizou a preferência.</span><span class="sxs-lookup"><span data-stu-id="2927c-121">ID of the principal that updated the preference.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="2927c-122">Chave</span><span class="sxs-lookup"><span data-stu-id="2927c-122">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2927c-123">Coluna</span><span class="sxs-lookup"><span data-stu-id="2927c-123">Column</span></span></th>
<th><span data-ttu-id="2927c-124">Descrição</span><span class="sxs-lookup"><span data-stu-id="2927c-124">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2927c-125">&lt;prefLabel, prefSeqID&gt;</span><span class="sxs-lookup"><span data-stu-id="2927c-125">&lt;prefLabel, prefSeqID&gt;</span></span></p></td>
<td><p><span data-ttu-id="2927c-126">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="2927c-126">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

