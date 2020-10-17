---
title: 'Lync Server 2013: tabela DeviceDriver'
description: 'Lync Server 2013: tabela DeviceDriver.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DeviceDriver table
ms:assetid: ca91a0b4-98c0-49f6-af9d-7d0f8ac75f1a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398844(v=OCS.15)
ms:contentKeyID: 48185449
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3d81e2e27ff5196112c6057c429f924e5b1c3e4b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565967"
---
# <a name="devicedriver-table-in-lync-server-2013"></a><span data-ttu-id="47707-103">Tabela DeviceDriver no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="47707-103">DeviceDriver table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="47707-104">_**Última modificação do tópico:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="47707-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="47707-105">A tabela DeviceDriver é uma tabela de suporte.</span><span class="sxs-lookup"><span data-stu-id="47707-105">The DeviceDriver table is a supporting table.</span></span> <span data-ttu-id="47707-106">Cada registro representa um driver usado por um dispositivo de captura ou um dispositivo de renderização.</span><span class="sxs-lookup"><span data-stu-id="47707-106">Each record represents a driver used by either a capture device or render device.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="47707-107"><strong>Coluna</strong></span><span class="sxs-lookup"><span data-stu-id="47707-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="47707-108"><strong>Tipo de dados</strong></span><span class="sxs-lookup"><span data-stu-id="47707-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="47707-109"><strong>Chave/índice</strong></span><span class="sxs-lookup"><span data-stu-id="47707-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="47707-110"><strong>Detalhes</strong></span><span class="sxs-lookup"><span data-stu-id="47707-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="47707-111"><strong>DeviceDriverKey</strong></span><span class="sxs-lookup"><span data-stu-id="47707-111"><strong>DeviceDriverKey</strong></span></span></p></td>
<td><p><span data-ttu-id="47707-112">int</span><span class="sxs-lookup"><span data-stu-id="47707-112">int</span></span></p></td>
<td><p><span data-ttu-id="47707-113">Primário</span><span class="sxs-lookup"><span data-stu-id="47707-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="47707-114">Número exclusivo que identifica este registro de driver de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="47707-114">Unique number identifying this device driver record.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47707-115"><strong>DeviceDriver</strong></span><span class="sxs-lookup"><span data-stu-id="47707-115"><strong>DeviceDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="47707-116">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="47707-116">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="47707-117">diferente</span><span class="sxs-lookup"><span data-stu-id="47707-117">unique</span></span></p></td>
<td><p><span data-ttu-id="47707-118">Nome do driver de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="47707-118">Device driver name.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

