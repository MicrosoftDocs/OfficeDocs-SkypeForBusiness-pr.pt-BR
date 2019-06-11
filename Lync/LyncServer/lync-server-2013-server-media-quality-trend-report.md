---
title: 'Lync Server 2013: relatório de tendências de qualidade de mídia do servidor'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Server Media Quality Trend Report
ms:assetid: 8a51fd13-1487-4632-b5ec-f7ae2abe8ed4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205071(v=OCS.15)
ms:contentKeyID: 48184760
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dc60cd4c0d8d00fa67a5fe77ca70e61058191baa
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34821870"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="server-media-quality-trend-report-in-lync-server-2013"></a>Relatório de tendências de qualidade de mídia do servidor no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-11-12_

O relatório de tendências de qualidade de mídia do servidor fornece uma maneira de comparar graficamente até cinco servidores com métricas de qualidade de experiência, como volume de chamadas, porcentagem de chamadas deficientes, perda de pacotes e Tremulação. Ele facilita determinadas tarefas como identificar servidores com desempenho ruim, subutilizados e superutilizados.

<div>

## <a name="accessing-the-server-media-quality-trend-report"></a>Acessando o Relatório de Tendências de Qualidade de Mídia do Servidor

O Relatório de Tendências de Qualidade de Mídia do Servidor pode ser acessado por um destes relatórios:

  - [Relatório de desempenho do servidor no Lync Server 2013](lync-server-2013-server-performance-report.md) (clicando na métrica de tendência)

  - [Relatório de detalhes da chamada no Lync Server 2013](lync-server-2013-call-detail-report.md) (clicando na métrica de servidor de borda A/V. Se o chamador ou o receptor for um servidor, você também poderá acessar o relatório de tendências de mídia de qualidade do servidor clicando no nome do ponto de extremidade.)

</div>

<div>

## <a name="making-the-best-use-of-server-media-quality-trend-report"></a>Aproveitando ao máximo o Relatório de Tendências de Qualidade de Mídia do Servidor

Quando você clica na métrica de tendência no [relatório de desempenho do servidor no Lync Server 2013](lync-server-2013-server-performance-report.md) para um servidor específico, o relatório de tendências de qualidade de mídia do servidor será aberto. No entanto, você verá uma instância em branco do relatório; o servidor selecionado no Relatório de Desempenho do Servidor não será exibido na tela. Será necessário selecionar o servidor em questão no menu suspenso "Servidores". O menu suspenso "Servidores" apresenta também a opção "Selecionar tudo". Essa opção não funcionará caso haja mais de cinco servidores; o relatório de tendências de qualidade de mídia do servidor só pode exibir dados para, no máximo, cinco servidores por vez.

Nos gráficos exibidos pelo relatório de tendências de qualidade de mídia do servidor, os pontos com o rótulo de chamadas e a porcentagem de chamada baixa são hotlinks; clicar em um ponto no gráfico abrirá uma instância do [relatório de lista de chamadas no Lync Server 2013](lync-server-2013-call-list-report.md) mostrando o total de chamadas (ou chamadas ruins) pelo período de tempo especificado.

</div>

<div>

## <a name="filters"></a>Filtros

Os filtros são uma forma de obter dados mais direcionados ou visualizar os dados obtidos de diferentes maneiras. A tabela a seguir relaciona os filtros que podem ser usados no relatório de tendências de qualidade de mídia do servidor.

