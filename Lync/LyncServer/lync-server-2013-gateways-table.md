---
title: 'Lync Server 2013: tabela gateways'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Gateways table
ms:assetid: a909daad-d137-45e0-b149-1de9f8e1e029
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412795(v=OCS.15)
ms:contentKeyID: 48185034
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: efb730e06d9ce74d8f4e7c3c3e1dbf507af2ba1c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147454"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="gateways-table-in-lync-server-2013"></a><span data-ttu-id="23596-102">Tabela gateways no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="23596-102">Gateways table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="23596-103">_**Última modificação do tópico:** 2010-11-05_</span><span class="sxs-lookup"><span data-stu-id="23596-103">_**Topic Last Modified:** 2010-11-05_</span></span>

<span data-ttu-id="23596-104">A tabela gateways é uma tabela de suporte.</span><span class="sxs-lookup"><span data-stu-id="23596-104">The Gateways table is a supporting table.</span></span> <span data-ttu-id="23596-105">Cada registro armazena informações sobre um gateway envolvido em chamadas PSTN (rede telefônica pública comutada) que têm registros no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="23596-105">Each record stores information about one gateway that is involved in public switched telephone network (PSTN) calls that have records in the database.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="23596-106">Coluna</span><span class="sxs-lookup"><span data-stu-id="23596-106">Column</span></span></th>
<th><span data-ttu-id="23596-107">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="23596-107">Data Type</span></span></th>
<th><span data-ttu-id="23596-108">Chave/índice</span><span class="sxs-lookup"><span data-stu-id="23596-108">Key/Index</span></span></th>
<th><span data-ttu-id="23596-109">Detalhes</span><span class="sxs-lookup"><span data-stu-id="23596-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="23596-110"><strong>Gatewayid</strong></span><span class="sxs-lookup"><span data-stu-id="23596-110"><strong>GatewayId</strong></span></span></p></td>
<td><p><span data-ttu-id="23596-111">int</span><span class="sxs-lookup"><span data-stu-id="23596-111">int</span></span></p></td>
<td><p><span data-ttu-id="23596-112">Primário</span><span class="sxs-lookup"><span data-stu-id="23596-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="23596-113">Número exclusivo que identifica esse gateway.</span><span class="sxs-lookup"><span data-stu-id="23596-113">Unique number identifying this gateway.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23596-114"><strong>Gateway</strong></span><span class="sxs-lookup"><span data-stu-id="23596-114"><strong>Gateway</strong></span></span></p></td>
<td><p><span data-ttu-id="23596-115">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="23596-115">nvarchar(256)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="23596-116">Nome do gateway.</span><span class="sxs-lookup"><span data-stu-id="23596-116">Gateway name.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

