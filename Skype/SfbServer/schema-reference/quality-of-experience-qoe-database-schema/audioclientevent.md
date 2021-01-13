---
title: Tabela AudioClientEvent
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: fef73d8f-7261-4e5b-9769-82435b007979
description: Cada registro contém um evento de cliente para um ponto de extremidade em uma chamada de áudio. Normalmente, uma chamada tem dois registros, um para o chamador e outro para o chamador.
ms.openlocfilehash: f5211d7f4ec3bc1d366d97def06edd325c448def
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809681"
---
# <a name="audioclientevent-table"></a>Tabela AudioClientEvent
 
Cada registro contém um evento de cliente para um ponto de extremidade em uma chamada de áudio. Normalmente, uma chamada tem dois registros, um para o chamador e outro para o chamador.
  
|**Coluna**|**Tipo de dados**|**Chave/Índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primário  <br/> |Referenciado na tabela [MediaLine](medialine-0.md).  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primário  <br/> |Referenciado na tabela [MediaLine](medialine-0.md).  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primário  <br/> |Referenciado na tabela [MediaLine](medialine-0.md).  <br/> |
|**FromCaller** <br/> |bit  <br/> |Primário  <br/> |0: Dados do destinatário da chamada  <br/> 1: Dados do chamador  <br/> |
|**NetworkSendQualityEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Porcentagem de sessão em que o evento NetworkSendQuality foi acionado para o estado 'Bad'.  <br/> A qualidade da rede em termos de tremida ou perda de pacotes é grave e afeta a qualidade do áudio que está sendo enviado.  <br/> |
|**NetworkReceiveQualityEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Porcentagem de sessão em que o evento ReceiveSendQuality foi acionado para o estado 'Bad'.  <br/> A qualidade da rede em termos de trem tremida ou perda de pacotes é grave e afeta a qualidade do áudio recebido.  <br/> |
|**NetworkDelayEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Porcentagem de sessão em que o evento Delay foi acionado para o estado 'Bad'. A latência de rede é grave e afeta a experiência evitando a comunicação interativa  <br/> |
|**NetworkBandwidthLowEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Porcentagem de sessão em que o evento LowBandwidth foi acionado para o estado 'Bad'. A largura de banda disponível é insuficiente para uma experiência de voz aceitável.  <br/> |
|**CPUInsufficientEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Porcentagem de sessão em que o evento de CPU insuficiente foi acionado para o estado 'Bad'. Há ciclos de CPU insuficientes para processamento com as modalidades e aplicativos atuais em uso. Isso causa distorções no canal de áudio.  <br/> |
|**DeviceHalfDuplexAECEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Porcentagem de sessão em que o evento DeviceHalfDuplexAEC foi acionado para o estado 'Bad'. Para evitar o eco, o sistema entrou no half duplex.  <br/> |
|**DeviceRenderNotFunctioningEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Porcentagem de sessão em que o evento DeviceRenderNotFunctioning foi acionado para o estado 'Bad'. O dispositivo de renderização atualmente usado para a sessão não está funcionando corretamente. Isso pode causar problemas de áudio de uma via.  <br/> |
|**DeviceCaptureNotFunctioningEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Porcentagem de sessão em que o evento DeviceCaptureNotFunctioning foi acionado para o estado 'Bad'. O dispositivo de captura atualmente em uso para a sessão não está funcionando corretamente. Isso pode causar problemas de áudio de uma via.  <br/> |
|**DeviceGlitchesEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Porcentagem de sessão em que o evento DeviceGlitches foi acionado para o estado 'Bad'. Há falhas graves na renderização de áudio que estão causando distorções. Essas falhas podem ser causadas por problemas de driver, bateria (drivers) de chamadas de procedimento adiadas (DPC) e alto uso da CPU.  <br/> |
|**DeviceLowSNREventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Porcentagem de sessão em que o evento DeviceLowSNR foi acionado para o estado 'Bad'. A qualidade da captura é muito ruim, muito barulhento ou o usuário está falando muito longe do microfone. Isso causará distorções.  <br/> |
|**DeviceLowSpeechLevelEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Porcentagem de sessão em que o evento DeviceLowSpeechLevel foi acionado para o estado 'Bad'. O nível de fala do usuário é muito baixo e o sistema não pode au incrementá-lo ainda mais. Isso pode causar distorções ou ser percebido como áudio de uma via.  <br/> |
|**DeviceClippingEventRatio** <br/> |Decimal(5,2)  <br/> | <br/> |Porcentagem de sessão em que o evento DeviceClipping foi acionado para o estado 'Bad'.  <br/> Quando a fala quase final recorta o microfone, a extremidade distante ouve distorção devido a recortes. É importante evitar recortes próximos do microfone.  <br/> |
|**DeviceEchoEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Porcentagem de sessão em que o evento DeviceEchoEvent foi acionado para o estado 'Bad'. O dispositivo ou a instalação está causando eco além da capacidade do sistema de compensar.  <br/> |
|**DeviceNearEndToEchoRatioEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Porcentagem de sessão em que o evento DeviceNearEndToEchoRatio foi acionado para o estado 'Bad'. A fala do usuário é muito baixa em comparação com o eco que está sendo capturado, o que afeta a experiência dos usuários porque limita a facilidade de interromper um usuário. Reduza o volume do alto-falante, mova o microfone para mais perto do talker.  <br/> |
|**DeviceMultipleEndpointsEventCount** <br/> |int  <br/> ||Número de vezes durante a sessão em que o evento DeviceMultipleEndpoints foi acionado para o estado 'Bad'. Vários pontos de extremidade de áudio na mesma sessão detectados e o sistema compensava reduzindo o volume de renderização.  <br/> |
|**DeviceHowlingEventCount** <br/> |int  <br/> | <br/> |Número de vezes durante a sessão em que o evento DeviceHowlingEvent foi acionado para o estado 'Bad'. Loop de feedback de áudio detectado (causado por vários pontos de extremidade compartilhando o caminho de áudio).  <br/> |
|**DeviceRenderZeroVolumeEventRatio** <br/> |decimal(5,2)  <br/> ||Porcentagem de sessão em que o evento DeviceRenderZeroVolume foi acionado por estar no estado "Ruim". O dispositivo de renderização foi definido como zero volume.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**DeviceRenderMuteEventRatio** <br/> |decimal(5,2)  <br/> ||Porcentagem de sessão em que o evento DeviceRenderMute foi acionado por estar no estado "Ruim". O dispositivo de renderização foi silenciado.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
   

