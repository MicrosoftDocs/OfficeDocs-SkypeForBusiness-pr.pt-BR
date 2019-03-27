---
title: Tabela AudioClientEvent
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fef73d8f-7261-4e5b-9769-82435b007979
description: Cada registro contém um evento do cliente para um ponto de extremidade em uma chamada de áudio. Normalmente, uma chamada tem dois registros, um para o chamador e um para o receptor.
ms.openlocfilehash: 307406446d71adf462cdc8a0345aa823129a8f99
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30895052"
---
# <a name="audioclientevent-table"></a>Tabela AudioClientEvent
 
Cada registro contém um evento do cliente para um ponto de extremidade em uma chamada de áudio. Normalmente, uma chamada tem dois registros, um para o chamador e um para o receptor.
  
|**Coluna**|**Tipo de dados**|**Chave/índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primária  <br/> |Referenciado de [MediaLine table](medialine-0.md).  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primária  <br/> |Referenciado de [MediaLine table](medialine-0.md).  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primária  <br/> |Referenciado de [MediaLine table](medialine-0.md).  <br/> |
|**FromCaller** <br/> |bit  <br/> |Primária  <br/> |0: dados do receptor  <br/> 1: dados do chamador  <br/> |
|**NetworkSendQualityEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Porcentagem da sessão que o evento NetworkSendQuality foi acionado para o estado 'Ruim'.  <br/> Qualidade da rede em termos de perda de pacote ou jitter é grave e afeta a qualidade do áudio que está sendo enviada.  <br/> |
|**NetworkReceiveQualityEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Porcentagem da sessão que o evento ReceiveSendQuality foi acionado para o estado 'Ruim'.  <br/> Qualidade da rede em termos de perda de pacote ou jitter é grave e afeta a qualidade do áudio que está sendo recebido.  <br/> |
|**NetworkDelayEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Porcentagem da sessão que o evento atraso foi acionado para o estado 'Ruim'. Latência de rede é grave e afeta a experiência, impedindo a execução de comunicação interativa  <br/> |
|**NetworkBandwidthLowEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Porcentagem da sessão que o evento LowBandwidth foi acionado para o estado 'Ruim'. A largura de banda disponível é insuficiente para uma experiência aceitável de voz.  <br/> |
|**CPUInsufficientEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Porcentagem da sessão que o evento de CPU insuficiente foi acionado para o estado 'Ruim'. Há insuficientes ciclos de CPU para processamento com as modalidades atuais e aplicativos em uso. Isso faz com que as distorções com o canal de áudio.  <br/> |
|**DeviceHalfDuplexAECEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Porcentagem da sessão que o evento DeviceHalfDuplexAEC foi acionado para o estado 'Ruim'. Para evitar o eco, o sistema tem entrar half duplex.  <br/> |
|**DeviceRenderNotFunctioningEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Porcentagem da sessão que o evento DeviceRenderNotFunctioning foi acionado para o estado 'Ruim'. O dispositivo de renderização sendo utilizado para a sessão não está funcionando corretamente. Isso pode causar problemas de áudio unidirecionais.  <br/> |
|**DeviceCaptureNotFunctioningEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Porcentagem da sessão que o evento DeviceCaptureNotFunctioning foi acionado para o estado 'Ruim'. O dispositivo de captura sendo utilizado para a sessão não está funcionando corretamente. Isso pode causar problemas de áudio unidirecionais.  <br/> |
|**DeviceGlitchesEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Porcentagem da sessão que o evento DeviceGlitches foi acionado para o estado 'Ruim'. Há falhas graves no processamento de áudio que está causando distorções. Esses problemas podem ser causados por problemas de driver, tempestade de chamadas (DPC) procedimento adiada (drivers) e alto uso da CPU.  <br/> |
|**DeviceLowSNREventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Porcentagem da sessão que o evento DeviceLowSNR foi acionado para o estado 'Ruim'. A qualidade de captura é muito fraco, seja com muito ruído ou o usuário está falando muito longe do microfone. Isso fará com que as distorções.  <br/> |
|**DeviceLowSpeechLevelEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Porcentagem da sessão que o evento DeviceLowSpeechLevel foi acionado para o estado 'Ruim'. Nível de fala do usuário é muito baixo e o sistema não é possível aumentá-lo qualquer ainda mais. Isso pode fazer com que as distorções ou percebido como áudio unidirecional.  <br/> |
|**DeviceClippingEventRatio** <br/> |Decimal(5,2)  <br/> | <br/> |Porcentagem da sessão que o evento DeviceClipping foi acionado para o estado 'Ruim'.  <br/> Quando a fala perto ponta recorta o microfone, extremidade oposta ouve distorção devido ao recorte. É importante evitar distorção do microfone perto-end.  <br/> |
|**DeviceEchoEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Porcentagem da sessão que o evento DeviceEchoEvent foi acionado para o estado 'Ruim'. Instalação ou dispositivo está causando eco além da capacidade do sistema para compensar.  <br/> |
|**DeviceNearEndToEchoRatioEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Porcentagem da sessão que o evento DeviceNearEndToEchoRatio foi acionado para o estado 'Ruim'. Fala do usuário é muito baixa em comparação com o eco sendo capturado que afeta a experiência de usuários porque ele limitará como é fácil interrompam um usuário. Reduzir o volume do alto-falante, mova o mais próximo do microfone para o talker.  <br/> |
|**DeviceMultipleEndpointsEventCount** <br/> |int  <br/> ||Número de vezes durante o evento DeviceMultipleEndpoints foi acionado da sessão para o estado 'Ruim'. Vários pontos de extremidade de áudio na mesma sessão detectadas e o sistema tem recompensado, reduzindo o volume de renderização.  <br/> |
|**DeviceHowlingEventCount** <br/> |int  <br/> | <br/> |Número de vezes durante o evento DeviceHowlingEvent foi acionado da sessão para o estado 'Ruim'. Foi detectado um loop retorno de áudio (causada por vários pontos de extremidade compartilhamento caminho de áudio).  <br/> |
|**DeviceRenderZeroVolumeEventRatio** <br/> |decimal(5,2)  <br/> ||Porcentagem da sessão que o evento DeviceRenderZeroVolume foi acionado para estar no "ruim ' estado. O dispositivo de renderização foi definido como zero volume.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**DeviceRenderMuteEventRatio** <br/> |decimal(5,2)  <br/> ||Porcentagem da sessão que o evento DeviceRenderMute foi acionado para estar no "ruim ' estado. O dispositivo de renderização foi colocado em mudo.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
   

