---
title: 'Lync Server 2013: relatório de diagnóstico de conferência'
description: 'Lync Server 2013: relatório de diagnóstico de conferência.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conference Diagnostic Report
ms:assetid: e9edc23c-8ce8-4ab8-8786-9d22e1e51e14
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615042(v=OCS.15)
ms:contentKeyID: 48185901
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9d3ef3c78bc2145d907d5a40e1aed95a2f4cb4c4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577637"
---
# <a name="conference-diagnostic-report-in-lync-server-2013"></a>Relatório de diagnóstico de conferência no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-22_

O Relatório de Diagnóstico de Conferência oferece informações sobre êxito e falha de todas as sessões de conferência. Observe que o Microsoft Lync Server distingue entre tipos diferentes de falha:

  - **Falha esperada**. Uma falha esperada normalmente é uma falha apenas no sentido mais técnico. Por exemplo, suponha que alguém inicie uma conferência mas desligue antes que alguém possa ingressar. Tecnicamente, é uma falha: a conferência foi iniciadas mas não concluída. No entanto, essa é uma falha que você poderia esperar que acontecesse: se o organizador cancela a conferência antes que alguém possa ingressar, você não esperaria que essa conferência fosse concluída.

  - **Falha inesperada**. Uma falha inesperada é exatamente o que o nome diz: um erro que, baseado nas circunstâncias, você não esperaria que ocorrese. Por exemplo, suponha que uma conferência não tenha acontecido porque a política de reunião do organizador não pôde ser recuperada. Isso é um erro inesperado: afinal, sempre deve ser possível recuperar a política de reunião de um usuário.

Obseve que a soma das métricas de Êxitos, Falhas esperadas e Falhas inesperadas podem não resultar na métrica de Total de sessões. Por exemplo, você pode ver os seguines valores no Relatório:


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Sucessos</th>
<th>Falhas esperadas</th>
<th>Falhas inesperadas</th>
<th>Total de sessões</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>2024</p></td>
<td><p>469</p></td>
<td><p>16 </p></td>
<td><p>2521</p></td>
</tr>
</tbody>
</table>


Se somar 2024 + 469 + 16 você obtém um total de 2.509 sessões, e no entanto a coluna de Total de sessões mostra um total de 2.521 sessões. As 12 sessões "faltando" são sessões que o sistema não foi capaz de categorizar como êxito ou falha. Isso ocorrerá, às vezes, quando um produto de terceiros introduz um novo código de diagnóstico que não é familiar ao Monitoring Server. Quando isso acontece, chamadas feitas usando o produto, e os relatórios sobre o código de diagnóstico nem sempre podem ser categorizados como Êxitos, Falhas esperadas ou Falhas inesperadas.

<div>

## <a name="accessing-the-conference-diagnostic-report"></a>Acessando o Relatório de Diagnóstico de Conferência

O Relatório de Diagnóstico de Conferência é acessado a partir da página inicial de Relatórios de Monitoramento. Você pode acessar o [relatório de distribuição de falhas no Lync Server 2013](lync-server-2013-failure-distribution-report.md) clicando em uma das seguintes métricas:

  - Volume de falhas inesperadas

  - Volume de falhas esperadas

</div>

<div>

## <a name="making-the-best-use-of-the-conference-diagnostic-report"></a>Usando o Relatório de Diagnóstico de Conferência da melhor maneira possível

O Relatório de Diagnóstico de Conferência inclui uma série de gráficos. Cada uma das colunas exibidas no gráfico é, na verdade, um hiperlink. Se clicar em uma coluna, você fará uma busca detalhada no [relatório de distribuição de falhas no Lync Server 2013](lync-server-2013-failure-distribution-report.md) para esse período de tempo e esse tipo de conferência.

</div>

<div>

## <a name="filters"></a>Filtros

Os filtros fornecem uma maneira de retornar um conjunto de dados mais direcionado ou de exibir os dados retornados de maneiras diferentes. Por exemplo, o Relatório de Diagnóstico de Conferência permite que você filtre coisas como o tipo de conferência que está sendo conduzida (por exemplo, uma conferência baseada em Foco) ou pelo Servidor de Borda usado na conferência. Também é possível escolher como os dados devem ser agrupados. Nesse caso, as conferências são agrupadas por hora, dia, semana ou mês.

A tabela a seguir lista os filtros que podem ser usados com o Relatório de Diagnóstico de Conferência.

### <a name="conference-diagnostic-report-filters"></a>Filtros do Relatório de Diagnóstico de Conferência

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
<td><p>FQDN (Nome de domínio totalmente qualificado) do pool de Registradores ou Servidor de Borda. Você pode selecionar um pool individual ou clicar em <strong>[Tudo]</strong> para ver os dados de todos os pools. Essa lista suspensa é automaticamente preenchida para você com base nos registros no banco de dados.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Sessões de conferência</strong></p></td>
<td><p>Indica o tipo de sessão de conferência. Selecione uma das seguintes opções:</p>
<ul>
<li><p>Todos os</p></li>
<li><p>Sessões de foco</p></li>
<li><p>Todas as sessões MCU</p></li>
<li><p>Conferência de IM</p></li>
<li><p>Compartilhamento de aplicativos</p></li>
<li><p>Conferências A/V</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>Métrica

A tabela a seguir lista as informações fornecidas no Relatório de Diagnóstico de Conferência para cada tipo de sessão de conferência.

### <a name="conference-diagnostic-report-metrics"></a>Métricas do Relatório de Diagnóstico de Conferência

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
<td><p><strong>Volume de sucesso</strong></p></td>
<td><p>Não</p></td>
<td><p>Número total de conferências bem-sucedidas.</p></td>
</tr>
<tr class="even">
<td><p><strong>Porcentagem de sucesso</strong></p></td>
<td><p>Não</p></td>
<td><p>Percentual de conferências concluídas com problemas consideráveis. Calculado dividindo o volume de Sucesso pelo Total de sessões.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Volume de falha esperado</strong></p></td>
<td><p>Não</p></td>
<td><p>Número total de conferências onde uma &quot; falha esperada &quot; ocorreu.</p>
<p>Uma falha esperada é quando se sabe que a falha ocorrerá. Por exemplo, se um usuário tiver definido seu status como Não perturbe, é esperado que qualquer chamada para esse usuário falhe.</p></td>
</tr>
<tr class="even">
<td><p><strong>Percentual de falha esperada</strong></p></td>
<td><p>Não</p></td>
<td><p>Percentual de conferências que enfrentaram um erro esperado. Calculado pela divisão do Volume de falha esperado pelo Total de sessões.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Volume de falha esperado</strong></p></td>
<td><p>Não</p></td>
<td><p>Número total de conferências onde uma &quot; falha inesperada &quot; ocorreu.</p>
<p>Uma falha inesperada é uma falha que ocorre no que aparenta ser um sistema íntegro. Por exemplo, uma chamada não deve ser encerrada se o chamador for colocado em espera. Se isso ocorrer, isso seria sinalizado como uma falha inesperada.</p></td>
</tr>
<tr class="even">
<td><p><strong>Percentual de falha inesperada</strong></p></td>
<td><p>Não</p></td>
<td><p>Percentual de conferências que enfrentaram um erro esperado. Calculado pela divisão do Volume de falha inesperado pelo Total de sessões.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Total de sessões</strong></p></td>
<td><p>Não</p></td>
<td><p>Número total de conferências, incluindo conferências bem-sucedidas, conferências com falha (falhas esperadas e inesperadas) e conferências não categorizadas.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

