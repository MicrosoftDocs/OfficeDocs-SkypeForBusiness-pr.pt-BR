---
title: Modo de exibição de sessão
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 49e33f5b-45d0-4146-a5a4-76954d895a98
description: O modo de exibição de sessão armazena informações sobre sessões que têm registros no banco de dados. Este modo de exibição foi introduzido no Microsoft Lync Server 2013.
ms.openlocfilehash: 056067b0c0e06b3ce9eb862898345fe4c8ff131c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="session-view"></a>Modo de exibição de sessão
 
O modo de exibição de sessão armazena informações sobre sessões que têm registros no banco de dados. Este modo de exibição foi introduzido no Microsoft Lync Server 2013.
  
|**Coluna**|**Tipo de dados**|**Detalhes**|
|:-----|:-----|:-----|
|ConferenceDateTime  <br/> |datetime  <br/> |Referenciado da MediaLine Table.  <br/> |
|ConferenceURI  <br/> |nvarchar(450)  <br/> |Caso se trate de uma conferência ou DialogID se este de URI de conferência é uma sessão ponto a ponto.  <br/> |
|Correlação  <br/> |varchar (max)  <br/> |ID de correlação da sessão.  <br/> |
|DialogCategory  <br/> |bit  <br/> |Categoria do diálogo; 0 é Skype para Business Server para a perna do servidor de mediação; 1 é o servidor de mediação para o trecho de gateway PSTN.  <br/> |
|MediationServerBypassFlag  <br/> |bit  <br/> |Indica se ou não a chamada foi ignorada.  <br/> |
|MediaBypassWarningFlag  <br/> |int  <br/> |Este campo, se presente, indica por que uma chamada não foi ignorada, mesmo se o desvio de correspondem de IDs. Skype para Business Server, somente um valor é definido:  <br/> 0x0001 - ID de desvio desconhecida adaptador de rede padrão  <br/> |
|StartTime  <br/> |datetime  <br/> |Hora de início da chamada.  <br/> |
|EndTime  <br/> |datetime  <br/> |Hora de término da chamada.  <br/> |
|CallerPool  <br/> |nvarchar(256)  <br/> |FQDN do pool do chamador.  <br/> |
|CalleePool  <br/> |nvarchar(256)  <br/> |FQDN do pool do receptor.  <br/> |
|CallerPAI  <br/> |nvarchar(450)  <br/> |Identidade do chamador declarada p URI.  <br/> |
|CalleePAI  <br/> |nvarchar(450)  <br/> |Identidade declarada p do receptor da chamada URI.  <br/> |
|CallerEndpoint  <br/> |nvarchar(256)  <br/> |Nome do ponto de extremidade do chamador.  <br/> |
|CalleeEndpoint  <br/> |nvarchar(256)  <br/> |Nome do ponto de extremidade do chamador.  <br/> |
|CallerUserAgent  <br/> |nvarchar(256)  <br/> |String de agente de usuário do chamador.  <br/> |
|CallerUserAgentType  <br/> |smallint  <br/> |Tipo de agente de usuário do chamador. Consulte a [tabela UserAgent](useragent.md) para obter detalhes. <br/> |
|CallerUserAgentCategory  <br/> |nvarchar (64)  <br/> |Categoria do agente do usuário do chamador. Consulte a [tabela UserAgentDef (QoE)](useragentdef-qoe.md) para obter detalhes. <br/> |
|CalleeUserAgent  <br/> |nvarchar(256)  <br/> |String de agente do usuário do receptor.  <br/> |
|CalleeUserAgentType  <br/> |smallint  <br/> |Tipo de agente de usuário para o receptor. Consulte a [tabela UserAgent](useragent.md) para obter detalhes. <br/> |
|CalleeUserAgentCategory  <br/> |nvarchar (64)  <br/> |Categoria do agente de usuário para o receptor. Consulte a [tabela UserAgentDef (QoE)](useragentdef-qoe.md) para obter detalhes. <br/> |
|CallerURI  <br/> |nvarchar(450)  <br/> |URI do chamador.  <br/> |
|CalleeURI  <br/> |nvarchar(450)  <br/> |URI do receptor.  <br/> |
|CallPrioirty  <br/> |int  <br/> |Prioridade da chamada.  <br/> |
   

