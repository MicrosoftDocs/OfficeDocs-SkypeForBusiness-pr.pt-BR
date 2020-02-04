---
title: 'Lync Server 2013: relatório de tempo de ingresso em conferência'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conference Join Time Report
ms:assetid: e64dc89a-25e4-4cb8-bcb1-51712e69ba5a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205344(v=OCS.15)
ms:contentKeyID: 48185686
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cce80d3c61e94752423c70de9827d41243da7119
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757005"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conference-join-time-report-in-lync-server-2013"></a>Relatório de tempo de ingresso em conferência no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2014-04-23_

O Resumo do Tempo de Ingresso em Conferência permite que você determine quanto tempo demora para que seus usuários ingressarem em uma conferência. O relatório mostra o tempo médio de ingresso (em milissegundos) e também oferece um detalhamento que permite que você saiba quantos usuários foram capazes de se juntar a uma conferência em 2 segundos ou menos, quantos usuários necessitaram de 2 a 5 segundos para ingressar em uma conferência, etc.

<div>

## <a name="accessing-the-conference-join-time-report"></a>Acessando o Relatório do Tempo de Ingresso em Conferência

O Relatório do Tempo de Ingresso em Conferência é acessado pela página inicial dos Relatórios de Monitoramento.

</div>

<div>

## <a name="filters"></a>Filtros

Os filtros oferecem uma forma de retornar um conjunto de dados mais direcionado ou exibir os dados devolvidos em formas diferentes. A tabela a seguir lista os filtros que você pode usar com os Relatórios do Tempo de Ingresso em Conferência.

### <a name="conference-join-time-report-filters"></a>Filtros de Relatório do Tempo de Ingresso em Conferência

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
<td><p><strong>Intervalo</strong></p></td>
<td><p>Intervalo de tempo. Selecione uma das seguintes opções:</p>
<ul>
<li><p>Por hora (é possível exibir no máximo 25 horas)</p></li>
<li><p>Diariamente (é possível exibir no máximo 31 dias)</p></li>
<li><p>Semanalmente (é possível exibir no máximo 12 semanas)</p></li>
<li><p>Mensalmente (é possível exibir no máximo 12 meses)</p></li>
</ul>
<p>Se as datas de início e término excederem o número máximo de valores permitidos para o intervalo selecionado, somente o número máximo de valores (a partir da data de início) será exibido. Por exemplo, se você selecionar o intervalo diário com uma data de início de 7/7/2012 e uma data de término de 2/28/2012, os dados serão exibidos para os dias 8/7/2012 12:00 AM a 9/7/2012 12:00 AM (ou seja, um total de 31 dias da importância dos dados).</p></td>
</tr>
<tr class="even">
<td><p><strong>Pool</strong></p></td>
<td><p>FQDN (Nome de domínio totalmente qualificado) do pool de Registradores Avançados ou Servidores de Borda. Você pode selecionar um pool individual ou clicar em <strong>[Tudo]</strong> para ver os dados de todos os pools. Essa lista suspensa é automaticamente preenchida para você com base nos registros no banco de dados.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Sessões de conferência</strong></p></td>
<td><p>Tipo de sessão. Os valores permitidos são:</p>
<ul>
<li><p>[Todos]</p></li>
<li><p>Sessões de Focus (Focus é o gerenciador central de políticas e estados para reuniões online e coordena todos os aspectos da conferência</p></li>
<li><p>Compartilhamento de aplicativos</p></li>
<li><p>Conferências de áudio/vídeo</p></li>
</ul>
<p>Caso selecione [Todos], o tempo total de ingresso em conferência será exibido no topo do relatório. Observe que esses totais são apenas para conferências que foram agendadas usando o Microsoft Exchange ou o Microsoft Outlook.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>Métricas

A tabela a seguir lista as informações fornecidas no Relatório de Tempo de Ingresso em Conferência.

### <a name="conference-join-time-report-metrics"></a>Métricas do Relatório de Tempo de Ingresso em Conferência

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Nome</th>
<th>Você pode classificar este item?</th>
<th>Descrição</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Data</strong></p>
<p>O título para essa métrica varia dependendo do Intervalo selecionado.</p></td>
<td><p>Não</p></td>
<td><p>Data e horário em que aconteceu a conferência.</p></td>
</tr>
<tr class="even">
<td><p><strong>Total de sessões</strong></p></td>
<td><p>Não</p></td>
<td><p>Número total de sessões, incluindo sessões bem-sucedidas, com falha (tanto falhas esperadas quanto inesperadas) e sessões não categorizadas.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Média (ms)</strong></p></td>
<td><p>Não</p></td>
<td><p>Média de tempo (em milissegundos) que demorou para que os participantes ingressassem na conferência.</p></td>
</tr>
<tr class="even">
<td><p><strong>Sessões &lt; com 2 segundos, volume</strong></p></td>
<td><p>Não</p></td>
<td><p>Número de participantes que conseguiram ingressar na conferência em menos de 2 segundos.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Sessões &lt; 2 segundos, porcentagem</strong></p></td>
<td><p>Não</p></td>
<td></td>
</tr>
<tr class="even">
<td><p><strong>Sessões de 2 a 5 segundos, Volume</strong></p></td>
<td><p>Não</p></td>
<td><p>Número de participantes que demoraram de 2 a 5 segundos para ingressar na conferência.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Sessões de 2 a 5 segundos, Porcentagem</strong></p></td>
<td><p>Não</p></td>
<td><p>Porcentagem do total de participantes da chamada que demoraram entre 2 a 5 segundos para ingressar na conferência.</p></td>
</tr>
<tr class="even">
<td><p><strong>Sessões de 5 a 10 segundos, Volume</strong></p></td>
<td><p>Não</p></td>
<td><p>Número de participantes que demoraram entre 5 a 10 segundos para ingressar na conferência.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Sessões de 5 a 10 segundos, Porcentagem</strong></p></td>
<td><p>Não</p></td>
<td><p>Porcentagem do total de participantes de chamadas que demoraram entre 5 a 10 segundos para ingressar na conferência.</p></td>
</tr>
<tr class="even">
<td><p><strong>Sessões &gt; de 10 segundos, volume</strong></p></td>
<td><p>Não</p></td>
<td><p>Número de participantes que precisaram de mais de 10 segundos para ingressar na conferência.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Sessões &gt; de 10 segundos, porcentagem</strong></p></td>
<td><p>Não</p></td>
<td><p>Porcentagem do total de participantes de chamadas que precisaram de mais de 10 segundos para ingressar na conferência.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

