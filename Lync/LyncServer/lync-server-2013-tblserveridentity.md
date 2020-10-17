---
title: 'Lync Server 2013: tblServerIdentity'
description: 'Lync Server 2013: tblServerIdentity.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblServerIdentity
ms:assetid: 5411c9bc-b0b3-41fc-8b7e-fa71cccd770b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558648(v=OCS.15)
ms:contentKeyID: 48184125
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e954618cb373f2cf4f1b7ed929c3aaf6d8875e92
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564527"
---
# <a name="tblserveridentity-in-lync-server-2013"></a><span data-ttu-id="85aa0-103">tblServerIdentity no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="85aa0-103">tblServerIdentity in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="85aa0-104">_**Última modificação do tópico:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="85aa0-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="85aa0-105">tblServerIdentity contém os servidores de chat ativos no pool do servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="85aa0-105">tblServerIdentity contains the active chat servers in the Persistent Chat Server pool.</span></span>

### <a name="columns"></a><span data-ttu-id="85aa0-106">Colunas</span><span class="sxs-lookup"><span data-stu-id="85aa0-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="85aa0-107">Coluna</span><span class="sxs-lookup"><span data-stu-id="85aa0-107">Column</span></span></th>
<th><span data-ttu-id="85aa0-108">Tipo</span><span class="sxs-lookup"><span data-stu-id="85aa0-108">Type</span></span></th>
<th><span data-ttu-id="85aa0-109">Descrição</span><span class="sxs-lookup"><span data-stu-id="85aa0-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="85aa0-110">serverID</span><span class="sxs-lookup"><span data-stu-id="85aa0-110">serverID</span></span></p></td>
<td><p><span data-ttu-id="85aa0-111">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="85aa0-111">int, not null</span></span></p></td>
<td><p><span data-ttu-id="85aa0-112">Identificação do Servidor.</span><span class="sxs-lookup"><span data-stu-id="85aa0-112">Server ID.</span></span> <span data-ttu-id="85aa0-113">Corresponde à ID de instância do repositório de gerenciamento central.</span><span class="sxs-lookup"><span data-stu-id="85aa0-113">Corresponds to the instance ID from Central Management store.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="85aa0-114">E/ou</span><span class="sxs-lookup"><span data-stu-id="85aa0-114">serverAddress</span></span></p></td>
<td><p><span data-ttu-id="85aa0-115">nvarchar (256), não nulo</span><span class="sxs-lookup"><span data-stu-id="85aa0-115">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="85aa0-116">Endereço do Servidor utilizando o endereço do Windows Communication Foundation.</span><span class="sxs-lookup"><span data-stu-id="85aa0-116">Server address using the Windows Communication Foundation address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="85aa0-117">serverLastPingTime</span><span class="sxs-lookup"><span data-stu-id="85aa0-117">serverLastPingTime</span></span></p></td>
<td><p><span data-ttu-id="85aa0-118">datetime</span><span class="sxs-lookup"><span data-stu-id="85aa0-118">datetime</span></span></p></td>
<td><p><span data-ttu-id="85aa0-119">A última vez em que o Servidor de Canal atualizou esta linha para fornecer evidências de que está sendo executado.</span><span class="sxs-lookup"><span data-stu-id="85aa0-119">The latest time that the Channel Server updated this row to give evidence that it is running.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="85aa0-120">Chave</span><span class="sxs-lookup"><span data-stu-id="85aa0-120">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="85aa0-121">Coluna</span><span class="sxs-lookup"><span data-stu-id="85aa0-121">Column</span></span></th>
<th><span data-ttu-id="85aa0-122">Descrição</span><span class="sxs-lookup"><span data-stu-id="85aa0-122">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="85aa0-123">serverID</span><span class="sxs-lookup"><span data-stu-id="85aa0-123">serverID</span></span></p></td>
<td><p><span data-ttu-id="85aa0-124">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="85aa0-124">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

