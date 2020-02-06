---
title: Tabela de TraceRoute
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
ms.assetid: b9493cef-6ece-4f13-bf68-dbf132aab4f4
description: A tabela TraceRoute contém informações de roteamento de chamadas. Esta tabela foi introduzida no Microsoft Lync Server 2013.
ms.openlocfilehash: e257bf6d89d04cd0f4784e62e7ac2876b6ede7e5
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41805109"
---
# <a name="traceroute-table"></a>Tabela de TraceRoute
 
A tabela TraceRoute contém informações de roteamento de chamadas. Esta tabela foi introduzida no Microsoft Lync Server 2013.
  
|**Coluna**|**Tipo de dados**|**Chave/índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primário, estrangeiro  <br/> |Data e hora em que a chamada começou.  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primário, estrangeiro  <br/> |Identificador exclusivo usado para distinguir entre várias chamadas que podem ter começado na mesma data e ao mesmo tempo.  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primário, estrangeiro  <br/> |Representa o tipo de linha de vídeo usado na chamada. Os valores permitidos são:  <br/> 0-áudio  <br/> 1-vídeo  <br/> 2-vídeo panorâmico  <br/> 3 – compartilhamento de aplicativos/área de trabalho  <br/> |
|**FromCaller** <br/> |bit  <br/> |Primária  <br/> |Ponto de extremidade que fez a chamada.  <br/> |
|**Hop** <br/> |int  <br/> ||Salto de rede/  <br/> |
|**IPAddressKey** <br/> |int  <br/> |Exterior  <br/> |Identificador exclusivo do endereço IP. As informações de endereço IP são armazenadas na [tabela IPAddress](ipaddress.md).  <br/> |
|**RESPOSTA** <br/> |int  <br/> ||Tempo de resposta. O tempo de resposta mede a quantidade de tempo que leva para um pacote de voz alcançar seu destino e enviar notificações de volta para que ele seja recebido.  <br/> |
   

