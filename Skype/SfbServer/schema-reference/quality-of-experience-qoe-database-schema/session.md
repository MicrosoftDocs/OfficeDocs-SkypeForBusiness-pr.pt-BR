---
title: Tabela Session
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
ms.assetid: 7f05529c-794d-41ed-bca4-2e85b87b2dec
description: Cada registro representa uma sessão que envolve áudio ou áudio e vídeo. Ele contém informações gerais sobre a sessão. Uma sessão é definida como uma caixa de diálogo de protocolo de iniciação de sessão de áudio ou de vídeo (SIP) entre dois pontos de extremidade.
ms.openlocfilehash: f48857f826a4e85519d7dc7d2942d48967df8b01
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41805769"
---
# <a name="session-table"></a>Tabela Session
 
Cada registro representa uma sessão que envolve áudio ou áudio e vídeo. Ele contém informações gerais sobre a sessão. Uma sessão é definida como uma caixa de diálogo de protocolo de iniciação de sessão de áudio ou de vídeo (SIP) entre dois pontos de extremidade.
  
|**Coluna**|**Tipo de dados**|**Chave/índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primária  <br/> |Referenciado na [tabela de caixa de diálogo](dialog.md).  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primária  <br/> |Referenciado na [tabela de caixa de diálogo](dialog.md).  <br/> |
|**ConferenceKey** <br/> |int  <br/> |Exterior  <br/> |Chave de conferência. Referenciado na [tabela de conferências](conference.md).  <br/> |
|**CorrelationKey** <br/> |int  <br/> |Exterior  <br/> |Chave de correlação. Referenciado da [tabela SessionCorrelation](sessioncorrelation.md).  <br/> |
|**DialogCategory** <br/> |bit  <br/> | <br/> |Categoria da caixa de diálogo; 0 é o trecho do servidor do Skype for Business para o servidor de mediação; 1 é o servidor de mediação para a perna do gateway PSTN.  <br/> |
|**MediationServerBypassFlag** <br/> |bit  <br/> ||Sinalizador que indica se a chamada foi ignorada ou não.  <br/> |
|**MediaBypassWarningFlag** <br/> |int  <br/> ||Esse campo, se presente, indicará por que uma chamada não foi ignorada mesmo se as IDs de bypass forem atendidas. Para o Skype for Business Server, somente um valor é definido.  <br/> 0x0001-ID de bypass desconhecido para o adaptador de rede padrão.  <br/> |
|**StartTime ** <br/> |datetime  <br/> | <br/> |Hora de início da chamada.  <br/> |
|**EndTime** <br/> |datetime  <br/> | <br/> |Hora de término da chamada.  <br/> |
|**CallerPool** <br/> |int  <br/> |Exterior  <br/> |O pool do chamador. Referenciado na [tabela de pool](pool.md).  <br/> |
|**CalleePool** <br/> |int  <br/> |Exterior  <br/> |O pool do receptor da chamada. Referenciado na [tabela de pool](pool.md).  <br/> |
|**CalleePAI** <br/> |int  <br/> |Exterior  <br/> |O URI de SIP na identidade SIP p-declarated (PAI) do ponto de extremidade de recebimento. Referenciado da [tabela de usuário](user-0.md).  <br/> |
|**CallerURI** <br/> |int  <br/> |Exterior  <br/> |URI do chamador. Referenciado da [tabela de usuário](user-0.md).  <br/> |
|**CallerEndpoint** <br/> |int  <br/> |Exterior  <br/> |Ponto de extremidade do chamador. Referenciado da [tabela de pontos de extremidade](endpoint.md).  <br/> |
|**CallerUserAgent** <br/> |bit  <br/> |Exterior  <br/> |Agente de usuário do chamador. Referenciado na [tabela UserAgent](useragent.md).  <br/> |
|**CallPriority** <br/> |smallint  <br/> ||A prioridade desta chamada.  <br/> |
|**ClassifiedPoorCall** <br/> |bit  <br/> ||Esta coluna foi preterida e não é usada no Skype for Business Server. Em vez disso, essas informações são relatadas em bases de linhas por mídia. Para obter mais informações, consulte a [tabela de mídia](medialine-0.md) . <br/> |
|**CallerPAI** <br/> |int  <br/> |Exterior  <br/> |P-declarado-identidade do usuário que fez a chamada. A identidade de P-declarada (PAI) é usada para transmitir a verdadeira identidade do usuário que fez a chamada.  <br/> |
|**CalleeEndpoint** <br/> |int  <br/> |Exterior  <br/> |Ponto de extremidade que recebeu a chamada.  <br/> |
|**CalleeUserAgent** <br/> |int  <br/> |Exterior  <br/> |Agente de usuário empregado pelo usuário que recebeu a chamada. Os agentes de usuário representam o dispositivo de ponto de extremidade do cliente.  <br/> |
|**CalleeUri** <br/> |int  <br/> |Exterior  <br/> |O URI SIP do usuário que recebeu a chamada.  <br/> |
   

