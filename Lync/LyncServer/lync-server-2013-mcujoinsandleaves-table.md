---
title: 'Lync Server 2013: Tabela McuJoinsAndLeaves'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: McuJoinsAndLeaves table
ms:assetid: 4e073366-0b5d-45b4-a3f6-d63dd5fd9f25
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398316(v=OCS.15)
ms:contentKeyID: 48184115
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5a936b6d6d9b371238873909646a146b94f659c4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827575"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mcujoinsandleaves-table-in-lync-server-2013"></a>Tabela McuJoinsAndLeaves no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-28_

Cada registro desta tabela contém detalhes da chamada sobre uma combinação de um servidor de ingresso ou de saída e conferência do usuário. Por exemplo, se um usuário ingressar em uma conferência que inclui a conferência da Web e os elementos de áudio/vídeo, um registro seria criado para a sua associação de Webconferência do usuário e outro registro será criado para a reunião de conferência de áudio/vídeo do usuário.


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
<td><p>Número de identificação para identificar a instância de conferência. Usado em conjunto com <strong></strong> a identificação_da_sessãotime para identificar exclusivamente uma instância de conferência. Consulte a <a href="lync-server-2013-conferences-table.md">tabela conferências no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ID</strong></p></td>
<td><p>int</p></td>
<td><p>Primário, estrangeiro</p></td>
<td><p>Número exclusivo que identifica esse usuário. Consulte a <a href="lync-server-2013-users-table.md">tabela usuários no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="even">
<td><p><strong>McuUserInstance</strong></p></td>
<td><p>int</p></td>
<td><p>Primária</p></td>
<td><p>Se um usuário estiver conectado em vários computadores ou dispositivos de uma vez, o McuUserInstance identifica exclusivamente a combinação de usuário/dispositivo.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsFromPstn</strong></p></td>
<td><p>bit</p></td>
<td><p> </p></td>
<td><p>Se o usuário está ingressando de uma PSTN ou não.</p></td>
</tr>
<tr class="even">
<td><p><strong>McuId</strong></p></td>
<td><p>int</p></td>
<td><p>Primário, estrangeiro</p></td>
<td><p>Número exclusivo que identifica esse servidor de conferência. Consulte a <a href="lync-server-2013-mcus-table.md">tabela MCUs no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DialogSessionIdTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Exterior</p></td>
<td><p>Tempo de solicitação de sessão. Usado em conjunto com o <strong>SessionIdSeq</strong> para identificar exclusivamente uma sessão. Consulte a <a href="lync-server-2013-dialogs-table.md">tabela de diálogos no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="even">
<td><p><strong>DialogSessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Exterior</p></td>
<td><p>Número de identificação para identificar a sessão. Usado em conjunto com <strong></strong> a identificação_da_sessãotime para identificar exclusivamente uma sessão. Consulte a <a href="lync-server-2013-dialogs-table.md">tabela de diálogos no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Userjointime</strong></p></td>
<td><p>datetime</p></td>
<td><p> </p></td>
<td><p>A hora em que este usuário entra neste servidor de conferência.</p></td>
</tr>
<tr class="even">
<td><p><strong>Userleavetime</strong></p></td>
<td><p>datetime</p></td>
<td><p> </p></td>
<td><p>O horário em que este usuário sai deste servidor de conferência.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ClientVerId</strong></p></td>
<td><p>int</p></td>
<td><p>Exterior</p></td>
<td><p>Identificador que especifica o número da versão do software cliente usado na conferência. Consulte a <a href="lync-server-2013-clientversions-table.md">tabela ClientVersions no Lync Server 2013</a> para obter mais informações.</p>
<p>Este campo foi apresentado no Microsoft Lync Server 2013.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

