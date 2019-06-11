---
title: 'Lync Server 2013: relatório de lista de chamadas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Call List Report
ms:assetid: 9739f9f0-7a37-4844-91d5-f089d2011013
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615020(v=OCS.15)
ms:contentKeyID: 48184921
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: faf330a776f64534c02833a0472cfefea7f0998e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836706"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-list-report-in-lync-server-2013"></a>Relatório de lista de chamadas no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-01_

O Relatório de Lista de Chamadas fornece métricas de QoE (qualidade da experiência) para chamadas individuais feitas e recebidas em sua organização. Observe que as métricas reais relatadas dependem de como você acessa o relatório de Lista de Chamadas. Por exemplo, se você abrir o relatório do [relatório de dispositivos no Lync Server 2013](lync-server-2013-device-report.md), verá métricas como as métricas a seguir, que também são relatadas no relatório do dispositivo:

  - Microfone do chamador

  - Alto-falante do chamador

  - Microfone do receptor

  - Alto-falante do receptor

  - Tempo de troca da taxa de voz

No entanto, se você abrir o relatório de lista de chamadas do [relatório de localização no Lync Server 2013](lync-server-2013-location-report.md), não verá nenhuma dessas métricas; em vez disso, você verá métricas como estas:

  - Ida e volta (ms)

  - Degradação (MOS)

  - Perda de pacote

  - Tremulação (ms)

Há métricas relatadas no Relatório de Local. Entretanto, a partir do Relatório de Lista de Chamadas, é sempre possível clicar na métrica Detalhe para fornecer informações completas de QoE de qualquer chamada.

<div>

## <a name="accessing-the-call-list-report"></a>Como acessar o Relatório de Lista de Chamadas

O Relatório de Lista de Chamadas pode ser acessado de qualquer um dos seguintes relatórios:

  - O [relatório de localização no Lync Server 2013](lync-server-2013-location-report.md) (clicando no volume da chamada ou na métrica de porcentagem baixa de chamada)

  - O [relatório de dispositivo no Lync Server 2013](lync-server-2013-device-report.md) (clicando no volume da chamada ou na métrica de porcentagem baixa de chamada)

  - O [relatório de Resumo de qualidade de mídia no Lync Server 2013](lync-server-2013-media-quality-summary-report.md) (clicando no volume da chamada ou na métrica de porcentagem baixa de chamada)

  - O [relatório de desempenho do servidor no Lync Server 2013](lync-server-2013-server-performance-report.md) (clicando no volume da chamada ou na métrica de porcentagem baixa de chamada)

No relatório de lista de chamadas, você pode acessar o [relatório de detalhes de chamadas no Lync Server 2013](lync-server-2013-call-detail-report.md) clicando na métrica de detalhes.

</div>

<div>

## <a name="making-the-best-use-of-the-call-list-report"></a>Como usar melhor o Relatório de Lista de Chamada

Se não conseguir se lembrar o que algumas das métricas do Relatório de Lista de Chamada (como o Tempo de troca da taxa de voz) realmente medem, coloque o mouse sobre o rótulo da métrica; uma dica de ferramenta aparecerá fornecendo uma breve descrição da métrica.

</div>

<div>

## <a name="filters"></a>Filtros

Nenhum. Não é possível filtrar o Relatório de Lista de Chamadas.

</div>

<div>

## <a name="metrics"></a>Métricas

A tabela a seguir lista as informações detalhadas fornecidas no Relatório de Lista de Chamadas para cada chamada.

