---
title: Exibição VoIPDetails
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
ms.openlocfilehash: 84f167fc3f4de45142d3bad80acf0fc9803b40db
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58593375"
---
# <a name="voipdetails-view"></a>Exibição VoIPDetails
 
O modo de exibição VoIPDetails armazena informações sobre sessões ponto a ponto, onde no mínimo um usuário é um usuário VoIP. Essa exibição foi introduzida no Microsoft Lync Server 2013.
  
> [!NOTE]
> O exibição VoIPDetails contém todas as colunas no [exibição SessionDetails,](sessiondetails-0.md) além das colunas listadas abaixo.
  
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
   

