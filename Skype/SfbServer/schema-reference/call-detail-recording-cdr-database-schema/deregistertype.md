---
title: Tabela canregistertype no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 09148118-6209-4fd7-a494-99118689a245
description: A tabela canregistertype é uma tabela estática que armazena a lista de possíveis tipos de registros de usuário possíveis, como ' cliente iniciado ', ' registro expirado ' ou ' cliente parou de responder '.
ms.openlocfilehash: 794f8f98ffe20cd69b63fd2084fee38ed055d40f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296347"
---
# <a name="deregistertype-table-in-skype-for-business-server-2015"></a>Tabela canregistertype no Skype for Business Server 2015
 
A tabela canregistertype é uma tabela estática que armazena a lista de possíveis tipos de registros de usuário possíveis, como ' cliente iniciado ', ' registro expirado ' ou ' cliente parou de responder '.
  
|**Coluna**|**Tipo de dados**|**Chave/índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**DeRegisterTypeId** <br/> |tinyint  <br/> |Primária  <br/> ||
|**DeRegisterReason** <br/> |nvarchar(256)  <br/> || Valores permitidos: <br/>  0--desconhecido <br/>  1--cliente iniciou o registro <br/>  2--registro expirado <br/>  3-cliente travado <br/>  4--atributos de usuário alterados <br/>  5-registrador preferencial alterado <br/>  6 – cliente herdado no modo de sobrevivência <br/> |
   

