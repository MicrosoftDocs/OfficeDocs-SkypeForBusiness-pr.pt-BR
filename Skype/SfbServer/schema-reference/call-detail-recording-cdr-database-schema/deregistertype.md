---
title: Tabela DeRegisterType Skype para Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 09148118-6209-4fd7-a494-99118689a245
description: A tabela DeRegisterType é uma tabela estática que armazena a lista de possível usuário registra desprovisionamento tipos, como "cliente iniciado", "registro vencido" ou 'cliente parado de responder.'
ms.openlocfilehash: be6fd10388c9f85315554605fd491aafa9d3a0d0
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213190"
---
# <a name="deregistertype-table-in-skype-for-business-server-2015"></a>Tabela DeRegisterType Skype para Business Server 2015
 
A tabela DeRegisterType é uma tabela estática que armazena a lista de possível usuário registra desprovisionamento tipos, como "cliente iniciado", "registro vencido" ou 'cliente parado de responder.'
  
|**Coluna**|**Tipo de dados**|**Chave/índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**DeRegisterTypeId** <br/> |tinyint  <br/> |Primária  <br/> ||
|**DeRegisterReason** <br/> |nvarchar(256)  <br/> || Valores permitidos: <br/>  0--desconhecido <br/>  1-- cliente iniciado o cancelamento do registro <br/>  2-- registro expirado <br/>  3 - cliente paralisado <br/>  4 atributos do usuário mudaram <br/>  5 - registrador preferido mudou <br/>  6-- Cliente de herdado em modo de sobrevivência <br/> |
   

