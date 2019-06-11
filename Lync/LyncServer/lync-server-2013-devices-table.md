---
title: 'Lync Server 2013: Tabela Devices'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Devices table
ms:assetid: 532e2280-4bbc-4a6c-93da-45d9f80a30a0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398351(v=OCS.15)
ms:contentKeyID: 48184169
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0f78e0b4ba3bb5271a2de43e423dfa4b3baf17cf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829414"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="devices-table-in-lync-server-2013"></a><span data-ttu-id="88b3c-102">Tabela Devices no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="88b3c-102">Devices table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="88b3c-103">_**Tópico da última modificação:** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="88b3c-103">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="88b3c-104">A tabela dispositivos é uma tabela de suporte.</span><span class="sxs-lookup"><span data-stu-id="88b3c-104">The Devices table is a supporting table.</span></span> <span data-ttu-id="88b3c-105">Cada registro armazena informações sobre um dispositivo (telefone de mesa).</span><span class="sxs-lookup"><span data-stu-id="88b3c-105">Each record stores information about one device (desk phone).</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="88b3c-106">Coluna</span><span class="sxs-lookup"><span data-stu-id="88b3c-106">Column</span></span></th>
<th><span data-ttu-id="88b3c-107">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="88b3c-107">Data Type</span></span></th>
<th><span data-ttu-id="88b3c-108">Chave/índice</span><span class="sxs-lookup"><span data-stu-id="88b3c-108">Key/Index</span></span></th>
<th><span data-ttu-id="88b3c-109">Detalhes</span><span class="sxs-lookup"><span data-stu-id="88b3c-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="88b3c-110"><strong>DeviceId</strong></span><span class="sxs-lookup"><span data-stu-id="88b3c-110"><strong>DeviceId</strong></span></span></p></td>
<td><p><span data-ttu-id="88b3c-111">int</span><span class="sxs-lookup"><span data-stu-id="88b3c-111">int</span></span></p></td>
<td><p><span data-ttu-id="88b3c-112">Primária</span><span class="sxs-lookup"><span data-stu-id="88b3c-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="88b3c-113">Número exclusivo que identifica esta versão de hardware.</span><span class="sxs-lookup"><span data-stu-id="88b3c-113">Unique number identifying this hardware version.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88b3c-114"><strong>ManufacturerId</strong></span><span class="sxs-lookup"><span data-stu-id="88b3c-114"><strong>ManufacturerId</strong></span></span></p></td>
<td><p><span data-ttu-id="88b3c-115">int</span><span class="sxs-lookup"><span data-stu-id="88b3c-115">int</span></span></p></td>
<td><p><span data-ttu-id="88b3c-116">Exterior</span><span class="sxs-lookup"><span data-stu-id="88b3c-116">Foreign</span></span></p></td>
<td><p><span data-ttu-id="88b3c-117">Fabricante do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="88b3c-117">Manufacturer of this device.</span></span> <span data-ttu-id="88b3c-118">Consulte a <a href="lync-server-2013-manufacturers-table.md">tabela fabricantes no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="88b3c-118">See the <a href="lync-server-2013-manufacturers-table.md">Manufacturers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88b3c-119"><strong>HardwareVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="88b3c-119"><strong>HardwareVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="88b3c-120">int</span><span class="sxs-lookup"><span data-stu-id="88b3c-120">int</span></span></p></td>
<td><p><span data-ttu-id="88b3c-121">Exterior</span><span class="sxs-lookup"><span data-stu-id="88b3c-121">Foreign</span></span></p></td>
<td><p><span data-ttu-id="88b3c-122">Versão de hardware deste dispositivo.</span><span class="sxs-lookup"><span data-stu-id="88b3c-122">Hardware version of this device.</span></span> <span data-ttu-id="88b3c-123">Consulte a <a href="lync-server-2013-hardwareversions-table.md">tabela HardwareVersions no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="88b3c-123">See the <a href="lync-server-2013-hardwareversions-table.md">HardwareVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88b3c-124"><strong>MacAddress</strong></span><span class="sxs-lookup"><span data-stu-id="88b3c-124"><strong>MacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="88b3c-125">bigint</span><span class="sxs-lookup"><span data-stu-id="88b3c-125">bigint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="88b3c-126">Endereço MAC</span><span class="sxs-lookup"><span data-stu-id="88b3c-126">MAC Address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

