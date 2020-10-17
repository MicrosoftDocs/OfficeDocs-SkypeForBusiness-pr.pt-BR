---
title: 'Lync Server 2013: tabela de caixas de diálogo'
description: 'Lync Server 2013: tabela de caixas de diálogo.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Dialog table
ms:assetid: 4d93424f-9072-43f5-83c2-3d539e3e9ca6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398313(v=OCS.15)
ms:contentKeyID: 48184068
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7ae93b8ca9f1146b7dc164803f27cbeeadc66777
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559717"
---
# <a name="dialog-table-in-lync-server-2013"></a><span data-ttu-id="814b1-103">Tabela Dialog no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="814b1-103">Dialog table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="814b1-104">_**Última modificação do tópico:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="814b1-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="814b1-105">A tabela da Caixa de Diálogo é uma tabela de suporte; cada registro representa uma caixa de diálogo de protocolo SIP.</span><span class="sxs-lookup"><span data-stu-id="814b1-105">The Dialog table is a supporting table; each record represents one Session Initiation Protocol (SIP) dialog.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="814b1-106"><strong>Coluna</strong></span><span class="sxs-lookup"><span data-stu-id="814b1-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="814b1-107"><strong>Tipo de dados</strong></span><span class="sxs-lookup"><span data-stu-id="814b1-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="814b1-108"><strong>Chave/índice</strong></span><span class="sxs-lookup"><span data-stu-id="814b1-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="814b1-109"><strong>Detalhes</strong></span><span class="sxs-lookup"><span data-stu-id="814b1-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="814b1-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="814b1-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="814b1-111">datetime</span><span class="sxs-lookup"><span data-stu-id="814b1-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="814b1-112">Primário</span><span class="sxs-lookup"><span data-stu-id="814b1-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="814b1-p101">Horário em que o agente de QoE (Qualidade de Excelência) recebe o primeiro relatório do chamador ou receptor. Usado em conjunto com SessionSeq para identificar exclusivamente uma sessão.</span><span class="sxs-lookup"><span data-stu-id="814b1-p101">Time when the Quality of Excellence (QoE) agent receives the first report from either caller or callee. Used in conjunction with SessionSeq to uniquely identify a session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="814b1-115"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="814b1-115"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="814b1-116">int</span><span class="sxs-lookup"><span data-stu-id="814b1-116">int</span></span></p></td>
<td><p><span data-ttu-id="814b1-117">Primário</span><span class="sxs-lookup"><span data-stu-id="814b1-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="814b1-118">Número de sequência para diferenciar sessões quando tiverem o mesmo ConferenceDateTime.</span><span class="sxs-lookup"><span data-stu-id="814b1-118">Sequence number to differentiate sessions when they have the same ConferenceDateTime.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="814b1-119"><strong>DialogID</strong></span><span class="sxs-lookup"><span data-stu-id="814b1-119"><strong>DialogID</strong></span></span></p></td>
<td><p><span data-ttu-id="814b1-120">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="814b1-120">varchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="814b1-121">ID da caixa de diálogo que é globalmente exclusiva.</span><span class="sxs-lookup"><span data-stu-id="814b1-121">Dialog ID which is globally unique.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="814b1-122"><strong>DialogIDChecksum</strong></span><span class="sxs-lookup"><span data-stu-id="814b1-122"><strong>DialogIDChecksum</strong></span></span></p></td>
<td><p><span data-ttu-id="814b1-123">int</span><span class="sxs-lookup"><span data-stu-id="814b1-123">int</span></span></p></td>
<td><p><span data-ttu-id="814b1-124">index</span><span class="sxs-lookup"><span data-stu-id="814b1-124">index</span></span></p></td>
<td><p><span data-ttu-id="814b1-125">Soma de verificação da ID da Caixa de Diálogo.</span><span class="sxs-lookup"><span data-stu-id="814b1-125">Checksum of the Dialog ID.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

