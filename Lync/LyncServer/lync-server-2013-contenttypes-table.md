---
title: 'Lync Server 2013: Tabela ContentTypes'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ContentTypes table
ms:assetid: e3e38035-457c-4173-bdb9-d53a7420eba2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399007(v=OCS.15)
ms:contentKeyID: 48185723
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4cf7ba9c9fb267e8c65c3ba672850c04eb95a459
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740561"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="contenttypes-table-in-lync-server-2013"></a><span data-ttu-id="e21c3-102">Tabela ContentTypes no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e21c3-102">ContentTypes table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e21c3-103">_**Tópico da última modificação:** 2010-11-07_</span><span class="sxs-lookup"><span data-stu-id="e21c3-103">_**Topic Last Modified:** 2010-11-07_</span></span>

<span data-ttu-id="e21c3-104">A tabela ContentTypes é uma tabela de suporte que armazena uma lista dos tipos de conteúdo usados em sessões ponto a ponto e em sessões de conferência.</span><span class="sxs-lookup"><span data-stu-id="e21c3-104">The ContentTypes table is a supporting table that stores a list of the content types used in both peer-to-peer sessions and conference sessions.</span></span> <span data-ttu-id="e21c3-105">Cada registro na tabela representa um tipo de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="e21c3-105">Each record in the table represents one content type.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e21c3-106">Coluna</span><span class="sxs-lookup"><span data-stu-id="e21c3-106">Column</span></span></th>
<th><span data-ttu-id="e21c3-107">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="e21c3-107">Data Type</span></span></th>
<th><span data-ttu-id="e21c3-108">Chave/índice</span><span class="sxs-lookup"><span data-stu-id="e21c3-108">Key/Index</span></span></th>
<th><span data-ttu-id="e21c3-109">Detalhes</span><span class="sxs-lookup"><span data-stu-id="e21c3-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e21c3-110"><strong>ContentTypeid</strong></span><span class="sxs-lookup"><span data-stu-id="e21c3-110"><strong>ContentTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="e21c3-111">int</span><span class="sxs-lookup"><span data-stu-id="e21c3-111">int</span></span></p></td>
<td><p><span data-ttu-id="e21c3-112">Primária</span><span class="sxs-lookup"><span data-stu-id="e21c3-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="e21c3-113">Número exclusivo que identifica o tipo de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="e21c3-113">Unique number identifying the content type.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e21c3-114"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="e21c3-114"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="e21c3-115">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e21c3-115">nvarchar(256)</span></span></p></td>
<td> </td>
<td><p><span data-ttu-id="e21c3-116">Nome do tipo de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="e21c3-116">Content type name.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

