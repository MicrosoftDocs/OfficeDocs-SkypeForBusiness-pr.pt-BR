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
ms.openlocfilehash: f450f5627fb79bd54a3b2a743a13a3cdfced82d5
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42129634"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="network-bandwidth-requirements-for-media-traffic-in-lync-server-2013"></a>Requisitos de largura de banda de rede para tráfego de mídia no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2015-09-24_

Uma parte importante do planejamento de rede é garantir que sua rede possa lidar com o tráfego de mídia gerado pelo Lync Server. Esta seção ajuda você a planejar esse tráfego de mídia.

<div>

## <a name="media-traffic-network-usage"></a>Uso da rede de tráfego de mídia

O uso da largura de banda do tráfego de mídia pode ser desafiador para calcular devido ao número de diferentes variáveis, como o uso de codec, resolução e níveis de atividade. O uso da largura de banda é uma função do codec usado e da atividade do fluxo, que podem variar entre os cenários. A tabela a seguir lista os codecs de áudio comumente usados nos cenários do Lync Server 2013.

### <a name="audio-codec-bandwidth"></a>Largura de banda de codec de áudio

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
<th>Taxa de bits da carga de áudio (KBPS)</th>
<th>Apenas carga de áudio da largura de banda e cabeçalho IP (Kbps)</th>
<th>Carga de áudio da largura de banda, cabeçalho IP, UDP, RTP e SRTP (Kbps)</th>
<th>Carga de áudio da largura de banda, cabeçalho IP, UDP, RTP, SRTP e correção de erro de encaminhamento (Kbps)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Banda larga RTAudio</p></td>
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
<td><p>G. 722</p></td>
<td><p>Conferências</p></td>
<td><p>64,0</p></td>
<td><p>80,0</p></td>
<td><p>95,6</p></td>
<td><p>159,6</p></td>
</tr>
<tr class="even">
<td><p>Estéreo G. 722</p></td>
<td><p>Ponto a ponto, conferência</p></td>
<td><p>128,0</p></td>
<td><p>144,0</p></td>
<td><p>159,6</p></td>
<td><p>223,6</p></td>
</tr>
<tr class="odd">
<td><p>G. 711</p></td>
<td><p>PSTN, conferência</p></td>
<td><p>64,0</p></td>
<td><p>80,0</p></td>
<td><p>92,0</p></td>
<td><p>156,0</p></td>
</tr>
<tr class="even">
<td><p>Siren</p></td>
<td><p>Conferências</p></td>
<td><p>16,0</p></td>
<td><p>32,0</p></td>
<td><p>47,6</p></td>
<td><p>63,6</p></td>
</tr>
</tbody>
</table>


Os números da largura de banda na tabela anterior são baseados na pacotização de 20ms (50 pacotes por segundo) e para Siren e G.722 incluem a sobrecarga do protocolo de transporte em tempo real seguro (SRTP) adicional dos cenários de conferência e assumem que o fluxo está 100% ativo. A Correção de Erro de Encaminhamento (FEC) é dinamicamente usada quando há uma perda de pacotes no link para ajudar a manter a qualidade do fluxo de áudio.

A versão estéreo do codec G. 722 é usada por sistemas baseados no sistema de salas do Lync, que permite a captura de microfone estéreo permitir que os ouvintes diferenciem melhor vários palestrantes na sala de reunião.

Para vídeo, o codec padrão é o padrão de codificação de vídeo avançado H. 264/MPEG-4 parte 10, juntamente com suas extensões escalonáveis de codificação de vídeo para escalabilidade temporal. Para manter a interoperabilidade com o Lync 2010 ou o Office Communicator 2007 R2 clients, o codec RTVideo ainda é usado para chamadas ponto a ponto entre o Lync 2013 e clientes herdados. Em sessões de conferência com ambos, Lync 2013 e clientes herdados o ponto de extremidade do Lync 2013 pode codificar o vídeo usando os codecs de vídeo e enviar o H. 264 Bitstream para o Lync 2013 e o RTVideo Bitstream para o Lync 2010 ou o Office Communicator 2007 clientes R2.

