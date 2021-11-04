---
title: Tabela de sessão
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
ms.assetid: 7f05529c-794d-41ed-bca4-2e85b87b2dec
description: Cada registro representa uma sessão que envolve áudio, áudio e vídeo. Ele contém informações gerais sobre a sessão. Uma sessão é definida como uma caixa de diálogo SIP (Protocolo de Iniciação de Sessão) de áudio ou vídeo entre dois pontos de extremidade.
ms.openlocfilehash: bc81bb3c67f91b975643929170354c7b152d2237
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60768319"
---
# <a name="session-table"></a>Tabela de sessão
 
Cada registro representa uma sessão que envolve áudio, áudio e vídeo. Ele contém informações gerais sobre a sessão. Uma sessão é definida como uma caixa de diálogo SIP (Protocolo de Iniciação de Sessão) de áudio ou vídeo entre dois pontos de extremidade.
  
|**Column**|**Tipo de dados**|**Chave/Índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primário  <br/> |Referenciado na tabela [Dialog](dialog.md).  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primário  <br/> |Referenciado na tabela [Dialog](dialog.md).  <br/> |
|**ConferenceKey** <br/> |int  <br/> |Foreign  <br/> |Chave de conferência. Referenciado na tabela [Conferência](conference.md).  <br/> |
|**CorrelationKey** <br/> |int  <br/> |Foreign  <br/> |Chave de correlação. Referenciado da tabela [SessionCorrelation.](sessioncorrelation.md)  <br/> |
|**DialogCategory** <br/> |bit  <br/> | <br/> |Categoria de caixa de diálogo; 0 é Skype for Business Server etapa do Servidor de Mediação; 1 é a etapa de gateway do Servidor de Mediação para PSTN.  <br/> |
|**MediationServerBypassFlag** <br/> |bit  <br/> ||Sinalizador que indica se a chamada foi ignorada ou não.  <br/> |
|**MediaBypassWarningFlag** <br/> |int  <br/> ||Caso presente, este campo indica o motivo de uma chamada não ter sido ignorada, mesmo se as IDs de bypass correspondessem. Para Skype for Business Server, apenas um valor é definido.  <br/> 0x0001 - ID de bypass desconhecido para adaptador de rede padrão.  <br/> |
|**StartTime** <br/> |datetime  <br/> | <br/> |Hora do início da chamada.  <br/> |
|**EndTime** <br/> |datetime  <br/> | <br/> |Hora da finalização da chamada.  <br/> |
|**CallerPool** <br/> |int  <br/> |Foreign  <br/> |O pool do chamador. Referenciado na [tabela Pool](pool.md).  <br/> |
|**CalleePool** <br/> |int  <br/> |Foreign  <br/> |O pool do receptor de chamada. Referenciado na [tabela Pool](pool.md).  <br/> |
|**CalleePAI** <br/> |int  <br/> |Foreign  <br/> |URI SIP no SIP p-asserted identity (PAI) do ponto de extremidade de recebimento. Referenciado na [tabela Usuário.](user-0.md)  <br/> |
|**CallerURI** <br/> |int  <br/> |Foreign  <br/> |URI do chamador. Referenciado na [tabela Usuário.](user-0.md)  <br/> |
|**CallerEndpoint** <br/> |int  <br/> |Foreign  <br/> |Ponto de extremidade do chamador. Referenciado da tabela [Endpoint](endpoint.md).  <br/> |
|**CallerUserAgent** <br/> |bit  <br/> |Foreign  <br/> |Agente de usuário do chamador. Referenciado na [tabela UserAgent](useragent.md).  <br/> |
|**CallPriority** <br/> |smallint  <br/> ||A prioridade dessa chamada.  <br/> |
|**ClassifiedPoorCall** <br/> |bit  <br/> ||Esta coluna foi preterida e não é usada Skype for Business Server. Em vez disso, essas informações são relatadas em bases de linha por mídia. Consulte a tabela [MediaLine para](medialine-0.md) obter mais informações. <br/> |
|**CallerPAI** <br/> |int  <br/> |Foreign  <br/> |P-Asserted-Identity do usuário que fez a chamada. O PAI (P-Asserted-Identity) é usado para transmitir a verdadeira identidade do usuário que fez a chamada.  <br/> |
|**CalleeEndpoint** <br/> |int  <br/> |Foreign  <br/> |Ponto de extremidade que recebeu a chamada.  <br/> |
|**CalleeUserAgent** <br/> |int  <br/> |Foreign  <br/> |Agente de usuário empregado pelo usuário que recebeu a chamada. Os agentes de usuário representam o dispositivo de ponto de extremidade do cliente.  <br/> |
|**CalleeUri** <br/> |int  <br/> |Foreign  <br/> |URI SIP do usuário que recebeu a chamada.  <br/> |
   

