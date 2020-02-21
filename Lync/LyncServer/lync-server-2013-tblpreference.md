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
ms.openlocfilehash: 6d1405634ad92b3f2cde2d085875648d738d6200
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214527"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblpreference-in-lync-server-2013"></a><span data-ttu-id="d9c87-102">tblPreference no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d9c87-102">tblPreference in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d9c87-103">_**Última modificação do tópico:** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="d9c87-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="d9c87-104">tblPreference contém as preferências de cliente do usuário.</span><span class="sxs-lookup"><span data-stu-id="d9c87-104">tblPreference contains the users’ client preferences.</span></span> <span data-ttu-id="d9c87-105">Isso geralmente é usado por clientes anteriores ao Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="d9c87-105">This is generally used by clients previous to Lync 2013.</span></span>

### <a name="columns"></a><span data-ttu-id="d9c87-106">Colunas</span><span class="sxs-lookup"><span data-stu-id="d9c87-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d9c87-107">Coluna</span><span class="sxs-lookup"><span data-stu-id="d9c87-107">Column</span></span></th>
<th><span data-ttu-id="d9c87-108">Tipo</span><span class="sxs-lookup"><span data-stu-id="d9c87-108">Type</span></span></th>
<th><span data-ttu-id="d9c87-109">Descrição</span><span class="sxs-lookup"><span data-stu-id="d9c87-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d9c87-110">prefLabel</span><span class="sxs-lookup"><span data-stu-id="d9c87-110">prefLabel</span></span></p></td>
<td><p><span data-ttu-id="d9c87-111">nvarchar (255), não nulo</span><span class="sxs-lookup"><span data-stu-id="d9c87-111">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="d9c87-112">Rótulo com um formato como: &lt;User SIP URI&gt;| username. &lt;definição&gt;de preferência.</span><span class="sxs-lookup"><span data-stu-id="d9c87-112">Label with a format such as: &lt;user sip uri&gt;|username.&lt;preference set&gt;.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d9c87-113">prefSeqID</span><span class="sxs-lookup"><span data-stu-id="d9c87-113">prefSeqID</span></span></p></td>
<td><p><span data-ttu-id="d9c87-114">int, not null</span><span class="sxs-lookup"><span data-stu-id="d9c87-114">int, not null</span></span></p></td>
<td><p><span data-ttu-id="d9c87-115">Um número sequencial (por rótulo) para fins de controle de versão.</span><span class="sxs-lookup"><span data-stu-id="d9c87-115">A sequential number (per label) for versioning purposes.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d9c87-116">prefContent</span><span class="sxs-lookup"><span data-stu-id="d9c87-116">prefContent</span></span></p></td>
<td><p><span data-ttu-id="d9c87-117">nvarchar (máx.)</span><span class="sxs-lookup"><span data-stu-id="d9c87-117">nvarchar (max)</span></span></p></td>
<td><p><span data-ttu-id="d9c87-118">Conteúdo codificado.</span><span class="sxs-lookup"><span data-stu-id="d9c87-118">Encoded content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d9c87-119">lastModifiedBy</span><span class="sxs-lookup"><span data-stu-id="d9c87-119">lastModifiedBy</span></span></p></td>
<td><p><span data-ttu-id="d9c87-120">int, not null</span><span class="sxs-lookup"><span data-stu-id="d9c87-120">int, not null</span></span></p></td>
<td><p><span data-ttu-id="d9c87-121">ID da entidade de segurança que atualizou a preferência.</span><span class="sxs-lookup"><span data-stu-id="d9c87-121">ID of the principal that updated the preference.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="d9c87-122">Chave</span><span class="sxs-lookup"><span data-stu-id="d9c87-122">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d9c87-123">Coluna</span><span class="sxs-lookup"><span data-stu-id="d9c87-123">Column</span></span></th>
<th><span data-ttu-id="d9c87-124">Descrição</span><span class="sxs-lookup"><span data-stu-id="d9c87-124">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d9c87-125">&lt;prefLabel, prefSeqID&gt;</span><span class="sxs-lookup"><span data-stu-id="d9c87-125">&lt;prefLabel, prefSeqID&gt;</span></span></p></td>
<td><p><span data-ttu-id="d9c87-126">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="d9c87-126">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

