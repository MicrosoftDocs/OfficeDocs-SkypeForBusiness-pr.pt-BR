---
title: Exibição de sessão
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 49e33f5b-45d0-4146-a5a4-76954d895a98
description: O Modo de exibição do servidor armazena informações sobre sessões que foram registradas no banco de dados. Essa exibição foi introduzida no Microsoft Lync Server 2013.
ms.openlocfilehash: 9f8fc3b22677da6794aeaaecdd180ade454fc36fbf9659c5f8196880c42c907b
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54314427"
---
# <a name="session-view"></a>Exibição de sessão
 
O Modo de exibição do servidor armazena informações sobre sessões que foram registradas no banco de dados. Essa exibição foi introduzida no Microsoft Lync Server 2013.
  
|**Coluna**|**Tipo de dados**|**Detalhes**|
|:-----|:-----|:-----|
|ConferenceDateTime  <br/> |datetime  <br/> |Referenciado da tabela MediaLine.  <br/> |
|ConferenceURI  <br/> |nvarchar(450)  <br/> |URI de Conferência é uma conferência, ou DialogID se é uma sessão peer-to-peer.  <br/> |
|Correlation  <br/> |varchar(max)  <br/> |ID de correlação da sessão.  <br/> |
|DialogCategory  <br/> |bit  <br/> |Categoria de caixa de diálogo; 0 é Skype for Business Server etapa do Servidor de Mediação; 1 é a etapa de gateway do Servidor de Mediação para PSTN.  <br/> |
|MediationServerBypassFlag  <br/> |bit  <br/> |Indica se uma ligação foi ou não ignorada.  <br/> |
|MediaBypassWarningFlag  <br/> |int  <br/> |Caso presente, este campo indica o motivo de uma chamada não ter sido ignorada, mesmo se as IDs de bypass correspondessem. Para Skype for Business Server, apenas um valor é definido:  <br/> 0x0001 - ID de bypass desconhecido para adaptador de rede padrão  <br/> |
|StartTime  <br/> |datetime  <br/> |Hora do início da chamada.  <br/> |
|EndTime  <br/> |datetime  <br/> |Hora da finalização da chamada.  <br/> |
|CallerPool  <br/> |nvarchar(256)  <br/> |Pool FQDN do chamador.  <br/> |
|CalleePool  <br/> |nvarchar(256)  <br/> |Pool FQDN do receptor.  <br/> |
|CallerPAI  <br/> |nvarchar(450)  <br/> |URI de identidade afirmada p do chamador.  <br/> |
|CalleePAI  <br/> |nvarchar(450)  <br/> |URI de identidade afirmada p do chamador.  <br/> |
|CallerEndpoint  <br/> |nvarchar(256)  <br/> |Nome do ponto de extremidade do chamador.  <br/> |
|CalleeEndpoint  <br/> |nvarchar(256)  <br/> |Nome do ponto de extremidade do chamador.  <br/> |
|CallerUserAgent  <br/> |nvarchar(256)  <br/> |Cadeia de caracteres de agente de usuário do chamador.  <br/> |
|CallerUserAgentType  <br/> |smallint  <br/> |Tipo de agente de usuário do chamador. Consulte a [tabela UserAgent para](useragent.md) obter detalhes. <br/> |
|CallerUserAgentCategory  <br/> |nvarchar (64)  <br/> |Categoria do agente de usuário do chamador. Consulte a [tabela UserAgentDef (QoE)](useragentdef-qoe.md) para obter detalhes. <br/> |
|CalleeUserAgent  <br/> |nvarchar(256)  <br/> |Cadeia de caracteres de agente de usuário do chamador.  <br/> |
|CalleeUserAgentType  <br/> |smallint  <br/> |Tipo de agente de usuário para o receptor. Consulte a [tabela UserAgent para](useragent.md) obter detalhes. <br/> |
|CalleeUserAgentCategory  <br/> |nvarchar (64)  <br/> |Categoria do agente de usuário para o receptor. Consulte a [tabela UserAgentDef (QoE)](useragentdef-qoe.md) para obter detalhes. <br/> |
|CallerURI  <br/> |nvarchar(450)  <br/> |URI do chamador.  <br/> |
|CalleeURI  <br/> |nvarchar(450)  <br/> |URI do chamador.  <br/> |
|CallPrioirty  <br/> |int  <br/> |Prioridade da chamada.  <br/> |
   

