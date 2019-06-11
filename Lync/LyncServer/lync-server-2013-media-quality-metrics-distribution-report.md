---
title: 'Lync Server 2013: relatório de distribuição de métricas de qualidade de mídia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Media Quality Metrics Distribution Report
ms:assetid: d07996e6-b0a5-4ff8-9512-ab707762b4e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205262(v=OCS.15)
ms:contentKeyID: 48185409
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d1d814fd001f3510a7ae83e63746bdc1265932e4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827386"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="the-media-quality-metrics-distribution-report-in-lync-server-2013"></a>O relatório de distribuição de métricas de qualidade de mídia no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-06-06_

O Relatório de Distribuição da Métrica de Qualidade de Mídia permite ver um gráfico que mostra os valores de distribuição para a métrica Qualidade da Experiência, como tremulação ou perda de pacotes. Por exemplo, suponha que seus usuários fazem um total de 10 ligações telefônicas; essas 10 chamadas relatam os seguintes tempos de ida e volta:


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Número da chamada</th>
<th>Tempo de resposta (milissegundos)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1</p></td>
<td><p>50</p></td>
</tr>
<tr class="even">
<td><p>2</p></td>
<td><p>50</p></td>
</tr>
<tr class="odd">
<td><p>3</p></td>
<td><p>50</p></td>
</tr>
<tr class="even">
<td><p>4</p></td>
<td><p>50</p></td>
</tr>
<tr class="odd">
<td><p>5</p></td>
<td><p>50</p></td>
</tr>
<tr class="even">
<td><p>6</p></td>
<td><p>50</p></td>
</tr>
<tr class="odd">
<td><p>7</p></td>
<td><p>50</p></td>
</tr>
<tr class="even">
<td><p>08</p></td>
<td><p>4550</p></td>
</tr>
<tr class="odd">
<td><p>222</p></td>
<td><p>50</p></td>
</tr>
<tr class="even">
<td><p>254</p></td>
<td><p>50</p></td>
</tr>
</tbody>
</table>


A média dessas horas de ida e volta é de 500 milissegundos (5000 dividida por 10). 500 milissegundos é um tempo de ida e volta extremamente grande; Como resultado, você pode acreditar que tem um problema sério com o congestionamento da rede. (Geralmente, períodos de tempo de resposta longos são o resultado de redes sobrecarregadas).

Na realidade, claro, 90% das suas chamadas têm excelentes tempos de ida e volta; você teve uma única chamada ruim que distorceu os resultados gerais. Se você só olhar o tempo médio de ida e volta, você pode ir para uma conclusão muito errada.

O Relatório de Distribuição da Métrica de Qualidade de Mídia ajuda a evitar conclusões incorretas mostrando uma distribuição gráfica de uma métrica especificada (como o tempo de ida e volta). Estes gráficos ajudam a deixar claro que você teve nove chamadas muito boas e uma muito ruim. Você ainda pode desejar investigar melhor essa chamada. No entanto, o fato de 9 entre 10 chamadas terem sido muito boas sugere que não há motivo para fazer qualquer mudança radical em sua rede, pelo menos não neste momento.

<div>

## <a name="filters"></a>Filtros

Os filtros fornecem uma maneira de retornar um conjunto de dados mais direcionadas ou para exibir os dados retornados de diferentes maneiras. A tabela a seguir lista os filtros que você pode usar com o Relatório de Distribuição da Métrica de Qualidade de Mídia.

### <a name="media-quality-metrics-distribution-report-filters"></a>Filtros do Relatório de Distribuição da Métrica de Qualidade de Mídia

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
<td><p>Data/hora de início para o intervalo de tempo. Para ver os dados por horas, insira a data e hora de início conforme segue:</p>
<p>7/7/2012 1:00 PM</p>
<p>Se você não inserir a hora de início, o relatório começará automaticamente à meia-noite do dia especificado. Para ver os dados por dia, insira somente a data:</p>
<p>7/7/2012</p>
<p>Para exibir por semana ou mês, insira uma data dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):</p>
<p>7/3/2012</p>
<p>As semanas sempre vão de domingo a sábado.</p></td>
</tr>
<tr class="even">
<td><p><strong>Até</strong></p></td>
<td><p>Data/hora final de intervalo de tempo. Para ver os dados por horas, insira a data e hora final conforme segue:</p>
<p>7/7/2012 1:00 PM</p>
<p>Se você não inserir a hora final, o relatório terminará automaticamente à meia-noite do dia especificado. Para ver os dados por dia, insira somente a data:</p>
<p>7/7/2012</p>
<p>Para exibir por semana ou mês, insira uma data dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):</p>
<p>7/3/2012</p>
<p>As semanas sempre vão de domingo a sábado.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Mínimo no eixo x</strong></p></td>
<td><p>Menor valor para ser exibido no eixo X do gráfico.</p></td>
</tr>
<tr class="even">
<td><p><strong>Máximo no eixo x</strong></p></td>
<td><p>Maior valor para ser exibido no eixo X do gráfico.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Tipo de acesso</strong></p></td>
<td><p>Indica se um cliente estava conectado na rede interna ou na rede externa quando a chamada foi realizada. Selecione um dos seguintes:</p>
<ul>
<li><p>[Todos]</p></li>
<li><p>Interno</p></li>
<li><p>Externo</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>VPN</strong></p></td>
<td><p>Indica se um cliente externo estava usando uma conexão de rede privada virtual (VPN) quando a chamada foi realizada. Selecione um dos seguintes:</p>
<ul>
<li><p>[Todos]</p></li>
<li><p>VPN</p></li>
<li><p>Não VPN</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>Tipo de rede</strong></p></td>
<td><p>Indica o tipo de rede que o cliente estava conectado quando a chamada foi realizada. Selecione um dos seguintes:</p>
<ul>
<li><p>[Todos]</p></li>
<li><p>Com fio</p></li>
<li><p>Sem fio</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

