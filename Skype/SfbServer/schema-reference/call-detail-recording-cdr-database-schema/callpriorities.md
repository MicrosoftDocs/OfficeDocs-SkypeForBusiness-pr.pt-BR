---
title: Tabela CallPriorities no Skype for Business Server 2015
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
ms.localizationpriority: medium
ms.assetid: 043b63ae-2d64-4f38-a0df-18aa08d6caf5
description: A tabela CallPriorities é uma tabela estática que armazena a lista de possíveis prioridades de chamada, como "emergência", "urgente" ou "normal".
ms.openlocfilehash: 0538af29f73c5e01d67dd61fe2ff304cd45f82ce
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58635925"
---
# <a name="callpriorities-table-in-skype-for-business-server-2015"></a>Tabela CallPriorities no Skype for Business Server 2015
 
A tabela CallPriorities é uma tabela estática que armazena a lista de possíveis prioridades de chamada, como "emergência", "urgente" ou "normal".
  
|**Coluna**|**Tipo de dados**|**Chave/Índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**PriorityId** <br/> |tinyint  <br/> |Primário  <br/> ||
|**Prioridade** <br/> |nvarchar(256)  <br/> || Valores permitidos: <br/>  0 - Desconhecido <br/>  1 - Não Urgente <br/>  2 - Normal <br/>  3 - Urgente <br/>  4 - Emergência <br/> |
   

