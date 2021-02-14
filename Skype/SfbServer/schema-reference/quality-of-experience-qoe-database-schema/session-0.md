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
ms.openlocfilehash: 34619c1555fac5935563dd72895f52d045c388ae
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802691"
---
# <a name="session-view"></a>Exibição de sessão
 
O Modo de exibição do servidor armazena informações sobre sessões que foram registradas no banco de dados. Essa exibição foi introduzida no Microsoft Lync Server 2013.
  
|**Coluna**|**Tipo de dados**|**Detalhes**|
|:-----|:-----|:-----|
|ConferenceDateTime  <br/> |datetime  <br/> |Referenciado da tabela MediaLine.  <br/> |
|ConferenceURI  <br/> |nvarchar(450)  <br/> |URI de Conferência é uma conferência, ou DialogID se é uma sessão peer-to-peer.  <br/> |
|Correlation  <br/> |varchar(max)  <br/> |ID de correlação da sessão.  <br/> |
|DialogCategory  <br/> |bit  <br/> |Categoria da caixa de diálogo; 0 é a etapa do Skype for Business Server para o Servidor de Mediação; 1 é o Servidor de Mediação para o trecho de gateway PSTN.  <br/> |
|MediationServerBypassFlag  <br/> |bit  <br/> |Indica se uma ligação foi ou não ignorada.  <br/> |
|MediaBypassWarningFlag  <br/> |int  <br/> |Caso presente, este campo indica o motivo de uma chamada não ter sido ignorada, mesmo se as IDs de bypass correspondessem. Para o Skype for Business Server, apenas um valor é definido:  <br/> 0x0001 - ID de bypass desconhecido para o adaptador de rede padrão  <br/> |
|StartTime  <br/> |datetime  <br/> |Hora do início da chamada.  <br/> |
|EndTime  <br/> |datetime  <br/> |Hora da finalização da chamada.  <br/> |
|CallerPool  <br/> |nvarchar(256)  <br/> |Pool FQDN do chamador.  <br/> |
|CalleePool  <br/> |nvarchar(256)  <br/> |Pool FQDN do receptor.  <br/> |
|CallerPAI  <br/> |nvarchar(450)  <br/> |URI de identidade p-asserted do chamador.  <br/> |
|CalleePAI  <br/> |nvarchar(450)  <br/> |URI de identidade p-asserted do destinatário da chamada.  <br/> |
|CallerEndpoint  <br/> |nvarchar(256)  <br/> |Nome do ponto de extremidade do chamador.  <br/> |
|CalleeEndpoint  <br/> |nvarchar(256)  <br/> |Nome do ponto de extremidade do chamador.  <br/> |
|CallerUserAgent  <br/> |nvarchar(256)  <br/> |Cadeia de caracteres do agente do usuário do chamador.  <br/> |
|CallerUserAgentType  <br/> |smallint  <br/> |Tipo de agente de usuário do chamador. Consulte a [tabela UserAgent](useragent.md) para obter detalhes. <br/> |
|CallerUserAgentCategory  <br/> |nvarchar (64)  <br/> |Categoria do agente de usuário do chamador. Consulte a [tabela UserAgentDef (QoE)](useragentdef-qoe.md) para obter detalhes. <br/> |
|CalleeUserAgent  <br/> |nvarchar(256)  <br/> |Cadeia de caracteres de agente do usuário do destinatário da chamada.  <br/> |
|CalleeUserAgentType  <br/> |smallint  <br/> |Tipo de agente de usuário para o receptor. Consulte a [tabela UserAgent](useragent.md) para obter detalhes. <br/> |
|CalleeUserAgentCategory  <br/> |nvarchar (64)  <br/> |Categoria do agente de usuário para o receptor. Consulte a [tabela UserAgentDef (QoE)](useragentdef-qoe.md) para obter detalhes. <br/> |
|CallerURI  <br/> |nvarchar(450)  <br/> |URI do chamador.  <br/> |
|CalleeURI  <br/> |nvarchar(450)  <br/> |URI do destinatário da chamada.  <br/> |
|CallPrioirty  <br/> |int  <br/> |Prioridade da chamada.  <br/> |
   

