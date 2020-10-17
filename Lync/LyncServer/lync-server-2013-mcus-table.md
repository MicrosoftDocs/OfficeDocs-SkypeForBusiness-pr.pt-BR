---
title: 'Lync Server 2013: tabela MCUs'
description: 'Lync Server 2013: tabela MCUs.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Mcus table
ms:assetid: 271b7963-8fd8-4d92-a701-1a62aaf895ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425742(v=OCS.15)
ms:contentKeyID: 48183674
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b0b5d0bcbebb5efc1d767776b4581b18d9f2ed18
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556477"
---
# <a name="mcus-table-in-lync-server-2013"></a><span data-ttu-id="2c0cc-103">Tabela MCUs no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2c0cc-103">Mcus table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2c0cc-104">_**Última modificação do tópico:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="2c0cc-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="2c0cc-105">A tabela MCUs é uma tabela de suporte.</span><span class="sxs-lookup"><span data-stu-id="2c0cc-105">The Mcus table is a supporting table.</span></span> <span data-ttu-id="2c0cc-106">Cada registro armazena informações sobre um serviço de conferência.</span><span class="sxs-lookup"><span data-stu-id="2c0cc-106">Each record stores information about one conferencing service.</span></span> <span data-ttu-id="2c0cc-107">Podem incluir o serviço de conferência de mensagens instantâneas e o serviço de conferência de telefonia (que são executados como processos em servidores front-end) e o serviço de conferência da Web e o serviço de conferência A/V.</span><span class="sxs-lookup"><span data-stu-id="2c0cc-107">These can include the IM Conferencing service and the Telephony Conferencing service (which run as processes on front-end servers), and the Web Conferencing service and A/V Conferencing service.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2c0cc-108">Coluna</span><span class="sxs-lookup"><span data-stu-id="2c0cc-108">Column</span></span></th>
<th><span data-ttu-id="2c0cc-109">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="2c0cc-109">Data Type</span></span></th>
<th><span data-ttu-id="2c0cc-110">Chave/índice</span><span class="sxs-lookup"><span data-stu-id="2c0cc-110">Key/Index</span></span></th>
<th><span data-ttu-id="2c0cc-111">Detalhes</span><span class="sxs-lookup"><span data-stu-id="2c0cc-111">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2c0cc-112"><strong>McuId</strong></span><span class="sxs-lookup"><span data-stu-id="2c0cc-112"><strong>McuId</strong></span></span></p></td>
<td><p><span data-ttu-id="2c0cc-113">int</span><span class="sxs-lookup"><span data-stu-id="2c0cc-113">int</span></span></p></td>
<td><p><span data-ttu-id="2c0cc-114">Primário</span><span class="sxs-lookup"><span data-stu-id="2c0cc-114">Primary</span></span></p></td>
<td><p><span data-ttu-id="2c0cc-115">Número exclusivo que identifica este servidor de conferência.</span><span class="sxs-lookup"><span data-stu-id="2c0cc-115">Unique number identifying this conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2c0cc-116"><strong>McuUri</strong></span><span class="sxs-lookup"><span data-stu-id="2c0cc-116"><strong>McuUri</strong></span></span></p></td>
<td><p><span data-ttu-id="2c0cc-117">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="2c0cc-117">nvarchar(450)</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2c0cc-118"><strong>McuTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="2c0cc-118"><strong>McuTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="2c0cc-119">inyint</span><span class="sxs-lookup"><span data-stu-id="2c0cc-119">inyint</span></span></p></td>
<td><p><span data-ttu-id="2c0cc-120"> Estrangeira</span><span class="sxs-lookup"><span data-stu-id="2c0cc-120"> Foreign</span></span></p></td>
<td><p><span data-ttu-id="2c0cc-121">Tipo de servidor de conferência, como conf: Chat (para IMs) ou conf: Audio-Video.</span><span class="sxs-lookup"><span data-stu-id="2c0cc-121">Conferencing server type, such as conf:chat (for IMs) or conf:audio-video.</span></span> <span data-ttu-id="2c0cc-122">Consulte a <a href="lync-server-2013-uritypes-table.md">tabela UriTypes no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="2c0cc-122">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

