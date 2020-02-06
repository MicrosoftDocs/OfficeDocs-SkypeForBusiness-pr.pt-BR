---
title: Modo de exibição conferências
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
ms.assetid: c0e5c4db-c135-401f-9296-e9a49f6499a1
description: O modo de exibição conferências armazena informações sobre as conferências. Este modo de exibição foi apresentado no Microsoft Lync Server 2013.
ms.openlocfilehash: 9f9448769256bfb05e6552a41c2521defa65ded0
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815359"
---
# <a name="conferences-view"></a>Modo de exibição conferências
 
O modo de exibição conferências armazena informações sobre as conferências. Este modo de exibição foi apresentado no Microsoft Lync Server 2013.
  
|**Coluna**|**Tipo de dados**|**Detalhes**|
|:-----|:-----|:-----|
|**Id_da_sessãotime** <br/> |datetime  <br/> |Tempo de solicitação de sessão. Usado em conjunto com o SessionIdSeq para identificar exclusivamente uma sessão. Consulte a [tabela de diálogos no Skype for Business Server 2015](dialogs.md) para obter mais informações. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Número de identificação para identificar a sessão. Usado em conjunto com a Identificação_da_sessãotime para identificar exclusivamente uma sessão. Consulte a [tabela de diálogos no Skype for Business Server 2015](dialogs.md) para obter mais informações. <br/> |
|**ConferenceUri** <br/> |nvarchar (450)  <br/> |URL para a conferência.  <br/> |
|**ConferenceUriType** <br/> |nvarchar(256)  <br/> |Tipo de URL da conferência. Consulte a [tabela UriTypes](uritypes.md) para obter mais informações. <br/> |
|**ConfInstance** <br/> |identificador  <br/> |Usado para conferências recorrentes. Cada instância de uma conferência recorrente tem o mesmo ConferenceUri, mas um ConfInstance diferente.  <br/> |
|**ConferenceStartTime** <br/> |datetime  <br/> |Hora de início da conferência.  <br/> |
|**ConferenceEndTime** <br/> |datetime  <br/> |Hora de término da conferência.  <br/> |
|**OrganizerUri** <br/> |nvarchar (450)  <br/> |URI do usuário que organizou a conferência.  <br/> |
|**OrganizerType** <br/> |nvarchar(256)  <br/> |Tipo de URI do usuário que organizou a conferência. Consulte a [tabela UriTypes](uritypes.md) para obter mais informações. <br/> |
|**OrganizerTenant** <br/> |nvarchar(256)  <br/> |Locatário do usuário que organizou a conferência. Consulte a [tabela locatários](tenants.md) para obter mais informações. <br/> |
|**Pool** <br/> |nvarchar(256)  <br/> |Nome de domínio totalmente qualificado do pool que hospeda a conferência.  <br/> |
|**Sinalizador** <br/> |smallint  <br/> |Máscara de bits que contém atributos de conferência. Os valores possíveis são:  <br/> 0X01-transação sintética  <br/> |
   

