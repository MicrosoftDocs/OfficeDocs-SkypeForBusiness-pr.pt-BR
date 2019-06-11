---
title: 'Lync Server 2013: Tabela SessionDetails'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: SessionDetails table
ms:assetid: 783d2508-e31f-4b54-be0c-63aa5ec21c04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398589(v=OCS.15)
ms:contentKeyID: 48184559
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: faebef9ad03370c2fa969d3b119f13b88d1d3173
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822108"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sessiondetails-table-in-lync-server-2013"></a>Tabela SessionDetails no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-28_

Cada registro representa uma sessão ponto a ponto, que pode ser uma chamada telefônica VoIP-VoIP, uma sessão de IM de duas partes ou outro tipo de sessão. Você pode executar uma junção de tabela com a [tabela de mídia no Lync Server 2013](lync-server-2013-media-table.md) para encontrar os detalhes de cada mídia envolvida nesta sessão.

Observe que os campos IsUser1IntegratedWithDeskPhone e IsUser2IntegratedWithDeskPhone foram descartados da tabela SessionDetails usada no Microsoft Lync Server 2013.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Coluna</th>
<th>Tipo de dados</th>
<th>Chave/índice</th>
<th>Detalhes</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Id_da_sessãotime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Primário, estrangeiro</p></td>
<td><p>Tempo de solicitação de sessão. Usado em conjunto com o <strong>SessionIdSeq</strong> para identificar exclusivamente uma sessão. Consulte a <a href="lync-server-2013-dialogs-table.md">tabela de diálogos no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Primário, estrangeiro</p></td>
<td><p>Número de identificação para identificar a sessão. Usado em conjunto com <strong></strong> a identificação_da_sessãotime para identificar exclusivamente uma sessão. * consulte a <a href="lync-server-2013-dialogs-table.md">tabela de caixas de diálogo no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CorrelationId</strong></p></td>
<td><p>identificador</p></td>
<td></td>
<td><p>Um GUID para correlacionar várias sessões.</p></td>
</tr>
<tr class="even">
<td><p><strong>ReplaceDialogIdTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Exterior</p></td>
<td><p>Número de identificação para identificar a caixa de diálogo que foi substituída pela sessão atual. Consulte a <a href="lync-server-2013-dialogs-table.md">tabela de diálogos no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ReplaceDialogIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Exterior</p></td>
<td><p>Número de identificação para identificar a sessão. Usado em conjunto com <strong>ReplacesDialogIdTime</strong> para identificar exclusivamente uma sessão substituída por esta sessão. Consulte a <a href="lync-server-2013-dialogs-table.md">tabela de diálogos no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="even">
<td><p><strong>Usuário1id</strong></p></td>
<td><p>int</p></td>
<td><p>Exterior</p></td>
<td><p>ID de um usuário na sessão. Consulte a <a href="lync-server-2013-users-table.md">tabela usuários no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="odd">
<td><p><strong>User2Id</strong></p></td>
<td><p>int</p></td>
<td><p>Exterior</p></td>
<td><p>ID do outro usuário na sessão. Consulte a <a href="lync-server-2013-users-table.md">tabela usuários no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="even">
<td><p><strong>User1EndpointId</strong></p></td>
<td><p>Identificador</p></td>
<td></td>
<td><p>GUID que identifica o ponto de extremidade usado pelo primeiro usuário na sessão.</p>
<p>Este campo foi apresentado no Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>User2EndpointId</strong></p></td>
<td><p>Identificador</p></td>
<td></td>
<td><p>GUID que identifica o ponto de extremidade usado pelo segundo usuário na sessão.</p>
<p>Este campo foi apresentado no Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>TargetUserId</strong></p></td>
<td><p>int</p></td>
<td><p>Exterior</p></td>
<td><p>O URI do usuário original na solicitação SIP. consulte a <a href="lync-server-2013-users-table.md">tabela usuários no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SessionStartedById</strong></p></td>
<td><p>int</p></td>
<td><p>Exterior</p></td>
<td><p>ID do usuário que iniciou a sessão. Consulte a <a href="lync-server-2013-users-table.md">tabela usuários no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="even">
<td><p><strong>OnBehalfOfId</strong></p></td>
<td><p>int</p></td>
<td><p>Exterior</p></td>
<td><p>Indica a ID do usuário de quem o chamador está em nome. Consulte a <a href="lync-server-2013-users-table.md">tabela usuários no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ReferredById</strong></p></td>
<td><p>int</p></td>
<td><p>Exterior</p></td>
<td><p>ID do usuário por quem a chamada é referida. Consulte a <a href="lync-server-2013-users-table.md">tabela usuários no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="even">
<td><p><strong>ServerID</strong></p></td>
<td><p>int</p></td>
<td><p>Exterior</p></td>
<td><p>ID do servidor front-end usado para esta sessão. Consulte a <a href="lync-server-2013-servers-table.md">tabela servidores no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Poolid</strong></p></td>
<td><p>int</p></td>
<td><p>Exterior</p></td>
<td><p>ID do pool no qual a sessão foi capturada. Consulte a <a href="lync-server-2013-pools-table.md">tabela de grupos no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="even">
<td><p><strong>ContentTypeid</strong></p></td>
<td><p>int</p></td>
<td><p>Exterior</p></td>
<td><p>Tipo de conteúdo usado na sessão. Consulte a <a href="lync-server-2013-contenttypes-table.md">tabela ContentTypes no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="odd">
<td><p><strong>User1ClientVerId</strong></p></td>
<td><p>int</p></td>
<td><p>Exterior</p></td>
<td><p>Versão do cliente usada pelo Usuário1. Consulte a <a href="lync-server-2013-clientversions-table.md">tabela ClientVersions no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="even">
<td><p><strong>User2ClientVerId</strong></p></td>
<td><p>int</p></td>
<td><p>Exterior</p></td>
<td><p>Versão do cliente usada pelo user2. Consulte a <a href="lync-server-2013-clientversions-table.md">tabela ClientVersions no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="odd">
<td><p><strong>User1EdgeServerid</strong></p></td>
<td><p>int</p></td>
<td><p>Exterior</p></td>
<td><p>Servidor de borda usado pelo Usuário1. Consulte a <a href="lync-server-2013-edgeservers-table.md">tabela EdgeServers no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="even">
<td><p><strong>User2EdgeServerid</strong></p></td>
<td><p>int</p></td>
<td><p>Exterior</p></td>
<td><p>Servidor de borda usado pelo user2. Consulte a <a href="lync-server-2013-edgeservers-table.md">tabela EdgeServers no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsUser1Internal</strong></p></td>
<td><p>bit</p></td>
<td></td>
<td><p>Se user1 está conectado de Internal ou not.</p></td>
</tr>
<tr class="even">
<td><p><strong>IsUser2Internal</strong></p></td>
<td><p>bit</p></td>
<td></td>
<td><p>Se o User2 está conectado do Internal ou não.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Invitetime</strong></p></td>
<td><p>datetime</p></td>
<td></td>
<td><p>A hora da primeira solicitação INVITE. Geralmente, esse campo é preenchido por dados gerados da mensagem de convite inicial na sessão. Se não houver nenhuma mensagem de convite, o campo será preenchido com a data e a hora da primeira mensagem SIP relevante (até mais, cancelamento, mensagem ou informações). Geralmente, esse campo é preenchido por dados gerados da mensagem de convite inicial na sessão. Se não houver nenhuma mensagem de convite, o campo será preenchido com a data e a hora da primeira mensagem SIP relevante (até mais, cancelamento, mensagem ou informações).</p></td>
</tr>
<tr class="even">
<td><p><strong>ResponseTime</strong></p></td>
<td><p>datetime</p></td>
<td></td>
<td><p>A hora da resposta para a primeira mensagem de convite. Geralmente, esse campo é preenchido por dados gerados da mensagem de convite inicial na sessão. Se não houver nenhuma mensagem de convite, o campo será preenchido com a data e a hora da primeira mensagem SIP relevante (até mais, cancelamento, mensagem ou informações).</p></td>
</tr>
<tr class="odd">
<td><p><strong>ResponseCode</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Código de resposta SIP para o convite da sessão. Geralmente, esse campo é preenchido por dados gerados da mensagem de convite inicial na sessão. Se não houver nenhuma mensagem de convite, o campo será preenchido com a data e a hora da primeira mensagem SIP relevante (até mais, cancelamento, mensagem ou informações).</p></td>
</tr>
<tr class="even">
<td><p><strong>Diagnosticid</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>ID de diagnóstico capturada do cabeçalho SIP.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallPriority</strong></p></td>
<td><p>int</p></td>
<td><p>Exterior</p></td>
<td><p>Prioridade da chamada. Consulte a <a href="lync-server-2013-callpriorities-table.md">tabela CallPriorities no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="even">
<td><p><strong>User1MessageCount</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Número de mensagens enviadas pelo Usuário1 durante a sessão.</p></td>
</tr>
<tr class="odd">
<td><p><strong>User2MessageCount</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Número de mensagens enviadas pelo user2 durante a sessão.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionEndTime</strong></p></td>
<td><p>datetime</p></td>
<td></td>
<td><p>Hora no final da sessão.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaTypes</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Um conjunto de bits que indica o tipo de mídia desta sessão. Listadas são as definições dos tipos:</p>
<h3 id="section-1"> </h3>
<div>
<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Mensagem instantânea</p></td>
<td><p>1</p></td>
</tr>
<tr class="even">
<td><p>FILE_TRANSFER</p></td>
<td><p>2</p></td>
</tr>
<tr class="odd">
<td><p>REMOTE_ASSISTANCE</p></td>
<td><p>4</p></td>
</tr>
<tr class="even">
<td><p>APP_SHARING</p></td>
<td><p>08</p></td>
</tr>
<tr class="odd">
<td><p>ÁUDIO</p></td>
<td><p>16</p></td>
</tr>
<tr class="even">
<td><p>VIDEO</p></td>
<td><p>32</p></td>
</tr>
<tr class="odd">
<td><p>APP_INVITE</p></td>
<td><p>64</p></td>
</tr>
</tbody>
</table>

