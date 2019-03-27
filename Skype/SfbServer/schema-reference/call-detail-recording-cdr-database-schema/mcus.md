---
title: Tabela MCUs Skype para Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 271b7963-8fd8-4d92-a701-1a62aaf895ee
description: A tabela Mcus é uma tabela de suporte. Cada registro armazena informações sobre um serviço de conferência. Eles podem incluir o serviço de conferência de mensagens Instantâneas e o serviço de conferência com telefonia (que são executados como processos em servidores front-end) e o serviço de webconferência e uma / serviço V Conferencing.
ms.openlocfilehash: e051af3a77d4f9b8231c122c596a3b6915f6f3e1
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30893009"
---
# <a name="mcus-table-in-skype-for-business-server-2015"></a>Tabela MCUs Skype para Business Server 2015
 
A tabela Mcus é uma tabela de suporte. Cada registro armazena informações sobre um serviço de conferência. Eles podem incluir o serviço de conferência de mensagens Instantâneas e o serviço de conferência com telefonia (que são executados como processos em servidores front-end) e o serviço de webconferência e uma / serviço V Conferencing. 
  
|**Coluna**|**Tipo de dados**|**Chave/índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**McuId** <br/> |int  <br/> |Primária  <br/> |Número exclusivo que identifica este servidor de conferência.  <br/> |
|**McuUri** <br/> |nvarchar(450)  <br/> | <br/> | <br/> |
|**McuTypeId** <br/> |inyint  <br/> | Externa <br/> |Tipo de servidor de conferência, como conf:chat (para mensagens instantâneas) ou conf:audio-vídeo. Consulte a [tabela UriTypes](uritypes.md) para obter mais informações. <br/> |
   

