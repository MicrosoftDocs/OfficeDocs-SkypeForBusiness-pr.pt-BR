---
title: Exibir ConferenceSessionDetails
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5858c84d-baed-421d-ad1d-3726e150e256
description: O modo de exibição ConferenceSessionDetails armazena informações sobre sessões com vários participantes. Cada registro representa uma sessão de conferência, que poderia ser a sessão com foco ou a sessão com um servidor de conferência específico. Este modo de exibição foi introduzido no Microsoft Lync Server 2013.
ms.openlocfilehash: 21c0bf2f68cabf5077c4bc975a84a57da4eeb188
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33901070"
---
# <a name="conferencesessiondetails-view"></a>Exibir ConferenceSessionDetails
 
O modo de exibição ConferenceSessionDetails armazena informações sobre sessões com vários participantes. Cada registro representa uma sessão de conferência, que poderia ser a sessão com foco ou a sessão com um servidor de conferência específico. Este modo de exibição foi introduzido no Microsoft Lync Server 2013.
  
|**Coluna**|**Tipo de dados**|**Detalhes**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Hora da solicitação de sessão. Usado em conjunto com SessionIdSeq para identificar exclusivamente uma sessão. Consulte a [tabela no Skype para Business Server 2015 de diálogos](dialogs.md) para obter mais informações. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Número de identificação para identificar a sessão. Usado em conjunto com SessionIdTime para identificar exclusivamente uma sessão. Consulte a [tabela no Skype para Business Server 2015 de diálogos](dialogs.md) para obter mais informações. <br/> |
|**InviteTime** <br/> |datetime  <br/> |Hora da primeira solicitação INVITE. Normalmente, este campo é preenchido pelos dados gerados a partir da mensagem de convite inicial da sessão. Se não houver nenhuma mensagem CONVIDAR o campo é preenchido com a data e hora da primeira relevante mensagem SIP (BYE, cancelar, mensagem ou INFO).  <br/> |
|**ConferenceUri** <br/> |nvarchar(450)  <br/> |URI da conferência.  <br/> |
|**ConferenceUriType** <br/> |nvarchar(256)  <br/> |Tipo de URI de conferência. Consulte a [tabela UriTypes](uritypes.md) para obter mais informações. <br/> |
|**ConfInstance** <br/> |Identificador exclusivo  <br/> |Identificador que diferencia entre instâncias de conferências recorrentes. Cada instância de conferência recorrente tem o mesmo ConferenceURI, mas um valor de ConfInstance diferente.  <br/> |
|**McuConferenceUri** <br/> |nvarchar(450)  <br/> |URI do servidor de conferência.  <br/> |
|**McuConferenceUriType** <br/> |nvarchar(256)  <br/> |Tipo de URI do servidor de conferência. Consulte a [tabela UriTypes](uritypes.md) para obter mais informações. <br/> |
|**UserUri** <br/> |nvarchar(450)  <br/> |URI do usuário envolvido na sessão.  <br/> |
|**UserUriType** <br/> |nvarchar(256)  <br/> |Tipo de URI do usuário que fez parte da sessão. Consulte a [tabela UriTypes](uritypes.md) para obter mais informações. <br/> |
|**UserTenant** <br/> |nvarchar(256)  <br/> |Locatário do usuário que fez parte da sessão. Consulte a [tabela de inquilinos](tenants.md) para obter mais informações. <br/> |
|**UserEndpointId** <br/> |Identificador exclusivo  <br/> |Identificador exclusivo do usuário que fez parte da sessão.  <br/> |
|**EndTime** <br/> |datetime  <br/> |Hora de término da sessão.  <br/> |
|**ConferenceClientVersion** <br/> |nvarchar(256)  <br/> |Versão do servidor de conferência.  <br/> |
|**ConferenceClientType** <br/> |int  <br/> |Tipo de servidor de conferência. Consulte a [tabela UserAgentDef](useragentdef.md) para obter mais informações. <br/> |
|**ConferenceCategory** <br/> |nvarchar(64)  <br/> |Categoria do servidor de conferência.  <br/> |
|**UserClientVersion** <br/> |nvarchar(256)  <br/> |Versão do cliente usado pelo usuário que participou da sessão.  <br/> |
|**UserClientType** <br/> |int  <br/> |Cliente usado pelo usuário que participou da sessão. Consulte a [tabela UserAgentDef](useragentdef.md) para obter mais detalhes. <br/> |
|**UserClientCategory** <br/> |nvarchar(64)  <br/> |Nome da categoria do cliente usado pelo usuário que fez parte da sessão.  <br/> |
|**OnBehalfOfUri** <br/> |nvarchar(450)  <br/> |URI do usuário em cujo nome a sessão foi iniciada.  <br/> |
|**OnBehalfOfUriType** <br/> |nvarchar(256)  <br/> |Tipo de URI do usuário em cujo nome a sessão foi iniciada. Consulte a [tabela UriTypes](uritypes.md) para obter mais informações. <br/> |
|**OnBehalfOfTenant** <br/> |nvarchar(256)  <br/> |Locatário do usuário cujo em nome, a sessão foi iniciada. Consulte a [tabela de inquilinos](tenants.md) para obter mais informações. <br/> |
|**ReferredByUri** <br/> |nvarchar(450)  <br/> |URI do usuário que referenciou a sessão.  <br/> |
|**ReferredByUriType** <br/> |nvarchar(256)  <br/> |Tipo de URI do usuário que referenciou a sessão. Consulte a [tabela UriTypes](uritypes.md) para obter mais informações. <br/> |
|**ReferredByUriTenant** <br/> |nvarchar(256)  <br/> |Locatário do usuário que referenciou a sessão. Consulte a [tabela de inquilinos](tenants.md) para obter mais informações. <br/> |
|**DialogId** <br/> |varstring(775)  <br/> |ID de diálogo SIP. O formato é  <br/> : diálogo; da marca; a marca  <br/> |
|**ReplaceDialogIdTime** <br/> |datetime  <br/> |Número de identificação para identificar a caixa de diálogo que foi substituída pela sessão atual. Consulte a [tabela no Skype para Business Server 2015 de diálogos](dialogs.md) para obter mais informações. <br/> |
|**ReplaceDialogIdSeq** <br/> |int  <br/> |Número de identificação para identificar a sessão. Usado em conjunto com ReplaceDialogIdTime para identificar exclusivamente uma sessão que foi substituída por esta sessão. Consulte a [tabela no Skype para Business Server 2015 de diálogos](dialogs.md) para obter mais informações. <br/> |
|**ReplacesDialogId** <br/> |varchar(775)  <br/> |ID de diálogo substitui a sessão de SIP. O formato do é:  <br/> diálogo; da marca; a marca  <br/> |
|**IsStartedByConfServer** <br/> |bit  <br/> |Indica se a sessão foi iniciada pelo servidor de conferência.  <br/> |
|**IsEndedByConfServer** <br/> |bit  <br/> |Indica se a sessão foi finalizada pelo servidor de conferência.  <br/> |
|**IsUserInternal** <br/> |bit  <br/> |Indica se o usuário fez logon da rede interna.  <br/> |
|**ResponseTime** <br/> |datetime  <br/> |Tempo de resposta à mensagem INVITE primeira. Normalmente, este campo é preenchido pelos dados gerados a partir da mensagem de convite inicial da sessão. Se não houver nenhuma mensagem CONVIDAR o campo é preenchido com a data e hora da primeira relevante mensagem SIP (BYE, cancelar, mensagem ou INFO).  <br/> |
|**ResponseCode** <br/> |int  <br/> |Código de resposta SIP para o convite de sessão. Normalmente, este campo é preenchido pelos dados gerados a partir da mensagem de convite inicial da sessão. Se não houver nenhuma mensagem CONVIDAR o campo é preenchido com a data e hora da primeira relevante mensagem SIP (BYE, cancelar, mensagem ou INFO).  <br/> |
|**DiagnosticId** <br/> |int  <br/> |ID de diagnóstico capturado dos cabeçalhos SIP de sessão.  <br/> |
|**ContentType** <br/> |nvarchar(256)  <br/> |Tipo de conteúdo para a sessão.  <br/> |
|**FrontEnd** <br/> |nvarchar(256)  <br/> |FQDN do servidor Front-End que capturou os dados da sessão.  <br/> |
|**Pool** <br/> |nvarchar(256)  <br/> |FQDN do pool que capturou os dados para a sessão.  <br/> |
|**MediationServer** <br/> |nvarchar(256)  <br/> |Servidor de mediação usado pelo usuário que participou da sessão.  <br/> |
|**Gateway** <br/> |nvarchar(256)  <br/> |Gateway usado pelo usuário que participou a sessão.  <br/> |
|**EdgeServer** <br/> |nvarchar(256)  <br/> |FQDN do servidor de borda usado pelo usuário que participou da sessão.  <br/> |
|**UserFlag** <br/> |smallint  <br/> |Indica os atributos do usuário que participou da sessão. As seguintes definições de atributo permitidas:  <br/> 0x01 - integrado com telefone de mesa  <br/> |
|**CallFlag** <br/> |smallint  <br/> |Indica os atributos de chamada. As seguintes definições de atributo são permitidas:  <br/> 0x01 - sessão repetida0  <br/> x02-uma chamada feita pelo operador em nome de um grupo de resposta  <br/> |
   

