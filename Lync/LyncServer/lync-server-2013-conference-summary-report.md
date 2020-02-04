---
title: 'Lync Server 2013: relatório de resumo da conferência'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conference Summary Report
ms:assetid: 62f54812-5700-45a3-8526-8f58b0f77fbc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558656(v=OCS.15)
ms:contentKeyID: 48184299
ms.date: 09/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 68858d56c47953a99928a59e5f83485ba9d305cb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756995"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conference-summary-report-in-lync-server-2013"></a>Relatório de Resumo de conferências no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2014-09-03_

O Relatório de Resumo de Conferências traz uma visão geral de suas sessões de conferência online. Geralmente, uma conferência envolve mais de 2 usuários e requer o uso de serviços de conferência do Microsoft Lync Server 2013. Por comparação, uma sessão ponto a ponto geralmente envolve apenas 2 usuários e não requer o uso de serviços de conferência do Lync Server. As atividades ponto a ponto são relatadas no [relatório de Resumo de atividades ponto a ponto no Lync Server 2013](lync-server-2013-peer-to-peer-activity-summary-report.md).

O relatório de Resumo de conferências não só informa quantas conferências foram mantidas durante um determinado período (por hora, diária, semanal, mensal), mas também informa o número total de pessoas que participaram de todas as conferências e o número total de conferências exclusivas organizadores.

Um organizador "exclusivo" é qualquer pessoa que agenda pelo menos uma conferência. Por exemplo, se Pilar Ackerman agendar uma conferência, ela será contabilizada como um organizador exclusivo. Se Ken Myer agendar 148 conferências, ele também será contabilizado como um único organizador exclusivo. Por exemplo, a tabela a seguir mostra 8 conferências agendadas, mas apenas três organizadores exclusivos (Ken Myer, pilar Alverca e David ahs).


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Organizador da conferência</th>
<th>Data da conferência</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Ken Myer</p></td>
<td><p>7/7/2012 10:00 AM</p></td>
</tr>
<tr class="even">
<td><p>David Ahs</p></td>
<td><p>7/7/2012 10:00 AM</p></td>
</tr>
<tr class="odd">
<td><p>Ken Myer</p></td>
<td><p>7/7/2012 11:00 AM</p></td>
</tr>
<tr class="even">
<td><p>Pilar Ackerman</p></td>
<td><p>7/7/2012 11:00 AM</p></td>
</tr>
<tr class="odd">
<td><p>Ken Myer</p></td>
<td><p>7/7/2012 1:00 PM</p></td>
</tr>
<tr class="even">
<td><p>Pilar Ackerman</p></td>
<td><p>7/7/2012 2:00 PM</p></td>
</tr>
<tr class="odd">
<td><p>Ken Myer</p></td>
<td><p>7/2/2012 10:00 AM</p></td>
</tr>
<tr class="even">
<td><p>Pilar Ackerman</p></td>
<td><p>7/2/2012 10:00 AM</p></td>
</tr>
</tbody>
</table>


O Relatório de Resumo de Conferências também indica quantas conferências incluíram áudio e/ou vídeo.

<div>

## <a name="accessing-the-conference-summary-report"></a>Acessando o Relatório de Resumo de Conferências

O Relatório de Resumo de Conferências pode ser acessado na home page Relatórios de Monitoramento. Você pode filtrar pelo Relatório de Atividade de Conferência clicando em uma das métricas a seguir:

  - Total de conferências

  - Total de participantes

</div>

<div>

## <a name="making-the-best-use-of-the-conference-summary-report"></a>Usando o Relatório de Resumo de Conferências da melhor maneira possível

Os valores totais para a maioria das métricas usadas no relatório de Resumo de conferências podem ser encontrados na parte inferior do relatório; Role para baixo para ver valores como o número total de conferências mantidas durante o período de tempo especificado e o número total de pessoas que participaram dessas conferências. Uma métrica que não está totalizada na parte inferior do relatório é o total de organizadores de conferências exclusivos. Por que não? Aqui está um motivo. Suponha que você esteja olhando para o valor de dados de um mês. No dia 1, você tinha 34 organizadores de conferência exclusivos; no dia 2, você tinha 27 organizadores de conferências exclusivos. Isso significa que você tinha 61 organizadores de conferência exclusivos para estes dois dias? Não necessariamente. Afinal, todas as 27 pessoas que organizaram conferências no dia 2 podem estar entre as pessoas do 34 que organizaram conferências no dia 1. Por exemplo, neste relatório simples, observe que Ken Myer e pilar Alverca conferências agendadas no 7/7/2012 e no 7/2/2012:


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Organizador da conferência</th>
<th>Data da conferência</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Ken Myer</p></td>
<td><p>7/7/2012 10:00 AM</p></td>
</tr>
<tr class="even">
<td><p>David Ahs</p></td>
<td><p>7/7/2012 10:00 AM</p></td>
</tr>
<tr class="odd">
<td><p>Ken Myer</p></td>
<td><p>7/7/2012 11:00 AM</p></td>
</tr>
<tr class="even">
<td><p>Pilar Ackerman</p></td>
<td><p>7/7/2012 11:00 AM</p></td>
</tr>
<tr class="odd">
<td><p>Ken Myer</p></td>
<td><p>7/7/2012 1:00 PM</p></td>
</tr>
<tr class="even">
<td><p>Pilar Ackerman</p></td>
<td><p>7/7/2012 2:00 PM</p></td>
</tr>
<tr class="odd">
<td><p>Ken Myer</p></td>
<td><p>7/2/2012 10:00 AM</p></td>
</tr>
<tr class="even">
<td><p>Pilar Ackerman</p></td>
<td><p>7/2/2012 10:00 AM</p></td>
</tr>
</tbody>
</table>


