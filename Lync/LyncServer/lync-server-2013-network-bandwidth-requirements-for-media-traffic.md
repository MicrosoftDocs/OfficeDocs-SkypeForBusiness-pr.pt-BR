---
title: Requisitos de largura de banda de rede do Lync Server 2013 para tráfego de mídia
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Network bandwidth requirements for media traffic
ms:assetid: 83e83b16-0f0e-4d87-901a-0faa4618cdc2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688118(v=OCS.15)
ms:contentKeyID: 49733716
ms.date: 09/25/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 684f13a10c066e8902bed0024d7546017450ee9e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765922"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="network-bandwidth-requirements-for-media-traffic-in-lync-server-2013"></a>Requisitos de largura de banda de rede para tráfego de mídia no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2015-09-24_

Uma parte importante do planejamento de rede é garantir que sua rede possa manipular o tráfego de mídia gerado pelo Lync Server. Esta seção ajuda a você a se planejar para esse tráfego.

<div>

## <a name="media-traffic-network-usage"></a>Uso da rede de tráfego de mídia

O cálculo do uso da largura de banda do tráfego de mídia pode ser desafiador devido às diferentes variáveis, como o uso de codec, resolução e níveis de atividade. O uso da largura de banda é uma função do codec usado e da atividade do fluxo, que varia de acordo com os cenários. A tabela a seguir lista os codecs de áudio comumente usados nos cenários do Lync Server 2013.

### <a name="audio-codec-bandwidth"></a>Largura de banda do codec de áudio

<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th>Codec de áudio</th>
<th>Cenários</th>
<th>Taxa de bits de carga de áudio (KBPS)</th>
<th>Apenas carga de áudio da largura de banda e cabeçalho IP (Kbps)</th>
<th>Carga de áudio da largura de banda, cabeçalho IP, UDP, RTP e SRTP (Kbps)</th>
<th>Carga de áudio da largura de banda, cabeçalho IP, UDP, RTP, SRTP e correção de erro de encaminhamento (Kbps)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Banda ampla RTAudio</p></td>
<td><p>Ponto a ponto</p></td>
<td><p>29,0</p></td>
<td><p>45,0</p></td>
<td><p>57,0</p></td>
<td><p>86,0</p></td>
</tr>
<tr class="even">
<td><p>Banda estreita RTAudio</p></td>
<td><p>Ponto a ponto, PSTN</p></td>
<td><p>11,8</p></td>
<td><p>27,8</p></td>
<td><p>39,8</p></td>
<td><p>51,6</p></td>
</tr>
<tr class="odd">
<td><p>G.722</p></td>
<td><p>Conferência</p></td>
<td><p>64,0</p></td>
<td><p>80,0</p></td>
<td><p>95,6</p></td>
<td><p>159,6</p></td>
</tr>
<tr class="even">
<td><p>Estéreo G.722</p></td>
<td><p>Conferência ponto a ponto, conferência</p></td>
<td><p>128,0</p></td>
<td><p>144,0</p></td>
<td><p>159,6</p></td>
<td><p>223,6</p></td>
</tr>
<tr class="odd">
<td><p>G.711</p></td>
<td><p>Conferência PSTN</p></td>
<td><p>64,0</p></td>
<td><p>80,0</p></td>
<td><p>92,0</p></td>
<td><p>156,0</p></td>
</tr>
<tr class="even">
<td><p>Siren</p></td>
<td><p>Conferência</p></td>
<td><p>16,0</p></td>
<td><p>32,0</p></td>
<td><p>47,6</p></td>
<td><p>63,6</p></td>
</tr>
</tbody>
</table>


Os números de largura de banda na tabela anterior são baseados em pacotes de 20ms (pacotes de 50 por segundo) e para sirene e G. 722 incluem a sobrecarga do SRTP (protocolo de transporte em tempo real seguro) adicional dos cenários de conferência e presume-se que o fluxo é 100% ativo. A correção de erro antecipada (FEC) é usada dinamicamente quando há perda de pacote no link para ajudar a manter a qualidade do fluxo de áudio.

A versão estéreo do codec G. 722 é usada por sistemas baseados no sistema de salas do Lync, que permite que os ouvintes estéreos diferenciem melhor vários falantes na sala de reunião.

