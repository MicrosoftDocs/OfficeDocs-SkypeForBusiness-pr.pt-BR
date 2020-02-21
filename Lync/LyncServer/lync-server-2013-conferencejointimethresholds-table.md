---
title: 'Lync Server 2013: tabela ConferenceJoinTimeThresholds'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ConferenceJoinTimeThresholds table
ms:assetid: 3944d724-bdd8-4d1c-a2af-933ee8141529
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204809(v=OCS.15)
ms:contentKeyID: 48183855
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6d6ce43adee4c00a945325cf31c4194816e7ee14
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42190295"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="conferencejointimethresholds-table-in-lync-server-2013"></a><span data-ttu-id="9c236-102">Tabela ConferenceJoinTimeThresholds no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9c236-102">ConferenceJoinTimeThresholds table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9c236-103">_**Última modificação do tópico:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="9c236-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="9c236-p101">A tabela ConferenceJoinTimeThresholds contém os limites de classificação usados pelo Relatório de Resumo de Tempo de Participação em Conferência. Este relatório resume o período necessário para que os usuários participem com êxito de uma conferência; esses valores de tempo são reportados como média e em uma das seguintes categorias:</span><span class="sxs-lookup"><span data-stu-id="9c236-p101">The ConferenceJoinTimeThresholds table contains the classification boundaries used by the Conference Join Time Summary Report. The Conference Join Time Summary Report summarizes the amount time required for users to successfully join a conference; these time values are reported both as an average and in one of the following categories:</span></span>

  - <span data-ttu-id="9c236-106">Menos de 2 segundos.</span><span class="sxs-lookup"><span data-stu-id="9c236-106">Less than 2 seconds.</span></span>

  - <span data-ttu-id="9c236-107">Entre 2 e 5 segundos.</span><span class="sxs-lookup"><span data-stu-id="9c236-107">Between 2 second and 5 seconds.</span></span>

  - <span data-ttu-id="9c236-108">Entre 5 e 10 segundos.</span><span class="sxs-lookup"><span data-stu-id="9c236-108">Between 5 seconds and 10 seconds.</span></span>

  - <span data-ttu-id="9c236-109">Mais de 10 segundos</span><span class="sxs-lookup"><span data-stu-id="9c236-109">More than 10 seconds.</span></span>

<span data-ttu-id="9c236-110">A tabela ConferenceJoinTimeThresholds contém os valores de classificação de 2 segundos, 5 segundos e 10 segundos.</span><span class="sxs-lookup"><span data-stu-id="9c236-110">The ConferenceJoinTimeThresholds table contains the classification values 2 seconds, 5 seconds, and 10 seconds.</span></span>

<span data-ttu-id="9c236-111">Esta tabela foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9c236-111">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9c236-112">Coluna</span><span class="sxs-lookup"><span data-stu-id="9c236-112">Column</span></span></th>
<th><span data-ttu-id="9c236-113">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="9c236-113">Data Type</span></span></th>
<th><span data-ttu-id="9c236-114">Chave/índice</span><span class="sxs-lookup"><span data-stu-id="9c236-114">Key/Index</span></span></th>
<th><span data-ttu-id="9c236-115">Detalhes</span><span class="sxs-lookup"><span data-stu-id="9c236-115">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9c236-116"><strong>Thresholdid</strong></span><span class="sxs-lookup"><span data-stu-id="9c236-116"><strong>ThresholdId</strong></span></span></p></td>
<td><p><span data-ttu-id="9c236-117">int</span><span class="sxs-lookup"><span data-stu-id="9c236-117">int</span></span></p></td>
<td><p><span data-ttu-id="9c236-118">Primário</span><span class="sxs-lookup"><span data-stu-id="9c236-118">Primary</span></span></p></td>
<td><p><span data-ttu-id="9c236-119">Identificador exclusivo da classificação.</span><span class="sxs-lookup"><span data-stu-id="9c236-119">Unique identifier for the classification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9c236-120"><strong>ThresholdValue</strong></span><span class="sxs-lookup"><span data-stu-id="9c236-120"><strong>ThresholdValue</strong></span></span></p></td>
<td><p><span data-ttu-id="9c236-121">int</span><span class="sxs-lookup"><span data-stu-id="9c236-121">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9c236-p102">Limite superior da classificação. Os valores permitidos são:</span><span class="sxs-lookup"><span data-stu-id="9c236-p102">Upper limit for the classification. Allowed values are:</span></span></p>
<ol>
<li><p><span data-ttu-id="9c236-124">duas</span><span class="sxs-lookup"><span data-stu-id="9c236-124">2</span></span></p></li>
<li><p><span data-ttu-id="9c236-125">0,5</span><span class="sxs-lookup"><span data-stu-id="9c236-125">5</span></span></p></li>
<li><p><span data-ttu-id="9c236-126">10 </span><span class="sxs-lookup"><span data-stu-id="9c236-126">10</span></span></p></li>
</ol></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