A largura de banda necessária depende da resolução, qualidade e taxa de quadros. Para cada resolução, há duas taxas de bits interessantes:

  - **Taxa de bits**   máxima de Payload esta é a taxa de bits que um ponto de extremidade do Lync 2013 usará para resolução na taxa de quadros máxima suportada para esta resolução. Este valor é interessante porque permite a maior qualidade e taxa de quadros do vídeo.

  - **Taxa de bits**   de carga mínima esta é a taxa de bits abaixo da qual o ponto de extremidade do Lync 2013 mudará para a próxima resolução mais baixa. Para garantir uma determinada resolução, a taxa de bits de carga de vídeo disponível não deve ficar abaixo dessa taxa de bits mínima para essa resolução. Este valor é interessante para que você possa compreender o menor valor possível em casos onde a taxa de bit máxima não está disponível ou não é praticável. Para alguns usuários, um vídeo de baixa taxa de bits pode ser considerado uma experiência de vídeo inaceitável, portanto, tenha cuidado ao considerar essas taxa de bits de carga de vídeo mínimas. Observe que, para cenas de vídeo, com pouco ou nenhum movimento do usuário, a taxa de bits real também pode ficar abaixo da taxa de bits mínima.

O Lync 2013 oferece suporte a muito mais soluções. Isso permite que você ajuste melhor a largura de banda de rede e os recursos de cliente diferentes. Além disso, a taxa de proporção padrão para o Lync 2013 foi alterada para 16:9. A taxa de proporção de 4:3 ainda é suportada para webcams que não permitem a captura em uma taxa de proporção 16:9.