Para vídeo, o codec padrão é o padrão de codificação de vídeo de H. 264/MPEG-4 parte 10 avançado juntamente com suas extensões de codificação de vídeo escaláveis para escalação temporal. Para manter a interoperabilidade com o Lync 2010 ou os clientes do Office Communicator 2007 R2, o codec RTVideo ainda é usado para chamadas ponto a ponto entre o Lync 2013 e clientes herdados. Em sessões de conferência com ambos, Lync 2013 e clientes herdados, o Lync 2013 Endpoint pode codificar o vídeo usando os dois codecs de vídeo e enviar o H. 264 Bitstream para o Lync 2013 e o RTVideo Bitstream para o Lync 2010 ou o Office Communicator 2007 clientes R2.

A largura de banda necessária depende da resolução, da qualidade e da taxa de quadros. Para cada resolução, há duas tarifas de bits interessantes:

  - **Taxa de bits**   máxima de Payload esta é a taxa de bits que um ponto de extremidade do Lync 2013 usará para resolução na taxa de quadros máxima com suporte para essa resolução. Esse valor é interessante porque permite o vídeo de melhor qualidade e taxa de quadros.

  - **Taxa de bits**   de carga mínima esta é a taxa de bits abaixo da qual um ponto de extremidade do Lync 2013 mudará para a próxima resolução inferior. Para garantir uma determinada resolução, a taxa de bits de carga de vídeo disponível não deve ficar abaixo dessa taxa de bits mínima para essa resolução. Esse valor é interessante para que você possa entender o menor valor possível em casos em que a taxa de bits máxima não está disponível ou é prática. Para alguns usuários, um vídeo de baixa taxa de bits pode ser considerado uma experiência de vídeo inaceitável, portanto tome cuidado ao considerar essas taxas mínimas de payload de vídeo. Observe que, para cenas de vídeo, com pouca ou nenhuma movimentação do usuário, a taxa de bits real também pode ficar abaixo da taxa de bits mínima.

O Lync 2013 oferece suporte a muitos mais resoluções. Isso permite que você melhor ajuste para diferentes largura de banda de rede e recursos de cliente de recebimento. Além disso, a taxa de proporção padrão do Lync 2013 foi alterada para 16:9. A taxa de proporção de 4:3 ainda tem suporte para webcams que não permitem a captura na taxa de proporção do 16:9.

### <a name="video-resolution-bandwidth"></a>Largura de banda da resolução do vídeo

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Codec de vídeo</th>
<th>Resolução e taxa de proporção</th>
<th>Taxa de bits máxima de carga de vídeo (Kbps)</th>
<th>Taxa de bits de carga de vídeo mínima (Kbps)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>H.264</p></td>
<td><p>320 x 180 (16:9)</p>
<p>212 x 160 (4:3)</p></td>
<td><p>250</p></td>
<td><p>15</p></td>
</tr>
<tr class="even">
<td><p>H.264/RTVideo</p></td>
<td><p>424 x 240 (16:9)</p>
<p>320 x 240 (4:3)</p></td>
<td><p>350</p></td>
<td><p>100</p></td>
</tr>
<tr class="odd">
<td><p>H.264</p></td>
<td><p>480 x 270 (16:9)</p>
<p>424 x 320 (4:3)</p></td>
<td><p>450</p></td>
<td><p>200</p></td>
</tr>
<tr class="even">
<td><p>H.264/RTVideo</p></td>
<td><p>640 x 360 (16:9)</p>
<p>640 x 480 (4:3)</p></td>
<td><p>800</p></td>
<td><p>300</p></td>
</tr>
<tr class="odd">
<td><p>H.264</p></td>
<td><p>848 x 480 (16:9)</p></td>
<td><p>1500</p></td>
<td><p>400</p></td>
</tr>
<tr class="even">
<td><p>H.264</p></td>
<td><p>960 x 540 (16:9)</p></td>
<td><p>2000</p></td>
<td><p>500</p></td>
</tr>
<tr class="odd">
<td><p>H.264/RTVideo</p></td>
<td><p>1280 x 720 (16:9)</p></td>
<td><p>2500</p></td>
<td><p>700</p></td>
</tr>
<tr class="even">
<td><p>H.264</p></td>
<td><p>1920 x1080 (16:9)</p></td>
<td><p>4000</p></td>
<td><p>1500</p></td>
</tr>
<tr class="odd">
<td><p>H.264/RTVideo</p></td>
<td><p>960 x 144 (20:3)</p></td>
<td><p>500</p></td>
<td><p>15</p></td>
</tr>
<tr class="even">
<td><p>H.264</p></td>
<td><p>1280 x 192 (20:3)</p></td>
<td><p>1000</p></td>
<td><p>250</p></td>
</tr>
<tr class="odd">
<td><p>H.264</p></td>
<td><p>1920 x 288 (20:3)</p></td>
<td><p>2000</p></td>
<td><p>500</p></td>
</tr>
</tbody>
</table>


