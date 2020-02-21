---
title: 'Lync Server 2013: tabela McuJoinsAndLeaves'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: McuJoinsAndLeaves table
ms:assetid: 4e073366-0b5d-45b4-a3f6-d63dd5fd9f25
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398316(v=OCS.15)
ms:contentKeyID: 48184115
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ae21b9a8ec2107d8a2bd0a99f1e21d6f182a830e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42185334"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="mcujoinsandleaves-table-in-lync-server-2013"></a>Tabela McuJoinsAndLeaves no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-28_

Cada registro desta tabela contém detalhes da chamada sobre uma combinação de um servidor de ingresso ou de licença e de conferência do usuário. Por exemplo, se um usuário ingressar em uma conferência que inclui a conferência da Web e os elementos de áudio/vídeo, um registro será criado para a associação de Webconferência do usuário, e outro registro será criado para a junção de conferência de áudio/vídeo do usuário.


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
<td><p>datetime</p></td>
<td><p>Primária, estrangeira</p></td>
<td><p>Hora da instância da conferência. Usado em conjunto com o <strong>SessionIdSeq</strong> para identificar exclusivamente uma instância de conferência. Consulte a <a href="lync-server-2013-conferences-table.md">tabela conferências no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Primário, externo</p></td>
<td><p>Número de ID para identificar a instância da conferência. Usado em conjunto com a <strong>identificação_da_sessãotime</strong> para identificar exclusivamente uma instância de conferência. Consulte a <a href="lync-server-2013-conferences-table.md">tabela conferências no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserId</strong></p></td>
<td><p>int</p></td>
<td><p>Primário, externo</p></td>
<td><p>Número exclusivo identificando este usuário. Consulte a <a href="lync-server-2013-users-table.md">tabela Users no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="even">
<td><p><strong>McuUserInstance</strong></p></td>
<td><p>int</p></td>
<td><p>Primário</p></td>
<td><p>Se um usuário estiver conectado em vários computadores ou dispositivos ao mesmo tempo, McuUserInstance identifica exclusivamente a combinação de usuário/dispositivo.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsFromPstn</strong></p></td>
<td><p>bits</p></td>
<td><p> </p></td>
<td><p>Se o usuário está ingressando de uma PSTN ou não.</p></td>
</tr>
<tr class="even">
<td><p><strong>McuId</strong></p></td>
<td><p>int</p></td>
<td><p>Primário, externo</p></td>
<td><p>Número exclusivo que identifica este servidor de conferência. Consulte a <a href="lync-server-2013-mcus-table.md">tabela MCUs no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DialogSessionIdTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Estrangeira</p></td>
<td><p>Tempo da solicitação de sessão. Usado em conjunto com <strong>SessionIdSeq</strong> para identificar exclusivamente uma sessão. Consulte a <a href="lync-server-2013-dialogs-table.md">tabela diálogos no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="even">
<td><p><strong>DialogSessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Estrangeira</p></td>
<td><p>O número de ID para identificar a sessão. Usado em conjunto com <strong>SessionIdTime</strong> para identificar exclusivamente uma sessão. Consulte a <a href="lync-server-2013-dialogs-table.md">tabela diálogos no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Userjointime</strong></p></td>
<td><p>datetime</p></td>
<td><p> </p></td>
<td><p>A hora em que este usuário ingressa neste servidor de conferência.</p></td>
</tr>
<tr class="even">
<td><p><strong>Userleavetime</strong></p></td>
<td><p>datetime</p></td>
<td><p> </p></td>
<td><p>O horário em que este usuário deixa este servidor de conferência.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ClientVerId</strong></p></td>
<td><p>int</p></td>
<td><p>Estrangeira</p></td>
<td><p>Identificador que especifica o número da versão do software cliente usado na conferência. Consulte a <a href="lync-server-2013-clientversions-table.md">tabela ClientVersions no Lync Server 2013</a> para obter mais informações.</p>
<p>Este campo foi introduzido no Microsoft Lync Server 2013.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

