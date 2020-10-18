---
title: 'Lync Server 2013: modo de exibição FocusJoinsAndLeaves'
description: 'Lync Server 2013: modo de exibição FocusJoinsAndLeaves.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: FocusJoinsAndLeaves view
ms:assetid: 226460ef-766f-4d61-80cb-f332b65a210d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687992(v=OCS.15)
ms:contentKeyID: 49733582
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c6f68c44461e378e9ebedce1305ee6b384a7a8a7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577447"
---
# <a name="focusjoinsandleaves-view-in-lync-server-2013"></a>Exibição FocusJoinsAndLeaves no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-01_

O modo de exibição FocusJoinsAndLeaves armazena informações sobre as informações de ingresso e saída de uma conferência. Cada conferência é representada por um registro escrito a cada vez que um usuário entra e sai da conferência. Este modo de exibição foi introduzido no Microsoft Lync Server 2013.


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
<td><p>Hora da instância da conferência. Usada em conjunto com SessionIdSeq para identificar uma instância da conferência de maneira exclusiva. Consulte a <a href="lync-server-2013-conferences-table.md">tabela conferências no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Número de ID para identificar a instância da conferência. Usada em conjunto com SessionIdTime para identificar uma instância da conferência de maneira exclusiva. Consulte a <a href="lync-server-2013-conferences-table.md">tabela conferências no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserUri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URI do usuário cujas informações de ingresso/saída da conferência foram capturadas.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserUriType</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Tipo de URI do usuário cujas informações de ingresso/saída da conferência foram capturadas. Consulte a <a href="lync-server-2013-uritypes-table.md">tabela UriTypes no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Userlocatário</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Locatário do usuário cujas informações de ingresso/saída da conferência foram capturadas. Consulte a <a href="lync-server-2013-tenants-table.md">tabela locatários no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="even">
<td><p><strong>Userendpointid</strong></p></td>
<td><p>identificador</p></td>
<td><p>Identificador exclusivo do usuário cujas informações de ingresso/saída da conferência foram capturadas.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserClientVersion</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Versão do cliente usado pelo usuário cujas informações de ingresso/saída da conferência foram capturadas.</p></td>
</tr>
<tr class="even">
<td><p><strong>Userclienttype</strong></p></td>
<td><p>int</p></td>
<td><p>Cliente usado pelo usuário cujas informações de ingresso/saída da conferência foram capturadas. Consulte a <a href="lync-server-2013-useragentdef-table.md">tabela UserAgentDef no Lync Server 2013</a> para obter mais detalhes.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserClientCategory</strong></p></td>
<td><p>nvarchar (64)</p></td>
<td><p>Nome da categoria do cliente usado pelo usuário cujas informações de ingresso/saída da conferência foram capturadas.</p></td>
</tr>
<tr class="even">
<td><p><strong>FocusUserInstance</strong></p></td>
<td><p>int</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><strong>IsuserInternal</strong></p></td>
<td><p>bits</p></td>
<td><p>Bit que representa se o usuário é interno ou não.</p></td>
</tr>
<tr class="even">
<td><p><strong>DialogSessionIdTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Hora da solicitação da sessão. Utilizada em conjunto com o SessionIdSeq para identificar de forma exclusiva uma sessão. Consulte a <a href="lync-server-2013-dialogs-table.md">tabela diálogos no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DialogSessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Se um usuário estiver conectado em vários computadores ou dispositivos ao mesmo tempo, UserInstance será usada para identificar exclusivamente a combinação de usuário/dispositivo.</p></td>
</tr>
<tr class="even">
<td><p><strong>DialogId</strong></p></td>
<td><p>varchar (775)</p></td>
<td><p>ID de diálogo SIP da sessão. O formato é: diálogo;de-marca;para-marca.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Userjointime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Hora em que o usuário entrou na conferência.</p></td>
</tr>
<tr class="even">
<td><p><strong>Userleavetime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Hora em que o usuário saiu da conferência.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserRole</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Função do usuário na conferência, como apresentador ou participante.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

