---
title: Tabela CallPriorities no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 043b63ae-2d64-4f38-a0df-18aa08d6caf5
description: A tabela CallPriorities é uma tabela estática que armazena a lista de possíveis prioridades de chamadas, como ' emergência ', ' urgente ' ou ' normal '.
ms.openlocfilehash: 6d324ce11b2e149378b6275441cb4a2467a641db
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296564"
---
# <a name="callpriorities-table-in-skype-for-business-server-2015"></a>Tabela CallPriorities no Skype for Business Server 2015
 
A tabela CallPriorities é uma tabela estática que armazena a lista de possíveis prioridades de chamadas, como ' emergência ', ' urgente ' ou ' normal '.
  
|**Coluna**|**Tipo de dados**|**Chave/índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**Priorityid** <br/> |tinyint  <br/> |Primária  <br/> ||
|**Prioridade** <br/> |nvarchar(256)  <br/> || Valores permitidos: <br/>  0-desconhecido <br/>  1-não urgente <br/>  2-normal <br/>  3-urgente <br/>  4-emergência <br/> |
   

