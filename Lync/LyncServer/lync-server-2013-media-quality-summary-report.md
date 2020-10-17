---
title: 'Lync Server 2013: relatório de Resumo de qualidade de mídia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Media Quality Summary Report
ms:assetid: 8bd59ad6-3087-49c8-b692-5573fe2ffcd8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615012(v=OCS.15)
ms:contentKeyID: 48184776
ms.date: 06/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4080460083074f7ad74618034ab2e7910de5e53d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48516178"
---
# <a name="media-quality-summary-report-in-lync-server-2013"></a>Relatório de Resumo de qualidade de mídia no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2016-06-29_

O Relatório de resumo de qualidade de mídia é talvez a melhor maneira de analisar a qualidade das chamadas em sua organização: este relatório fornece métricas de chamada para Qualidade de Serviço (QoS) divididas nas seguintes categorias:

  - Chamadas ponto a ponto de UC (como uma chamada do Microsoft Lync 2013 para o Microsoft Lync 2013)

  - Sessões de Conferência de UC

  - Sessões de Conferência PSTN

  - Chamadas PSTN: Desvio de Mídia

  - Chamadas PSTN (Não Ignorar): Trecho de UC

  - Chamadas PSTN (Não Ignorar): Trecho de Gateway

  - Outros Tipos de Chamada

Ao abrir pela primeira vez o relatório, você verá informações resumidas para cada uma das categorias. Sem sair do relatório, você pode expandir cada categoria para examinar subcategorias como chamadas feitas do Office Communicator 2007 R2 para o Lync 2013. Por sua vez, você pode ver os detalhes de cada chamada feita dentro dessa subcategoria.

No Microsoft Lync Server 2013, o relatório de Resumo de qualidade de mídia divide ainda mais os dados em três tipos de chamadas: chamadas de áudio, chamadas de vídeo e chamadas de compartilhamento de aplicativos. Cada tipo de chamada tem sua própria seção no relatório, e seu próprio conjunto de métricas de chamadas.

O Relatório de resumo de qualidade de mídia também permite aplicar filtros que permitem comparar a qualidade de chamada de chamadas com fio em relação a chamadas sem fio, chamadas internas x chamadas externas e chamadas VPN x chamadas não VPN.

<div>

## <a name="accessing-the-media-quality-summary-report"></a>Como acessar o Relatório de resumo de qualidade de mídia

O Relatório de resumo de qualidade de mídia é acessado a partir da página inicial dos Relatórios de Monitoramento. Você pode fazer uma busca detalhada no [relatório de lista de chamadas no Lync Server 2013](lync-server-2013-call-list-report.md) clicando em uma das seguintes métricas:

  - Volume da chamada

  - Percentual de chamadas ruins

Além disso, você pode acessar o Relatório de distribuição de métricas de qualidade de mídia clicando em uma das seguintes métricas de chamada de áudio:

  - Viagem de ida e volta (ms)

  - Degradação (MOS)

  - Perda de pacote

  - Tremulação (ms)

  - Taxa de correção oculta

  - Taxa de correção estendida

  - Taxa de correção compactada

</div>

<div>

## <a name="filters"></a>Filtros

Filtros fornecem uma forma de retornar um conjunto de dados mais focado ou exibir os dados retornados de diferentes formas. Por exemplo, o Relatório de Resumo de Qualidade de Mídia permite filtrar os dados retornados por informações como tipo de acesso (ou seja, acesso interno vs. acesso externo) ou por conexão de rede com fio/sem fio. Você também pode escolher como os dados serão agrupados. Neste caso, as chamadas são agrupadas por hora, dia, semana ou mês.

A tabela a seguir lista os filtros que podem ser usados com o Relatório de Resumo de Qualidade de Mídia.

### <a name="media-quality-summary-report-filters"></a>Filtros do Relatório de Resumo de Qualidade de Mídia

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
<p>As semanas sempre vão de domingo a sábado.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Tipo de acesso</strong></p></td>
<td><p>Indica se um cliente estava conectado na rede interna ou na rede externa quando a chamada foi realizada. Selecione um dos seguintes:</p>
<ul>
<li><p>Todos os</p></li>
<li><p>Interno</p></li>
<li><p>Externo</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Tipo de rede</strong></p></td>
<td><p>Indica o tipo de rede que o cliente estava conectado quando a chamada foi realizada. Selecione um dos seguintes:</p>
<ul>
<li><p>Todos os</p></li>
<li><p>Com fio</p></li>
<li><p>Conexão</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>VPN</strong></p></td>
<td><p>Indica se um cliente externo estava usando uma conexão de rede privada virtual (VPN) quando a chamada foi realizada. Selecione um dos seguintes:</p>
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

