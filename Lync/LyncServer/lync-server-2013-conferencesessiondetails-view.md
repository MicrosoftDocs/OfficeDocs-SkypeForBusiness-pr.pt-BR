---
title: 'Lync Server 2013: modo de exibição ConferenceSessionDetails'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ConferenceSessionDetails view
ms:assetid: 5858c84d-baed-421d-ad1d-3726e150e256
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688066(v=OCS.15)
ms:contentKeyID: 49733660
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ef6d8baf95cc99c342e18200f9a17e5ab03a7f4f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140554"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="conferencesessiondetails-view-in-lync-server-2013"></a>Exibição ConferenceSessionDetails no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-11-12_

O ConferenceSessionDetails visualiza as informações dos repositórios sobre sessões com vários participantes. Cada registro representa uma sessão de conferência, que poderia ser a sessão com Foco ou a sessão com um servidor de conferência específico. Este modo de exibição foi introduzido no Microsoft Lync Server 2013.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Coluna</th>
<th>Tipo de dados</th>
<th>Detalhes</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Identificação_da_sessãotime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Hora da solicitação da sessão. Utilizada em conjunto com o SessionIdSeq para identificar de forma exclusiva uma sessão. Consulte a <a href="lync-server-2013-dialogs-table.md">tabela diálogos no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Número de identificação para identificar a sessão. Utilizado em conjunto com o SessionIdTime para identificar de forma exclusiva uma sessão. Consulte a <a href="lync-server-2013-dialogs-table.md">tabela diálogos no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Invitetime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Horário da primeira solicitação CONVIDAR. Este campo é, geralmente, preenchido por dados gerados a partir da mensagem CONVIDAR inicial na sessão. Se não houver nenhuma mensagem CONVIDAR, então o campo será preenchido com a data e a hora da primeira mensagem SIP relevante (ATÉ LOGO, CANCELAR, MENSAGEM ou INFO).</p></td>
</tr>
<tr class="even">
<td><p><strong>Conferenceui</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URI da conferência.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConferenceUriType</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Tipo de URI da conferência. Consulte a <a href="lync-server-2013-uritypes-table.md">tabela UriTypes no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="even">
<td><p><strong>ConfInstance</strong></p></td>
<td><p>identificador</p></td>
<td><p>Identificador que diferencia instâncias de conferências recorrentes. Cada instância de conferência recorrente possui o mesmo ConferenceURI, mas um valor ConfInstance diferente.</p></td>
</tr>
<tr class="odd">
<td><p><strong>McuConferenceUri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URI do servidor de conferência.</p></td>
</tr>
<tr class="even">
<td><p><strong>McuConferenceUriType</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Tipo de URI de servidor de conferência. Consulte a <a href="lync-server-2013-uritypes-table.md">tabela UriTypes no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserUri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URI do usuário envolvido na sessão.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserUriType</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Tipo de URI do usuário que fez parte da sessão. Consulte a <a href="lync-server-2013-uritypes-table.md">tabela UriTypes no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Userlocatário</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Locatário do usuário que fez parte da sessão. Consulte a <a href="lync-server-2013-tenants-table.md">tabela locatários no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="even">
<td><p><strong>Userendpointid</strong></p></td>
<td><p>identificador</p></td>
<td><p>Identificador exclusivo do usuário que fez parte da sessão.</p></td>
</tr>
<tr class="odd">
<td><p><strong>EndTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Hora de término da sessão.</p></td>
</tr>
<tr class="even">
<td><p><strong>ConferenceClientVersion</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Versão do servidor de conferência.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConferenceClientType</strong></p></td>
<td><p>int</p></td>
<td><p>Tipo de servidor de conferência. Consulte a <a href="lync-server-2013-useragentdef-table.md">tabela UserAgentDef no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="even">
<td><p><strong>ConferenceCategory</strong></p></td>
<td><p>nvarchar (64)</p></td>
<td><p>Categoria do servidor de conferência.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserClientVersion</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Versão do cliente utilizado pelo usuário que participou da sessão.</p></td>
</tr>
<tr class="even">
<td><p><strong>Userclienttype</strong></p></td>
<td><p>int</p></td>
<td><p>Cliente utilizado pelo usuário que participou da sessão. Consulte a <a href="lync-server-2013-useragentdef-table.md">tabela UserAgentDef no Lync Server 2013</a> para obter mais detalhes.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserClientCategory</strong></p></td>
<td><p>nvarchar (64)</p></td>
<td><p>Nome da categoria do cliente utilizado pelo usuário que foi parte da sessão.</p></td>
</tr>
<tr class="even">
<td><p><strong>OnBehalfOfUri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URI do usuário em cujo nome a sessão foi iniciada.</p></td>
</tr>
<tr class="odd">
<td><p><strong>OnBehalfOfUriType</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Tipo de URI do usuário em cujo nome a sessão foi iniciada. Consulte a <a href="lync-server-2013-uritypes-table.md">tabela UriTypes no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="even">
<td><p><strong>OnBehalfOfTenant</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Locatário do usuário em cujo nome a sessão foi iniciada. Consulte a <a href="lync-server-2013-tenants-table.md">tabela locatários no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ReferredByUri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URI do usuário que se refere à sessão.</p></td>
</tr>
<tr class="even">
<td><p><strong>ReferredByUriType</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Tipo de URI do usuário que se refere à sessão. Consulte a <a href="lync-server-2013-uritypes-table.md">tabela UriTypes no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ReferredByUriTenant</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Locatário do usuário que se refere à sessão. Consulte a <a href="lync-server-2013-tenants-table.md">tabela locatários no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="even">
<td><p><strong>DialogId</strong></p></td>
<td><p>VARSTRING (775)</p></td>
<td><p>Identificação da caixa de diálogo SIP. O formato é</p>
<p>:d ialog; from-tag; to-tag</p></td>
</tr>
<tr class="odd">
<td><p><strong>ReplaceDialogIdTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Número de identificação para identificar o diálogo que foi substituído pela sessão atual. Consulte a <a href="lync-server-2013-dialogs-table.md">tabela diálogos no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="even">
<td><p><strong>ReplaceDialogIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Número de identificação para identificar a sessão. Utilizado em conjunto com o ReplaceDialogIdTime para identificar de forma exclusiva a sessão que foi substituída por esta sessão. Consulte a <a href="lync-server-2013-dialogs-table.md">tabela diálogos no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ReplacesDialogId</strong></p></td>
<td><p>varchar (775)</p></td>
<td><p>Identificação da caixa de diálogo SIP substitui a sessão. O formato dela é:</p>
<p>caixa de diálogo; de-tag; to-tag</p></td>
</tr>
<tr class="even">
<td><p><strong>IsStartedByConfServer</strong></p></td>
<td><p>bits</p></td>
<td><p>Indica se a sessão foi iniciada pelo servidor de conferência.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsEndedByConfServer</strong></p></td>
<td><p>bits</p></td>
<td><p>Indica se a sessão foi finalizada pelo servidor de conferência.</p></td>
</tr>
<tr class="even">
<td><p><strong>IsUserInternal</strong></p></td>
<td><p>bits</p></td>
<td><p>Indica se o usuário está conectado à rede interna.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ResponseTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>O tempo de resposta para a primeira mensagem CONVIDAR. Este campo é, geralmente, preenchido por dados gerados a partir da mensagem CONVIDAR inicial na sessão. Se não houver nenhuma mensagem CONVIDAR, então o campo será preenchido com a data e a hora da primeira mensagem SIP relevante (ATÉ LOGO, CANCELAR, MENSAGEM ou INFO).</p></td>
</tr>
<tr class="even">
<td><p><strong>ResponseCode</strong></p></td>
<td><p>int</p></td>
<td><p>Código de resposta SIP para convite de sessão. Este campo é normalmente preenchido por dados gerados na mensagem CONVIDAR inicial na sessão. Caso não haja nenhuma mensagem CONVIDAR, o campo é preenchidos com a data e horário da primeira mensagem de SIP relevante (ATÉ LOGO, CANCELAR, MENSAGEM ou INFO).</p></td>
</tr>
<tr class="odd">
<td><p><strong>Diagnosticid</strong></p></td>
<td><p>int</p></td>
<td><p>ID de diagnóstico capturada dos cabeçalhos SIP da sessão.</p></td>
</tr>
<tr class="even">
<td><p><strong>ContentType</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Tipo de conteúdo para a sessão.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Front</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>FQDN do servidor de Front-End que capturou os dados para a sessão.</p></td>
</tr>
<tr class="even">
<td><p><strong>Pool</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>FQDN do pool que capturou os dados para a sessão.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediationServer</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Servidor de Mediação utilizado pelo usuário que participou da sessão.</p></td>
</tr>
<tr class="even">
<td><p><strong>Gateway</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Gateway usado pelo usuário que participou da sessão.</p></td>
</tr>
<tr class="odd">
<td><p><strong>EdgeServer</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>FQDN do Servidor de Borda utilizado pelo usuário que participou da sessão.</p></td>
</tr>
<tr class="even">
<td><p><strong>Sinalizador</strong></p></td>
<td><p>smallint</p></td>
<td><p>Indica os atributos do usuário que participou da sessão. As definições de atributos a seguir são permitidas:</p>
<p>0x01 - Integrado com telefone de mesa</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallFlag</strong></p></td>
<td><p>smallint</p></td>
<td><p>Indica os atributos da chamada. As definições de atributo a seguir são permitidas:</p>
<p>0x01 - Sessão repetida0</p>
<p>x02 - Uma chamada feita por um agente em nome de um Grupo de Resposta</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

