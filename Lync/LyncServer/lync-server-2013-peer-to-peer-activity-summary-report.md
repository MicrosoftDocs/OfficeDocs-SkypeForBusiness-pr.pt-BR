---
title: 'Lync Server 2013: relatório de Resumo de atividade ponto a ponto'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Peer-to-Peer Activity Summary Report
ms:assetid: e829a21e-9dfa-46ba-9b5b-077c175d6586
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615041(v=OCS.15)
ms:contentKeyID: 48185884
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 62bdd1203db471de770ed56cf6377d7a3c651649
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825384"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="peer-to-peer-activity-summary-report-in-lync-server-2013"></a>Relatório de Resumo de atividade ponto a ponto no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-21_

O Relatório de Resumo de Atividades Ponto a Ponto fornece uma visão geral de suas sessões de comunicação ponto a ponto. Uma sessão ponto a ponto geralmente envolve apenas dois usuários e não requer o uso dos serviços de conferência do Lync Server. Por comparação, uma conferência geralmente envolve mais de dois usuários e requer o uso de serviços de conferência do Microsoft Lync Server 2013. As atividades de conferência são relatadas no Relatório de Resumo de Conferências.

O Relatório de Resumo de Atividades Ponto a Ponto ajuda você a responder perguntas como as seguintes:

  - Quantas mensagens instantâneas ponto a ponto meus usuários enviam em um dia normal?

  - Algum dos meus usuários realmente aproveita os recursos de compartilhamento de aplicativos e transferência de arquivos do Lync Server?

  - Os usuários têm reclamado que a rede parece devagar em certos horários do dia. Quantos minutos são dedicados às sessões de áudio e vídeo durante esses períodos?

<div>

## <a name="accessing-the-peer-to-peer-activity-summary-report"></a>Acessando o Relatório de Resumo de Atividades Ponto a Ponto

O Relatório de Resumo de Atividades Ponto a Ponto é acessado na página inicial de Relatórios de Monitoramento. Você abre o [relatório de im ponto a ponto no Lync Server 2013](lync-server-2013-peer-to-peer-im-report.md) clicando em uma das seguintes métricas:

  - Total de sessões de mensagens instantâneas ponto a ponto

  - Total de mensagens instantâneas ponto a ponto

Da mesma forma, você pode abrir o Relatório de Vídeo e Voz Ponto a Ponto clicando em qualquer uma destas métricas:

  - Total de sessões de áudio ponto a ponto

  - Total de minutos de sessão de áudio ponto a ponto

  - Total de sessões de áudio ponto a ponto

  - Total de minutos de sessão de áudio ponto a ponto

</div>

<div>

## <a name="making-the-best-use-of-the-peer-to-peer-activity-summary-report"></a>Como usar o Relatório de Resumo de Atividades Ponto a Ponto da melhor maneira possível

No final do Relatório de Resumo de Atividades Ponto a Ponto, você encontrará os totais de métricas como Total de sessões de mensagens instantâneas ponto a ponto e Total de mensagens instantâneas ponto a ponto. Isso oferece um resumo rápido das informações detalhadas encontradas no corpo do relatório.

</div>

<div>

## <a name="filters"></a>Filtros

Os filtros fornecem uma maneira de retornar um conjunto de dados mais direcionado ou de exibir os dados retornados de maneiras diferentes. Por exemplo, o Relatório de Resumo de Atividades Ponto a Ponto permite que você escolha como os dados devem ser agrupados. Nesse caso, atividades agrupadas por hora, dia, semana ou mês.

A tabela a seguir lista os filtros que podem ser usados com o Relatório de Resumo de Atividades Ponto a Ponto.

### <a name="peer-to-peer-activity-summary-report-filters"></a>Filtros do Relatório de Resumo de Atividades Ponto a Ponto

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
<td><p>Data e hora de início do intervalo de tempo. Para ver os dados por hora, insira a data e hora de início desta forma:</p>
<p>7/17/12012 1:00 PM</p>
<p>Se você não inserir a hora de início, o relatório começará automaticamente à meia-noite do dia especificado. Para ver os dados por dia, insira somente a data:</p>
<p>7/17/12012</p>
<p>Para exibir por semana ou mês, insira uma data dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):</p>
<p>7/13/2012</p>
<p>As semanas sempre vão de domingo a sábado.</p></td>
</tr>
<tr class="even">
<td><p><strong>Até</strong></p></td>
<td><p>Data e hora final para o intervalo de tempo. Para exibir os dados por hora, insira a data e hora final como a seguir:</p>
<p>7/17/12012 1:00 PM</p>
<p>Se você não inserir a hora final, o relatório terminará automaticamente à meia-noite do dia especificado. Para ver os dados por dia, insira somente a data:</p>
<p>7/17/12012</p>
<p>Para exibir por semana ou mês, insira uma data dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):</p>
<p>7/13/2012</p>
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
<p>Se as datas de início e término excederem o número máximo de valores permitidos para o intervalo selecionado, somente o número máximo de valores (a partir da data de início) será exibido. Por exemplo, se você selecionar o intervalo diário com uma data de início de 7/17/12012 e uma data de término de 2/28/2012, os dados serão exibidos para os dias 8/7/12012 12:00 AM a 9/7/12012 12:00 AM (ou seja, um total de 31 dias da importância dos dados).</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>Métricas

