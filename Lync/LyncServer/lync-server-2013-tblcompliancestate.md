---
title: 'Lync Server 2013: tblComplianceState'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblComplianceState
ms:assetid: ea82e56c-3cca-4d89-b4e6-6bcaeb1f2830
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615045(v=OCS.15)
ms:contentKeyID: 48185937
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fce70f05b317ac7467fd17306d6933c66087e5e6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844797"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblcompliancestate-in-lync-server-2013"></a>tblComplianceState no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-06-28_

tblComplianceState contém informações de estado de conformidade em todo o pool.

### <a name="columns"></a>Colunas

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Coluna</th>
<th>Tipo</th>
<th>Descrição</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>lastProcessedEntryID</p></td>
<td><p>bigint, e não nulo</p></td>
<td><p>ID do evento de conformidade processado mais recente.</p></td>
</tr>
<tr class="even">
<td><p>activeServerID</p></td>
<td><p>int, não nulo</p></td>
<td><p>ID do servidor de conformidade que mantém o bloqueio exclusivo no banco de dados ou-1 se nenhum.</p></td>
</tr>
<tr class="odd">
<td><p>lockExpirationTime</p></td>
<td><p>datetime2, não nulo</p></td>
<td><p>Bloquear o tempo de expiração (se activeServerID não for-1).</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

