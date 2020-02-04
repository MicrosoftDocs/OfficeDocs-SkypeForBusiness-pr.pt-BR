---
title: 'Lync Server 2013: Tabela Phones'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Phones table
ms:assetid: 41cb356d-9cc8-42b6-ac23-98a61b25aadc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425923(v=OCS.15)
ms:contentKeyID: 48183996
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cddf5eac7cc85852f4a7f61f4b746091158257e2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755181"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="phones-table-in-lync-server-2013"></a><span data-ttu-id="c81b9-102">Tabela Phones no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c81b9-102">Phones table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c81b9-103">_**Tópico da última modificação:** 2012-08-20_</span><span class="sxs-lookup"><span data-stu-id="c81b9-103">_**Topic Last Modified:** 2012-08-20_</span></span>

<span data-ttu-id="c81b9-104">A tabela de telefones é uma tabela de suporte.</span><span class="sxs-lookup"><span data-stu-id="c81b9-104">The Phones table is a supporting table.</span></span> <span data-ttu-id="c81b9-105">Cada registro na tabela armazena informações sobre um número de telefone envolvido em chamadas VoIP que têm registros no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="c81b9-105">Each record in the table stores information about one phone number involved in VoIP calls that have records in the database.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c81b9-106">Coluna</span><span class="sxs-lookup"><span data-stu-id="c81b9-106">Column</span></span></th>
<th><span data-ttu-id="c81b9-107">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="c81b9-107">Data Type</span></span></th>
<th><span data-ttu-id="c81b9-108">Chave/índice</span><span class="sxs-lookup"><span data-stu-id="c81b9-108">Key/Index</span></span></th>
<th><span data-ttu-id="c81b9-109">Detalhes</span><span class="sxs-lookup"><span data-stu-id="c81b9-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c81b9-110"><strong>PHONEID</strong></span><span class="sxs-lookup"><span data-stu-id="c81b9-110"><strong>PhoneId</strong></span></span></p></td>
<td><p><span data-ttu-id="c81b9-111">int</span><span class="sxs-lookup"><span data-stu-id="c81b9-111">int</span></span></p></td>
<td><p><span data-ttu-id="c81b9-112">Primária</span><span class="sxs-lookup"><span data-stu-id="c81b9-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="c81b9-113">Número exclusivo que identifica este telefone.</span><span class="sxs-lookup"><span data-stu-id="c81b9-113">Unique number identifying this phone.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c81b9-114"><strong>PhoneUri</strong></span><span class="sxs-lookup"><span data-stu-id="c81b9-114"><strong>PhoneUri</strong></span></span></p></td>
<td><p><span data-ttu-id="c81b9-115">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="c81b9-115">nvarchar(450)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="c81b9-116">Número de telefone.</span><span class="sxs-lookup"><span data-stu-id="c81b9-116">Phone number.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c81b9-117"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="c81b9-117"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="c81b9-118">dateTime</span><span class="sxs-lookup"><span data-stu-id="c81b9-118">dateTime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c81b9-119">Carimbo de data/hora (apenas para uso interno).</span><span class="sxs-lookup"><span data-stu-id="c81b9-119">Time stamp (for internal use only).</span></span></p>
<p><span data-ttu-id="c81b9-120">Este campo foi apresentado no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c81b9-120">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

