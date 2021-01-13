---
title: Tabela DeRegisterType no Skype for Business Server 2015
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
localization_priority: Normal
ms.assetid: 09148118-6209-4fd7-a494-99118689a245
description: A tabela DeRegisterType é uma tabela estática que armazena a lista de possíveis tipos de registro de usuário, como "iniciado pelo cliente", "registro expirado" ou "o cliente parou de responder".
ms.openlocfilehash: 388aebc1ac180e1298addd54859cff6759b28be0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816071"
---
# <a name="deregistertype-table-in-skype-for-business-server-2015"></a>Tabela DeRegisterType no Skype for Business Server 2015
 
A tabela DeRegisterType é uma tabela estática que armazena a lista de possíveis tipos de registro de usuário, como "iniciado pelo cliente", "registro expirado" ou "o cliente parou de responder".
  
|**Coluna**|**Tipo de dados**|**Chave/Índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**DeRegisterTypeId** <br/> |tinyint  <br/> |Primário  <br/> ||
|**DeRegisterReason** <br/> |nvarchar(256)  <br/> || Valores permitidos: <br/>  0 -- Desconhecido <br/>  Iniciado o cancelamento do registro pelo cliente <br/>  2 -- Registro expirado <br/>  3 - O cliente parou de ser <br/>  Atributos do usuário mudaram <br/>  5 - Registrador Preferencial Alterado <br/>  6 -- Cliente herdado em Modo de sobrevivência <br/> |
   

