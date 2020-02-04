---
title: 'Lync Server 2013: Tabela FocusJoinsAndLeaves'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: FocusJoinsAndLeaves table
ms:assetid: e6f0212c-67e9-4061-8720-d0296e855991
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399026(v=OCS.15)
ms:contentKeyID: 48185690
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4365e5bbfe92168047165adf6504333e1c34fab6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765259"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="focusjoinsandleaves-table-in-lync-server-2013"></a>Tabela FocusJoinsAndLeaves no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-28_

Cada registro desta tabela contém as informações de CDR sobre o ingresso de um usuário e as informações de licença de uma conferência. Cada conferência é representada por um registro por cada vez que um usuário entra e sai da conferência.


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
<td><p>Hora da ocorrência da conferência. Usado em conjunto com <strong>SessionIdSeq</strong> para identificar uma instância de conferência de maneira exclusiva. Consulte a <a href="lync-server-2013-conferences-table.md">tabela conferências no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Primário, estrangeiro</p></td>
<td><p>Número de identificação para identificar a instância de conferência. Usado em conjunto com a <strong>identificação_da_sessãotime</strong> para identificar exclusivamente uma instância de conferência. Consulte a <a href="lync-server-2013-conferences-table.md">tabela conferências no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DialogSessionIdTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Primário, estrangeiro</p></td>
<td><p>Tempo de solicitação de sessão. Usado em conjunto com o <strong>SessionIdSeq</strong> para identificar exclusivamente uma sessão. Consulte a <a href="lync-server-2013-dialogs-table.md">tabela de diálogos no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="even">
<td><p><strong>DialogSessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Primário, estrangeiro</p></td>
<td><p>Número de identificação para identificar a sessão. Usado em conjunto com a <strong>identificação_da_sessãotime</strong> para identificar exclusivamente uma sessão. consulte a <a href="lync-server-2013-dialogs-table.md">tabela de diálogos no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ID</strong></p></td>
<td><p>int</p></td>
<td><p>Exterior</p></td>
<td><p>Número exclusivo que identifica esse usuário, referenciado pela <a href="lync-server-2013-users-table.md">tabela usuários no Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>FocusUserInstance</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Se um usuário estiver conectado em vários computadores ou dispositivos ao mesmo tempo, o <strong>UserInstance</strong> será usado para identificar exclusivamente a combinação de usuário/dispositivo.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsUserInternal</strong></p></td>
<td><p>bit</p></td>
<td><p> </p></td>
<td><p>Se o usuário está conectado de interno ou não.</p></td>
</tr>
<tr class="even">
<td><p><strong>Função</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>A função deste usuário na conferência, como apresentador ou participante.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Userjointime</strong></p></td>
<td><p>datetime</p></td>
<td><p> </p></td>
<td><p>A hora em que este usuário entra na conferência.</p></td>
</tr>
<tr class="even">
<td><p><strong>Userleavetime</strong></p></td>
<td><p>datetime</p></td>
<td><p> </p></td>
<td><p>A hora em que esse usuário sai da conferência.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ClientVerId</strong></p></td>
<td><p>int</p></td>
<td><p>Exterior</p></td>
<td><p>Versão do software cliente do usuário, referenciada à <a href="lync-server-2013-clientversions-table.md">tabela ClientVersions no Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>Userendpointid</strong></p></td>
<td><p>Identificador</p></td>
<td></td>
<td><p>Identificador global exclusivo (GUID) do ponto de extremidade usado na conferência.</p>
<p>Este campo foi apresentado no Microsoft Lync Server 2013.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

