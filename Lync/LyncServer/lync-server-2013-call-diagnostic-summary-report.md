---
title: 'Lync Server 2013: relatório de Resumo de diagnóstico de chamadas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call Diagnostic Summary Report
ms:assetid: 9091de56-13e6-440e-9353-f57c10c906fe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615016(v=OCS.15)
ms:contentKeyID: 48184789
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 112a21dbb131e0bd34729584b8fb58399b192f70
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044483"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-diagnostic-summary-report-in-lync-server-2013"></a>Relatório de Resumo de diagnóstico de chamadas no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-06-06_

O Relatório de Resumo de Diagnóstico de Chamadas fornece uma visão geral de sessões peer-to-peer e de conferências que falharam. O relatório mostra a taxa de falha geral para os dois tipos de sessão, e detalha as informações de falha por tipo de modalidade de sessão:

  - Mensagens instantâneas

  - Compartilhamento de aplicativos

  - Transferência de arquivo

  - Áudio

  - Vídeo

<div>

## <a name="accessing-the-call-diagnostic-summary-report"></a>Como acessar o Relatório de resumo de diagnóstico de chamadas

O Relatório de resumo de diagnóstico de chamadas é acessado a partir da página inicial dos Relatórios de Monitoramento. No relatório de Resumo de diagnóstico de chamadas, você pode acessar o [relatório de diagnóstico de atividades ponto a ponto no Lync Server 2013](lync-server-2013-peer-to-peer-activity-diagnostic-report.md) clicando na métrica de taxa de falha na seção Resumo de sessão ponto a ponto do relatório. Você também pode acessar o [relatório de diagnóstico de conferência no Lync Server 2013](lync-server-2013-conference-diagnostic-report.md) clicando em qualquer uma das seguintes métricas de conferência:

  - Taxa de falha de sessão geral

  - Taxa de falha de foco

  - Taxa de falha MCU

</div>

<div>

## <a name="making-the-best-use-of-the-call-diagnostic-summary-report"></a>Como usar melhor o Relatório de resumo de diagnóstico de chamadas

O relatório de Resumo de diagnóstico de chamada inclui gráficos que comparam taxas de falha para as várias modalidades usadas no Microsoft Lync Server 2013. Na verdade, as colunas nesses gráficos são hotlinks; por exemplo, se você clicar na coluna mensagens instantâneas para sessões ponto a ponto, fará uma busca detalhada em uma instância do relatório de [diagnóstico de atividades ponto a ponto no Lync Server 2013](lync-server-2013-peer-to-peer-activity-diagnostic-report.md), um relatório que fornece detalhes adicionais sobre todas as sessões de mensagens instantâneas incluídas no relatório de Resumo de diagnóstico de chamadas.

</div>

<div>

## <a name="filters"></a>Filtros

Filtros fornecem uma forma de retornar um conjunto de dados mais focado ou exibir os dados retornados de diferentes formas. Por exemplo, o Relatório de Resumo de Diagnóstico de Chamadas permite filtrar por informações como pool do Registrador Avançado ou Servidor de Borda usado na sessão. Você também pode escolher como os dados serão agrupados. Neste caso, as chamadas são agrupadas por hora, dia, semana ou mês.

A tabela a seguir lista os filtros que podem ser usados com o Relatório de Resumo de Diagnóstico de Chamadas.

### <a name="call-diagnostic-summary-report-filters"></a>Filtros do Relatório de Resumo de Diagnóstico de Chamadas

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
<p>As semanas sempre são de Domingo a Sábado.</p></td>
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
<td><p>Intervalo de tempo. Selecione uma das seguintes opções:</p>
<ul>
<li><p>Por hora (é possível exibir no máximo 25 horas)</p></li>
<li><p>Diariamente (é possível exibir no máximo 31 dias)</p></li>
<li><p>Semanalmente (é possível exibir no máximo 12 semanas)</p></li>
<li><p>Mensalmente (é possível exibir no máximo 12 meses)</p></li>
</ul>
<p>Se as datas de início e término excederem o número máximo de valores permitidos para o intervalo selecionado, somente o número máximo de valores (a partir da data de início) será exibido. Por exemplo, se você selecionar o intervalo Diariamente com a data de início 07.07.12 e uma data de término de 28.02.12, os dados serão exibidos para os dias 07.08.12 12:00 AM até 07.09.12 12:00 AM (ou seja, um total de 31 dias de dados).</p></td>
</tr>
<tr class="even">
<td><p><strong>Pool</strong></p></td>
<td><p>Nome de domínio totalmente qualificado (FQDN) do pool do Registrador Avançado ou Servidor de Borda. Você pode selecionar um pool individual ou clicar em <strong>[Todos]</strong> para exibir dados para todos os pools. Esta lista suspensa é preenchida automaticamente, com base nos registros do banco de dados.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-sessions"></a>Métricas para Sessões Ponto a Ponto

A tabela a seguir lista as informações fornecidas no Relatório de Resumo de Diagnóstico de Chamadas para sessões ponto a ponto (ou seja, sessões envolvendo somente dois participantes).

### <a name="metrics-for-peer-to-peer-sessions"></a>Métricas para sessões ponto a ponto

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
<td><p><strong>Sessões totais</strong></p></td>
<td><p>Não</p></td>
<td><p>Número total de sessões ponto a ponto conduzidas.</p></td>
</tr>
<tr class="even">
<td><p><strong>Taxa de falha</strong></p></td>
<td><p>Não</p></td>
<td><p>Percentual de sessões ponto a ponto que falharam. Ao clicar neste item, o relatório exibe o relatório de Diagnóstico de Atividades Ponto a Ponto, que mostra informações mais detalhadas sobre as sessões ponto a ponto com falha.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferencing-sessions"></a>Métricas para Sessões de Conferência

A tabela a seguir lista as informações fornecidas pelo Relatório de Diagnóstico de Chamadas para sessões de conferência (ou seja, sessões envolvendo três ou mais participantes).

### <a name="metrics-for-conferencing-sessions"></a>Métricas para sessões de conferência

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
<td><p><strong>Total de conferências</strong></p></td>
<td><p>Não</p></td>
<td><p>Número total de conferências conduzidas.</p></td>
</tr>
<tr class="even">
<td><p><strong>Sessões de conferência totais</strong></p></td>
<td><p>Não</p></td>
<td><p>Número total de sessões de conferência conduzidas.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Taxa de falha de sessão geral</strong></p></td>
<td><p>Não</p></td>
<td><p>Percentual de sessões de conferência totais que falharam.</p></td>
</tr>
<tr class="even">
<td><p><strong>Sessões de Foco</strong></p></td>
<td><p>Não</p></td>
<td><p>Número total de sessões de conferência baseadas em Foco que falharam.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Taxa de falha de Foco</strong></p></td>
<td><p>Não</p></td>
<td><p>Percentual de sessões de conferência baseadas em Foco que falharam.</p></td>
</tr>
<tr class="even">
<td><p><strong>Sessões MCU</strong></p></td>
<td><p>Não</p></td>
<td><p>Número total de conferências baseadas em servidor (anteriormente conhecidas como Unidade de Controle de Multipontos ou MCU) que falharam.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Taxa de falha de MCU</strong></p></td>
<td><p>Não</p></td>
<td><p>Percentual de conferências baseadas em servidor (anteriormente conhecidas como Unidade de Controle de Multipontos ou MCU) que falharam.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

