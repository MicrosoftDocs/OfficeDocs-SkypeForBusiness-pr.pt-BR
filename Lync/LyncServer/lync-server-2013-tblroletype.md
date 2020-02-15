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
ms.openlocfilehash: ab96d6cd090ebaaa9e33ddf1672ab704ee371f8b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046144"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblroletype-in-lync-server-2013"></a><span data-ttu-id="1369f-102">tblRoleType no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1369f-102">tblRoleType in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1369f-103">_**Última modificação do tópico:** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="1369f-103">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="1369f-104">tblRoleType é uma tabela de pesquisa estática com tipos de funções e seus conjuntos de permissões associados.</span><span class="sxs-lookup"><span data-stu-id="1369f-104">tblRoleType is a static lookup table with role types and their associated permission sets.</span></span>

### <a name="columns"></a><span data-ttu-id="1369f-105">Colunas</span><span class="sxs-lookup"><span data-stu-id="1369f-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1369f-106">Coluna</span><span class="sxs-lookup"><span data-stu-id="1369f-106">Column</span></span></th>
<th><span data-ttu-id="1369f-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="1369f-107">Type</span></span></th>
<th><span data-ttu-id="1369f-108">Descrição</span><span class="sxs-lookup"><span data-stu-id="1369f-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1369f-109">rtypeID</span><span class="sxs-lookup"><span data-stu-id="1369f-109">rtypeID</span></span></p></td>
<td><p><span data-ttu-id="1369f-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="1369f-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="1369f-111">ID do tipo de função.</span><span class="sxs-lookup"><span data-stu-id="1369f-111">Role type ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1369f-112">rtypeDesc</span><span class="sxs-lookup"><span data-stu-id="1369f-112">rtypeDesc</span></span></p></td>
<td><p><span data-ttu-id="1369f-113">nvarchar (256), not null</span><span class="sxs-lookup"><span data-stu-id="1369f-113">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="1369f-p101">Descrição do tipo de função. Existem quatro funções disponíveis:</span><span class="sxs-lookup"><span data-stu-id="1369f-p101">Role type description. There are four available roles:</span></span></p>
<ul>
<li><p><span data-ttu-id="1369f-116">Membro: Membro da sala de chat</span><span class="sxs-lookup"><span data-stu-id="1369f-116">Member: Chat room member</span></span></p></li>
<li><p><span data-ttu-id="1369f-117">Gerente: Gerente da sala de chat</span><span class="sxs-lookup"><span data-stu-id="1369f-117">Manager: Chat room manager</span></span></p></li>
<li><p><span data-ttu-id="1369f-118">Com voz: Apresentador para uma sala de chat de auditório</span><span class="sxs-lookup"><span data-stu-id="1369f-118">Voiced: Presenter for an auditorium chat room</span></span></p></li>
<li><p><span data-ttu-id="1369f-119">Criador: Pode criar salas de bate-papo</span><span class="sxs-lookup"><span data-stu-id="1369f-119">Creator: Can create chat rooms</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1369f-120">rtypeAllowedPermSet</span><span class="sxs-lookup"><span data-stu-id="1369f-120">rtypeAllowedPermSet</span></span></p></td>
<td><p><span data-ttu-id="1369f-121">bigint, not null</span><span class="sxs-lookup"><span data-stu-id="1369f-121">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="1369f-p102">Permissão configurada para a função. Os bits usados são:</span><span class="sxs-lookup"><span data-stu-id="1369f-p102">Permission set for the role. The used bits are:</span></span></p>
<ul>
<li><p><span data-ttu-id="1369f-124">2: True se a função puder gerenciar nós.</span><span class="sxs-lookup"><span data-stu-id="1369f-124">2: True if the role can manage nodes.</span></span></p></li>
<li><p><span data-ttu-id="1369f-125">4: True se a função puder criar nós filhos.</span><span class="sxs-lookup"><span data-stu-id="1369f-125">4: True if the role can create children nodes.</span></span></p></li>
<li><p><span data-ttu-id="1369f-126">7: True se a função puder entrar em uma sala de chat (ou nas salas filhos de uma categoria).</span><span class="sxs-lookup"><span data-stu-id="1369f-126">7: True if the role can join a chat room (or children chat rooms of a category).</span></span></p></li>
<li><p><span data-ttu-id="1369f-127">8: True se a função puder conversar em uma sala de chat (ou nas salas filhos de uma categoria).</span><span class="sxs-lookup"><span data-stu-id="1369f-127">8: True if the role can chat in a chat room (or in children chat rooms of a category).</span></span></p></li>
<li><p><span data-ttu-id="1369f-128">10: True se a função puder ler o histórico do chat mesmo quando não tiver entrado na sala de chat.</span><span class="sxs-lookup"><span data-stu-id="1369f-128">10: True if the role can read chat history even when not joined to a chat room.</span></span></p></li>
<li><p><span data-ttu-id="1369f-p103">11: True se a função puder ver a sala de chat (refinado por fatores como escopo e visibilidade).</span><span class="sxs-lookup"><span data-stu-id="1369f-p103">11: True if the role can see the chat room. (This is further refined by factors such as scope and visibility.)</span></span></p></li>
<li><p><span data-ttu-id="1369f-131">12: True se a função puder conversar em uma sala de chat de auditório.</span><span class="sxs-lookup"><span data-stu-id="1369f-131">12: True if the role can chat in an auditorium chat room.</span></span></p></li>
<li><p><span data-ttu-id="1369f-132">13: True se a função puder ignorar as regras de visibilidade ao exibir nós.</span><span class="sxs-lookup"><span data-stu-id="1369f-132">13: True if the role can bypass visibility rules when viewing nodes.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="1369f-133">Chave</span><span class="sxs-lookup"><span data-stu-id="1369f-133">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1369f-134">Coluna</span><span class="sxs-lookup"><span data-stu-id="1369f-134">Column</span></span></th>
<th><span data-ttu-id="1369f-135">Descrição</span><span class="sxs-lookup"><span data-stu-id="1369f-135">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1369f-136">rtypeID</span><span class="sxs-lookup"><span data-stu-id="1369f-136">rtypeID</span></span></p></td>
<td><p><span data-ttu-id="1369f-137">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="1369f-137">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

