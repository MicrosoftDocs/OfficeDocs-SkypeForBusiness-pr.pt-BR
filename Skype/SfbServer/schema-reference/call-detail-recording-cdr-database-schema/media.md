---
title: Tabela de mídia
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 1e1b427f-59b5-4564-bde5-1002a80439ee
description: Cada registro representa um tipo de mídia usado em uma sessão ponto a ponto. Uma sessão será representada por vários registros na tabela se mais de um tipo de mídia for usado.
ms.openlocfilehash: a32a61d5ba7c3aa7d3a77008af373a5ea45daeda
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60756464"
---
# <a name="media-table"></a>Tabela de mídia
 
Cada registro representa um tipo de mídia usado em uma sessão ponto a ponto. Uma sessão será representada por vários registros na tabela se mais de um tipo de mídia for usado.
  
> [!NOTE]
> A tabela de Mídia não deve ser usada para calcular a duração da mídia de uma sessão. Esta tabela contém os detalhes de sinalização da troca de mídia em uma sessão. A troca de mídia é realizada pela solicitação INVITE e StartTime indica a hora que INVITE foi enviado. O horário do convite não necessariamente significa a hora inicial da mídia, porque a mídia começa apenas após o participante aceitar a sessão. O EndTime geralmente significa a hora final desta sessão. 
  
|**Column**|**Tipo de dados**|**Chave/Índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Primário, Estrangeiro  <br/> |Tempo da solicitação de sessão. Usado em conjunto com **SessionIdSeq** para identificar exclusivamente uma sessão. Consulte a [tabela Dialogs no Skype for Business Server 2015](dialogs.md) para obter mais informações. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primário, Estrangeiro  <br/> |O número de ID para identificar a sessão. Usado em conjunto com **SessionIdTime** para identificar exclusivamente uma sessão. Consulte a [tabela Dialogs no Skype for Business Server 2015](dialogs.md) para obter mais informações. <br/> |
|**MediaId** <br/> |tinyint  <br/> |Primária, Estrangeira  <br/> |Número exclusivo identificando este tipo de mídia. Consulte a [tabela MediaList para](medialist.md) obter mais informações. <br/> |
|**StartTime** <br/> |datetime  <br/> |Primário  <br/> |Este é o horário em que a solicitação de mídia foi enviada, não o horário de início de mídia real. O **StartTime** inclui a hora de configuração da sessão.<br/> |
|**EndTime** <br/> |datetime  <br/> ||Este é o horário de término da sessão.  <br/> |
   

