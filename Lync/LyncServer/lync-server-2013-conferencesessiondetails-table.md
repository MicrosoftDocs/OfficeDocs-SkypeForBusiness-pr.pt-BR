---
title: 'Lync Server 2013: tabela ConferenceSessionDetails'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ConferenceSessionDetails table
ms:assetid: 9eae6a54-69fd-4966-aa17-7ecee1297ad8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412741(v=OCS.15)
ms:contentKeyID: 48184925
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6c88cb167f334bc27148b16deafb0e7759105955
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42040900"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencesessiondetails-table-in-lync-server-2013"></a>Tabela ConferenceSessionDetails no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-28_

Cada registro representa uma sessão de conferência, que poderia ser a sessão com Foco ou a sessão com um servidor de conferência específico.


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
<td><p><strong>Identificação_da_sessãotime</strong></p></td>
<td><p>Datetime</p></td>
<td><p>Primário, externo</p></td>
<td><p>Tempo da solicitação da sessão; usado em conjunto com <strong>SessionIdSeq</strong> para identificar de forma única uma sessão de conferência. Consulte a <a href="lync-server-2013-dialogs-table.md">tabela diálogos no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Primário, Estrangeiro</p></td>
<td><p>O número de ID para identificar a sessão. Usado em conjunto com a <strong>identificação_da_sessãotime</strong> para identificar exclusivamente uma sessão de conferência. Consulte a <a href="lync-server-2013-dialogs-table.md">tabela diálogos no Lync Server 2013</a> para obter mais informações. *</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConferenceUriId</strong></p></td>
<td><p>int</p></td>
<td><p>Estrangeira</p></td>
<td><p>URI da conferência com foco relacionada a esta sessão. Consulte a <a href="lync-server-2013-conferenceuris-table.md">tabela ConferenceUris no Lync Server 2013</a> para obter mais informações. Esta é uma URI de conferência baseada em Foco.</p></td>
</tr>
<tr class="even">
<td><p><strong>ConfInstance</strong></p></td>
<td><p>Identificador</p></td>
<td></td>
<td><p>Identificador que diferencia entre instâncias de conferências recorrentes. Cada instância de conferência recorrente possui o mesmo ConferenceURI, mas um valor ConfInstance diferente.</p>
<p>Este campo foi introduzido no Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>McuConferenceUriId</strong></p></td>
<td><p>int</p></td>
<td><p>Estrangeira</p></td>
<td><p>URI da conferência do servidor de conferências relacionada a esta sessão. Consulte a <a href="lync-server-2013-conferenceuris-table.md">tabela ConferenceUris no Lync Server 2013</a> para obter mais informações. Esta é a URI de conferência baseada em servidor. Para sessões de conferência com foco, esta coluna estará nula.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserId</strong></p></td>
<td><p>int</p></td>
<td><p>Estrangeira</p></td>
<td><p>ID de um usuário na sessão de conferência. Consulte a <a href="lync-server-2013-users-table.md">tabela Users no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Userendpointid</strong></p></td>
<td><p>identificador</p></td>
<td></td>
<td><p>Um GUID para identificar a instância do ponto de extremidade. Por exemplo, se um usuário faz logon em máquinas diferentes com a mesma conta, cada máquina terá um ID de ponto de extremidade diferente.</p></td>
</tr>
<tr class="even">
<td><p><strong>OnBehalfOfId</strong></p></td>
<td><p>int</p></td>
<td><p>Estrangeira</p></td>
<td><p>Indica a ID do usuário que está em nome do chamador. Consulte a <a href="lync-server-2013-users-table.md">tabela Users no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ReferredById</strong></p></td>
<td><p>int</p></td>
<td><p>Estrangeira</p></td>
<td><p>A ID do usuário a quem se refere a chamada. Consulte a <a href="lync-server-2013-users-table.md">tabela Users no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserClientVersionId</strong></p></td>
<td><p>int</p></td>
<td><p>Estrangeira</p></td>
<td><p>Versão do cliente usado pelo usuário da conferência. Consulte a <a href="lync-server-2013-clientversions-table.md">tabela ClientVersions no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConfClientVersionId</strong></p></td>
<td><p>int</p></td>
<td><p>Estrangeira</p></td>
<td><p>Versão do cliente usado pelo servidor de conferências. Consulte a <a href="lync-server-2013-clientversions-table.md">tabela ClientVersions no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="even">
<td><p><strong>ReplaceDialogIdTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Estrangeira</p></td>
<td><p>O número de identificação para identificar a caixa de diálogo que foi substituída pela sessão atual. Consulte a <a href="lync-server-2013-dialogs-table.md">tabela diálogos no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ReplaceDialogIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Estrangeira</p></td>
<td><p>O número de identificação para identificar a sessão. Usado em conjunto com <strong>ReplacesDialogIdTime </strong> para identificar exclusivamente uma sessão que é substituída por esta sessão. Consulte a <a href="lync-server-2013-dialogs-table.md">tabela diálogos no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="even">
<td><p><strong>IsStartedByConfServer</strong></p></td>
<td><p>bits</p></td>
<td></td>
<td><p>Indica se a sessão é iniciada pelo Servidor de conferências.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsEndedByConfServer</strong></p></td>
<td><p>bits</p></td>
<td></td>
<td><p>Indica se a sessão é encerrada pelo Servidor de conferências.</p></td>
</tr>
<tr class="even">
<td><p><strong>IsUserInternal</strong></p></td>
<td><p>bits</p></td>
<td></td>
<td><p>Se o usuário está conectado de um local interno ou não.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ResponseCode</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Código de resposta do Protocolo de Iniciação de Sessão (SIP) para o convite da sessão. Este campo é geralmente preenchido por dados gerados da mensagem INVITE inicial em uma sessão. Caso não haja nenhuma mensagem CONVIDAR, o campo é preenchidos com a data e horário da primeira mensagem de SIP relevante (ATÉ LOGO, CANCELAR, MENSAGEM ou INFO).</p></td>
</tr>
<tr class="even">
<td><p><strong>Diagnosticid</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>ID de diagnóstico capturado do cabeçalho do SIP.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ServerId</strong></p></td>
<td><p>int</p></td>
<td><p>Estrangeira</p></td>
<td><p>A ID do servidor Front-End usado para esta sessão. Consulte a <a href="lync-server-2013-servers-table.md">tabela de servidores no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="even">
<td><p><strong>Poolid</strong></p></td>
<td><p>int</p></td>
<td><p>Estrangeira</p></td>
<td><p>A ID do pool no qual a sessão foi capturada. Consulte a <a href="lync-server-2013-pools-table.md">tabela pools no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediationServerId</strong></p></td>
<td><p>int</p></td>
<td><p>Estrangeira</p></td>
<td><p>O servidor de mediação que a chamada está usando. Consulte a <a href="lync-server-2013-mediationservers-table.md">tabela MediationServers no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="even">
<td><p><strong>Gatewayid</strong></p></td>
<td><p>int</p></td>
<td><p>Estrangeira</p></td>
<td><p>O gateway que a chamada está usando. Consulte a <a href="lync-server-2013-gateways-table.md">tabela gateways no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="odd">
<td><p><strong>EdgeServerId</strong></p></td>
<td><p>int</p></td>
<td><p>Estrangeira</p></td>
<td><p>O Servidor de Borda que a chamada está usando. Consulte a <a href="lync-server-2013-edgeservers-table.md">tabela EdgeServers no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="even">
<td><p><strong>ContentTypeId</strong></p></td>
<td><p>int</p></td>
<td><p>Estrangeira</p></td>
<td><p>Tipo de conteúdo usado na sessão. Consulte a <a href="lync-server-2013-contenttypes-table.md">tabela ContentTypes no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Invitetime</strong></p></td>
<td><p>datetime</p></td>
<td></td>
<td><p>A hora da primeira solicitação INVITE. Este campo é geralmente preenchido por dados gerados da mensagem INVITE inicial em uma sessão. Se não houver mensagem INVITE, então o campo será preenchido com a data e hora da primeira mensagem SIP relevante (BYE, CANCEL, MESSAGE ou INFO).</p></td>
</tr>
<tr class="even">
<td><p><strong>ResponseTime</strong></p></td>
<td><p>datetime</p></td>
<td></td>
<td><p>A hora da primeira SIP RESPONSE. Este campo é geralmente preenchido por dados gerados da mensagem INVITE inicial em uma sessão. Se não houver mensagem INVITE, então o campo será preenchido com a data e hora da primeira mensagem SIP relevante (BYE, CANCEL, MESSAGE ou INFO).</p></td>
</tr>
<tr class="odd">
<td><p><strong>SessionEndTime</strong></p></td>
<td><p>datetime</p></td>
<td></td>
<td><p>O horário em que a sessão terminou.</p></td>
</tr>
<tr class="even">
<td><p><strong>UriTypeId</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Estrangeira</p></td>
<td><p>Contém o valor do tipo URI MCU da <a href="lync-server-2013-uritypes-table.md">tabela UriTypes no Lync Server 2013</a>. Esse campo é usado para melhorar o desempenho da consulta.</p>
<p>Este campo foi introduzido no Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Sinalizador</strong></p></td>
<td><p>smallint</p></td>
<td></td>
<td><p>Um conjunto de bits que indica os atributos do usuário. As definições de atributo a seguir são listadas:</p>
<ul>
<li><p>Integrado com telefone de mesa - 1</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>CallFlag</strong></p></td>
<td><p>smallint</p></td>
<td></td>
<td><p>Um conjunto de bits que indica os atributos da chamada. As definições de atributo a seguir são listadas:</p>
<ul>
<li><p>Sessão Repetida - 1</p></li>
</ul></td>
</tr>
</tbody>
</table>


\*Para a maioria das sessões, SessionIdSeq terá o valor 1. Se várias sessões iniciam exatamente ao mesmo tempo, o SessionIdSeq para uma delas será 1 e para a outra será 2 e assim por diante.

</div>

<span> </span>

</div>

</div>

</div>

