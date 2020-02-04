---
title: 'Lync Server 2013: Tabela Conferences'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conferences table
ms:assetid: c3da6271-b3c6-4898-894f-10456ec794d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412964(v=OCS.15)
ms:contentKeyID: 48185340
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0c5464d3161a52a31fddb1322c82181d6e7a97fe
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756395"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferences-table-in-lync-server-2013"></a>Tabela Conferences no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-28_

Cada registro desta tabela contém detalhes da chamada sobre uma conferência.


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
<td><p>Primária</p></td>
<td><p>Hora em que a solicitação de conferência foi capturada pelo agente de CDR. Usado apenas como uma chave primária para identificar uma instância de conferência de forma exclusiva.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Primária</p></td>
<td><p>Número de identificação para identificar a sessão. Usado em conjunto com a <strong>identificação_da_sessãotime</strong> para identificar exclusivamente uma instância de conferência. *</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConferenceUriId</strong></p></td>
<td><p>int</p></td>
<td><p>Exterior</p></td>
<td><p>URL da conferência. Consulte a <a href="lync-server-2013-conferenceuris-table.md">tabela ConferenceUris no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="even">
<td><p><strong>ConfInstance</strong></p></td>
<td><p>identificador</p></td>
<td><p> </p></td>
<td><p>Útil para conferências recorrentes; cada instância de uma conferência recorrente tem o mesmo <strong>ConferenceUri</strong>, mas terá um <strong>ConfInstance</strong>diferente.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConferenceStartTime</strong></p></td>
<td><p>datetime</p></td>
<td><p> </p></td>
<td><p>Hora de início da conferência.</p></td>
</tr>
<tr class="even">
<td><p><strong>ConferenceEndTime</strong></p></td>
<td><p>datetime</p></td>
<td><p> </p></td>
<td><p>Hora de início da conferência.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Poolid</strong></p></td>
<td><p>int</p></td>
<td><p>Exterior</p></td>
<td><p>Número de identificação para identificar o pool no qual a conferência foi capturada. Consulte a <a href="lync-server-2013-pools-table.md">tabela de grupos no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="even">
<td><p><strong>OrganizerId</strong></p></td>
<td><p>Núm</p></td>
<td><p>Exterior</p></td>
<td><p>Número de identificação para identificar o URI do organizador dessa conferência. Consulte a <a href="lync-server-2013-users-table.md">tabela usuários no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Sinalizador</strong></p></td>
<td><p>smallint</p></td>
<td></td>
<td><p>Uma máscara de bits que contém atributos de conferência. Os valores possíveis são:</p>
<ul>
<li><p>0X01</p></li>
<li><p>Sintética</p></li>
<li><p>Transação</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Processe</strong></p></td>
<td><p>bit</p></td>
<td></td>
<td><p>Campo interno usado pelo serviço de monitoramento.</p>
<p>Este campo foi apresentado no Microsoft Lync Server 2013.</p></td>
</tr>
</tbody>
</table>


\*Para a maioria das sessões, o SessionIdSeq terá o valor de 1. Se duas sessões começarem exatamente ao mesmo tempo, o SessionIdSeq de uma será 1 e, para a outra, será 2 e assim por diante.

</div>

<span> </span>

</div>

</div>

</div>

