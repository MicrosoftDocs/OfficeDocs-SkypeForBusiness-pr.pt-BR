---
title: Exibição SessionDetails
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ea328c6f-cf22-48dd-8f7f-f1666c9148c8
description: A exibição SessionDetails armazena informações sobre sessões ponto a ponto, que podem ser chamadas telefônicas VoIP, VoIP, uma sessão de IM de duas partes ou outro tipo de sessão. Este modo de exibição foi apresentado no Microsoft Lync Server 2013.
ms.openlocfilehash: 627d038389098583b5e42f73e8dd0a1cc339d014
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295843"
---
# <a name="sessiondetails-view"></a>Exibição SessionDetails
 
A exibição SessionDetails armazena informações sobre sessões ponto a ponto, que podem ser chamadas telefônicas VoIP, VoIP, uma sessão de IM de duas partes ou outro tipo de sessão. Este modo de exibição foi apresentado no Microsoft Lync Server 2013.
  
|**Coluna**|**Tipo de dados**|**Detalhes**|
|:-----|:-----|:-----|
|**Id_da_sessãotime** <br/> |datetime  <br/> |Tempo de solicitação de sessão. Usado em conjunto com o SessionIdSeq para identificar exclusivamente uma sessão. Consulte a [tabela de diálogos na tabela do Skype for Business Server 2015](dialogs.md) para obter mais informações. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Número de identificação para identificar a sessão. Usado em conjunto com a Identificação_da_sessãotime para identificar exclusivamente uma sessão. Consulte a [tabela de diálogos no Skype for Business Server 2015](dialogs.md) para obter mais informações. <br/> |
|**Invitetime** <br/> |datetime  <br/> |Hora da primeira solicitação INVITE. Geralmente, esse campo é preenchido por dados gerados da mensagem de convite inicial na sessão. Se não houver nenhuma mensagem de convite, o campo será preenchido com a data e a hora da primeira mensagem SIP relevante (até mais, cancelamento, mensagem ou informações). Geralmente, esse campo é preenchido por dados gerados da mensagem de convite inicial na sessão. Se não houver nenhuma mensagem de convite, o campo será preenchido com a data e a hora da primeira mensagem SIP relevante (até mais, cancelamento, mensagem ou informações).  <br/> |
|**FromUri** <br/> |nvarchar (450)  <br/> |URL do usuário que iniciou a sessão.  <br/> |
|**ToUri** <br/> |nvarchar (450)  <br/> |URL do usuário que ingressou na sessão.  <br/> |
|**FromUriType** <br/> |nvarchar(256)  <br/> |Tipo de URI do usuário que iniciou a sessão. Consulte a [tabela UriTypes](uritypes.md) para obter mais informações. <br/> |
|**ToUriType** <br/> |nvarchar(256)  <br/> |Tipo de URI do usuário que ingressou na sessão. Consulte a [tabela UriTypes](uritypes.md) para obter mais informações. <br/> |
|**FromTenant** <br/> |nvarchar (450)  <br/> |Locatário do usuário que iniciou a sessão. Consulte a [tabela locatários](tenants.md) para obter mais informações. <br/> |
|**Tolocatário** <br/> |nvarchar(256)  <br/> |O locatário do usuário que ingressou na sessão. Consulte a [tabela locatários](tenants.md) para obter mais informações. <br/> |
|**FromEndpointId** <br/> |identificador  <br/> |Identificador exclusivo do ponto de extremidade do usuário que iniciou a sessão.  <br/> |
|**Toendpointid** <br/> |identificador  <br/> |Identificador exclusivo do ponto de extremidade do usuário que ingressou na sessão.  <br/> |
|**EndTime** <br/> |datetime  <br/> |Hora de término da sessão.  <br/> |
|**FromMessageCount** <br/> |int  <br/> |Número de mensagens enviadas pelo usuário que iniciou a sessão.  <br/> |
|**ToMessageCount** <br/> |int  <br/> |Número de mensagens enviadas pelo usuário que ingressou na sessão.  <br/> |
|**FromClientVersion** <br/> |nvarchar(256)  <br/> |Versão do cliente usada pelo usuário que iniciou a sessão.  <br/> |
|**FromClientType** <br/> |int  <br/> |Cliente usado pelo usuário que iniciou a sessão. Consulte a [tabela UserAgentDef](useragentdef.md) para obter mais detalhes. <br/> |
|**FromClientCategory** <br/> |nvarchar (64)  <br/> |Nome da categoria do cliente usado pelo usuário que iniciou a sessão.  <br/> |
|**ToClientVersion** <br/> |nvarchar(256)  <br/> |Versão do cliente usada pelo usuário que ingressou na sessão  <br/> |
|**Toclientetype** <br/> |int  <br/> |Cliente usado pelo usuário que ingressou na sessão. Consulte a [tabela UserAgentDef](useragentdef.md) para obter mais detalhes. <br/> |
|**ToClientCategory** <br/> |nvarchar (64)  <br/> |Nome da categoria do cliente usado pelo usuário que ingressou na sessão.  <br/> |
|**TargetUri** <br/> |nvarchar (450)  <br/> |URL do usuário de destino da sessão.  <br/> |
|**TargetUriType** <br/> |nvarchar (450)  <br/> |Tipo de URI do usuário de destino da sessão. Consulte a [tabela UriTypes](uritypes.md) para obter mais informações. <br/> |
|**OnBehalfOfUri** <br/> |nvarchar (450)  <br/> |O URI do usuário em nome do qual a sessão foi iniciada.  <br/> |
|**OnnnBehalfOfUriType** <br/> |nvarchar(256)  <br/> |Tipo de URI do usuário em nome do qual a sessão foi iniciada. Consulte a [tabela UriTypes](uritypes.md) para obter mais informações. <br/> |
|**OnBehalfOfTenant** <br/> |nvarchar(256)  <br/> |Locatário do usuário cujo nome da sessão foi iniciado. Consulte a [tabela locatários](tenants.md) para obter mais informações. <br/> |
|**ReferredByUri** <br/> |nvarchar (450)  <br/> |URL do usuário que fez a chamada para a sessão.  <br/> |
|**ReferredByUriType** <br/> |nvarchar(256)  <br/> |Tipo de URI do usuário que a fez referência à sessão. Consulte a [tabela UriTypes](uritypes.md) para obter mais informações. <br/> |
|**ReferredByTenant** <br/> |nvarchar(256)  <br/> |Locatário do usuário que fez a chamada para a sessão. Consulte a [tabela locatários](tenants.md) para obter mais informações. <br/> |
|**Caixa de diálogo** <br/> |varchar (775)  <br/> |ID da caixa de diálogo SIP. O formato é:  <br/> caixa de diálogo; de-marca; até-marca  <br/> |
|**CorrelationId** <br/> |identificador  <br/> |GUID usado para correlacionar várias sessões.  <br/> |
|**ReplaceDialogIdTime** <br/> |datetime  <br/> |A hora da caixa de diálogo que foi substituída pela sessão. Usado em conjunto com ReplaceDialogIdSeq para identificar exclusivamente uma caixa de diálogo que é substituída pela sessão. Consulte a [tabela de diálogos no Skype for Business Server 2015](dialogs.md) para obter mais informações. <br/> |
|**ReplaceDialogIdSeq** <br/> |int  <br/> |Número de identificação para identificar a sessão. Usado em conjunto com ReplaceDialogIdTime para identificar exclusivamente uma caixa de diálogo que é substituída pela sessão. Consulte a [tabela de diálogos no Skype for Business Server 2015](dialogs.md) para obter mais informações. <br/> |
|**ReplacesDialogId** <br/> |varchar (775)  <br/> |ID da caixa de diálogo SIP a sessão substitui. O formato é:  <br/> caixa de diálogo; de-marca; até-marca  <br/> |
|**ResponseTime** <br/> |datetime  <br/> |Hora da resposta à primeira mensagem de convite. Geralmente, esse campo é preenchido por dados gerados da mensagem de convite inicial na sessão. Se não houver nenhuma mensagem de convite, o campo será preenchido com a data e a hora da primeira mensagem SIP relevante (até mais, cancelamento, mensagem ou informações).  <br/> |
|**ResponseCode** <br/> |int  <br/> |Código de resposta SIP para o convite da sessão. Geralmente, esse campo é preenchido por dados gerados da mensagem de convite inicial na sessão. Se não houver nenhuma mensagem de convite, o campo será preenchido com a data e a hora da primeira mensagem SIP relevante (até mais, cancelamento, mensagem ou informações).  <br/> |
|**Diagnosticid** <br/> |int  <br/> |ID de diagnóstico capturada de cabeçalhos SIP.  <br/> |
|**ContentType** <br/> |nvarchar(256)  <br/> |Tipo de conteúdo da sessão.  <br/> |
|**FrontEnd** <br/> |nvarchar(256)  <br/> |FQDN do servidor de front-end que capturou os dados para a sessão.  <br/> |
|**Pool** <br/> |nvarchar(256)  <br/> |FQDN do pool que capturou os dados da sessão.  <br/> |
|**FromEdgeServer** <br/> |nvarchar(256)  <br/> |FQDN do servidor de borda usado pelo usuário que iniciou a sessão.  <br/> |
|**ToEdgeServer** <br/> |nvarchar(256)  <br/> |FQDN do servidor de borda usado pelo usuário que iniciou a sessão  <br/> |
|**IsFromInternal** <br/> |bit  <br/> |Indica se o usuário que iniciou a sessão está conectada a partir da rede interna.  <br/> |
|**IsToInternal** <br/> |bit  <br/> |Indica se o usuário que ingressou na sessão que se conectou na rede interna.  <br/> |
|**CallPriority** <br/> |nvarchar(256)  <br/> |Prioridade da chamada da sessão.  <br/> |
|**FromUserFlag** <br/> |smallint  <br/> |Indica os atributos do usuário que iniciou a sessão. As definições de atributo a seguir são permitidas:  <br/> 0x01-integrado ao telefone desktop  <br/> |
|**ToUserFlag** <br/> |smallint  <br/> |Indica os atributos do usuário que iniciou a sessão. As definições de atributo a seguir são permitidas:  <br/> 0x01-integrado ao telefone desktop  <br/> |
|**CallFlag** <br/> |smallint  <br/> |Indica os atributos da chamada. As definições de atributo a seguir são permitidas:  <br/> 0x01-sessão repetida  <br/> 0x02-uma chamada feita pelo agente em nome de um grupo de resposta  <br/> |
|**Local** <br/> |varchar (max)  <br/> |Local de chamada de emergência.  <br/> |
|**LastModifiedtime** <br/> |DateTime  <br/> |Para uso interno pelo serviço de monitoramento.  <br/> Este campo foi apresentado no Skype for Business Server 2015.  <br/> |
   

