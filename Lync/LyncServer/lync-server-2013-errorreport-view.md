---
title: 'Lync Server 2013: modo de exibição ErrorReport'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ErrorReport view
ms:assetid: ca873f7e-b18b-4eaf-8db0-5f9d5a9b60a1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721887(v=OCS.15)
ms:contentKeyID: 49733821
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a72b2f12c00248095b99198182b8c71bb945bfa3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735271"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="errorreport-view-in-lync-server-2013"></a>Exibição ErrorReport no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-01-22_

A exibição ErrorReport armazena informações sobre erros relatados. Cada registro é uma ocorrência de um erro. Os erros são capturados pelo agente CDR executado no servidor front-end ou enviados do cliente. Este modo de exibição foi apresentado no Microsoft Lync Server 2013.


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
<td><p><strong>ErrorTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Ocorreu um erro de hora. Usado em conjunto com ErrorReportSeq para identificar um erro exclusivamente.</p></td>
</tr>
<tr class="even">
<td><p><strong>ErrorReportSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Número de identificação para identificar o erro. Usado em conjunto com ErrorTime para identificar um erro com exclusividade.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MsDiagId</strong></p></td>
<td><p>int</p></td>
<td><p>ID de diagnóstico do relatório de erros.</p></td>
</tr>
<tr class="even">
<td><p><strong>FromUri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URL do usuário que originou o erro.</p></td>
</tr>
<tr class="odd">
<td><p><strong>FromUriType</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Tipo de URI do usuário que originou o erro. Consulte a <a href="lync-server-2013-uritypes-table.md">tabela UriTypes no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="even">
<td><p><strong>FromTenant</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Locatário do usuário que originou o erro. Consulte a <a href="lync-server-2013-tenants-table.md">tabela locatários no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ToUri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URI do usuário que foi o destino do relatório de erros.</p></td>
</tr>
<tr class="even">
<td><p><strong>ToUriType</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Tipo de URI do usuário que direciona o relatório de erros. Consulte a tabela UriTypes para obter mais informações.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Tolocatário</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Locatário do usuário que direciona o relatório de erros. Consulte a <a href="lync-server-2013-tenants-table.md">tabela locatários no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="even">
<td><p><strong>ConferenceUri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URL da conferência que foi o alvo do relatório de erros.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConferenceUriType</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Tipo de URI da conferência que foi o destino do relatório de erros. Consulte a <a href="lync-server-2013-uritypes-table.md">tabela UriTypes no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="even">
<td><p><strong>Id_da_sessãotime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Tempo de solicitação de sessão que originou o relatório de erros. Usado em conjunto com o SessionIdSeq para identificar exclusivamente uma sessão. Consulte a <a href="lync-server-2013-dialogs-table.md">tabela de diálogos no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Número de identificação para identificar a solicitação de sessão que originou o relatório de erros. Usado em conjunto com a Identificação_da_sessãotime para identificar exclusivamente uma sessão. Consulte a <a href="lync-server-2013-dialogs-table.md">tabela de diálogos no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="even">
<td><p><strong>Caixa de diálogo</strong></p></td>
<td><p>VARSTRING (775)</p></td>
<td><p>ID da caixa de diálogo SIP da sessão que originou o erro. O formato é:</p>
<p>caixa de diálogo; de-marca; até-marca</p>
<p>Esses dados podem ser convertidos em um formato de texto usando esta sintaxe:</p>
<p>Cast (castid (externalId como varbinary (max)) como varchar (max))</p></td>
</tr>
<tr class="odd">
<td><p><strong>ClientVersion</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Versão do cliente usada pelo usuário que originou o erro.</p></td>
</tr>
<tr class="even">
<td><p><strong>ClientType</strong></p></td>
<td><p>int</p></td>
<td><p>Cliente usado pelo usuário que originou o erro. Consulte a <a href="lync-server-2013-useragentdef-table.md">tabela UserAgentDef no Lync Server 2013</a> para obter mais detalhes.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ClientCategory</strong></p></td>
<td><p>nvarchar (64)</p></td>
<td><p>Nome da categoria do cliente usado pelo usuário que originou o erro.</p></td>
</tr>
<tr class="even">
<td><p><strong>Origem</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Nome do servidor que originou o erro (se o relatório foi enviado a partir de um componente de servidor).</p></td>
</tr>
<tr class="odd">
<td><p><strong>Aplicativo</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Nome do aplicativo que originou o erro (se o relatório foi enviado a partir de um componente de servidor).</p></td>
</tr>
<tr class="even">
<td><p><strong>ResponseCode</strong></p></td>
<td><p>int</p></td>
<td><p>Código de resposta SIP para a sessão da mensagem SIP que contém o relatório de erros.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RequestType</strong></p></td>
<td><p>varchar (max)</p></td>
<td><p>Tipo de solicitação que falhou.</p></td>
</tr>
<tr class="even">
<td><p><strong>ContentType</strong></p></td>
<td><p>varchar (max)</p></td>
<td><p>Tipo de conteúdo da solicitação que falhou.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallType</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Tipo de sessão. Consulte a <a href="lync-server-2013-calltype-table.md">tabela CallType no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="even">
<td><p><strong>Telemetria</strong></p></td>
<td><p>identificador</p></td>
<td><p>Identificador exclusivo que correlaciona as informações de tempo de junção para os diferentes componentes envolvidos em uma conferência.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Setuptime</strong></p></td>
<td><p>int</p></td>
<td><p>Tempo (em milissegundos) necessário para um componente específico entrar em uma conferência.</p></td>
</tr>
<tr class="even">
<td><p><strong>IsCapturedByServer</strong></p></td>
<td><p>bit</p></td>
<td><p>Indica se o relatório de erros foi capturado pelo agente CDR em execução no servidor front-end ou enviado pelo cliente.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Sinalizador</strong></p></td>
<td><p>smallint</p></td>
<td><p>Reservado para uso futuro.</p></td>
</tr>
<tr class="even">
<td><p><strong>MsDiagHeader</strong></p></td>
<td><p>varchar (max)</p></td>
<td><p>Informações adicionais sobre o erro.</p></td>
</tr>
<tr class="odd">
<td><p><strong>FrontEnd</strong></p></td>
<td><p>nvarchar</p></td>
<td><p>Nome de domínio totalmente qualificado do servidor front-end que enviou o relatório.</p></td>
</tr>
<tr class="even">
<td><p><strong>Pool</strong></p></td>
<td><p>nvarchar</p></td>
<td><p>Nome de domínio totalmente qualificado do pool que contém o servidor front-end que enviou o relatório.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