A tabela a seguir lista as informações fornecidas no Relatório de Resumo de Qualidade de Mídia.

### <a name="media-quality-summary-report-metrics-audio-call-summary"></a>Métricas do Relatório de Resumo de Qualidade de Mídia: Resumo da chamada de áudio

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
<td><p><strong>Tipo de Chamada/Tipo de Ponto de Extremidade</strong></p></td>
<td><p>Não</p></td>
<td><p>Ao clicar neste item, o relatório mostra informações detalhadas sobre chamadas baseadas no tipo escolhido. Tipos de chamada incluem:</p>
<ul>
<li><p>Chamadas Ponto a Ponto de UC</p></li>
<li><p>Sessões de Conferência de UC</p></li>
<li><p>Sessões de Conferência PSTN</p></li>
<li><p>Chamadas PSTN: Desvio de Mídia</p></li>
<li><p>Chamadas PSTN (Não Ignorar): Trecho de UC</p></li>
<li><p>Chamadas PSTN (Não Ignorar): Trecho de Gateway</p></li>
<li><p>Outros Tipos de Chamada</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Volume da chamada</strong></p></td>
<td><p>Não</p></td>
<td><p>Número total de chamadas por tipo de chamada.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Percentual de chamadas ruins</strong></p></td>
<td><p>Não</p></td>
<td><p>Número total de chamadas classificadas como ruins. Uma chamada ruim é qualquer chamada em que no mínimo uma das métricas medidas excedeu o valor permitido (por exemplo, uma chamada com tremulação excessiva).</p></td>
</tr>
<tr class="even">
<td><p><strong>Volume de chamadas (chamadas sem fio)</strong></p></td>
<td><p>Não</p></td>
<td><p>Número total de chamadas que usaram uma conexão sem fio.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Volume de chamadas (chamadas VPN)</strong></p></td>
<td><p>Não</p></td>
<td><p>Número total de chamadas que usaram uma conexão VPN.</p></td>
</tr>
<tr class="even">
<td><p><strong>Volume de chamadas (chamadas externas)</strong></p></td>
<td><p>Não</p></td>
<td><p>Número de chamadas que usaram uma conexão externa (ou seja, uma conexão fora da rede interna).</p></td>
</tr>
<tr class="odd">
<td><p><strong>Tempo de resposta (ms)</strong></p></td>
<td><p>Não</p></td>
<td><p>Quantidade média (em milissegundos) necessária para um pacote de protocolo de transporte em tempo real (RTP) viajar para outro ponto de extremidade e voltar. Tempos de resposta de 100 milissegundos ou menos são considerados de qualidade aceitável.</p>
<p>Os valores altos de ida e volta pode ser causados por roteamento de chamada internacional, um erro de configuração de roteamento ou um servidor de mídia sobrecarregado. Tempos de ida e volta altos resultam em dificuldades com conversas de áudio em tempo real e bidirecionais.</p></td>
</tr>
<tr class="even">
<td><p><strong>Degradação (MOS)</strong></p></td>
<td><p>Não</p></td>
<td><p>Quantidade média de degradação MOS (pontuação média de opinião) experimentada durante uma chamada. Os valores de degradação variam de um baixo de 0,0 a um alto de 5,0. Um valor de 0,5 ou menos representa degradação aceitável. Historicamente, pontuações de opções médias foram calculadas com usuários classificando a qualidade de uma chamada em uma escala de 1 a 5. No Lync Server, o Lync Server usa um conjunto de algoritmos para prever como os usuários classificaram uma chamada.</p>
<p>Os valores de degradação altos podem ser causados por congestão, falta de largura de banda, congestionamento ou interferência sem fio ou um servidor de mídia ou ponto de extremidade sobrecarregado. A alta degradação resulta em perda ou distorção de áudio.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Perda de pacote </strong></p></td>
<td><p>Não</p></td>
<td><p>Taxa média de perda de pacotes RTP (a perda de pacotes acontece quando pacotes RTP, um protocolo usado para transmitir áudio e vídeo pela Internet, falha ao tentar alcançar seu destino). Altas taxas de perda geralmente são causadas por congestionamento, insuficiência da largura de banda, congestionamento ou interferência da rede sem fio ou um servidor de mídia sobrecarregado. A perda de pacotes normalmente resulta em distorção ou perda do áudio.</p></td>
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
<td><p>Taxa média de amostras de áudio compactadas para o número total de amostras (áudio compactado é o áudio que foi comprimido para ajudar a manter a qualidade da chamada quando um pacote de rede ignorado foi detectado). Altos valores indicam níveis significativos de compressão de amostras causados por tremulação, o que resulta em áudio acelerado ou distorcido.</p></td>
</tr>
</tbody>
</table>


