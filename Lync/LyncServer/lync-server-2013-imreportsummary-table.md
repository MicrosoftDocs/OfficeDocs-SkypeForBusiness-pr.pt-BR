---
title: 'Lync Server 2013: tabela IMReportSummary'
description: 'Lync Server 2013: tabela IMReportSummary.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IMReportSummary table
ms:assetid: 27ff9453-53f2-4fae-b637-70a086c9df96
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204753(v=OCS.15)
ms:contentKeyID: 48183673
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dfafa81d1605845b29a3627321fcbc0f72ca7ac7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547737"
---
# <a name="imreportsummary-table-in-lync-server-2013"></a><span data-ttu-id="72065-103">Tabela IMReportSummary no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="72065-103">IMReportSummary table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="72065-104">_**Última modificação do tópico:** 2012-08-20_</span><span class="sxs-lookup"><span data-stu-id="72065-104">_**Topic Last Modified:** 2012-08-20_</span></span>

<span data-ttu-id="72065-105">O IMReportSummaryTable oferece um relatório geral sobre as sessões de mensagem instantânea mantidas em uma organização.</span><span class="sxs-lookup"><span data-stu-id="72065-105">The IMReportSummaryTable provides an overall report on the instant messaging sessions held in an organization.</span></span> <span data-ttu-id="72065-106">Esta tabela foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="72065-106">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="72065-107">Coluna</span><span class="sxs-lookup"><span data-stu-id="72065-107">Column</span></span></th>
<th><span data-ttu-id="72065-108">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="72065-108">Data Type</span></span></th>
<th><span data-ttu-id="72065-109">Chave/índice</span><span class="sxs-lookup"><span data-stu-id="72065-109">Key/Index</span></span></th>
<th><span data-ttu-id="72065-110">Detalhes</span><span class="sxs-lookup"><span data-stu-id="72065-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="72065-111"><strong>StartTime</strong></span><span class="sxs-lookup"><span data-stu-id="72065-111"><strong>StartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="72065-112">datetime</span><span class="sxs-lookup"><span data-stu-id="72065-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="72065-113">Primário</span><span class="sxs-lookup"><span data-stu-id="72065-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="72065-114">Data e hora que a sessão de mensagem instantânea começou.</span><span class="sxs-lookup"><span data-stu-id="72065-114">Date and time that the instant messaging session began.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="72065-115"><strong>TimePeriod</strong></span><span class="sxs-lookup"><span data-stu-id="72065-115"><strong>TimePeriod</strong></span></span></p></td>
<td><p><span data-ttu-id="72065-116">Char (1)</span><span class="sxs-lookup"><span data-stu-id="72065-116">char(1)</span></span></p></td>
<td><p><span data-ttu-id="72065-117">Primário</span><span class="sxs-lookup"><span data-stu-id="72065-117">Primary</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="72065-118"><strong>PoolFQDN</strong></span><span class="sxs-lookup"><span data-stu-id="72065-118"><strong>PoolFQDN</strong></span></span></p></td>
<td><p><span data-ttu-id="72065-119">nvarchar (257)</span><span class="sxs-lookup"><span data-stu-id="72065-119">nvarchar(257)</span></span></p></td>
<td><p><span data-ttu-id="72065-120">Primário</span><span class="sxs-lookup"><span data-stu-id="72065-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="72065-121">Nome de domínio totalmente qualificado do pool hospedando a sessão.</span><span class="sxs-lookup"><span data-stu-id="72065-121">Fully qualified domain name of the pool hosting the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="72065-122"><strong>AuthType</strong></span><span class="sxs-lookup"><span data-stu-id="72065-122"><strong>AuthType</strong></span></span></p></td>
<td><p><span data-ttu-id="72065-123">int</span><span class="sxs-lookup"><span data-stu-id="72065-123">int</span></span></p></td>
<td><p><span data-ttu-id="72065-124">Primário</span><span class="sxs-lookup"><span data-stu-id="72065-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="72065-125">Prioridade (por exemplo, urgente ou não urgente) da chamada.</span><span class="sxs-lookup"><span data-stu-id="72065-125">Priority (for example, urgent or non-urgent) of the call.</span></span> <span data-ttu-id="72065-126">As informações de prioridade são armazenadas na <a href="lync-server-2013-callpriorities-table.md">tabela CallPriorities no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="72065-126">Priority information is stored in the <a href="lync-server-2013-callpriorities-table.md">CallPriorities table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="72065-127"><strong>SessionCount</strong></span><span class="sxs-lookup"><span data-stu-id="72065-127"><strong>SessionCount</strong></span></span></p></td>
<td><p><span data-ttu-id="72065-128">bigint</span><span class="sxs-lookup"><span data-stu-id="72065-128">bigint</span></span></p></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="72065-129"><strong>MsgCount</strong></span><span class="sxs-lookup"><span data-stu-id="72065-129"><strong>MsgCount</strong></span></span></p></td>
<td><p><span data-ttu-id="72065-130">bigint</span><span class="sxs-lookup"><span data-stu-id="72065-130">bigint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="72065-131">Número total de mensagens instantâneas trocadas durante a sessão.</span><span class="sxs-lookup"><span data-stu-id="72065-131">Total number of instant messages exchanged during the session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

