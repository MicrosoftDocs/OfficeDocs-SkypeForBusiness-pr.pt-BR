---
title: 'Lync Server 2013: relatório de Resumo de conferência PSTN'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: PSTN Conference Summary Report
ms:assetid: 8e2f0862-4dfa-4c2b-bf8d-ad71419f15d2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615014(v=OCS.15)
ms:contentKeyID: 48184764
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f8cd36f651a84b25f7e8163a8cfc40aff5162f90
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724791"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="pstn-conference-summary-report-in-lync-server-2013"></a>Relatório de Resumo de conferência PSTN no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-22_

No Microsoft Lync Server 2013, uma conferência PSTN é qualquer conferência na qual pelo menos um participante disca para a parte de áudio por meio de um telefone PSTN (rede telefônica pública comutada). (Um telefone PSTN é um "telefone fixo", um telefone celular ou qualquer outro telefone que não usa voz sobre IP.) Ainda que sejam chamadas de conferências PSTN nos relatórios de monitoramento, essas conferências talvez sejam mais conhecidas como conferências discadas.

O Relatório de resumo de conferência fornece informações sobre todas as conferências PSTN feitas em sua organização (isto é, todas as conferências que tenham pelo menos um usuário discado). O relatório contém informações sobre o número total de conferências PSTN, total de número de pessoas que participaram nessas conferências e, talvez, o mais importante, o número total de usuários discados (a métrica de Total de participantes PSTN).

<div>

## <a name="accessing-the-pstn-conference-summary-report"></a>Como acessar o Relatório de resumo de conferência PSTN

O Relatório de resumo de conferência PSTN pode ser acessado apenas da página inicial dos Relatórios de Monitoramento. Este relatório não está vinculado a nenhum outro. Observe que você não pode recuperar informações de chamadas detalhadas para uma conferência PSTN, em parte porque os pontos de extremidade individuais são responsáveis por enviar essas informações. Os telefones PSTN não são capazes de rastrear ou enviar informações de detalhes de chamada.

</div>

<div>

## <a name="making-the-best-use-of-the-pstn-conference-summary-report"></a>Como usar melhor o Relatório de resumo de conferência PSTN

Para determinar a porcentagem de todas as suas conferências que incluem usuários de discagem, compare o valor da métrica total de conferências PSTN com a métrica total de conferências encontradas no [relatório de Resumo de conferências no Lync Server 2013](lync-server-2013-conference-summary-report.md).

Se você não vir o número de conferências PSTN que esperava ver, saiba que a capacidade de organizar uma conferência que permita usuários discados depende da política de conferência que foi atribuída a um usuário: se poucos usuários tiverem permissão para hospedar conferências PSTN, você obviamente verá poucas conferências PSTN. Você pode verificar rapidamente quais políticas de conferência (se houver) permitem que os usuários agendem conferências PSTN executando o seguinte comando no Shell de gerenciamento do Lync Server:

    Get-CsConferencingPolicy | Select-Object Identity, EnableDialInConferencing

Serão retornados dados semelhantes a estes:

    Identity                                EnableDialInConferencing
    --------                                ------------------------
    Global                                                      True
    site:Redmond                                               False
    site:Dublin                                                False
    Tag:RedmondDialInUsers                                      True
    Tag:DublinDialInUsers                                       True

Serão retornados dados semelhantes a estes:

</div>

<div>

## <a name="filters"></a>Filtros

Os filtros oferecem uma forma de retornar um conjunto de dados mais direcionado ou exibir os dados devolvidos em formas diferentes. Por exemplo, o Relatório de Resumo de Conferências PSTN permite escolher como os dados devem ser agrupados. Neste caso, as conferências são agrupadas por hora, dia, semana ou mês.

A tabela a seguir lista os filtros que podem ser usados com o Relatório de Resumo de Conferências PSTN.

### <a name="pstn-conference-summary-report-filters"></a>Filtros do Relatório de Resumo de Conferências PSTN

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
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>Métricas

A tabela a seguir lista as informações no Relatório de Resumo de Conferências PSTN.

### <a name="pstn-conference-summary-report-metrics"></a>Métricas do Relatório de Resumo de Conferências PSTN

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
<td><p>Indica o intervalo de tempo selecionado. Quando aplicável, você pode clicar em um dado intervalo de tempo para exibir informações detalhadas para aquele intervalo. Por exemplo, se você estiver usando o intervalo diário e clicar em 7/7/2012, verá um detalhamento por hora da atividade de registro do usuário para essa data.</p></td>
</tr>
<tr class="even">
<td><p><strong>Total de conferências PSTN</strong></p></td>
<td><p>Não</p></td>
<td><p>Número total de conferências que permitiram acesso discado.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Total de participantes</strong></p></td>
<td><p>Não</p></td>
<td><p>Número total de pessoas que participaram de conferências que permitiram acesso discado.</p></td>
</tr>
<tr class="even">
<td><p><strong>Total de minutos de conferências de A/V</strong></p></td>
<td><p>Não</p></td>
<td><p>Quantidade total do tempo de conferências audiovisuais.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Total de minutos de participantes de conferências de A/V</strong></p></td>
<td><p>Não</p></td>
<td><p>Quantidade total do tempo de participantes audiovisuais. Por exemplo, se um participante passou cinco minutos em uma conferência de A/V e outro passou três minutos na mesma conferência, o tempo de participantes de conferência de A/V total seria oito minutos.</p></td>
</tr>
<tr class="even">
<td><p><strong>Total de participantes PSTN</strong></p></td>
<td><p>Não</p></td>
<td><p>Número total de usuários que discaram para conferências que permitiram acesso discado.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Total de minutos de participantes PSTN</strong></p></td>
<td><p>Não</p></td>
<td><p>Quantidade total de tempo de conferência gasto por usuários discados. Por exemplo, se um participante discado passou cinco minutos em uma conferência e outro passou três minutos na mesma conferência, o tempo de participantes PSTN total seria oito minutos.</p></td>
</tr>
<tr class="even">
<td><p><strong>Organizadores de conferência exclusivas</strong></p></td>
<td><p>Não</p></td>
<td><p>Número total de usuários que organizaram no mínimo uma conferência que permitia acesso discado. Usuários que organizaram mais de uma conferência são contados como um organizador exclusivo, assim como usuários que organizaram somente uma única conferência.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

