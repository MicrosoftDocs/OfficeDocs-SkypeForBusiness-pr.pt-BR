---
title: Exibir SessionDetails
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 7/15/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ea328c6f-cf22-48dd-8f7f-f1666c9148c8
description: O modo de exibição do SessionDetails armazena informações sobre sessões ponto a ponto, o que poderia ser um telefonema VoIP-VoIP, sessão de mensagens Instantâneas de dois participantes ou outro tipo de sessão. Este modo de exibição foi introduzido no Microsoft Lync Server 2013.
ms.openlocfilehash: c62f6e2c1bb505bf00d56898a562db2c00d298d0
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212814"
---
# <a name="sessiondetails-view"></a>Exibir SessionDetails
 
O modo de exibição do SessionDetails armazena informações sobre sessões ponto a ponto, o que poderia ser um telefonema VoIP-VoIP, sessão de mensagens Instantâneas de dois participantes ou outro tipo de sessão. Este modo de exibição foi introduzido no Microsoft Lync Server 2013.
  
|**Coluna**|**Tipo de dados**|**Detalhes**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Hora da solicitação de sessão. Usado em conjunto com SessionIdSeq para identificar exclusivamente uma sessão. Consulte a tabela [Dialogs tabela Skype para Business Server 2015](dialogs.md) para obter mais informações. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Número de identificação para identificar a sessão. Usado em conjunto com SessionIdTime para identificar exclusivamente uma sessão. Consulte a [tabela no Skype para Business Server 2015 de diálogos](dialogs.md) para obter mais informações. <br/> |
|**InviteTime** <br/> |datetime  <br/> |Hora da primeira solicitação INVITE. Normalmente, este campo é preenchido pelos dados gerados a partir da mensagem de convite inicial da sessão. Se não houver nenhuma mensagem CONVIDAR o campo é preenchido com a data e hora da primeira relevante mensagem SIP (BYE, cancelar, mensagem ou INFO). Normalmente, este campo é preenchido pelos dados gerados a partir da mensagem de convite inicial da sessão. Se não houver nenhuma mensagem CONVIDAR o campo é preenchido com a data e hora da primeira relevante mensagem SIP (BYE, cancelar, mensagem ou INFO).  <br/> |
|**FromUri** <br/> |nvarchar(450)  <br/> |URI do usuário que iniciou a sessão.  <br/> |
|**ToUri** <br/> |nvarchar(450)  <br/> |URI do usuário que ingressou na sessão.  <br/> |
|**FromUriType** <br/> |nvarchar(256)  <br/> |Tipo de URI do usuário que iniciou a sessão. Consulte a [tabela UriTypes](uritypes.md) para obter mais informações. <br/> |
|**ToUriType** <br/> |nvarchar(256)  <br/> |Tipo de URI do usuário que ingressou na sessão. Consulte a [tabela UriTypes](uritypes.md) para obter mais informações. <br/> |
|**FromTenant** <br/> |nvarchar(450)  <br/> |Locatário do usuário que iniciou a sessão. Consulte a [tabela de inquilinos](tenants.md) para obter mais informações. <br/> |
|**ToTenant** <br/> |nvarchar(256)  <br/> |O locatário do usuário que ingressou na sessão. Consulte a [tabela de inquilinos](tenants.md) para obter mais informações. <br/> |
|**FromEndpointId** <br/> |Identificador exclusivo  <br/> |Identificador exclusivo do ponto de extremidade do usuário que iniciou a sessão.  <br/> |
|**ToEndpointId** <br/> |Identificador exclusivo  <br/> |Identificador exclusivo do ponto de extremidade do usuário que ingressou na sessão.  <br/> |
|**EndTime** <br/> |datetime  <br/> |Hora de término da sessão.  <br/> |
|**FromMessageCount** <br/> |int  <br/> |Número de mensagens enviadas pelo usuário que iniciou a sessão.  <br/> |
|**ToMessageCount** <br/> |int  <br/> |Número de mensagens enviadas pelo usuário que ingressou na sessão.  <br/> |
|**FromClientVersion** <br/> |nvarchar(256)  <br/> |Versão do cliente usado pelo usuário que iniciou a sessão.  <br/> |
|**FromClientType** <br/> |int  <br/> |Cliente usado pelo usuário que iniciou a sessão. Consulte a [tabela UserAgentDef](useragentdef.md) para obter mais detalhes. <br/> |
|**FromClientCategory** <br/> |nvarchar(64)  <br/> |Nome da categoria do cliente usado pelo usuário que iniciou a sessão.  <br/> |
|**ToClientVersion** <br/> |nvarchar(256)  <br/> |Versão do cliente usado pelo usuário que ingressou na sessão  <br/> |
|**ToClientType** <br/> |int  <br/> |Cliente usado pelo usuário que ingressou na sessão. Consulte a [tabela UserAgentDef](useragentdef.md) para obter mais detalhes. <br/> |
|**ToClientCategory** <br/> |nvarchar(64)  <br/> |Nome da categoria do cliente usado pelo usuário que ingressou na sessão.  <br/> |
|**TargetUri** <br/> |nvarchar(450)  <br/> |URI do usuário de destino da sessão.  <br/> |
|**TargetUriType** <br/> |nvarchar(450)  <br/> |Tipo de URI do usuário de destino para a sessão. Consulte a [tabela UriTypes](uritypes.md) para obter mais informações. <br/> |
|**OnBehalfOfUri** <br/> |nvarchar(450)  <br/> |URI do usuário em cujo nome a sessão foi iniciada.  <br/> |
|**OnnnBehalfOfUriType** <br/> |nvarchar(256)  <br/> |Tipo de URI do usuário em cujo nome a sessão foi iniciada. Consulte a [tabela UriTypes](uritypes.md) para obter mais informações. <br/> |
|**OnBehalfOfTenant** <br/> |nvarchar(256)  <br/> |Locatário do usuário cujo em nome, a sessão foi iniciada. Consulte a [tabela de inquilinos](tenants.md) para obter mais informações. <br/> |
|**ReferredByUri** <br/> |nvarchar(450)  <br/> |URI do usuário que referenciou a sessão.  <br/> |
|**ReferredByUriType** <br/> |nvarchar(256)  <br/> |Tipo de URI do usuário que referenciou a sessão. Consulte a [tabela UriTypes](uritypes.md) para obter mais informações. <br/> |
|**ReferredByTenant** <br/> |nvarchar(256)  <br/> |Locatário do usuário que referenciou a sessão. Consulte a [tabela de inquilinos](tenants.md) para obter mais informações. <br/> |
|**DialogId** <br/> |varchar(775)  <br/> |ID de diálogo SIP. O formato é:  <br/> diálogo; da marca; a marca  <br/> |
|**CorrelationId** <br/> |Identificador exclusivo  <br/> |GUID usadoo para correlacionar várias sessões.  <br/> |
|**ReplaceDialogIdTime** <br/> |datetime  <br/> |Hora da caixa de diálogo que foi substituído pela sessão. Usado em conjunto com ReplaceDialogIdSeq para identificar exclusivamente uma caixa de diálogo que foram substituída por sessão. Consulte a [tabela no Skype para Business Server 2015 de diálogos](dialogs.md) para obter mais informações. <br/> |
|**ReplaceDialogIdSeq** <br/> |int  <br/> |Número de identificação para identificar a sessão. Usado em conjunto com ReplaceDialogIdTime para identificar exclusivamente uma caixa de diálogo que foram substituída por sessão. Consulte a [tabela no Skype para Business Server 2015 de diálogos](dialogs.md) para obter mais informações. <br/> |
|**ReplacesDialogId** <br/> |varchar(775)  <br/> |ID de diálogo substitui a sessão de SIP. O formato é:  <br/> diálogo; da marca; a marca  <br/> |
|**ResponseTime** <br/> |datetime  <br/> |Tempo de resposta à mensagem INVITE primeira. Normalmente, este campo é preenchido pelos dados gerados a partir da mensagem de convite inicial da sessão. Se não houver nenhuma mensagem CONVIDAR o campo é preenchido com a data e hora da primeira relevante mensagem SIP (BYE, cancelar, mensagem ou INFO).  <br/> |
|**ResponseCode** <br/> |int  <br/> |Código de resposta SIP para o convite de sessão. Normalmente, este campo é preenchido pelos dados gerados a partir da mensagem de convite inicial da sessão. Se não houver nenhuma mensagem CONVIDAR o campo é preenchido com a data e hora da primeira relevante mensagem SIP (BYE, cancelar, mensagem ou INFO).  <br/> |
|**DiagnosticId** <br/> |int  <br/> |ID de diagnóstico capturado dos cabeçalhos do SIP.  <br/> |
|**ContentType** <br/> |nvarchar(256)  <br/> |Tipo de conteúdo para a sessão.  <br/> |
|**FrontEnd** <br/> |nvarchar(256)  <br/> |FQDN do servidor Front-End que capturou os dados da sessão.  <br/> |
|**Pool** <br/> |nvarchar(256)  <br/> |FQDN do pool que capturou os dados para a sessão.  <br/> |
|**FromEdgeServer** <br/> |nvarchar(256)  <br/> |FQDN do servidor de borda usado pelo usuário que iniciou a sessão.  <br/> |
|**ToEdgeServer** <br/> |nvarchar(256)  <br/> |FQDN do servidor de borda usado pelo usuário que iniciou a sessão  <br/> |
|**IsFromInternal** <br/> |bit  <br/> |Indica se o usuário que iniciou a sessão fez logon da rede interna.  <br/> |
|**IsToInternal** <br/> |bit  <br/> |Indica se o usuário que ingressou na sessão fez logon da rede interna.  <br/> |
|**CallPriority** <br/> |nvarchar(256)  <br/> |Chame a prioridade da sessão.  <br/> |
|**FromUserFlag** <br/> |smallint  <br/> |Indica os atributos do usuário que iniciou a sessão. As seguintes definições de atributo são permitidas:  <br/> 0x01 - integrado com telefone de mesa  <br/> |
|**ToUserFlag** <br/> |smallint  <br/> |Indica os atributos do usuário que iniciou a sessão. As seguintes definições de atributo são permitidas:  <br/> 0x01 - integrado com telefone de mesa  <br/> |
|**CallFlag** <br/> |smallint  <br/> |Indica os atributos de chamada. As seguintes definições de atributo são permitidas:  <br/> 0x01 - sessão repetida  <br/> 0x02 - uma chamada feita pelo operador em nome de um grupo de resposta  <br/> |
|**Local** <br/> |varchar (max)  <br/> |Local da chamada de emergência.  <br/> |
|**LastModifiedTime** <br/> |DateTime  <br/> |Para uso interno pelo serviço de monitoramento.  <br/> Este campo foi introduzido no Skype para Business Server 2015.  <br/> |
   