### <a name="call-list-report-metrics"></a>Métricas do Relatório de Lista de Chamadas

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
<td><p><strong>Detalhes</strong></p></td>
<td><p>Não</p></td>
<td><p>Ao clicar neste item, o relatório exibe informações adicionais sobre a chamada.</p></td>
</tr>
<tr class="even">
<td><p><strong>Chamador</strong></p></td>
<td><p>Sim</p></td>
<td><p>Endereço SIP da pessoa que iniciou a chamada.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Receptor</strong></p></td>
<td><p>Sim</p></td>
<td><p>Endereço SIP da pessoa que recebeu a chamada.</p></td>
</tr>
<tr class="even">
<td><p><strong>Hora inicial</strong></p></td>
<td><p>Sim</p></td>
<td><p>Data e horário em que a chamada teve início.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Hora de término</strong></p></td>
<td><p>Sim</p></td>
<td><p>Data e horário em que a chamada terminou.</p></td>
</tr>
<tr class="even">
<td><p><strong>Agente do usuário do chamador</strong></p></td>
<td><p>Sim</p></td>
<td><p>Software usado pelo ponto de extremidade da pessoa que iniciou a chamada.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Agente do usuário do receptor</strong></p></td>
<td><p>Sim</p></td>
<td><p>Software usado pelo ponto de extremidade da pessoa que recebeu a chamada.</p></td>
</tr>
<tr class="even">
<td><p><strong>Ida e volta (ms)</strong></p></td>
<td><p>Sim</p></td>
<td><p>Quantidade média de (em milissegundos) exigida para que um pacote RTP (protocolo de transporte em tempo real) viaje até outra extremidade e retorne. Tempos de viagem de ida e volta de 100 milissegundos ou menos são considerados de qualidade aceitável.</p>
<p>Os valores altos de ida e volta pode ser causados por roteamento de chamada internacional, um erro de configuração de roteamento ou um servidor de mídia sobrecarregado. Tempos de ida e volta altos resultam em dificuldades com conversas de áudio em tempo real e bidirecionais.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Degradação (MOS)</strong></p></td>
<td><p>Sim</p></td>
<td><p>Quantidade média da degradação MOS (pontuação média de opinião) enfrentada durante uma chamada. Os valores de degradação variam de um baixo de 0,0 a um alto de 5,0. Um valor de 0,5 ou menos representa degradação aceitável. As pontuações médias de opinião costumava ser calculadas a partir da classificação da qualidade de uma chamada em uma escala de 1 a 5, feita pelos dos usuários. No Lync Server, o Lync Server usa um conjunto de algoritmos para prever como os usuários teriam classificado uma chamada.</p>
<p>Os valores de degradação altos podem ser causados por congestão, falta de largura de banda, congestionamento ou interferência sem fio ou um servidor de mídia ou ponto de extremidade sobrecarregado. A alta degradação resulta em perda ou distorção de áudio.</p></td>
</tr>
<tr class="even">
<td><p><strong>Perda de pacote</strong></p></td>
<td><p>Sim</p></td>
<td><p>Taxa média de perda de pacote RTP. (A perda de pacote ocorre quando os pacotes RTP, um protocolo usado para transmissão de áudio e vídeo pela Internet, não conseguem chegar aos seus destinos.) Taxas de perda altas normalmente são causadas por congestionamento, falta de largura de banda, congestionamento ou interferência sem fio ou um servidor de mídia sobrecarregado. A perda de pacote normalmente resulta em perda ou distorção de áudio.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Tremulação</strong></p></td>
<td><p>Sim</p></td>
<td><p>Tremulação média detectada entre chegadas de pacote RTP. (Tremulação é uma medida do &quot;shakiness&quot; de uma chamada.) Os valores de variação alta geralmente são causados por congestionamento ou um servidor de mídia sobrecarregado, resultando em áudio distorcido ou perdido.</p></td>
</tr>
<tr class="even">
<td><p><strong>Taxa de correção oculta</strong></p></td>
<td><p>Sim</p></td>
<td><p>Taxa média de amostras de áudio ocultas para o número total de amostras. (Uma amostra de áudio oculta é uma técnica usada para suavizar a transição abrupta que normalmente seria causada por pacotes de rede descartados.) Valores altos indicam níveis consideráveis de perda de ocultação aplicada causada por perda de pacote ou tremulação e resulta na perda ou distorção de áudio.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Taxa de correção estendida</strong></p></td>
<td><p>Sim</p></td>
<td><p>Taxa média de amostras de áudio estendidas para o número total de amostras. (Áudio estendido é o áudio que foi expandido a fim de ajudar a manter a qualidade da chamada quando um pacote de rede descartado é detectado.) Valores altos indicam níveis significativos de extensão de amostra causada por tremulação e resultam em um som robótico ou distorcido.</p></td>
</tr>
<tr class="even">
<td><p><strong>Taxa de correção compactada</strong></p></td>
<td><p>Sim</p></td>
<td><p>Taxa média de amostras de áudio compactadas para o número total de amostras. (Áudio compactado é o áudio que foi compactado para ajudar a manter a qualidade da chamada quando um pacote de rede descartado é detectado.) Valores altos podem indicar níveis consideráveis de compactação de amostra causada por tremulação e resultam em um som acelerado ou distorcido.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Conectividade</strong></p></td>
<td><p>Sim</p></td>
<td><p>Tipo de link de comunicação sem fio. Normalmente é um dos seguintes:</p>
<ul>
<li><p>Retransmissão</p></li>
<li><p>Direto</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

