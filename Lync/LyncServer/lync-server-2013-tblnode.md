---
title: 'Lync Server 2013: tblNode'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblNode
ms:assetid: a31d2961-aa83-4286-a12e-15d279c95f19
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615024(v=OCS.15)
ms:contentKeyID: 48184960
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 84bf7cf57f9890093a56deb2e0769b82e92aa0ea
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844789"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblnode-in-lync-server-2013"></a><span data-ttu-id="330ef-102">tblNode no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="330ef-102">tblNode in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="330ef-103">_**Tópico da última modificação:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="330ef-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="330ef-104">tblNode contém a árvore de objetos (com os nós da categoria ou da sala de chat), conforme gerenciado no painel de controle e cmdlets administrativos do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="330ef-104">tblNode contains the object tree (with category or chat room nodes) as managed in the Lync Server 2013 Control Panel and administrative cmdlets.</span></span>

### <a name="columns"></a><span data-ttu-id="330ef-105">Colunas</span><span class="sxs-lookup"><span data-stu-id="330ef-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="330ef-106">Coluna</span><span class="sxs-lookup"><span data-stu-id="330ef-106">Column</span></span></th>
<th><span data-ttu-id="330ef-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="330ef-107">Type</span></span></th>
<th><span data-ttu-id="330ef-108">Descrição</span><span class="sxs-lookup"><span data-stu-id="330ef-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="330ef-109">NodeId</span><span class="sxs-lookup"><span data-stu-id="330ef-109">nodeID</span></span></p></td>
<td><p><span data-ttu-id="330ef-110">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="330ef-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="330ef-111">ID do nó (número exclusivo).</span><span class="sxs-lookup"><span data-stu-id="330ef-111">Node ID (unique number).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="330ef-112">nodeGuid</span><span class="sxs-lookup"><span data-stu-id="330ef-112">nodeGuid</span></span></p></td>
<td><p><span data-ttu-id="330ef-113">GUID, não nulo</span><span class="sxs-lookup"><span data-stu-id="330ef-113">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="330ef-114">GUID do nó.</span><span class="sxs-lookup"><span data-stu-id="330ef-114">Node GUID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="330ef-115">parentID</span><span class="sxs-lookup"><span data-stu-id="330ef-115">parentID</span></span></p></td>
<td><p><span data-ttu-id="330ef-116">int</span><span class="sxs-lookup"><span data-stu-id="330ef-116">int</span></span></p></td>
<td><p><span data-ttu-id="330ef-117">ID do nó do pai.</span><span class="sxs-lookup"><span data-stu-id="330ef-117">Node ID of parent.</span></span> <span data-ttu-id="330ef-118">O nó raiz (com ID 1) também inclui o próprio pai.</span><span class="sxs-lookup"><span data-stu-id="330ef-118">The root node (with ID 1) includes itself as parent as well.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="330ef-119">nodeType</span><span class="sxs-lookup"><span data-stu-id="330ef-119">nodeType</span></span></p></td>
<td><p><span data-ttu-id="330ef-120">bit, e não nulo</span><span class="sxs-lookup"><span data-stu-id="330ef-120">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="330ef-121">Verdadeiro se o nó for uma categoria.</span><span class="sxs-lookup"><span data-stu-id="330ef-121">True if the node is a category.</span></span></p>
<p><span data-ttu-id="330ef-122">Falso se o nó for uma sala de chat.</span><span class="sxs-lookup"><span data-stu-id="330ef-122">False if the node is a chat room.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="330ef-123">Node</span><span class="sxs-lookup"><span data-stu-id="330ef-123">nodeName</span></span></p></td>
<td><p><span data-ttu-id="330ef-124">nvarchar (256), NOT NULL</span><span class="sxs-lookup"><span data-stu-id="330ef-124">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="330ef-125">Nome do nó.</span><span class="sxs-lookup"><span data-stu-id="330ef-125">Node name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="330ef-126">nodeDesc</span><span class="sxs-lookup"><span data-stu-id="330ef-126">nodeDesc</span></span></p></td>
<td><p><span data-ttu-id="330ef-127">nvarchar (256), NOT NULL</span><span class="sxs-lookup"><span data-stu-id="330ef-127">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="330ef-128">Descrição do nó.</span><span class="sxs-lookup"><span data-stu-id="330ef-128">Node description.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="330ef-129">Eles</span><span class="sxs-lookup"><span data-stu-id="330ef-129">invite</span></span></p></td>
<td><p><span data-ttu-id="330ef-130">bit</span><span class="sxs-lookup"><span data-stu-id="330ef-130">bit</span></span></p></td>
<td><p><span data-ttu-id="330ef-131">Para categorias:</span><span class="sxs-lookup"><span data-stu-id="330ef-131">For categories:</span></span></p>
<ul>
<li><p><span data-ttu-id="330ef-132">Verdadeiro se os convites estiverem em.</span><span class="sxs-lookup"><span data-stu-id="330ef-132">True if invites are on.</span></span></p></li>
<li><p><span data-ttu-id="330ef-133">Falso se os convites estiverem desativados.</span><span class="sxs-lookup"><span data-stu-id="330ef-133">False if invites are off.</span></span></p></li>
</ul>
<p><span data-ttu-id="330ef-134">Para salas:</span><span class="sxs-lookup"><span data-stu-id="330ef-134">For rooms:</span></span></p>
<ul>
<li><p><span data-ttu-id="330ef-135">Falso se os convites estiverem desativados (Substitui a categoria pai).</span><span class="sxs-lookup"><span data-stu-id="330ef-135">False if invites are off (overrides the parent category).</span></span></p></li>
<li><p><span data-ttu-id="330ef-136">Nulo se a configuração convites for herdada da categoria pai.</span><span class="sxs-lookup"><span data-stu-id="330ef-136">Null if the invites setting is inherited from the parent category.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="330ef-137">realizou</span><span class="sxs-lookup"><span data-stu-id="330ef-137">logged</span></span></p></td>
<td><p><span data-ttu-id="330ef-138">bit</span><span class="sxs-lookup"><span data-stu-id="330ef-138">bit</span></span></p></td>
<td><p><span data-ttu-id="330ef-139">Para categorias:</span><span class="sxs-lookup"><span data-stu-id="330ef-139">For categories:</span></span></p>
<ul>
<li><p><span data-ttu-id="330ef-140">Verdadeiro se o histórico de chats estiver ativado.</span><span class="sxs-lookup"><span data-stu-id="330ef-140">True if chat history is on.</span></span></p></li>
<li><p><span data-ttu-id="330ef-141">Falso se o histórico de chats estiver desativado.</span><span class="sxs-lookup"><span data-stu-id="330ef-141">False if chat history is off.</span></span></p></li>
</ul>
<p><span data-ttu-id="330ef-142">Para salas:</span><span class="sxs-lookup"><span data-stu-id="330ef-142">For rooms:</span></span></p>
<ul>
<li><p><span data-ttu-id="330ef-143">Vazio.</span><span class="sxs-lookup"><span data-stu-id="330ef-143">Null.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="330ef-144">Postagem de mensagem</span><span class="sxs-lookup"><span data-stu-id="330ef-144">filePost</span></span></p></td>
<td><p><span data-ttu-id="330ef-145">bit</span><span class="sxs-lookup"><span data-stu-id="330ef-145">bit</span></span></p></td>
<td><p><span data-ttu-id="330ef-146">Para categorias:</span><span class="sxs-lookup"><span data-stu-id="330ef-146">For categories:</span></span></p>
<ul>
<li><p><span data-ttu-id="330ef-147">Verdadeiro se os carregamentos de arquivo forem permitidos.</span><span class="sxs-lookup"><span data-stu-id="330ef-147">True if file uploads are allowed.</span></span></p></li>
<li><p><span data-ttu-id="330ef-148">Falso se os carregamentos de arquivos não forem permitidos.</span><span class="sxs-lookup"><span data-stu-id="330ef-148">False if file uploads are disallowed.</span></span></p></li>
</ul>
<p><span data-ttu-id="330ef-149">Para salas:</span><span class="sxs-lookup"><span data-stu-id="330ef-149">For rooms:</span></span></p>
<ul>
<li><p><span data-ttu-id="330ef-150">Vazio.</span><span class="sxs-lookup"><span data-stu-id="330ef-150">Null.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="330ef-151">ativo</span><span class="sxs-lookup"><span data-stu-id="330ef-151">disabled</span></span></p></td>
<td><p><span data-ttu-id="330ef-152">bit, e não nulo</span><span class="sxs-lookup"><span data-stu-id="330ef-152">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="330ef-153">Verdadeiro se a sala de chat estiver desabilitada.</span><span class="sxs-lookup"><span data-stu-id="330ef-153">True if the chat room is disabled.</span></span> <span data-ttu-id="330ef-154">Aplica-se somente a salas de chat.</span><span class="sxs-lookup"><span data-stu-id="330ef-154">Applies only to chat rooms.</span></span> <span data-ttu-id="330ef-155">(Falso para categorias.)</span><span class="sxs-lookup"><span data-stu-id="330ef-155">(False for categories.)</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="330ef-156">funcionamento</span><span class="sxs-lookup"><span data-stu-id="330ef-156">behavior</span></span></p></td>
<td><p><span data-ttu-id="330ef-157">smallint, não nulo</span><span class="sxs-lookup"><span data-stu-id="330ef-157">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="330ef-158">Comportamento (pesquisado na tabela EnumValue):</span><span class="sxs-lookup"><span data-stu-id="330ef-158">Behavior (looked up in EnumValue table):</span></span></p>
<ul>
<li><p><span data-ttu-id="330ef-159">4: normal (salas de chat normal).</span><span class="sxs-lookup"><span data-stu-id="330ef-159">4: Normal (normal chat rooms).</span></span></p></li>
<li><p><span data-ttu-id="330ef-160">5: Auditorium (salas de chat Auditorium, somente os apresentadores podem contribuir).</span><span class="sxs-lookup"><span data-stu-id="330ef-160">5: Auditorium (auditorium chat rooms, only presenters can contribute).</span></span></p></li>
</ul>
<p><span data-ttu-id="330ef-161">Aplica-se somente a salas de chat.</span><span class="sxs-lookup"><span data-stu-id="330ef-161">Applies only to chat rooms.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="330ef-162">visibilidade</span><span class="sxs-lookup"><span data-stu-id="330ef-162">visibility</span></span></p></td>
<td><p><span data-ttu-id="330ef-163">smallint, não nulo</span><span class="sxs-lookup"><span data-stu-id="330ef-163">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="330ef-164">Visibilidade (pesquisada na tabela de EnumValue):</span><span class="sxs-lookup"><span data-stu-id="330ef-164">Visibility (looked up on EnumValue table):</span></span></p>
<ul>
<li><p><span data-ttu-id="330ef-165">2: particular</span><span class="sxs-lookup"><span data-stu-id="330ef-165">2: Private</span></span></p></li>
<li><p><span data-ttu-id="330ef-166">3: com escopo</span><span class="sxs-lookup"><span data-stu-id="330ef-166">3: Scoped</span></span></p></li>
<li><p><span data-ttu-id="330ef-167">6: abrir</span><span class="sxs-lookup"><span data-stu-id="330ef-167">6: Open</span></span></p></li>
</ul>
<p><span data-ttu-id="330ef-168">Aplica-se somente a salas de chat.</span><span class="sxs-lookup"><span data-stu-id="330ef-168">Applies only to chat rooms.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="330ef-169">siopID</span><span class="sxs-lookup"><span data-stu-id="330ef-169">siopID</span></span></p></td>
<td><p><span data-ttu-id="330ef-170">GUID</span><span class="sxs-lookup"><span data-stu-id="330ef-170">GUID</span></span></p></td>
<td><p><span data-ttu-id="330ef-171">GUID do suplemento se um suplemento estiver associado a esta sala de chat.</span><span class="sxs-lookup"><span data-stu-id="330ef-171">Add-In GUID if an add-in is associated with this chat room.</span></span> <span data-ttu-id="330ef-172">(As categorias não têm suplementos.)</span><span class="sxs-lookup"><span data-stu-id="330ef-172">(Categories do not have add-ins.)</span></span></p>
<p><span data-ttu-id="330ef-173">As informações do suplemento são pesquisadas na tabela SiopWhiteList.</span><span class="sxs-lookup"><span data-stu-id="330ef-173">The add-in information is looked up in SiopWhiteList table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="330ef-174">nodeAddedBy</span><span class="sxs-lookup"><span data-stu-id="330ef-174">nodeAddedBy</span></span></p></td>
<td><p><span data-ttu-id="330ef-175">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="330ef-175">int, not null</span></span></p></td>
<td><p><span data-ttu-id="330ef-176">ID da entidade de segurança que criou esse nó.</span><span class="sxs-lookup"><span data-stu-id="330ef-176">ID of the principal that created this node.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="330ef-177">nodeAddedOn</span><span class="sxs-lookup"><span data-stu-id="330ef-177">nodeAddedOn</span></span></p></td>
<td><p><span data-ttu-id="330ef-178">bigint, e não nulo</span><span class="sxs-lookup"><span data-stu-id="330ef-178">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="330ef-179">Carimbo de data/hora da criação de nós.</span><span class="sxs-lookup"><span data-stu-id="330ef-179">Time stamp of the node creation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="330ef-180">nodeUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="330ef-180">nodeUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="330ef-181">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="330ef-181">int, not null</span></span></p></td>
<td><p><span data-ttu-id="330ef-182">ID da entidade de segurança que fez a atualização mais recente deste nó.</span><span class="sxs-lookup"><span data-stu-id="330ef-182">ID of the principal that did the latest update of this node.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="330ef-183">nodeUpdatedOn</span><span class="sxs-lookup"><span data-stu-id="330ef-183">nodeUpdatedOn</span></span></p></td>
<td><p><span data-ttu-id="330ef-184">bigint, e não nulo</span><span class="sxs-lookup"><span data-stu-id="330ef-184">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="330ef-185">Carimbo de data/hora da atualização mais recente deste nó.</span><span class="sxs-lookup"><span data-stu-id="330ef-185">Time stamp of the latest update of this node.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="330ef-186">purgedOn</span><span class="sxs-lookup"><span data-stu-id="330ef-186">purgedOn</span></span></p></td>
<td><p><span data-ttu-id="330ef-187">datetime</span><span class="sxs-lookup"><span data-stu-id="330ef-187">datetime</span></span></p></td>
<td><p><span data-ttu-id="330ef-188">Hora da última operação de limpeza (remoção de escopos da tabela tblScopedPrincipal e funções da tabela tblPrincipalRole) que afetou esse nó.</span><span class="sxs-lookup"><span data-stu-id="330ef-188">Time of the latest purge operation (removal of scopes from tblScopedPrincipal table and roles from tblPrincipalRole table) that affected this node.</span></span> <span data-ttu-id="330ef-189">Isso é usado pelo mecanismo de atualização do cache interno do serviço de chat.</span><span class="sxs-lookup"><span data-stu-id="330ef-189">This is used by the Chat service’s internal cache update mechanism.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="330ef-190">As</span><span class="sxs-lookup"><span data-stu-id="330ef-190">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="330ef-191">Coluna</span><span class="sxs-lookup"><span data-stu-id="330ef-191">Column</span></span></th>
<th><span data-ttu-id="330ef-192">Descrição</span><span class="sxs-lookup"><span data-stu-id="330ef-192">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="330ef-193">NodeId</span><span class="sxs-lookup"><span data-stu-id="330ef-193">nodeID</span></span></p></td>
<td><p><span data-ttu-id="330ef-194">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="330ef-194">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="330ef-195">funcionamento</span><span class="sxs-lookup"><span data-stu-id="330ef-195">behavior</span></span></p></td>
<td><p><span data-ttu-id="330ef-196">Chave estrangeira com Lookup na tabela tblEnumValue. valueid.</span><span class="sxs-lookup"><span data-stu-id="330ef-196">Foreign key with lookup in tblEnumValue.valueID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="330ef-197">visibilidade</span><span class="sxs-lookup"><span data-stu-id="330ef-197">visibility</span></span></p></td>
<td><p><span data-ttu-id="330ef-198">Chave estrangeira com Lookup na tabela tblEnumValue. valueid.</span><span class="sxs-lookup"><span data-stu-id="330ef-198">Foreign key with lookup in tblEnumValue.valueID table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="330ef-199">parentID</span><span class="sxs-lookup"><span data-stu-id="330ef-199">parentID</span></span></p></td>
<td><p><span data-ttu-id="330ef-200">Chave estrangeira com Lookup na tabela tblNode. NodeId.</span><span class="sxs-lookup"><span data-stu-id="330ef-200">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="330ef-201">siopID</span><span class="sxs-lookup"><span data-stu-id="330ef-201">siopID</span></span></p></td>
<td><p><span data-ttu-id="330ef-202">Chave estrangeira com Lookup na tabela tblSiopWhiteList. siopId.</span><span class="sxs-lookup"><span data-stu-id="330ef-202">Foreign key with lookup in tblSiopWhiteList.siopId table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

