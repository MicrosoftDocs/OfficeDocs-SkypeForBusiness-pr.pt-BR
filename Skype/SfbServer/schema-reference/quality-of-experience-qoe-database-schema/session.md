---
title: Tabela Session
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7f05529c-794d-41ed-bca4-2e85b87b2dec
description: Cada registro representa uma sessão que envolve o áudio ou áudio e vídeo. Ele contém informações gerais sobre a sessão. Uma sessão é definida como um diálogo de protocolo de iniciação de sessão (SIP) de áudio ou vídeo entre dois pontos de extremidade.
ms.openlocfilehash: 7a0ea3f9753529c22299ef46017b863c314319b5
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30881375"
---
# <a name="session-table"></a>Tabela Session
 
Cada registro representa uma sessão que envolve o áudio ou áudio e vídeo. Ele contém informações gerais sobre a sessão. Uma sessão é definida como um diálogo de protocolo de iniciação de sessão (SIP) de áudio ou vídeo entre dois pontos de extremidade.
  
|**Coluna**|**Tipo de dados**|**Chave/índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primária  <br/> |Referenciado pela [Dialog table](dialog.md).  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primária  <br/> |Referenciado pela [Dialog table](dialog.md).  <br/> |
|**ConferenceKey** <br/> |int  <br/> |Externa  <br/> |Chave de conferência. Referenciado da [tabela de conferência](conference.md).  <br/> |
|**CorrelationKey** <br/> |int  <br/> |Externa  <br/> |Chave de correlação. Referenciado da [tabela SessionCorrelation](sessioncorrelation.md).  <br/> |
|**DialogCategory** <br/> |bit  <br/> | <br/> |Categoria do diálogo; 0 é Skype para Business Server para a perna do servidor de mediação; 1 é o servidor de mediação para o trecho de gateway PSTN.  <br/> |
|**MediationServerBypassFlag** <br/> |bit  <br/> ||Sinalizador que indica se a chamada foi ignorada ou não.  <br/> |
|**MediaBypassWarningFlag** <br/> |int  <br/> ||Este campo, se presente, indica por que uma chamada não foi ignorada, mesmo se o desvio de correspondem de IDs. Skype para Business Server, somente um valor é definido.  <br/> 0x0001 - ID de desvio desconhecida adaptador de rede padrão.  <br/> |
|**StartTime ** <br/> |datetime  <br/> | <br/> |Hora de início da chamada.  <br/> |
|**EndTime** <br/> |datetime  <br/> | <br/> |Hora de término da chamada.  <br/> |
|**CallerPool** <br/> |int  <br/> |Externa  <br/> |O pool do chamador. Referenciado da [tabela de Pool](pool.md).  <br/> |
|**CalleePool** <br/> |int  <br/> |Externa  <br/> |O pool do receptor da chamada. Referenciado da [tabela de Pool](pool.md).  <br/> |
|**CalleePAI** <br/> |int  <br/> |Externa  <br/> |URI do SIP na SIP declarada p identidade (PAI) do ponto de extremidade de recepção. Referenciado da [tabela do usuário](user-0.md).  <br/> |
|**CallerURI** <br/> |int  <br/> |Externa  <br/> |URI do chamador. Referenciado da [tabela do usuário](user-0.md).  <br/> |
|**CallerEndpoint** <br/> |int  <br/> |Externa  <br/> |Ponto de extremidade do chamador. Referenciado da [tabela de ponto de extremidade](endpoint.md).  <br/> |
|**CallerUserAgent** <br/> |bit  <br/> |Externa  <br/> |Agente de usuário do chamador. Referenciado da [tabela UserAgent](useragent.md).  <br/> |
|**CallPriority** <br/> |smallint  <br/> ||A prioridade desta chamada.  <br/> |
|**ClassifiedPoorCall** <br/> |bit  <br/> ||Esta coluna foi preterida e não é usada no Skype para Business Server. Em vez disso, essa informação é relatada em um bases de linha-media. Consulte a [tabela MediaLine](medialine-0.md) para obter mais informações. <br/> |
|**CallerPAI** <br/> |int  <br/> |Externa  <br/> |P-Asserted-Identity do usuário que fez a chamada. P-Asserted-Identity (PAI) é usado para transmitir a verdadeira identidade do usuário que fez a chamada.  <br/> |
|**CalleeEndpoint** <br/> |int  <br/> |Externa  <br/> |Ponto de extremidade que recebeu a chamada.  <br/> |
|**CalleeUserAgent** <br/> |int  <br/> |Externa  <br/> |Agente de usuário empregado pelo usuário que recebeu a chamada. Agentes de usuário representam um dispositivo de ponto de extremidade do cliente.  <br/> |
|**CalleeUri** <br/> |int  <br/> |Externa  <br/> |URI do SIP do usuário que recebeu a chamada.  <br/> |
   

