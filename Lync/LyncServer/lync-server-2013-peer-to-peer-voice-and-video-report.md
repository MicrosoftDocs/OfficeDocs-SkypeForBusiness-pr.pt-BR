---
title: 'Lync Server 2013: relatório de voz e vídeo ponto a ponto'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Peer-to-Peer Voice and Video Report
ms:assetid: e17c36b5-5a2f-4673-9696-3b2d31c2bb2f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615040(v=OCS.15)
ms:contentKeyID: 48185535
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 68cddb8296a94ff5d5b084895024d7379a42022c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755281"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="peer-to-peer-voice-and-video-report-in-lync-server-2013"></a>Relatório de voz e vídeo ponto a ponto no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-21_

O Relatório de Vídeo e Voz Ponto a Ponto oferece uma visão detalhada da distribuição de chamadas de voz e vídeo por um período específico (por exemplo, chamadas por hora ou chamadas por dia). O relatório também oferece a opção de exibir todas as chamadas de voz e vídeo realizadas ou de exibir apenas as chamadas bem-sucedidas ou com falha. Os relatórios mostram as informações das chamadas divididas nos seguintes agrupamentos:

  - Chamadas por pool

  - Chamadas por tipo de chamada (por exemplo, uma chamada de Lync para Lync versus uma chamada do Lync para uma pessoa na rede PSTN)

  - Chamadas por tipo de acesso (os usuários conectados na rede interna versus usuários conectados na rede externa)

  - Chamadas por servidor de mediação

<div>

## <a name="to-access-the-peer-to-peer-voice-and-video-report"></a>Para acessar o relatório de vídeo e voz ponto a ponto

É possível acessar o Relatório de Vídeo e Voz Ponto a Ponto apenas abrindo o Relatório de Resumo de Atividades Ponto a Ponto e clicando em qualquer uma das seguintes métricas:

  - Total de sessões de áudio ponto a ponto

  - Total de minutos de áudio ponto a ponto

  - Total de sessões de vídeo ponto a ponto

  - Total de minutos de vídeo ponto a ponto

</div>

<div>

## <a name="to-make-the-best-use-of-the-peer-to-peer-voice-and-video-report"></a>Para aproveitar melhor o relatório de vídeo e voz ponto a ponto

Existem várias formas de filtrar o Relatório de Vídeo e Voz Ponto a Ponto. No entanto, essas opções de filtragem são ocultas da exibição por padrão. Para exibir as opções de filtragem disponíveis, clique no botão **Exibir/Ocultar Parâmetros** no canto superior direito da janela Relatório.

</div>

<div>

## <a name="filters"></a>Filtros

Os filtros fornecem uma maneira de retornar um conjunto de dados mais direcionado ou de exibir dados de maneiras diferentes. A tabela a seguir lista os filtros que podem ser usados com o Relatório de Vídeo e Voz Ponto a Ponto.

### <a name="peer-to-peer-voice-and-video-report-filters"></a>Filtros do relatório de vídeo e voz ponto a ponto

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
<td><p><strong>Tipo de mídia</strong></p></td>
<td><p>Indica o tipo de mídia usado na sessão. Selecione uma das seguintes opções:</p>
<ul>
<li><p>Ambos</p></li>
<li><p>Áudio</p></li>
<li><p>Vídeo</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>Disposição da chamada</strong></p></td>
<td><p>Indica o sucesso ou fracasso da sessão. Selecione uma das seguintes opções:</p>
<ul>
<li><p>[Todos]</p></li>
<li><p>Chamadas com Êxito</p></li>
<li><p>Chamadas com Falha</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Relatório por</strong></p></td>
<td><p>Indica os valores a serem usados no relatório. Selecione uma das seguintes opções:</p>
<ul>
<li><p>Contagem de sessões</p></li>
<li><p>Minutos de chamadas</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-pool"></a>Métricas para atividade de vídeo e voz ponto a ponto por pool

A tabela a seguir lista as informações fornecidas no Relatório de Vídeo e Voz Ponto a Ponto para cada pool.

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-pool"></a>Métricas para atividade de vídeo e voz ponto a ponto por pool

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
<td><p><strong>Pool</strong></p></td>
<td><p>Não</p></td>
<td><p>Nome do pool de registradores ou servidor de borda usado para a chamada.</p></td>
</tr>
<tr class="even">
<td><p><strong>Data/Hora</strong></p></td>
<td><p>Não</p></td>
<td><p>Período de data e hora durante o qual a chamada foi realizada.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Total</strong></p></td>
<td><p>Não</p></td>
<td><p>Número total de sessões ou contagem total de mensagens.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-call-type"></a>Métricas da atividade de vídeo e voz ponto a ponto por tipo de chamada

A tabela a seguir lista as informações fornecidas no Relatório de Vídeo e Voz Ponto a Ponto para cada tipo de chamada realizada.

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-call-type"></a>Métricas da atividade de vídeo e voz ponto a ponto por tipo de chamada

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
<td><p><strong>Tipo de chamada</strong></p></td>
<td><p>Não</p></td>
<td><p>Indica o tipo de chamada realizada. Os valores são um dos seguintes:</p>
<ul>
<li><p>UC-para-UC</p></li>
<li><p>UC-para-PSTN</p></li>
<li><p>PSTN-para-UC</p></li>
<li><p>PSTN-para-PSTN</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Data/Hora</strong></p></td>
<td><p>Não</p></td>
<td><p>Período de data e hora durante o qual a chamada foi realizada.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Total</strong></p></td>
<td><p>Não</p></td>
<td><p>Número total de sessões ou contagem total de mensagens.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-access-type"></a>Métricas da atividade de vídeo e voz ponto a ponto por tipo de acesso

A tabela a seguir lista as informações fornecidas no Relatório de Vídeo e Voz Ponto a Ponto para cada tipo de acesso à rede.

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-access-type"></a>Métricas da atividade de vídeo e voz ponto a ponto por tipo de acesso

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
<td><p><strong>Tipo de atividade</strong></p></td>
<td><p>Não</p></td>
<td><p>Indica se os clientes estavam conectados na rede interna ou rede externa quando a chamada foi realizada. Os valores são normalmente um dos seguintes:</p>
<ul>
<li><p>Interno</p></li>
<li><p>Externo</p></li>
<li><p>Misto</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Data/Hora</strong></p></td>
<td><p>Não</p></td>
<td><p>Período de data e hora durante o qual a chamada foi realizada.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Total</strong></p></td>
<td><p>Não</p></td>
<td><p>Número total de sessões ou contagem total de mensagens.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-mediation-server"></a>Métricas para atividade de vídeo e voz ponto a ponto por servidor de mediação

A tabela a seguir lista as informações fornecidas no relatório de voz e vídeo ponto a ponto para cada servidor de mediação.

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-mediation-server"></a>Métricas para atividade de vídeo e voz ponto a ponto por servidor de mediação

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
<td><p><strong>Servidor de Mediação</strong></p></td>
<td><p>Não</p></td>
<td><p>Nome do servidor de mediação.</p></td>
</tr>
<tr class="even">
<td><p><strong>Data/Hora</strong></p></td>
<td><p>Não</p></td>
<td><p>Período de data e hora durante o qual a chamada foi realizada.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Total</strong></p></td>
<td><p>Não</p></td>
<td><p>Número total de sessões ou contagem total de mensagens.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

