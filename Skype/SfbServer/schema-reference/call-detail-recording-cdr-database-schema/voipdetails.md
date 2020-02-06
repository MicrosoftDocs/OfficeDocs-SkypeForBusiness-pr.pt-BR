---
title: Exibição VoIPDetails
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 14c44736-71ba-4fc5-82c7-1df65bf6261c
description: A exibição VoIPDetails armazena informações sobre sessões ponto a ponto, onde pelo menos um usuário é um usuário de VoIP. Este modo de exibição foi apresentado no Microsoft Lync Server 2013.
ms.openlocfilehash: 4d3aec4c58c2cb11f21ec6403f7532bcde46b05e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814769"
---
# <a name="voipdetails-view"></a>Exibição VoIPDetails
 
A exibição VoIPDetails armazena informações sobre sessões ponto a ponto, onde pelo menos um usuário é um usuário de VoIP. Este modo de exibição foi apresentado no Microsoft Lync Server 2013.
  
> [!NOTE]
> A exibição VoIPDetails contém todas as colunas na [exibição SessionDetails](sessiondetails-0.md) , além das colunas listadas abaixo.
  
|**Coluna**|**Tipo de dados**|**Detalhes**|
|:-----|:-----|:-----|
|**FromPhone** <br/> |nvarchar (450)  <br/> |URI do telefone do usuário que iniciou a sessão.  <br/> |
|**Por telefone** <br/> |nvarchar (450)  <br/> |URI do telefone do usuário que ingressou na sessão.  <br/> |
|**DisconnectedByUri** <br/> |nvarchar (450)  <br/> |URL do usuário que desconectou a sessão.  <br/> |
|**DisconnectedByUriType** <br/> |nvarchar(256)  <br/> |Tipo de URI do usuário que desconectou a sessão. Consulte a [tabela UriTypes](uritypes.md) para obter mais informações. <br/> |
|**DisconnectedByTenant** <br/> |nvarchar(256)  <br/> |Locatário do usuário que desconectou a sessão.  <br/> |
|**DisconnectedByPhone** <br/> |nvarchar (450)  <br/> |URI do telefone do usuário que desconectou a sessão.  <br/> |
|**FromMediationServer** <br/> |nvarchar(256)  <br/> |Servidor de mediação usado pelo usuário que iniciou a sessão.  <br/> |
|**ToMediationServer** <br/> |nvarchar(256)  <br/> |Servidor de mediação usado pelo usuário que ingressou na sessão.  <br/> |
|**FromGateway** <br/> |nvarchar(256)  <br/> |O gateway usado pelo usuário que iniciou a sessão.  <br/> |
|**Togateway** <br/> |nvarchar(256)  <br/> |O gateway usado pelo usuário que ingressou na sessão.  <br/> |
   

