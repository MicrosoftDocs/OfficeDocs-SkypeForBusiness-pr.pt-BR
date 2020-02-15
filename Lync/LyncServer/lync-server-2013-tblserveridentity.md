---
title: 'Lync Server 2013: tblServerIdentity'
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
ms.openlocfilehash: 5f6ed7f0eed08dbb4ab3b0d6f41c9ec91fb719f1
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029182"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblserveridentity-in-lync-server-2013"></a><span data-ttu-id="d9e53-102">tblServerIdentity no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d9e53-102">tblServerIdentity in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d9e53-103">_**Última modificação do tópico:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="d9e53-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="d9e53-104">tblServerIdentity contém os servidores de chat ativos no pool do servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="d9e53-104">tblServerIdentity contains the active chat servers in the Persistent Chat Server pool.</span></span>

### <a name="columns"></a><span data-ttu-id="d9e53-105">Colunas</span><span class="sxs-lookup"><span data-stu-id="d9e53-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d9e53-106">Coluna</span><span class="sxs-lookup"><span data-stu-id="d9e53-106">Column</span></span></th>
<th><span data-ttu-id="d9e53-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="d9e53-107">Type</span></span></th>
<th><span data-ttu-id="d9e53-108">Descrição</span><span class="sxs-lookup"><span data-stu-id="d9e53-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d9e53-109">serverID</span><span class="sxs-lookup"><span data-stu-id="d9e53-109">serverID</span></span></p></td>
<td><p><span data-ttu-id="d9e53-110">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="d9e53-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="d9e53-111">Identificação do Servidor.</span><span class="sxs-lookup"><span data-stu-id="d9e53-111">Server ID.</span></span> <span data-ttu-id="d9e53-112">Corresponde à ID de instância do repositório de gerenciamento central.</span><span class="sxs-lookup"><span data-stu-id="d9e53-112">Corresponds to the instance ID from Central Management store.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d9e53-113">E/ou</span><span class="sxs-lookup"><span data-stu-id="d9e53-113">serverAddress</span></span></p></td>
<td><p><span data-ttu-id="d9e53-114">nvarchar (256), não nulo</span><span class="sxs-lookup"><span data-stu-id="d9e53-114">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="d9e53-115">Endereço do Servidor utilizando o endereço do Windows Communication Foundation.</span><span class="sxs-lookup"><span data-stu-id="d9e53-115">Server address using the Windows Communication Foundation address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d9e53-116">serverLastPingTime</span><span class="sxs-lookup"><span data-stu-id="d9e53-116">serverLastPingTime</span></span></p></td>
<td><p><span data-ttu-id="d9e53-117">datetime</span><span class="sxs-lookup"><span data-stu-id="d9e53-117">datetime</span></span></p></td>
<td><p><span data-ttu-id="d9e53-118">A última vez em que o Servidor de Canal atualizou esta linha para fornecer evidências de que está sendo executado.</span><span class="sxs-lookup"><span data-stu-id="d9e53-118">The latest time that the Channel Server updated this row to give evidence that it is running.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="d9e53-119">Chave</span><span class="sxs-lookup"><span data-stu-id="d9e53-119">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d9e53-120">Coluna</span><span class="sxs-lookup"><span data-stu-id="d9e53-120">Column</span></span></th>
<th><span data-ttu-id="d9e53-121">Descrição</span><span class="sxs-lookup"><span data-stu-id="d9e53-121">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d9e53-122">serverID</span><span class="sxs-lookup"><span data-stu-id="d9e53-122">serverID</span></span></p></td>
<td><p><span data-ttu-id="d9e53-123">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="d9e53-123">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

