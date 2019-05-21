---
title: Modo de exibição sessão
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 49e33f5b-45d0-4146-a5a4-76954d895a98
description: A exibição de sessão armazena informações sobre as sessões que têm registros no banco de dados. Este modo de exibição foi apresentado no Microsoft Lync Server 2013.
ms.openlocfilehash: b24afdff32b5223725aa4f8ff0b7d875199713c7
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294681"
---
# <a name="session-view"></a>Modo de exibição sessão
 
A exibição de sessão armazena informações sobre as sessões que têm registros no banco de dados. Este modo de exibição foi apresentado no Microsoft Lync Server 2013.
  
|**Coluna**|**Tipo de dados**|**Detalhes**|
|:-----|:-----|:-----|
|ConferenceDateTime  <br/> |datetime  <br/> |Referenciado da tabela de mídia.  <br/> |
|ConferenceURI  <br/> |nvarchar (450)  <br/> |URL da conferência se for uma conferência ou caixa de diálogo se for uma sessão ponto a ponto.  <br/> |
|Relation  <br/> |varchar (max)  <br/> |ID de correlação da sessão.  <br/> |
|DialogCategory  <br/> |bit  <br/> |Categoria da caixa de diálogo; 0 é o trecho do servidor do Skype for Business para o servidor de mediação; 1 é o servidor de mediação para a perna do gateway PSTN.  <br/> |
|MediationServerBypassFlag  <br/> |bit  <br/> |Indica se a chamada foi ignorada ou não.  <br/> |
|MediaBypassWarningFlag  <br/> |int  <br/> |Esse campo, se presente, indicará por que uma chamada não foi ignorada mesmo se as IDs de bypass forem atendidas. Para o Skype for Business Server, somente um valor é definido:  <br/> 0x0001-ID de bypass desconhecido para o adaptador de rede padrão  <br/> |
|StartTime   <br/> |datetime  <br/> |Hora de início da chamada.  <br/> |
|EndTime  <br/> |datetime  <br/> |Hora de término da chamada.  <br/> |
|CallerPool  <br/> |nvarchar(256)  <br/> |FQDN do pool de chamadas.  <br/> |
|CalleePool  <br/> |nvarchar(256)  <br/> |FQDN do pool do chamador.  <br/> |
|CallerPAI  <br/> |nvarchar (450)  <br/> |URI de identidade declarado p do chamador.  <br/> |
|CalleePAI  <br/> |nvarchar (450)  <br/> |URI de identidade declarada do p do chamador.  <br/> |
|CallerEndpoint  <br/> |nvarchar(256)  <br/> |Nome do ponto de extremidade do chamador.  <br/> |
|CalleeEndpoint  <br/> |nvarchar(256)  <br/> |Nome do ponto de extremidade do chamador.  <br/> |
|CallerUserAgent  <br/> |nvarchar(256)  <br/> |Cadeia de caracteres do agente do usuário do chamador.  <br/> |
|CallerUserAgentType  <br/> |smallint  <br/> |Tipo de agente do usuário do chamador. Consulte a [tabela UserAgent](useragent.md) para obter detalhes. <br/> |
|CallerUserAgentCategory  <br/> |nvarchar (64)  <br/> |Categoria do agente do usuário do chamador. Consulte a [tabela UserAgentDef (QoE)](useragentdef-qoe.md) para obter detalhes. <br/> |
|CalleeUserAgent  <br/> |nvarchar(256)  <br/> |Cadeia de caracteres do agente do usuário do chamador.  <br/> |
|CalleeUserAgentType  <br/> |smallint  <br/> |Tipo de agente do usuário para o chamador. Consulte a [tabela UserAgent](useragent.md) para obter detalhes. <br/> |
|CalleeUserAgentCategory  <br/> |nvarchar (64)  <br/> |Categoria do agente do usuário para o chamador. Consulte a [tabela UserAgentDef (QoE)](useragentdef-qoe.md) para obter detalhes. <br/> |
|CallerURI  <br/> |nvarchar (450)  <br/> |URI do chamador.  <br/> |
|CalleeURI  <br/> |nvarchar (450)  <br/> |URI do chamador.  <br/> |
|CallPrioirty  <br/> |int  <br/> |Prioridade da chamada.  <br/> |
   

