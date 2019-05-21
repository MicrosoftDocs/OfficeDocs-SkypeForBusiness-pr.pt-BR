---
title: Tabela Media
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1e1b427f-59b5-4564-bde5-1002a80439ee
description: Cada registro representa um tipo de mídia usado em uma sessão ponto a ponto. Uma sessão seria representada por vários registros na tabela, se mais de um tipo de mídia for usado.
ms.openlocfilehash: 181a78a9fc3fabe8c166f4cdc8c452b5a16b016b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296004"
---
# <a name="media-table"></a>Tabela Media
 
Cada registro representa um tipo de mídia usado em uma sessão ponto a ponto. Uma sessão seria representada por vários registros na tabela, se mais de um tipo de mídia for usado.
  
> [!NOTE]
> A tabela de mídia não deve ser usada para calcular a duração da mídia de uma sessão. Esta tabela contém os detalhes de sinalização da troca de mídia em uma sessão. A troca de mídia é feita pela solicitação de convite e StartTime indica a hora em que o convite foi enviado. O tempo de convite não necessariamente significa a hora de início da mídia porque a mídia só inicia depois que a sessão aceita a sessão. A EndTime geralmente significa a hora de término desta sessão. 
  
|**Coluna**|**Tipo de dados**|**Chave/índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**Id_da_sessãotime** <br/> |datetime  <br/> |Primário, estrangeiro  <br/> |Tempo de solicitação de sessão. Usado em conjunto com o **SessionIdSeq** para identificar exclusivamente uma sessão. Consulte a [tabela de diálogos no Skype for Business Server 2015](dialogs.md) para obter mais informações. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primário, estrangeiro  <br/> |Número de identificação para identificar a sessão. Usado em conjunto com **** a identificação_da_sessãotime para identificar exclusivamente uma sessão. Consulte a [tabela de diálogos no Skype for Business Server 2015](dialogs.md) para obter mais informações. <br/> |
|**MediaId** <br/> |tinyint  <br/> |Primário, estrangeiro  <br/> |Número exclusivo que identifica esse tipo de mídia. Consulte a [tabela medialist](medialist.md) para obter mais informações. <br/> |
|**StartTime ** <br/> |datetime  <br/> |Primária  <br/> |Esta é a hora em que uma solicitação de mídia foi enviada, e não a hora de início da mídia real. **StartTime** inclui o tempo de configuração da sessão. <br/> |
|**EndTime** <br/> |datetime  <br/> ||Esta é a hora de término da sessão.  <br/> |
   

