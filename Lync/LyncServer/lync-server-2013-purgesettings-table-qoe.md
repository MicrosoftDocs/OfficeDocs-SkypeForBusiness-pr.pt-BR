---
title: 'Lync Server 2013: tabela PurgeSettings (QoE)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: PurgeSettings table (QoE)
ms:assetid: 31b85d1c-3f32-4f67-94bf-9389cdd282c5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204788(v=OCS.15)
ms:contentKeyID: 48183777
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ac236e08f79adbe1ec7cbe92ea04405de46d0055
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512218"
---
# <a name="purgesettings-table-qoe-in-lync-server-2013"></a><span data-ttu-id="2e3fa-102">Tabela PurgeSettings (QoE) no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2e3fa-102">PurgeSettings table (QoE) in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2e3fa-103">_**Última modificação do tópico:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="2e3fa-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="2e3fa-104">A tabela PurgeSettings contém informações que especificam se (e quando) os registros de qualidade de experiência defasados serão excluídos automaticamente do banco de dados de QoE.</span><span class="sxs-lookup"><span data-stu-id="2e3fa-104">The PurgeSettings table contains information that specifies if (and when) outdated Quality of Experience records will automatically be deleted from the QoE database.</span></span> <span data-ttu-id="2e3fa-105">Observe que as informações relacionadas à limpeza também podem ser obtidas no Shell de gerenciamento do Microsoft Lync Server 2013 executando o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="2e3fa-105">Note that purging-related information can also be obtained from within the Microsoft Lync Server 2013 Management Shell by running the following command:</span></span>

    Get-CsQoEConfiguration

<span data-ttu-id="2e3fa-106">Esta tabela foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2e3fa-106">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2e3fa-107"><strong>Coluna</strong></span><span class="sxs-lookup"><span data-stu-id="2e3fa-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="2e3fa-108"><strong>Tipo de dados</strong></span><span class="sxs-lookup"><span data-stu-id="2e3fa-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="2e3fa-109"><strong>Chave/índice</strong></span><span class="sxs-lookup"><span data-stu-id="2e3fa-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="2e3fa-110"><strong>Detalhes</strong></span><span class="sxs-lookup"><span data-stu-id="2e3fa-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2e3fa-111"><strong>ID</strong></span><span class="sxs-lookup"><span data-stu-id="2e3fa-111"><strong>ID</strong></span></span></p></td>
<td><p><span data-ttu-id="2e3fa-112">int</span><span class="sxs-lookup"><span data-stu-id="2e3fa-112">int</span></span></p></td>
<td><p><span data-ttu-id="2e3fa-113">Primário</span><span class="sxs-lookup"><span data-stu-id="2e3fa-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="2e3fa-114">Identificador exclusivo do conjunto de configurações de limpeza de QoE.</span><span class="sxs-lookup"><span data-stu-id="2e3fa-114">Unique identifier for the collection of QoE purge settings.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2e3fa-115"><strong>EnablePurge</strong></span><span class="sxs-lookup"><span data-stu-id="2e3fa-115"><strong>EnablePurge</strong></span></span></p></td>
<td><p><span data-ttu-id="2e3fa-116">bits</span><span class="sxs-lookup"><span data-stu-id="2e3fa-116">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2e3fa-117">Quando definido como true (1), o Microsoft Lync Server 2013 limpará periodicamente registros desatualizados do banco de dados de QoE.</span><span class="sxs-lookup"><span data-stu-id="2e3fa-117">When set to True (1) Microsoft Lync Server 2013 will periodically purge outdated records from the QoE database.</span></span> <span data-ttu-id="2e3fa-118">A limpeza ocorrerá todos os dias na hora especificada pela configuração PurgeHour.</span><span class="sxs-lookup"><span data-stu-id="2e3fa-118">Purging will take place each day at the tome specified by the PurgeHour setting.</span></span> <span data-ttu-id="2e3fa-119">Se definido como Falso (0), os registros não serão limpados automaticamente do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="2e3fa-119">If set to False (0) then records will not be automatically purged from the database.</span></span> <span data-ttu-id="2e3fa-120">O valor padrão é verdadeiro.</span><span class="sxs-lookup"><span data-stu-id="2e3fa-120">The default value is True.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2e3fa-121"><strong>KeepQoEDataForDays</strong></span><span class="sxs-lookup"><span data-stu-id="2e3fa-121"><strong>KeepQoEDataForDays</strong></span></span></p></td>
<td><p><span data-ttu-id="2e3fa-122">int</span><span class="sxs-lookup"><span data-stu-id="2e3fa-122">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2e3fa-p103">Especifica a idade dos registros de QoE (em dias) que serão limpados do banco de dados: se a limpeza estiver ativada, os registros de QoE mais antigos que esse valor serão removidos do banco de dados. O valor padrão é 60 dias.</span><span class="sxs-lookup"><span data-stu-id="2e3fa-p103">Specifies the age of QoE records (in days) that will be purged from the database: if purging is enabled, QoE records older than this value will be removed from the database. The default value is 60 days.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2e3fa-125"><strong>PurgeHour</strong></span><span class="sxs-lookup"><span data-stu-id="2e3fa-125"><strong>PurgeHour</strong></span></span></p></td>
<td><p><span data-ttu-id="2e3fa-126">int</span><span class="sxs-lookup"><span data-stu-id="2e3fa-126">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2e3fa-p104">Especifica a hora local do dia em que a limpeza ocorrerá. A hora é especificada usando um relógio de 24 horas, sendo que 0 representa meia-noite (00:00) e 23 representa 23:00. Observe que você pode especificar apenas a hora: um valor 10 (indicando 10:00) é permitido, mas um valor 10:30 representado por 10,5 (indicando 10:30) não é permitido. O valor padrão é 1 (1:00). Especifica a hora local do dia em que a limpeza do banco de dados ocorrerá. A hora é especificada usando um relógio de 24 horas, sendo que 0 representa meia-noite (00:00) e 23 representa 23:00. Observe que você pode especificar apenas a hora: um valor 10 (indicando 10:00) é permitido, mas um valor 10:30 representado por 10,5 (indicando 10:30) não é permitido. O valor padrão é 1 (1:00).</span><span class="sxs-lookup"><span data-stu-id="2e3fa-p104">Specifies the local time of day when database purging will take place. The time of day is specified using a 24-hour clock, with 0 representing midnight (12:00 AM) and 23 representing 11:00 PM. Note that you can only specify the hour of the day: a value of 10 (indicating 10:00 AM) is allowed, but a value of 10:30 of 10.5 (indicating 10:30 AM) is not allowed. The default value is 1 (1:00 AM). Specifies the local time of day when database purging will take place. The time of day is specified using a 24-hour clock, with 0 representing midnight (12:00 AM) and 23 representing 11:00 PM. Note that you can only specify the hour of the day: a value of 10 (indicating 10:00 AM) is allowed, but a value of 10:30 of 10.5 (indicating 10:30 AM) is not allowed. The default value is 1 (1:00 AM).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