Para ter uma ideia melhor do número total de usuários exclusivos que organizaram conferências, altere o intervalo de tempo. Por exemplo, exiba os dados por mês e não por dia.

</div>

<div>

## <a name="filters"></a>Filtros

Os filtros fornecem uma maneira de retornar um conjunto de dados mais direcionado ou de exibir os dados retornados de diferentes maneiras. Por exemplo, o Relatório de Resumo de Conferências permite que você escolha como os dados devem ser agrupados. Nesse caso, conferências agrupadas por hora, dia, semana ou mês.

A tabela a seguir lista os filtros que você pode usar com o Relatório de Resumo de Conferências.

### <a name="conference-summary-report-filters"></a>Filtros do Relatório de Resumo de Conferências

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
<p>Se as datas de início e término excederem o número máximo de valores permitidos para o intervalo selecionado, apenas o número máximo de valores (começando pela data de início) será exibido. Por exemplo, se você selecionar o intervalo diário com uma data de início de 7/7/2012 e uma data de término de 2/28/2012, os dados serão exibidos para os dias 8/7/2012 12:00 AM a 9/7/2012 12:00 AM (ou seja, um total de 31 dias da importância dos dados).</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>Métricas

A tabela a seguir as informações fornecidas pelo Relatório de Resumo de Conferências.

### <a name="conference-summary-report-metrics"></a>Métricas do Relatório de Resumo de Conferências

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
<td><p>Indica o intervalo de tempo selecionado na barra de ferramentas de filtro. Quando aplicável, é possível clicar em determinado intervalo de tempo para exibir informações detalhadas sobre ele. Por exemplo, se você estiver usando o intervalo diário e clicar em 7/7/2012, verá um detalhamento por hora da atividade de registro do usuário para essa data.</p></td>
</tr>
<tr class="even">
<td><p><strong>Conferências totais</strong></p></td>
<td><p>Não</p></td>
<td><p>Número total de conferências (independentemente do tipo de conferência) que foram mantidas. Quando você clica nesse item, o relatório mostra o Relatório de Resumo de Conferências para o período de tempo selecionado.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Total de participantes</strong></p></td>
<td><p>Não</p></td>
<td><p>Número total de pessoas que participaram nas conferências. Quando você clica nesse item, o relatório mostra o Relatório de Resumo de Conferências para o período de tempo selecionado.</p></td>
</tr>
<tr class="even">
<td><p><strong>Média de participantes por conferência</strong></p></td>
<td><p>Não</p></td>
<td><p>Número médio de pessoas que participaram de uma determinada conferência. É determinado dividindo o total de conferências pelo total de participantes.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Total de conferências A/V</strong></p></td>
<td><p>Não</p></td>
<td><p>Número total de conferências com áudio ou vídeo.</p></td>
</tr>
<tr class="even">
<td><p><strong>Total de minutos de conferências de A/V</strong></p></td>
<td><p>Não</p></td>
<td><p>Número total de minutos para a conferência de áudio/vídeo.</p>
<p>A métrica de minutos total de conferência a/V resume todos os tipos de áudio/conferência Visual, incluindo: conferências A/V; Conferências de mensagens instantâneas; conferências de compartilhamento de aplicativos; conferências de dados; e conferências PSTN.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Total de minutos de participantes de conferências de A/V</strong></p></td>
<td><p>Não</p></td>
<td><p>Número total de minutos do participante na conferência de áudio/vídeo. Por exemplo, suponha que um usuário gaste cinco minutos em uma conferência de áudio/vídeo e um segundo usuário gaste três minutos nessa mesma conferência. O que soma um total de oito minutos de participantes: cinco minutos mais três minutos.</p></td>
</tr>
<tr class="even">
<td><p><strong>Média de minutos da conferência A/V</strong></p></td>
<td><p>Não</p></td>
<td><p>Número médio de minutos por conferência de áudio/vídeo.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Número total de organizadores exclusivos de conferências</strong></p></td>
<td><p>Não</p></td>
<td><p>Número total de usuários que organizaram pelo menos uma conferência. Os usuários que organizaram mais de uma conferência são contados como um organizador exclusivo, assim como os usuários que só organizaram uma única conferência.</p></td>
</tr>
<tr class="even">
<td><p><strong>Total de mensagens de conferência</strong></p></td>
<td><p>Não</p></td>
<td><p>Número total de mensagens instantâneas enviadas durante as conferências.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

