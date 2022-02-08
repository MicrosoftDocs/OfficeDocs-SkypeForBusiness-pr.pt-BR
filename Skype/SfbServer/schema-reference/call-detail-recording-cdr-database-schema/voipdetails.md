---
title: Exibição VoIPDetails
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 14c44736-71ba-4fc5-82c7-1df65bf6261c
description: O modo de exibição VoIPDetails armazena informações sobre sessões ponto a ponto, onde no mínimo um usuário é um usuário VoIP. Essa exibição foi introduzida no Microsoft Lync Server 2013.
ms.openlocfilehash: 5804f32dfebb2fe8c6844acb0bcd343c5b6ead21
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62385399"
---
# <a name="voipdetails-view"></a>Exibição VoIPDetails
 
O modo de exibição VoIPDetails armazena informações sobre sessões ponto a ponto, onde no mínimo um usuário é um usuário VoIP. Essa exibição foi introduzida no Microsoft Lync Server 2013.
  
> [!NOTE]
> O exibição VoIPDetails contém todas as colunas no [exibição SessionDetails](sessiondetails-0.md) , além das colunas listadas abaixo.
  
|**Coluna**|**Tipo de dados**|**Detalhes**|
|:-----|:-----|:-----|
|**FromPhone** <br/> |nvarchar(450)  <br/> |URI do telefone do usuário que iniciou a sessão.  <br/> |
|**ToPhone** <br/> |nvarchar(450)  <br/> |URI do telefone do usuário que entrou na sessão.  <br/> |
|**DisconnectedByUri** <br/> |nvarchar(450)  <br/> |URI do usuário que desconectou da sessão.  <br/> |
|**DisconnectedByUriType** <br/> |nvarchar(256)  <br/> |Tipo da URI do usuário que desconectou da sessão. Consulte a [tabela UriTypes para](uritypes.md) obter mais informações. <br/> |
|**DisconnectedByTenant** <br/> |nvarchar(256)  <br/> |Locatário do usuário que desconectou da sessão.  <br/> |
|**DisconnectedByPhone** <br/> |nvarchar(450)  <br/> |URI do telefone do usuário que desconectou da sessão.  <br/> |
|**FromMediationServer** <br/> |nvarchar(256)  <br/> |Servidor de Mediação usado pelo usuário que iniciou a sessão.  <br/> |
|**ToMediationServer** <br/> |nvarchar(256)  <br/> |Servidor de Mediação usado pelo usuário que entrou na sessão.  <br/> |
|**FromGateway** <br/> |nvarchar(256)  <br/> |Gateway usado pelo usuário que iniciou a sessão.  <br/> |
|**ToGateway** <br/> |nvarchar(256)  <br/> |Gateway usado pelo usuário que entrou na sessão.  <br/> |
   

