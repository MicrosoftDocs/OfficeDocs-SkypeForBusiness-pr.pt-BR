---
title: 'Lync Server 2013: Tabela AudioClientEvent'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: AudioClientEvent table
ms:assetid: fef73d8f-7261-4e5b-9769-82435b007979
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413086(v=OCS.15)
ms:contentKeyID: 48185967
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 44d5146b334af83618ca2dd6261a18e72708f4f5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722621"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="audioclientevent-table-in-lync-server-2013"></a>Tabela AudioClientEvent no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-17_

Cada registro contém um evento de cliente para um ponto de extremidade em uma chamada de áudio. Geralmente, uma chamada tem dois registros, um para o chamador e outro para o receptor.


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
<td><p><strong>NetworkSendQualityEventRatio</strong></p></td>
<td><p>decimal (5; 2)</p></td>
<td><p> </p></td>
<td><p>Porcentagem da sessão o evento NetworkSendQuality foi disparado para o estado ' ruim '.</p>
<p>A qualidade da rede em termos de tremulação ou perda de pacote é grave e afetando a qualidade do áudio que está sendo enviado.</p></td>
</tr>
<tr class="even">
<td><p><strong>NetworkReceiveQualityEventRatio</strong></p></td>
<td><p>decimal (5; 2)</p></td>
<td><p> </p></td>
<td><p>Porcentagem da sessão o evento ReceiveSendQuality foi disparado para o estado ' ruim '.</p>
<p>A qualidade da rede em termos de tremulação ou perda de pacote é severa e afeta a qualidade do áudio sendo recebido.</p></td>
</tr>
<tr class="odd">
<td><p><strong>NetworkDelayEventRatio</strong></p></td>
<td><p>decimal (5; 2)</p></td>
<td><p> </p></td>
<td><p>Porcentagem da sessão o evento Delay foi acionado para o estado ' Bad '. A latência da rede é severa e impacta a experiência ao impedir a comunicação interativa</p></td>
</tr>
<tr class="even">
<td><p><strong>NetworkBandwidthLowEventRatio</strong></p></td>
<td><p>decimal (5; 2)</p></td>
<td><p> </p></td>
<td><p>Porcentagem da sessão o evento LowBandwidth foi disparado para o estado ' ruim '. A largura de banda disponível é insuficiente para uma experiência de voz aceitável.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CPUInsufficientEventRatio</strong></p></td>
<td><p>decimal (5; 2)</p></td>
<td><p> </p></td>
<td><p>Porcentagem da sessão o evento de CPU insuficiente foi acionado para o estado ' ruim '. Não há ciclos de CPU suficientes para processamento com as modalidades e aplicativos atuais em uso. Isso causa distorções com o canal de áudio.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceHalfDuplexAECEventRatio</strong></p></td>
<td><p>decimal (5; 2)</p></td>
<td><p> </p></td>
<td><p>Porcentagem da sessão o evento DeviceHalfDuplexAEC foi disparado para o estado ' ruim '. Para evitar eco, o sistema entra em Half duplex.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceRenderNotFunctioningEventRatio</strong></p></td>
<td><p>decimal (5; 2)</p></td>
<td><p> </p></td>
<td><p>Porcentagem da sessão o evento DeviceRenderNotFunctioning foi disparado para o estado ' ruim '. O dispositivo de renderização atualmente sendo usado para a sessão não está funcionando corretamente. Isso pode causar problemas de áudio unidirecionais.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceCaptureNotFunctioningEventRatio</strong></p></td>
<td><p>decimal (5; 2)</p></td>
<td><p> </p></td>
<td><p>Porcentagem da sessão o evento DeviceCaptureNotFunctioning foi disparado para o estado ' ruim '. O dispositivo de captura atualmente sendo usado para a sessão não está funcionando corretamente. Isso pode causar problemas de áudio unidirecionais.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceGlitchesEventRatio</strong></p></td>
<td><p>decimal (5; 2)</p></td>
<td><p> </p></td>
<td><p>Porcentagem da sessão o evento DeviceGlitches foi disparado para o estado ' ruim '. Há graves problemas na renderização de áudio que está causando distorções. Esses problemas podem ser causados por problemas de driver, Storm (chamadas de procedimento) adiadas (DPC) e alta utilização da CPU.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceLowSNREventRatio</strong></p></td>
<td><p>decimal (5; 2)</p></td>
<td><p> </p></td>
<td><p>Porcentagem da sessão o evento DeviceLowSNR foi disparado para o estado ' ruim '. A qualidade de captura é muito ruim, ou seja, muito ruidosa ou o usuário está falando muito longe do microfone. Isso causará distorções.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceLowSpeechLevelEventRatio</strong></p></td>
<td><p>decimal (5; 2)</p></td>
<td><p> </p></td>
<td><p>Porcentagem da sessão o evento DeviceLowSpeechLevel foi disparado para o estado ' ruim '. O nível de fala do usuário é muito baixo e o sistema não pode aumentar ainda mais. Isso pode causar distorções ou ser percebida como um áudio unidirecional.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceClippingEventRatio</strong></p></td>
<td><p>Decimal (5; 2)</p></td>
<td><p> </p></td>
<td><p>Porcentagem da sessão o evento DeviceClipping foi disparado para o estado ' ruim '.</p>
<p>Quando a fala near-end corta o microfone, a distorção de alta distância é distorcido devido ao recorte. É importante evitar o recorte de microfone near-end.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceEchoEventRatio</strong></p></td>
<td><p>decimal (5; 2)</p></td>
<td><p> </p></td>
<td><p>Porcentagem da sessão o evento DeviceEchoEvent foi disparado para o estado ' ruim '. O dispositivo ou a instalação está causando eco além da capacidade do sistema de compensar.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceNearEndToEchoRatioEventRatio</strong></p></td>
<td><p>decimal (5; 2)</p></td>
<td><p> </p></td>
<td><p>Porcentagem da sessão o evento DeviceNearEndToEchoRatio foi disparado para o estado ' ruim '. A fala do usuário é muito baixa em comparação com o eco sendo capturado, o que afeta a experiência dos usuários porque limita como é fácil interromper um usuário. Reduza o volume do alto-falante e aproxime o microfone do locutor.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceMultipleEndpointsEventCount</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Número de vezes durante a sessão em que o evento DeviceMultipleEndpoints foi disparado para o estado ' ruim '. Vários pontos de extremidade de áudio na mesma sessão detectados e o sistema foi compensado por meio da redução do volume de renderização.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceHowlingEventCount</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Número de vezes durante a sessão em que o evento DeviceHowlingEvent foi disparado para o estado ' ruim '. Loop de comentários sobre áudio detectado (causado por vários pontos de extremidade que compartilham o caminho de áudio).</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceRenderZeroVolumeEventRatio</strong></p></td>
<td><p>decimal (5; 2)</p></td>
<td></td>
<td><p>Porcentagem da sessão em que o evento DeviceRenderZeroVolume foi disparado para estar no estado "ruim". O dispositivo de renderização foi definido como volume zero.</p>
<p>Esta coluna foi introduzida no Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceRenderMuteEventRatio</strong></p></td>
<td><p>decimal (5; 2)</p></td>
<td></td>
<td><p>Porcentagem da sessão em que o evento DeviceRenderMute foi disparado para estar no estado "ruim". O dispositivo de renderização estava com mudo ativado.</p>
<p>Esta coluna foi introduzida no Microsoft Lync Server 2013.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

