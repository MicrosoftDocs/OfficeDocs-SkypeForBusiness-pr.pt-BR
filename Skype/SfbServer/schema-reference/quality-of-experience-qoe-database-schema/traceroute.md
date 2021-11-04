---
title: Tabela TraceRoute
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: b9493cef-6ece-4f13-bf68-dbf132aab4f4
description: A tabela TraceRoute contém informações de roteamento de chamadas. Esta tabela foi introduzida no Microsoft Lync Server 2013.
ms.openlocfilehash: 9b06b312abf00bcec5726741cfc7d5dc8eeb4520
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60756112"
---
# <a name="traceroute-table"></a>Tabela TraceRoute
 
A tabela TraceRoute contém informações de roteamento de chamadas. Esta tabela foi introduzida no Microsoft Lync Server 2013.
  
|**Column**|**Tipo de dados**|**Chave/Índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primária, estrangeira  <br/> |Data e hora de início da chamada.  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primária, estrangeira  <br/> |Identificador exclusivo usado para distinguir entre várias chamadas que podem ter começado na mesma data e hora.  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primário, externo  <br/> |Representa o tipo de linha de vídeo usada na chamada. Os valores permitidos são:  <br/> 0 - Áudio  <br/> 1 - Vídeo  <br/> 2 - Vídeo panorâmico  <br/> 3 - Compartilhamento de aplicativo/área de trabalho  <br/> |
|**FromCaller** <br/> |bit  <br/> |Primário  <br/> |Ponto de extremidade que executou a chamada.  <br/> |
|**Hop** <br/> |int  <br/> ||Salto de rede/  <br/> |
|**IPAddressKey** <br/> |int  <br/> |Foreign  <br/> |Identificador exclusivo do endereço IP. As informações de endereço IP são armazenadas na [tabela IPAddress.](ipaddress.md)  <br/> |
|**RTT** <br/> |int  <br/> ||Tempo de viagem de ida e volta. O tempo de viagem de ida e volta mede quanto tempo leva para que um pacote de voz chegue ao seu destino e retorne uma notificação de recebimento.  <br/> |
   