### <a name="video-resolution-bandwidth"></a>Largura de banda de resolução de vídeo

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
<th>Taxa de bit de carga de vídeo máxima (Kbps)</th>
<th>Taxa de bit de carga de vídeo mínima (Kbps)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>H. 264</p></td>
<td><p>320x180 (16:9)</p>
<p>212x160 (4:3)</p></td>
<td><p>250</p></td>
<td><p>15 </p></td>
</tr>
<tr class="even">
<td><p>H. 264/RTVideo</p></td>
<td><p>424x240 (16:9))</p>
<p>320x240 (4:3</p></td>
<td><p>350</p></td>
<td><p>100</p></td>
</tr>
<tr class="odd">
<td><p>H. 264</p></td>
<td><p>480x270 (16:9)</p>
<p>424x320 (4:3)</p></td>
<td><p>450</p></td>
<td><p>200</p></td>
</tr>
<tr class="even">
<td><p>H. 264/RTVideo</p></td>
<td><p>640x360 (16:9)</p>
<p>640x480 (4:3)</p></td>
<td><p>800</p></td>
<td><p>300</p></td>
</tr>
<tr class="odd">
<td><p>H. 264</p></td>
<td><p>848x480 (16:9)</p></td>
<td><p>1500</p></td>
<td><p>400</p></td>
</tr>
<tr class="even">
<td><p>H. 264</p></td>
<td><p>960x540 (16:9)</p></td>
<td><p>2000</p></td>
<td><p>500</p></td>
</tr>
<tr class="odd">
<td><p>H. 264/RTVideo</p></td>
<td><p>1280 x 720 (16:9)</p></td>
<td><p>2500</p></td>
<td><p>700</p></td>
</tr>
<tr class="even">
<td><p>H. 264</p></td>
<td><p>1920 x 1080 (16:9)</p></td>
<td><p>4000</p></td>
<td><p>1500</p></td>
</tr>
<tr class="odd">
<td><p>H. 264/RTVideo</p></td>
<td><p>960 x 144 (20:3)</p></td>
<td><p>500</p></td>
<td><p>15 </p></td>
</tr>
<tr class="even">
<td><p>H. 264</p></td>
<td><p>1280x192 (20:3)</p></td>
<td><p>1000</p></td>
<td><p>250</p></td>
</tr>
<tr class="odd">
<td><p>H. 264</p></td>
<td><p>1920 x 288 (20:3)</p></td>
<td><p>2000</p></td>
<td><p>500</p></td>
</tr>
</tbody>
</table>


O FEC de vídeo é incluído na taxa de bit de carga de vídeo quando é usado para que não hajam valores separados com o FEC de vídeo e sem o FEC de vídeo.

Os pontos de extremidade não transmitem pacotes de áudio ou vídeo continuamente. Dependendo do cenário, existem níveis diferentes de atividade de fluxo que indicam a frequência com que os pacotes são enviados por um fluxo. A atividade de um fluxo depende da mídia e do cenário e não depende do codec que está sendo usado. Em um cenário ponto a ponto:

  - Os pontos de extremidade enviam fluxos de áudio apenas quando os usuários falam.

  - Ambos os participantes recebem fluxos de áudio.

  - Se o vídeo é usado, ambos pontos de extremidade enviam e recebem fluxos de vídeo durante toda a chamada.

  - Para cenas de vídeo com pouco ou nenhum movimento, a taxa de bits real pode ser temporariamente muito baixa, pois o codec de vídeo ignorará a codificação de regiões do vídeo sem alterações.

Em um cenário de conferência:

  - Os pontos de extremidade enviam fluxos de áudio apenas quando os usuários falam.

  - Todos os participantes recebem fluxos de áudio.

  - Se o vídeo for usado, todos os participantes poderão receber até cinco fluxos de vídeo de recebimento e um fluxo de vídeo panorâmico (por exemplo, taxa de proporção 20:3). Por padrão, os cinco fluxos de vídeo de recebimento são baseados no histórico de alto-falantes ativos, mas os usuários também podem selecionar manualmente os participantes dos quais desejam receber um fluxo de vídeo.

  - Cada participante que liga o fluxo de vídeo de envio do usuário enviará um ou mais fluxos de vídeo. Lync 2013 adicione a capacidade de enviar até cinco fluxos de vídeo para otimizar a qualidade de vídeo de todos os clientes de recebimento. O número real de fluxos de vídeo sendo enviados é determinado pelo remetente com base no recurso de CPU, na largura de banda de uplink disponível e no número de clientes de recebimento que solicitam um determinado fluxo de vídeo. O caso mais comum é que um e um fluxo de vídeo do RTVideo estão sendo enviados, caso um cliente herdado ingresse na conferência. Outro cenário comum é que vários fluxos de vídeo H. 264 (por exemplo, com diferentes resoluções de vídeo) são enviados para acomodar diferentes solicitações de destinatário.

Além da largura de banda necessária par ao tráfego do protocolo de transporte em tempo real (RTP) para mídia de áudio e vídeo, a largura de banda é necessária para o protocolo de controle de transporte em tempo real (RTCP). O RTCP é usado para relatar diagnósticos e controle fora da banda do fluxo RTP. Para planejamento, use os números da largura de banda da seguinte tabela para tráfego RTCP. Estes valores representam a largura de banda máxima usada para RTCP e difere entre os fluxos de áudio e vídeo por causa das diferenças nos dados de controle

### <a name="rtcp-bandwidth"></a>Largura de banda RTCP

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Mídia</th>
<th>Largura de banda máxima RTCP (Kbps)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Áudio</p></td>
<td><p>0,5</p></td>
</tr>
<tr class="even">
<td><p>Vídeo (somente H. 264 ou RTVideo sendo enviado/recebido)</p></td>
<td><p>10 </p></td>
</tr>
<tr class="odd">
<td><p>Vídeo (H. 264 e RTVideo sendo enviado/recebido)</p></td>
<td><p>15 </p></td>
</tr>
</tbody>
</table>


Para fins de planejamento de capacidade, as seguintes duas larguras de banda são interessantes:

  - **Largura de banda máxima sem FEC**   a largura de banda máxima que um fluxo utilizará, incluindo a atividade típica do fluxo e o codec típico usado no cenário sem FEC.Esta é a largura de banda quando o fluxo está a 100% de atividade e não há perda de pacotes acionando o uso do FEC.Isto é interessante para computar quanta largura de banda deve ser alocada para permitir que o codec seja usado em um determinado cenário. 

  - **Largura de banda máxima com FEC**   a largura de banda máxima que um fluxo consome, incluindo a atividade típica do fluxo e o codec típico usado no cenário com FEC. Esta é a largura de banda quando o fluxo está a 100% de atividade e há perda de pacote acionando o uso do FEC para melhorar a qualidade. Isto é interessante para computar quanta largura de banda deve ser alocada para permitir que o codec seja usado em um determinado cenário e permitir o uso do FEC para preservar a qualidade em condições de perda de pacotes. 

As tabelas a seguir também lista um valor de largura de banda adicional, **Largura de banda típica**. Esta é a largura de banda média que um fluxo consome, incluindo a atividade típica do fluxo e o codec típico usado no cenário. Esta largura de banda pode ser usada para aproximar quanta largura de banda em um determinado tempo é consumida pelo tráfego de mídia, mas não deve ser usada para planejamento de capacidade, porque as chamadas individuais excederão este valor quando o nível de atividade é maior do que a média. A largura de banda de fluxo de vídeo típica nas tabelas abaixo baseia-se em uma mistura de diferentes resoluções de vídeo, conforme observado em dados de cliente medidos. Por exemplo, em sessões ponto a ponto, a maioria dos usuários usaria a janela de renderização de vídeo padrão, enquanto alguma porcentagem de usuários aumentaria ou maximizaria o aplicativo Lync para permitir resoluções de vídeo mais altas.

As tabelas a seguir oferecem estes três valores de largura de banda para vários cenários.

### <a name="audiovideo-capacity-planning-for-peer-to-peer-sessions"></a>Planejamento de capacidade de áudio/vídeo para sessões ponto a ponto

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
<td><p>Vídeo principal ao chamar os pontos de extremidade do Lync 2013</p></td>
<td><p>H. 264</p></td>
<td><p>460</p></td>
<td><p>4010 (para resolução máxima de 1920 x 1080)</p></td>
<td><p>Não aplicável</p></td>
</tr>
<tr class="even">
<td><p>Vídeo principal ao chamar os pontos de extremidade do Lync 2010 ou do Office Communicator 2007 R2</p></td>
<td><p>RTVideo</p></td>
<td><p>460</p></td>
<td><p>2510 (para resolução máxima de 1280 x 720)</p></td>
<td><p>Não aplicável</p></td>
</tr>
<tr class="odd">
<td><p>Vídeo panorâmico ao chamar pontos de extremidade do Lync 2013</p></td>
<td><p>H. 264</p></td>
<td><p>190</p></td>
<td><p>2010 (para resolução máxima de 1920 x 288)</p></td>
<td><p>Não aplicável</p></td>
</tr>
<tr class="even">
<td><p>Vídeo panorâmico ao chamar os pontos de extremidade do Lync 2010 ou do Office Communicator 2007 R2</p></td>
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
<td><p>G. 722</p></td>
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
<td><p>Recebimento de vídeo principal</p></td>
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
<td><p>Recebimento de vídeo panorâmico</p></td>
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


Para o vídeo principal, a largura de banda de fluxo típica e máxima é a largura de banda agregada sobre todos os fluxos de vídeo recebidos e todos os fluxos de vídeo de envio, respectivamente. Mesmo com vários fluxos de vídeo, a largura de banda de vídeo típica é menor do que no cenário ponto a ponto, pois muitas conferências de vídeo estão usando o compartilhamento de conteúdo que leva a janelas de vídeo muito menores e, portanto, as resoluções de vídeo menores. A largura de banda máxima suportada de carga de vídeo agregada é de 8000 kbps para os fluxos de envio e recebimento, que seriam usados por exemplo, se houver dois fluxos de vídeo do 1920x1080p de entrada.

A largura de banda de fluxo típica para vídeo panorâmico é baseada em dispositivos atualmente disponíveis que só transmitem vídeo panorâmico no 960 x 144. Depois que os dispositivos com vídeo panorâmico do 1920 x 288 se tornarem disponíveis, espera-se que a largura de banda de fluxo típica aumente.

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


Os números de largura de banda da rede nestas tabelas representam apenas o tráfego de uma via e inclui 5 Kbps de sobrecarga de tráfego RTCP para cada fluxo. Para vídeo, a taxa de bit de vídeo máxima é usada para computar o fluxo máximo.

</div>

</div>

<span> </span>

</div>

</div>

</div>

