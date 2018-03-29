---
title: Tabela TraceRoute
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b9493cef-6ece-4f13-bf68-dbf132aab4f4
description: A tabela TraceRoute contém informações de roteamento de chamadas. Esta tabela foi introduzida no Microsoft Lync Server 2013.
ms.openlocfilehash: e8796b164bd6a0f2809025b784ada9d12dda449b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="traceroute-table"></a>Tabela TraceRoute
 
A tabela TraceRoute contém informações de roteamento de chamadas. Esta tabela foi introduzida no Microsoft Lync Server 2013.
  
|**Coluna**|**Tipo de dados**|**Índice de chaves /**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primária, estrangeira  <br/> |Data e hora de início da chamada.  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primária, estrangeira  <br/> |Identificador exclusivo usado para distinguir entre várias chamadas que podem ter começado na mesma data e ao mesmo tempo.  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primária, estrangeira  <br/> |Representa o tipo da linha de vídeo utilizado na chamada. Os valores permitidos são:  <br/> 0 - áudio  <br/> 1 - vídeo  <br/> 2 - vídeo panorâmico  <br/> 3 - aplicativo/área de trabalho  <br/> |
|**FromCaller** <br/> |bit  <br/> |Primária  <br/> |Ponto de extremidade que executou a chamada.  <br/> |
|**Salto** <br/> |int  <br/> ||Salto de rede /  <br/> |
|**IPAddressKey** <br/> |int  <br/> |Externa  <br/> |Identificador exclusivo para o endereço IP. Informações de endereço IP são armazenadas na [tabela IPAddress](ipaddress.md).  <br/> |
|**TEMPO DE RESPOSTA** <br/> |int  <br/> ||Tempo de ida e volta. O tempo de ida e volta mede a quantidade de tempo que leva para um pacote de voz chegar ao seu destino e, em seguida, enviar notificação regressivo que ela foi recebida.  <br/> |
   

