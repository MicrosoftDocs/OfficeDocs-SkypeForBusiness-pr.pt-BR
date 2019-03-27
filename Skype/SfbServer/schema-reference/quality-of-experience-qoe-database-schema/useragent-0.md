---
title: Exibir UserAgent
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b986f76f-f16e-4e5e-96cb-6e8f7f9b42ee
description: O modo de exibição UserAgent armazena informações sobre os agentes de usuário que participaram de sessões que têm registros no banco de dados. Este modo de exibição foi introduzido no Microsoft Lync Server 2013.
ms.openlocfilehash: c63873f219f5d741925339f52f949be55fc64411
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30875001"
---
# <a name="useragent-view"></a>Exibir UserAgent
 
O modo de exibição UserAgent armazena informações sobre os agentes de usuário que participaram de sessões que têm registros no banco de dados. Este modo de exibição foi introduzido no Microsoft Lync Server 2013.
  
|**Coluna**|**Tipo de dados**|**Detalhes**|
|:-----|:-----|:-----|
|UserAgentKey  <br/> |int  <br/> |Número exclusivo que identifica esse agente de usuário.  <br/> |
|UserAgent  <br/> |nvarchar(256)  <br/> |Cadeia de caracteres de agente do usuário.  <br/> |
|UAType  <br/> |smallint  <br/> |Tipo de agente de usuário. Consulte a [tabela UserAgent](useragent.md) para obter mais detalhes. <br/> |
|UACategory  <br/> |nvarchar(64)  <br/> |Categoria à qual pertence o agente do usuário. Por exemplo, o agente do usuário Conferencing_Attendant_1.0 pertence o CAA UACategory.  <br/> |
   

