---
title: 'Lync Server 2013: tblNode'
description: 'Lync Server 2013: tblNode.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblNode
ms:assetid: a31d2961-aa83-4286-a12e-15d279c95f19
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615024(v=OCS.15)
ms:contentKeyID: 48184960
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d0a5d630621c32cbc54501249c7a679bf4023c60
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547547"
---
# <a name="tblnode-in-lync-server-2013"></a><span data-ttu-id="88b07-103">tblNode no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="88b07-103">tblNode in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="88b07-104">_**Última modificação do tópico:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="88b07-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="88b07-105">tblNode contém a árvore de objetos (com nós de sala de categoria ou de chat) conforme gerenciado no painel de controle do Lync Server 2013 e cmdlets administrativos.</span><span class="sxs-lookup"><span data-stu-id="88b07-105">tblNode contains the object tree (with category or chat room nodes) as managed in the Lync Server 2013 Control Panel and administrative cmdlets.</span></span>

### <a name="columns"></a><span data-ttu-id="88b07-106">Colunas</span><span class="sxs-lookup"><span data-stu-id="88b07-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="88b07-107">Coluna</span><span class="sxs-lookup"><span data-stu-id="88b07-107">Column</span></span></th>
<th><span data-ttu-id="88b07-108">Tipo</span><span class="sxs-lookup"><span data-stu-id="88b07-108">Type</span></span></th>
<th><span data-ttu-id="88b07-109">Descrição</span><span class="sxs-lookup"><span data-stu-id="88b07-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="88b07-110">nodeID</span><span class="sxs-lookup"><span data-stu-id="88b07-110">nodeID</span></span></p></td>
<td><p><span data-ttu-id="88b07-111">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="88b07-111">int, not null</span></span></p></td>
<td><p><span data-ttu-id="88b07-112">ID do Nó (número único).</span><span class="sxs-lookup"><span data-stu-id="88b07-112">Node ID (unique number).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88b07-113">nodeGuid</span><span class="sxs-lookup"><span data-stu-id="88b07-113">nodeGuid</span></span></p></td>
<td><p><span data-ttu-id="88b07-114">GUID, não nulo</span><span class="sxs-lookup"><span data-stu-id="88b07-114">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="88b07-115">GUIDO do Nó.</span><span class="sxs-lookup"><span data-stu-id="88b07-115">Node GUID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88b07-116">parentID</span><span class="sxs-lookup"><span data-stu-id="88b07-116">parentID</span></span></p></td>
<td><p><span data-ttu-id="88b07-117">int</span><span class="sxs-lookup"><span data-stu-id="88b07-117">int</span></span></p></td>
<td><p><span data-ttu-id="88b07-p101">ID do nó do pai. O nó raiz (com ID 1) inclui si mesmo como pai também.</span><span class="sxs-lookup"><span data-stu-id="88b07-p101">Node ID of parent. The root node (with ID 1) includes itself as parent as well.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88b07-120">nodeType</span><span class="sxs-lookup"><span data-stu-id="88b07-120">nodeType</span></span></p></td>
<td><p><span data-ttu-id="88b07-121">bit, não nulo</span><span class="sxs-lookup"><span data-stu-id="88b07-121">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="88b07-122">Verdadeiro se o nó for uma categoria.</span><span class="sxs-lookup"><span data-stu-id="88b07-122">True if the node is a category.</span></span></p>
<p><span data-ttu-id="88b07-123">Falso se o nó for uma sala de chat.</span><span class="sxs-lookup"><span data-stu-id="88b07-123">False if the node is a chat room.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88b07-124">Nome</span><span class="sxs-lookup"><span data-stu-id="88b07-124">nodeName</span></span></p></td>
<td><p><span data-ttu-id="88b07-125">nvarchar (256), não nulo</span><span class="sxs-lookup"><span data-stu-id="88b07-125">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="88b07-126">Nome do nó.</span><span class="sxs-lookup"><span data-stu-id="88b07-126">Node name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88b07-127">nodeDesc</span><span class="sxs-lookup"><span data-stu-id="88b07-127">nodeDesc</span></span></p></td>
<td><p><span data-ttu-id="88b07-128">nvarchar (256), não nulo</span><span class="sxs-lookup"><span data-stu-id="88b07-128">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="88b07-129">Descrição do nó.</span><span class="sxs-lookup"><span data-stu-id="88b07-129">Node description.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88b07-130">invite</span><span class="sxs-lookup"><span data-stu-id="88b07-130">invite</span></span></p></td>
<td><p><span data-ttu-id="88b07-131">bits</span><span class="sxs-lookup"><span data-stu-id="88b07-131">bit</span></span></p></td>
<td><p><span data-ttu-id="88b07-132">Para categorias:</span><span class="sxs-lookup"><span data-stu-id="88b07-132">For categories:</span></span></p>
<ul>
<li><p><span data-ttu-id="88b07-133">Verdadeiro se convites estiverem ativados.</span><span class="sxs-lookup"><span data-stu-id="88b07-133">True if invites are on.</span></span></p></li>
<li><p><span data-ttu-id="88b07-134">Falso se convites estiverem desativados.</span><span class="sxs-lookup"><span data-stu-id="88b07-134">False if invites are off.</span></span></p></li>
</ul>
<p><span data-ttu-id="88b07-135">Para salas:</span><span class="sxs-lookup"><span data-stu-id="88b07-135">For rooms:</span></span></p>
<ul>
<li><p><span data-ttu-id="88b07-136">Falso se convites estiverem desativados (substitui a categoria pai).</span><span class="sxs-lookup"><span data-stu-id="88b07-136">False if invites are off (overrides the parent category).</span></span></p></li>
<li><p><span data-ttu-id="88b07-137">Nulo se a configuração de convites for herdada da categoria pai.</span><span class="sxs-lookup"><span data-stu-id="88b07-137">Null if the invites setting is inherited from the parent category.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88b07-138">login</span><span class="sxs-lookup"><span data-stu-id="88b07-138">logged</span></span></p></td>
<td><p><span data-ttu-id="88b07-139">bits</span><span class="sxs-lookup"><span data-stu-id="88b07-139">bit</span></span></p></td>
<td><p><span data-ttu-id="88b07-140">Para categorias:</span><span class="sxs-lookup"><span data-stu-id="88b07-140">For categories:</span></span></p>
<ul>
<li><p><span data-ttu-id="88b07-141">Verdadeiro se o histórico de chat estiver ativado.</span><span class="sxs-lookup"><span data-stu-id="88b07-141">True if chat history is on.</span></span></p></li>
<li><p><span data-ttu-id="88b07-142">Falso se o histórico de chat estiver desativado.</span><span class="sxs-lookup"><span data-stu-id="88b07-142">False if chat history is off.</span></span></p></li>
</ul>
<p><span data-ttu-id="88b07-143">Para salas:</span><span class="sxs-lookup"><span data-stu-id="88b07-143">For rooms:</span></span></p>
<ul>
<li><p><span data-ttu-id="88b07-144">Vazio.</span><span class="sxs-lookup"><span data-stu-id="88b07-144">Null.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88b07-145">FilePost</span><span class="sxs-lookup"><span data-stu-id="88b07-145">filePost</span></span></p></td>
<td><p><span data-ttu-id="88b07-146">bits</span><span class="sxs-lookup"><span data-stu-id="88b07-146">bit</span></span></p></td>
<td><p><span data-ttu-id="88b07-147">Para categorias:</span><span class="sxs-lookup"><span data-stu-id="88b07-147">For categories:</span></span></p>
<ul>
<li><p><span data-ttu-id="88b07-148">Verdadeiro se o carregamento de arquivos for permitido.</span><span class="sxs-lookup"><span data-stu-id="88b07-148">True if file uploads are allowed.</span></span></p></li>
<li><p><span data-ttu-id="88b07-149">Falso se o carregamento de arquivos não for permitido.</span><span class="sxs-lookup"><span data-stu-id="88b07-149">False if file uploads are disallowed.</span></span></p></li>
</ul>
<p><span data-ttu-id="88b07-150">Para salas:</span><span class="sxs-lookup"><span data-stu-id="88b07-150">For rooms:</span></span></p>
<ul>
<li><p><span data-ttu-id="88b07-151">Vazio.</span><span class="sxs-lookup"><span data-stu-id="88b07-151">Null.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88b07-152">desabilitadas</span><span class="sxs-lookup"><span data-stu-id="88b07-152">disabled</span></span></p></td>
<td><p><span data-ttu-id="88b07-153">bit, não nulo</span><span class="sxs-lookup"><span data-stu-id="88b07-153">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="88b07-p102">Verdadeiros se a sala de chat estiver desabilitada. Aplica-se somente a salas de chat (falso para categorias).</span><span class="sxs-lookup"><span data-stu-id="88b07-p102">True if the chat room is disabled. Applies only to chat rooms. (False for categories.)</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88b07-157">comportamental</span><span class="sxs-lookup"><span data-stu-id="88b07-157">behavior</span></span></p></td>
<td><p><span data-ttu-id="88b07-158">smallint, not null</span><span class="sxs-lookup"><span data-stu-id="88b07-158">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="88b07-159">Comportamento (consultado na tabela EnumValue):</span><span class="sxs-lookup"><span data-stu-id="88b07-159">Behavior (looked up in EnumValue table):</span></span></p>
<ul>
<li><p><span data-ttu-id="88b07-160">4: Normal (salas de chat normais).</span><span class="sxs-lookup"><span data-stu-id="88b07-160">4: Normal (normal chat rooms).</span></span></p></li>
<li><p><span data-ttu-id="88b07-161">5: Auditório (salas de chat de auditório, somente apresentadores podem contribuir).</span><span class="sxs-lookup"><span data-stu-id="88b07-161">5: Auditorium (auditorium chat rooms, only presenters can contribute).</span></span></p></li>
</ul>
<p><span data-ttu-id="88b07-162">Aplica-se somente a salas de chat</span><span class="sxs-lookup"><span data-stu-id="88b07-162">Applies only to chat rooms.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88b07-163">visibility</span><span class="sxs-lookup"><span data-stu-id="88b07-163">visibility</span></span></p></td>
<td><p><span data-ttu-id="88b07-164">smallint, não nulo</span><span class="sxs-lookup"><span data-stu-id="88b07-164">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="88b07-165">Visibilidade (consultado na tabela EnumValue):</span><span class="sxs-lookup"><span data-stu-id="88b07-165">Visibility (looked up on EnumValue table):</span></span></p>
<ul>
<li><p><span data-ttu-id="88b07-166">2: Particular</span><span class="sxs-lookup"><span data-stu-id="88b07-166">2: Private</span></span></p></li>
<li><p><span data-ttu-id="88b07-167">3: Com escopo</span><span class="sxs-lookup"><span data-stu-id="88b07-167">3: Scoped</span></span></p></li>
<li><p><span data-ttu-id="88b07-168">6: Abrir</span><span class="sxs-lookup"><span data-stu-id="88b07-168">6: Open</span></span></p></li>
</ul>
<p><span data-ttu-id="88b07-169">Aplica-se somente a salas de chat</span><span class="sxs-lookup"><span data-stu-id="88b07-169">Applies only to chat rooms.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88b07-170">siopID</span><span class="sxs-lookup"><span data-stu-id="88b07-170">siopID</span></span></p></td>
<td><p><span data-ttu-id="88b07-171">GUID</span><span class="sxs-lookup"><span data-stu-id="88b07-171">GUID</span></span></p></td>
<td><p><span data-ttu-id="88b07-p103">O GUID de um suplemento é associado a esta sala de chat (categorias não possuem suplementos).</span><span class="sxs-lookup"><span data-stu-id="88b07-p103">Add-In GUID if an add-in is associated with this chat room. (Categories do not have add-ins.)</span></span></p>
<p><span data-ttu-id="88b07-174">As informações do suplemento são consultadas na tabela SiopWhiteList.</span><span class="sxs-lookup"><span data-stu-id="88b07-174">The add-in information is looked up in SiopWhiteList table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88b07-175">nodeAddedBy</span><span class="sxs-lookup"><span data-stu-id="88b07-175">nodeAddedBy</span></span></p></td>
<td><p><span data-ttu-id="88b07-176">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="88b07-176">int, not null</span></span></p></td>
<td><p><span data-ttu-id="88b07-177">ID da entidade de segurança que criou este nó.</span><span class="sxs-lookup"><span data-stu-id="88b07-177">ID of the principal that created this node.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88b07-178">nodeAddedOn</span><span class="sxs-lookup"><span data-stu-id="88b07-178">nodeAddedOn</span></span></p></td>
<td><p><span data-ttu-id="88b07-179">bigint, não nulo</span><span class="sxs-lookup"><span data-stu-id="88b07-179">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="88b07-180">Carimbo de data/hora da criação do nó.</span><span class="sxs-lookup"><span data-stu-id="88b07-180">Time stamp of the node creation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88b07-181">nodeUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="88b07-181">nodeUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="88b07-182">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="88b07-182">int, not null</span></span></p></td>
<td><p><span data-ttu-id="88b07-183">ID da entidade de segurança que efetuou a atualização mais recente deste nó.</span><span class="sxs-lookup"><span data-stu-id="88b07-183">ID of the principal that did the latest update of this node.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88b07-184">nodeUpdatedOn</span><span class="sxs-lookup"><span data-stu-id="88b07-184">nodeUpdatedOn</span></span></p></td>
<td><p><span data-ttu-id="88b07-185">bigint, não nulo</span><span class="sxs-lookup"><span data-stu-id="88b07-185">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="88b07-186">Carimbo de data/hora da última atualização deste nó.</span><span class="sxs-lookup"><span data-stu-id="88b07-186">Time stamp of the latest update of this node.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88b07-187">purgedOn</span><span class="sxs-lookup"><span data-stu-id="88b07-187">purgedOn</span></span></p></td>
<td><p><span data-ttu-id="88b07-188">datetime</span><span class="sxs-lookup"><span data-stu-id="88b07-188">datetime</span></span></p></td>
<td><p><span data-ttu-id="88b07-p104">Horário da última operação de limpeza (remoção de escopos da tabela tblScopedPrincipal e funções da tabela tblPrincipalRole) que afetou este nó. Usado pelo mecanismo de atualização do cache interno do serviço de chat.</span><span class="sxs-lookup"><span data-stu-id="88b07-p104">Time of the latest purge operation (removal of scopes from tblScopedPrincipal table and roles from tblPrincipalRole table) that affected this node. This is used by the Chat service’s internal cache update mechanism.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="88b07-191">Chaves</span><span class="sxs-lookup"><span data-stu-id="88b07-191">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="88b07-192">Coluna</span><span class="sxs-lookup"><span data-stu-id="88b07-192">Column</span></span></th>
<th><span data-ttu-id="88b07-193">Descrição</span><span class="sxs-lookup"><span data-stu-id="88b07-193">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="88b07-194">nodeID</span><span class="sxs-lookup"><span data-stu-id="88b07-194">nodeID</span></span></p></td>
<td><p><span data-ttu-id="88b07-195">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="88b07-195">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88b07-196">comportamental</span><span class="sxs-lookup"><span data-stu-id="88b07-196">behavior</span></span></p></td>
<td><p><span data-ttu-id="88b07-197">Chave estrangeira com consulta na tabela tblEnumValue.valueID.</span><span class="sxs-lookup"><span data-stu-id="88b07-197">Foreign key with lookup in tblEnumValue.valueID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88b07-198">visibility</span><span class="sxs-lookup"><span data-stu-id="88b07-198">visibility</span></span></p></td>
<td><p><span data-ttu-id="88b07-199">Chave estrangeira com consulta na tabela tblEnumValue.valueID.</span><span class="sxs-lookup"><span data-stu-id="88b07-199">Foreign key with lookup in tblEnumValue.valueID table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88b07-200">parentID</span><span class="sxs-lookup"><span data-stu-id="88b07-200">parentID</span></span></p></td>
<td><p><span data-ttu-id="88b07-201">Chave estrangeira com pesquisa na tabela tblNode.nodeID.</span><span class="sxs-lookup"><span data-stu-id="88b07-201">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88b07-202">siopID</span><span class="sxs-lookup"><span data-stu-id="88b07-202">siopID</span></span></p></td>
<td><p><span data-ttu-id="88b07-203">Chave estrangeira com consulta na tabela tblSiopWhiteList.siopId.</span><span class="sxs-lookup"><span data-stu-id="88b07-203">Foreign key with lookup in tblSiopWhiteList.siopId table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

