---
title: Tabela CallPriorities Skype para Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 043b63ae-2d64-4f38-a0df-18aa08d6caf5
description: A tabela CallPriorities é uma tabela estática que armazena a lista de prioridades de chamada possíveis, como "emergência", "urgente" ou "normal".
ms.openlocfilehash: faf4e7f04d7a63b096cb2369c21916e5fcb71a24
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30882987"
---
# <a name="callpriorities-table-in-skype-for-business-server-2015"></a>Tabela CallPriorities Skype para Business Server 2015
 
A tabela CallPriorities é uma tabela estática que armazena a lista de prioridades de chamada possíveis, como "emergência", "urgente" ou "normal".
  
|**Coluna**|**Tipo de dados**|**Chave/índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**PriorityId** <br/> |tinyint  <br/> |Primária  <br/> ||
|**Prioridade** <br/> |nvarchar(256)  <br/> || Valores permitidos: <br/>  0 - desconhecido <br/>  1 - não urgente <br/>  2 - Normal <br/>  3 - urgente <br/>  4 - emergência <br/> |
   

