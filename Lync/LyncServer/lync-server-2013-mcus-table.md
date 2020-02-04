---
title: 'Lync Server 2013: Tabela Mcus'
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
ms.openlocfilehash: 522c7babbda63c550679dab1eb8eb03114417169
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737171"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mcus-table-in-lync-server-2013"></a><span data-ttu-id="3f0bb-102">Tabela Mcus no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3f0bb-102">Mcus table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3f0bb-103">_**Tópico da última modificação:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="3f0bb-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="3f0bb-104">A tabela MCUs é uma tabela de suporte.</span><span class="sxs-lookup"><span data-stu-id="3f0bb-104">The Mcus table is a supporting table.</span></span> <span data-ttu-id="3f0bb-105">Cada registro armazena informações sobre um serviço de conferência.</span><span class="sxs-lookup"><span data-stu-id="3f0bb-105">Each record stores information about one conferencing service.</span></span> <span data-ttu-id="3f0bb-106">Eles podem incluir o serviço de conferência de mensagem instantânea e o serviço de conferência de telefonia (que são executados como processos em servidores front-end) e o serviço de conferência via Web e o serviço de conferência A/V.</span><span class="sxs-lookup"><span data-stu-id="3f0bb-106">These can include the IM Conferencing service and the Telephony Conferencing service (which run as processes on front-end servers), and the Web Conferencing service and A/V Conferencing service.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3f0bb-107">Coluna</span><span class="sxs-lookup"><span data-stu-id="3f0bb-107">Column</span></span></th>
<th><span data-ttu-id="3f0bb-108">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="3f0bb-108">Data Type</span></span></th>
<th><span data-ttu-id="3f0bb-109">Chave/índice</span><span class="sxs-lookup"><span data-stu-id="3f0bb-109">Key/Index</span></span></th>
<th><span data-ttu-id="3f0bb-110">Detalhes</span><span class="sxs-lookup"><span data-stu-id="3f0bb-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3f0bb-111"><strong>McuId</strong></span><span class="sxs-lookup"><span data-stu-id="3f0bb-111"><strong>McuId</strong></span></span></p></td>
<td><p><span data-ttu-id="3f0bb-112">int</span><span class="sxs-lookup"><span data-stu-id="3f0bb-112">int</span></span></p></td>
<td><p><span data-ttu-id="3f0bb-113">Primária</span><span class="sxs-lookup"><span data-stu-id="3f0bb-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="3f0bb-114">Número exclusivo que identifica esse servidor de conferência.</span><span class="sxs-lookup"><span data-stu-id="3f0bb-114">Unique number identifying this conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f0bb-115"><strong>McuUri</strong></span><span class="sxs-lookup"><span data-stu-id="3f0bb-115"><strong>McuUri</strong></span></span></p></td>
<td><p><span data-ttu-id="3f0bb-116">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="3f0bb-116">nvarchar(450)</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f0bb-117"><strong>McuTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="3f0bb-117"><strong>McuTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="3f0bb-118">inyint</span><span class="sxs-lookup"><span data-stu-id="3f0bb-118">inyint</span></span></p></td>
<td><p><span data-ttu-id="3f0bb-119"> Exterior</span><span class="sxs-lookup"><span data-stu-id="3f0bb-119"> Foreign</span></span></p></td>
<td><p><span data-ttu-id="3f0bb-120">Tipo de servidor de conferência, como conf: Chat (para IMs) ou conf: Audio-Video.</span><span class="sxs-lookup"><span data-stu-id="3f0bb-120">Conferencing server type, such as conf:chat (for IMs) or conf:audio-video.</span></span> <span data-ttu-id="3f0bb-121">Consulte a <a href="lync-server-2013-uritypes-table.md">tabela UriTypes no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="3f0bb-121">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

