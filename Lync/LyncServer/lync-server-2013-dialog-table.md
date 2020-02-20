---
title: 'Lync Server 2013: tabela de caixas de diálogo'
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
ms.openlocfilehash: 65fb3fd81eb9128dea5479868617bb429b271719
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151653"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dialog-table-in-lync-server-2013"></a><span data-ttu-id="1c520-102">Tabela Dialog no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1c520-102">Dialog table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1c520-103">_**Última modificação do tópico:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="1c520-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="1c520-104">A tabela da Caixa de Diálogo é uma tabela de suporte; cada registro representa uma caixa de diálogo de protocolo SIP.</span><span class="sxs-lookup"><span data-stu-id="1c520-104">The Dialog table is a supporting table; each record represents one Session Initiation Protocol (SIP) dialog.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1c520-105"><strong>Coluna</strong></span><span class="sxs-lookup"><span data-stu-id="1c520-105"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="1c520-106"><strong>Tipo de dados</strong></span><span class="sxs-lookup"><span data-stu-id="1c520-106"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="1c520-107"><strong>Chave/índice</strong></span><span class="sxs-lookup"><span data-stu-id="1c520-107"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="1c520-108"><strong>Detalhes</strong></span><span class="sxs-lookup"><span data-stu-id="1c520-108"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1c520-109"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="1c520-109"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="1c520-110">datetime</span><span class="sxs-lookup"><span data-stu-id="1c520-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="1c520-111">Primário</span><span class="sxs-lookup"><span data-stu-id="1c520-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="1c520-p101">Horário em que o agente de QoE (Qualidade de Excelência) recebe o primeiro relatório do chamador ou receptor. Usado em conjunto com SessionSeq para identificar exclusivamente uma sessão.</span><span class="sxs-lookup"><span data-stu-id="1c520-p101">Time when the Quality of Excellence (QoE) agent receives the first report from either caller or callee. Used in conjunction with SessionSeq to uniquely identify a session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1c520-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="1c520-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="1c520-115">int</span><span class="sxs-lookup"><span data-stu-id="1c520-115">int</span></span></p></td>
<td><p><span data-ttu-id="1c520-116">Primário</span><span class="sxs-lookup"><span data-stu-id="1c520-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="1c520-117">Número de sequência para diferenciar sessões quando tiverem o mesmo ConferenceDateTime.</span><span class="sxs-lookup"><span data-stu-id="1c520-117">Sequence number to differentiate sessions when they have the same ConferenceDateTime.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1c520-118"><strong>DialogID</strong></span><span class="sxs-lookup"><span data-stu-id="1c520-118"><strong>DialogID</strong></span></span></p></td>
<td><p><span data-ttu-id="1c520-119">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="1c520-119">varchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1c520-120">ID da caixa de diálogo que é globalmente exclusiva.</span><span class="sxs-lookup"><span data-stu-id="1c520-120">Dialog ID which is globally unique.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1c520-121"><strong>DialogIDChecksum</strong></span><span class="sxs-lookup"><span data-stu-id="1c520-121"><strong>DialogIDChecksum</strong></span></span></p></td>
<td><p><span data-ttu-id="1c520-122">int</span><span class="sxs-lookup"><span data-stu-id="1c520-122">int</span></span></p></td>
<td><p><span data-ttu-id="1c520-123">index</span><span class="sxs-lookup"><span data-stu-id="1c520-123">index</span></span></p></td>
<td><p><span data-ttu-id="1c520-124">Soma de verificação da ID da Caixa de Diálogo.</span><span class="sxs-lookup"><span data-stu-id="1c520-124">Checksum of the Dialog ID.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

