---
title: Exibição UserAgent
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
ms.assetid: b986f76f-f16e-4e5e-96cb-6e8f7f9b42ee
description: A Exibição UserAgent armazena informações sobre os agentes do usuário que foram envolvidos em sessões com registros no banco de dados. Essa exibição foi introduzida no Microsoft Lync Server 2013.
ms.openlocfilehash: 22dcd5e127e123e027448ccddaa79007cfdbfe8d
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62420814"
---
# <a name="useragent-view"></a>Exibição UserAgent
 
A Exibição UserAgent armazena informações sobre os agentes do usuário que foram envolvidos em sessões com registros no banco de dados. Essa exibição foi introduzida no Microsoft Lync Server 2013.
  
|**Coluna**|**Tipo de dados**|**Detalhes**|
|:-----|:-----|:-----|
|UserAgentKey  <br/> |int  <br/> |Número exclusivo que identifica esse agente do usuário.  <br/> |
|UserAgent  <br/> |nvarchar(256)  <br/> |Cadeia de caracteres de agente do usuário.  <br/> |
|UAType  <br/> |smallint  <br/> |Tipo de agente do usuário. Consulte a [tabela UserAgent para](useragent.md) obter mais detalhes. <br/> |
|UACategory  <br/> |nvarchar(64)  <br/> |Categoria que o agente do usuário pertence. Por exemplo, o agente do usuário Conferencing_Attendant_1.0 pertence à UACategory CAA.  <br/> |
   

