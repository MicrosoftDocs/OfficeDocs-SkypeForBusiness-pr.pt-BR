---
title: 'Lync Server 2013: relatório de Resumo de atividades ponto a ponto'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Peer-to-Peer Activity Summary Report
ms:assetid: e829a21e-9dfa-46ba-9b5b-077c175d6586
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615041(v=OCS.15)
ms:contentKeyID: 48185884
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 03a3015f24bae2595ac845c351c32ccb5d36c5f7
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153091"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="peer-to-peer-activity-summary-report-in-lync-server-2013"></a>Relatório de Resumo de atividades ponto a ponto no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-21_

O Relatório de Resumo de Atividades Ponto a Ponto fornece uma visão geral de suas sessões de comunicação ponto a ponto. Uma sessão ponto a ponto geralmente envolve apenas dois usuários e não requer o uso dos serviços de conferência do Lync Server. Por comparação, uma conferência geralmente envolve mais de dois usuários e requer o uso de serviços de conferência do Microsoft Lync Server 2013. Atividades de conferência são relatadas no Relatório de Resumo de Conferência.

O Relatório de Resumo de Atividade Ponto a Ponto ajuda você a responder perguntas como as seguintes:

  - Quantas mensagens instantâneas ponto a ponto meus usuários enviam em um dia normal?

  - Algum de meus usuários realmente aproveita as vantagens do compartilhamento de aplicativos do Lync Server e dos recursos de transferência de arquivos?

  - Usuários tem reclamado que a rede parece devagar em certos horários do dia. Quantos minutos são devotados para sessões de áudio e video durante estes períodos de tempo?

<div>

## <a name="accessing-the-peer-to-peer-activity-summary-report"></a>Acessando o Relatório de Resumo de Atividade Ponto a Ponto

O Relatório de Resumo de Atividade Ponto a Ponto é acessado a partir da página inicial de Relatórios de Monitoramento. Abra o [relatório de mensagens instantâneas ponto a ponto no Lync Server 2013](lync-server-2013-peer-to-peer-im-report.md) clicando em uma das seguintes métricas:

  - Total de sessões de IM ponto a ponto

  - Total de mensagens instantâneas ponto a ponto

De modo parecido, você pode abrir o Relatório de Vídeo e Voz Ponto a Ponto clicando em qualquer uma destas métricas:

  - Total de sessões de áudio ponto a ponto

  - Total de minutos de sessão de áudio ponto a ponto

  - Total de sessões de áudio ponto a ponto

  - Total de minutos de sessão de áudio ponto a ponto

</div>

<div>

## <a name="making-the-best-use-of-the-peer-to-peer-activity-summary-report"></a>Fazendo o Melhor Uso do Relatório de Resumo de Atividade Ponto a Ponto

Ao final do Relatório de Resumo de Atividade Ponto a Ponto, você encontrará os totais para métricas tais como Total de sessões de mensagens instantâneas ponto a ponto e Total de mensagens instantâneas ponto a ponto. Isso oferece um resumo rápido das informações detalhadas encontradas no corpo do relatório.

</div>

<div>

## <a name="filters"></a>Filtros

Os filtros fornecem uma maneira de retornar um conjunto de dados mais direcionado ou de exibir os dados retornados de maneiras diferentes. Por exemplo, o Relatório de Resumos de Atividades Ponto a Ponto permite que você escolha como os dados devem ser agrupados. Nesse caso, atividades agrupadas por hora, dia, semana ou mês.

A tabela a seguir lista os filtros que podem ser usados com o Relatório de Resumos de Atividades Ponta a Ponta.

### <a name="peer-to-peer-activity-summary-report-filters"></a>Filtros do Relatório de Resumos de Atividades Ponto a Ponto

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
<td><p>Data e hora de início para o intervalo de tempo. Para exibir os dados por horas, digite a data e a hora de início da seguinte maneira:</p>
<p>17/07/12012 13:00</p>
<p>Se você não digitar um horário de início, o relatório começará automaticamente às 12:00 AM no dia especificado. Para exibir os dados por dia, digite apenas a data:</p>
<p>7/17/12012</p>
<p>Para exibir por semana ou por mês, insira uma data cai em qualquer lugar dentro da semana ou mês que você deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):</p>
<p>7/13/2012</p>
<p>As semanas sempre correm do domingo até sábado.</p></td>
</tr>
<tr class="even">
<td><p><strong>To</strong></p></td>
<td><p>Data e hora final para o intervalo de tempo. Para exibir os dados por hora, insira a data e hora final como a seguir:</p>
<p>17/07/2012 13:00</p>
<p>Se você não digitar um horário de término, o relatório terminará automaticamente às 12:00 AM no dia especificado. Para exibir os dados por dia, digite apenas a data:</p>
<p>7/17/12012</p>
<p>Para exibir por semana ou por mês, insira uma data cai em qualquer lugar dentro da semana ou mês que você deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):</p>
<p>7/13/2012</p>
<p>As semanas sempre correm do domingo até sábado.</p></td>
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
<p>Se as datas de início e término excederem o número máximo de valores permitidos para o intervalo selecionado, somente o número máximo de valores (a partir da data de início) será exibido. Por exemplo, se você selecionar o intervalo Diariamente com a data de início 17/07/2012 e uma data de término de 28/02/12, os dados serão exibidos para os dias 07/08/2012 12:00 AM até 07/09/2012 12:00 AM (ou seja, um total de 31 dias de dados).</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>Métricas

