---
title: 'Lync Server 2013: tabela IMReportSummary'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: IMReportSummary table
ms:assetid: 27ff9453-53f2-4fae-b637-70a086c9df96
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204753(v=OCS.15)
ms:contentKeyID: 48183673
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c2254bafe059cc1a4bc6436580e9d604711f5fb3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829021"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="imreportsummary-table-in-lync-server-2013"></a><span data-ttu-id="ab7b0-102">Tabela IMReportSummary no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ab7b0-102">IMReportSummary table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ab7b0-103">_**Tópico da última modificação:** 2012-08-20_</span><span class="sxs-lookup"><span data-stu-id="ab7b0-103">_**Topic Last Modified:** 2012-08-20_</span></span>

<span data-ttu-id="ab7b0-104">O IMReportSummaryTable fornece um relatório geral sobre as sessões de mensagens instantâneas contidas em uma organização.</span><span class="sxs-lookup"><span data-stu-id="ab7b0-104">The IMReportSummaryTable provides an overall report on the instant messaging sessions held in an organization.</span></span> <span data-ttu-id="ab7b0-105">Esta tabela foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ab7b0-105">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ab7b0-106">Coluna</span><span class="sxs-lookup"><span data-stu-id="ab7b0-106">Column</span></span></th>
<th><span data-ttu-id="ab7b0-107">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="ab7b0-107">Data Type</span></span></th>
<th><span data-ttu-id="ab7b0-108">Chave/índice</span><span class="sxs-lookup"><span data-stu-id="ab7b0-108">Key/Index</span></span></th>
<th><span data-ttu-id="ab7b0-109">Detalhes</span><span class="sxs-lookup"><span data-stu-id="ab7b0-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ab7b0-110"><strong>StartTime </strong></span><span class="sxs-lookup"><span data-stu-id="ab7b0-110"><strong>StartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="ab7b0-111">datetime</span><span class="sxs-lookup"><span data-stu-id="ab7b0-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="ab7b0-112">Primária</span><span class="sxs-lookup"><span data-stu-id="ab7b0-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="ab7b0-113">Data e hora de início da sessão de mensagens instantâneas.</span><span class="sxs-lookup"><span data-stu-id="ab7b0-113">Date and time that the instant messaging session began.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab7b0-114"><strong>Período de tempo</strong></span><span class="sxs-lookup"><span data-stu-id="ab7b0-114"><strong>TimePeriod</strong></span></span></p></td>
<td><p><span data-ttu-id="ab7b0-115">caractere (1)</span><span class="sxs-lookup"><span data-stu-id="ab7b0-115">char(1)</span></span></p></td>
<td><p><span data-ttu-id="ab7b0-116">Primária</span><span class="sxs-lookup"><span data-stu-id="ab7b0-116">Primary</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab7b0-117"><strong>PoolFQDN</strong></span><span class="sxs-lookup"><span data-stu-id="ab7b0-117"><strong>PoolFQDN</strong></span></span></p></td>
<td><p><span data-ttu-id="ab7b0-118">nvarchar (257)</span><span class="sxs-lookup"><span data-stu-id="ab7b0-118">nvarchar(257)</span></span></p></td>
<td><p><span data-ttu-id="ab7b0-119">Primária</span><span class="sxs-lookup"><span data-stu-id="ab7b0-119">Primary</span></span></p></td>
<td><p><span data-ttu-id="ab7b0-120">Nome de domínio totalmente qualificado do pool que hospeda a sessão.</span><span class="sxs-lookup"><span data-stu-id="ab7b0-120">Fully qualified domain name of the pool hosting the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab7b0-121"><strong>AuthType</strong></span><span class="sxs-lookup"><span data-stu-id="ab7b0-121"><strong>AuthType</strong></span></span></p></td>
<td><p><span data-ttu-id="ab7b0-122">int</span><span class="sxs-lookup"><span data-stu-id="ab7b0-122">int</span></span></p></td>
<td><p><span data-ttu-id="ab7b0-123">Primária</span><span class="sxs-lookup"><span data-stu-id="ab7b0-123">Primary</span></span></p></td>
<td><p><span data-ttu-id="ab7b0-124">Prioridade (por exemplo, urgente ou não urgente) da chamada.</span><span class="sxs-lookup"><span data-stu-id="ab7b0-124">Priority (for example, urgent or non-urgent) of the call.</span></span> <span data-ttu-id="ab7b0-125">As informações de prioridade são armazenadas na <a href="lync-server-2013-callpriorities-table.md">tabela CallPriorities no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="ab7b0-125">Priority information is stored in the <a href="lync-server-2013-callpriorities-table.md">CallPriorities table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab7b0-126"><strong>SessionCount</strong></span><span class="sxs-lookup"><span data-stu-id="ab7b0-126"><strong>SessionCount</strong></span></span></p></td>
<td><p><span data-ttu-id="ab7b0-127">bigint</span><span class="sxs-lookup"><span data-stu-id="ab7b0-127">bigint</span></span></p></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab7b0-128"><strong>MsgCount</strong></span><span class="sxs-lookup"><span data-stu-id="ab7b0-128"><strong>MsgCount</strong></span></span></p></td>
<td><p><span data-ttu-id="ab7b0-129">bigint</span><span class="sxs-lookup"><span data-stu-id="ab7b0-129">bigint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab7b0-130">Número total de mensagens instantâneas trocadas durante a sessão.</span><span class="sxs-lookup"><span data-stu-id="ab7b0-130">Total number of instant messages exchanged during the session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

