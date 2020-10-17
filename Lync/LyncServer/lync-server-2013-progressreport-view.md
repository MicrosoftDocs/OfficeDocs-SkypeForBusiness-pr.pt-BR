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
ms.openlocfilehash: 492f7f5e34631de5ff843a00dd3fdf75b6f32f00
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48513218"
---
# <a name="progressreport-view-in-lync-server-2013"></a>Exibição ProgressReport no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-01_

A exibição ProgressReport armazena informações sobre sessões concluídas. Os relatórios de progresso será gravados somente para chamadas e sessões que o Lync Server 2013 determina como úteis para diagnósticos. Este modo de exibição foi introduzido no Microsoft Lync Server 2013.

<div>


> [!NOTE]  
> Os campos ErrorTime, ErrorReportSeq e ProgressReportSeq não se referem necessariamente aos erros, mas a mensagens que indicam o status das chamadas ou mensagens.



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
<td><p>Hora do erro. Usada com o ErrorReportSeq para identificar um erro.</p></td>
</tr>
<tr class="even">
<td><p><strong>ErrorReportSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Um número de ID para identificar o erro. Usado com ErrorTime para identificar um erro.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ProgressReportSeq</strong></p></td>
<td><p>int</p></td>
<td><p>ID para identificar o relatórios de progresso. Usado para distinguir relatórios de progresso do mesmo relatório de erro.</p></td>
</tr>
<tr class="even">
<td><p><strong>MsDiagId</strong></p></td>
<td><p>int</p></td>
<td><p>ID de diagnóstico do relatório de erro.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Fonte</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Nome do servidor que originou o erro (se o relatório foi enviado de um componente do servidor).</p></td>
</tr>
<tr class="even">
<td><p><strong>Aplicação</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Nome de um aplicativo que originou o erro (se o relatório foi enviado de um componente do servidor).</p></td>
</tr>
<tr class="odd">
<td><p><strong>Telemetria</strong></p></td>
<td><p>identificador</p></td>
<td><p>Identificador exclusivo correlacionando as informações da hora de ingresso dos diferentes componentes envolvidos em uma conferência.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSetupTime</strong></p></td>
<td><p>int</p></td>
<td><p>Tempo (em milissegundos) necessário para que um componentes específico ingresse em uma conferência.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MsDiagHeader</strong></p></td>
<td><p>varchar (max)</p></td>
<td><p>Informações de erro adicionais.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

