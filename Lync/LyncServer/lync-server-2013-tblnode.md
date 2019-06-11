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

# <a name="tblnode-in-lync-server-2013"></a>tblNode no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-12_

tblNode contém a árvore de objetos (com os nós da categoria ou da sala de chat), conforme gerenciado no painel de controle e cmdlets administrativos do Lync Server 2013.

### <a name="columns"></a>Colunas

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Coluna</th>
<th>Tipo</th>
<th>Descrição</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>NodeId</p></td>
<td><p>int, não nulo</p></td>
<td><p>ID do nó (número exclusivo).</p></td>
</tr>
<tr class="even">
<td><p>nodeGuid</p></td>
<td><p>GUID, não nulo</p></td>
<td><p>GUID do nó.</p></td>
</tr>
<tr class="odd">
<td><p>parentID</p></td>
<td><p>int</p></td>
<td><p>ID do nó do pai. O nó raiz (com ID 1) também inclui o próprio pai.</p></td>
</tr>
<tr class="even">
<td><p>nodeType</p></td>
<td><p>bit, e não nulo</p></td>
<td><p>Verdadeiro se o nó for uma categoria.</p>
<p>Falso se o nó for uma sala de chat.</p></td>
</tr>
<tr class="odd">
<td><p>Node</p></td>
<td><p>nvarchar (256), NOT NULL</p></td>
<td><p>Nome do nó.</p></td>
</tr>
<tr class="even">
<td><p>nodeDesc</p></td>
<td><p>nvarchar (256), NOT NULL</p></td>
<td><p>Descrição do nó.</p></td>
</tr>
<tr class="odd">
<td><p>Eles</p></td>
<td><p>bit</p></td>
<td><p>Para categorias:</p>
<ul>
<li><p>Verdadeiro se os convites estiverem em.</p></li>
<li><p>Falso se os convites estiverem desativados.</p></li>
</ul>
<p>Para salas:</p>
<ul>
<li><p>Falso se os convites estiverem desativados (Substitui a categoria pai).</p></li>
<li><p>Nulo se a configuração convites for herdada da categoria pai.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>realizou</p></td>
<td><p>bit</p></td>
<td><p>Para categorias:</p>
<ul>
<li><p>Verdadeiro se o histórico de chats estiver ativado.</p></li>
<li><p>Falso se o histórico de chats estiver desativado.</p></li>
</ul>
<p>Para salas:</p>
<ul>
<li><p>Vazio.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Postagem de mensagem</p></td>
<td><p>bit</p></td>
<td><p>Para categorias:</p>
<ul>
<li><p>Verdadeiro se os carregamentos de arquivo forem permitidos.</p></li>
<li><p>Falso se os carregamentos de arquivos não forem permitidos.</p></li>
</ul>
<p>Para salas:</p>
<ul>
<li><p>Vazio.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>ativo</p></td>
<td><p>bit, e não nulo</p></td>
<td><p>Verdadeiro se a sala de chat estiver desabilitada. Aplica-se somente a salas de chat. (Falso para categorias.)</p></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p>funcionamento</p></td>
<td><p>smallint, não nulo</p></td>
<td><p>Comportamento (pesquisado na tabela EnumValue):</p>
<ul>
<li><p>4: normal (salas de chat normal).</p></li>
<li><p>5: Auditorium (salas de chat Auditorium, somente os apresentadores podem contribuir).</p></li>
</ul>
<p>Aplica-se somente a salas de chat.</p></td>
</tr>
<tr class="odd">
<td><p>visibilidade</p></td>
<td><p>smallint, não nulo</p></td>
<td><p>Visibilidade (pesquisada na tabela de EnumValue):</p>
<ul>
<li><p>2: particular</p></li>
<li><p>3: com escopo</p></li>
<li><p>6: abrir</p></li>
</ul>
<p>Aplica-se somente a salas de chat.</p></td>
</tr>
<tr class="even">
<td><p>siopID</p></td>
<td><p>GUID</p></td>
<td><p>GUID do suplemento se um suplemento estiver associado a esta sala de chat. (As categorias não têm suplementos.)</p>
<p>As informações do suplemento são pesquisadas na tabela SiopWhiteList.</p></td>
</tr>
<tr class="odd">
<td><p>nodeAddedBy</p></td>
<td><p>int, não nulo</p></td>
<td><p>ID da entidade de segurança que criou esse nó.</p></td>
</tr>
<tr class="even">
<td><p>nodeAddedOn</p></td>
<td><p>bigint, e não nulo</p></td>
<td><p>Carimbo de data/hora da criação de nós.</p></td>
</tr>
<tr class="odd">
<td><p>nodeUpdatedBy</p></td>
<td><p>int, não nulo</p></td>
<td><p>ID da entidade de segurança que fez a atualização mais recente deste nó.</p></td>
</tr>
<tr class="even">
<td><p>nodeUpdatedOn</p></td>
<td><p>bigint, e não nulo</p></td>
<td><p>Carimbo de data/hora da atualização mais recente deste nó.</p></td>
</tr>
<tr class="odd">
<td><p>purgedOn</p></td>
<td><p>datetime</p></td>
<td><p>Hora da última operação de limpeza (remoção de escopos da tabela tblScopedPrincipal e funções da tabela tblPrincipalRole) que afetou esse nó. Isso é usado pelo mecanismo de atualização do cache interno do serviço de chat.</p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a>As

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Coluna</th>
<th>Descrição</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>NodeId</p></td>
<td><p>Chave primária.</p></td>
</tr>
<tr class="even">
<td><p>funcionamento</p></td>
<td><p>Chave estrangeira com Lookup na tabela tblEnumValue. valueid.</p></td>
</tr>
<tr class="odd">
<td><p>visibilidade</p></td>
<td><p>Chave estrangeira com Lookup na tabela tblEnumValue. valueid.</p></td>
</tr>
<tr class="even">
<td><p>parentID</p></td>
<td><p>Chave estrangeira com Lookup na tabela tblNode. NodeId.</p></td>
</tr>
<tr class="odd">
<td><p>siopID</p></td>
<td><p>Chave estrangeira com Lookup na tabela tblSiopWhiteList. siopId.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

