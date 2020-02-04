---
title: 'Lync Server 2013: Tabela ErrorReport'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ErrorReport table
ms:assetid: ae0287b4-e8ca-4f8c-84ef-502897dcaa2a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412826(v=OCS.15)
ms:contentKeyID: 48185129
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8de4163f94d5848808c5b01c34b1676d3a0bbcff
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735381"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="errorreport-table-in-lync-server-2013"></a>Tabela ErrorReport no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-28_

A tabela ErrorReport armazena informações sobre erros ocorridos. Cada registro é uma ocorrência de um erro. Os erros são capturados pelo agente CDR executado no servidor front-end ou enviados do cliente.


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
<td><p><strong>ErrorTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Primária</p></td>
<td><p>Data e hora em que o erro ocorreu.</p></td>
</tr>
<tr class="even">
<td><p><strong>ErrorReportSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Primária</p></td>
<td><p>Número de identificação para identificar o relatório de erros. Usado em conjunto com <strong>ErrorTime</strong> para identificar com exclusividade um relatório de erro.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ErrorID</strong></p></td>
<td><p>int</p></td>
<td><p>Exterior</p></td>
<td><p>ID exclusiva do tipo de erro. Consulte a <a href="lync-server-2013-errordef-table.md">tabela ErrorDef no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="even">
<td><p><strong>FromUserId</strong></p></td>
<td><p>int</p></td>
<td><p>Exterior</p></td>
<td><p>Usuário que originou a solicitação que causou o erro. Consulte a <a href="lync-server-2013-users-table.md">tabela usuários no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Parauserid</strong></p></td>
<td><p>int</p></td>
<td><p>Exterior</p></td>
<td><p>Usuário de destino para a solicitação que causou o erro. Consulte a <a href="lync-server-2013-users-table.md">tabela usuários no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="even">
<td><p><strong>ConferenceUriId</strong></p></td>
<td><p>int</p></td>
<td><p>Exterior</p></td>
<td><p>URL de conferência relacionada ao erro. Consulte a <a href="lync-server-2013-conferenceuris-table.md">tabela ConferenceUris no Lync Server 2013</a> para obter mais informações. Geralmente, se ConferenceUriId não for nulo, o FromUserId ou o parauserid será nulo.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Id_da_sessãotime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Exterior</p></td>
<td><p>Usado em conjunto com o <strong>SessionIdSeq</strong> para identificar exclusivamente uma sessão. Consulte a <a href="lync-server-2013-dialogs-table.md">tabela de diálogos no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Exterior</p></td>
<td><p>Número de identificação para identificar a sessão. Usado em conjunto com a <strong>identificação_da_sessãotime</strong> para identificar exclusivamente uma sessão. Consulte a <a href="lync-server-2013-dialogs-table.md">tabela de diálogos no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SourceID</strong></p></td>
<td><p>int</p></td>
<td><p>Exterior</p></td>
<td><p>Servidor que enviou o relatório de erro (se o relatório estiver sendo enviado de um componente de servidor). Consulte a <a href="lync-server-2013-servers-table.md">tabela servidores no Lync Server 2013</a> para obter mais informações.</p>
<p>Este campo foi apresentado no Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>ApplicationId</strong></p></td>
<td><p>int</p></td>
<td><p>Exterior</p></td>
<td><p>Servidor que enviou o relatório de erro (se o relatório estiver sendo enviado de um componente de servidor). Consulte a <a href="lync-server-2013-application-table.md">tabela de aplicativos no Lync Server 2013</a> para obter mais informações.</p>
<p>Este campo foi apresentado no Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MsDiagHeader</strong></p></td>
<td><p>imagem</p></td>
<td><p> </p></td>
<td><p>Mais informações sobre o erro.</p>
<p>Esses dados podem ser convertidos em um formato de texto usando esta sintaxe:</p>
<p><code>cast(cast(Detail as varbinary(max)) as varchar(max)) </code></p></td>
</tr>
<tr class="even">
<td><p><strong>ClientVersionId</strong></p></td>
<td><p>int</p></td>
<td><p>Exterior</p></td>
<td><p>A versão do cliente do ponto de extremidade que envia o relatório de erros. Consulte a <a href="lync-server-2013-clientversions-table.md">tabela ClientVersions no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsCapturedByServer</strong></p></td>
<td><p>bit</p></td>
<td></td>
<td><p>É o relatório de erros capturado pelo agente CDR em execução no servidor front-end ou enviado pelo cliente.</p></td>
</tr>
<tr class="even">
<td><p><strong>Sinalizador</strong></p></td>
<td><p>smallint</p></td>
<td></td>
<td><p>Reservado para uso futuro.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Telemetria</strong></p></td>
<td><p>Identificador</p></td>
<td></td>
<td><p>Identificador exclusivo que correlaciona as informações de tempo de junção para os diferentes componentes envolvidos em uma conferência.</p>
<p>Este campo foi apresentado no Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSetupTime</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Tempo (em milissegundos) necessário para um componente específico entrar em uma conferência.</p>
<p>Este campo foi apresentado no Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ServerID</strong></p></td>
<td><p>int</p></td>
<td><p>Exterior</p></td>
<td><p>Representa o nome de domínio totalmente qualificado do servidor que gerou o relatório de erros.</p></td>
</tr>
<tr class="even">
<td><p><strong>Poolid</strong></p></td>
<td><p>int</p></td>
<td><p>Exterior</p></td>
<td><p>Representa o nome de domínio totalmente qualificado do pool onde o relatório de erro foi gerado.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

