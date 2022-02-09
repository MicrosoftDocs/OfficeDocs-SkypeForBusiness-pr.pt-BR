---
title: Tabela VoipDetails
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
ms.assetid: 74ffbb71-569b-4018-be1f-4db2bbafcf36
description: Cada registro representa uma chamada de dois participantes na qual pelo menos um usuário utiliza VoIP.
ms.openlocfilehash: 4cb3513ae5eb528c5e681cd55b173749c8cf1a02
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62416364"
---
# <a name="voipdetails-table"></a>Tabela VoipDetails
 
Cada registro representa uma chamada de dois participantes na qual pelo menos um usuário utiliza VoIP.
  
|**Coluna**|**Tipo de dados**|**Chave/Índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Primário  <br/> |Tempo da solicitação de sessão. Usado em conjunto com **SessionIdSeq** para identificar exclusivamente uma sessão. Consulte a [tabela Dialogs no Skype for Business Server 2015](dialogs.md) para obter mais informações. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primário  <br/> |O número de ID para identificar a sessão. Usado em conjunto com **SessionIdTime** para identificar exclusivamente uma sessão. Consulte a [tabela Dialogs no Skype for Business Server 2015](dialogs.md) para obter mais informações. <br/> |
|**FromNumberId** <br/> |int  <br/> |Foreign  <br/> |**PhoneId** do chamador. Consulte a [tabela Telefones para](phones.md) obter mais informações. Se não é NULL e **FromGatewayId** não é nulo, o chamador era um usuário PSTN. <br/> |
|**ConnectedNumberId** <br/> |int  <br/> |Foreign  <br/> |**PhoneId** do receptor de chamada. Consulte a [tabela Telefones para](phones.md) obter mais informações. Se não é NULL e **ToGatewayId** não é nulo, o receptor de chamada era um usuário PSTN. <br/> |
|**FromMediationServerId** <br/> |int  <br/> |Foreign  <br/> |O Servidor de Mediação de onde a chamada está vindo. Consulte a tabela [MediationServers para](mediationservers.md) obter mais informações. <br/> |
|**ToMediationServerId** <br/> |int  <br/> |Foreign  <br/> |O Servidor de Mediação para onde vai a chamada. Consulte a tabela [MediationServers para](mediationservers.md) obter mais informações. <br/> |
|**FromGatewayId** <br/> |int  <br/> |Foreign  <br/> |O Gateway de onde a chamada é feita. Consulte a [tabela Gateways no Skype for Business Server 2015](gateways.md) para obter mais informações. <br/> |
|**ToGatewayId** <br/> |int  <br/> |Foreign  <br/> |O Gateway para onde a chamada vai. Consulte a [tabela Gateways no Skype for Business Server 2015](gateways.md) para obter mais informações. <br/> |
|**DisconnectedbyURIId** <br/> |int  <br/> |Foreign  <br/> |URI do usuário que desconectou a chamada, se o usuário tem um URI. Consulte a [tabela Usuários para](users.md) obter mais informações. <br/> |
|**DisconnectedbyPhoneId** <br/> |int  <br/> |Foreign  <br/> |A ID do telefone que desconectou a chamada foi desconectada de um telefone. Consulte a [tabela Telefones para](phones.md) obter mais informações. <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||Para uso interno pelo serviço de Monitoramento.  <br/> Este campo foi introduzido no Skype for Business Server 2015.  <br/> |
   

