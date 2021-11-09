---
title: Tabela AudioClientEvent
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: fef73d8f-7261-4e5b-9769-82435b007979
description: Cada registro contém um evento cliente para um ponto de extremidade em uma chamada de áudio. Normalmente, uma chamada tem dois registros, um para chamador e outro para chamador.
ms.openlocfilehash: e51146211567af3abfe68fdc415814d433e84884
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60843644"
---
# <a name="audioclientevent-table"></a>Tabela AudioClientEvent
 
Cada registro contém um evento cliente para um ponto de extremidade em uma chamada de áudio. Normalmente, uma chamada tem dois registros, um para chamador e outro para chamador.
  
|**Column**|**Tipo de dados**|**Chave/Índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primário  <br/> |Referenciado na tabela [MediaLine](medialine-0.md).  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primário  <br/> |Referenciado na tabela [MediaLine](medialine-0.md).  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primário  <br/> |Referenciado na tabela [MediaLine](medialine-0.md).  <br/> |
|**FromCaller** <br/> |bit  <br/> |Primário  <br/> |0: Dados do chamador  <br/> 1: Dados do chamador  <br/> |
|**NetworkSendQualityEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Porcentagem da sessão em que o evento NetworkSendQuality foi disparado para o estado 'Bad'.  <br/> A qualidade da rede em termos de tremeamento ou perda de pacotes é grave e afeta a qualidade do áudio que está sendo enviado.  <br/> |
|**NetworkReceiveQualityEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Porcentagem da sessão em que o evento ReceiveSendQuality foi disparado para o estado 'Bad'.  <br/> A qualidade da rede em termos de tremeamento ou perda de pacotes é grave e afeta a qualidade do áudio recebido.  <br/> |
|**NetworkDelayEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Porcentagem da sessão em que o evento Delay foi disparado para o estado 'Bad'. A latência de rede é grave e afeta a experiência impedindo a comunicação interativa  <br/> |
|**NetworkBandwidthLowEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Porcentagem de sessão em que o evento LowBandwidth foi disparado para o estado 'Bad'. A largura de banda disponível é insuficiente para uma experiência de voz aceitável.  <br/> |
|**CPUInsufficientEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Porcentagem de sessão em que o evento CPU insuficiente foi disparado para o estado 'Bad'. Há ciclos de CPU insuficientes para processamento com as modalidades e aplicativos atuais em uso. Isso causa distorções com o canal de áudio.  <br/> |
|**DeviceHalfDuplexAECEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Porcentagem da sessão em que o evento DeviceHalfDuplexAEC foi disparado para o estado 'Bad'. Para evitar o eco, o sistema entrou em half duplex.  <br/> |
|**DeviceRenderNotFunctioningEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Porcentagem de sessão em que o evento DeviceRenderNotFunctioning foi disparado para o estado 'Bad'. O dispositivo de renderização atualmente usado para a sessão não está funcionando corretamente. Isso pode causar problemas de áudio único.  <br/> |
|**DeviceCaptureNotFunctioningEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Porcentagem de sessão em que o evento DeviceCaptureNotFunctioning foi disparado para o estado 'Bad'. O dispositivo de captura que está sendo usado para a sessão não está funcionando corretamente. Isso pode causar problemas de áudio único.  <br/> |
|**DeviceGlitchesEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Porcentagem da sessão em que o evento DeviceGlitches foi disparado para o estado 'Bad'. Há falhas graves na renderização de áudio que estão causando distorções. Essas falhas podem ser causadas por problemas de driver, chamadas de procedimento adiadas (drivers) e alto uso da CPU.  <br/> |
|**DeviceLowSNREventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Porcentagem da sessão em que o evento DeviceLowSNR foi disparado para o estado 'Bad'. A qualidade da captura é muito ruim, muito barulhento ou o usuário está falando muito longe do microfone. Isso causará distorções.  <br/> |
|**DeviceLowSpeechLevelEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Porcentagem de sessão em que o evento DeviceLowSpeechLevel foi disparado para o estado 'Bad'. O nível de fala do usuário é muito baixo e o sistema não pode aumentar ainda mais. Isso pode causar distorções ou ser percebido como áudio único.  <br/> |
|**DeviceClippingEventRatio** <br/> |Decimal(5,2)  <br/> | <br/> |Porcentagem da sessão em que o evento DeviceClipping foi disparado para o estado 'Bad'.  <br/> Quando a fala quase-final corta o microfone, a extremidade distante ouve distorção devido ao recorte. É importante evitar o recorte de microfone quase-final.  <br/> |
|**DeviceEchoEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Porcentagem de sessão em que o evento DeviceEchoEvent foi disparado para o estado 'Bad'. O dispositivo ou a instalação está causando eco além da capacidade do sistema de compensar.  <br/> |
|**DeviceNearEndToEchoRatioEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Porcentagem de sessão em que o evento DeviceNearEndToEchoRatio foi disparado para o estado 'Bad'. A fala do usuário é muito baixa em comparação com o eco que está sendo capturado, o que afeta a experiência dos usuários porque limita a facilidade de interromper um usuário. Reduza o volume do alto-falante, mova o microfone para mais perto do talker.  <br/> |
|**DeviceMultipleEndpointsEventCount** <br/> |int  <br/> ||Número de vezes durante a sessão em que o evento DeviceMultipleEndpoints foi disparado para o estado 'Bad'. Vários pontos de extremidade de áudio na mesma sessão detectados e o sistema foi compensado reduzindo o volume de renderização.  <br/> |
|**DeviceHowlingEventCount** <br/> |int  <br/> | <br/> |Número de vezes durante a sessão em que o evento DeviceHowlingEvent foi disparado para o estado 'Bad'. Loop de feedback de áudio detectado (causado por vários pontos de extremidade que compartilham o caminho de áudio).  <br/> |
|**DeviceRenderZeroVolumeEventRatio** <br/> |decimal(5,2)  <br/> ||Porcentagem de sessão em que o evento DeviceRenderZeroVolume foi disparado por estar no estado "Bad". O dispositivo de renderização foi definido como volume zero.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**DeviceRenderMuteEventRatio** <br/> |decimal(5,2)  <br/> ||Porcentagem de sessão em que o evento DeviceRenderMute foi disparado por estar no estado "Bad". O dispositivo de renderização foi silenciado.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
   

