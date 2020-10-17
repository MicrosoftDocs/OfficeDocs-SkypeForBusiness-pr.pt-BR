---
title: 'Lync Server 2013: tabela de conferência'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conference table
ms:assetid: 2a2c327c-4719-42dc-a3bb-6dbc0864d9af
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425762(v=OCS.15)
ms:contentKeyID: 48183700
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a6f51e05c9721ca789724dcd015c62c2a71d8731
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520618"
---
# <a name="conference-table-in-lync-server-2013"></a><span data-ttu-id="b4a7e-102">Tabela de conferência no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b4a7e-102">Conference table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b4a7e-103">_**Última modificação do tópico:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="b4a7e-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="b4a7e-p101">A tabela de Conferência é uma tabela de suporte. Cada registro representa uma conferência ou sessão ponto a ponto.</span><span class="sxs-lookup"><span data-stu-id="b4a7e-p101">The Conference table is a supporting table. Each record represents one conference or peer-to-peer session.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b4a7e-106"><strong>Coluna</strong></span><span class="sxs-lookup"><span data-stu-id="b4a7e-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="b4a7e-107"><strong>Tipo de dados</strong></span><span class="sxs-lookup"><span data-stu-id="b4a7e-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="b4a7e-108"><strong>Chave/índice</strong></span><span class="sxs-lookup"><span data-stu-id="b4a7e-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="b4a7e-109"><strong>Detalhes</strong></span><span class="sxs-lookup"><span data-stu-id="b4a7e-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b4a7e-110"><strong>ConferenceKey</strong></span><span class="sxs-lookup"><span data-stu-id="b4a7e-110"><strong>ConferenceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="b4a7e-111">int</span><span class="sxs-lookup"><span data-stu-id="b4a7e-111">int</span></span></p></td>
<td><p><span data-ttu-id="b4a7e-112">Primário</span><span class="sxs-lookup"><span data-stu-id="b4a7e-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="b4a7e-113">Número exclusivo que identifica o registro desta conferência.</span><span class="sxs-lookup"><span data-stu-id="b4a7e-113">Unique number identifying this conference record.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b4a7e-114"><strong>ConfURI</strong></span><span class="sxs-lookup"><span data-stu-id="b4a7e-114"><strong>ConfURI</strong></span></span></p></td>
<td><p><span data-ttu-id="b4a7e-115">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="b4a7e-115">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="b4a7e-116">diferente</span><span class="sxs-lookup"><span data-stu-id="b4a7e-116">unique</span></span></p></td>
<td><p><span data-ttu-id="b4a7e-117">URI da conferência, se isso for uma conferência, ou DialogID se for uma sessão ponto a ponto.</span><span class="sxs-lookup"><span data-stu-id="b4a7e-117">Conference URI if this is a conference, or DialogID if this is a peer-to-peer session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b4a7e-118"><strong>Soma de verificação</strong></span><span class="sxs-lookup"><span data-stu-id="b4a7e-118"><strong>Checksum</strong></span></span></p></td>
<td><p><span data-ttu-id="b4a7e-119">int</span><span class="sxs-lookup"><span data-stu-id="b4a7e-119">int</span></span></p></td>
<td><p><span data-ttu-id="b4a7e-120">index</span><span class="sxs-lookup"><span data-stu-id="b4a7e-120">index</span></span></p></td>
<td><p><span data-ttu-id="b4a7e-p102">Soma de verificação do URI de conferência. Isso é usado internamente.</span><span class="sxs-lookup"><span data-stu-id="b4a7e-p102">Checksum of the conference URI. This is used internally.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b4a7e-123"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="b4a7e-123"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="b4a7e-124">datetime</span><span class="sxs-lookup"><span data-stu-id="b4a7e-124">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b4a7e-125">Apenas para uso interno.</span><span class="sxs-lookup"><span data-stu-id="b4a7e-125">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

