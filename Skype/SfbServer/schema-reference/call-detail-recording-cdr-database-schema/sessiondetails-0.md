---
title: Exibição SessionDetails
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: ea328c6f-cf22-48dd-8f7f-f1666c9148c8
description: A visualização de SessionDetails armazena informações sobre sessões ponto a ponto, que pode ser uma chamada de telefone VoIP a VoIP, sessão de mensagens instantâneas entre duas partes ou outro tipo de sessão. Essa exibição foi introduzida no Microsoft Lync Server 2013.
ms.openlocfilehash: 5a278960912ac38dc75fe398e3d75de710785800
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60767449"
---
# <a name="sessiondetails-view"></a>Exibição SessionDetails
 
A visualização de SessionDetails armazena informações sobre sessões ponto a ponto, que pode ser uma chamada de telefone VoIP a VoIP, sessão de mensagens instantâneas entre duas partes ou outro tipo de sessão. Essa exibição foi introduzida no Microsoft Lync Server 2013.
  
|**Column**|**Tipo de dados**|**Detalhes**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Hora da solicitação da sessão. Utilizada em conjunto com o SessionIdSeq para identificar de forma exclusiva uma sessão. Consulte a [tabela Dialogs no Skype for Business Server 2015](dialogs.md) Table para obter mais informações. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Número de identificação para identificar a sessão. Utilizado em conjunto com o SessionIdTime para identificar de forma exclusiva uma sessão. Consulte a [tabela Dialogs no Skype for Business Server 2015](dialogs.md) para obter mais informações. <br/> |
|**InviteTime** <br/> |datetime  <br/> |Horário da primeira solicitação INVITE. Este campo é normalmente preenchido pelos dados gerados a partir da mensagem INVITE inicial na sessão. Caso não exista uma mensagem INVITE então o campo é preenchido com a data e horário da primeira mensagem SIP relevante (BYE, CANCEL, MESSAGE, ou INFO). Este campo é normalmente preenchido pelos dados gerados a partir da mensagem INVITE inicial na sessão. Caso não exista uma mensagem INVITE então o campo é preenchido com a data e horário da primeira mensagem SIP relevante (BYE, CANCEL, MESSAGE, ou INFO).  <br/> |
|**FromUri** <br/> |nvarchar(450)  <br/> |URI do usuário que iniciou a sessão.  <br/> |
|**ToUri** <br/> |nvarchar(450)  <br/> |URI do usuário que ingressou na sessão.  <br/> |
|**FromUriType** <br/> |nvarchar(256)  <br/> |Tipo do URI do usuário que iniciou a sessão. Consulte a [tabela UriTypes para](uritypes.md) obter mais informações. <br/> |
|**ToUriType** <br/> |nvarchar(256)  <br/> |Tipo do URI do usuário que ingressou na sessão. Consulte a [tabela UriTypes para](uritypes.md) obter mais informações. <br/> |
|**FromTenant** <br/> |nvarchar(450)  <br/> |Locatário do usuário que iniciou a sessão. Consulte a [tabela Locatários](tenants.md) para obter mais informações. <br/> |
|**ToTenant** <br/> |nvarchar(256)  <br/> |O locatário do usuário que iniciou a sessão. Consulte a [tabela Locatários](tenants.md) para obter mais informações. <br/> |
|**FromEndpointId** <br/> |uniqueidentifier  <br/> |Identificador exclusivo do ponto de extremidade do usuário que iniciou a sessão.  <br/> |
|**ToEndpointId** <br/> |uniqueidentifier  <br/> |Identificador exclusivo do ponto de extremidade do usuário que ingressou na sessão.  <br/> |
|**EndTime** <br/> |datetime  <br/> |Horário de término da sessão.  <br/> |
|**FromMessageCount** <br/> |int  <br/> |Número de mensagens enviadas pelo usuário que iniciou a sessão.  <br/> |
|**ToMessageCount** <br/> |int  <br/> |Número de mensagens evniadas pelo usuário que ingressou na sessão.  <br/> |
|**FromClientVersion** <br/> |nvarchar(256)  <br/> |Versão do cliente usado pelo usuário que iniciou a sessão.  <br/> |
|**FromClientType** <br/> |int  <br/> |Cliente usado pelo usuário que iniciou a sessão. Consulte a [tabela UserAgentDef](useragentdef.md) para obter mais detalhes. <br/> |
|**FromClientCategory** <br/> |nvarchar(64)  <br/> |Nome da categoria do cliente usado pelo usuário que iniciou a sessão.  <br/> |
|**ToClientVersion** <br/> |nvarchar(256)  <br/> |Versão do cliente usado pelo usuário que ingressou na sessão  <br/> |
|**ToClientType** <br/> |int  <br/> |Cliente usado pelo usuário que ingressou na sessão. Consulte a [tabela UserAgentDef](useragentdef.md) para obter mais detalhes. <br/> |
|**ToClientCategory** <br/> |nvarchar(64)  <br/> |Nome da categoria do cliente usado pelo usuário que ingressou na sessão.  <br/> |
|**TargetUri** <br/> |nvarchar(450)  <br/> |URI do usuário de destino da sessão.  <br/> |
|**TargetUriType** <br/> |nvarchar(450)  <br/> |Tipo do URI do usuário de destino da sessão. Consulte a [tabela UriTypes para](uritypes.md) obter mais informações. <br/> |
|**OnBehalfOfUri** <br/> |nvarchar(450)  <br/> |URI do usuário em cujo nome a sessão foi iniciada.  <br/> |
|**OnnnBehalfOfUriType** <br/> |nvarchar(256)  <br/> |Tipo de URI do usuário em cujo nome a sessão foi iniciada. Consulte a [tabela UriTypes para](uritypes.md) obter mais informações. <br/> |
|**OnBehalfOfTenant** <br/> |nvarchar(256)  <br/> |Locatário do usuário em cujo nome a sessão foi iniciada. Consulte a [tabela Locatários](tenants.md) para obter mais informações. <br/> |
|**ReferredByUri** <br/> |nvarchar(450)  <br/> |URI do usuário que se refere à sessão.  <br/> |
|**ReferredByUriType** <br/> |nvarchar(256)  <br/> |Tipo de URI do usuário que se refere à sessão. Consulte a [tabela UriTypes para](uritypes.md) obter mais informações. <br/> |
|**ReferredByTenant** <br/> |nvarchar(256)  <br/> |Locatário do usuário que se refere à sessão. Consulte a [tabela Locatários](tenants.md) para obter mais informações. <br/> |
|**DialogId** <br/> |varchar(775)  <br/> |ID de diálogo do SIP. O formato é:  <br/> dialog;from-tag;to-tag  <br/> |
|**CorrelationId** <br/> |uniqueidentifier  <br/> |GUID usadoo para correlacionar múltiplas sessões.  <br/> |
|**ReplaceDialogIdTime** <br/> |datetime  <br/> |Horário do diálogo que foi substituído pela sessão. Usado em conjunto com ReplaceDialogIdSeq para identificar exclusivamente um diálogo que foi substituído pela sessão. Consulte a [tabela Dialogs no Skype for Business Server 2015](dialogs.md) para obter mais informações. <br/> |
|**ReplaceDialogIdSeq** <br/> |int  <br/> |Número de ID para identificar a sessão. Usado em conjunto com ReplaceDialogIdTime para identificar exclusivamente uma sessão. Consulte a [tabela Dialogs no Skype for Business Server 2015](dialogs.md) para obter mais informações. <br/> |
|**ReplacesDialogId** <br/> |varchar(775)  <br/> |ID do diálogo do SIP substituído pela sessão. O formato é:  <br/> dialog;from-tag;to-tag  <br/> |
|**ResponseTime** <br/> |datetime  <br/> |O tempo de resposta para a primeira mensagem CONVIDAR. Este campo é, geralmente, preenchido por dados gerados a partir da mensagem CONVIDAR inicial na sessão. Se não houver nenhuma mensagem CONVIDAR, então o campo será preenchido com a data e a hora da primeira mensagem SIP relevante (ATÉ LOGO, CANCELAR, MENSAGEM ou INFO).  <br/> |
|**ResponseCode** <br/> |int  <br/> |Código de resposta SIP para convite de sessão. Este campo é normalmente preenchido por dados gerados na mensagem CONVIDAR inicial na sessão. Caso não haja nenhuma mensagem CONVIDAR, o campo é preenchidos com a data e horário da primeira mensagem de SIP relevante (ATÉ LOGO, CANCELAR, MENSAGEM ou INFO).  <br/> |
|**DiagnosticId** <br/> |int  <br/> |ID de diagnóstico capturado dos cabeçalhos do SIP.  <br/> |
|**ContentType** <br/> |nvarchar(256)  <br/> |Tipo de conteúdo para a sessão.  <br/> |
|**FrontEnd** <br/> |nvarchar(256)  <br/> |FQDN do servidor de Front-End que capturou os dados para a sessão.  <br/> |
|**Pool** <br/> |nvarchar(256)  <br/> |FQDN do pool que capturou os dados para a sessão.  <br/> |
|**FromEdgeServer** <br/> |nvarchar(256)  <br/> |FQDN do servidor de Borda usado pelo usuário que iniciou a sessão.  <br/> |
|**ToEdgeServer** <br/> |nvarchar(256)  <br/> |FQDN do servidor de Borda usado pelo usuário que iniciou a sessão  <br/> |
|**IsFromInternal** <br/> |bit  <br/> |Indica se o usuário que iniciou a sessão fez logon a partir da rede interna.  <br/> |
|**IsToInternal** <br/> |bit  <br/> |Indica se o usuário que ingressou na sessão fez logon a partir da rede interna.  <br/> |
|**CallPriority** <br/> |nvarchar(256)  <br/> |Prioridade de chamada da sessão.  <br/> |
|**FromUserFlag** <br/> |smallint  <br/> |Indica os atributos do usuário que iniciou a sessão. As definições de atributo a seguir são permitidas:  <br/> 0x01 - Integrado com telefone de mesa  <br/> |
|**ToUserFlag** <br/> |smallint  <br/> |Indica os atributos do usuário que iniciou a sessão. As definições de atributo a seguir são permitidas:  <br/> 0x01 - Integrado com telefone de mesa  <br/> |
|**CallFlag** <br/> |smallint  <br/> |Indica os atributos de chamada. As definições de atributo a seguir são permitidas:  <br/> 0x01 - Sessão repetida  <br/> 0x02 - Uma chamada feita por um agente em nome de um Grupo de Resposta  <br/> |
|**Localização** <br/> |varchar(max)  <br/> |Local da chamada de emergência.  <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> |Para uso interno pelo serviço de Monitoramento.  <br/> Este campo foi introduzido no Skype for Business Server 2015.  <br/> |
   

