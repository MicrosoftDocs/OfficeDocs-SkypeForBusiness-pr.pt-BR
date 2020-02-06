---
title: Exibição ConferenceSessionDetails
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 5858c84d-baed-421d-ad1d-3726e150e256
description: A exibição ConferenceSessionDetails armazena informações sobre sessões com vários participantes. Cada registro representa uma sessão de conferência, que pode ser a sessão com foco ou a sessão com um servidor de conferência específico. Este modo de exibição foi apresentado no Microsoft Lync Server 2013.
ms.openlocfilehash: 3dc345c10836a34f99baa4d6a088ab152b23427d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815329"
---
# <a name="conferencesessiondetails-view"></a>Exibição ConferenceSessionDetails
 
A exibição ConferenceSessionDetails armazena informações sobre sessões com vários participantes. Cada registro representa uma sessão de conferência, que pode ser a sessão com foco ou a sessão com um servidor de conferência específico. Este modo de exibição foi apresentado no Microsoft Lync Server 2013.
  
|**Coluna**|**Tipo de dados**|**Detalhes**|
|:-----|:-----|:-----|
|**Id_da_sessãotime** <br/> |datetime  <br/> |Tempo de solicitação de sessão. Usado em conjunto com o SessionIdSeq para identificar exclusivamente uma sessão. Consulte a [tabela de diálogos no Skype for Business Server 2015](dialogs.md) para obter mais informações. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Número de identificação para identificar a sessão. Usado em conjunto com a Identificação_da_sessãotime para identificar exclusivamente uma sessão. Consulte a [tabela de diálogos no Skype for Business Server 2015](dialogs.md) para obter mais informações. <br/> |
|**Invitetime** <br/> |datetime  <br/> |Hora da primeira solicitação INVITE. Geralmente, esse campo é preenchido por dados gerados da mensagem de convite inicial na sessão. Se não houver nenhuma mensagem de convite, o campo será preenchido com a data e a hora da primeira mensagem SIP relevante (até mais, cancelamento, mensagem ou informações).  <br/> |
|**ConferenceUri** <br/> |nvarchar (450)  <br/> |URL da conferência.  <br/> |
|**ConferenceUriType** <br/> |nvarchar(256)  <br/> |Tipo de URI de conferência. Consulte a [tabela UriTypes](uritypes.md) para obter mais informações. <br/> |
|**ConfInstance** <br/> |identificador  <br/> |Identificador que diferencia as instâncias de conferências recorrentes. Cada instância de conferência recorrente tem o mesmo ConferenceURI, mas um valor ConfInstance diferente.  <br/> |
|**McuConferenceUri** <br/> |nvarchar (450)  <br/> |URL do servidor de conferência.  <br/> |
|**McuConferenceUriType** <br/> |nvarchar(256)  <br/> |Tipo de URI do servidor de conferência. Consulte a [tabela UriTypes](uritypes.md) para obter mais informações. <br/> |
|**UserUri** <br/> |nvarchar (450)  <br/> |O URI do usuário envolvido na sessão.  <br/> |
|**UserUriType** <br/> |nvarchar(256)  <br/> |Tipo de URI do usuário cuja parte da sessão faz parte. Consulte a [tabela UriTypes](uritypes.md) para obter mais informações. <br/> |
|**Userlocatário** <br/> |nvarchar(256)  <br/> |Locatário do usuário cuja parte da sessão faz parte. Consulte a [tabela locatários](tenants.md) para obter mais informações. <br/> |
|**Userendpointid** <br/> |identificador  <br/> |Identificador exclusivo do usuário cuja parte da sessão faz parte.  <br/> |
|**EndTime** <br/> |datetime  <br/> |Hora de término da sessão.  <br/> |
|**ConferenceClientVersion** <br/> |nvarchar(256)  <br/> |Versão do servidor de conferência.  <br/> |
|**ConferenceClientType** <br/> |int  <br/> |Tipo de servidor de conferência. Consulte a [tabela UserAgentDef](useragentdef.md) para obter mais informações. <br/> |
|**ConferenceCategory** <br/> |nvarchar (64)  <br/> |Categoria do servidor de conferência.  <br/> |
|**UserClientVersion** <br/> |nvarchar(256)  <br/> |Versão do cliente usada pelo usuário que participou na sessão.  <br/> |
|**Userclienttype** <br/> |int  <br/> |Cliente usado pelo usuário que participou na sessão. Consulte a [tabela UserAgentDef](useragentdef.md) para obter mais detalhes. <br/> |
|**UserClientCategory** <br/> |nvarchar (64)  <br/> |Nome da categoria do cliente usado pelo usuário que fazia parte da sessão.  <br/> |
|**OnBehalfOfUri** <br/> |nvarchar (450)  <br/> |O URI do usuário em nome do qual a sessão foi iniciada.  <br/> |
|**OnBehalfOfUriType** <br/> |nvarchar(256)  <br/> |Tipo de URI do usuário em nome do qual a sessão foi iniciada. Consulte a [tabela UriTypes](uritypes.md) para obter mais informações. <br/> |
|**OnBehalfOfTenant** <br/> |nvarchar(256)  <br/> |Locatário do usuário cujo nome da sessão foi iniciado. Consulte a [tabela locatários](tenants.md) para obter mais informações. <br/> |
|**ReferredByUri** <br/> |nvarchar (450)  <br/> |URL do usuário que fez a chamada para a sessão.  <br/> |
|**ReferredByUriType** <br/> |nvarchar(256)  <br/> |Tipo de URI do usuário que a fez referência à sessão. Consulte a [tabela UriTypes](uritypes.md) para obter mais informações. <br/> |
|**ReferredByUriTenant** <br/> |nvarchar(256)  <br/> |Locatário do usuário que fez a chamada para a sessão. Consulte a [tabela locatários](tenants.md) para obter mais informações. <br/> |
|**Caixa de diálogo** <br/> |VARSTRING (775)  <br/> |ID da caixa de diálogo SIP. O formato é  <br/> :d ialog; de-marca; até-marca  <br/> |
|**ReplaceDialogIdTime** <br/> |datetime  <br/> |Número de identificação para identificar a caixa de diálogo que foi substituída pela sessão atual. Consulte a [tabela de diálogos no Skype for Business Server 2015](dialogs.md) para obter mais informações. <br/> |
|**ReplaceDialogIdSeq** <br/> |int  <br/> |Número de identificação para identificar a sessão. Usado em conjunto com ReplaceDialogIdTime para identificar exclusivamente uma sessão substituída por esta sessão. Consulte a [tabela de diálogos no Skype for Business Server 2015](dialogs.md) para obter mais informações. <br/> |
|**ReplacesDialogId** <br/> |varchar (775)  <br/> |ID da caixa de diálogo SIP a sessão substitui. O formato do é:  <br/> caixa de diálogo; de-marca; até-marca  <br/> |
|**IsStartedByConfServer** <br/> |bit  <br/> |Indica se a sessão foi iniciada pelo servidor de conferência.  <br/> |
|**IsEndedByConfServer** <br/> |bit  <br/> |Indica se a sessão foi encerrada pelo servidor de conferência.  <br/> |
|**IsUserInternal** <br/> |bit  <br/> |Indica se o usuário está conectado à rede interna.  <br/> |
|**ResponseTime** <br/> |datetime  <br/> |Hora da resposta à primeira mensagem de convite. Geralmente, esse campo é preenchido por dados gerados da mensagem de convite inicial na sessão. Se não houver nenhuma mensagem de convite, o campo será preenchido com a data e a hora da primeira mensagem SIP relevante (até mais, cancelamento, mensagem ou informações).  <br/> |
|**ResponseCode** <br/> |int  <br/> |Código de resposta SIP para o convite da sessão. Geralmente, esse campo é preenchido por dados gerados da mensagem de convite inicial na sessão. Se não houver nenhuma mensagem de convite, o campo será preenchido com a data e a hora da primeira mensagem SIP relevante (até mais, cancelamento, mensagem ou informações).  <br/> |
|**Diagnosticid** <br/> |int  <br/> |ID do diagnóstico capturada dos cabeçalhos SIP da sessão.  <br/> |
|**ContentType** <br/> |nvarchar(256)  <br/> |Tipo de conteúdo da sessão.  <br/> |
|**FrontEnd** <br/> |nvarchar(256)  <br/> |FQDN do servidor de front-end que capturou os dados para a sessão.  <br/> |
|**Pool** <br/> |nvarchar(256)  <br/> |FQDN do pool que capturou os dados da sessão.  <br/> |
|**MediationServer** <br/> |nvarchar(256)  <br/> |Servidor de mediação usado pelo usuário que participou na sessão.  <br/> |
|**Gateway** <br/> |nvarchar(256)  <br/> |O gateway usado pelo usuário que participou da sessão.  <br/> |
|**EdgeServer** <br/> |nvarchar(256)  <br/> |FQDN do servidor de borda usado pelo usuário que participou na sessão.  <br/> |
|**Sinalizador** <br/> |smallint  <br/> |Indica os atributos do usuário que participou na sessão. As definições de atributo a seguir são permitidas:  <br/> 0x01-integrado ao telefone desktop  <br/> |
|**CallFlag** <br/> |smallint  <br/> |Indica os atributos da chamada. As definições de atributo a seguir são permitidas:  <br/> 0x01-repetidas Session0  <br/> X02-uma chamada feita pelo agente em nome de um grupo de resposta  <br/> |
   

