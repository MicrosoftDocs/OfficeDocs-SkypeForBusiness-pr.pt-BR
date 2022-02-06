---
title: Tabela VideoClientEvent
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: e8ab963b-fe1d-45b3-b9bd-66a5f44c1629
description: 'Cada registro contém evento cliente para um ponto de extremidade em uma chamada de vídeo. Normalmente, uma chamada tem dois registros, um para chamador e outro para chamador.'
---

# <a name="videoclientevent-table"></a>Tabela VideoClientEvent
 
Cada registro contém evento cliente para um ponto de extremidade em uma chamada de vídeo. Normalmente, uma chamada tem dois registros, um para chamador e outro para chamador.
  
|**Coluna**|**Tipo de dados**|**Chave/Índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primário  <br/> |Referenciado na tabela [MediaLine](medialine-0.md).  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primário  <br/> |Referenciado na tabela [MediaLine](medialine-0.md).  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primário  <br/> |Referenciado na tabela [MediaLine](medialine-0.md).  <br/> |
|**FromCaller** <br/> |bit  <br/> |Primário  <br/> |0: Dados do chamador  <br/> 1: Dados do chamador  <br/> |
|**NetworkBandwidthLowEventRatio** <br/> || <br/> |Porcentagem de sessão em que o evento LowBandwidth foi disparado para o estado 'Bad'. A largura de banda disponível é insuficiente para uma experiência de voz aceitável.  <br/> |
|**NetworkReceiveQualityEventRatio** <br/> || <br/> |Porcentagem da sessão em que o evento ReceiveSendQuality foi disparado para o estado 'Bad'.  <br/> A qualidade da rede em termos de tremeamento ou perda de pacotes é grave e afeta a qualidade do áudio recebido.  <br/> |
   

