---
title: 'Lync Server 2013: tabela de dispositivos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Device table
ms:assetid: d5a4f777-bc12-4ce8-bc0d-867d5e22b436
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398930(v=OCS.15)
ms:contentKeyID: 48185544
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8bd5b62059329d9a2277e28f1a2ae08c25384bde
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48522428"
---
# <a name="device-table-in-lync-server-2013"></a><span data-ttu-id="f326c-102">Tabela de dispositivos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f326c-102">Device table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f326c-103">_**Última modificação do tópico:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="f326c-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="f326c-p101">A tabela Device é uma tabela de suporte que armazena informações sobre os vários dispositivos de captura ou renderização. Cada registro na tabela representa um dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f326c-p101">The Device table is a supporting table that stores information about the various capture or render devices. Each record in the table represents one device.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f326c-106"><strong>Coluna</strong></span><span class="sxs-lookup"><span data-stu-id="f326c-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="f326c-107"><strong>Tipo de dados</strong></span><span class="sxs-lookup"><span data-stu-id="f326c-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="f326c-108"><strong>Chave/índice</strong></span><span class="sxs-lookup"><span data-stu-id="f326c-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="f326c-109"><strong>Detalhes</strong></span><span class="sxs-lookup"><span data-stu-id="f326c-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f326c-110"><strong>DeviceKey</strong></span><span class="sxs-lookup"><span data-stu-id="f326c-110"><strong>DeviceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="f326c-111">int</span><span class="sxs-lookup"><span data-stu-id="f326c-111">int</span></span></p></td>
<td><p><span data-ttu-id="f326c-112">Primário</span><span class="sxs-lookup"><span data-stu-id="f326c-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="f326c-113">Número exclusivo que identifica este dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f326c-113">Unique number identifying this device.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f326c-114"><strong>DeviceName</strong></span><span class="sxs-lookup"><span data-stu-id="f326c-114"><strong>DeviceName</strong></span></span></p></td>
<td><p><span data-ttu-id="f326c-115">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="f326c-115">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f326c-116">DeviceName + DeviceType é exclusivo</span><span class="sxs-lookup"><span data-stu-id="f326c-116">DeviceName + DeviceType is unique</span></span></p></td>
<td><p><span data-ttu-id="f326c-117">Nome do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f326c-117">Device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f326c-118"><strong>DeviceType</strong></span><span class="sxs-lookup"><span data-stu-id="f326c-118"><strong>DeviceType</strong></span></span></p></td>
<td><p><span data-ttu-id="f326c-119">bits</span><span class="sxs-lookup"><span data-stu-id="f326c-119">bit</span></span></p></td>
<td><p><span data-ttu-id="f326c-120">DeviceName + DeviceType é exclusivo</span><span class="sxs-lookup"><span data-stu-id="f326c-120">DeviceName + DeviceType is unique</span></span></p></td>
<td><p><span data-ttu-id="f326c-p102">Tipo de dispositivo. 1 é um dispositivo de captura, 0 é um dispositivo de processamento.</span><span class="sxs-lookup"><span data-stu-id="f326c-p102">Device type. 1 is a capture device, 0 is a render device.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

