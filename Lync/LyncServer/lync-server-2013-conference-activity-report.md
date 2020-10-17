---
title: 'Lync Server 2013: relatório de atividade de conferência'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conference Activity Report
ms:assetid: 22ddb509-af16-4fc8-9b98-6f58caa6f37e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558627(v=OCS.15)
ms:contentKeyID: 48183618
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fe99c67faa5cc9d0fadd2bdabd260c9d40091303
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526038"
---
# <a name="conference-activity-report-in-lync-server-2013"></a>Relatório de atividade de conferência no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-22_

O relatório de atividade de conferência facilita a resposta a perguntas como estas: quantas conferências estão sendo mantidas por dia e quando as conferências são mantidas? As informações, como esta, são úteis não apenas em seu próprio direito, mas também como uma ferramenta de solução de problemas. Por exemplo, suponha que os usuários estão reclamando que a rede parece ser especialmente lenta no meio do dia. Uma rápida visão geral dos relatórios de atividade de conferência pode sugerir uma possível razão: muito mais conferências estão sendo agendadas entre as horas de 10:00 AM e 2:00 PM em qualquer outro momento.

Se a rede lenta está causando problemas, é possível incentivar os usuários a reagendar algumas de suas conferências durante os horários menos pesados do dia.

<div>

## <a name="accessing-the-conference-activity-report"></a>Acessar o relatório de atividade de conferência

O relatório de atividade de conferência é acessado a partir do [relatório de Resumo de conferências no Lync Server 2013](lync-server-2013-conference-summary-report.md) clicando em uma das seguintes métricas:

  - Total de conferências

  - Total de participantes

</div>

<div>

## <a name="making-the-best-use-of-the-conference-activity-report"></a>Fazendo o melhor uso do relatório de atividade de conferência

Por padrão, o relatório de atividade de conferência mostra o número total de conferências para o período de tempo especificado (por exemplo, o número total de conferências por dia ou o número total de conferências por hora do dia). No entanto, você também pode optar por exibir o número total de participantes desse período de tempo ou o número total de minutos do participante. Para fazer isso, clique no botão Mostrar/ocultar parâmetros para exibir as opções de filtragem e selecione uma das seguintes opções na lista suspensa relatório por:

  - Contagem de participantes

  - Minutos do participante

  - Contagem de conferência

</div>

<div>

## <a name="filters"></a>Filtros

Os filtros fornecem uma maneira de retornar um conjunto de dados mais direcionadas ou para exibir os dados retornados de diferentes maneiras. A tabela a seguir lista os filtros que podem ser usados com o relatório atividade de conferência.

### <a name="conference-activity-report-filters"></a>Filtros de relatório de atividade de conferência

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Nome</th>
<th>Descrição</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>De</strong></p></td>
<td><p>Data/hora inicial para o intervalo de tempo. Para exibir os dados por hora, insira a data e hora inicial como a seguir:</p>
<p>7/7/2012 13:00 horas</p>
<p>Se você não inserir uma hora inicial, o relatório começa automaticamente as 12:00 AM no dia especificado. Para exibir os dados por dia, insira apenas a data:</p>
<p>7/7/2012</p>
<p>Para exibir por semana ou mês, insira uma data que está dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):</p>
<p>7/3/2012</p>
<p>As semanas são sempre de domingo a sábado.</p></td>
</tr>
<tr class="even">
<td><p><strong>To</strong></p></td>
<td><p>Data/hora final para o intervalo de tempo. Para exibir os dados por hora, insira a data e hora final como a seguir:</p>
<p>7/7/2012 13:00 horas</p>
<p>Se você não inserir uma hora final, o relatório termina automaticamente as 12:00 AM no dia especificado. Para exibir os dados por dia, insira apenas a data:</p>
<p>7/7/2012</p>
<p>Para exibir por semana ou mês, insira uma data que está dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):</p>
<p>7/3/2012</p>
<p>As semanas são sempre de domingo a sábado.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Intervalo</strong></p></td>
<td><p>Intervalo de tempo. Selecione qualquer um dos seguintes:</p>
<ul>
<li><p>Por hora (é possível exibir no máximo 25 horas)</p></li>
<li><p>Diariamente (é possível exibir no máximo 31 dias)</p></li>
<li><p>Semanalmente (é possível exibir no máximo 12 semanas)</p></li>
<li><p>Mensalmente (é possível exibir no máximo 12 meses)</p></li>
</ul>
<p>Se as datas de início e término excederem o número máximo de valores permitidos para o intervalo selecionado, somente o número máximo de valores (a partir da data de início) será exibido. Por exemplo, se você selecionar o intervalo Diariamente com data de início em 7/7/12 e data de término de 28/2/12, os dados serão exibidos do dia 7/8/12, às 12:00, até o dia 7/9/12, às 12:00 (ou seja, um total de 31 dias de dados).</p></td>
</tr>
<tr class="even">
<td><p><strong>Relatório por</strong></p></td>
<td><p>Indica os valores a serem usados no relatório. Você pode selecionar um dos seguintes:</p>
<ul>
<li><p>Contagem de participantes</p></li>
<li><p>Minutos do participante</p></li>
<li><p>Contagem de conferência</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferences-by-pool"></a>Métricas para conferências por pool

A tabela a seguir lista as informações no relatório de atividade de conferência para cada pool.

### <a name="metrics-for-conferences-by-pool"></a>Métricas para conferências por pool

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Nome</th>
<th>É possível classificar este item?</th>
<th>Descrição</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Pool</strong></p></td>
<td><p>Não</p></td>
<td><p>Nome do pool de registradores ou servidor de borda usado na conferência.</p></td>
</tr>
<tr class="even">
<td><p><strong>Data/Hora</strong></p></td>
<td><p>Não</p></td>
<td><p>Data e hora em que a conferência foi realizada.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Total</strong></p></td>
<td><p>Não</p></td>
<td><p>Contagem total de participantes, minutos totais de participantes ou contagem total de conferências.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferences-by-server-type"></a>Métricas para conferências por tipo de servidor

A tabela a seguir lista as informações no relatório de atividade de conferência para cada tipo de servidor.

### <a name="metrics-for-conferences-by-server-type"></a>Métricas para conferências por tipo de servidor

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Nome</th>
<th>É possível classificar este item?</th>
<th>Descrição</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Tipo de servidor de conferência</strong></p></td>
<td><p>Não</p></td>
<td><p>Tipo de servidor usado na conferência, geralmente um dos seguintes:</p>
<ul>
<li><p>Servidor de Webconferência</p></li>
<li><p>Servidor de conferência de IM</p></li>
<li><p>Servidor de conferência telefônica</p></li>
<li><p>Servidor de conferência AV</p></li>
<li><p>Compartilhamento de aplicativo</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Data/Hora</strong></p></td>
<td><p>Não</p></td>
<td><p>Data e hora em que a conferência foi realizada.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Total</strong></p></td>
<td><p>Não</p></td>
<td><p>Contagem total de participantes, minutos totais de participantes ou contagem total de conferências.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

