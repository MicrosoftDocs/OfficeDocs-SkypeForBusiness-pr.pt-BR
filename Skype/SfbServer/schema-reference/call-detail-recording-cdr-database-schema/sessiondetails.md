---
title: Tabela SessionDetails
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 783d2508-e31f-4b54-be0c-63aa5ec21c04
description: Cada registro representa uma sessão ponto a ponto, que poderia ser uma chamada telefônica VoIP-VoIP, uma sessão de IM de duas partes ou outro tipo de sessão. Você pode executar uma junção de tabela com a tabela Mídia para encontrar os detalhes de cada mídia envolvida nesta sessão.
ms.openlocfilehash: e7b89dc242fb3e4adec215948915218b579631ef
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60863428"
---
# <a name="sessiondetails-table"></a>Tabela SessionDetails
 
Cada registro representa uma sessão ponto a ponto, que poderia ser uma chamada telefônica VoIP-VoIP, uma sessão de IM de duas partes ou outro tipo de sessão. Você pode executar uma junção de tabela com a [tabela Mídia](media.md) para encontrar os detalhes de cada mídia envolvida nesta sessão.
  
Observe que os campos IsUser1IntegratedWithDeskPhone e IsUser2IntegratedWithDeskPhone foram descartados da tabela SessionDetails usada no Skype for Business Server 2015.
  