### <a name="server-media-quality-trend-report-filters"></a>Filtros do Relatório de Tendências de Qualidade de Mídia do Servidor

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
</ul>
<p>Se as datas de início e término excederem o número máximo de valores permitidos para o intervalo selecionado, somente o número máximo de valores (a partir da data de início) será exibido. Por exemplo, se você selecionar o intervalo diário com uma data de início de 8/7/2012 e uma data de término de 9/28/2012, os dados serão exibidos para os dias 8/7/2012 12:00 AM a 9/7/2012 12:00 AM (ou seja, um total de 31 dias da importância dos dados).</p></td>
</tr>
<tr class="even">
<td><p><strong>Tipo de Servidor</strong></p></td>
<td><p>Tipo de servidor envolvido na chamada. Os valores permitidos são</p>
<ul>
<li><p>Servidor de Mediação</p></li>
<li><p>Servidor de Conferência A/V</p></li>
<li><p>Servidor de Borda A/V</p></li>
<li><p>Gateway (Servidor de Mediação)</p></li>
<li><p>Gateway (Bypass do servidor de mediação)</p></li>
<li><p>Servidor de conferência AS</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>Servidores</strong></p></td>
<td><p>Nome do servidor envolvido na sessão; essa lista suspensa é preenchida automaticamente com base no valor do filtro de tipo de arquivo. É possível selecionar até cinco servidores diferentes ao compilar o relatório.</p></td>
</tr>
<tr class="even">
<td><p><strong>Tipo de acesso</strong></p></td>
<td><p>Indica se o participante fez logon a partir da rede interna ou de uma rede externa. Os valores permitidos são:</p>
<ul>
<li><p>[Todos]</p></li>
<li><p>Interno</p></li>
<li><p>Externo</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>Tipo de rede</strong></p></td>
<td><p>Indica o tipo de rede ao qual o participante estava conectado. Os valores permitidos são:</p>
<ul>
<li><p>[Todos]</p></li>
<li><p>Com fio</p></li>
<li><p>Sem fio</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>VPN</strong></p></td>
<td><p>Indica se o participante externos estava usando conexão VPN durante a sessão. Os valores permitidos são:</p>
<ul>
<li><p>[Todos]</p></li>
<li><p>VPN</p></li>
<li><p>Não-VPN</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>Métricas

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
<th>Você pode classificar este item?</th>
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
<td><p>Valor médio de uma redução da opção MOS (média da opção) durante uma chamada. Os valores de degradação podem variar de um baixo de 0,0 a um alto de 5,0; um valor de 0,5 ou menos representa uma degradação aceitável. As pontuações médias de opinião costumava ser calculadas a partir da classificação da qualidade de uma chamada em uma escala de 1 a 5, feita pelos dos usuários. O Lync Server usa um conjunto de algoritmos para prever como os usuários teriam classificado uma chamada.</p>
<p>Valores altos de degradação podem ser causados por congestionamento, falta de largura de banda, congestionamento ou interferência na rede sem fio ou um servidor de mídia ou ponto de extremidade sobrecarregado. A alta degradação resulta em perda ou distorção de áudio.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Porcentagem de chamadas ruins</strong></p></td>
<td><p>Não</p></td>
<td><p>O número total de chamadas classificadas como ruins. Uma chamada ruim é qualquer chamada em que no mínimo uma das métricas excedeu o valor permitido (por exemplo, uma chamada com tremulação excessiva).</p></td>
</tr>
<tr class="even">
<td><p><strong>Ida e volta (ms)</strong></p></td>
<td><p>Não</p></td>
<td><p>Quantidade média de tempo (em milissegundos) exigida para que um pacote de protocolo RTP vá até um ponto de extremidade e retorne. Tempos de ida e volta de 200 milissegundos ou menos são considerados de qualidade aceitável.</p>
<p>Altos valores de tempo de resposta podem ser causados por roteamento de chamadas internacionais, configuração incorreta de um roteamento ou um servidor de mídia sobrecarregado. Tempos de resposta altos resultam em dificuldades para conversas de áudio bidirecionais e em tempo real.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Perda de pacote</strong></p></td>
<td><p>Não</p></td>
<td><p>Taxa média de perda de pacotes de RTP (protocolo de transporte em tempo real). (A perda de pacotes ocorre quando pacotes de RTP, um protocolo usado para transmitir áudio e vídeo pela Internet, falha ao tentar alcançar seu destino). Altas taxas de perda geralmente são causadas por congestionamento, insuficiência da largura de banda, congestionamento ou interferência na rede sem fio ou um servidor de mídia sobrecarregado. A perda de pacotes normalmente resulta em distorção ou perda de áudio.</p></td>
</tr>
<tr class="even">
<td><p><strong>Tremulação (ms)</strong></p></td>
<td><p>Não</p></td>
<td><p>Tremulação média detectada entre chegadas de pacote RTP. (Tremulação é uma medida do &quot;shakiness&quot; de uma chamada.) Os valores de variação alta geralmente são causados por congestionamento ou um servidor de mídia sobrecarregado, resultando em áudio distorcido ou perdido.</p></td>
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

