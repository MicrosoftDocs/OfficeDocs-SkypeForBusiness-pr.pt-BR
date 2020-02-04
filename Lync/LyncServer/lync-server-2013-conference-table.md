---
title: 'Lync Server 2013: Tabela Conference'
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
ms.openlocfilehash: 4941dc3ef59630cd77cfb0f8a51407d15ca628f7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756975"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conference-table-in-lync-server-2013"></a><span data-ttu-id="d55fd-102">Tabela Conference no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d55fd-102">Conference table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d55fd-103">_**Tópico da última modificação:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="d55fd-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="d55fd-104">A tabela de conferências é uma tabela de suporte.</span><span class="sxs-lookup"><span data-stu-id="d55fd-104">The Conference table is a supporting table.</span></span> <span data-ttu-id="d55fd-105">Cada registro representa uma reunião ou sessão ponto a ponto.</span><span class="sxs-lookup"><span data-stu-id="d55fd-105">Each record represents one conference or peer-to-peer session.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d55fd-106"><strong>Coluna</strong></span><span class="sxs-lookup"><span data-stu-id="d55fd-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="d55fd-107"><strong>Tipo de dados</strong></span><span class="sxs-lookup"><span data-stu-id="d55fd-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="d55fd-108"><strong>Chave/índice</strong></span><span class="sxs-lookup"><span data-stu-id="d55fd-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="d55fd-109"><strong>Detalhes</strong></span><span class="sxs-lookup"><span data-stu-id="d55fd-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d55fd-110"><strong>ConferenceKey</strong></span><span class="sxs-lookup"><span data-stu-id="d55fd-110"><strong>ConferenceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="d55fd-111">int</span><span class="sxs-lookup"><span data-stu-id="d55fd-111">int</span></span></p></td>
<td><p><span data-ttu-id="d55fd-112">Primária</span><span class="sxs-lookup"><span data-stu-id="d55fd-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="d55fd-113">Número exclusivo que identifica esse registro de conferência.</span><span class="sxs-lookup"><span data-stu-id="d55fd-113">Unique number identifying this conference record.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d55fd-114"><strong>ConfURI</strong></span><span class="sxs-lookup"><span data-stu-id="d55fd-114"><strong>ConfURI</strong></span></span></p></td>
<td><p><span data-ttu-id="d55fd-115">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="d55fd-115">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="d55fd-116">exclusividade</span><span class="sxs-lookup"><span data-stu-id="d55fd-116">unique</span></span></p></td>
<td><p><span data-ttu-id="d55fd-117">URL da conferência se for uma conferência ou caixa de diálogo se for uma sessão ponto a ponto.</span><span class="sxs-lookup"><span data-stu-id="d55fd-117">Conference URI if this is a conference, or DialogID if this is a peer-to-peer session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d55fd-118"><strong>Prova</strong></span><span class="sxs-lookup"><span data-stu-id="d55fd-118"><strong>Checksum</strong></span></span></p></td>
<td><p><span data-ttu-id="d55fd-119">int</span><span class="sxs-lookup"><span data-stu-id="d55fd-119">int</span></span></p></td>
<td><p><span data-ttu-id="d55fd-120">dedo</span><span class="sxs-lookup"><span data-stu-id="d55fd-120">index</span></span></p></td>
<td><p><span data-ttu-id="d55fd-121">Checksum do URI da conferência.</span><span class="sxs-lookup"><span data-stu-id="d55fd-121">Checksum of the conference URI.</span></span> <span data-ttu-id="d55fd-122">Isso é usado internamente.</span><span class="sxs-lookup"><span data-stu-id="d55fd-122">This is used internally.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d55fd-123"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="d55fd-123"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="d55fd-124">datetime</span><span class="sxs-lookup"><span data-stu-id="d55fd-124">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d55fd-125">Somente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="d55fd-125">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

