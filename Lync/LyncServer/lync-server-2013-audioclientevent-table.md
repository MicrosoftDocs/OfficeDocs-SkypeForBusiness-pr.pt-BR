---
title: 'Lync Server 2013: tabela AudioClientEvent'
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
ms.openlocfilehash: 53f43bdae2fd134e851c93be958aa671657489e1
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044593"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="audioclientevent-table-in-lync-server-2013"></a>Tabela AudioClientEvent no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-17_

Cada registro contém um evento de cliente para um ponto de extremidade em uma chamada de áudio. Normalmente, uma chamada tem dois registros, um para o chamador e um para o receptor.


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
<td><p>Primário</p></td>
<td><p>Referenciado da <a href="lync-server-2013-medialine-table.md">tabela de mídia no Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Primário</p></td>
<td><p>Referenciado da <a href="lync-server-2013-medialine-table.md">tabela de mídia no Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaLineLabel</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Primário</p></td>
<td><p>Referenciado da <a href="lync-server-2013-medialine-table.md">tabela de mídia no Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>FromCaller</strong></p></td>
<td><p>bits</p></td>
<td><p>Primário</p></td>
<td><p>0: dados do receptor</p>
<p>1: dados do chamador</p></td>
</tr>
<tr class="odd">
<td><p><strong>NetworkSendQualityEventRatio</strong></p></td>
<td><p>decimal (5, 2)</p></td>
<td><p> </p></td>
<td><p>Porcentagem da sessão que o evento NetworkSendQuality foi acionado para o estado "Bad".</p>
<p>A qualidade da rede em termos de tremulação ou perda de pacote é grave e afeta a qualidade do áudio que está sendo enviado.</p></td>
</tr>
<tr class="even">
<td><p><strong>NetworkReceiveQualityEventRatio</strong></p></td>
<td><p>decimal (5, 2)</p></td>
<td><p> </p></td>
<td><p>Porcentagem da sessão que o evento ReceiveSendQuality foi acionado para o estado "Bad".</p>
<p>A qualidade da rede em termos de tremulação ou perda de pacote é grave e afeta a qualidade do áudio que está sendo recebido.</p></td>
</tr>
<tr class="odd">
<td><p><strong>NetworkDelayEventRatio</strong></p></td>
<td><p>decimal (5, 2)</p></td>
<td><p> </p></td>
<td><p>Porcentagem da sessão em que o evento Delay foi acionado para o estado "ruim". A latência da rede é grave e afeta a experiência ao impedir a comunicação interativa</p></td>
</tr>
<tr class="even">
<td><p><strong>NetworkBandwidthLowEventRatio</strong></p></td>
<td><p>decimal (5, 2)</p></td>
<td><p> </p></td>
<td><p>Porcentagem da sessão que o evento LowBandwidth foi acionado para o estado "Bad". A largura de banda disponível é insuficiente para uma experiência de voz aceitável.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CPUInsufficientEventRatio</strong></p></td>
<td><p>decimal (5, 2)</p></td>
<td><p> </p></td>
<td><p>Porcentagem de sessão o evento de CPU insuficiente foi acionado para o estado ' ruim '. Há ciclos de CPU insuficientes para processamento com as modalidades atuais e os aplicativos em uso. Isso causa distorções com o canal de áudio.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceHalfDuplexAECEventRatio</strong></p></td>
<td><p>decimal (5, 2)</p></td>
<td><p> </p></td>
<td><p>Porcentagem da sessão que o evento DeviceHalfDuplexAEC foi acionado para o estado "Bad". Para evitar o eco, o sistema digitou Half duplex.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceRenderNotFunctioningEventRatio</strong></p></td>
<td><p>decimal (5, 2)</p></td>
<td><p> </p></td>
<td><p>Porcentagem da sessão que o evento DeviceRenderNotFunctioning foi acionado para o estado "Bad". O dispositivo de renderização que está sendo usado atualmente para a sessão não está funcionando corretamente. Isso pode causar problemas de áudio unidirecionais.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceCaptureNotFunctioningEventRatio</strong></p></td>
<td><p>decimal (5, 2)</p></td>
<td><p> </p></td>
<td><p>Porcentagem da sessão que o evento DeviceCaptureNotFunctioning foi acionado para o estado "Bad". O dispositivo de captura que está sendo usado atualmente para a sessão não está funcionando corretamente. Isso pode causar problemas de áudio unidirecionais.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceGlitchesEventRatio</strong></p></td>
<td><p>decimal (5, 2)</p></td>
<td><p> </p></td>
<td><p>Porcentagem da sessão que o evento DeviceGlitches foi acionado para o estado "Bad". Há problemas sérios na renderização de áudio que está causando distorções. Essas falhas podem ser causadas por problemas de driver, Storm (chamadas de procedimento adiadas) (DPC) e alto uso da CPU.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceLowSNREventRatio</strong></p></td>
<td><p>decimal (5, 2)</p></td>
<td><p> </p></td>
<td><p>Porcentagem da sessão que o evento DeviceLowSNR foi acionado para o estado "Bad". A qualidade de captura é muito ruim, ou seja, muito ruidosa ou o usuário está falando muito longe do microfone. Isso causará distorções.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceLowSpeechLevelEventRatio</strong></p></td>
<td><p>decimal (5, 2)</p></td>
<td><p> </p></td>
<td><p>Porcentagem da sessão que o evento DeviceLowSpeechLevel foi acionado para o estado "Bad". O nível de fala do usuário é muito baixo e o sistema não pode aumentar ainda mais. Isso pode causar distorções ou ser percebido como um áudio unidirecional.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceClippingEventRatio</strong></p></td>
<td><p>Decimal (5, 2)</p></td>
<td><p> </p></td>
<td><p>Porcentagem da sessão que o evento DeviceClipping foi acionado para o estado "Bad".</p>
<p>Quando os clipes de fala near-end, o microfone é distorção de escuta de ponta devido ao recorte. É importante evitar o recorte de microfone near-end.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceEchoEventRatio</strong></p></td>
<td><p>decimal (5, 2)</p></td>
<td><p> </p></td>
<td><p>Porcentagem da sessão que o evento por que deviceechoevent foi acionado para o estado "Bad". O dispositivo ou a instalação está causando eco além da capacidade do sistema de compensar.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceNearEndToEchoRatioEventRatio</strong></p></td>
<td><p>decimal (5, 2)</p></td>
<td><p> </p></td>
<td><p>Porcentagem da sessão que o evento DeviceNearEndToEchoRatio foi acionado para o estado "Bad". A fala do usuário é muito baixa em comparação com o eco que está sendo capturado, o que afeta a experiência dos usuários porque limita como é fácil interromper um usuário. Reduzir volume do alto-falante, mova o microfone para perto do Talker.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceMultipleEndpointsEventCount</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Número de vezes durante a sessão em que o evento DeviceMultipleEndpoints foi acionado para o estado ' Bad '. Vários pontos de extremidade de áudio na mesma sessão detectados e o sistema compensado pela redução do volume de renderização.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceHowlingEventCount</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Número de vezes durante a sessão em que o evento DeviceHowlingEvent foi acionado para o estado ' Bad '. Loop de comentários de áudio detectado (causado por vários pontos de extremidade que compartilham o caminho de áudio).</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceRenderZeroVolumeEventRatio</strong></p></td>
<td><p>decimal (5, 2)</p></td>
<td></td>
<td><p>Porcentagem da sessão em que o evento DeviceRenderZeroVolume foi acionado para estar no estado "ruim". O dispositivo de renderização foi definido como volume zero.</p>
<p>Esta coluna foi introduzida no Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceRenderMuteEventRatio</strong></p></td>
<td><p>decimal (5, 2)</p></td>
<td></td>
<td><p>Porcentagem da sessão em que o evento DeviceRenderMute foi acionado para estar no estado "ruim". O dispositivo de renderização estava com mudo ativado.</p>
<p>Esta coluna foi introduzida no Microsoft Lync Server 2013.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

