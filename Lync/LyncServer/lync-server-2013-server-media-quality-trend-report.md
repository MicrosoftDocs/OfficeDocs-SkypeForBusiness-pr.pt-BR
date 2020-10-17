---
title: 'Lync Server 2013: relatório de tendências de qualidade de mídia do servidor'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Server Media Quality Trend Report
ms:assetid: 8a51fd13-1487-4632-b5ec-f7ae2abe8ed4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205071(v=OCS.15)
ms:contentKeyID: 48184760
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4b40f2c316216b01415b3e58d5d59c97421439d2
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48510298"
---
# <a name="server-media-quality-trend-report-in-lync-server-2013"></a>Relatório de tendências de qualidade de mídia do servidor no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-11-12_

O relatório de tendências de qualidade de mídia do servidor é uma forma gráfica de comparar até cinco servidores em relação a métricas de qualidade de experiência, como volume da chamada, percentagem de chamadas ruins, perda de pacotes e tremulação. Ele facilita determinadas tarefas como identificar servidores com desempenho ruim, subutilizados e superutilizados.

<div>

## <a name="accessing-the-server-media-quality-trend-report"></a>Acessando o relatório de tendências de qualidade de mídia do servidor

O relatório de tendências de qualidade de mídia do servidor pode ser acessado por um destes relatórios:

  - [Relatório de desempenho do servidor no Lync Server 2013](lync-server-2013-server-performance-report.md) (clicando na métrica de tendência)

  - [Relatório detalhado de chamadas no Lync Server 2013](lync-server-2013-call-detail-report.md) (clicando na métrica de servidor de borda a/V. Se o chamador ou o receptor for um servidor, você também pode acessar o relatório de tendências de mídia de qualidade do servidor clicando no nome do ponto de extremidade.

</div>

<div>

## <a name="making-the-best-use-of-server-media-quality-trend-report"></a>Aproveitando ao máximo o relatório de tendências de qualidade de mídia do servidor

Ao clicar na métrica de tendência no [relatório de desempenho do servidor no Lync Server 2013](lync-server-2013-server-performance-report.md) para um servidor específico, o relatório de tendências de qualidade de mídia do servidor será aberto. No entanto, você verá uma instância em branco do relatório; o servidor selecionado no Relatório de desempenho do servidor não será exibido na tela. Será necessário selecionar o servidor em questão no menu suspenso "Servidores". O menu suspenso "Servidores" apresenta também a opção "Seleciontar tudo". Essa opção não funcionará caso haja mais de cinco servidores; o relatório de tendências de qualidade de mídia do servidor só pode exibir dados para, no máximo, cinco servidores por vez.

Nos gráficos exibidos pelo relatório de tendências de qualidade de mídia do servidor, os pontos com o rótulo volume de chamadas e a porcentagem de chamadas ruins são hotlinks; clicar em um ponto no gráfico abrirá uma instância do [relatório de lista de chamadas no Lync Server 2013](lync-server-2013-call-list-report.md) , mostrando o total de chamadas (ou chamadas ruins) para o período de tempo especificado.

</div>

<div>

## <a name="filters"></a>Filtros

Os filtros são uma forma de obter dados mais direcionados ou visualizar os dados obtidos de diferentes maneiras. A tabela a seguir relaciona os filtros que podem ser usados no relatório de tendências de qualidade de mídia do servidor.

### <a name="server-media-quality-trend-report-filters"></a>Filtros do relatório de tendências de qualidade de mídia do servidor

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
<li><p>Semanal (podem ser exibidas, no máximo, 12 semanas)</p></li>
</ul>
<p>Se as datas de início e término ultrapassarem a quantidade máxima permitida para o intervalo selecionado, apenas o máximo de valores (a contar da data de início) será exibido. Por exemplo, se você selecionar o intervalo "Diário" com data de início em 7/7/2012 e data de término em 28/9/2012, os dados são exibidos das 12:00 AM do dia 7/8/2012 a 12:00 AM do dia 7/9/2012 (ou seja, um tota de 31 dias de dados).</p></td>
</tr>
<tr class="even">
<td><p><strong>Tipo de servidor</strong></p></td>
<td><p>Tipo de servidor envolvido na chamada. Os valores permitidos são</p>
<ul>
<li><p>Servidor de mediação</p></li>
<li><p>Servidor de Conferência A/V</p></li>
<li><p>Servidor de Borda A/V</p></li>
<li><p>Gateway (servidor de mediação)</p></li>
<li><p>Gateway (Bypass do servidor de mediação)</p></li>
<li><p>Servidor de conferência AS</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>Servidores</strong></p></td>
<td><p>Nome do servidor envolvidona sessão; essa lista suspensa é preenchida automaticamente com base no valor do filtro de tipo de arquivo. É possível selecionar até cinco servidores diferentes ao compilar o relatório.</p></td>
</tr>
<tr class="even">
<td><p><strong>Tipo de acesso</strong></p></td>
<td><p>Indica se o participante fez logon a partir da rede interna ou de uma rede externa. Os valores permitidos são:</p>
<ul>
<li><p>Todos os</p></li>
<li><p>Interno</p></li>
<li><p>Externo</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>Tipo de rede</strong></p></td>
<td><p>Indicao tipo de rede ao qual o participante estava conectado. Osvalores permitidos são:</p>
<ul>
<li><p>Todos os</p></li>
<li><p>Com fio</p></li>
<li><p>Conexão</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>VPN</strong></p></td>
<td><p>Indica se o participante externos estava usando conexão VPN durante a sessão. Os valores permitidos são:</p>
<ul>
<li><p>Todos os</p></li>
<li><p>VPN</p></li>
<li><p>Não VPN</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>Métrica

A tabela a seguir lista as informações fornecidas no relatório de tendências de qualidade de mídia do servidor.

### <a name="server-media-quality-trend-report-metrics"></a>Métricas do relatório de tendências de qualidade de mídia do servidor

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
<td><p><strong>Volume da chamada</strong></p></td>
<td><p>Não</p></td>
<td><p>Número total de chamadas.</p></td>
</tr>
<tr class="even">
<td><p><strong>Degradação (MOS)</strong></p></td>
<td><p>Não</p></td>
<td><p>Valor médio de uma degradação da marca de opção (média) em uma chamada. Os valores de degradação podem variar de um baixo de 0,0 para um alto de 5,0; um valor de 0,5 ou menos representa degradação aceitável. Historicamente, pontuações de opções médias foram calculadas com usuários classificando a qualidade de uma chamada em uma escala de 1 a 5. O Lync Server usa um conjunto de algoritmos para prever como os usuários classificaram uma chamada.</p>
<p>Os valores de degradação altos podem ser causados por congestão, falta de largura de banda, congestionamento ou interferência sem fio ou um servidor de mídia ou ponto de extremidade sobrecarregado. A alta degradação resulta em perda ou distorção de áudio.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Percentual de chamadas ruins</strong></p></td>
<td><p>Não</p></td>
<td><p>O número total de chamadas classificadas como ruins. Uma chamada ruim é qualquer chamada em que no mínimo uma das métricas medidas excedeu o valor permitido (por exemplo, uma chamada com tremulação excessiva).</p></td>
</tr>
<tr class="even">
<td><p><strong>Viagem de ida e volta (ms)</strong></p></td>
<td><p>Não</p></td>
<td><p>Quantidade média de tempo (em milésimos de seguntos) exigida para que um pacote (protocolo de transporte em tempo real) viaje até outra extremidade e retorne. Tempos de viagem de ida e volta de 200 milésimos de segundo ou menos são considerados de qualidade aceitável.</p>
<p>Viagens de ida e volta com altos valores podem ser resultado do roteamento de chamadas internacionais, configurações incorretas de roteamento ou servidor de mídia sobrecarregado. Viagens de ida e volta com altos valores resultam em dificuldades para conversas de áudio bidirecionais e em tempo real.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Perda de pacote </strong></p></td>
<td><p>Não</p></td>
<td><p>Taxa média de perda de pacotes de Protocolo de Transporte em Tempo Real (RTP). (A perda de pacotes ocorre quando pacotes RTP, um protocolo usado para transmitir áudio e vídeo pela internet, falha ao tentar alcançar seu destino). Altas taxas de perda geralmente são causadas por congestionamento, insuficiência da largura de banda, congestionamento ou interferência na rede sem fio ou um servidor de mídia sobrecarregado. A perda de pacotes normalmente resulta em distorção ou perda de áudio.</p></td>
</tr>
<tr class="even">
<td><p><strong>Tremulação (ms)</strong></p></td>
<td><p>Não</p></td>
<td><p>Tremulação média detectada entre chegadas de pacote RTP. (Tremulação é uma medida do &quot; tremula &quot; de uma chamada.) Os valores de variação alta geralmente são causados por congestionamento ou por um servidor de mídia sobrecarregado e resultam em um áudio distorcido ou perdido.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Taxa de correção oculta</strong></p></td>
<td><p>Não</p></td>
<td><p>Taxa média de amostras de áudio ocultas para o número total de amostras. (Uma amostra de áudio oculta é uma técnica usada para suavizar a transição abrupta que normalmente seria causada por pacotes de rede descartados.) Valores altos indicam níveis consideráveis de perda de ocultação aplicada causada por perda de pacote ou tremulação e resulta na perda ou distorção de áudio.</p></td>
</tr>
<tr class="even">
<td><p><strong>Taxa de correção estendida</strong></p></td>
<td><p>Não</p></td>
<td><p>Taxa média de amostras de áudio estendidas para o número total de amostras. (Áudio estendido é o áudio que foi expandido a fim de ajudar a manter a qualidade da chamada quando um pacote de rede descartado é detectado.) Valores altos indicam níveis significativos de extensão de amostra causada por tremulação e resultam em um som robótico ou distorcido.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Taxa de correção compactada</strong></p></td>
<td><p>Não</p></td>
<td><p>Taxa média de amostras de áudio compactadas para o número total de amostras. (Áudio compactado é o áudio que foi compactado para ajudar a manter a qualidade da chamada quando um pacote de rede descartado é detectado.) Valores altos podem indicar níveis consideráveis de compactação de amostra causada por tremulação e resultam em um som acelerado ou distorcido.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

