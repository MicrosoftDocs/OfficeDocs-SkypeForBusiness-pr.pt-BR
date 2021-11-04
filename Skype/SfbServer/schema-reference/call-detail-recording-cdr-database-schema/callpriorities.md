---
title: Tabela CallPriorities no Skype for Business Server 2015
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
ms.assetid: 043b63ae-2d64-4f38-a0df-18aa08d6caf5
description: A tabela CallPriorities é uma tabela estática que armazena a lista de possíveis prioridades de chamada, como "emergência", "urgente" ou "normal".
ms.openlocfilehash: 21924d712ff4ee658f757911ce168fe8b662357d
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60743207"
---
# <a name="callpriorities-table-in-skype-for-business-server-2015"></a>Tabela CallPriorities no Skype for Business Server 2015
 
A tabela CallPriorities é uma tabela estática que armazena a lista de possíveis prioridades de chamada, como "emergência", "urgente" ou "normal".
  
|**Column**|**Tipo de dados**|**Chave/Índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**PriorityId** <br/> |tinyint  <br/> |Primário  <br/> ||
|**Prioridade** <br/> |nvarchar(256)  <br/> || Valores permitidos: <br/>  0 - Desconhecido <br/>  1 - Não Urgente <br/>  2 - Normal <br/>  3 - Urgente <br/>  4 - Emergência <br/> |
   