Vídeo FEC está incluído na taxa de bits de carga de vídeo quando ele é usado, portanto, não há valores separados com vídeo FEC e sem vídeo FEC.

Os pontos de extremidade não transmitem pacotes de áudio ou vídeo continuamente. De acordo com o cenário, existem níveis diferentes de atividade de fluxo que indicam a frequência com que os pacotes são enviados para um fluxo. A atividade de um fluxo depende da mídia e do cenário e não depende do codec que está sendo usado. Em um cenário ponto a ponto:

  - Os pontos de extremidade enviam fluxos de áudio apenas quando os usuários falam.

  - Ambos os participantes recebem fluxos de áudio.

  - Se o vídeo for usado, os dois pontos de extremidade enviarão e receberão fluxos de vídeo durante toda a chamada.

  - Em cenas de vídeo com pouca ou nenhuma movimentação, a taxa de bits real pode estar temporariamente muito baixa, pois o codec de vídeo ignorará a codificação de regiões do vídeo sem alteração.

Em um cenário de conferência:

  - Os pontos de extremidade enviam fluxos de áudio apenas quando os usuários falam.

  - Todos os participantes recebem fluxos de áudio.

  - Se o vídeo for usado, todos os participantes podem receber até cinco fluxos de vídeo e um fluxo de vídeo panorâmico (por exemplo, taxa de proporção 20:3). Por padrão, os cinco fluxos de vídeo têm base no histórico do orador ativo, mas os usuários também podem selecionar manualmente os participantes de quem eles desejam receber fluxo de vídeo.

  - Cada participante que usar o fluxo de vídeo de envio do usuário enviará um ou mais fluxos de vídeo. O Lync 2013 adiciona a funcionalidade de enviar até cinco fluxos de vídeo para otimizar a qualidade de vídeo para todos os clientes de recebimento. A quantidade real de fluxos de vídeo enviados é determinada pelo remetente com base na capacidade da CPU, na largura de banda uplink disponível e na quantidade de clientes receptores que tenham selecionado um determinado fluxo de vídeo. O mais comum são os fluxos de vídeo H.264 e RTVideo enviados em caso de presença de clientes herdados na conferência. Outro cenário comum é o envio de diversos fluxos de vídeo H.264 (por exemplo, com a mesma resolução de vídeo) para acomodação de diferentes solicitações do receptor.

Além da largura de banda necessária para o tráfego do protocolo de transporte em tempo real (RTP) para mídia em áudio e vídeo, a largura de banda é necessária também para o protocolo de controle de transporte em tempo real (RTCP). O RTCP é usado para obter estatísticas e controle fora da banda para o fluxo RTP. Para fins de planejamento, use os números de largura de banda da tabela a seguir para verificar o tráfego RTCP. Esses valores representam a largura de banda máxima usada para RTCP e são diferentes entre fluxos de áudio e vídeo devido a diferenças nos dados de controle

### <a name="rtcp-bandwidth"></a>Largura de banda de RTCP

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Mídia</th>
<th>Largura de banda máxima de RTCP (Kbps)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Áudio</p></td>
<td><p>5</p></td>
</tr>
<tr class="even">
<td><p>Vídeo (somente H.264 ou RTVideo enviado/recebido)</p></td>
<td><p>254</p></td>
</tr>
<tr class="odd">
<td><p>Vídeo (somente H.264 ou RTVideo enviado/recebido)</p></td>
<td><p>15</p></td>
</tr>
</tbody>
</table>