### <a name="media-quality-summary-report-metrics-video-call-summary"></a>Métricas do Relatório de Resumo de Qualidade de Mídia: Resumo da chamada de vídeo

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
<td><p><strong>Tipo de Chamada/Tipo de Ponto de Extremidade</strong></p></td>
<td><p>Não</p></td>
<td><p>Ao clicar neste item, o relatório mostra informações detalhadas sobre chamadas baseadas no tipo escolhido. Tipos de chamada incluem:</p>
<ul>
<li><p>Chamadas Ponto a Ponto de UC</p></li>
<li><p>Sessões de Conferência de UC</p></li>
<li><p>Sessões de Conferência PSTN</p></li>
<li><p>Chamadas PSTN: Desvio de Mídia</p></li>
<li><p>Chamadas PSTN (Não Ignorar): Trecho de UC</p></li>
<li><p>Chamadas PSTN (Não Ignorar): Trecho de Gateway</p></li>
<li><p>Outros Tipos de Chamada</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Volume da chamada</strong></p></td>
<td><p>Não</p></td>
<td><p>Número total de chamadas por tipo de chamada.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Percentual de chamadas ruins</strong></p></td>
<td><p>Não</p></td>
<td><p>Número total de chamadas classificadas como ruins. Uma chamada ruim é qualquer chamada em que no mínimo uma das métricas medidas excedeu o valor permitido (por exemplo, uma chamada com tremulação excessiva).</p></td>
</tr>
<tr class="even">
<td><p><strong>Volume de chamadas (chamadas sem fio)</strong></p></td>
<td><p>Não</p></td>
<td><p>Número total de chamadas que usaram uma conexão sem fio.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Volume de chamadas (chamadas VPN)</strong></p></td>
<td><p>Não</p></td>
<td><p>Número total de chamadas que usaram uma conexão VPN.</p></td>
</tr>
<tr class="even">
<td><p><strong>Volume de chamadas (chamadas externas)</strong></p></td>
<td><p>Não</p></td>
<td><p>Número de chamadas que usaram uma conexão externa (ou seja, uma conexão fora da rede interna).</p></td>
</tr>
<tr class="odd">
<td><p><strong>Taxa de bits média (Kbits/s)</strong></p></td>
<td><p>Não</p></td>
<td><p>Taxa de bits média (em quilobytes por segundo).</p></td>
</tr>
<tr class="even">
<td><p><strong>% de taxa de bits baixa</strong></p></td>
<td><p>Não</p></td>
<td><p>Porcentagem da chamada onde a taxa de bits foi baixa.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Perda de pacote de saída</strong></p></td>
<td><p>Não</p></td>
<td><p>Perda de pacotes do Protocolo de transporte em tempo real (RTP) para pacotes enviados. (A perda de pacotes ocorre quando pacotes RTP, um protocolo usado para transmitir áudio e vídeo pela internet, falha ao tentar alcançar seu destino). Altas taxas de perda geralmente são causadas por congestionamento, insuficiência da largura de banda, congestionamento ou interferência na rede sem fio ou um servidor de mídia sobrecarregado. A perda de pacotes normalmente resulta em distorção ou perda de áudio.</p></td>
</tr>
<tr class="even">
<td><p><strong>% de quadros congelados</strong></p></td>
<td><p>Não</p></td>
<td><p>Porcentagem de quadros "congelados". Em um quadro congelado, o vídeo não avança enquanto a parte de áudio da chamada prossegue.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Taxa de quadros média de saída</strong></p></td>
<td><p>Não</p></td>
<td><p>Taxa de quadros média para transmissões de saída durante a chamada.</p></td>
</tr>
<tr class="even">
<td><p><strong>Taxa de quadros média de entrada</strong></p></td>
<td><p>Não</p></td>
<td><p>Taxa de quadros média para transmissões de entrada durante a chamada.</p></td>
</tr>
<tr class="odd">
<td><p><strong>% de taxa de quadros baixa de entrada</strong></p></td>
<td><p>Não</p></td>
<td><p>Porcentagem da chamada onde a taxa de bits foi baixa para vídeo de entrada.</p></td>
</tr>
<tr class="even">
<td><p><strong>% de integridade do cliente</strong></p></td>
<td></td>
<td><p>Indica o estado relativo do dispositivo do cliente durante a chamada.</p></td>
</tr>
</tbody>
</table>


