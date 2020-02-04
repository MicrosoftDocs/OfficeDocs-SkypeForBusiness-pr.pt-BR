---
title: 'Lync Server 2013: tblRoleType'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblRoleType
ms:assetid: 1eac3a54-656a-40ac-b771-edfc64d6e34b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558623(v=OCS.15)
ms:contentKeyID: 48183577
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ba6b5041453b0965fafc12ada2be62ec42316f89
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731181"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblroletype-in-lync-server-2013"></a><span data-ttu-id="07288-102">tblRoleType no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="07288-102">tblRoleType in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="07288-103">_**Tópico da última modificação:** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="07288-103">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="07288-104">tblRoleType é uma tabela de pesquisa estática com tipos de função e seus conjuntos de permissões associados.</span><span class="sxs-lookup"><span data-stu-id="07288-104">tblRoleType is a static lookup table with role types and their associated permission sets.</span></span>

### <a name="columns"></a><span data-ttu-id="07288-105">Colunas</span><span class="sxs-lookup"><span data-stu-id="07288-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="07288-106">Coluna</span><span class="sxs-lookup"><span data-stu-id="07288-106">Column</span></span></th>
<th><span data-ttu-id="07288-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="07288-107">Type</span></span></th>
<th><span data-ttu-id="07288-108">Descrição</span><span class="sxs-lookup"><span data-stu-id="07288-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="07288-109">rtypeID</span><span class="sxs-lookup"><span data-stu-id="07288-109">rtypeID</span></span></p></td>
<td><p><span data-ttu-id="07288-110">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="07288-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="07288-111">ID do tipo de função.</span><span class="sxs-lookup"><span data-stu-id="07288-111">Role type ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="07288-112">rtypeDesc</span><span class="sxs-lookup"><span data-stu-id="07288-112">rtypeDesc</span></span></p></td>
<td><p><span data-ttu-id="07288-113">nvarchar (256), NOT NULL</span><span class="sxs-lookup"><span data-stu-id="07288-113">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="07288-114">Descrição do tipo de função.</span><span class="sxs-lookup"><span data-stu-id="07288-114">Role type description.</span></span> <span data-ttu-id="07288-115">Há quatro funções disponíveis:</span><span class="sxs-lookup"><span data-stu-id="07288-115">There are four available roles:</span></span></p>
<ul>
<li><p><span data-ttu-id="07288-116">Membro: membro da sala de chat</span><span class="sxs-lookup"><span data-stu-id="07288-116">Member: Chat room member</span></span></p></li>
<li><p><span data-ttu-id="07288-117">Manager: gerente da sala de chat</span><span class="sxs-lookup"><span data-stu-id="07288-117">Manager: Chat room manager</span></span></p></li>
<li><p><span data-ttu-id="07288-118">Encaixado: apresentador para uma sala de chat do Auditorium</span><span class="sxs-lookup"><span data-stu-id="07288-118">Voiced: Presenter for an auditorium chat room</span></span></p></li>
<li><p><span data-ttu-id="07288-119">Creator: pode criar salas de chat</span><span class="sxs-lookup"><span data-stu-id="07288-119">Creator: Can create chat rooms</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="07288-120">rtypeAllowedPermSet</span><span class="sxs-lookup"><span data-stu-id="07288-120">rtypeAllowedPermSet</span></span></p></td>
<td><p><span data-ttu-id="07288-121">bigint, e não nulo</span><span class="sxs-lookup"><span data-stu-id="07288-121">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="07288-122">Conjunto de permissões para a função.</span><span class="sxs-lookup"><span data-stu-id="07288-122">Permission set for the role.</span></span> <span data-ttu-id="07288-123">Os bits usados são:</span><span class="sxs-lookup"><span data-stu-id="07288-123">The used bits are:</span></span></p>
<ul>
<li><p><span data-ttu-id="07288-124">2: verdadeiro se a função puder gerenciar nós.</span><span class="sxs-lookup"><span data-stu-id="07288-124">2: True if the role can manage nodes.</span></span></p></li>
<li><p><span data-ttu-id="07288-125">4: verdadeiro se a função puder criar nós filhos.</span><span class="sxs-lookup"><span data-stu-id="07288-125">4: True if the role can create children nodes.</span></span></p></li>
<li><p><span data-ttu-id="07288-126">7: verdadeiro se a função puder ingressar em uma sala de chat (ou salas de chat dos filhos de uma categoria).</span><span class="sxs-lookup"><span data-stu-id="07288-126">7: True if the role can join a chat room (or children chat rooms of a category).</span></span></p></li>
<li><p><span data-ttu-id="07288-127">8: verdadeiro se a função puder conversar em uma sala de chat (ou nas salas de chat dos filhos de uma categoria).</span><span class="sxs-lookup"><span data-stu-id="07288-127">8: True if the role can chat in a chat room (or in children chat rooms of a category).</span></span></p></li>
<li><p><span data-ttu-id="07288-128">10: verdadeiro se a função puder ler o histórico de chats mesmo quando não estiver associado a uma sala de chat.</span><span class="sxs-lookup"><span data-stu-id="07288-128">10: True if the role can read chat history even when not joined to a chat room.</span></span></p></li>
<li><p><span data-ttu-id="07288-129">11: verdadeiro se a função puder ver a sala de chat.</span><span class="sxs-lookup"><span data-stu-id="07288-129">11: True if the role can see the chat room.</span></span> <span data-ttu-id="07288-130">(Isso é ainda mais refinado por fatores como escopo e visibilidade.)</span><span class="sxs-lookup"><span data-stu-id="07288-130">(This is further refined by factors such as scope and visibility.)</span></span></p></li>
<li><p><span data-ttu-id="07288-131">12: verdadeiro se a função puder conversar em uma sala de chat do Auditorium.</span><span class="sxs-lookup"><span data-stu-id="07288-131">12: True if the role can chat in an auditorium chat room.</span></span></p></li>
<li><p><span data-ttu-id="07288-132">13: verdadeiro se a função puder ignorar as regras de visibilidade ao exibir nós.</span><span class="sxs-lookup"><span data-stu-id="07288-132">13: True if the role can bypass visibility rules when viewing nodes.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="07288-133">Chave</span><span class="sxs-lookup"><span data-stu-id="07288-133">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="07288-134">Coluna</span><span class="sxs-lookup"><span data-stu-id="07288-134">Column</span></span></th>
<th><span data-ttu-id="07288-135">Descrição</span><span class="sxs-lookup"><span data-stu-id="07288-135">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="07288-136">rtypeID</span><span class="sxs-lookup"><span data-stu-id="07288-136">rtypeID</span></span></p></td>
<td><p><span data-ttu-id="07288-137">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="07288-137">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

