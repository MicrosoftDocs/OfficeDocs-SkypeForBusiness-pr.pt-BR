---
title: Exibição ConferenceSessionDetails
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 5858c84d-baed-421d-ad1d-3726e150e256
description: O ConferenceSessionDetails visualiza as informações dos repositórios sobre sessões com vários participantes. Cada registro representa uma sessão de conferência, que poderia ser a sessão com Foco ou a sessão com um servidor de conferência específico. Essa exibição foi introduzida no Microsoft Lync Server 2013.
ms.openlocfilehash: cebd4acd218d551f7f43dba39334c342441e216a
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60771897"
---
# <a name="conferencesessiondetails-view"></a>Exibição ConferenceSessionDetails
 
O ConferenceSessionDetails visualiza as informações dos repositórios sobre sessões com vários participantes. Cada registro representa uma sessão de conferência, que poderia ser a sessão com Foco ou a sessão com um servidor de conferência específico. Essa exibição foi introduzida no Microsoft Lync Server 2013.
  
|**Column**|**Tipo de dados**|**Detalhes**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Hora da solicitação da sessão. Utilizada em conjunto com o SessionIdSeq para identificar de forma exclusiva uma sessão. Consulte a [tabela Dialogs no Skype for Business Server 2015](dialogs.md) para obter mais informações. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Número de identificação para identificar a sessão. Utilizado em conjunto com o SessionIdTime para identificar de forma exclusiva uma sessão. Consulte a [tabela Dialogs no Skype for Business Server 2015](dialogs.md) para obter mais informações. <br/> |
|**InviteTime** <br/> |datetime  <br/> |Horário da primeira solicitação CONVIDAR. Este campo é, geralmente, preenchido por dados gerados a partir da mensagem CONVIDAR inicial na sessão. Se não houver nenhuma mensagem CONVIDAR, então o campo será preenchido com a data e a hora da primeira mensagem SIP relevante (ATÉ LOGO, CANCELAR, MENSAGEM ou INFO).  <br/> |
|**ConferenceUri** <br/> |nvarchar(450)  <br/> |URI da conferência.  <br/> |
|**ConferenceUriType** <br/> |nvarchar(256)  <br/> |Tipo de URI da conferência. Consulte a [tabela UriTypes para](uritypes.md) obter mais informações. <br/> |
|**ConfInstance** <br/> |uniqueidentifier  <br/> |Identificador que diferencia instâncias de conferências recorrentes. Cada instância de conferência recorrente possui o mesmo ConferenceURI, mas um valor ConfInstance diferente.  <br/> |
|**McuConferenceUri** <br/> |nvarchar(450)  <br/> |URI do servidor de conferência.  <br/> |
|**McuConferenceUriType** <br/> |nvarchar(256)  <br/> |Tipo de URI de servidor de conferência. Consulte a [tabela UriTypes para](uritypes.md) obter mais informações. <br/> |
|**UserUri** <br/> |nvarchar(450)  <br/> |URI do usuário envolvido na sessão.  <br/> |
|**UserUriType** <br/> |nvarchar(256)  <br/> |Tipo de URI do usuário que fez parte da sessão. Consulte a [tabela UriTypes para](uritypes.md) obter mais informações. <br/> |
|**UserTenant** <br/> |nvarchar(256)  <br/> |Locatário do usuário que fez parte da sessão. Consulte a [tabela Locatários](tenants.md) para obter mais informações. <br/> |
|**UserEndpointId** <br/> |uniqueidentifier  <br/> |Identificador exclusivo do usuário que fez parte da sessão.  <br/> |
|**EndTime** <br/> |datetime  <br/> |Hora de término da sessão.  <br/> |
|**ConferenceClientVersion** <br/> |nvarchar(256)  <br/> |Versão do servidor de conferência.  <br/> |
|**ConferenceClientType** <br/> |int  <br/> |Tipo de servidor de conferência. Consulte a [tabela UserAgentDef para](useragentdef.md) obter mais informações. <br/> |
|**ConferenceCategory** <br/> |nvarchar(64)  <br/> |Categoria do servidor de conferência.  <br/> |
|**UserClientVersion** <br/> |nvarchar(256)  <br/> |Versão do cliente utilizado pelo usuário que participou da sessão.  <br/> |
|**UserClientType** <br/> |int  <br/> |Cliente utilizado pelo usuário que participou da sessão. Consulte a [tabela UserAgentDef](useragentdef.md) para obter mais detalhes. <br/> |
|**UserClientCategory** <br/> |nvarchar(64)  <br/> |Nome da categoria do cliente utilizado pelo usuário que foi parte da sessão.  <br/> |
|**OnBehalfOfUri** <br/> |nvarchar(450)  <br/> |URI do usuário em cujo nome a sessão foi iniciada.  <br/> |
|**OnBehalfOfUriType** <br/> |nvarchar(256)  <br/> |Tipo de URI do usuário em cujo nome a sessão foi iniciada. Consulte a [tabela UriTypes para](uritypes.md) obter mais informações. <br/> |
|**OnBehalfOfTenant** <br/> |nvarchar(256)  <br/> |Locatário do usuário em cujo nome a sessão foi iniciada. Consulte a [tabela Locatários](tenants.md) para obter mais informações. <br/> |
|**ReferredByUri** <br/> |nvarchar(450)  <br/> |URI do usuário que se refere à sessão.  <br/> |
|**ReferredByUriType** <br/> |nvarchar(256)  <br/> |Tipo de URI do usuário que se refere à sessão. Consulte a [tabela UriTypes para](uritypes.md) obter mais informações. <br/> |
|**ReferredByUriTenant** <br/> |nvarchar(256)  <br/> |Locatário do usuário que se refere à sessão. Consulte a [tabela Locatários](tenants.md) para obter mais informações. <br/> |
|**DialogId** <br/> |varstring(775)  <br/> |Identificação da caixa de diálogo SIP. O formato é  <br/> :d ialog;from-tag;to-tag  <br/> |
|**ReplaceDialogIdTime** <br/> |datetime  <br/> |Número de identificação para identificar o diálogo que foi substituído pela sessão atual. Consulte a [tabela Dialogs no Skype for Business Server 2015](dialogs.md) para obter mais informações. <br/> |
|**ReplaceDialogIdSeq** <br/> |int  <br/> |Número de identificação para identificar a sessão. Utilizado em conjunto com o ReplaceDialogIdTime para identificar de forma exclusiva a sessão que foi substituída por esta sessão. Consulte a [tabela Dialogs no Skype for Business Server 2015](dialogs.md) para obter mais informações. <br/> |
|**ReplacesDialogId** <br/> |varchar(775)  <br/> |Identificação da caixa de diálogo SIP substitui a sessão. O formato dela é:  <br/> dialog;from-tag;to-tag  <br/> |
|**IsStartedByConfServer** <br/> |bit  <br/> |Indica se a sessão foi iniciada pelo servidor de conferência.  <br/> |
|**IsEndedByConfServer** <br/> |bit  <br/> |Indica se a sessão foi finalizada pelo servidor de conferência.  <br/> |
|**IsUserInternal** <br/> |bit  <br/> |Indica se o usuário está conectado à rede interna.  <br/> |
|**ResponseTime** <br/> |datetime  <br/> |O tempo de resposta para a primeira mensagem CONVIDAR. Este campo é, geralmente, preenchido por dados gerados a partir da mensagem CONVIDAR inicial na sessão. Se não houver nenhuma mensagem CONVIDAR, então o campo será preenchido com a data e a hora da primeira mensagem SIP relevante (ATÉ LOGO, CANCELAR, MENSAGEM ou INFO).  <br/> |
|**ResponseCode** <br/> |int  <br/> |Código de resposta SIP para convite de sessão. Este campo é normalmente preenchido por dados gerados na mensagem CONVIDAR inicial na sessão. Caso não haja nenhuma mensagem CONVIDAR, o campo é preenchidos com a data e horário da primeira mensagem de SIP relevante (ATÉ LOGO, CANCELAR, MENSAGEM ou INFO).  <br/> |
|**DiagnosticId** <br/> |int  <br/> |ID de diagnóstico capturada dos cabeçalhos SIP da sessão.  <br/> |
|**ContentType** <br/> |nvarchar(256)  <br/> |Tipo de conteúdo para a sessão.  <br/> |
|**FrontEnd** <br/> |nvarchar(256)  <br/> |FQDN do servidor de Front-End que capturou os dados para a sessão.  <br/> |
|**Pool** <br/> |nvarchar(256)  <br/> |FQDN do pool que capturou os dados para a sessão.  <br/> |
|**MediationServer** <br/> |nvarchar(256)  <br/> |Servidor de Mediação utilizado pelo usuário que participou da sessão.  <br/> |
|**Gateway** <br/> |nvarchar(256)  <br/> |Gateway usado pelo usuário que participou da sessão.  <br/> |
|**EdgeServer** <br/> |nvarchar(256)  <br/> |FQDN do Servidor de Borda utilizado pelo usuário que participou da sessão.  <br/> |
|**UserFlag** <br/> |smallint  <br/> |Indica os atributos do usuário que participou da sessão. As definições de atributos a seguir são permitidas:  <br/> 0x01 - Integrado com telefone de mesa  <br/> |
|**CallFlag** <br/> |smallint  <br/> |Indica os atributos da chamada. As definições de atributo a seguir são permitidas:  <br/> 0x01 - Sessão repetida0  <br/> x02 - Uma chamada feita por um agente em nome de um Grupo de Resposta  <br/> |
   

