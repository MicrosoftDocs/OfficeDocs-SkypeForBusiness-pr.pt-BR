---
title: 'Lync Server 2013: tabela DeRegisterType'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DeRegisterType table
ms:assetid: 09148118-6209-4fd7-a494-99118689a245
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398142(v=OCS.15)
ms:contentKeyID: 48183346
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 65c94513a3578f8608da555cdd0b3e2273b8a7da
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762529"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deregistertype-table-in-lync-server-2013"></a><span data-ttu-id="291ce-102">Tabela DeRegisterType no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="291ce-102">DeRegisterType table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="291ce-103">_**Tópico da última modificação:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="291ce-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="291ce-104">A tabela canregistertype é uma tabela estática que armazena a lista de possíveis tipos de registros de usuário possíveis, como ' cliente iniciado ', ' registro expirado ' ou ' cliente parou de responder '.</span><span class="sxs-lookup"><span data-stu-id="291ce-104">The DeRegisterType table is a static table that stores the list of possible user de-registers types, such as ‘client initiated’, ‘registration expired’, or ‘client stopped responding.’</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="291ce-105">Coluna</span><span class="sxs-lookup"><span data-stu-id="291ce-105">Column</span></span></th>
<th><span data-ttu-id="291ce-106">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="291ce-106">Data Type</span></span></th>
<th><span data-ttu-id="291ce-107">Chave/índice</span><span class="sxs-lookup"><span data-stu-id="291ce-107">Key/Index</span></span></th>
<th><span data-ttu-id="291ce-108">Detalhes</span><span class="sxs-lookup"><span data-stu-id="291ce-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="291ce-109"><strong>DeRegisterTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="291ce-109"><strong>DeRegisterTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="291ce-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="291ce-110">tinyint</span></span></p></td>
<td><p><span data-ttu-id="291ce-111">Primária</span><span class="sxs-lookup"><span data-stu-id="291ce-111">Primary</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="291ce-112"><strong>DeRegisterReason</strong></span><span class="sxs-lookup"><span data-stu-id="291ce-112"><strong>DeRegisterReason</strong></span></span></p></td>
<td><p><span data-ttu-id="291ce-113">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="291ce-113">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="291ce-114">Valores permitidos:</span><span class="sxs-lookup"><span data-stu-id="291ce-114">Allowed values:</span></span></p>
<ul>
<li><p><span data-ttu-id="291ce-115">0--desconhecido</span><span class="sxs-lookup"><span data-stu-id="291ce-115">0 -- Unknown</span></span></p></li>
<li><p><span data-ttu-id="291ce-116">1--cliente iniciou o registro</span><span class="sxs-lookup"><span data-stu-id="291ce-116">1 -- Client Initiated Deregistration</span></span></p></li>
<li><p><span data-ttu-id="291ce-117">2--registro expirado</span><span class="sxs-lookup"><span data-stu-id="291ce-117">2 -- Registration Expired</span></span></p></li>
<li><p><span data-ttu-id="291ce-118">3 – cliente travou</span><span class="sxs-lookup"><span data-stu-id="291ce-118">3 – Client crashed</span></span></p></li>
<li><p><span data-ttu-id="291ce-119">4--atributos de usuário alterados</span><span class="sxs-lookup"><span data-stu-id="291ce-119">4 -- User Attributes Changed</span></span></p></li>
<li><p><span data-ttu-id="291ce-120">5 – registrador preferencial alterado</span><span class="sxs-lookup"><span data-stu-id="291ce-120">5 – Preferred Registrar Changed</span></span></p></li>
<li><p><span data-ttu-id="291ce-121">6 – cliente herdado no modo de sobrevivência</span><span class="sxs-lookup"><span data-stu-id="291ce-121">6 -- Legacy Client In Survival Mode</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

