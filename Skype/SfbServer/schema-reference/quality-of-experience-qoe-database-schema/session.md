---
title: Tabela Session
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
ms.assetid: 7f05529c-794d-41ed-bca4-2e85b87b2dec
description: Cada registro representa uma sessão que envolve áudio ou áudio e vídeo. Ele contém informações gerais sobre a sessão. Uma sessão é definida como uma caixa de diálogo SIP (Session Initiation Protocol) de áudio ou vídeo entre dois pontos de extremidade.
ms.openlocfilehash: cdf639e7360248e02378c66eb68a60d49acb9749
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802671"
---
# <a name="session-table"></a>Tabela Session
 
Cada registro representa uma sessão que envolve áudio ou áudio e vídeo. Ele contém informações gerais sobre a sessão. Uma sessão é definida como uma caixa de diálogo SIP (Session Initiation Protocol) de áudio ou vídeo entre dois pontos de extremidade.
  
|**Coluna**|**Tipo de dados**|**Chave/Índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primário  <br/> |Referenciado na tabela [Dialog](dialog.md).  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primário  <br/> |Referenciado na tabela [Dialog](dialog.md).  <br/> |
|**ConferenceKey** <br/> |int  <br/> |Externo  <br/> |Chave de conferência. Referenciado na tabela [Conference](conference.md).  <br/> |
|**CorrelationKey** <br/> |int  <br/> |Externo  <br/> |Chave de correlação. Referenciado na tabela [SessionCorrelation](sessioncorrelation.md).  <br/> |
|**DialogCategory** <br/> |bit  <br/> | <br/> |Categoria da caixa de diálogo; 0 é a etapa do Skype for Business Server para o Servidor de Mediação; 1 é o Servidor de Mediação para o trecho de gateway PSTN.  <br/> |
|**MediationServerBypassFlag** <br/> |bit  <br/> ||Sinalizador que indica se a chamada foi ignorada ou não.  <br/> |
|**MediaBypassWarningFlag** <br/> |int  <br/> ||Caso presente, este campo indica o motivo de uma chamada não ter sido ignorada, mesmo se as IDs de bypass correspondessem. Para o Skype for Business Server, apenas um valor é definido.  <br/> 0x0001 - ID de desvio desconhecido para o adaptador de rede padrão.  <br/> |
|**StartTime** <br/> |datetime  <br/> | <br/> |Hora do início da chamada.  <br/> |
|**EndTime** <br/> |datetime  <br/> | <br/> |Hora da finalização da chamada.  <br/> |
|**CallerPool** <br/> |int  <br/> |Externo  <br/> |O pool do chamador. Referenciado na tabela [Pool](pool.md).  <br/> |
|**CalleePool** <br/> |int  <br/> |Externo  <br/> |O pool do receptor da chamada. Referenciado na tabela [Pool](pool.md).  <br/> |
|**CalleePAI** <br/> |int  <br/> |Externo  <br/> |URI sip no SIP p-asserted identity (PAI) do ponto de extremidade de recebimento. Referenciado na tabela [User](user-0.md).  <br/> |
|**CallerURI** <br/> |int  <br/> |Externo  <br/> |URI do chamador. Referenciado na tabela [User](user-0.md).  <br/> |
|**CallerEndpoint** <br/> |int  <br/> |Externo  <br/> |Ponto de extremidade do chamador. Referenciado na tabela [ponto de extremidade](endpoint.md).  <br/> |
|**CallerUserAgent** <br/> |bit  <br/> |Externo  <br/> |Agente de usuário do chamador. Referenciado na [tabela UserAgent](useragent.md).  <br/> |
|**CallPriority** <br/> |smallint  <br/> ||A prioridade dessa chamada.  <br/> |
|**ClassifiedPoorCall** <br/> |bit  <br/> ||Essa coluna foi preterida e não é usada no Skype for Business Server. Em vez disso, essas informações são relatadas em bases de linha por mídia. Consulte a tabela [MediaLine para](medialine-0.md) obter mais informações. <br/> |
|**CallerPAI** <br/> |int  <br/> |Externo  <br/> |P-Asserted-Identity do usuário que fez a chamada. O PAI (P-Asserted-Identity) é usado para transmitir a identidade verdadeira do usuário que fez a chamada.  <br/> |
|**CalleeEndpoint** <br/> |int  <br/> |Externo  <br/> |Ponto de extremidade que recebeu a chamada.  <br/> |
|**CalleeUserAgent** <br/> |int  <br/> |Externo  <br/> |Agente do usuário empregado pelo usuário que recebeu a chamada. Os agentes do usuário representam o dispositivo de ponto de extremidade do cliente.  <br/> |
|**CalleeUri** <br/> |int  <br/> |Externo  <br/> |URI do SIP do usuário que recebeu a chamada.  <br/> |
   

