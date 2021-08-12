---
title: Exibição UserAgent
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
localization_priority: Normal
ms.assetid: b986f76f-f16e-4e5e-96cb-6e8f7f9b42ee
description: A Exibição UserAgent armazena informações sobre os agentes do usuário que foram envolvidos em sessões com registros no banco de dados. Essa exibição foi introduzida no Microsoft Lync Server 2013.
ms.openlocfilehash: d6ed446c429c3e055d3b5387f4675eaed7fb1f9e992d7211346309254549b66d
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54282983"
---
# <a name="useragent-view"></a>Exibição UserAgent
 
A Exibição UserAgent armazena informações sobre os agentes do usuário que foram envolvidos em sessões com registros no banco de dados. Essa exibição foi introduzida no Microsoft Lync Server 2013.
  
|**Coluna**|**Tipo de dados**|**Detalhes**|
|:-----|:-----|:-----|
|UserAgentKey  <br/> |int  <br/> |Número exclusivo que identifica esse agente do usuário.  <br/> |
|UserAgent  <br/> |nvarchar(256)  <br/> |Cadeia de caracteres de agente do usuário.  <br/> |
|UAType  <br/> |smallint  <br/> |Tipo de agente do usuário. Consulte a [tabela UserAgent para](useragent.md) obter mais detalhes. <br/> |
|UACategory  <br/> |nvarchar(64)  <br/> |Categoria que o agente do usuário pertence. Por exemplo, o agente do usuário Conferencing_Attendant_1.0 pertence à UACategory CAA.  <br/> |
   

