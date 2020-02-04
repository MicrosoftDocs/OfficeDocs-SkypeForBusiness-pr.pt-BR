---
title: 'Lync Server 2013: Tabela Devices'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Devices table
ms:assetid: 532e2280-4bbc-4a6c-93da-45d9f80a30a0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398351(v=OCS.15)
ms:contentKeyID: 48184169
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 381b03fc5680276a64fc327f423f74c6773c2ed3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762349"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="devices-table-in-lync-server-2013"></a><span data-ttu-id="51cb6-102">Tabela Devices no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="51cb6-102">Devices table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="51cb6-103">_**Tópico da última modificação:** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="51cb6-103">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="51cb6-104">A tabela dispositivos é uma tabela de suporte.</span><span class="sxs-lookup"><span data-stu-id="51cb6-104">The Devices table is a supporting table.</span></span> <span data-ttu-id="51cb6-105">Cada registro armazena informações sobre um dispositivo (telefone de mesa).</span><span class="sxs-lookup"><span data-stu-id="51cb6-105">Each record stores information about one device (desk phone).</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="51cb6-106">Coluna</span><span class="sxs-lookup"><span data-stu-id="51cb6-106">Column</span></span></th>
<th><span data-ttu-id="51cb6-107">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="51cb6-107">Data Type</span></span></th>
<th><span data-ttu-id="51cb6-108">Chave/índice</span><span class="sxs-lookup"><span data-stu-id="51cb6-108">Key/Index</span></span></th>
<th><span data-ttu-id="51cb6-109">Detalhes</span><span class="sxs-lookup"><span data-stu-id="51cb6-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="51cb6-110"><strong>DeviceId</strong></span><span class="sxs-lookup"><span data-stu-id="51cb6-110"><strong>DeviceId</strong></span></span></p></td>
<td><p><span data-ttu-id="51cb6-111">int</span><span class="sxs-lookup"><span data-stu-id="51cb6-111">int</span></span></p></td>
<td><p><span data-ttu-id="51cb6-112">Primária</span><span class="sxs-lookup"><span data-stu-id="51cb6-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="51cb6-113">Número exclusivo que identifica esta versão de hardware.</span><span class="sxs-lookup"><span data-stu-id="51cb6-113">Unique number identifying this hardware version.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51cb6-114"><strong>ManufacturerId</strong></span><span class="sxs-lookup"><span data-stu-id="51cb6-114"><strong>ManufacturerId</strong></span></span></p></td>
<td><p><span data-ttu-id="51cb6-115">int</span><span class="sxs-lookup"><span data-stu-id="51cb6-115">int</span></span></p></td>
<td><p><span data-ttu-id="51cb6-116">Exterior</span><span class="sxs-lookup"><span data-stu-id="51cb6-116">Foreign</span></span></p></td>
<td><p><span data-ttu-id="51cb6-117">Fabricante do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="51cb6-117">Manufacturer of this device.</span></span> <span data-ttu-id="51cb6-118">Consulte a <a href="lync-server-2013-manufacturers-table.md">tabela fabricantes no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="51cb6-118">See the <a href="lync-server-2013-manufacturers-table.md">Manufacturers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51cb6-119"><strong>HardwareVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="51cb6-119"><strong>HardwareVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="51cb6-120">int</span><span class="sxs-lookup"><span data-stu-id="51cb6-120">int</span></span></p></td>
<td><p><span data-ttu-id="51cb6-121">Exterior</span><span class="sxs-lookup"><span data-stu-id="51cb6-121">Foreign</span></span></p></td>
<td><p><span data-ttu-id="51cb6-122">Versão de hardware deste dispositivo.</span><span class="sxs-lookup"><span data-stu-id="51cb6-122">Hardware version of this device.</span></span> <span data-ttu-id="51cb6-123">Consulte a <a href="lync-server-2013-hardwareversions-table.md">tabela HardwareVersions no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="51cb6-123">See the <a href="lync-server-2013-hardwareversions-table.md">HardwareVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51cb6-124"><strong>MacAddress</strong></span><span class="sxs-lookup"><span data-stu-id="51cb6-124"><strong>MacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="51cb6-125">bigint</span><span class="sxs-lookup"><span data-stu-id="51cb6-125">bigint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="51cb6-126">Endereço MAC</span><span class="sxs-lookup"><span data-stu-id="51cb6-126">MAC Address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

