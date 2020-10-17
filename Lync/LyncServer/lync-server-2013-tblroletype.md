---
title: 'Lync Server 2013: tblRoleType'
description: 'Lync Server 2013: tblRoleType.'
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
ms.openlocfilehash: f458259acaee7821d5f6a7339b993c70fe65f595
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568537"
---
# <a name="tblroletype-in-lync-server-2013"></a><span data-ttu-id="c91a1-103">tblRoleType no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c91a1-103">tblRoleType in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c91a1-104">_**Última modificação do tópico:** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="c91a1-104">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="c91a1-105">tblRoleType é uma tabela de pesquisa estática com tipos de funções e seus conjuntos de permissões associados.</span><span class="sxs-lookup"><span data-stu-id="c91a1-105">tblRoleType is a static lookup table with role types and their associated permission sets.</span></span>

### <a name="columns"></a><span data-ttu-id="c91a1-106">Colunas</span><span class="sxs-lookup"><span data-stu-id="c91a1-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c91a1-107">Coluna</span><span class="sxs-lookup"><span data-stu-id="c91a1-107">Column</span></span></th>
<th><span data-ttu-id="c91a1-108">Tipo</span><span class="sxs-lookup"><span data-stu-id="c91a1-108">Type</span></span></th>
<th><span data-ttu-id="c91a1-109">Descrição</span><span class="sxs-lookup"><span data-stu-id="c91a1-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c91a1-110">rtypeID</span><span class="sxs-lookup"><span data-stu-id="c91a1-110">rtypeID</span></span></p></td>
<td><p><span data-ttu-id="c91a1-111">int, not null</span><span class="sxs-lookup"><span data-stu-id="c91a1-111">int, not null</span></span></p></td>
<td><p><span data-ttu-id="c91a1-112">ID do tipo de função.</span><span class="sxs-lookup"><span data-stu-id="c91a1-112">Role type ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c91a1-113">rtypeDesc</span><span class="sxs-lookup"><span data-stu-id="c91a1-113">rtypeDesc</span></span></p></td>
<td><p><span data-ttu-id="c91a1-114">nvarchar (256), not null</span><span class="sxs-lookup"><span data-stu-id="c91a1-114">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="c91a1-p101">Descrição do tipo de função. Existem quatro funções disponíveis:</span><span class="sxs-lookup"><span data-stu-id="c91a1-p101">Role type description. There are four available roles:</span></span></p>
<ul>
<li><p><span data-ttu-id="c91a1-117">Membro: Membro da sala de chat</span><span class="sxs-lookup"><span data-stu-id="c91a1-117">Member: Chat room member</span></span></p></li>
<li><p><span data-ttu-id="c91a1-118">Gerente: Gerente da sala de chat</span><span class="sxs-lookup"><span data-stu-id="c91a1-118">Manager: Chat room manager</span></span></p></li>
<li><p><span data-ttu-id="c91a1-119">Com voz: Apresentador para uma sala de chat de auditório</span><span class="sxs-lookup"><span data-stu-id="c91a1-119">Voiced: Presenter for an auditorium chat room</span></span></p></li>
<li><p><span data-ttu-id="c91a1-120">Criador: Pode criar salas de bate-papo</span><span class="sxs-lookup"><span data-stu-id="c91a1-120">Creator: Can create chat rooms</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c91a1-121">rtypeAllowedPermSet</span><span class="sxs-lookup"><span data-stu-id="c91a1-121">rtypeAllowedPermSet</span></span></p></td>
<td><p><span data-ttu-id="c91a1-122">bigint, not null</span><span class="sxs-lookup"><span data-stu-id="c91a1-122">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="c91a1-p102">Permissão configurada para a função. Os bits usados são:</span><span class="sxs-lookup"><span data-stu-id="c91a1-p102">Permission set for the role. The used bits are:</span></span></p>
<ul>
<li><p><span data-ttu-id="c91a1-125">2: True se a função puder gerenciar nós.</span><span class="sxs-lookup"><span data-stu-id="c91a1-125">2: True if the role can manage nodes.</span></span></p></li>
<li><p><span data-ttu-id="c91a1-126">4: True se a função puder criar nós filhos.</span><span class="sxs-lookup"><span data-stu-id="c91a1-126">4: True if the role can create children nodes.</span></span></p></li>
<li><p><span data-ttu-id="c91a1-127">7: True se a função puder entrar em uma sala de chat (ou nas salas filhos de uma categoria).</span><span class="sxs-lookup"><span data-stu-id="c91a1-127">7: True if the role can join a chat room (or children chat rooms of a category).</span></span></p></li>
<li><p><span data-ttu-id="c91a1-128">8: True se a função puder conversar em uma sala de chat (ou nas salas filhos de uma categoria).</span><span class="sxs-lookup"><span data-stu-id="c91a1-128">8: True if the role can chat in a chat room (or in children chat rooms of a category).</span></span></p></li>
<li><p><span data-ttu-id="c91a1-129">10: True se a função puder ler o histórico do chat mesmo quando não tiver entrado na sala de chat.</span><span class="sxs-lookup"><span data-stu-id="c91a1-129">10: True if the role can read chat history even when not joined to a chat room.</span></span></p></li>
<li><p><span data-ttu-id="c91a1-p103">11: True se a função puder ver a sala de chat (refinado por fatores como escopo e visibilidade).</span><span class="sxs-lookup"><span data-stu-id="c91a1-p103">11: True if the role can see the chat room. (This is further refined by factors such as scope and visibility.)</span></span></p></li>
<li><p><span data-ttu-id="c91a1-132">12: True se a função puder conversar em uma sala de chat de auditório.</span><span class="sxs-lookup"><span data-stu-id="c91a1-132">12: True if the role can chat in an auditorium chat room.</span></span></p></li>
<li><p><span data-ttu-id="c91a1-133">13: True se a função puder ignorar as regras de visibilidade ao exibir nós.</span><span class="sxs-lookup"><span data-stu-id="c91a1-133">13: True if the role can bypass visibility rules when viewing nodes.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="c91a1-134">Chave</span><span class="sxs-lookup"><span data-stu-id="c91a1-134">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c91a1-135">Coluna</span><span class="sxs-lookup"><span data-stu-id="c91a1-135">Column</span></span></th>
<th><span data-ttu-id="c91a1-136">Descrição</span><span class="sxs-lookup"><span data-stu-id="c91a1-136">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c91a1-137">rtypeID</span><span class="sxs-lookup"><span data-stu-id="c91a1-137">rtypeID</span></span></p></td>
<td><p><span data-ttu-id="c91a1-138">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="c91a1-138">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

