---
title: 'Lync Server 2013: tabela NetworkConnectionDetail'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: NetworkConnectionDetail table
ms:assetid: b48cc9a6-5232-48b5-bd20-53b68229336b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205185(v=OCS.15)
ms:contentKeyID: 48185170
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bb192385cfd5d04712b0e66169326aedd6c0f1b1
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42128324"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="networkconnectiondetail-table-in-lync-server-2013"></a><span data-ttu-id="a7b67-102">Tabela NetworkConnectionDetail no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a7b67-102">NetworkConnectionDetail table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a7b67-103">_**Última modificação do tópico:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="a7b67-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="a7b67-104">A tabela NetworkConnectionDetail mapeia os tipos de conexão de rede em identificadores de conexão de rede usados em outro lugar no banco de dados de Qualidade da Experiência.</span><span class="sxs-lookup"><span data-stu-id="a7b67-104">The NetworkConnectionDetail table maps network connection types to the network connection identifiers used elsewhere in the Quality of Experience database.</span></span> <span data-ttu-id="a7b67-105">Esta tabela foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a7b67-105">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a7b67-106"><strong>Coluna</strong></span><span class="sxs-lookup"><span data-stu-id="a7b67-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="a7b67-107"><strong>Tipo de dados</strong></span><span class="sxs-lookup"><span data-stu-id="a7b67-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="a7b67-108"><strong>Chave/índice</strong></span><span class="sxs-lookup"><span data-stu-id="a7b67-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="a7b67-109"><strong>Detalhes</strong></span><span class="sxs-lookup"><span data-stu-id="a7b67-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a7b67-110"><strong>NetworkConnectionDetailKey</strong></span><span class="sxs-lookup"><span data-stu-id="a7b67-110"><strong>NetworkConnectionDetailKey</strong></span></span></p></td>
<td><p><span data-ttu-id="a7b67-111">tinyint</span><span class="sxs-lookup"><span data-stu-id="a7b67-111">tinyint</span></span></p></td>
<td><p><span data-ttu-id="a7b67-112">Primário</span><span class="sxs-lookup"><span data-stu-id="a7b67-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="a7b67-113">Identificador exclusivo do tipo de conexão de rede.</span><span class="sxs-lookup"><span data-stu-id="a7b67-113">Unique identifier for the network connection type.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7b67-114"><strong>NetworkConnectionDetail</strong></span><span class="sxs-lookup"><span data-stu-id="a7b67-114"><strong>NetworkConnectionDetail</strong></span></span></p></td>
<td><p><span data-ttu-id="a7b67-115">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="a7b67-115">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a7b67-116">Diferente</span><span class="sxs-lookup"><span data-stu-id="a7b67-116">Unique</span></span></p></td>
<td><p><span data-ttu-id="a7b67-p102">Tipo de conexão de rede que corresponde a NetworkConnectionDetailKey. Os valores permitidos são:</span><span class="sxs-lookup"><span data-stu-id="a7b67-p102">Network connection type that corresponds to the NetworkConnectionDetailKey. Allowed values are:</span></span></p>
<ol>
<li><p><span data-ttu-id="a7b67-119">0 -- Com fio</span><span class="sxs-lookup"><span data-stu-id="a7b67-119">0 -- Wired</span></span></p></li>
<li><p><span data-ttu-id="a7b67-120">1 -- Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="a7b67-120">1 -- WiFi</span></span></p></li>
<li><p><span data-ttu-id="a7b67-121">2 -- Ethernet</span><span class="sxs-lookup"><span data-stu-id="a7b67-121">2 -- Ethernet</span></span></p></li>
</ol></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

