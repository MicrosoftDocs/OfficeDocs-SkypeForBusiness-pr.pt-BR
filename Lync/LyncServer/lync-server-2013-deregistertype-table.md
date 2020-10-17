---
title: 'Lync Server 2013: tabela de cancelamento de registro'
description: 'Lync Server 2013: tabela de cancelamento de Registrotype.'
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
ms.openlocfilehash: afad63c2abeba3e91565e07dac75d0ac6c96ca3a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555347"
---
# <a name="deregistertype-table-in-lync-server-2013"></a><span data-ttu-id="79c4e-103">Tabela deregistertype no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="79c4e-103">DeRegisterType table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="79c4e-104">_**Última modificação do tópico:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="79c4e-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="79c4e-105">DeRegisterType é uma tabela estática que armazena a lista de possíveis tipos de cancelamento de registro de usuário, como "cliente iniciado", "registro vencido" ou "cliente não responde".</span><span class="sxs-lookup"><span data-stu-id="79c4e-105">The DeRegisterType table is a static table that stores the list of possible user de-registers types, such as ‘client initiated’, ‘registration expired’, or ‘client stopped responding.’</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="79c4e-106">Coluna</span><span class="sxs-lookup"><span data-stu-id="79c4e-106">Column</span></span></th>
<th><span data-ttu-id="79c4e-107">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="79c4e-107">Data Type</span></span></th>
<th><span data-ttu-id="79c4e-108">Chave/índice</span><span class="sxs-lookup"><span data-stu-id="79c4e-108">Key/Index</span></span></th>
<th><span data-ttu-id="79c4e-109">Detalhes</span><span class="sxs-lookup"><span data-stu-id="79c4e-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="79c4e-110"><strong>DeRegisterTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="79c4e-110"><strong>DeRegisterTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="79c4e-111">tinyint</span><span class="sxs-lookup"><span data-stu-id="79c4e-111">tinyint</span></span></p></td>
<td><p><span data-ttu-id="79c4e-112">Primário</span><span class="sxs-lookup"><span data-stu-id="79c4e-112">Primary</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="79c4e-113"><strong>DeRegisterReason</strong></span><span class="sxs-lookup"><span data-stu-id="79c4e-113"><strong>DeRegisterReason</strong></span></span></p></td>
<td><p><span data-ttu-id="79c4e-114">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="79c4e-114">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="79c4e-115">Valores permitidos:</span><span class="sxs-lookup"><span data-stu-id="79c4e-115">Allowed values:</span></span></p>
<ul>
<li><p><span data-ttu-id="79c4e-116">0 -- Desconhecido</span><span class="sxs-lookup"><span data-stu-id="79c4e-116">0 -- Unknown</span></span></p></li>
<li><p><span data-ttu-id="79c4e-117">Iniciado o cancelamento do registro pelo cliente</span><span class="sxs-lookup"><span data-stu-id="79c4e-117">1 -- Client Initiated Deregistration</span></span></p></li>
<li><p><span data-ttu-id="79c4e-118">2 -- Registro expirado</span><span class="sxs-lookup"><span data-stu-id="79c4e-118">2 -- Registration Expired</span></span></p></li>
<li><p><span data-ttu-id="79c4e-119">3 – Client crashed</span><span class="sxs-lookup"><span data-stu-id="79c4e-119">3 – Client crashed</span></span></p></li>
<li><p><span data-ttu-id="79c4e-120">Atributos do usuário mudaram</span><span class="sxs-lookup"><span data-stu-id="79c4e-120">4 -- User Attributes Changed</span></span></p></li>
<li><p><span data-ttu-id="79c4e-121">5 - Registrador preferido mudou</span><span class="sxs-lookup"><span data-stu-id="79c4e-121">5 – Preferred Registrar Changed</span></span></p></li>
<li><p><span data-ttu-id="79c4e-122">6 -- Cliente herdado em Modo de sobrevivência</span><span class="sxs-lookup"><span data-stu-id="79c4e-122">6 -- Legacy Client In Survival Mode</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

