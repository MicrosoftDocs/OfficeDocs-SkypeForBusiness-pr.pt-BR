---
title: 'Lync Server 2013: relatório de comparação de qualidade de mídia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Media Quality Comparison Report
ms:assetid: c1d0b5a8-98ff-455a-b78b-a05a21cf066d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205236(v=OCS.15)
ms:contentKeyID: 48185317
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a6697e02d7b821ebd3dc3cabc3a95c8d00960a08
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827442"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="media-quality-comparison-report-in-lync-server-2013"></a>Relatório de comparação de qualidade de mídia no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2014-04-22_

O Relatório de Comparação de Qualidade da Mídia permite comparar os valores de qualidade da chamada para diferentes tipos de chamadas de áudio (por exemplo, chamadas realizadas por uma rede sem fio contra chamadas realizadas em uma conexão com fio).

<div>

## <a name="accessing-the-media-quality-comparison-report"></a>Como acessar o Relatório de Comparação de Qualidade de Mídia

O Relatório de Comparação de Qualidade de Mídia é acessado na página inicial de Relatórios de Monitoramento.

</div>

<div>

## <a name="filters"></a>Filtros

Os filtros oferecem uma forma de retornar um conjunto de dados mais detalhado ou exibir os dados retornados em formas diferentes. A tabela a seguir lista os filtros que você pode usar com o Relatório de Comparação de Qualidade de Mídia.

### <a name="media-quality-comparison-report-filters"></a>Filtros do Relatório de Comparação de Qualidade de Mídia

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
<td><p><strong>Chamadas</strong></p></td>
<td><p>Tipo de chamada a ser usado como o item de comparação principal. Os valores permitidos são:</p>
<ul>
<li><p>[Todos]</p></li>
<li><p>Externo</p></li>
<li><p>Interno</p></li>
<li><p>VPN</p></li>
<li><p>Não VPN</p></li>
<li><p>Com fio</p></li>
<li><p>Sem fio</p></li>
<li><p>Externo e com fio</p></li>
<li><p>Externo e sem fio</p></li>
<li><p>Externo e VPN</p></li>
<li><p>Externo e não VPN</p></li>
<li><p>Interno e com fio</p></li>
<li><p>Interno e sem fio</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Comparar com chamadas</strong></p></td>
<td><p>Tipo de chamada a ser usado como o item de comparação secundário. Os valores permitidos são:</p>
<ul>
<li><p>[Todos]</p></li>
<li><p>Externo</p></li>
<li><p>Interno</p></li>
<li><p>VPN</p></li>
<li><p>Não VPN</p></li>
<li><p>Com fio</p></li>
<li><p>Sem fio</p></li>
<li><p>Externo e com fio</p></li>
<li><p>Externo e sem fio</p></li>
<li><p>Externo e VPN</p></li>
<li><p>Externo e não VPN</p></li>
<li><p>Interno e com fio</p></li>
<li><p>Interno e sem fio</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>Intervalo</strong></p></td>
<td><p>Intervalo de tempo. Selecione uma das seguintes opções:</p>
<ul>
<li><p>Por hora (é possível exibir no máximo 25 horas)</p></li>
<li><p>Diariamente (é possível exibir no máximo 31 dias)</p></li>
<li><p>Semanalmente (é possível exibir no máximo 12 semanas)</p></li>
</ul>
<p>Se as datas de início e término excederem o número máximo de valores permitidos para o intervalo selecionado, somente o número máximo de valores (a partir da data de início) será exibido. Por exemplo, se você selecionar o intervalo diário com uma data de início de 7/7/2012 e uma data de término de 2/28/2012, os dados serão exibidos para os dias 8/7/2012 12:00 AM a 9/7/2012 12:00 AM (ou seja, um total de 31 dias da importância dos dados).</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>Métricas

A tabela a seguir lista as informações fornecidas no Relatório de Comparação de Qualidade da Mídia.

### <a name="media-quality-comparison-report-metrics"></a>Métricas do Relatório de Comparação de Qualidade da Mídia

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
<td><p>Valor médio da degradação da MOS (Pontuação de opinião média) durante uma chamada. Os valores de degradação podem variar de um baixo de 0,0 a um alto de 5,0; um valor de 0,5 ou menos representa uma degradação aceitável. Historicamente, a média das pontuações de opinião foi calculada pela necessidade de os usuários classificarem a qualidade de uma chamada em uma escala de 1 a 5. O Lync Server usa um conjunto de algoritmos para prever como os usuários teriam classificado uma chamada.</p>
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
<td><p>Quantidade média (em milissegundos) exigida para que um pacote de protocolo RTP viaje até outro ponto de extremidade e retorne. Tempos de viagem de ida e volta de 200 milissegundos ou menos são considerados de qualidade aceitável.</p>
<p>Os valores altos de tempo de resposta podem ser causados por roteamento de chamadas internacionais, configuração incorreta de um roteamento ou um servidor de mídia sobrecarregado. Tempos de resposta altos resultam em dificuldades para conversas de áudio bidirecionais e em tempo real.</p></td>
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

