---
title: Tabela SessionDetails
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 783d2508-e31f-4b54-be0c-63aa5ec21c04
description: Cada registro representa uma sessão de ponto a ponto, o que poderia ser um telefonema VoIP-VoIP, sessão de mensagens Instantâneas de dois participantes ou outro tipo de sessão. Você pode executar uma junção de tabelas com a tabela de mídia para encontrar os detalhes de cada mídia envolvidos nesta sessão.
ms.openlocfilehash: bd4603811dd699bfe856f7151841c5f8021c2703
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33888041"
---
# <a name="sessiondetails-table"></a>Tabela SessionDetails
 
Cada registro representa uma sessão de ponto a ponto, o que poderia ser um telefonema VoIP-VoIP, sessão de mensagens Instantâneas de dois participantes ou outro tipo de sessão. Você pode executar uma junção de tabelas com a [tabela de mídia](media.md) para encontrar os detalhes de cada mídia envolvidos nesta sessão.
  
Observe que o IsUser1IntegratedWithDeskPhone e os campos de IsUser2IntegratedWithDeskPhone foram retirados da tabela SessionDetails usada no Skype para Business Server 2015.
  
|**Coluna**|**Tipo de dados**|**Chave/índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Primária, estrangeira  <br/> |Hora da solicitação de sessão. Usado em conjunto com **SessionIdSeq** para identificar exclusivamente uma sessão. Consulte a [tabela no Skype para Business Server 2015 de diálogos](dialogs.md) para obter mais informações. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primária, estrangeira  <br/> |Número de identificação para identificar a sessão. Usado em conjunto com **SessionIdTime** para identificar exclusivamente um session.*, consulte a [tabela no Skype para Business Server 2015 de diálogos](dialogs.md) para obter mais informações. <br/> |
|**CorrelationId** <br/> |Identificador exclusivo  <br/> ||Um GUID para correlacionar múltiplas sessões.  <br/> |
|**ReplaceDialogIdTime** <br/> |datetime  <br/> |Externa  <br/> |Número de identificação para identificar a caixa de diálogo que foi substituída pela sessão atual. Consulte a [tabela no Skype para Business Server 2015 de diálogos](dialogs.md) para obter mais informações. <br/> |
|**ReplaceDialogIdSeq** <br/> |int  <br/> |Externa  <br/> |Número de identificação para identificar a sessão. Usado em conjunto com **ReplacesDialogIdTime** para identificar exclusivamente uma sessão que foi substituída por esta sessão. Consulte a [tabela no Skype para Business Server 2015 de diálogos](dialogs.md) para obter mais informações. <br/> |
|**User1Id** <br/> |int  <br/> |Externa  <br/> |ID de um usuário na sessão. Consulte a [tabela de usuários](users.md) para obter mais informações. <br/> |
|**User2Id** <br/> |int  <br/> |Externa  <br/> |ID do usuário na sessão. Consulte a [tabela de usuários](users.md) para obter mais informações. <br/> |
|**User1EndpointId** <br/> |Identificador exclusivo  <br/> ||GUID que identifica o ponto de extremidade usado pelo primeiro usuário na sessão.  <br/> Este campo foi introduzido no Microsoft Lync Server 2013.  <br/> |
|**User2EndpointId** <br/> |Identificador exclusivo  <br/> ||GUID que identifica o ponto de extremidade usado pelo segundo usuário na sessão.  <br/> Este campo foi introduzido no Microsoft Lync Server 2013.  <br/> |
|**TargetUserId** <br/> |int  <br/> |Externa  <br/> |URI do usuário na solicitação SIP original. Consulte a [tabela de usuários](users.md) para obter mais informações. <br/> |
|**SessionStartedById** <br/> |int  <br/> |Externa  <br/> |ID do usuário que iniciou a sessão. Consulte a [tabela de usuários](users.md) para obter mais informações. <br/> |
|**OnBehalfOfId** <br/> |int  <br/> |Externa  <br/> |Indica a identificação do usuário do que o chamador está em nome. Consulte a [tabela de usuários](users.md) para obter mais informações. <br/> |
|**ReferredById** <br/> |int  <br/> |Externa  <br/> |ID do usuário por que a chamada é conhecida. Consulte a [tabela de usuários](users.md) para obter mais informações. <br/> |
|**ServerId** <br/> |int  <br/> |Externa  <br/> |ID do servidor de front-end usado nesta sessão. Consulte a [tabela de servidores](servers.md) para obter mais informações. <br/> |
|**PoolId** <br/> |int  <br/> |Externa  <br/> |ID do pool no qual a sessão foi capturada. Consulte a [tabela de Pools](pools.md) para obter mais informações. <br/> |
|**ContentTypeID** <br/> |int  <br/> |Externa  <br/> |Tipo de conteúdo usado na sessão. Consulte a [tabela ContentTypes Skype para Business Server 2015](contenttypes.md) para obter mais informações. <br/> |
|**User1ClientVerId** <br/> |int  <br/> |Externa  <br/> |Versão do cliente usado pelo Usuário1. Consulte a [tabela ClientVersions Skype para Business Server 2015](clientversions.md) para obter mais informações. <br/> |
|**User2ClientVerId** <br/> |int  <br/> |Externa  <br/> |Versão do cliente usado pelo Usuário2. Consulte a [tabela ClientVersions Skype para Business Server 2015](clientversions.md) para obter mais informações. <br/> |
|**User1EdgeServerid** <br/> |int  <br/> |Externa  <br/> |Servidor de borda usado pelo Usuário1. Consulte a [tabela EdgeServers no Skype para Business Server 2015](edgeservers.md) para obter mais informações. <br/> |
|**User2EdgeServerid** <br/> |int  <br/> |Externa  <br/> |Servidor de borda usado pelo Usuário2. Consulte a [tabela EdgeServers no Skype para Business Server 2015](edgeservers.md) para obter mais informações. <br/> |
|**IsUser1Internal** <br/> |bit  <br/> ||Se o Usuário1 está conectado internamente ou não.  <br/> |
|**IsUser2Internal** <br/> |bit  <br/> ||Se o Usuário2 está conectado internamente ou não.  <br/> |
|**InviteTime** <br/> |datetime  <br/> ||A hora da primeira solicitação INVITE. Normalmente, este campo é preenchido pelos dados gerados a partir da mensagem de convite inicial da sessão. Se não houver nenhuma mensagem CONVIDAR o campo é preenchido com a data e hora da primeira relevante mensagem SIP (BYE, cancelar, mensagem ou INFO). Normalmente, este campo é preenchido pelos dados gerados a partir da mensagem de convite inicial da sessão. Se não houver nenhuma mensagem CONVIDAR o campo é preenchido com a data e hora da primeira relevante mensagem SIP (BYE, cancelar, mensagem ou INFO).  <br/> |
|**ResponseTime** <br/> |datetime  <br/> ||A hora da resposta à mensagem INVITE primeira. Normalmente, este campo é preenchido pelos dados gerados a partir da mensagem de convite inicial da sessão. Se não houver nenhuma mensagem CONVIDAR o campo é preenchido com a data e hora da primeira relevante mensagem SIP (BYE, cancelar, mensagem ou INFO).  <br/> |
|**ResponseCode** <br/> |int  <br/> ||Código de resposta SIP para o convite de sessão. Normalmente, este campo é preenchido pelos dados gerados a partir da mensagem de convite inicial da sessão. Se não houver nenhuma mensagem CONVIDAR o campo é preenchido com a data e hora da primeira relevante mensagem SIP (BYE, cancelar, mensagem ou INFO).  <br/> |
|**DiagnosticId** <br/> |int  <br/> ||ID de diagnóstico capturado do cabeçalho SIP.  <br/> |
|**CallPriority** <br/> |int  <br/> |Externa  <br/> |Prioridade de chamada. Consulte a [tabela CallPriorities do Skype para Business Server 2015](callpriorities.md) para obter mais informações. <br/> |
|**User1MessageCount** <br/> |int  <br/> ||Número de mensagens enviadas pelo Usuário1 durante a sessão.  <br/> |
|**User2MessageCount** <br/> |int  <br/> ||Número de mensagens enviadas pelo Usuário2 durante a sessão.  <br/> |
|**SessionEndTime** <br/> |datetime  <br/> ||Hora ao final da sessão.  <br/> |
|**MediaTypes** <br/> |int  <br/> ||Um conjunto de bits que indica o tipo de mídia dessa sessão. As definições dos tipos estão listados:  <br/> 1 - MENSAGENS INSTANTÂNEAS  <br/> 2 - FILE_TRANSFER  <br/> 4 - REMOTE_ASSISTANCE  <br/> 8 - APP_SHARING  <br/> 16 - ÁUDIO  <br/> 32 - VÍDEO  <br/> 64 - APP_INVITE  <br/> |
|**User1Flag** <br/> |smallint  <br/> ||Um conjunto de bits que indica os atributos de User1. As seguintes definições de atributo são listadas:  <br/> 0x01 - integrado com telefone de mesa  <br/> |
|**User2Flag** <br/> |smallint  <br/> ||Um conjunto de bits que indica os atributos de Usuário2. As seguintes definições de atributo são listadas:  <br/> 0x01 - integrado com telefone de mesa  <br/> |
|**CallFlag** <br/> |smallint  <br/> ||Um conjunto de bits que indica os atributos de chamada. As seguintes definições de atributo são listadas:  <br/> 0x01 - sessão repetida  <br/> 0x02 - uma chamada feita pelo operador em nome de um grupo de resposta  <br/> |
|**Processadas** <br/> |bit  <br/> ||Para uso interno pelo serviço de monitoramento.  <br/> Este campo foi introduzido no Microsoft Lync Server 2013.  <br/> |
|**LastModifiedTime** <br/> |DateTime  <br/> ||Para uso interno pelo serviço de monitoramento.  <br/> Este campo foi introduzido no Skype para Business Server 2015.  <br/> |
   
\*Para a maioria das sessões, SessionIdSeq terá o valor de 1. Se várias sessões iniciar exatamente simultaneamente, o SessionIdSeq para um será 1, para outro será 2 e assim por diante.
  

