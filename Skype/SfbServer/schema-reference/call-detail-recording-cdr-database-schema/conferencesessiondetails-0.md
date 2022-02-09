---
title: Tabela ConferenceSessionDetails Skype for Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 9eae6a54-69fd-4966-aa17-7ecee1297ad8
description: Cada registro representa uma sessão de conferência, que poderia ser a sessão com Foco ou a sessão com um servidor de conferência específico.
ms.openlocfilehash: d6bb5b76f7ad8a5d5843be91db0ab420eea3d9f4
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62416384"
---
# <a name="conferencesessiondetails-table-in-skype-for-business-server-2015"></a>Tabela ConferenceSessionDetails Skype for Business Server 2015
 
Cada registro representa uma sessão de conferência, que poderia ser a sessão com Foco ou a sessão com um servidor de conferência específico.
  
|**Coluna**|**Tipo de dados**|**Chave/Índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |Datetime  <br/> |Primária, Estrangeira  <br/> |Tempo da solicitação da sessão; usado em conjunto com **SessionIdSeq** para identificar de forma única uma sessão de conferência. Consulte a [tabela Dialogs no Skype for Business Server 2015](dialogs.md) para obter mais informações. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primário, Estrangeiro  <br/> |O número de ID para identificar a sessão. Usado em conjunto com **SessionIdTime** para identificar exclusivamente uma sessão de conferência. Consulte a [tabela Dialogs no Skype for Business Server 2015](dialogs.md) para obter mais informações. * <br/> |
|**ConferenceUriId** <br/> |int  <br/> |Foreign  <br/> |URI da conferência com foco relacionada a esta sessão. Consulte a [tabela ConferenceUris no Skype for Business Server 2015](conferenceuris.md) para obter mais informações. Esta é uma URI de conferência baseada em Foco. <br/> |
|**ConfInstance** <br/> |uniqueIdentifier  <br/> ||Identificador que diferencia instâncias de conferências recorrentes. Cada instância de conferência recorrente possui o mesmo ConferenceURI, mas um valor ConfInstance diferente.  <br/> Este campo foi introduzido no Microsoft Lync Server 2013.  <br/> |
|**McuConferenceUriId** <br/> |int  <br/> |Foreign  <br/> |URI da conferência do servidor de conferências relacionada a esta sessão. Consulte a [tabela ConferenceUris no Skype for Business Server 2015](conferenceuris.md) para obter mais informações. Esta é a URI de conferência baseada em servidor. Para sessões de conferência com foco, esta coluna estará nula. <br/> |
|**UserId** <br/> |int  <br/> |Foreign  <br/> |ID de um usuário na sessão de conferência. Consulte a [tabela Usuários para](users.md) obter mais informações. <br/> |
|**UserEndpointId** <br/> |uniqueidentifier  <br/> ||Um GUID para identificar a instância do ponto de extremidade. Por exemplo, se um usuário faz logon em máquinas diferentes com a mesma conta, cada máquina terá um ID de ponto de extremidade diferente.  <br/> |
|**OnBehalfOfId** <br/> |int  <br/> |Foreign  <br/> |Indica a ID do usuário que está em nome do chamador. Consulte a [tabela Usuários para](users.md) obter mais informações. <br/> |
|**ReferredById** <br/> |int  <br/> |Foreign  <br/> |A ID do usuário a quem se refere a chamada. Consulte a [tabela Usuários para](users.md) obter mais informações. <br/> |
|**UserClientVersionId** <br/> |int  <br/> |Foreign  <br/> |Versão do cliente usado pelo usuário da conferência. Consulte a [tabela ClientVersions no Skype for Business Server 2015](clientversions.md) para obter mais informações. <br/> |
|**ConfClientVersionId** <br/> |int  <br/> |Foreign  <br/> |Versão do cliente usado pelo servidor de conferências. Consulte a [tabela ClientVersions no Skype for Business Server 2015](clientversions.md) para obter mais informações. <br/> |
|**ReplaceDialogIdTime** <br/> |datetime  <br/> |Foreign  <br/> |O número de identificação para identificar a caixa de diálogo que foi substituída pela sessão atual. Consulte a [tabela Dialogs no Skype for Business Server 2015](dialogs.md) para obter mais informações. <br/> |
|**ReplaceDialogIdSeq** <br/> |int  <br/> |Foreign  <br/> |O número de identificação para identificar a sessão. Usado em conjunto com **ReplacesDialogIdTime** para identificar exclusivamente uma sessão que é substituída por esta sessão. Consulte a [tabela Dialogs no Skype for Business Server 2015](dialogs.md) para obter mais informações. <br/> |
|**IsStartedByConfServer** <br/> |bit  <br/> ||Indica se a sessão é iniciada pelo Servidor de conferências.  <br/> |
|**IsEndedByConfServer** <br/> |bit  <br/> ||Indica se a sessão é encerrada pelo Servidor de conferências.  <br/> |
|**IsUserInternal** <br/> |bit  <br/> ||Se o usuário está conectado de um local interno ou não.  <br/> |
|**ResponseCode** <br/> |int  <br/> ||Código de resposta do Protocolo de Iniciação de Sessão (SIP) para o convite da sessão. Este campo é geralmente preenchido por dados gerados da mensagem INVITE inicial em uma sessão. Caso não haja nenhuma mensagem CONVIDAR, o campo é preenchidos com a data e horário da primeira mensagem de SIP relevante (ATÉ LOGO, CANCELAR, MENSAGEM ou INFO).  <br/> |
|**DiagnosticId** <br/> |int  <br/> ||ID de diagnóstico capturado do cabeçalho do SIP.  <br/> |
|**ServerId** <br/> |int  <br/> |Foreign  <br/> |A ID do servidor Front-End usado para esta sessão. Consulte a [tabela Servidores para](servers.md) obter mais informações. <br/> |
|**PoolId** <br/> |int  <br/> |Foreign  <br/> |A ID do pool no qual a sessão foi capturada. Consulte a [tabela Pools para](pools.md) obter mais informações. <br/> |
|**MediationServerId** <br/> |int  <br/> |Foreign  <br/> |O Servidor de Mediação que a chamada está usando. Consulte a tabela [MediationServers para](mediationservers.md) obter mais informações. <br/> |
|**GatewayId** <br/> |int  <br/> |Foreign  <br/> |O gateway que a chamada está usando. Consulte a [tabela Gateways no Skype for Business Server 2015](gateways.md) para obter mais informações. <br/> |
|**EdgeServerId** <br/> |int  <br/> |Foreign  <br/> |O Servidor de Borda que a chamada está usando. Consulte a [tabela EdgeServers no Skype for Business Server 2015](edgeservers.md) para obter mais informações. <br/> |
|**ContentTypeId** <br/> |int  <br/> |Foreign  <br/> |Tipo de conteúdo usado na sessão. Consulte a [tabela ContentTypes no Skype for Business Server 2015](contenttypes.md) para obter mais informações. <br/> |
|**InviteTime** <br/> |datetime  <br/> ||A hora da primeira solicitação INVITE. Este campo é geralmente preenchido por dados gerados da mensagem INVITE inicial em uma sessão. Se não houver mensagem INVITE, então o campo será preenchido com a data e hora da primeira mensagem SIP relevante (BYE, CANCEL, MESSAGE ou INFO).  <br/> |
|**ResponseTime** <br/> |datetime  <br/> ||A hora da primeira SIP RESPONSE. Este campo é geralmente preenchido por dados gerados da mensagem INVITE inicial em uma sessão. Se não houver mensagem INVITE, então o campo será preenchido com a data e hora da primeira mensagem SIP relevante (BYE, CANCEL, MESSAGE ou INFO).  <br/> |
|**SessionEndTime** <br/> |datetime  <br/> ||O horário em que a sessão terminou.  <br/> |
|**UriTypeId** <br/> |tinyint  <br/> |Foreign  <br/> |Contém o valor de tipo de URI MCU da [tabela UriTypes](uritypes.md). Esse campo é usado para melhorar o desempenho da consulta.  <br/> Este campo foi introduzido no Microsoft Lync Server 2013.  <br/> |
|**UserFlag** <br/> |smallint  <br/> || Um conjunto de bits que indica os atributos do usuário. As definições de atributo a seguir são listadas: <br/>  Integrado com telefone de mesa - 1 <br/> |
|**CallFlag** <br/> |smallint  <br/> || Um conjunto de bits que indica os atributos da chamada. As definições de atributo a seguir são listadas: <br/>  Sessão Repetida - 1 <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||Para uso interno pelo serviço de Monitoramento.  <br/> Este campo foi introduzido no Skype for Business Server 2015.  <br/> |
   
\* Para a maioria das sessões, SessionIdSeq terá o valor de 1. Se várias sessões iniciam exatamente ao mesmo tempo, o SessionIdSeq para uma delas será 1 e para a outra será 2 e assim por diante.
  

