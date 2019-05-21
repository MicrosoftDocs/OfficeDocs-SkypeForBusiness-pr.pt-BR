---
title: Tabela ConferenceSessionDetails no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9eae6a54-69fd-4966-aa17-7ecee1297ad8
description: Cada registro representa uma sessão de conferência, que pode ser a sessão com foco ou a sessão com um servidor de conferência específico.
ms.openlocfilehash: 40216d159c9d52dcf8c22f7fe7b915255ed0f741
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296438"
---
# <a name="conferencesessiondetails-table-in-skype-for-business-server-2015"></a>Tabela ConferenceSessionDetails no Skype for Business Server 2015
 
Cada registro representa uma sessão de conferência, que pode ser a sessão com foco ou a sessão com um servidor de conferência específico.
  
|**Coluna**|**Tipo de dados**|**Chave/índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**Id_da_sessãotime** <br/> |DateTime  <br/> |Primário, estrangeiro  <br/> |Tempo de solicitação de sessão; usado em conjunto com **SessionIdSeq** para identificar uma sessão de conferência com exclusividade. Consulte a [tabela de diálogos no Skype for Business Server 2015](dialogs.md) para obter mais informações. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primário, estrangeiro  <br/> |Número de identificação para identificar a sessão. Usado em conjunto com **** a identificação_da_sessãotime para identificar exclusivamente uma sessão de conferência. Consulte a [tabela de diálogos no Skype for Business Server 2015](dialogs.md) para obter mais informações. * <br/> |
|**ConferenceUriId** <br/> |int  <br/> |Exterior  <br/> |URI da conferência em foco relacionado a esta sessão. Consulte a [tabela ConferenceUris no Skype for Business Server 2015](conferenceuris.md) para obter mais informações. Esse URI é um URI de conferência baseado em foco. <br/> |
|**ConfInstance** <br/> |Identificador  <br/> ||Identificador que diferencia as instâncias de conferências recorrentes. Cada instância de conferência recorrente tem o mesmo ConferenceURI, mas um valor ConfInstance diferente.  <br/> Este campo foi apresentado no Microsoft Lync Server 2013.  <br/> |
|**McuConferenceUriId** <br/> |int  <br/> |Exterior  <br/> |URL de conferência do servidor de conferência relacionada a esta sessão. Consulte a [tabela ConferenceUris no Skype for Business Server 2015](conferenceuris.md) para obter mais informações. Esse URI é o URI da conferência baseada no servidor de conferência. Para sessões de conferência de foco, esta coluna será nula. <br/> |
|**ID** <br/> |int  <br/> |Exterior  <br/> |ID de um usuário na sessão de conferência. Para obter mais informações, consulte a [tabela usuários](users.md) . <br/> |
|**Userendpointid** <br/> |identificador  <br/> ||Um GUID para identificar a instância do ponto de extremidade. Por exemplo, se um usuário fizer logon em máquinas diferentes com a mesma conta, cada computador terá uma ID de ponto de extremidade diferente.  <br/> |
|**OnBehalfOfId** <br/> |int  <br/> |Exterior  <br/> |Indica a ID do usuário de quem o chamador está em nome. Para obter mais informações, consulte a [tabela usuários](users.md) . <br/> |
|**ReferredById** <br/> |int  <br/> |Exterior  <br/> |ID do usuário por quem a chamada é referida. Para obter mais informações, consulte a [tabela usuários](users.md) . <br/> |
|**UserClientVersionId** <br/> |int  <br/> |Exterior  <br/> |Versão do cliente usada pelo usuário da conferência. Consulte a [tabela ClientVersions no Skype for Business Server 2015](clientversions.md) para obter mais informações. <br/> |
|**ConfClientVersionId** <br/> |int  <br/> |Exterior  <br/> |Versão do cliente usada pelo servidor de conferência. Consulte a [tabela ClientVersions no Skype for Business Server 2015](clientversions.md) para obter mais informações. <br/> |
|**ReplaceDialogIdTime** <br/> |datetime  <br/> |Exterior  <br/> |Número de identificação para identificar a caixa de diálogo que foi substituída pela sessão atual. Consulte a [tabela de diálogos no Skype for Business Server 2015](dialogs.md) para obter mais informações. <br/> |
|**ReplaceDialogIdSeq** <br/> |int  <br/> |Exterior  <br/> |Número de identificação para identificar a sessão. Usado em conjunto com **ReplacesDialogIdTime** para identificar exclusivamente uma sessão substituída por esta sessão. Consulte a [tabela de diálogos no Skype for Business Server 2015](dialogs.md) para obter mais informações. <br/> |
|**IsStartedByConfServer** <br/> |bit  <br/> ||Indica se a sessão foi iniciada pelo servidor de conferência.  <br/> |
|**IsEndedByConfServer** <br/> |bit  <br/> ||Indica se a sessão terminou pelo servidor de conferência.  <br/> |
|**IsUserInternal** <br/> |bit  <br/> ||Se o usuário está conectado de Internal ou not.  <br/> |
|**ResponseCode** <br/> |int  <br/> ||Código de resposta do SIP (Session Initiation Protocol) para o convite da sessão. Geralmente, esse campo é preenchido por dados gerados da mensagem de convite inicial na sessão. Se não houver nenhuma mensagem de convite, o campo será preenchido com a data e a hora da primeira mensagem SIP relevante (até mais, cancelamento, mensagem ou informações).  <br/> |
|**Diagnosticid** <br/> |int  <br/> ||ID de diagnóstico capturada do cabeçalho SIP.  <br/> |
|**ServerID** <br/> |int  <br/> |Exterior  <br/> |ID do servidor front-end usado para esta sessão. Consulte a [tabela servidores](servers.md) para obter mais informações. <br/> |
|**Poolid** <br/> |int  <br/> |Exterior  <br/> |ID do pool no qual a sessão foi capturada. Consulte a [tabela de grupos](pools.md) para obter mais informações. <br/> |
|**MediationServerId** <br/> |int  <br/> |Exterior  <br/> |O servidor de mediação que a chamada está usando. Consulte a [tabela MediationServers](mediationservers.md) para obter mais informações. <br/> |
|**Gatewayid** <br/> |int  <br/> |Exterior  <br/> |O gateway que a chamada está usando. Consulte a [tabela gateways no Skype for Business Server 2015](gateways.md) para obter mais informações. <br/> |
|**EdgeServerId** <br/> |int  <br/> |Exterior  <br/> |O servidor de borda que a chamada está usando. Consulte a [tabela EdgeServers no Skype for Business Server 2015](edgeservers.md) para obter mais informações. <br/> |
|**ContentTypeid** <br/> |int  <br/> |Exterior  <br/> |Tipo de conteúdo usado na sessão. Consulte a [tabela ContentTypes no Skype for Business Server 2015](contenttypes.md) para obter mais informações. <br/> |
|**Invitetime** <br/> |datetime  <br/> ||A hora da primeira solicitação INVITE. Geralmente, esse campo é preenchido por dados gerados da mensagem de convite inicial na sessão. Se não houver nenhuma mensagem de convite, o campo será preenchido com a data e a hora da primeira mensagem SIP relevante (até mais, cancelamento, mensagem ou informações).  <br/> |
|**ResponseTime** <br/> |datetime  <br/> ||Hora da primeira resposta SIP. Geralmente, esse campo é preenchido por dados gerados da mensagem de convite inicial na sessão. Se não houver nenhuma mensagem de convite, o campo será preenchido com a data e a hora da primeira mensagem SIP relevante (até mais, cancelamento, mensagem ou informações).  <br/> |
|**SessionEndTime** <br/> |datetime  <br/> ||A hora de término da sessão.  <br/> |
|**UriTypeId** <br/> |tinyint  <br/> |Exterior  <br/> |Contém o valor do tipo URI de MCU na [tabela UriTypes](uritypes.md). Este campo é usado para melhorar o desempenho das consultas.  <br/> Este campo foi apresentado no Microsoft Lync Server 2013.  <br/> |
|**Sinalizador** <br/> |smallint  <br/> || Um conjunto de bits que indica os atributos de usuário. As definições de atributo a seguir estão listadas: <br/>  Integrado ao telefone de mesa-1 <br/> |
|**CallFlag** <br/> |smallint  <br/> || Um conjunto de bits que indica os atributos da chamada. As definições de atributo a seguir estão listadas: <br/>  Sessão 1 repetida <br/> |
|**LastModifiedtime** <br/> |DateTime  <br/> ||Para uso interno pelo serviço de monitoramento.  <br/> Este campo foi apresentado no Skype for Business Server 2015.  <br/> |
   
\*Para a maioria das sessões, o SessionIdSeq terá o valor de 1. Se várias sessões começarem exatamente ao mesmo tempo, o SessionIdSeq de uma será 1, por outro será 2, e assim por diante.
  