### <a name="media-quality-summary-report-metrics-application-sharing-call-summary"></a>Métricas do Relatório de resumo de qualidade de mídia: Resumo de chamada de compartilhamento de aplicativos

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
<td><p><strong>Tipo de Chamada/Tipo de Ponto de Extremidade</strong></p></td>
<td><p>Não</p></td>
<td><p>Ao clicar neste item, o relatório mostra informações detalhadas sobre chamadas baseadas no tipo escolhido. Tipos de chamada incluem:</p>
<ul>
<li><p>Chamadas Ponto a Ponto de UC</p></li>
<li><p>Sessões de Conferência de UC</p></li>
<li><p>Sessões de Conferência PSTN</p></li>
<li><p>Chamadas PSTN: Desvio de Mídia</p></li>
<li><p>Chamadas PSTN (Não Ignorar): Trecho de UC</p></li>
<li><p>Chamadas PSTN (Não Ignorar): Trecho de Gateway</p></li>
<li><p>Outros Tipos de Chamada</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Volume da chamada</strong></p></td>
<td><p>Não</p></td>
<td><p>Número total de chamadas por tipo de chamada.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Percentual de chamadas ruins</strong></p></td>
<td><p>Não</p></td>
<td><p>Número total de chamadas classificadas como ruins. Uma chamada ruim é qualquer chamada em que no mínimo uma das métricas medidas excedeu o valor permitido (por exemplo, uma chamada com tremulação excessiva).</p></td>
</tr>
<tr class="even">
<td><p><strong>Volume de chamadas (chamadas sem fio)</strong></p></td>
<td><p>Não</p></td>
<td><p>Número total de chamadas que usaram uma conexão sem fio.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Volume de chamadas (chamadas VPN)</strong></p></td>
<td><p>Não</p></td>
<td><p>Número total de chamadas que usaram uma conexão VPN.</p></td>
</tr>
<tr class="even">
<td><p><strong>Volume de chamadas (chamadas externas)</strong></p></td>
<td><p>Não</p></td>
<td><p>Número de chamadas que usaram uma conexão externa (ou seja, uma conexão fora da rede interna).</p></td>
</tr>
<tr class="odd">
<td><p><strong>Tremulação (ms)</strong></p></td>
<td><p>Não</p></td>
<td><p>Tremulação média detectada entre chegadas de pacote RTP. (Tremulação é uma medida do &quot; tremula &quot; de uma chamada.) Os valores de variação alta geralmente são causados por congestionamento ou por um servidor de mídia sobrecarregado e resultam em um áudio distorcido ou perdido.</p></td>
</tr>
<tr class="even">
<td><p><strong>Unidirecional relativo médio</strong></p></td>
<td><p>Não</p></td>
<td><p>Atraso unidirecional relativo médio entre dois pontos de extremidade de mídia. Esta é uma medida de latência de salto único.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Latência média de processamento lado a lado RDP</strong></p></td>
<td><p>Não</p></td>
<td><p>A latência média de processamento lado a lado RDP no Servidor de Conferência AS durante a sessão de visualização. Uma média alta reflete um atraso maior na experiência de visualização e inclui latência de rede. Um servidor de conferência sobrecarregado pode enfrentar atrasos médios maiores.</p></td>
</tr>
<tr class="even">
<td><p><strong>% total de lado a lado estragado</strong></p></td>
<td><p>Não</p></td>
<td><p>A porcentagem total de lado a lado estragados.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

