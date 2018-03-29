---
title: Tabela Media
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1e1b427f-59b5-4564-bde5-1002a80439ee
description: Cada registro representa um tipo de mídia usado em uma sessão ponto a ponto. Uma sessão seria representada por vários registros na tabela, se mais de um tipo de mídia é usado.
ms.openlocfilehash: 8833e7272c82dcbb7eef0da89d915680198589b5
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="media-table"></a>Tabela Media
 
Cada registro representa um tipo de mídia usado em uma sessão ponto a ponto. Uma sessão seria representada por vários registros na tabela, se mais de um tipo de mídia é usado.
  
> [!NOTE]
> A tabela de mídia não deve ser usada para calcular a duração de mídia para uma sessão. Esta tabela contém os detalhes de sinalização de troca de mídia em uma sessão. Troca de mídia é feita com a solicitação de convite e StartTime indica a hora em que o convite foi enviado. O tempo de convidar não necessariamente que a mídia Iniciar tempo, porque a mídia inicia somente depois que o sessionee aceita a sessão. A EndTime geralmente significa que a hora de término dessa sessão. 
  
|**Coluna**|**Tipo de dados**|**Índice de chaves /**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Primária, estrangeira  <br/> |Hora da solicitação de sessão. Usado em conjunto com **SessionIdSeq** para identificar exclusivamente uma sessão. Consulte a [tabela no Skype para Business Server 2015 de diálogos](dialogs.md) para obter mais informações. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primária, estrangeira  <br/> |Número de identificação para identificar a sessão. Usado em conjunto com **SessionIdTime** para identificar exclusivamente uma sessão. Consulte a [tabela no Skype para Business Server 2015 de diálogos](dialogs.md) para obter mais informações. <br/> |
|**MediaId** <br/> |tinyint  <br/> |Primária, estrangeira  <br/> |Número exclusivo que identifica esse tipo de mídia. Consulte a [tabela MediaList](medialist.md) para obter mais informações. <br/> |
|**StartTime** <br/> |datetime  <br/> |Primária  <br/> |Esta é a hora em que uma solicitação de mídia foi enviada, não a mídia real de hora de início. **StartTime** inclui o tempo de configuração de sessão. <br/> |
|**EndTime** <br/> |datetime  <br/> ||Esta é a hora de término da sessão.  <br/> |
   

