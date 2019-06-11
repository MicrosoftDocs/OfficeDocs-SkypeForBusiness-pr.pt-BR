---
title: 'Lync Server 2013: Tabela ConferenceSessionDetails'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: ConferenceSessionDetails table
ms:assetid: 9eae6a54-69fd-4966-aa17-7ecee1297ad8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412741(v=OCS.15)
ms:contentKeyID: 48184925
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4c5aaa3ec022be18ad54cc8a24b8410c23faf799
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836495"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencesessiondetails-table-in-lync-server-2013"></a>Tabela ConferenceSessionDetails no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-28_

Cada registro representa uma sessão de conferência, que pode ser a sessão com foco ou a sessão com um servidor de conferência específico.


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
<td><p>DateTime</p></td>
<td><p>Primário, estrangeiro</p></td>
<td><p>Tempo de solicitação de sessão; usado em conjunto com <strong>SessionIdSeq</strong> para identificar uma sessão de conferência com exclusividade. Consulte a <a href="lync-server-2013-dialogs-table.md">tabela de diálogos no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Primário, estrangeiro</p></td>
<td><p>Número de identificação para identificar a sessão. Usado em conjunto com <strong></strong> a identificação_da_sessãotime para identificar exclusivamente uma sessão de conferência. Consulte a <a href="lync-server-2013-dialogs-table.md">tabela de diálogos no Lync Server 2013</a> para obter mais informações. *</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConferenceUriId</strong></p></td>
<td><p>int</p></td>
<td><p>Exterior</p></td>
<td><p>URI da conferência em foco relacionado a esta sessão. Consulte a <a href="lync-server-2013-conferenceuris-table.md">tabela ConferenceUris no Lync Server 2013</a> para obter mais informações. Esse URI é um URI de conferência baseado em foco.</p></td>
</tr>
<tr class="even">
<td><p><strong>ConfInstance</strong></p></td>
<td><p>Identificador</p></td>
<td></td>
<td><p>Identificador que diferencia as instâncias de conferências recorrentes. Cada instância de conferência recorrente tem o mesmo ConferenceURI, mas um valor ConfInstance diferente.</p>
<p>Este campo foi apresentado no Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>McuConferenceUriId</strong></p></td>
<td><p>int</p></td>
<td><p>Exterior</p></td>
<td><p>URL de conferência do servidor de conferência relacionada a esta sessão. Consulte a <a href="lync-server-2013-conferenceuris-table.md">tabela ConferenceUris no Lync Server 2013</a> para obter mais informações. Esse URI é o URI da conferência baseada no servidor de conferência. Para sessões de conferência de foco, esta coluna será nula.</p></td>
</tr>
<tr class="even">
<td><p><strong>ID</strong></p></td>
<td><p>int</p></td>
<td><p>Exterior</p></td>
<td><p>ID de um usuário na sessão de conferência. Consulte a <a href="lync-server-2013-users-table.md">tabela usuários no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Userendpointid</strong></p></td>
<td><p>identificador</p></td>
<td></td>
<td><p>Um GUID para identificar a instância do ponto de extremidade. Por exemplo, se um usuário fizer logon em máquinas diferentes com a mesma conta, cada computador terá uma ID de ponto de extremidade diferente.</p></td>
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
<td><p><strong>UserClientVersionId</strong></p></td>
<td><p>int</p></td>
<td><p>Exterior</p></td>
<td><p>Versão do cliente usada pelo usuário da conferência. Consulte a <a href="lync-server-2013-clientversions-table.md">tabela ClientVersions no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConfClientVersionId</strong></p></td>
<td><p>int</p></td>
<td><p>Exterior</p></td>
<td><p>Versão do cliente usada pelo servidor de conferência. Consulte a <a href="lync-server-2013-clientversions-table.md">tabela ClientVersions no Lync Server 2013</a> para obter mais informações.</p></td>
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
<td><p><strong>IsStartedByConfServer</strong></p></td>
<td><p>bit</p></td>
<td></td>
<td><p>Indica se a sessão foi iniciada pelo servidor de conferência.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsEndedByConfServer</strong></p></td>
<td><p>bit</p></td>
<td></td>
<td><p>Indica se a sessão terminou pelo servidor de conferência.</p></td>
</tr>
<tr class="even">
<td><p><strong>IsUserInternal</strong></p></td>
<td><p>bit</p></td>
<td></td>
<td><p>Se o usuário está conectado de Internal ou not.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ResponseCode</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Código de resposta do SIP (Session Initiation Protocol) para o convite da sessão. Geralmente, esse campo é preenchido por dados gerados da mensagem de convite inicial na sessão. Se não houver nenhuma mensagem de convite, o campo será preenchido com a data e a hora da primeira mensagem SIP relevante (até mais, cancelamento, mensagem ou informações).</p></td>
</tr>
<tr class="even">
<td><p><strong>Diagnosticid</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>ID de diagnóstico capturada do cabeçalho SIP.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ServerID</strong></p></td>
<td><p>int</p></td>
<td><p>Exterior</p></td>
<td><p>ID do servidor front-end usado para esta sessão. Consulte a <a href="lync-server-2013-servers-table.md">tabela servidores no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="even">
<td><p><strong>Poolid</strong></p></td>
<td><p>int</p></td>
<td><p>Exterior</p></td>
<td><p>ID do pool no qual a sessão foi capturada. Consulte a <a href="lync-server-2013-pools-table.md">tabela de grupos no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediationServerId</strong></p></td>
<td><p>int</p></td>
<td><p>Exterior</p></td>
<td><p>O servidor de mediação que a chamada está usando. Consulte a <a href="lync-server-2013-mediationservers-table.md">tabela MediationServers no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="even">
<td><p><strong>Gatewayid</strong></p></td>
<td><p>int</p></td>
<td><p>Exterior</p></td>
<td><p>O gateway que a chamada está usando. Consulte a <a href="lync-server-2013-gateways-table.md">tabela gateways no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="odd">
<td><p><strong>EdgeServerId</strong></p></td>
<td><p>int</p></td>
<td><p>Exterior</p></td>
<td><p>O servidor de borda que a chamada está usando. Consulte a <a href="lync-server-2013-edgeservers-table.md">tabela EdgeServers no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="even">
<td><p><strong>ContentTypeid</strong></p></td>
<td><p>int</p></td>
<td><p>Exterior</p></td>
<td><p>Tipo de conteúdo usado na sessão. Consulte a <a href="lync-server-2013-contenttypes-table.md">tabela ContentTypes no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Invitetime</strong></p></td>
<td><p>datetime</p></td>
<td></td>
<td><p>A hora da primeira solicitação INVITE. Geralmente, esse campo é preenchido por dados gerados da mensagem de convite inicial na sessão. Se não houver nenhuma mensagem de convite, o campo será preenchido com a data e a hora da primeira mensagem SIP relevante (até mais, cancelamento, mensagem ou informações).</p></td>
</tr>
<tr class="even">
<td><p><strong>ResponseTime</strong></p></td>
<td><p>datetime</p></td>
<td></td>
<td><p>Hora da primeira resposta SIP. Geralmente, esse campo é preenchido por dados gerados da mensagem de convite inicial na sessão. Se não houver nenhuma mensagem de convite, o campo será preenchido com a data e a hora da primeira mensagem SIP relevante (até mais, cancelamento, mensagem ou informações).</p></td>
</tr>
<tr class="odd">
<td><p><strong>SessionEndTime</strong></p></td>
<td><p>datetime</p></td>
<td></td>
<td><p>A hora de término da sessão.</p></td>
</tr>
<tr class="even">
<td><p><strong>UriTypeId</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Exterior</p></td>
<td><p>Contém o valor do tipo URI de MCU da <a href="lync-server-2013-uritypes-table.md">tabela UriTypes no Lync Server 2013</a>. Este campo é usado para melhorar o desempenho das consultas.</p>
<p>Este campo foi apresentado no Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Sinalizador</strong></p></td>
<td><p>smallint</p></td>
<td></td>
<td><p>Um conjunto de bits que indica os atributos de usuário. As definições de atributo a seguir estão listadas:</p>
<ul>
<li><p>Integrado ao telefone de mesa-1</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>CallFlag</strong></p></td>
<td><p>smallint</p></td>
<td></td>
<td><p>Um conjunto de bits que indica os atributos da chamada. As definições de atributo a seguir estão listadas:</p>
<ul>
<li><p>Sessão 1 repetida</p></li>
</ul></td>
</tr>
</tbody>
</table>


\*Para a maioria das sessões, o SessionIdSeq terá o valor de 1. Se várias sessões começarem exatamente ao mesmo tempo, o SessionIdSeq de uma será 1, por outro será 2, e assim por diante.

</div>

<span> </span>

</div>

</div>

</div>