|**Column**|**Tipo de dados**|**Chave/Índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Primário, Estrangeiro  <br/> |Tempo da solicitação de sessão. Usado em conjunto com **SessionIdSeq** para identificar exclusivamente uma sessão. Consulte a [tabela Dialogs no Skype for Business Server 2015](dialogs.md) para obter mais informações. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primário, Estrangeiro  <br/> |O número de ID para identificar a sessão. Usado em conjunto com **SessionIdTime** para identificar exclusivamente uma sessão.* Consulte a tabela Dialogs no Skype for Business Server [2015](dialogs.md) para obter mais informações. <br/> |
|**CorrelationId** <br/> |uniqueidentifier  <br/> ||Um GUID para correlacionar várias sessões.  <br/> |
|**ReplaceDialogIdTime** <br/> |datetime  <br/> |Foreign  <br/> |O número de identificação para identificar a caixa de diálogo que foi substituída pela sessão atual. Consulte a [tabela Dialogs no Skype for Business Server 2015](dialogs.md) para obter mais informações. <br/> |
|**ReplaceDialogIdSeq** <br/> |int  <br/> |Foreign  <br/> |O número de identificação para identificar a sessão. Usado em conjunto com **ReplacesDialogIdTime** para identificar exclusivamente uma sessão que é substituída por esta sessão. Consulte a [tabela Dialogs no Skype for Business Server 2015](dialogs.md) para obter mais informações. <br/> |
|**User1Id** <br/> |int  <br/> |Foreign  <br/> |A ID de um usuário na sessão. Consulte a [tabela Usuários para](users.md) obter mais informações. <br/> |
|**User2Id** <br/> |int  <br/> |Foreign  <br/> |A ID de outro usuário na sessão. Consulte a [tabela Usuários para](users.md) obter mais informações. <br/> |
|**User1EndpointId** <br/> |uniqueIdentifier  <br/> ||GUID que identifica o ponto de extremidade usado pelo primeiro usuário na sessão.  <br/> Este campo foi introduzido no Microsoft Lync Server 2013.  <br/> |
|**User2EndpointId** <br/> |uniqueIdentifier  <br/> ||GUID que identifica o ponto de extremidade usado pelo segundo usuário na sessão.  <br/> Este campo foi introduzido no Microsoft Lync Server 2013.  <br/> |
|**TargetUserId** <br/> |int  <br/> |Foreign  <br/> |A solicitação original Para o URI do usuário no SIP. consulte a [tabela Usuários](users.md) para obter mais informações. <br/> |
|**SessionStartedById** <br/> |int  <br/> |Foreign  <br/> |A ID do usuário que iniciou a sessão. Consulte a [tabela Usuários para](users.md) obter mais informações. <br/> |
|**OnBehalfOfId** <br/> |int  <br/> |Foreign  <br/> |Indica a ID do usuário que está em nome do chamador. Consulte a [tabela Usuários para](users.md) obter mais informações. <br/> |
|**ReferredById** <br/> |int  <br/> |Foreign  <br/> |A ID do usuário a quem se refere a chamada. Consulte a [tabela Usuários para](users.md) obter mais informações. <br/> |
|**ServerId** <br/> |int  <br/> |Foreign  <br/> |A ID do servidor Front-End usado para esta sessão. Consulte a [tabela Servidores para](servers.md) obter mais informações. <br/> |
|**PoolId** <br/> |int  <br/> |Foreign  <br/> |A ID do pool no qual a sessão foi capturada. Consulte a [tabela Pools para](pools.md) obter mais informações. <br/> |
|**ContentTypeID** <br/> |int  <br/> |Foreign  <br/> |Tipo de conteúdo usado na sessão. Consulte a [tabela ContentTypes no Skype for Business Server 2015](contenttypes.md) para obter mais informações. <br/> |
|**User1ClientVerId** <br/> |int  <br/> |Foreign  <br/> |A versão do cliente usada pelo Usuário1. Consulte a [tabela ClientVersions no Skype for Business Server 2015](clientversions.md) para obter mais informações. <br/> |
|**User2ClientVerId** <br/> |int  <br/> |Foreign  <br/> |A versão do cliente usada pelo Usuário2. Consulte a [tabela ClientVersions no Skype for Business Server 2015](clientversions.md) para obter mais informações. <br/> |
|**User1EdgeServerid** <br/> |int  <br/> |Foreign  <br/> |O Servidor de Borda usado pelo Usuário1. Consulte a [tabela EdgeServers no Skype for Business Server 2015](edgeservers.md) para obter mais informações. <br/> |
|**User2EdgeServerid** <br/> |int  <br/> |Foreign  <br/> |O Servidor de Borda usado pelo Usuário2. Consulte a [tabela EdgeServers no Skype for Business Server 2015](edgeservers.md) para obter mais informações. <br/> |
|**IsUser1Internal** <br/> |bit  <br/> ||Se o Usuário1 está conectado internamente ou não.  <br/> |
|**IsUser2Internal** <br/> |bit  <br/> ||Se o Usuário2 está conectado internamente ou não.  <br/> |
|**InviteTime** <br/> |datetime  <br/> ||A hora da primeira solicitação INVITE. Este campo é geralmente preenchido por dados gerados da mensagem INVITE inicial em uma sessão. Caso não exista uma mensagem INVITE então o campo é preenchido com a data e horário da primeira mensagem SIP relevante (BYE, CANCEL, MESSAGE, ou INFO). Este campo é normalmente preenchido pelos dados gerados a partir da mensagem INVITE inicial na sessão. Se não houver mensagem INVITE, então o campo será preenchido com a data e hora da primeira mensagem SIP relevante (BYE, CANCEL, MESSAGE ou INFO).  <br/> |
|**ResponseTime** <br/> |datetime  <br/> ||O tempo de resposta da primeira mensagem INVITE. Este campo é tipicamente preenchido pelos dados gerados pela mensagem INVITE inicial na sessão. Se não houver nenhuma mensagem CONVIDAR, então o campo será preenchido com a data e a hora da primeira mensagem SIP relevante (ATÉ LOGO, CANCELAR, MENSAGEM ou INFO).  <br/> |
|**ResponseCode** <br/> |int  <br/> ||Código de resposta SIP para convite de sessão. Este campo é normalmente preenchido por dados gerados na mensagem CONVIDAR inicial na sessão. Caso não haja nenhuma mensagem CONVIDAR, o campo é preenchidos com a data e horário da primeira mensagem de SIP relevante (ATÉ LOGO, CANCELAR, MENSAGEM ou INFO).  <br/> |
|**DiagnosticId** <br/> |int  <br/> ||ID de diagnóstico capturada do cabeçalho SIP.  <br/> |
|**CallPriority** <br/> |int  <br/> |Foreign  <br/> |Prioridade de chamada. Consulte a [tabela CallPriorities no Skype for Business Server 2015](callpriorities.md) para obter mais informações. <br/> |
|**User1MessageCount** <br/> |int  <br/> ||O número de mensagens enviadas pelo Usuário1 durante a sessão.  <br/> |
|**User2MessageCount** <br/> |int  <br/> ||O número de mensagens enviadas pelo Usuário2 durante a sessão.  <br/> |
|**SessionEndTime** <br/> |datetime  <br/> ||Hora ao final da sessão.  <br/> |
|**MediaTypes** <br/> |int  <br/> ||Um conjunto de bits que indica o tipo de mídia esta sessão. As definições dos tipos estão listadas:  <br/> 1- IM  <br/> 2- FILE_TRANSFER  <br/> 4- REMOTE_ASSISTANCE  <br/> 8- APP_SHARING  <br/> 16- AUDIO  <br/> 32- VÍDEO  <br/> 64- APP_INVITE  <br/> |
|**User1Flag** <br/> |smallint  <br/> ||Um conjunto de bits que indica os atributos do Usuário1. As seguintes definições de atributo são listadas:  <br/> 0x01 - Integrado com telefone da área de trabalho  <br/> |
|**User2Flag** <br/> |smallint  <br/> ||Um conjunto de bits que indica os atributos do Usuário2. As seguintes definições de atributo são listadas:  <br/> 0x01 - Integrado com telefone da área de trabalho  <br/> |
|**CallFlag** <br/> |smallint  <br/> ||Um conjunto de bits que indica os atributos da chamada. As seguintes definições de atributo são listadas:  <br/> 0x01 - Sessão Repetida  <br/> 0x02 - Uma chamada feita pelo operador em nome de um grupo de resposta  <br/> |
|**Processado** <br/> |bit  <br/> ||Para uso interno pelo serviço de Monitoramento.  <br/> Este campo foi introduzido no Microsoft Lync Server 2013.  <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||Para uso interno pelo serviço de Monitoramento.  <br/> Este campo foi introduzido no Skype for Business Server 2015.  <br/> |
   
\* Para a maioria das sessões, SessionIdSeq terá o valor de 1. Se várias sessões iniciam exatamente ao mesmo tempo, o SessionIdSeq para uma delas será 1 e para a outra será 2 e assim por diante.
  

