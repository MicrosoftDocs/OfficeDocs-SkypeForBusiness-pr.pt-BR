---
title: 'Lync Server 2013: tabela IPAddress'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IPAddress table
ms:assetid: 8ec018b9-158e-4bbe-ad46-869e60315555
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205077(v=OCS.15)
ms:contentKeyID: 48184771
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2be3760d16053e07010f4be1df39adbbd39130a6
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146094"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="ipaddress-table-in-lync-server-2013"></a><span data-ttu-id="98b9e-102">Tabela IPAddress no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="98b9e-102">IPAddress table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="98b9e-103">_**Última modificação do tópico:** 2012-10-17_</span><span class="sxs-lookup"><span data-stu-id="98b9e-103">_**Topic Last Modified:** 2012-10-17_</span></span>

<span data-ttu-id="98b9e-104">A tabela IPAddress mapeia endereços IP para os identificadores de endereço IP únicos usados em outros locais no banco de dados de qualidade da experiência.</span><span class="sxs-lookup"><span data-stu-id="98b9e-104">The IPAddress table maps IP addresses to the unique IP address identifiers used elsewhere in the Quality of Experience database.</span></span> <span data-ttu-id="98b9e-105">Esta tabela foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="98b9e-105">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="98b9e-106"><strong>Coluna</strong></span><span class="sxs-lookup"><span data-stu-id="98b9e-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="98b9e-107"><strong>Tipo de dados</strong></span><span class="sxs-lookup"><span data-stu-id="98b9e-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="98b9e-108"><strong>Chave/índice</strong></span><span class="sxs-lookup"><span data-stu-id="98b9e-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="98b9e-109"><strong>Detalhes</strong></span><span class="sxs-lookup"><span data-stu-id="98b9e-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="98b9e-110"><strong>IPAddressKey</strong></span><span class="sxs-lookup"><span data-stu-id="98b9e-110"><strong>IPAddressKey</strong></span></span></p></td>
<td><p><span data-ttu-id="98b9e-111">int</span><span class="sxs-lookup"><span data-stu-id="98b9e-111">int</span></span></p></td>
<td><p><span data-ttu-id="98b9e-112">Primário</span><span class="sxs-lookup"><span data-stu-id="98b9e-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="98b9e-113">Identificador exclusivo do endereço IP especificado.</span><span class="sxs-lookup"><span data-stu-id="98b9e-113">Unique identifier for the specified IP address.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="98b9e-114"><strong>IPAddress</strong></span><span class="sxs-lookup"><span data-stu-id="98b9e-114"><strong>IPAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="98b9e-115">varchar (50)</span><span class="sxs-lookup"><span data-stu-id="98b9e-115">varchar(50)</span></span></p></td>
<td><p><span data-ttu-id="98b9e-116">Diferente</span><span class="sxs-lookup"><span data-stu-id="98b9e-116">Unique</span></span></p></td>
<td><p><span data-ttu-id="98b9e-117">Endereço IP exclusivo (por exemplo, 189.168.1.1) que mapeia para o IpAddressKey.</span><span class="sxs-lookup"><span data-stu-id="98b9e-117">Unique IP address (for example, 189.168.1.1) that maps to the IpAddressKey.</span></span> <span data-ttu-id="98b9e-118">Pode ser um endereço IPv4 ou IPv6.</span><span class="sxs-lookup"><span data-stu-id="98b9e-118">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

