---
title: 'Lync Server 2013: tabela de dispositivos'
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
ms.openlocfilehash: c5fdc4c3b20bdd60d2c8013b79a15bdfd30b56af
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536928"
---
# <a name="devices-table-in-lync-server-2013"></a><span data-ttu-id="1b3bd-102">Tabela de dispositivos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1b3bd-102">Devices table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1b3bd-103">_**Última modificação do tópico:** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="1b3bd-103">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="1b3bd-104">A tabela de dispositivos é uma tabela de suporte.</span><span class="sxs-lookup"><span data-stu-id="1b3bd-104">The Devices table is a supporting table.</span></span> <span data-ttu-id="1b3bd-105">Cada registro armazena informações sobre um dispositivo (telefone de mesa).</span><span class="sxs-lookup"><span data-stu-id="1b3bd-105">Each record stores information about one device (desk phone).</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1b3bd-106">Coluna</span><span class="sxs-lookup"><span data-stu-id="1b3bd-106">Column</span></span></th>
<th><span data-ttu-id="1b3bd-107">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="1b3bd-107">Data Type</span></span></th>
<th><span data-ttu-id="1b3bd-108">Chave/índice</span><span class="sxs-lookup"><span data-stu-id="1b3bd-108">Key/Index</span></span></th>
<th><span data-ttu-id="1b3bd-109">Detalhes</span><span class="sxs-lookup"><span data-stu-id="1b3bd-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1b3bd-110"><strong>DeviceId</strong></span><span class="sxs-lookup"><span data-stu-id="1b3bd-110"><strong>DeviceId</strong></span></span></p></td>
<td><p><span data-ttu-id="1b3bd-111">int</span><span class="sxs-lookup"><span data-stu-id="1b3bd-111">int</span></span></p></td>
<td><p><span data-ttu-id="1b3bd-112">Primário</span><span class="sxs-lookup"><span data-stu-id="1b3bd-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="1b3bd-113">Número exclusivo que identifica esta versão de hardware.</span><span class="sxs-lookup"><span data-stu-id="1b3bd-113">Unique number identifying this hardware version.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b3bd-114"><strong>ManufacturerID</strong></span><span class="sxs-lookup"><span data-stu-id="1b3bd-114"><strong>ManufacturerId</strong></span></span></p></td>
<td><p><span data-ttu-id="1b3bd-115">int</span><span class="sxs-lookup"><span data-stu-id="1b3bd-115">int</span></span></p></td>
<td><p><span data-ttu-id="1b3bd-116">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="1b3bd-116">Foreign</span></span></p></td>
<td><p><span data-ttu-id="1b3bd-117">Fabricante deste dispositivo.</span><span class="sxs-lookup"><span data-stu-id="1b3bd-117">Manufacturer of this device.</span></span> <span data-ttu-id="1b3bd-118">Consulte a <a href="lync-server-2013-manufacturers-table.md">tabela fabricantes no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="1b3bd-118">See the <a href="lync-server-2013-manufacturers-table.md">Manufacturers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b3bd-119"><strong>HardwareVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="1b3bd-119"><strong>HardwareVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="1b3bd-120">int</span><span class="sxs-lookup"><span data-stu-id="1b3bd-120">int</span></span></p></td>
<td><p><span data-ttu-id="1b3bd-121">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="1b3bd-121">Foreign</span></span></p></td>
<td><p><span data-ttu-id="1b3bd-122">Versão de hardware desse dispositivo.</span><span class="sxs-lookup"><span data-stu-id="1b3bd-122">Hardware version of this device.</span></span> <span data-ttu-id="1b3bd-123">Consulte a <a href="lync-server-2013-hardwareversions-table.md">tabela HardwareVersions no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="1b3bd-123">See the <a href="lync-server-2013-hardwareversions-table.md">HardwareVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b3bd-124"><strong>MacAddress</strong></span><span class="sxs-lookup"><span data-stu-id="1b3bd-124"><strong>MacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="1b3bd-125">bigint</span><span class="sxs-lookup"><span data-stu-id="1b3bd-125">bigint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b3bd-126">Endereço MAC</span><span class="sxs-lookup"><span data-stu-id="1b3bd-126">MAC Address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