Para fins de planejamento da capacidade, as duas seguintes larguras de banda são de interesse:

  - **Largura de banda máxima sem FEC**   a largura de banda máxima que um fluxo consumirá, incluindo a atividade típica do fluxo e o codec típico usado no cenário sem FEC.Trata-se da largura de banda quando o fluxo está 100% em atividade e não há perda de pacote que gere uso de FEC.Isso é interessante para a computação da quantidade de largura de banda que deve ser alocada para permitir que o codec seja usado em um determinado cenário. 

  - **Largura de banda máxima com FEC**   a largura de banda máxima que um fluxo consome, incluindo a atividade típica do fluxo e o codec típico usado no cenário com FEC. Trata-se da largura de banda quando o fluxo está 100% em atividade e há perda de pacote que gere uso de FEC para aprimorar a qualidade. Isso é interessante para a computação da quantidade de largura de banda que deve ser alocada para permitir que o codec seja usado em um determinado cenário e permitir o uso do FEC para preservar a qualidade em condições de perda de pacote. 

A tabela a seguir também lista outro valor da largura de banda, a **Largura de banda típica**. Esta é a largura de banda média que um fluxo consome, incluindo a atividade típica do fluxo e o codec típico usado no cenário. Essa largura de banda pode ser usada para approximating a quantidade de largura de banda a qualquer momento é consumida pelo tráfego de mídia, mas não deve ser usada para o planejamento da capacidade, pois as chamadas individuais excederão esse valor quando o nível da atividade for maior que a média. A largura de banda de fluxo de vídeo típica nas tabelas abaixo baseia-se em uma combinação de diferentes resoluções de vídeo, conforme observado em dados medidos do cliente. Por exemplo, em sessões ponto a ponto, a maioria dos usuários usaria a janela de renderização de vídeo padrão, enquanto uma porcentagem de usuários aumentaria ou maximizaria o aplicativo Lync para permitir resoluções de vídeo mais altas.

As tabelas a seguir fornecem esses três valores de largura de banda para os vários cenários.

### <a name="audiovideo-capacity-planning-for-peer-to-peer-sessions"></a>Planejamento da capacidade de áudio/vídeo em sessões ponto a ponto

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>Mídia</th>
<th>Codec</th>
<th>Largura de banda de fluxo típico (Kbps)</th>
<th>Largura de banda de fluxo máximo sem FEC</th>
<th>Largura de banda de fluxo máximo com FEC</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Áudio</p></td>
<td><p>Banda ampla RTAudio</p></td>
<td><p>39,8</p></td>
<td><p>62</p></td>
<td><p>91</p></td>
</tr>
<tr class="even">
<td><p>Áudio</p></td>
<td><p>Banda estreita RTAudio</p></td>
<td><p>29,3</p></td>
<td><p>44,8</p></td>
<td><p>56,6</p></td>
</tr>
<tr class="odd">
<td><p>Vídeo principal ao ligar para pontos de extremidade do Lync 2013</p></td>
<td><p>H.264</p></td>
<td><p>460</p></td>
<td><p>4010 (para resolução máxima de 1920 x 1080)</p></td>
<td><p>Não aplicável</p></td>
</tr>
<tr class="even">
<td><p>Vídeo principal ao ligar para os pontos de extremidade do Lync 2010 ou do Office Communicator 2007 R2</p></td>
<td><p>RTVideo</p></td>
<td><p>460</p></td>
<td><p>2510 (para resolução máxima de 1280 x 720)</p></td>
<td><p>Não aplicável</p></td>
</tr>
<tr class="odd">
<td><p>Vídeo panorâmico ao ligar para pontos de extremidade do Lync 2013</p></td>
<td><p>H.264</p></td>
<td><p>190</p></td>
<td><p>2010 (para resolução máxima de 1920 x 288)</p></td>
<td><p>Não aplicável</p></td>
</tr>
<tr class="even">
<td><p>Vídeo panorâmico ao ligar para os pontos de extremidade do Lync 2010 ou do Office Communicator 2007 R2</p></td>
<td><p>RTVideo</p></td>
<td><p>190</p></td>
<td><p>510 (para resolução máxima de 960 x 144)</p></td>
<td><p>Não aplicável</p></td>
</tr>
</tbody>
</table>


