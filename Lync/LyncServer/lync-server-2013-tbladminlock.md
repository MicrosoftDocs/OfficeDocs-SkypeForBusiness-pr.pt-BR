---
title: 'Lync Server 2013: tblAdminLock'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblAdminLock
ms:assetid: 785a43c0-6892-474c-821c-fa9cdbeb99d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558665(v=OCS.15)
ms:contentKeyID: 48184560
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 89e1509a1a84e0a9dd03527eedfb0b9e6da1590e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764227"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tbladminlock-in-lync-server-2013"></a><span data-ttu-id="0792e-102">tblAdminLock no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0792e-102">tblAdminLock in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0792e-103">_**Tópico da última modificação:** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="0792e-103">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="0792e-104">tblAdminLock contém o bloqueio do administrador necessário para executar alguns comandos de administrador.</span><span class="sxs-lookup"><span data-stu-id="0792e-104">tblAdminLock contains the administrator lock that is needed to run some administrator commands.</span></span>

### <a name="columns"></a><span data-ttu-id="0792e-105">Colunas</span><span class="sxs-lookup"><span data-stu-id="0792e-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0792e-106">Coluna</span><span class="sxs-lookup"><span data-stu-id="0792e-106">Column</span></span></th>
<th><span data-ttu-id="0792e-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="0792e-107">Type</span></span></th>
<th><span data-ttu-id="0792e-108">Descrição</span><span class="sxs-lookup"><span data-stu-id="0792e-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0792e-109">lockExpiresTime</span><span class="sxs-lookup"><span data-stu-id="0792e-109">lockExpiresTime</span></span></p></td>
<td><p><span data-ttu-id="0792e-110">DateTime, não nulo</span><span class="sxs-lookup"><span data-stu-id="0792e-110">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="0792e-111">Bloquear data e hora de expiração.</span><span class="sxs-lookup"><span data-stu-id="0792e-111">Lock expiration date and time.</span></span> <span data-ttu-id="0792e-112">O proprietário pode estender esse valor periodicamente.</span><span class="sxs-lookup"><span data-stu-id="0792e-112">The owner can extend this value periodically.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0792e-113">lockServerID</span><span class="sxs-lookup"><span data-stu-id="0792e-113">lockServerID</span></span></p></td>
<td><p><span data-ttu-id="0792e-114">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="0792e-114">int, not null</span></span></p></td>
<td><p><span data-ttu-id="0792e-115">ID do servidor que é proprietário do bloqueio.</span><span class="sxs-lookup"><span data-stu-id="0792e-115">ID of the server that owns the lock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0792e-116">lockActorID</span><span class="sxs-lookup"><span data-stu-id="0792e-116">lockActorID</span></span></p></td>
<td><p><span data-ttu-id="0792e-117">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="0792e-117">int, not null</span></span></p></td>
<td><p><span data-ttu-id="0792e-118">ID da entidade de segurança que é proprietária do bloqueio.</span><span class="sxs-lookup"><span data-stu-id="0792e-118">ID of the principal that owns the lock.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

