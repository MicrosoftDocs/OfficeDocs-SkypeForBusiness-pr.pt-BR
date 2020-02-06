---
title: Tabela VoipDetails
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 74ffbb71-569b-4018-be1f-4db2bbafcf36
description: Cada registro representa uma chamada de 1 2 a terceiros na qual pelo menos um usuário é um usuário de VoIP.
ms.openlocfilehash: 65bf3b4d7a815434b21b761030a7ac514d9bd803
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814779"
---
# <a name="voipdetails-table"></a>Tabela VoipDetails
 
Cada registro representa uma chamada de 1 2 a terceiros na qual pelo menos um usuário é um usuário de VoIP.
  
|**Coluna**|**Tipo de dados**|**Chave/índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**Id_da_sessãotime** <br/> |datetime  <br/> |Primária  <br/> |Tempo de solicitação de sessão. Usado em conjunto com o **SessionIdSeq** para identificar exclusivamente uma sessão. Consulte a [tabela de diálogos no Skype for Business Server 2015](dialogs.md) para obter mais informações. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primária  <br/> |Número de identificação para identificar a sessão. Usado em conjunto com a **identificação_da_sessãotime** para identificar exclusivamente uma sessão. Consulte a [tabela de diálogos no Skype for Business Server 2015](dialogs.md) para obter mais informações. <br/> |
|**FromNumberId** <br/> |int  <br/> |Exterior  <br/> |Identificação de **telefone** do chamador. Consulte a [tabela de telefones](phones.md) para obter mais informações. Se não for nulo e **FromGatewayId** não for nulo, o chamador será um usuário PSTN. <br/> |
|**ConnectedNumberId** <br/> |int  <br/> |Exterior  <br/> |**Número de telefoneid** do receptor da chamada. Consulte a [tabela de telefones](phones.md) para obter mais informações. Se não for nulo e **Togatewayid** não for nulo, o receptor da chamada será um usuário PSTN. <br/> |
|**FromMediationServerId** <br/> |int  <br/> |Exterior  <br/> |O servidor de mediação do qual a chamada está vindo. Consulte a [tabela MediationServers](mediationservers.md) para obter mais informações. <br/> |
|**ToMediationServerId** <br/> |int  <br/> |Exterior  <br/> |O servidor de mediação chamado está indo para. Consulte a [tabela MediationServers](mediationservers.md) para obter mais informações. <br/> |
|**FromGatewayId** <br/> |int  <br/> |Exterior  <br/> |Gateway do qual a chamada está vindo. Consulte a [tabela gateways no Skype for Business Server 2015](gateways.md) para obter mais informações. <br/> |
|**Togatewayid** <br/> |int  <br/> |Exterior  <br/> |Gateway em que a chamada vai. Consulte a [tabela gateways no Skype for Business Server 2015](gateways.md) para obter mais informações. <br/> |
|**DisconnectedbyURIId** <br/> |int  <br/> |Exterior  <br/> |URI do usuário que desconectou a chamada, se o usuário tiver um URI. Para obter mais informações, consulte a [tabela usuários](users.md) . <br/> |
|**DisconnectedbyPhoneId** <br/> |int  <br/> |Exterior  <br/> |ID do telefone que desconectou a chamada foi desconectado de um telefone. Consulte a [tabela de telefones](phones.md) para obter mais informações. <br/> |
|**LastModifiedtime** <br/> |DateTime  <br/> ||Para uso interno pelo serviço de monitoramento.  <br/> Este campo foi apresentado no Skype for Business Server 2015.  <br/> |
   

