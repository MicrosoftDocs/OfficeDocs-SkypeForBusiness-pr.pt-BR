---
title: 'Lync Server 2013: tblComplianceState'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblComplianceState
ms:assetid: ea82e56c-3cca-4d89-b4e6-6bcaeb1f2830
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615045(v=OCS.15)
ms:contentKeyID: 48185937
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 051f9929c7728db4b1e6e55b061098211bbc11ad
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42207197"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblcompliancestate-in-lync-server-2013"></a><span data-ttu-id="f0823-102">tblComplianceState no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f0823-102">tblComplianceState in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f0823-103">_**Última modificação do tópico:** 2012-06-28_</span><span class="sxs-lookup"><span data-stu-id="f0823-103">_**Topic Last Modified:** 2012-06-28_</span></span>

<span data-ttu-id="f0823-104">tblComplianceState contém informações sobre o estado de conformidade de todo o pool.</span><span class="sxs-lookup"><span data-stu-id="f0823-104">tblComplianceState contains pool-wide compliance state information.</span></span>

### <a name="columns"></a><span data-ttu-id="f0823-105">Colunas</span><span class="sxs-lookup"><span data-stu-id="f0823-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f0823-106">Coluna</span><span class="sxs-lookup"><span data-stu-id="f0823-106">Column</span></span></th>
<th><span data-ttu-id="f0823-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="f0823-107">Type</span></span></th>
<th><span data-ttu-id="f0823-108">Descrição</span><span class="sxs-lookup"><span data-stu-id="f0823-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f0823-109">lastProcessedEntryID</span><span class="sxs-lookup"><span data-stu-id="f0823-109">lastProcessedEntryID</span></span></p></td>
<td><p><span data-ttu-id="f0823-110">bigint, não nulo</span><span class="sxs-lookup"><span data-stu-id="f0823-110">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="f0823-111">ID do último evento de conformidade processado.</span><span class="sxs-lookup"><span data-stu-id="f0823-111">ID of the latest processed compliance event.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0823-112">activeServerID</span><span class="sxs-lookup"><span data-stu-id="f0823-112">activeServerID</span></span></p></td>
<td><p><span data-ttu-id="f0823-113">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="f0823-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="f0823-114">ID do servidor de conformidade que possui o bloqueio exclusivo no banco de dados, ou -1 se nenhum.</span><span class="sxs-lookup"><span data-stu-id="f0823-114">ID of the Compliance server holding the exclusive lock on the database, or -1 if none.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0823-115">lockExpirationTime</span><span class="sxs-lookup"><span data-stu-id="f0823-115">lockExpirationTime</span></span></p></td>
<td><p><span data-ttu-id="f0823-116">datetime2, não nulo</span><span class="sxs-lookup"><span data-stu-id="f0823-116">datetime2, not null</span></span></p></td>
<td><p><span data-ttu-id="f0823-117">Hora de expiração do bloqueio (se activeServerID não for igual a -1).</span><span class="sxs-lookup"><span data-stu-id="f0823-117">Lock expiration time (if activeServerID is not -1).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

