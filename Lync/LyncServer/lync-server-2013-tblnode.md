---
title: 'Lync Server 2013: tblNode'
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
ms.openlocfilehash: cee7c67421ae12d08e52bee1b013dfa6280472f3
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142057"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblnode-in-lync-server-2013"></a><span data-ttu-id="d45df-102">tblNode no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d45df-102">tblNode in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d45df-103">_**Última modificação do tópico:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="d45df-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="d45df-104">tblNode contém a árvore de objetos (com nós de sala de categoria ou de chat) conforme gerenciado no painel de controle do Lync Server 2013 e cmdlets administrativos.</span><span class="sxs-lookup"><span data-stu-id="d45df-104">tblNode contains the object tree (with category or chat room nodes) as managed in the Lync Server 2013 Control Panel and administrative cmdlets.</span></span>

### <a name="columns"></a><span data-ttu-id="d45df-105">Colunas</span><span class="sxs-lookup"><span data-stu-id="d45df-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d45df-106">Coluna</span><span class="sxs-lookup"><span data-stu-id="d45df-106">Column</span></span></th>
<th><span data-ttu-id="d45df-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="d45df-107">Type</span></span></th>
<th><span data-ttu-id="d45df-108">Descrição</span><span class="sxs-lookup"><span data-stu-id="d45df-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d45df-109">nodeID</span><span class="sxs-lookup"><span data-stu-id="d45df-109">nodeID</span></span></p></td>
<td><p><span data-ttu-id="d45df-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="d45df-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="d45df-111">ID do Nó (número único).</span><span class="sxs-lookup"><span data-stu-id="d45df-111">Node ID (unique number).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d45df-112">nodeGuid</span><span class="sxs-lookup"><span data-stu-id="d45df-112">nodeGuid</span></span></p></td>
<td><p><span data-ttu-id="d45df-113">GUID, não nulo</span><span class="sxs-lookup"><span data-stu-id="d45df-113">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="d45df-114">GUIDO do Nó.</span><span class="sxs-lookup"><span data-stu-id="d45df-114">Node GUID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d45df-115">parentID</span><span class="sxs-lookup"><span data-stu-id="d45df-115">parentID</span></span></p></td>
<td><p><span data-ttu-id="d45df-116">int</span><span class="sxs-lookup"><span data-stu-id="d45df-116">int</span></span></p></td>
<td><p><span data-ttu-id="d45df-p101">ID do nó do pai. O nó raiz (com ID 1) inclui si mesmo como pai também.</span><span class="sxs-lookup"><span data-stu-id="d45df-p101">Node ID of parent. The root node (with ID 1) includes itself as parent as well.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d45df-119">nodeType</span><span class="sxs-lookup"><span data-stu-id="d45df-119">nodeType</span></span></p></td>
<td><p><span data-ttu-id="d45df-120">bit, não vazio</span><span class="sxs-lookup"><span data-stu-id="d45df-120">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="d45df-121">Verdadeiro se o nó for uma categoria.</span><span class="sxs-lookup"><span data-stu-id="d45df-121">True if the node is a category.</span></span></p>
<p><span data-ttu-id="d45df-122">Falso se o nó for uma sala de chat.</span><span class="sxs-lookup"><span data-stu-id="d45df-122">False if the node is a chat room.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d45df-123">Nome</span><span class="sxs-lookup"><span data-stu-id="d45df-123">nodeName</span></span></p></td>
<td><p><span data-ttu-id="d45df-124">não nulo nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="d45df-124">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="d45df-125">Nome do nó.</span><span class="sxs-lookup"><span data-stu-id="d45df-125">Node name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d45df-126">nodeDesc</span><span class="sxs-lookup"><span data-stu-id="d45df-126">nodeDesc</span></span></p></td>
<td><p><span data-ttu-id="d45df-127">nvarchar (256), não nulo</span><span class="sxs-lookup"><span data-stu-id="d45df-127">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="d45df-128">Descrição do nó.</span><span class="sxs-lookup"><span data-stu-id="d45df-128">Node description.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d45df-129">invite</span><span class="sxs-lookup"><span data-stu-id="d45df-129">invite</span></span></p></td>
<td><p><span data-ttu-id="d45df-130">bits</span><span class="sxs-lookup"><span data-stu-id="d45df-130">bit</span></span></p></td>
<td><p><span data-ttu-id="d45df-131">Para categorias:</span><span class="sxs-lookup"><span data-stu-id="d45df-131">For categories:</span></span></p>
<ul>
<li><p><span data-ttu-id="d45df-132">Verdadeiro se convites estiverem ativados.</span><span class="sxs-lookup"><span data-stu-id="d45df-132">True if invites are on.</span></span></p></li>
<li><p><span data-ttu-id="d45df-133">Falso se convites estiverem desativados.</span><span class="sxs-lookup"><span data-stu-id="d45df-133">False if invites are off.</span></span></p></li>
</ul>
<p><span data-ttu-id="d45df-134">Para salas:</span><span class="sxs-lookup"><span data-stu-id="d45df-134">For rooms:</span></span></p>
<ul>
<li><p><span data-ttu-id="d45df-135">Falso se convites estiverem desativados (substitui a categoria pai).</span><span class="sxs-lookup"><span data-stu-id="d45df-135">False if invites are off (overrides the parent category).</span></span></p></li>
<li><p><span data-ttu-id="d45df-136">Nulo se a configuração de convites for herdada da categoria pai.</span><span class="sxs-lookup"><span data-stu-id="d45df-136">Null if the invites setting is inherited from the parent category.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d45df-137">login</span><span class="sxs-lookup"><span data-stu-id="d45df-137">logged</span></span></p></td>
<td><p><span data-ttu-id="d45df-138">bits</span><span class="sxs-lookup"><span data-stu-id="d45df-138">bit</span></span></p></td>
<td><p><span data-ttu-id="d45df-139">Para categorias:</span><span class="sxs-lookup"><span data-stu-id="d45df-139">For categories:</span></span></p>
<ul>
<li><p><span data-ttu-id="d45df-140">Verdadeiro se o histórico de chat estiver ativado.</span><span class="sxs-lookup"><span data-stu-id="d45df-140">True if chat history is on.</span></span></p></li>
<li><p><span data-ttu-id="d45df-141">Falso se o histórico de chat estiver desativado.</span><span class="sxs-lookup"><span data-stu-id="d45df-141">False if chat history is off.</span></span></p></li>
</ul>
<p><span data-ttu-id="d45df-142">Para salas:</span><span class="sxs-lookup"><span data-stu-id="d45df-142">For rooms:</span></span></p>
<ul>
<li><p><span data-ttu-id="d45df-143">Vazio.</span><span class="sxs-lookup"><span data-stu-id="d45df-143">Null.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d45df-144">FilePost</span><span class="sxs-lookup"><span data-stu-id="d45df-144">filePost</span></span></p></td>
<td><p><span data-ttu-id="d45df-145">bits</span><span class="sxs-lookup"><span data-stu-id="d45df-145">bit</span></span></p></td>
<td><p><span data-ttu-id="d45df-146">Para categorias:</span><span class="sxs-lookup"><span data-stu-id="d45df-146">For categories:</span></span></p>
<ul>
<li><p><span data-ttu-id="d45df-147">Verdadeiro se o carregamento de arquivos for permitido.</span><span class="sxs-lookup"><span data-stu-id="d45df-147">True if file uploads are allowed.</span></span></p></li>
<li><p><span data-ttu-id="d45df-148">Falso se o carregamento de arquivos não for permitido.</span><span class="sxs-lookup"><span data-stu-id="d45df-148">False if file uploads are disallowed.</span></span></p></li>
</ul>
<p><span data-ttu-id="d45df-149">Para salas:</span><span class="sxs-lookup"><span data-stu-id="d45df-149">For rooms:</span></span></p>
<ul>
<li><p><span data-ttu-id="d45df-150">Vazio.</span><span class="sxs-lookup"><span data-stu-id="d45df-150">Null.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d45df-151">deficiência</span><span class="sxs-lookup"><span data-stu-id="d45df-151">disabled</span></span></p></td>
<td><p><span data-ttu-id="d45df-152">bit, não nulo</span><span class="sxs-lookup"><span data-stu-id="d45df-152">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="d45df-p102">Verdadeiros se a sala de chat estiver desabilitada. Aplica-se somente a salas de chat (falso para categorias).</span><span class="sxs-lookup"><span data-stu-id="d45df-p102">True if the chat room is disabled. Applies only to chat rooms. (False for categories.)</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d45df-156">comportamental</span><span class="sxs-lookup"><span data-stu-id="d45df-156">behavior</span></span></p></td>
<td><p><span data-ttu-id="d45df-157">smallint, not null</span><span class="sxs-lookup"><span data-stu-id="d45df-157">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="d45df-158">Comportamento (consultado na tabela EnumValue):</span><span class="sxs-lookup"><span data-stu-id="d45df-158">Behavior (looked up in EnumValue table):</span></span></p>
<ul>
<li><p><span data-ttu-id="d45df-159">4: Normal (salas de chat normais).</span><span class="sxs-lookup"><span data-stu-id="d45df-159">4: Normal (normal chat rooms).</span></span></p></li>
<li><p><span data-ttu-id="d45df-160">5: Auditório (salas de chat de auditório, somente apresentadores podem contribuir).</span><span class="sxs-lookup"><span data-stu-id="d45df-160">5: Auditorium (auditorium chat rooms, only presenters can contribute).</span></span></p></li>
</ul>
<p><span data-ttu-id="d45df-161">Aplica-se somente a salas de chat</span><span class="sxs-lookup"><span data-stu-id="d45df-161">Applies only to chat rooms.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d45df-162">visibility</span><span class="sxs-lookup"><span data-stu-id="d45df-162">visibility</span></span></p></td>
<td><p><span data-ttu-id="d45df-163">smallint, não nulo</span><span class="sxs-lookup"><span data-stu-id="d45df-163">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="d45df-164">Visibilidade (consultado na tabela EnumValue):</span><span class="sxs-lookup"><span data-stu-id="d45df-164">Visibility (looked up on EnumValue table):</span></span></p>
<ul>
<li><p><span data-ttu-id="d45df-165">2: Particular</span><span class="sxs-lookup"><span data-stu-id="d45df-165">2: Private</span></span></p></li>
<li><p><span data-ttu-id="d45df-166">3: Com escopo</span><span class="sxs-lookup"><span data-stu-id="d45df-166">3: Scoped</span></span></p></li>
<li><p><span data-ttu-id="d45df-167">6: Abrir</span><span class="sxs-lookup"><span data-stu-id="d45df-167">6: Open</span></span></p></li>
</ul>
<p><span data-ttu-id="d45df-168">Aplica-se somente a salas de chat</span><span class="sxs-lookup"><span data-stu-id="d45df-168">Applies only to chat rooms.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d45df-169">siopID</span><span class="sxs-lookup"><span data-stu-id="d45df-169">siopID</span></span></p></td>
<td><p><span data-ttu-id="d45df-170">GUID</span><span class="sxs-lookup"><span data-stu-id="d45df-170">GUID</span></span></p></td>
<td><p><span data-ttu-id="d45df-p103">O GUID de um suplemento é associado a esta sala de chat (categorias não possuem suplementos).</span><span class="sxs-lookup"><span data-stu-id="d45df-p103">Add-In GUID if an add-in is associated with this chat room. (Categories do not have add-ins.)</span></span></p>
<p><span data-ttu-id="d45df-173">As informações do suplemento são consultadas na tabela SiopWhiteList.</span><span class="sxs-lookup"><span data-stu-id="d45df-173">The add-in information is looked up in SiopWhiteList table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d45df-174">nodeAddedBy</span><span class="sxs-lookup"><span data-stu-id="d45df-174">nodeAddedBy</span></span></p></td>
<td><p><span data-ttu-id="d45df-175">int, not null</span><span class="sxs-lookup"><span data-stu-id="d45df-175">int, not null</span></span></p></td>
<td><p><span data-ttu-id="d45df-176">ID da entidade de segurança que criou este nó.</span><span class="sxs-lookup"><span data-stu-id="d45df-176">ID of the principal that created this node.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d45df-177">nodeAddedOn</span><span class="sxs-lookup"><span data-stu-id="d45df-177">nodeAddedOn</span></span></p></td>
<td><p><span data-ttu-id="d45df-178">bigint, não nulo</span><span class="sxs-lookup"><span data-stu-id="d45df-178">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="d45df-179">Carimbo de data/hora da criação do nó.</span><span class="sxs-lookup"><span data-stu-id="d45df-179">Time stamp of the node creation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d45df-180">nodeUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="d45df-180">nodeUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="d45df-181">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="d45df-181">int, not null</span></span></p></td>
<td><p><span data-ttu-id="d45df-182">ID da entidade de segurança que efetuou a atualização mais recente deste nó.</span><span class="sxs-lookup"><span data-stu-id="d45df-182">ID of the principal that did the latest update of this node.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d45df-183">nodeUpdatedOn</span><span class="sxs-lookup"><span data-stu-id="d45df-183">nodeUpdatedOn</span></span></p></td>
<td><p><span data-ttu-id="d45df-184">bigint, não nulo</span><span class="sxs-lookup"><span data-stu-id="d45df-184">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="d45df-185">Carimbo de data/hora da última atualização deste nó.</span><span class="sxs-lookup"><span data-stu-id="d45df-185">Time stamp of the latest update of this node.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d45df-186">purgedOn</span><span class="sxs-lookup"><span data-stu-id="d45df-186">purgedOn</span></span></p></td>
<td><p><span data-ttu-id="d45df-187">datetime</span><span class="sxs-lookup"><span data-stu-id="d45df-187">datetime</span></span></p></td>
<td><p><span data-ttu-id="d45df-p104">Horário da última operação de limpeza (remoção de escopos da tabela tblScopedPrincipal e funções da tabela tblPrincipalRole) que afetou este nó. Usado pelo mecanismo de atualização do cache interno do serviço de chat.</span><span class="sxs-lookup"><span data-stu-id="d45df-p104">Time of the latest purge operation (removal of scopes from tblScopedPrincipal table and roles from tblPrincipalRole table) that affected this node. This is used by the Chat service’s internal cache update mechanism.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="d45df-190">Chaves</span><span class="sxs-lookup"><span data-stu-id="d45df-190">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d45df-191">Coluna</span><span class="sxs-lookup"><span data-stu-id="d45df-191">Column</span></span></th>
<th><span data-ttu-id="d45df-192">Descrição</span><span class="sxs-lookup"><span data-stu-id="d45df-192">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d45df-193">nodeID</span><span class="sxs-lookup"><span data-stu-id="d45df-193">nodeID</span></span></p></td>
<td><p><span data-ttu-id="d45df-194">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="d45df-194">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d45df-195">comportamental</span><span class="sxs-lookup"><span data-stu-id="d45df-195">behavior</span></span></p></td>
<td><p><span data-ttu-id="d45df-196">Chave estrangeira com consulta na tabela tblEnumValue.valueID.</span><span class="sxs-lookup"><span data-stu-id="d45df-196">Foreign key with lookup in tblEnumValue.valueID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d45df-197">visibility</span><span class="sxs-lookup"><span data-stu-id="d45df-197">visibility</span></span></p></td>
<td><p><span data-ttu-id="d45df-198">Chave estrangeira com consulta na tabela tblEnumValue.valueID.</span><span class="sxs-lookup"><span data-stu-id="d45df-198">Foreign key with lookup in tblEnumValue.valueID table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d45df-199">parentID</span><span class="sxs-lookup"><span data-stu-id="d45df-199">parentID</span></span></p></td>
<td><p><span data-ttu-id="d45df-200">Chave estrangeira com pesquisa na tabela tblNode.nodeID.</span><span class="sxs-lookup"><span data-stu-id="d45df-200">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d45df-201">siopID</span><span class="sxs-lookup"><span data-stu-id="d45df-201">siopID</span></span></p></td>
<td><p><span data-ttu-id="d45df-202">Chave estrangeira com consulta na tabela tblSiopWhiteList.siopId.</span><span class="sxs-lookup"><span data-stu-id="d45df-202">Foreign key with lookup in tblSiopWhiteList.siopId table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

