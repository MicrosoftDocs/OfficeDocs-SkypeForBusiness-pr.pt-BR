---
title: Exibição do UserAgent
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b986f76f-f16e-4e5e-96cb-6e8f7f9b42ee
description: A exibição do UserAgent armazena informações sobre os agentes de usuário envolvidos em sessões que têm registros no banco de dados. Este modo de exibição foi apresentado no Microsoft Lync Server 2013.
ms.openlocfilehash: 874a9c986ec77c3e19b557cd65dcf6dbeb045752
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294604"
---
# <a name="useragent-view"></a>Exibição do UserAgent
 
A exibição do UserAgent armazena informações sobre os agentes de usuário envolvidos em sessões que têm registros no banco de dados. Este modo de exibição foi apresentado no Microsoft Lync Server 2013.
  
|**Coluna**|**Tipo de dados**|**Detalhes**|
|:-----|:-----|:-----|
|UserAgentKey  <br/> |int  <br/> |Número exclusivo que identifica esse agente de usuário.  <br/> |
|UserAgent  <br/> |nvarchar(256)  <br/> |Cadeia de caracteres do agente do usuário.  <br/> |
|UAType  <br/> |smallint  <br/> |Tipo de agente do usuário. Consulte a [tabela UserAgent](useragent.md) para obter mais detalhes. <br/> |
|UACategory  <br/> |nvarchar (64)  <br/> |Categoria à qual o agente do usuário pertence. Por exemplo, o agente de usuário Conferencing_Attendant_ 1.0 pertence ao UACategory CAA.  <br/> |
   

