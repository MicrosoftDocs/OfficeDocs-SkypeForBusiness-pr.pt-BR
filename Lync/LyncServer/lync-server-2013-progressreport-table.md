---
title: 'Lync Server 2013: Tabela ProgressReport'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ProgressReport table
ms:assetid: 38e5f060-5e9b-4185-87b2-7ef61c4bb75f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425864(v=OCS.15)
ms:contentKeyID: 48183847
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2e1cb7c8e764097af96981220ee74d481b379341
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724811"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="progressreport-table-in-lync-server-2013"></a>Tabela ProgressReport no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-28_

Os relatórios de progresso são baseados em dados carregados pelo cliente para o banco de dados após a conclusão de uma chamada ou sessão. Os relatórios de progresso serão escritos apenas para chamadas e sessões que o Lync Server 2013 determina que podem ser úteis para fins de diagnóstico.

Os campos ErrorTime, ErrorReportSeq e ProgressReportSeq não se referem necessariamente a erros, mas a mensagens que indicam o status de chamadas ou mensagens.


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
<td><p>Primário, estrangeiro</p></td>
<td><p>Data e hora do relatório de erro de progresso que contém este relatório de progresso. Consulte a <a href="lync-server-2013-errorreport-table.md">tabela errorreport no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="even">
<td><p><strong>ErrorID</strong></p></td>
<td><p>int</p></td>
<td><p>Primário, estrangeiro</p></td>
<td><p>Número de identificação usado em conjunto com ErrorTime, ProgressReportSeq para identificar exclusivamente um relatório de progresso. Consulte a <a href="lync-server-2013-errorreport-table.md">tabela errorreport no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ErrorReportSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Primário, estrangeiro</p></td>
<td><p>Número de identificação que identifica o relatório de erros. ErrorReporSeq é usado em conjunto com ErrorTime para identificar com exclusividade um relatório de erro. Consulte a <a href="lync-server-2013-errorreport-table.md">tabela errorreport no Lync Server 2013</a> para obter mais informações</p>
<p>Este campo foi apresentado no Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>ProgressReportSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Primária</p></td>
<td><p>Número de identificação para identificar o relatório de progresso. Usado em conjunto com ErrorTime e ErrorReportSeq para identificar com exclusividade um relatório de progresso.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MsDiagId</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>ID de diagnóstico do relatório de progresso.</p>
<p>Este campo foi apresentado no Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>SourceID</strong></p></td>
<td><p>int</p></td>
<td><p>Exterior</p></td>
<td><p>Servidor que enviou o relatório de erro (se o relatório foi enviado de um componente de servidor). Consulte a <a href="lync-server-2013-servers-table.md">tabela servidores no Lync Server 2013</a> para obter mais informações. Este campo foi apresentado no Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ApplicationId</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>O processo do Lync Server no qual o relatório se encontra. Consulte a tabela de aplicativos para obter mais informações.</p></td>
</tr>
<tr class="even">
<td><p><strong>Detalhe</strong></p></td>
<td><p>imagem</p></td>
<td></td>
<td><p>Detalhes do relatório de progresso armazenados em formato binário para economizar espaço. Esses dados podem ser convertidos em um formato de texto usando esta sintaxe:</p>
<p>Cast (Cast (detalhes como varbinary (max)) as varchar (max))</p></td>
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
<td><p>Tempo (em milissegundos) para um componente específico para ingressar em uma conferência.</p>
<p>Este campo foi apresentado no Microsoft Lync Server 2013.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

