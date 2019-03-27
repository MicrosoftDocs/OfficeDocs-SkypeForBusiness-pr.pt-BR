---
title: Tabela VoipDetails
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 7/15/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 74ffbb71-569b-4018-be1f-4db2bbafcf36
description: Cada registro representa uma chamada de dois participantes na qual pelo menos um usuário é um usuário de VoIP.
ms.openlocfilehash: 304efbd8148c363afaa792abe97d0b15ab5a34fd
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30879669"
---
# <a name="voipdetails-table"></a>Tabela VoipDetails
 
Cada registro representa uma chamada de dois participantes na qual pelo menos um usuário é um usuário de VoIP.
  
|**Coluna**|**Tipo de dados**|**Chave/índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Primária  <br/> |Hora da solicitação de sessão. Usado em conjunto com **SessionIdSeq** para identificar exclusivamente uma sessão. Consulte a [tabela no Skype para Business Server 2015 de diálogos](dialogs.md) para obter mais informações. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primária  <br/> |Número de identificação para identificar a sessão. Usado em conjunto com **SessionIdTime** para identificar exclusivamente uma sessão. Consulte a [tabela no Skype para Business Server 2015 de diálogos](dialogs.md) para obter mais informações. <br/> |
|**FromNumberId** <br/> |int  <br/> |Externa  <br/> |**PhoneId** do chamador. Consulte a [tabela de telefones](phones.md) para obter mais informações. Se não NULL e **FromGatewayId** não for nula, o chamador era um usuário por PSTN. <br/> |
|**ConnectedNumberId** <br/> |int  <br/> |Externa  <br/> |**PhoneId** do receptor da chamada. Consulte a [tabela de telefones](phones.md) para obter mais informações. Se não NULL e **ToGatewayId** não for nula, o receptor da chamada era um usuário por PSTN. <br/> |
|**FromMediationServerId** <br/> |int  <br/> |Externa  <br/> |O servidor de mediação a chamada é proveniente. Consulte a [tabela MediationServers](mediationservers.md) para obter mais informações. <br/> |
|**ToMediationServerId** <br/> |int  <br/> |Externa  <br/> |O servidor de mediação chamado vai. Consulte a [tabela MediationServers](mediationservers.md) para obter mais informações. <br/> |
|**FromGatewayId** <br/> |int  <br/> |Externa  <br/> |Gateway a chamada é proveniente. Consulte a [tabela de Gateways no Skype para Business Server 2015](gateways.md) para obter mais informações. <br/> |
|**ToGatewayId** <br/> |int  <br/> |Externa  <br/> |Gateway a chamada será. Consulte a [tabela de Gateways no Skype para Business Server 2015](gateways.md) para obter mais informações. <br/> |
|**DisconnectedbyURIId** <br/> |int  <br/> |Externa  <br/> |URI do usuário que desconectou a chamada, se o usuário possui um URI. Consulte a [tabela de usuários](users.md) para obter mais informações. <br/> |
|**DisconnectedbyPhoneId** <br/> |int  <br/> |Externa  <br/> |ID do telefone que desconectou a chamada foi desconectada de um telefone. Consulte a [tabela de telefones](phones.md) para obter mais informações. <br/> |
|**LastModifiedTime** <br/> |DateTime  <br/> ||Para uso interno pelo serviço de monitoramento.  <br/> Este campo foi introduzido no Skype para Business Server 2015.  <br/> |
   

