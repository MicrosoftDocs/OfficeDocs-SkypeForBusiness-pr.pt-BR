---
title: 'Lync Server 2013: modo de exibição McuJoinsAndLeaves'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: McuJoinsAndLeaves view
ms:assetid: 6f00b8e7-b8b6-4657-ac5e-d8a571806ae2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688088(v=OCS.15)
ms:contentKeyID: 49733687
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c4f3f73606cfd05df17022770da7dcd1f5266b21
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42185324"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="mcujoinsandleaves-view-in-lync-server-2013"></a>Exibição McuJoinsAndLeaves no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-01_

A exibição McuJoinsAndLeaves armazena informações sobre ingresso e saída de usuários de um servidor de conferências. Cada registro nessa exibição inclui os detalhes da chamada sobre uma combinação da entrada ou saída de um usuário e o servidor de conferência. Este modo de exibição foi introduzido no Microsoft Lync Server 2013.


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
<td><p><strong>McuUri</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>URI do servidor de conferências ao qual o usuário está conectado.</p></td>
</tr>
<tr class="even">
<td><p><strong>McuUriType</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>URI do servidor de conferências ao qual o usuário está conectado. Consulte a <a href="lync-server-2013-uritypes-table.md">tabela UriTypes no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserUri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URI do usuário cujas informações de ingresso/saída do servidor de conferências foram capturadas.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserUriType</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Tipo de URI do usuário cujas informações de ingresso/saída do servidor de conferências foram capturadas. Consulte a <a href="lync-server-2013-uritypes-table.md">tabela UriTypes no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Userlocatário</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Locatário do usuário cujas informações de ingresso/saída do servidor de conferências foram capturadas. Consulte a <a href="lync-server-2013-tenants-table.md">tabela locatários no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserClientVersion</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Versão do cliente usado pelo usuário cujas informações de ingresso/saída do servidor de conferências foram capturadas.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Userclienttype</strong></p></td>
<td><p>int</p></td>
<td><p>Cliente usado pelo usuário cujas informações de ingresso/saída do servidor de conferências foram capturadas. Consulte a <a href="lync-server-2013-useragentdef-table.md">tabela UserAgentDef no Lync Server 2013</a> para obter mais detalhes.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserClientCategory</strong></p></td>
<td><p>nvarchar (64)</p></td>
<td><p>Nome da categoria do cliente usado pelo usuário cujas informações de ingresso/saída do servidor de conferências foram capturadas.</p></td>
</tr>
<tr class="odd">
<td><p><strong>McuUserInstance</strong></p></td>
<td><p>int</p></td>
<td><p>Identificador exclusivo da combinação de usuário/dispositivo para usuários que fizeram logon simultâneo em vários dispositivos.</p></td>
</tr>
<tr class="even">
<td><p><strong>IsUserFromPstn</strong></p></td>
<td><p>bits</p></td>
<td><p>Bit que representa se o usuário é interno ou não.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DialogSessionIdTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Hora da solicitação da sessão. Utilizada em conjunto com o SessionIdSeq para identificar de forma exclusiva uma sessão. Consulte a <a href="lync-server-2013-dialogs-table.md">tabela diálogos no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="even">
<td><p><strong>DialogSessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Número de identificação para identificar a sessão. Utilizado em conjunto com o SessionIdTime para identificar de forma exclusiva uma sessão. Consulte a <a href="lync-server-2013-dialogs-table.md">tabela diálogos no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DialogId</strong></p></td>
<td><p>varchar (775)</p></td>
<td><p>ID de diálogo SIP da sessão. O formato é: diálogo;de-marca;para-marca.</p></td>
</tr>
<tr class="even">
<td><p><strong>Userjointime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Hora em que o usuário ingressou no servidor de conferências.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Userleavetime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Hora em que o usuário saiu do servidor de conferências.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

