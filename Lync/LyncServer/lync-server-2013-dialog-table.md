---
title: 'Lync Server 2013: Tabela Dialog'
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
ms.openlocfilehash: 2f0ef564ad1224ba9970b7cceb5db60e0eb344da
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762239"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dialog-table-in-lync-server-2013"></a><span data-ttu-id="1f034-102">Tabela Dialog no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1f034-102">Dialog table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1f034-103">_**Tópico da última modificação:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="1f034-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="1f034-104">A tabela de caixa de diálogo é uma tabela de suporte; cada registro representa uma caixa de diálogo SIP (protocolo de início de sessão).</span><span class="sxs-lookup"><span data-stu-id="1f034-104">The Dialog table is a supporting table; each record represents one Session Initiation Protocol (SIP) dialog.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1f034-105"><strong>Coluna</strong></span><span class="sxs-lookup"><span data-stu-id="1f034-105"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="1f034-106"><strong>Tipo de dados</strong></span><span class="sxs-lookup"><span data-stu-id="1f034-106"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="1f034-107"><strong>Chave/índice</strong></span><span class="sxs-lookup"><span data-stu-id="1f034-107"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="1f034-108"><strong>Detalhes</strong></span><span class="sxs-lookup"><span data-stu-id="1f034-108"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1f034-109"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="1f034-109"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="1f034-110">datetime</span><span class="sxs-lookup"><span data-stu-id="1f034-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="1f034-111">Primária</span><span class="sxs-lookup"><span data-stu-id="1f034-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="1f034-112">Tempo quando o agente de Quality of Excellence (QoE) recebe o primeiro relatório do chamador ou do receptor.</span><span class="sxs-lookup"><span data-stu-id="1f034-112">Time when the Quality of Excellence (QoE) agent receives the first report from either caller or callee.</span></span> <span data-ttu-id="1f034-113">Usado em conjunto com o SessionSeq para identificar exclusivamente uma sessão.</span><span class="sxs-lookup"><span data-stu-id="1f034-113">Used in conjunction with SessionSeq to uniquely identify a session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1f034-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="1f034-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="1f034-115">int</span><span class="sxs-lookup"><span data-stu-id="1f034-115">int</span></span></p></td>
<td><p><span data-ttu-id="1f034-116">Primária</span><span class="sxs-lookup"><span data-stu-id="1f034-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="1f034-117">Número de sequência para diferenciar sessões quando elas tiverem o mesmo ConferenceDateTime.</span><span class="sxs-lookup"><span data-stu-id="1f034-117">Sequence number to differentiate sessions when they have the same ConferenceDateTime.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1f034-118"><strong>Caixa de diálogo</strong></span><span class="sxs-lookup"><span data-stu-id="1f034-118"><strong>DialogID</strong></span></span></p></td>
<td><p><span data-ttu-id="1f034-119">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="1f034-119">varchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1f034-120">IDENTIFICAÇÃO da caixa de diálogo que é globalmente exclusiva.</span><span class="sxs-lookup"><span data-stu-id="1f034-120">Dialog ID which is globally unique.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1f034-121"><strong>DialogIDChecksum</strong></span><span class="sxs-lookup"><span data-stu-id="1f034-121"><strong>DialogIDChecksum</strong></span></span></p></td>
<td><p><span data-ttu-id="1f034-122">int</span><span class="sxs-lookup"><span data-stu-id="1f034-122">int</span></span></p></td>
<td><p><span data-ttu-id="1f034-123">dedo</span><span class="sxs-lookup"><span data-stu-id="1f034-123">index</span></span></p></td>
<td><p><span data-ttu-id="1f034-124">Checksum da ID da caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="1f034-124">Checksum of the Dialog ID.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

