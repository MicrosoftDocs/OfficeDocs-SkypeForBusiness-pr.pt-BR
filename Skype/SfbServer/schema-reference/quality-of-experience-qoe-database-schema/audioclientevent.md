---
title: Tabela AudioClientEvent
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: fef73d8f-7261-4e5b-9769-82435b007979
description: Cada registro contém um evento de cliente para um ponto de extremidade em uma chamada de áudio. Geralmente, uma chamada tem dois registros, um para o chamador e outro para o receptor.
ms.openlocfilehash: 713804875f9cd2a1fc37a2255697c4ffda47a3c5
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41811079"
---
# <a name="audioclientevent-table"></a>Tabela AudioClientEvent
 
Cada registro contém um evento de cliente para um ponto de extremidade em uma chamada de áudio. Geralmente, uma chamada tem dois registros, um para o chamador e outro para o receptor.
  
|**Coluna**|**Tipo de dados**|**Chave/índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primária  <br/> |Referenciado da [tabela de mídia](medialine-0.md).  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primária  <br/> |Referenciado da [tabela de mídia](medialine-0.md).  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primária  <br/> |Referenciado da [tabela de mídia](medialine-0.md).  <br/> |
|**FromCaller** <br/> |bit  <br/> |Primária  <br/> |0: dados do chamador  <br/> 1: dados do chamador  <br/> |
|**NetworkSendQualityEventRatio** <br/> |decimal (5; 2)  <br/> | <br/> |Porcentagem da sessão o evento NetworkSendQuality foi disparado para o estado ' ruim '.  <br/> A qualidade da rede em termos de tremulação ou perda de pacote é grave e afetando a qualidade do áudio que está sendo enviado.  <br/> |
|**NetworkReceiveQualityEventRatio** <br/> |decimal (5; 2)  <br/> | <br/> |Porcentagem da sessão o evento ReceiveSendQuality foi disparado para o estado ' ruim '.  <br/> A qualidade da rede em termos de tremulação ou perda de pacote é severa e afeta a qualidade do áudio sendo recebido.  <br/> |
|**NetworkDelayEventRatio** <br/> |decimal (5; 2)  <br/> | <br/> |Porcentagem da sessão o evento Delay foi acionado para o estado ' Bad '. A latência da rede é severa e impacta a experiência ao impedir a comunicação interativa  <br/> |
|**NetworkBandwidthLowEventRatio** <br/> |decimal (5; 2)  <br/> | <br/> |Porcentagem da sessão o evento LowBandwidth foi disparado para o estado ' ruim '. A largura de banda disponível é insuficiente para uma experiência de voz aceitável.  <br/> |
|**CPUInsufficientEventRatio** <br/> |decimal (5; 2)  <br/> | <br/> |Porcentagem da sessão o evento de CPU insuficiente foi acionado para o estado ' ruim '. Não há ciclos de CPU suficientes para processamento com as modalidades e aplicativos atuais em uso. Isso causa distorções com o canal de áudio.  <br/> |
|**DeviceHalfDuplexAECEventRatio** <br/> |decimal (5; 2)  <br/> | <br/> |Porcentagem da sessão o evento DeviceHalfDuplexAEC foi disparado para o estado ' ruim '. Para evitar eco, o sistema entra em Half duplex.  <br/> |
|**DeviceRenderNotFunctioningEventRatio** <br/> |decimal (5; 2)  <br/> | <br/> |Porcentagem da sessão o evento DeviceRenderNotFunctioning foi disparado para o estado ' ruim '. O dispositivo de renderização atualmente sendo usado para a sessão não está funcionando corretamente. Isso pode causar problemas de áudio unidirecionais.  <br/> |
|**DeviceCaptureNotFunctioningEventRatio** <br/> |decimal (5; 2)  <br/> | <br/> |Porcentagem da sessão o evento DeviceCaptureNotFunctioning foi disparado para o estado ' ruim '. O dispositivo de captura atualmente sendo usado para a sessão não está funcionando corretamente. Isso pode causar problemas de áudio unidirecionais.  <br/> |
|**DeviceGlitchesEventRatio** <br/> |decimal (5; 2)  <br/> | <br/> |Porcentagem da sessão o evento DeviceGlitches foi disparado para o estado ' ruim '. Há graves problemas na renderização de áudio que está causando distorções. Esses problemas podem ser causados por problemas de driver, Storm (chamadas de procedimento) adiadas (DPC) e alta utilização da CPU.  <br/> |
|**DeviceLowSNREventRatio** <br/> |decimal (5; 2)  <br/> | <br/> |Porcentagem da sessão o evento DeviceLowSNR foi disparado para o estado ' ruim '. A qualidade de captura é muito ruim, ou seja, muito ruidosa ou o usuário está falando muito longe do microfone. Isso causará distorções.  <br/> |
|**DeviceLowSpeechLevelEventRatio** <br/> |decimal (5; 2)  <br/> | <br/> |Porcentagem da sessão o evento DeviceLowSpeechLevel foi disparado para o estado ' ruim '. O nível de fala do usuário é muito baixo e o sistema não pode aumentar ainda mais. Isso pode causar distorções ou ser percebida como um áudio unidirecional.  <br/> |
|**DeviceClippingEventRatio** <br/> |Decimal (5; 2)  <br/> | <br/> |Porcentagem da sessão o evento DeviceClipping foi disparado para o estado ' ruim '.  <br/> Quando a fala near-end corta o microfone, a distorção de alta distância é distorcido devido ao recorte. É importante evitar o recorte de microfone near-end.  <br/> |
|**DeviceEchoEventRatio** <br/> |decimal (5; 2)  <br/> | <br/> |Porcentagem da sessão o evento DeviceEchoEvent foi disparado para o estado ' ruim '. O dispositivo ou a instalação está causando eco além da capacidade do sistema de compensar.  <br/> |
|**DeviceNearEndToEchoRatioEventRatio** <br/> |decimal (5; 2)  <br/> | <br/> |Porcentagem da sessão o evento DeviceNearEndToEchoRatio foi disparado para o estado ' ruim '. A fala do usuário é muito baixa em comparação com o eco sendo capturado, o que afeta a experiência dos usuários porque limita como é fácil interromper um usuário. Reduza o volume do alto-falante e aproxime o microfone do locutor.  <br/> |
|**DeviceMultipleEndpointsEventCount** <br/> |int  <br/> ||Número de vezes durante a sessão em que o evento DeviceMultipleEndpoints foi disparado para o estado ' ruim '. Vários pontos de extremidade de áudio na mesma sessão detectados e o sistema foi compensado por meio da redução do volume de renderização.  <br/> |
|**DeviceHowlingEventCount** <br/> |int  <br/> | <br/> |Número de vezes durante a sessão em que o evento DeviceHowlingEvent foi disparado para o estado ' ruim '. Loop de comentários sobre áudio detectado (causado por vários pontos de extremidade que compartilham o caminho de áudio).  <br/> |
|**DeviceRenderZeroVolumeEventRatio** <br/> |decimal (5; 2)  <br/> ||Porcentagem da sessão em que o evento DeviceRenderZeroVolume foi disparado para estar no estado "ruim". O dispositivo de renderização foi definido como volume zero.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**DeviceRenderMuteEventRatio** <br/> |decimal (5; 2)  <br/> ||Porcentagem da sessão em que o evento DeviceRenderMute foi disparado para estar no estado "ruim". O dispositivo de renderização estava com mudo ativado.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
   

