---
title: 'Lync Server 2013: Tabela AudioSignal'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: AudioSignal table
ms:assetid: 0013c8c6-cdf9-4d70-bc2a-cddd1560f66b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398064(v=OCS.15)
ms:contentKeyID: 48183217
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 950c8457f80c69af5875064fff55c5ac7df61b24
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739571"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="audiosignal-table-in-lync-server-2013"></a>Tabela AudioSignal no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-11-12_

Cada registro representa as métricas do sinal de áudio para um ponto de extremidade. Geralmente, cada chamada tem dois registros, um é para o chamador e um é para o receptor.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Coluna</strong></th>
<th><strong>Tipo de dados</strong></th>
<th><strong>Chave/índice</strong></th>
<th><strong>Detalhes</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>ConferenceDateTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Primária</p></td>
<td><p>Referenciado da <a href="lync-server-2013-medialine-table.md">tabela de mídias no Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Primária</p></td>
<td><p>Referenciado da <a href="lync-server-2013-medialine-table.md">tabela de mídias no Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaLineLabel</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Primária</p></td>
<td><p>Referenciado da <a href="lync-server-2013-medialine-table.md">tabela de mídias no Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>FromCaller</strong></p></td>
<td><p>bit</p></td>
<td><p>Primária</p></td>
<td><p>0: dados do chamador</p>
<p>1: dados do chamador</p></td>
</tr>
<tr class="odd">
<td><p><strong>SendSignalLevel</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Representa o nível de sinal de áudio de controle de ganho de cruz analógico. A unidade para essa métrica é dBmo. Para ter uma qualidade aceitável, ele deve ter pelo menos 30 dBmo. Essa métrica não é reportada pelo servidor de conferência A/V ou por telefones IP.</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvSignalLevel</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Consulte SendSignalLevel.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SendNoiseLevel</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Representa o nível de ruído de áudio de controle de ganho analógicos. A unidade para essa métrica é dBmo. Para ter uma qualidade aceitável, deve ser menor do que 35 dBmo. Essa métrica não é reportada pelo servidor de conferência A/V ou por telefones IP.</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvNoiseLevel</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Consulte SendNoiseLevel.</p></td>
</tr>
<tr class="odd">
<td><p><strong>EchoReturn</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Métrica de aprimoramento de perda de retorno de eco. A unidade para essa métrica é dB. Valores inferiores representam menos eco. Essa métrica não é reportada pelo servidor de conferência A/V ou por telefones IP.</p></td>
</tr>
<tr class="even">
<td><p><strong>AudioSpeakerGlitchRate</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Média de falhas por cinco minutos para a renderização de alto-falante. Para ter uma boa qualidade, isso deve ser inferior a um por cinco minutos. Não relatado por servidores de conferência A/V, servidores de mediação ou telefones IP.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AudioMicGlitchRate</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Média de falhas por cinco minutos para a captura de microfone. Para ter uma boa qualidade, isso deve ser inferior a um por cinco minutos. Não relatado por servidores de conferência A/V, servidores de mediação ou telefones IP.</p></td>
</tr>
<tr class="even">
<td><p><strong>AudioTimestampDriftRateMic</strong></p></td>
<td><p>decimal (9; 2)</p></td>
<td><p> </p></td>
<td><p>Taxa de descompasso do relógio do dispositivo de microfone, relativa ao relógio da CPU.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AudioTimestampDriftRateSpk</strong></p></td>
<td><p>decimal (9; 2)</p></td>
<td><p> </p></td>
<td><p>Taxa de descompasso do relógio do dispositivo de alto-falante, relativa ao relógio da CPU.</p></td>
</tr>
<tr class="even">
<td><p><strong>AudioTimestampErrorMicMs</strong></p></td>
<td><p>decimal (9; 2)</p></td>
<td><p> </p></td>
<td><p>Taxa de descompasso do relógio do dispositivo de alto-falante, relativa ao relógio da CPU.</p>
<p>Erro de carimbo de data/hora médio do fluxo de captura de microfone, em milissegundos, nos últimos 20 segundos da chamada.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AudioTimestampErrorSpkMs</strong></p></td>
<td><p>decimal (9; 2)</p></td>
<td><p> </p></td>
<td><p>Média de um erro de carimbo de data/hora do fluxo de alto-falante, em milissegundos, nos últimos 20 segundos da chamada.</p></td>
</tr>
<tr class="even">
<td><p><strong>VsEntryCauses</strong></p></td>
<td><p>smallint</p></td>
<td><p> </p></td>
<td><p>A opção de voz é um modo Half-duplex com capacidade de interrupção reduzida. Causas da entrada da opção de voz:</p>
<p>ENTER_VS_BADTS 0x01</p>
<p>ENTER_VS_ECHO 0x02</p>
<p>ENTER_VS_FORCEORCONVERGENCE 0x04</p>
<p>ENTER_VS_DNLP 0x08</p>
<p>A causa pode ser uma combinação dessas causas individuais. ENTER_VS_FORCEORCONVERGENCE só pode ser habilitado pela RegKey para fins de teste.</p>
<p>O tipo de dados para esta coluna foi alterado no Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>EchoEventCauses</strong></p></td>
<td><p>tinyint</p></td>
<td><p> </p></td>
<td><p>Causas de um evento de eco:</p>
<p>ECHO_EVENT_BAD_TIMESTAMP 0x01</p>
<p>ECHO_EVENT_POSTAEC_ECHO 0x02</p>
<p>ECHO_EVENT_ANLP 0x04</p>
<p>ECHO_EVENT_DNLP 0x08</p>
<p>ECHO_EVENT_MIC_CLIPPING 0x10</p>
<p>ECHO_EVENT_BAD_STATE 0x20</p>
<p>A causa pode ser uma combinação dessas causas individuais.</p></td>
</tr>
<tr class="even">
<td><p><strong>EchoPercentMicIn</strong></p></td>
<td><p>decimal (5; 2)</p></td>
<td><p> </p></td>
<td><p>Porcentagem de tempo em que o eco foi detectado no fluxo de captura do microfone. Normalmente, os valores são baixos para fones de ouvido ou celulares e mais altos para viva voz e auto falante. Para dispositivos que suportam cancelamento de eco acústico na placa, os altos níveis indicam vazamento de eco. Para outros dispositivos, essa métrica não deve ser utilizada para avaliar a qualidade do dispositivo.</p></td>
</tr>
<tr class="odd">
<td><p><strong>EchoPercentSend</strong></p></td>
<td><p>decimal (5; 2)</p></td>
<td></td>
<td><p>Porcentagem de tempo em que o eco é detectado no fluxo de envio. Alta porcentagem de eco em enviar transmite uma indicação de vazamento de eco.</p></td>
</tr>
<tr class="even">
<td><p><strong>RxAGCSignalLevel</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Nível de sinal recebido no servidor de mediação do gateway; Isso se aplica apenas ao servidor de mediação. A unidade desta métrica é dBoV. Para ter uma boa qualidade, o intervalo aceitável deve ser [-30 a-18] dBoV.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RxAGCNoiseLevel</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Nível de sinal recebido no servidor de mediação do gateway. Isso se aplica apenas ao servidor de mediação. A unidade desta métrica é dBoV. Para ter uma boa qualidade, o intervalo aceitável deve ser menor do que-50 dBoV.</p></td>
</tr>
<tr class="even">
<td><p><strong>RxAvgAGCGain</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Controle de ganho automático (AGC) no lado do servidor de mediação.</p></td>
</tr>
<tr class="odd">
<td><p><strong>InitialSignalLevelRMS</strong></p></td>
<td><p>float</p></td>
<td><p> </p></td>
<td><p>O quadrado de raiz média (RMS) do sinal de entrada de até os primeiros 30 segundos da chamada.</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvSignalLevelCh1</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Nível de sinal como recebido no canal 1.</p>
<p>Esta coluna foi introduzida no Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvSignalLevelCh2</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Nível de sinal como recebido no canal 2.</p>
<p>Esta coluna foi introduzida no Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvNoiseLevelCh1</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Nível de ruído como recebido no canal 1.</p>
<p>Esta coluna foi introduzida no Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvNoiseLevelCh2</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Nível de ruído como recebido no canal 2.</p>
<p>Esta coluna foi introduzida no Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>SendSignalLevelCh1</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Nível de sinal como enviado no canal 1.</p>
<p>Esta coluna foi introduzida no Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SendSignalLevelCh2</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Nível de sinal como enviado no canal 2.</p>
<p>Esta coluna foi introduzida no Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>SendNoiseLevelCh1</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Nível de ruído enviado no canal 1.</p>
<p>Esta coluna foi introduzida no Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SendNoiseLevelCh2</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Nível de ruído enviado no canal 2.</p>
<p>Esta coluna foi introduzida no Microsoft Lync Server 2013.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