</div></td>
</tr>
<tr class="even">
<td><p><strong>User1Flag</strong></p></td>
<td><p>smallint</p></td>
<td></td>
<td><p>Um conjunto de bits que indica os atributos Usuário1. As definições de atributo a seguir estão listadas:</p>
<ul>
<li><p>0x01-integrado ao telefone desktop</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>User2Flag</strong></p></td>
<td><p>smallint</p></td>
<td></td>
<td><p>Um conjunto de bits que indica os atributos do user2. As definições de atributo a seguir estão listadas:</p>
<ul>
<li><p>0x01-integrado ao telefone desktop</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>CallFlag</strong></p></td>
<td><p>smallint</p></td>
<td></td>
<td><p>Um conjunto de bits que indica os atributos da chamada. As definições de atributo a seguir estão listadas:</p>
<ul>
<li><p>0x01-sessão repetida</p></li>
<li><p>0x02-uma chamada feita pelo agente em nome de um grupo de resposta</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>Processe</strong></p></td>
<td><p>bit</p></td>
<td></td>
<td><p>Para uso interno pelo serviço de monitoramento.</p>
<p>Este campo foi apresentado no Microsoft Lync Server 2013.</p></td>
</tr>
</tbody>
</table>


\*Para a maioria das sessões, o SessionIdSeq terá o valor de 1. Se várias sessões começarem exatamente ao mesmo tempo, o SessionIdSeq de uma será 1, por outro será 2, e assim por diante.

</div>

<span> </span>

</div>

</div>

</div>

