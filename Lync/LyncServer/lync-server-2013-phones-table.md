---
title: 'Lync Server 2013: tabela de telefones'
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
ms.openlocfilehash: 0f7a03cdad1e3b080bb62db31ea1796e14cd2887
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42215467"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="phones-table-in-lync-server-2013"></a><span data-ttu-id="87a8d-102">Tabela phones no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="87a8d-102">Phones table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="87a8d-103">_**Última modificação do tópico:** 2012-08-20_</span><span class="sxs-lookup"><span data-stu-id="87a8d-103">_**Topic Last Modified:** 2012-08-20_</span></span>

<span data-ttu-id="87a8d-104">A tabela telefones é uma tabela de suporte.</span><span class="sxs-lookup"><span data-stu-id="87a8d-104">The Phones table is a supporting table.</span></span> <span data-ttu-id="87a8d-105">Cada registro na tabela armazena informações sobre um número de telefone envolvido em chamadas VoIP que têm registros no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="87a8d-105">Each record in the table stores information about one phone number involved in VoIP calls that have records in the database.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="87a8d-106">Coluna</span><span class="sxs-lookup"><span data-stu-id="87a8d-106">Column</span></span></th>
<th><span data-ttu-id="87a8d-107">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="87a8d-107">Data Type</span></span></th>
<th><span data-ttu-id="87a8d-108">Chave/índice</span><span class="sxs-lookup"><span data-stu-id="87a8d-108">Key/Index</span></span></th>
<th><span data-ttu-id="87a8d-109">Detalhes</span><span class="sxs-lookup"><span data-stu-id="87a8d-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="87a8d-110"><strong>PHONEID</strong></span><span class="sxs-lookup"><span data-stu-id="87a8d-110"><strong>PhoneId</strong></span></span></p></td>
<td><p><span data-ttu-id="87a8d-111">int</span><span class="sxs-lookup"><span data-stu-id="87a8d-111">int</span></span></p></td>
<td><p><span data-ttu-id="87a8d-112">Primário</span><span class="sxs-lookup"><span data-stu-id="87a8d-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="87a8d-113">Número exclusivo que identifica esse telefone.</span><span class="sxs-lookup"><span data-stu-id="87a8d-113">Unique number identifying this phone.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="87a8d-114"><strong>PhoneUri</strong></span><span class="sxs-lookup"><span data-stu-id="87a8d-114"><strong>PhoneUri</strong></span></span></p></td>
<td><p><span data-ttu-id="87a8d-115">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="87a8d-115">nvarchar(450)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="87a8d-116">Número de telefone.</span><span class="sxs-lookup"><span data-stu-id="87a8d-116">Phone number.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="87a8d-117"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="87a8d-117"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="87a8d-118">dateTime</span><span class="sxs-lookup"><span data-stu-id="87a8d-118">dateTime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="87a8d-119">Carimbo de data/hora (somente para uso interno).</span><span class="sxs-lookup"><span data-stu-id="87a8d-119">Time stamp (for internal use only).</span></span></p>
<p><span data-ttu-id="87a8d-120">Este campo foi introduzido no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="87a8d-120">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

