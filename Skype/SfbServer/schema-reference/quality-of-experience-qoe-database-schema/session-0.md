---
title: Exibição de sessão
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 49e33f5b-45d0-4146-a5a4-76954d895a98
description: O Modo de exibição do servidor armazena informações sobre sessões que foram registradas no banco de dados. Essa exibição foi introduzida no Microsoft Lync Server 2013.
ms.openlocfilehash: 22ad5fdc02eb7b3dc7531a18f4b40bee0334ce09
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60776011"
---
# <a name="session-view"></a>Exibição de sessão
 
O Modo de exibição do servidor armazena informações sobre sessões que foram registradas no banco de dados. Essa exibição foi introduzida no Microsoft Lync Server 2013.
  
|**Column**|**Tipo de dados**|**Detalhes**|
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
   

