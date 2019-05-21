---
title: Tabela SessionDetails
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 783d2508-e31f-4b54-be0c-63aa5ec21c04
description: Cada registro representa uma sessão ponto a ponto, que pode ser uma chamada telefônica VoIP-VoIP, uma sessão de IM de duas partes ou outro tipo de sessão. Você pode executar uma junção de tabela com a tabela de mídia para encontrar os detalhes de cada mídia envolvida nesta sessão.
ms.openlocfilehash: d6c0d68cf5b8efd83cc764e74a56621cdd591ac1
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295801"
---
# <a name="sessiondetails-table"></a>Tabela SessionDetails
 
Cada registro representa uma sessão ponto a ponto, que pode ser uma chamada telefônica VoIP-VoIP, uma sessão de IM de duas partes ou outro tipo de sessão. Você pode executar uma junção de tabela com a [tabela de mídia](media.md) para encontrar os detalhes de cada mídia envolvida nesta sessão.
  
Observe que os campos IsUser1IntegratedWithDeskPhone e IsUser2IntegratedWithDeskPhone foram descartados da tabela SessionDetails usada no Skype for Business Server 2015.
  
|**Coluna**|**Tipo de dados**|**Chave/índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**Id_da_sessãotime** <br/> |datetime  <br/> |Primário, estrangeiro  <br/> |Tempo de solicitação de sessão. Usado em conjunto com o **SessionIdSeq** para identificar exclusivamente uma sessão. Consulte a [tabela de diálogos no Skype for Business Server 2015](dialogs.md) para obter mais informações. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primário, estrangeiro  <br/> |Número de identificação para identificar a sessão. Usado em conjunto com **** a identificação_da_sessãotime para identificar exclusivamente uma sessão. * consulte a [tabela de caixas de diálogo no Skype for Business Server 2015](dialogs.md) para obter mais informações. <br/> |
|**CorrelationId** <br/> |identificador  <br/> ||Um GUID para correlacionar várias sessões.  <br/> |
|**ReplaceDialogIdTime** <br/> |datetime  <br/> |Exterior  <br/> |Número de identificação para identificar a caixa de diálogo que foi substituída pela sessão atual. Consulte a [tabela de diálogos no Skype for Business Server 2015](dialogs.md) para obter mais informações. <br/> |
|**ReplaceDialogIdSeq** <br/> |int  <br/> |Exterior  <br/> |Número de identificação para identificar a sessão. Usado em conjunto com **ReplacesDialogIdTime** para identificar exclusivamente uma sessão substituída por esta sessão. Consulte a [tabela de diálogos no Skype for Business Server 2015](dialogs.md) para obter mais informações. <br/> |
|**Usuário1id** <br/> |int  <br/> |Exterior  <br/> |ID de um usuário na sessão. Para obter mais informações, consulte a [tabela usuários](users.md) . <br/> |
|**User2Id** <br/> |int  <br/> |Exterior  <br/> |ID do outro usuário na sessão. Para obter mais informações, consulte a [tabela usuários](users.md) . <br/> |
|**User1EndpointId** <br/> |Identificador  <br/> ||GUID que identifica o ponto de extremidade usado pelo primeiro usuário na sessão.  <br/> Este campo foi apresentado no Microsoft Lync Server 2013.  <br/> |
|**User2EndpointId** <br/> |Identificador  <br/> ||GUID que identifica o ponto de extremidade usado pelo segundo usuário na sessão.  <br/> Este campo foi apresentado no Microsoft Lync Server 2013.  <br/> |
|**TargetUserId** <br/> |int  <br/> |Exterior  <br/> |O URI do usuário original na solicitação SIP. para obter mais informações, consulte a [tabela usuários](users.md) . <br/> |
|**SessionStartedById** <br/> |int  <br/> |Exterior  <br/> |ID do usuário que iniciou a sessão. Para obter mais informações, consulte a [tabela usuários](users.md) . <br/> |
|**OnBehalfOfId** <br/> |int  <br/> |Exterior  <br/> |Indica a ID do usuário de quem o chamador está em nome. Para obter mais informações, consulte a [tabela usuários](users.md) . <br/> |
|**ReferredById** <br/> |int  <br/> |Exterior  <br/> |ID do usuário por quem a chamada é referida. Para obter mais informações, consulte a [tabela usuários](users.md) . <br/> |
|**ServerID** <br/> |int  <br/> |Exterior  <br/> |ID do servidor front-end usado para esta sessão. Consulte a [tabela servidores](servers.md) para obter mais informações. <br/> |
|**Poolid** <br/> |int  <br/> |Exterior  <br/> |ID do pool no qual a sessão foi capturada. Consulte a [tabela de grupos](pools.md) para obter mais informações. <br/> |
|**ContentTypeid** <br/> |int  <br/> |Exterior  <br/> |Tipo de conteúdo usado na sessão. Consulte a [tabela ContentTypes no Skype for Business Server 2015](contenttypes.md) para obter mais informações. <br/> |
|**User1ClientVerId** <br/> |int  <br/> |Exterior  <br/> |Versão do cliente usada pelo Usuário1. Consulte a [tabela ClientVersions no Skype for Business Server 2015](clientversions.md) para obter mais informações. <br/> |
|**User2ClientVerId** <br/> |int  <br/> |Exterior  <br/> |Versão do cliente usada pelo user2. Consulte a [tabela ClientVersions no Skype for Business Server 2015](clientversions.md) para obter mais informações. <br/> |
|**User1EdgeServerid** <br/> |int  <br/> |Exterior  <br/> |Servidor de borda usado pelo Usuário1. Consulte a [tabela EdgeServers no Skype for Business Server 2015](edgeservers.md) para obter mais informações. <br/> |
|**User2EdgeServerid** <br/> |int  <br/> |Exterior  <br/> |Servidor de borda usado pelo user2. Consulte a [tabela EdgeServers no Skype for Business Server 2015](edgeservers.md) para obter mais informações. <br/> |
|**IsUser1Internal** <br/> |bit  <br/> ||Se user1 está conectado de Internal ou not.  <br/> |
|**IsUser2Internal** <br/> |bit  <br/> ||Se o User2 está conectado do Internal ou não.  <br/> |
|**Invitetime** <br/> |datetime  <br/> ||A hora da primeira solicitação INVITE. Geralmente, esse campo é preenchido por dados gerados da mensagem de convite inicial na sessão. Se não houver nenhuma mensagem de convite, o campo será preenchido com a data e a hora da primeira mensagem SIP relevante (até mais, cancelamento, mensagem ou informações). Geralmente, esse campo é preenchido por dados gerados da mensagem de convite inicial na sessão. Se não houver nenhuma mensagem de convite, o campo será preenchido com a data e a hora da primeira mensagem SIP relevante (até mais, cancelamento, mensagem ou informações).  <br/> |
|**ResponseTime** <br/> |datetime  <br/> ||A hora da resposta para a primeira mensagem de convite. Geralmente, esse campo é preenchido por dados gerados da mensagem de convite inicial na sessão. Se não houver nenhuma mensagem de convite, o campo será preenchido com a data e a hora da primeira mensagem SIP relevante (até mais, cancelamento, mensagem ou informações).  <br/> |
|**ResponseCode** <br/> |int  <br/> ||Código de resposta SIP para o convite da sessão. Geralmente, esse campo é preenchido por dados gerados da mensagem de convite inicial na sessão. Se não houver nenhuma mensagem de convite, o campo será preenchido com a data e a hora da primeira mensagem SIP relevante (até mais, cancelamento, mensagem ou informações).  <br/> |
|**Diagnosticid** <br/> |int  <br/> ||ID de diagnóstico capturada do cabeçalho SIP.  <br/> |
|**CallPriority** <br/> |int  <br/> |Exterior  <br/> |Prioridade da chamada. Consulte a [tabela CallPriorities no Skype for Business Server 2015](callpriorities.md) para obter mais informações. <br/> |
|**User1MessageCount** <br/> |int  <br/> ||Número de mensagens enviadas pelo Usuário1 durante a sessão.  <br/> |
|**User2MessageCount** <br/> |int  <br/> ||Número de mensagens enviadas pelo user2 durante a sessão.  <br/> |
|**SessionEndTime** <br/> |datetime  <br/> ||Hora no final da sessão.  <br/> |
|**MediaTypes** <br/> |int  <br/> ||Um conjunto de bits que indica o tipo de mídia desta sessão. Listadas são as definições dos tipos:  <br/> 1-MENSAGENS INSTANTÂNEAS  <br/> 2-FILE_TRANSFER  <br/> 4-REMOTE_ASSISTANCE  <br/> 8-APP_SHARING  <br/> 16-ÁUDIO  <br/> 32-VÍDEO  <br/> 64-APP_INVITE  <br/> |
|**User1Flag** <br/> |smallint  <br/> ||Um conjunto de bits que indica os atributos Usuário1. As definições de atributo a seguir estão listadas:  <br/> 0x01-integrado ao telefone desktop  <br/> |
|**User2Flag** <br/> |smallint  <br/> ||Um conjunto de bits que indica os atributos do user2. As definições de atributo a seguir estão listadas:  <br/> 0x01-integrado ao telefone desktop  <br/> |
|**CallFlag** <br/> |smallint  <br/> ||Um conjunto de bits que indica os atributos da chamada. As definições de atributo a seguir estão listadas:  <br/> 0x01-sessão repetida  <br/> 0x02-uma chamada feita pelo agente em nome de um grupo de resposta  <br/> |
|**Processe** <br/> |bit  <br/> ||Para uso interno pelo serviço de monitoramento.  <br/> Este campo foi apresentado no Microsoft Lync Server 2013.  <br/> |
|**LastModifiedtime** <br/> |DateTime  <br/> ||Para uso interno pelo serviço de monitoramento.  <br/> Este campo foi apresentado no Skype for Business Server 2015.  <br/> |
   
\*Para a maioria das sessões, o SessionIdSeq terá o valor de 1. Se várias sessões começarem exatamente ao mesmo tempo, o SessionIdSeq de uma será 1, por outro será 2, e assim por diante.
  