A tabela a seguir lista as informações fornecidas no Relatório de Resumos de Atividades Ponto a Ponto.

### <a name="peer-to-peer-activity-summary-report-metrics"></a>Métricas do Relatório de Resumos de Atividades Ponto a Ponto

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
<td><p><strong>A cada hora</strong></p>
<p><strong>Diariamente</strong></p>
<p><strong>Semanalmente</strong></p>
<p><strong>Mensal</strong></p></td>
<td><p>Não</p></td>
<td><p>Indica o intervalo de tempo selecionado na barra de ferramentas do filtro. Quando aplicável, é possível clicar em um determinado intervalo de tempo para exibir informações detalhadas desse intervalo. Por exemplo, se você estiver usando o intervalo Diário e clicar em 17/07/2012, você verá uma divisão por hora da atividade de registro do usuário para essa data.</p></td>
</tr>
<tr class="even">
<td><p><strong>Total de sessões ponto a ponto </strong></p></td>
<td><p>Não</p></td>
<td><p>Número total de sessões ponto a ponto conduzidas, independentemente do tipo de sessão.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Total de sessões de mensagens instantâneas ponto a ponto </strong></p></td>
<td><p>Não</p></td>
<td><p>Número total de sessões de mensagens instantâneas (IM) ponto a ponto. Quando você clica nesse item, o relatório mostra o Relatório de Mensagens Instantâneas Ponto a Ponto para o período selecionado.</p></td>
</tr>
<tr class="even">
<td><p><strong>Total de mensagens instantâneas ponto a ponto </strong></p></td>
<td><p>Não</p></td>
<td><p>Número total de mensagens instantâneas enviadas em sessões ponto a ponto. Quando você clica nesse item, o relatório mostra o Relatório de Mensagens Instantâneas Ponto a Ponto para o período selecionado.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Total de sessões de áudio ponto a ponto </strong></p></td>
<td><p>Não</p></td>
<td><p>Número total de chamadas de áudio ponto a ponto. Quando você clica nesse campo, o relatório mostra o Relatório de de Voz e Vídeo Ponto a Ponto para o período selecionado.</p></td>
</tr>
<tr class="even">
<td><p><strong>Total de minutos de sessão de áudio ponto a ponto</strong></p></td>
<td><p>Não</p></td>
<td><p>Tempo total gasto em sessões de áudio ponto a ponto. Quando você clica nesse item, o relatório mostra o relatório de vídeo e voz ponto a ponto para o período de tempo selecionado.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Média de minutos de sessão de áudio ponto a ponto</strong></p></td>
<td><p>Não</p></td>
<td><p>Tempo médio gasto em sessões de áudio ponto a ponto. Calculado dividindo o tempo de sessão de áudio total pelo número total de sessões de áudio.</p></td>
</tr>
<tr class="even">
<td><p><strong>Total de sessões de vídeo ponto a ponto </strong></p></td>
<td><p>Não</p></td>
<td><p>Número total de chamadas de vídeo ponto a ponto. Observe que as sessões de vídeo também são contadas como sessões de áudio: cada sessão de vídeo é contada como uma sessão de vídeo e uma sessão de áudio. Quando você clica nesse item, o relatório mostra o relatório de vídeo e voz ponto a ponto para o período de tempo selecionado.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Total de minutos de sessão de vídeo ponto a ponto</strong></p></td>
<td><p>Não</p></td>
<td><p>Tempo total gasto em sessões de vídeo ponto a ponto. Quando você clica nesse item, o relatório mostra o relatório de vídeo e voz ponto a ponto para o período de tempo selecionado.</p></td>
</tr>
<tr class="even">
<td><p><strong>Média de minutos de sessão de vídeo ponto a ponto</strong></p></td>
<td><p>Não</p></td>
<td><p>Tempo médio gasto em sessões de vídeo ponto a ponto. Calculado dividindo o tempo de sessão de vídeo total pelo número total de sessões de áudio.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Total de sessões de transferência de arquivo ponto a ponto</strong></p></td>
<td><p>Não</p></td>
<td><p>Número total de sessões ponto a ponto que incluem transferências de arquivo.</p></td>
</tr>
<tr class="even">
<td><p><strong>Total de sessões de compartilhamento de arquivo ponto a ponto</strong></p></td>
<td><p>Não</p></td>
<td><p>Número total de sessões ponto a ponto que incluem compartilhamento de aplicativo.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

