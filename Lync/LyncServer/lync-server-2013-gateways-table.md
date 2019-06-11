---
title: 'Lync Server 2013: Tabela Gateways'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Gateways table
ms:assetid: a909daad-d137-45e0-b149-1de9f8e1e029
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412795(v=OCS.15)
ms:contentKeyID: 48185034
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a4f26a45d992d716b94cb7353f813c038272b132
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829131"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="gateways-table-in-lync-server-2013"></a><span data-ttu-id="7c0d8-102">Tabela Gateways no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7c0d8-102">Gateways table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7c0d8-103">_**Tópico da última modificação:** 2010-11-05_</span><span class="sxs-lookup"><span data-stu-id="7c0d8-103">_**Topic Last Modified:** 2010-11-05_</span></span>

<span data-ttu-id="7c0d8-104">A tabela gateways é uma tabela de suporte.</span><span class="sxs-lookup"><span data-stu-id="7c0d8-104">The Gateways table is a supporting table.</span></span> <span data-ttu-id="7c0d8-105">Cada registro armazena informações sobre um gateway envolvido em chamadas PSTN (rede telefônica pública comutada) que têm registros no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="7c0d8-105">Each record stores information about one gateway that is involved in public switched telephone network (PSTN) calls that have records in the database.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7c0d8-106">Coluna</span><span class="sxs-lookup"><span data-stu-id="7c0d8-106">Column</span></span></th>
<th><span data-ttu-id="7c0d8-107">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="7c0d8-107">Data Type</span></span></th>
<th><span data-ttu-id="7c0d8-108">Chave/índice</span><span class="sxs-lookup"><span data-stu-id="7c0d8-108">Key/Index</span></span></th>
<th><span data-ttu-id="7c0d8-109">Detalhes</span><span class="sxs-lookup"><span data-stu-id="7c0d8-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7c0d8-110"><strong>Gatewayid</strong></span><span class="sxs-lookup"><span data-stu-id="7c0d8-110"><strong>GatewayId</strong></span></span></p></td>
<td><p><span data-ttu-id="7c0d8-111">int</span><span class="sxs-lookup"><span data-stu-id="7c0d8-111">int</span></span></p></td>
<td><p><span data-ttu-id="7c0d8-112">Primária</span><span class="sxs-lookup"><span data-stu-id="7c0d8-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="7c0d8-113">Número exclusivo que identifica esse gateway.</span><span class="sxs-lookup"><span data-stu-id="7c0d8-113">Unique number identifying this gateway.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c0d8-114"><strong>Gateway</strong></span><span class="sxs-lookup"><span data-stu-id="7c0d8-114"><strong>Gateway</strong></span></span></p></td>
<td><p><span data-ttu-id="7c0d8-115">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="7c0d8-115">nvarchar(256)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7c0d8-116">Nome do gateway.</span><span class="sxs-lookup"><span data-stu-id="7c0d8-116">Gateway name.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

