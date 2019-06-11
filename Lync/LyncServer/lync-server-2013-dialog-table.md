---
title: 'Lync Server 2013: Tabela Dialog'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Dialog table
ms:assetid: 4d93424f-9072-43f5-83c2-3d539e3e9ca6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398313(v=OCS.15)
ms:contentKeyID: 48184068
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d47744cf17d3459c16e382c3551b427aa45b5ce6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829391"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dialog-table-in-lync-server-2013"></a><span data-ttu-id="01273-102">Tabela Dialog no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="01273-102">Dialog table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="01273-103">_**Tópico da última modificação:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="01273-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="01273-104">A tabela de caixa de diálogo é uma tabela de suporte; cada registro representa uma caixa de diálogo SIP (protocolo de início de sessão).</span><span class="sxs-lookup"><span data-stu-id="01273-104">The Dialog table is a supporting table; each record represents one Session Initiation Protocol (SIP) dialog.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="01273-105"><strong>Coluna</strong></span><span class="sxs-lookup"><span data-stu-id="01273-105"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="01273-106"><strong>Tipo de dados</strong></span><span class="sxs-lookup"><span data-stu-id="01273-106"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="01273-107"><strong>Chave/índice</strong></span><span class="sxs-lookup"><span data-stu-id="01273-107"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="01273-108"><strong>Detalhes</strong></span><span class="sxs-lookup"><span data-stu-id="01273-108"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="01273-109"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="01273-109"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="01273-110">datetime</span><span class="sxs-lookup"><span data-stu-id="01273-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="01273-111">Primária</span><span class="sxs-lookup"><span data-stu-id="01273-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="01273-112">Tempo quando o agente de Quality of Excellence (QoE) recebe o primeiro relatório do chamador ou do receptor.</span><span class="sxs-lookup"><span data-stu-id="01273-112">Time when the Quality of Excellence (QoE) agent receives the first report from either caller or callee.</span></span> <span data-ttu-id="01273-113">Usado em conjunto com o SessionSeq para identificar exclusivamente uma sessão.</span><span class="sxs-lookup"><span data-stu-id="01273-113">Used in conjunction with SessionSeq to uniquely identify a session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="01273-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="01273-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="01273-115">int</span><span class="sxs-lookup"><span data-stu-id="01273-115">int</span></span></p></td>
<td><p><span data-ttu-id="01273-116">Primária</span><span class="sxs-lookup"><span data-stu-id="01273-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="01273-117">Número de sequência para diferenciar sessões quando elas tiverem o mesmo ConferenceDateTime.</span><span class="sxs-lookup"><span data-stu-id="01273-117">Sequence number to differentiate sessions when they have the same ConferenceDateTime.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="01273-118"><strong>Caixa de diálogo</strong></span><span class="sxs-lookup"><span data-stu-id="01273-118"><strong>DialogID</strong></span></span></p></td>
<td><p><span data-ttu-id="01273-119">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="01273-119">varchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="01273-120">IDENTIFICAÇÃO da caixa de diálogo que é globalmente exclusiva.</span><span class="sxs-lookup"><span data-stu-id="01273-120">Dialog ID which is globally unique.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="01273-121"><strong>DialogIDChecksum</strong></span><span class="sxs-lookup"><span data-stu-id="01273-121"><strong>DialogIDChecksum</strong></span></span></p></td>
<td><p><span data-ttu-id="01273-122">int</span><span class="sxs-lookup"><span data-stu-id="01273-122">int</span></span></p></td>
<td><p><span data-ttu-id="01273-123">dedo</span><span class="sxs-lookup"><span data-stu-id="01273-123">index</span></span></p></td>
<td><p><span data-ttu-id="01273-124">Checksum da ID da caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="01273-124">Checksum of the Dialog ID.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

