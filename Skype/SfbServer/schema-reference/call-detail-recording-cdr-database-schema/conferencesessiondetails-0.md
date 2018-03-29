---
title: Tabela ConferenceSessionDetails Skype para Business Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 7/15/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9eae6a54-69fd-4966-aa17-7ecee1297ad8
description: Cada registro representa uma sessão de conferência, que poderia ser a sessão com foco ou a sessão com um servidor de conferência específico.
ms.openlocfilehash: 72f2eb11c79348ad72815be7acfd337a40d288af
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="conferencesessiondetails-table-in-skype-for-business-server-2015"></a>Tabela ConferenceSessionDetails Skype para Business Server 2015
 
Cada registro representa uma sessão de conferência, que poderia ser a sessão com foco ou a sessão com um servidor de conferência específico.
  
|**Coluna**|**Tipo de dados**|**Índice de chaves /**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |DateTime  <br/> |Primária, estrangeira  <br/> |Hora da solicitação de sessão; usado em conjunto com **SessionIdSeq** para identificar exclusivamente uma sessão de conferência. Consulte a [tabela no Skype para Business Server 2015 de diálogos](dialogs.md) para obter mais informações. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primária, estrangeira  <br/> |Número de identificação para identificar a sessão. Usado em conjunto com **SessionIdTime** para identificar exclusivamente uma sessão de conferência. Consulte a [tabela no Skype para Business Server 2015 de diálogos](dialogs.md) para obter mais informações. * <br/> |
|**ConferenceUriId** <br/> |int  <br/> |Externa  <br/> |URI de conferência do foco relacionada nesta sessão. Consulte a [tabela ConferenceUris do Skype para Business Server 2015](conferenceuris.md) para obter mais informações. Esse URI é um URI de conferência baseadas em foco. <br/> |
|**ConfInstance** <br/> |Identificador exclusivo  <br/> ||Identificador que diferencia entre instâncias de conferências recorrentes. Cada instância de conferência recorrente tem o mesmo ConferenceURI, mas um valor de ConfInstance diferente.  <br/> Este campo foi introduzido no Microsoft Lync Server 2013.  <br/> |
|**McuConferenceUriId** <br/> |int  <br/> |Externa  <br/> |Conferência de servidor de conferência URI relacionada nesta sessão. Consulte a [tabela ConferenceUris do Skype para Business Server 2015](conferenceuris.md) para obter mais informações. Esse URI é o conferência baseadas em servidor URI de conferência. Para sessões de conferência de foco, esta coluna será nula. <br/> |
|**UserId** <br/> |int  <br/> |Externa  <br/> |ID de um usuário da sessão de conferência. Consulte a [tabela de usuários](users.md) para obter mais informações. <br/> |
|**UserEndpointId** <br/> |Identificador exclusivo  <br/> ||Um GUID para identificar a instância do ponto de extremidade. Por exemplo, se um usuário fizer logon máquinas diferentes com a mesma conta, em seguida, cada máquina terá uma ID de ponto de extremidade diferente.  <br/> |
|**OnBehalfOfId** <br/> |int  <br/> |Externa  <br/> |Indica a identificação do usuário do que o chamador está em nome. Consulte a [tabela de usuários](users.md) para obter mais informações. <br/> |
|**ReferredById** <br/> |int  <br/> |Externa  <br/> |ID do usuário por que a chamada é conhecida. Consulte a [tabela de usuários](users.md) para obter mais informações. <br/> |
|**UserClientVersionId** <br/> |int  <br/> |Externa  <br/> |Versão do cliente usado pelo usuário de conferência. Consulte a [tabela ClientVersions Skype para Business Server 2015](clientversions.md) para obter mais informações. <br/> |
|**ConfClientVersionId** <br/> |int  <br/> |Externa  <br/> |Versão do cliente usado pelo servidor de conferência. Consulte a [tabela ClientVersions Skype para Business Server 2015](clientversions.md) para obter mais informações. <br/> |
|**ReplaceDialogIdTime** <br/> |datetime  <br/> |Externa  <br/> |Número de identificação para identificar a caixa de diálogo que foi substituída pela sessão atual. Consulte a [tabela no Skype para Business Server 2015 de diálogos](dialogs.md) para obter mais informações. <br/> |
|**ReplaceDialogIdSeq** <br/> |int  <br/> |Externa  <br/> |Número de identificação para identificar a sessão. Usado em conjunto com **ReplacesDialogIdTime** para identificar exclusivamente uma sessão que foi substituída por esta sessão. Consulte a [tabela no Skype para Business Server 2015 de diálogos](dialogs.md) para obter mais informações. <br/> |
|**IsStartedByConfServer** <br/> |bit  <br/> ||Indica se a sessão é iniciada pelo servidor de conferências.  <br/> |
|**IsEndedByConfServer** <br/> |bit  <br/> ||Indica se a sessão é encerrada pelo servidor de conferência.  <br/> |
|**IsUserInternal** <br/> |bit  <br/> ||Se usuário está conectado internamente ou não.  <br/> |
|**ResponseCode** <br/> |int  <br/> ||Código de resposta sessão Initiation Protocol (SIP) para o convite de sessão. Normalmente, este campo é preenchido pelos dados gerados a partir da mensagem de convite inicial da sessão. Se não houver nenhuma mensagem CONVIDAR o campo é preenchido com a data e hora da primeira relevante mensagem SIP (BYE, cancelar, mensagem ou INFO).  <br/> |
|**DiagnosticId** <br/> |int  <br/> ||ID de diagnóstico capturado do cabeçalho SIP.  <br/> |
|**ServerId** <br/> |int  <br/> |Externa  <br/> |ID do servidor de front-end usado nesta sessão. Consulte a [tabela de servidores](servers.md) para obter mais informações. <br/> |
|**PoolId** <br/> |int  <br/> |Externa  <br/> |ID do pool no qual a sessão foi capturada. Consulte a [tabela de Pools](pools.md) para obter mais informações. <br/> |
|**MediationServerId** <br/> |int  <br/> |Externa  <br/> |O servidor de mediação a chamada está usando. Consulte a [tabela MediationServers](mediationservers.md) para obter mais informações. <br/> |
|**GatewayId** <br/> |int  <br/> |Externa  <br/> |O gateway a chamada está usando. Consulte a [tabela de Gateways no Skype para Business Server 2015](gateways.md) para obter mais informações. <br/> |
|**EdgeServerId** <br/> |int  <br/> |Externa  <br/> |O servidor de borda a chamada está usando. Consulte a [tabela EdgeServers no Skype para Business Server 2015](edgeservers.md) para obter mais informações. <br/> |
|**ContentTypeId** <br/> |int  <br/> |Externa  <br/> |Tipo de conteúdo usado na sessão. Consulte a [tabela ContentTypes Skype para Business Server 2015](contenttypes.md) para obter mais informações. <br/> |
|**InviteTime** <br/> |datetime  <br/> ||A hora da primeira solicitação INVITE. Normalmente, este campo é preenchido pelos dados gerados a partir da mensagem de convite inicial da sessão. Se não houver nenhuma mensagem CONVIDAR o campo é preenchido com a data e hora da primeira relevante mensagem SIP (BYE, cancelar, mensagem ou INFO).  <br/> |
|**ResponseTime** <br/> |datetime  <br/> ||Hora da primeira resposta SIP. Normalmente, este campo é preenchido pelos dados gerados a partir da mensagem de convite inicial da sessão. Se não houver nenhuma mensagem CONVIDAR o campo é preenchido com a data e hora da primeira relevante mensagem SIP (BYE, cancelar, mensagem ou INFO).  <br/> |
|**SessionEndTime** <br/> |datetime  <br/> ||A hora em que a sessão terminou.  <br/> |
|**UriTypeId** <br/> |tinyint  <br/> |Externa  <br/> |Contém o valor de tipo de MCU URI da [tabela UriTypes](uritypes.md). Este campo é usado para melhorar o desempenho da consulta.  <br/> Este campo foi introduzido no Microsoft Lync Server 2013.  <br/> |
|**UserFlag** <br/> |smallint  <br/> || Um conjunto de bits que indica os atributos de usuário. As seguintes definições de atributo são listadas: <br/>  Integrado com telefone de mesa - 1 <br/> |
|**CallFlag** <br/> |smallint  <br/> || Um conjunto de bits que indica os atributos de chamada. As seguintes definições de atributo são listadas: <br/>  Sessão repetida - 1 <br/> |
|**LastModifiedTime** <br/> |DateTime  <br/> ||Para uso interno pelo serviço de monitoramento.  <br/> Este campo foi introduzido no Skype para Business Server 2015.  <br/> |
   
\*Para a maioria das sessões, SessionIdSeq terá o valor de 1. Se várias sessões iniciar exatamente simultaneamente, o SessionIdSeq para um será 1, para outro será 2 e assim por diante.
  

