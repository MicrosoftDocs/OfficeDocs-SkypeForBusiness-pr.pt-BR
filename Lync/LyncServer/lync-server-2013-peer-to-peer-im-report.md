---
title: 'Lync Server 2013: relatório de mensagens instantâneas ponto a ponto'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Peer-to-Peer IM Report
ms:assetid: 19ec0145-2398-437b-8989-f780c179b798
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558620(v=OCS.15)
ms:contentKeyID: 48183533
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 16098a1d549c155f9a642f7e68f056f07973217d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48524368"
---
# <a name="peer-to-peer-im-report-in-lync-server-2013"></a>Relatório de mensagens instantâneas ponto a ponto no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-11-01_

O Relatório de Mensagens Instantâneas Ponto a Ponto fornece informações de tendência sobre sessões de IM (mensagens instantâneas) ponto a ponto, detalhadas por pool e tipo de autenticação. O relatório pode mostrar o número total de sessões que aconeceram durante o período de tempo especificado (por exemplo, dia por dia ou hora por hora), ou pode mostrar o número total de mensagens instantâneas enviadas durante esse período de tempo.

<div>

## <a name="accessing-the-peer-to-peer-im-report"></a>Acessando o Relatório de Mensagens Instantâneas Ponto a Ponto

Você pode acessar o relatório de mensagens instantâneas ponto a ponto apenas abrindo o [relatório de Resumo de atividades ponto a ponto no Lync Server 2013](lync-server-2013-peer-to-peer-activity-summary-report.md) e, em seguida, clicando em uma das seguintes métricas:

  - Total de sessões de mensagens instantâneas ponto a ponto

  - Total de mensagens de IM ponto a ponto

</div>

<div>

## <a name="making-the-best-use-of-the-peer-to-peer-im-report"></a>Usando o Relatório de Mensagens Instantâneas Ponto a Ponto da melhor maneira possível

Por padrão, o Relatório de Mensagens Instantâneas Ponto a Ponto mostra a você a conagem de mensagens por hora (ou dia, dependendo de suas configurações). No entanto, você também pode escolher visualizar o dia por sessões por hora. Para fazer isso, clique em **Ocultar/Exibir Parâmetros** no canto superior direito da janela Relatórios, e então clique em **Contagem de Sessão** a partir da lista **Relatar por**.

</div>

<div>

## <a name="filters"></a>Filtros

Os filtros fornecem uma maneira de obter um resultado mais refinado de conjunto de dados ou visualizar os dados resultantes de maneiras diferentes. A tabela a seguir lista os filtros que você pode utilizar com o Relatório do Sistema de Mensagens Instantâneas Ponto a Ponto.

### <a name="peer-to-peer-im-report-filters"></a>Filtros do Relatório do Sistema de Mensagens Instantâneas Ponto a Ponto

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
<td><p>Data e hora de início para o intervalo de tempo. Para ver os dados por hora, digite a data e hora de início no seguinte formato:</p>
<p>07/07/2012 13:00</p>
<p>Se você não inserir uma hora inicial, o relatório começa automaticamente as 12:00 AM no dia especificado. Para exibir os dados por dia, insira apenas a data:</p>
<p>7/7/2012</p>
<p>Para visualizar por semana ou por mês, digite uma data qualquer da semana ou mês (não é necessário digitar o primeiro dia da semana ou mês)</p>
<p>7/3/2012</p>
<p>As semanas são sempre de domingo a sábado.</p></td>
</tr>
<tr class="even">
<td><p><strong>To</strong></p></td>
<td><p>Data e hora de término para o dia intervalo de tempo. Para ver os dados por hora, digite a data e a hora de término no seguinte formato:</p>
<p>07/07/2012 13:00</p>
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
<li><p>Mensalmente (exibição de no máximo 12 meses)</p></li>
</ul>
<p>Caso as datas de início e término excedam o número máximo de valores permitidos para o intervalo selecionado, será exibido somente o número máximo de valores (começando a partir da data de inicio). Por exemplo, se você selecionar o intervalo Diariamente com uma data de início em 1/1/2011 e a data de término em 28/02/2012, os dados serão exibidos para dos dias 07/08/2012 12:00 ao 07/09/2012 12:00 (ou seja, um total de 31 dias de dados).</p></td>
</tr>
<tr class="even">
<td><p><strong>Relatório por</strong></p></td>
<td><p>Indica os valores a serem usados no relatório. Selecione um dos seguintes valores:</p>
<ul>
<li><p>Contagem de sessão</p></li>
<li><p>Contagem de mensagem</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-im-session-by-pool"></a>Medição da sessão do Sistema de Mensagens Instantâneas Ponto a Ponto por Pool

A tabela a seguir lista as informações fornecidas pelo Relatório do Sistema de Mensagens Instantâneas Ponto a Ponto.

### <a name="metrics-for-peer-to-peer-im-session-by-pool"></a>Medição da sessão do Sistema de Mensagens Instantâneas Ponto a Ponto por Pool

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
<td><p>Nome do pool de registradores ou servidor de borda.</p></td>
</tr>
<tr class="even">
<td><p><strong>Data/Hora</strong></p></td>
<td><p>Não</p></td>
<td><p>Data e hora em que a sessões ocorreram.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Total</strong></p></td>
<td><p>Não</p></td>
<td><p>Número total de sessões ou de contagem total de mensagens.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-im-session-by-authentication-type"></a>Medição da sessão do Sistema de Mensagens Instantâneas Ponto a Ponto por tipo de autenticação

A tabela a seguir lista as informações fornecidas pelo Relatório do Sistema de Mensagens Instantâneas Ponto a Ponto para cada tipo de autenticação usada pelos participantes em uma sessão ponto a ponto.

### <a name="metrics-for-peer-to-peer-im-session-by-authentication-type"></a>Medição da sessão do Sistema de Mensagens Instantâneas Ponto a Ponto por tipo de autenticação

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
<td><p><strong>Tipo de Autenticação</strong>:</p></td>
<td><p>Não</p></td>
<td><p>Tipo de autenticação usada pelos participantes da sessão. Normalmente, os valores são um dos seguintes:</p>
<ul>
<li><p>Enterprise</p></li>
<li><p>Fica</p></li>
<li><p>PIC</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Data/Hora</strong></p></td>
<td><p>Não</p></td>
<td><p>Data e hora em que a sessões ocorreram.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Total</strong></p></td>
<td><p>Não</p></td>
<td><p>Número total de sessões ou de contagem total de mensagens.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

