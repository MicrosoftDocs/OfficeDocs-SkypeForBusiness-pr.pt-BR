---
title: Tabela VideoClientEvent
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e8ab963b-fe1d-45b3-b9bd-66a5f44c1629
description: Cada registro contém um evento de cliente para um ponto de extremidade em uma chamada com vídeo. Geralmente, uma chamada tem dois registros, um para o chamador e outro para o receptor.
ms.openlocfilehash: b8e93206ea30622baa82adcec5ee9a80235521c5
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294548"
---
# <a name="videoclientevent-table"></a>Tabela VideoClientEvent
 
Cada registro contém um evento de cliente para um ponto de extremidade em uma chamada com vídeo. Geralmente, uma chamada tem dois registros, um para o chamador e outro para o receptor.
  
|**Coluna**|**Tipo de dados**|**Chave/índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primária  <br/> |Referenciado da [tabela de mídia](medialine-0.md).  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primária  <br/> |Referenciado da [tabela de mídia](medialine-0.md).  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primária  <br/> |Referenciado da [tabela de mídia](medialine-0.md).  <br/> |
|**FromCaller** <br/> |bit  <br/> |Primária  <br/> |0: dados do chamador  <br/> 1: dados do chamador  <br/> |
|**NetworkBandwidthLowEventRatio** <br/> || <br/> |Porcentagem da sessão o evento LowBandwidth foi disparado para o estado ' ruim '. A largura de banda disponível é insuficiente para uma experiência de voz aceitável.  <br/> |
|**NetworkReceiveQualityEventRatio** <br/> || <br/> |Porcentagem da sessão o evento ReceiveSendQuality foi disparado para o estado ' ruim '.  <br/> A qualidade da rede em termos de tremulação ou perda de pacote é severa e afeta a qualidade do áudio sendo recebido.  <br/> |
   

