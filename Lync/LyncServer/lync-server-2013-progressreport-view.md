---
title: 'Lync Server 2013: modo de exibição ProgressReport'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ProgressReport view
ms:assetid: b49f3fc7-0e2f-498f-8505-aaaf54e435f9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721857(v=OCS.15)
ms:contentKeyID: 49733790
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4fa8d73981490503b26b77b79be6f42aab77703e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747235"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="progressreport-view-in-lync-server-2013"></a>Exibição ProgressReport no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-01_

A exibição ProgressReport armazena informações sobre sessões concluídas. Os relatórios de progresso serão escritos apenas para chamadas e sessões que o Lync Server 2013 determina que podem ser úteis para fins de diagnóstico. Este modo de exibição foi apresentado no Microsoft Lync Server 2013.

<div>


> [!NOTE]  
> Os campos ErrorTime, ErrorReportSeq e ProgressReportSeq não se referem necessariamente a erros, mas a mensagens que indicam o status de chamadas ou mensagens.



</div>


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
<td><p><strong>ProgressReportSeq</strong></p></td>
<td><p>int</p></td>
<td><p>ID para identificar o relatório de progresso. Usado para distinguir relatórios de progresso do mesmo relatório de erro.</p></td>
</tr>
<tr class="even">
<td><p><strong>MsDiagId</strong></p></td>
<td><p>int</p></td>
<td><p>ID de diagnóstico do relatório de erros.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Origem</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Nome do servidor que originou o erro (se o relatório foi enviado a partir de um componente de servidor).</p></td>
</tr>
<tr class="even">
<td><p><strong>Aplicativo</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Nome do aplicativo que originou o erro (se o relatório foi enviado a partir de um componente de servidor).</p></td>
</tr>
<tr class="odd">
<td><p><strong>Telemetria</strong></p></td>
<td><p>identificador</p></td>
<td><p>Identificador exclusivo que correlaciona as informações de tempo de junção para os diferentes componentes envolvidos em uma conferência.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSetupTime</strong></p></td>
<td><p>int</p></td>
<td><p>Tempo (em milissegundos) necessário para um componente específico entrar em uma conferência.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MsDiagHeader</strong></p></td>
<td><p>varchar (max)</p></td>
<td><p>Informações adicionais sobre o erro.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

