---
title: Tabela VideoClientEvent
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e8ab963b-fe1d-45b3-b9bd-66a5f44c1629
description: Cada registro contém um evento do cliente para um ponto de extremidade em uma chamada de vídeo. Normalmente, uma chamada tem dois registros, um para o chamador e um para o receptor.
ms.openlocfilehash: b0c73cb3bc07a3e258f66555993698c21a978250
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="videoclientevent-table"></a>Tabela VideoClientEvent
 
Cada registro contém um evento do cliente para um ponto de extremidade em uma chamada de vídeo. Normalmente, uma chamada tem dois registros, um para o chamador e um para o receptor.
  
|**Coluna**|**Tipo de dados**|**Índice de chaves /**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primária  <br/> |Referenciado de [MediaLine table](medialine-0.md).  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primária  <br/> |Referenciado de [MediaLine table](medialine-0.md).  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primária  <br/> |Referenciado de [MediaLine table](medialine-0.md).  <br/> |
|**FromCaller** <br/> |bit  <br/> |Primária  <br/> |0: dados do receptor  <br/> 1: dados do chamador  <br/> |
|**NetworkBandwidthLowEventRatio** <br/> || <br/> |Porcentagem da sessão que o evento LowBandwidth foi acionado para o estado 'Ruim'. A largura de banda disponível é insuficiente para uma experiência aceitável de voz.  <br/> |
|**NetworkReceiveQualityEventRatio** <br/> || <br/> |Porcentagem da sessão que o evento ReceiveSendQuality foi acionado para o estado 'Ruim'.  <br/> Qualidade da rede em termos de perda de pacote ou jitter é grave e afeta a qualidade do áudio que está sendo recebido.  <br/> |
   

