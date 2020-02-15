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
ms.openlocfilehash: 733b3fc6fa77f8f18de1a5c79be86a5aea340cec
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048582"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conference-table-in-lync-server-2013"></a><span data-ttu-id="4d9b8-102">Tabela de conferência no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4d9b8-102">Conference table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4d9b8-103">_**Última modificação do tópico:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="4d9b8-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="4d9b8-p101">A tabela de Conferência é uma tabela de suporte. Cada registro representa uma conferência ou sessão ponto a ponto.</span><span class="sxs-lookup"><span data-stu-id="4d9b8-p101">The Conference table is a supporting table. Each record represents one conference or peer-to-peer session.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4d9b8-106"><strong>Coluna</strong></span><span class="sxs-lookup"><span data-stu-id="4d9b8-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="4d9b8-107"><strong>Tipo de dados</strong></span><span class="sxs-lookup"><span data-stu-id="4d9b8-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="4d9b8-108"><strong>Chave/índice</strong></span><span class="sxs-lookup"><span data-stu-id="4d9b8-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="4d9b8-109"><strong>Detalhes</strong></span><span class="sxs-lookup"><span data-stu-id="4d9b8-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4d9b8-110"><strong>ConferenceKey</strong></span><span class="sxs-lookup"><span data-stu-id="4d9b8-110"><strong>ConferenceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="4d9b8-111">int</span><span class="sxs-lookup"><span data-stu-id="4d9b8-111">int</span></span></p></td>
<td><p><span data-ttu-id="4d9b8-112">Primário</span><span class="sxs-lookup"><span data-stu-id="4d9b8-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="4d9b8-113">Número exclusivo que identifica o registro desta conferência.</span><span class="sxs-lookup"><span data-stu-id="4d9b8-113">Unique number identifying this conference record.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4d9b8-114"><strong>ConfURI</strong></span><span class="sxs-lookup"><span data-stu-id="4d9b8-114"><strong>ConfURI</strong></span></span></p></td>
<td><p><span data-ttu-id="4d9b8-115">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="4d9b8-115">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="4d9b8-116">diferente</span><span class="sxs-lookup"><span data-stu-id="4d9b8-116">unique</span></span></p></td>
<td><p><span data-ttu-id="4d9b8-117">URI da conferência, se isso for uma conferência, ou DialogID se for uma sessão ponto a ponto.</span><span class="sxs-lookup"><span data-stu-id="4d9b8-117">Conference URI if this is a conference, or DialogID if this is a peer-to-peer session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4d9b8-118"><strong>Soma de verificação</strong></span><span class="sxs-lookup"><span data-stu-id="4d9b8-118"><strong>Checksum</strong></span></span></p></td>
<td><p><span data-ttu-id="4d9b8-119">int</span><span class="sxs-lookup"><span data-stu-id="4d9b8-119">int</span></span></p></td>
<td><p><span data-ttu-id="4d9b8-120">index</span><span class="sxs-lookup"><span data-stu-id="4d9b8-120">index</span></span></p></td>
<td><p><span data-ttu-id="4d9b8-p102">Soma de verificação do URI de conferência. Isso é usado internamente.</span><span class="sxs-lookup"><span data-stu-id="4d9b8-p102">Checksum of the conference URI. This is used internally.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4d9b8-123"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="4d9b8-123"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="4d9b8-124">datetime</span><span class="sxs-lookup"><span data-stu-id="4d9b8-124">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4d9b8-125">Apenas para uso interno.</span><span class="sxs-lookup"><span data-stu-id="4d9b8-125">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

