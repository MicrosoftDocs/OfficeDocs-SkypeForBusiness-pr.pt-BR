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
ms.openlocfilehash: 56ea95d0ba54a34eaa315ff345efb45cd563700c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747021"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="purgesettings-table-in-lync-server-2013"></a><span data-ttu-id="a1a4b-102">Tabela PurgeSettings no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a1a4b-102">PurgeSettings table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a1a4b-103">_**Tópico da última modificação:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="a1a4b-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="a1a4b-104">A tabela PurgeSettings contém informações que especificam se (e quando) registros de detalhes de chamadas desatualizados serão automaticamente excluídos do banco de dados CDR.</span><span class="sxs-lookup"><span data-stu-id="a1a4b-104">The PurgeSettings table contains information that specifies if (and when) outdated call detail records will automatically be deleted from the CDR database.</span></span> <span data-ttu-id="a1a4b-105">Observe que as informações relacionadas à remoção também podem ser obtidas dentro do Shell de gerenciamento do Microsoft Lync Server 2013 executando o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="a1a4b-105">Note that purging-related information can also be obtained from within the Microsoft Lync Server 2013 Management Shell by running the following command:</span></span>

    Get-CsCdrConfiguration

<span data-ttu-id="a1a4b-106">Os administradores devem tratar a tabela PurgeSettings como somente leitura: as alterações nas configurações de limpeza de detalhes da chamada devem ser feitas somente usando cmdlets [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) ou [set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="a1a4b-106">Administrators should treat the PurgeSettings table as read-only: changes to the call detail purge settings should only be made using the [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) or [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) cmdlets.</span></span>

<span data-ttu-id="a1a4b-107">Esta tabela foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a1a4b-107">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a1a4b-108">Coluna</span><span class="sxs-lookup"><span data-stu-id="a1a4b-108">Column</span></span></th>
<th><span data-ttu-id="a1a4b-109">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="a1a4b-109">Data Type</span></span></th>
<th><span data-ttu-id="a1a4b-110">Chave/índice</span><span class="sxs-lookup"><span data-stu-id="a1a4b-110">Key/Index</span></span></th>
<th><span data-ttu-id="a1a4b-111">Detalhes</span><span class="sxs-lookup"><span data-stu-id="a1a4b-111">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a1a4b-112"><strong>%</strong></span><span class="sxs-lookup"><span data-stu-id="a1a4b-112"><strong>Id</strong></span></span></p></td>
<td><p><span data-ttu-id="a1a4b-113">int</span><span class="sxs-lookup"><span data-stu-id="a1a4b-113">int</span></span></p></td>
<td><p><span data-ttu-id="a1a4b-114">Primária</span><span class="sxs-lookup"><span data-stu-id="a1a4b-114">Primary</span></span></p></td>
<td><p><span data-ttu-id="a1a4b-115">Identificador exclusivo da coleção de configurações de limpeza de CDR.</span><span class="sxs-lookup"><span data-stu-id="a1a4b-115">Unique identifier for the collection of CDR purge settings.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a1a4b-116"><strong>EnablePurge</strong></span><span class="sxs-lookup"><span data-stu-id="a1a4b-116"><strong>EnablePurge</strong></span></span></p></td>
<td><p><span data-ttu-id="a1a4b-117">bit</span><span class="sxs-lookup"><span data-stu-id="a1a4b-117">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a1a4b-118">Quando definido como true (1), o Microsoft Lync Server 2013 limpará periodicamente registros desatualizados do banco de dados CDR.</span><span class="sxs-lookup"><span data-stu-id="a1a4b-118">When set to True (1) Microsoft Lync Server 2013 will periodically purge outdated records from the CDR database.</span></span> <span data-ttu-id="a1a4b-119">A limpeza ocorrerá a cada dia no Tomé especificado pela configuração PurgeHour.</span><span class="sxs-lookup"><span data-stu-id="a1a4b-119">Purging will take place each day at the tome specified by the PurgeHour setting.</span></span> <span data-ttu-id="a1a4b-120">Se definido como falso (0), os registros não serão automaticamente limpos do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="a1a4b-120">If set to False (0) then records will not be automatically purged from the database.</span></span> <span data-ttu-id="a1a4b-121">O valor padrão é True.</span><span class="sxs-lookup"><span data-stu-id="a1a4b-121">The default value is True.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a1a4b-122"><strong>KeepCallDetailForDays</strong></span><span class="sxs-lookup"><span data-stu-id="a1a4b-122"><strong>KeepCallDetailForDays</strong></span></span></p></td>
<td><p><span data-ttu-id="a1a4b-123">int</span><span class="sxs-lookup"><span data-stu-id="a1a4b-123">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a1a4b-124">Especifica a idade dos registros CDR (em dias) que serão removidos do banco de dados: se a limpeza estiver habilitada, os registros CDR mais antigos do que esse valor serão removidos do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="a1a4b-124">Specifies the age of CDR records (in days) that will be purged from the database: if purging is enabled, CDR records older than this value will be removed from the database.</span></span> <span data-ttu-id="a1a4b-125">O valor padrão é 60 dias.</span><span class="sxs-lookup"><span data-stu-id="a1a4b-125">The default value is 60 days.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a1a4b-126"><strong>KeepErrorReportForDays</strong></span><span class="sxs-lookup"><span data-stu-id="a1a4b-126"><strong>KeepErrorReportForDays</strong></span></span></p></td>
<td><p><span data-ttu-id="a1a4b-127">int</span><span class="sxs-lookup"><span data-stu-id="a1a4b-127">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a1a4b-128">Especifica a idade dos registros de relatório de tempo (em dias) que serão removidos do banco de dados: se a limpeza estiver habilitada, os registros de relatório de erros anteriores a esse valor serão removidos do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="a1a4b-128">Specifies the age of error report records (in days) that will be purged from the database: if purging is enabled, error report records older than this value will be removed from the database.</span></span> <span data-ttu-id="a1a4b-129">O valor padrão é 60 dias.</span><span class="sxs-lookup"><span data-stu-id="a1a4b-129">The default value is 60 days.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a1a4b-130"><strong>PurgeHour</strong></span><span class="sxs-lookup"><span data-stu-id="a1a4b-130"><strong>PurgeHour</strong></span></span></p></td>
<td><p><span data-ttu-id="a1a4b-131">int</span><span class="sxs-lookup"><span data-stu-id="a1a4b-131">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a1a4b-132">Especifica a hora local do dia em que a limpeza do banco de dados ocorrerá.</span><span class="sxs-lookup"><span data-stu-id="a1a4b-132">Specifies the local time of day when database purging will take place.</span></span> <span data-ttu-id="a1a4b-133">O horário é especificado utilizando-se um relógio de 24 horas, onde 0 representa a meia-noite (00:00) e 23 representa 23 horas.</span><span class="sxs-lookup"><span data-stu-id="a1a4b-133">The time of day is specified using a 24-hour clock, with 0 representing midnight (12:00 AM) and 23 representing 11:00 PM.</span></span> <span data-ttu-id="a1a4b-134">Observe que você só pode especificar a hora do dia: é permitido um valor de 10 (indicando 10:00 AM), mas um valor de 10:30 de 10,5 (indicando 10:30 AM) não é permitido.</span><span class="sxs-lookup"><span data-stu-id="a1a4b-134">Note that you can only specify the hour of the day: a value of 10 (indicating 10:00 AM) is allowed, but a value of 10:30 of 10.5 (indicating 10:30 AM) is not allowed.</span></span> <span data-ttu-id="a1a4b-135">O valor padrão é 2 (2:00).</span><span class="sxs-lookup"><span data-stu-id="a1a4b-135">The default value is 2 (2:00 AM).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