### <a name="audiovideo-capacity-planning-for-conferences"></a>Planejamento de capacidade de áudio/vídeo para conferências

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>Mídia</th>
<th>Codec típico</th>
<th>Largura de banda de fluxo típico (Kbps)</th>
<th>Largura de banda de fluxo máximo sem FEC</th>
<th>Largura de banda de fluxo máximo com FEC</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Áudio</p></td>
<td><p>G.722</p></td>
<td><p>46,1</p></td>
<td><p>100,6</p></td>
<td><p>164,6</p></td>
</tr>
<tr class="even">
<td><p>Áudio</p></td>
<td><p>Siren</p></td>
<td><p>25,5</p></td>
<td><p>52,6</p></td>
<td><p>68,6</p></td>
</tr>
<tr class="odd">
<td><p>Recepção de vídeo principal</p></td>
<td><p>H. 264 e/ou RTVideo</p></td>
<td><p>260</p></td>
<td><p>8015</p></td>
<td><p>Não aplicável</p></td>
</tr>
<tr class="even">
<td><p>Envio de vídeo principal</p></td>
<td><p>H. 264 e/ou RTVideo</p></td>
<td><p>270</p></td>
<td><p>8015</p></td>
<td><p>Não aplicável</p></td>
</tr>
<tr class="odd">
<td><p>Recepção de vídeo panorâmico</p></td>
<td><p>H. 264 e/ou RTVideo</p></td>
<td><p>190</p></td>
<td><p>2010 (para resolução máxima de 1920 x 288)</p></td>
<td><p>Não aplicável</p></td>
</tr>
<tr class="even">
<td><p>Envio de vídeo panorâmico</p></td>
<td><p>H. 264 e/ou RTVideo</p></td>
<td><p>190</p></td>
<td><p>2515 (para envio de bitstreams usando várias resoluções/codecs</p></td>
<td><p>Não aplicável</p></td>
</tr>
</tbody>
</table>


Para o vídeo principal, a largura de banda de fluxo típica e máxima é a largura de banda agregada em todos os fluxos de vídeo recebidos e todos os fluxos de vídeo de envio, respectivamente. Mesmo com vários fluxos de vídeo, a largura de banda de vídeo típica é menor do que no cenário ponto a ponto, pois muitas conferências de vídeo estão usando o compartilhamento de conteúdo que leva a janelas de vídeo muito menores e, portanto, resoluções de vídeo menores. A largura de banda máxima de carga de vídeo agregada com suporte é de 8000 kbps para os fluxos de envio e recebimento, que seriam usados por exemplo, se houver dois fluxos de vídeo 1920x1080p de entrada.

A largura de banda do fluxo típico para o vídeo panorâmico é baseada em dispositivos atualmente disponíveis que só transmitem para vídeos panorâmicos do 960x144. Depois que os dispositivos com 1920x288 de vídeo panorâmico estiverem disponíveis, espera-se que o aumento da largura de banda do fluxo típico.

### <a name="audio-capacity-planning-for-pstn"></a>Planejamento de capacidade de áudio para PSTN

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>Mídia</th>
<th>Codec típico</th>
<th>Largura de banda de fluxo típico (Kbps)</th>
<th>Largura de banda de fluxo máximo sem FEC</th>
<th>Largura de banda de fluxo máximo com FEC</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Áudio</p></td>
<td><p>G. 711 (inclui participantes PSTN em conferências)</p></td>
<td><p>64,8</p></td>
<td><p>97</p></td>
<td><p>161</p></td>
</tr>
<tr class="even">
<td><p>Áudio</p></td>
<td><p>Banda estreita RTAudio</p></td>
<td><p>30,9</p></td>
<td><p>44,8</p></td>
<td><p>56,6</p></td>
</tr>
</tbody>
</table>


Os números de largura de banda da rede dessas tabelas representam apenas o tráfego de uma via e incluem 5 Kbps de sobrecarga de tráfego RTCP para cada fluxo. Para vídeo, a taxa de bits de vídeo máxima é usada para calcular o fluxo máximo.

</div>

</div>

<span> </span>

</div>

</div>

</div>

