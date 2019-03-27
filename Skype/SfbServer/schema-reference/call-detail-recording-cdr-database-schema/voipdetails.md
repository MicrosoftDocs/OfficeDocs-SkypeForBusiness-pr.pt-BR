---
title: Exibir VoIPDetails
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 14c44736-71ba-4fc5-82c7-1df65bf6261c
description: O modo de exibição VoIPDetails armazena informações sobre sessões ponto a ponto, onde pelo menos um usuário é um usuário de VoIP. Este modo de exibição foi introduzido no Microsoft Lync Server 2013.
ms.openlocfilehash: 940c3874d5ce8eb8a4d2261de56b8988b6d3a4c9
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30875550"
---
# <a name="voipdetails-view"></a>Exibir VoIPDetails
 
O modo de exibição VoIPDetails armazena informações sobre sessões ponto a ponto, onde pelo menos um usuário é um usuário de VoIP. Este modo de exibição foi introduzido no Microsoft Lync Server 2013.
  
> [!NOTE]
> O modo de exibição VoIPDetails contém todas as colunas no [SessionDetails view](sessiondetails-0.md) além das colunas listadas abaixo.
  
|**Coluna**|**Tipo de dados**|**Detalhes**|
|:-----|:-----|:-----|
|**FromPhone** <br/> |nvarchar(450)  <br/> |URI do telefone do usuário que iniciou a sessão.  <br/> |
|**ToPhone** <br/> |nvarchar(450)  <br/> |URI do telefone do usuário que ingressou na sessão.  <br/> |
|**DisconnectedByUri** <br/> |nvarchar(450)  <br/> |URI do usuário que desconectou da sessão.  <br/> |
|**DisconnectedByUriType** <br/> |nvarchar(256)  <br/> |Tipo de URI do usuário que desconectou da sessão. Consulte a [tabela UriTypes](uritypes.md) para obter mais informações. <br/> |
|**DisconnectedByTenant** <br/> |nvarchar(256)  <br/> |Locatário do usuário que desconectou da sessão.  <br/> |
|**DisconnectedByPhone** <br/> |nvarchar(450)  <br/> |URI do usuário que desconectou da sessão do telefone.  <br/> |
|**FromMediationServer** <br/> |nvarchar(256)  <br/> |Servidor de mediação usado pelo usuário que iniciou a sessão.  <br/> |
|**ToMediationServer** <br/> |nvarchar(256)  <br/> |Servidor de mediação usado pelo usuário que ingressou na sessão.  <br/> |
|**FromGateway** <br/> |nvarchar(256)  <br/> |Gateway usado pelo usuário que iniciou a sessão.  <br/> |
|**ToGateway** <br/> |nvarchar(256)  <br/> |Gateway usado pelo usuário que ingressou na sessão.  <br/> |
   