A tabela a seguir lista as informações fornecidas no Relatório de Resumo de Atividades Ponto a Ponto.

### <a name="peer-to-peer-activity-summary-report-metrics"></a>Métricas do Relatório de Resumo de Atividades Ponto a Ponto

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
<td><p><strong>Por hora</strong></p>
<p><strong>Diário</strong></p>
<p><strong>Semanal</strong></p>
<p><strong>Mensal</strong></p></td>
<td><p>Não</p></td>
<td><p>Indica o intervalo de tempo selecionado na barra de ferramentas de filtro. Quando aplicável, é possível clicar em determinado intervalo de tempo para exibir informações detalhadas sobre ele. Por exemplo, se você estiver usando o intervalo diário e clicar em 7/17/12012, verá um detalhamento por hora da atividade de registro do usuário para essa data.</p></td>
</tr>
<tr class="even">
<td><p><strong>Total de sessões ponto a ponto</strong></p></td>
<td><p>Não</p></td>
<td><p>Número total de sessões ponto a ponto conduzidas, independentemente do tipo de sessão.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Total de sessões de mensagens instantâneas ponto a ponto</strong></p></td>
<td><p>Não</p></td>
<td><p>Número total de sessões de mensagens instantâneas (IM) ponto a ponto. Quando você clica nesse item, o relatório mostra o Relatório de Mensagens Instantâneas Ponto a Ponto para o período selecionado.</p></td>
</tr>
<tr class="even">
<td><p><strong>Total de mensagens instantâneas ponto a ponto</strong></p></td>
<td><p>Não</p></td>
<td><p>Número total de mensagens instantâneas enviadas em sessões ponto a ponto. Quando você clica nesse item, o relatório mostra o Relatório de Mensagens Instantâneas Ponto a Ponto para o período selecionado.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Total de sessões de áudio ponto a ponto</strong></p></td>
<td><p>Não</p></td>
<td><p>Número total de chamadas de áudio ponto a ponto. Quando você clica nesse campo, o relatório mostra o Relatório de Voz e Vídeo Ponto a Ponto para o período selecionado.</p></td>
</tr>
<tr class="even">
<td><p><strong>Total de minutos de sessão de áudio ponto a ponto</strong></p></td>
<td><p>Não</p></td>
<td><p>Tempo total gasto em sessões de áudio ponto a ponto. Quando você clica nesse item, o relatório mostra o Relatório de Vídeo e Voz Ponto a Ponto do período selecionado.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Média de minutos de sessão de áudio ponto a ponto</strong></p></td>
<td><p>Não</p></td>
<td><p>Tempo médio gasto em sessões de áudio ponto a ponto. Calculado dividindo o tempo total de sessão de áudio pelo número total de sessões de áudio.</p></td>
</tr>
<tr class="even">
<td><p><strong>Total de sessões de vídeo ponto a ponto</strong></p></td>
<td><p>Não</p></td>
<td><p>Número total de chamadas de vídeo ponto a ponto. Observe que as sessões de vídeo também contam como sessões de áudio: cada sessão de vídeo conta como uma sessão de vídeo e uma sessão de áudio. Quando você clica nesse item, o relatório mostra o Relatório de Vídeo e Voz Ponto a Ponto do período selecionado.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Total de minutos de sessão de vídeo ponto a ponto</strong></p></td>
<td><p>Não</p></td>
<td><p>Tempo total gasto em sessões de vídeo ponto a ponto. Quando você clica nesse item, o relatório mostra o Relatório de Vídeo e Voz Ponto a Ponto do período selecionado.</p></td>
</tr>
<tr class="even">
<td><p><strong>Média de minutos de sessão de vídeo ponto a ponto</strong></p></td>
<td><p>Não</p></td>
<td><p>Tempo médio gasto em sessões de vídeo ponto a ponto. Calculado dividindo o tempo total de sessão de vídeo pelo número total de sessões de áudio.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Total de sessões de transferência de arquivo ponto a ponto</strong></p></td>
<td><p>Não</p></td>
<td><p>Número total de sessões ponto a ponto que incluem transferências de arquivo.</p></td>
</tr>
<tr class="even">
<td><p><strong>Total de sessões de compartilhamento de arquivo ponto a ponto</strong></p></td>
<td><p>Não</p></td>
<td><p>Número total de sessões ponto a ponto que incluem compartilhamento de aplicativos.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

