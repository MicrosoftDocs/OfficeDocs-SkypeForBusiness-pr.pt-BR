---
title: Exibição VoIPDetails
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
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
ms.openlocfilehash: 666959270167c5d1322cacef4acbbeb1a0d22dc9
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60833255"
---
# <a name="voipdetails-view"></a>Exibição VoIPDetails
 
O modo de exibição VoIPDetails armazena informações sobre sessões ponto a ponto, onde no mínimo um usuário é um usuário VoIP. Essa exibição foi introduzida no Microsoft Lync Server 2013.
  
> [!NOTE]
> O exibição VoIPDetails contém todas as colunas no [exibição SessionDetails,](sessiondetails-0.md) além das colunas listadas abaixo.
  
|**Column**|**Tipo de dados**|**Detalhes**|
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
   

