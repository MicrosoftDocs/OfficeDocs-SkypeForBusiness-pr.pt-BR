---
title: 'Lync Server 2013: tabela PurgeSettings'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: PurgeSettings table
ms:assetid: 9ff2c8fc-4ae8-4f22-96a8-1f4d5eecbf2d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205121(v=OCS.15)
ms:contentKeyID: 48184932
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 84c75e96c9a1541a8bd56f68d5fcf9d1a8655204
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512208"
---
# <a name="purgesettings-table-in-lync-server-2013"></a><span data-ttu-id="85330-102">Tabela PurgeSettings no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="85330-102">PurgeSettings table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="85330-103">_**Última modificação do tópico:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="85330-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="85330-104">A tabela PurgeSettings contém informações que especificam se (e quando) registros de detalhes de chamada desatualizadas serão automaticamente excluídos do banco de dados CDR.</span><span class="sxs-lookup"><span data-stu-id="85330-104">The PurgeSettings table contains information that specifies if (and when) outdated call detail records will automatically be deleted from the CDR database.</span></span> <span data-ttu-id="85330-105">Observe que as informações relacionadas à limpeza também podem ser obtidas no Shell de gerenciamento do Microsoft Lync Server 2013 executando o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="85330-105">Note that purging-related information can also be obtained from within the Microsoft Lync Server 2013 Management Shell by running the following command:</span></span>

    Get-CsCdrConfiguration

<span data-ttu-id="85330-106">Os administradores devem tratar a tabela PurgeSettings como somente leitura: as alterações nas configurações de limpeza de detalhes da chamada devem ser feitas apenas usando os cmdlets [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) ou [set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="85330-106">Administrators should treat the PurgeSettings table as read-only: changes to the call detail purge settings should only be made using the [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) or [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) cmdlets.</span></span>

<span data-ttu-id="85330-107">Esta tabela foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="85330-107">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="85330-108">Coluna</span><span class="sxs-lookup"><span data-stu-id="85330-108">Column</span></span></th>
<th><span data-ttu-id="85330-109">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="85330-109">Data Type</span></span></th>
<th><span data-ttu-id="85330-110">Chave/índice</span><span class="sxs-lookup"><span data-stu-id="85330-110">Key/Index</span></span></th>
<th><span data-ttu-id="85330-111">Detalhes</span><span class="sxs-lookup"><span data-stu-id="85330-111">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="85330-112"><strong>Id</strong></span><span class="sxs-lookup"><span data-stu-id="85330-112"><strong>Id</strong></span></span></p></td>
<td><p><span data-ttu-id="85330-113">int</span><span class="sxs-lookup"><span data-stu-id="85330-113">int</span></span></p></td>
<td><p><span data-ttu-id="85330-114">Primário</span><span class="sxs-lookup"><span data-stu-id="85330-114">Primary</span></span></p></td>
<td><p><span data-ttu-id="85330-115">Identificador exclusivo da coleção de configurações de limpeza de CDR.</span><span class="sxs-lookup"><span data-stu-id="85330-115">Unique identifier for the collection of CDR purge settings.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="85330-116"><strong>EnablePurge</strong></span><span class="sxs-lookup"><span data-stu-id="85330-116"><strong>EnablePurge</strong></span></span></p></td>
<td><p><span data-ttu-id="85330-117">bits</span><span class="sxs-lookup"><span data-stu-id="85330-117">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="85330-118">Quando definido como true (1), o Microsoft Lync Server 2013 limpará periodicamente registros desatualizados do banco de dados CDR.</span><span class="sxs-lookup"><span data-stu-id="85330-118">When set to True (1) Microsoft Lync Server 2013 will periodically purge outdated records from the CDR database.</span></span> <span data-ttu-id="85330-119">A limpeza ocorrerá todos os dias na hora especificada pela configuração PurgeHour.</span><span class="sxs-lookup"><span data-stu-id="85330-119">Purging will take place each day at the tome specified by the PurgeHour setting.</span></span> <span data-ttu-id="85330-120">Se definido como Falso (0), os registros não serão limpados automaticamente do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="85330-120">If set to False (0) then records will not be automatically purged from the database.</span></span> <span data-ttu-id="85330-121">O valor padrão é verdadeiro.</span><span class="sxs-lookup"><span data-stu-id="85330-121">The default value is True.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="85330-122"><strong>KeepCallDetailForDays</strong></span><span class="sxs-lookup"><span data-stu-id="85330-122"><strong>KeepCallDetailForDays</strong></span></span></p></td>
<td><p><span data-ttu-id="85330-123">int</span><span class="sxs-lookup"><span data-stu-id="85330-123">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="85330-124">Especifica a idade dos registros de CDR (em dias) que serão removidos do banco de dados: se a limpeza estiver habilitada, os registros de CDR mais antigos do que esse valor serão removidos do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="85330-124">Specifies the age of CDR records (in days) that will be purged from the database: if purging is enabled, CDR records older than this value will be removed from the database.</span></span> <span data-ttu-id="85330-125">O valor padrão é 60 dias.</span><span class="sxs-lookup"><span data-stu-id="85330-125">The default value is 60 days.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="85330-126"><strong>KeepErrorReportForDays</strong></span><span class="sxs-lookup"><span data-stu-id="85330-126"><strong>KeepErrorReportForDays</strong></span></span></p></td>
<td><p><span data-ttu-id="85330-127">int</span><span class="sxs-lookup"><span data-stu-id="85330-127">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="85330-128">Especifica a idade dos registros do relatório de erros (em dias) que serão removidos do banco de dados: se a limpeza estiver habilitada, os registros do relatório de erros mais antigos do que esse valor serão removidos do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="85330-128">Specifies the age of error report records (in days) that will be purged from the database: if purging is enabled, error report records older than this value will be removed from the database.</span></span> <span data-ttu-id="85330-129">O valor padrão é 60 dias.</span><span class="sxs-lookup"><span data-stu-id="85330-129">The default value is 60 days.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="85330-130"><strong>PurgeHour</strong></span><span class="sxs-lookup"><span data-stu-id="85330-130"><strong>PurgeHour</strong></span></span></p></td>
<td><p><span data-ttu-id="85330-131">int</span><span class="sxs-lookup"><span data-stu-id="85330-131">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="85330-132">Especifica a hora local do dia em que a limpeza ocorrerá.</span><span class="sxs-lookup"><span data-stu-id="85330-132">Specifies the local time of day when database purging will take place.</span></span> <span data-ttu-id="85330-133">A hora é especificada usando um relógio de 24 horas, sendo que 0 representa meia-noite (00:00) e 23 representa 23:00.</span><span class="sxs-lookup"><span data-stu-id="85330-133">The time of day is specified using a 24-hour clock, with 0 representing midnight (12:00 AM) and 23 representing 11:00 PM.</span></span> <span data-ttu-id="85330-134">Observe que você pode especificar apenas a hora: um valor 10 (indicando 10:00) é permitido, mas um valor 10:30 representado por 10,5 (indicando 10:30) não é permitido.</span><span class="sxs-lookup"><span data-stu-id="85330-134">Note that you can only specify the hour of the day: a value of 10 (indicating 10:00 AM) is allowed, but a value of 10:30 of 10.5 (indicating 10:30 AM) is not allowed.</span></span> <span data-ttu-id="85330-135">O valor padrão é 2 (2:00).</span><span class="sxs-lookup"><span data-stu-id="85330-135">The default value is 2 (2:00 AM).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

