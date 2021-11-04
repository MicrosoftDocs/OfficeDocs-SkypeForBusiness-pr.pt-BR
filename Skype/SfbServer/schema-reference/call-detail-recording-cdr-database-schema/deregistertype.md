---
title: Tabela DeRegisterType no Skype for Business Server 2015
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
ms.assetid: 09148118-6209-4fd7-a494-99118689a245
description: A tabela DeRegisterType é uma tabela estática que armazena a lista de possíveis tipos de registro de usuários, como 'iniciado pelo cliente', 'registro expirado' ou 'cliente parou de responder'.
ms.openlocfilehash: f369416a15f0b1c024dd70fbe97042193940f669
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60743987"
---
# <a name="deregistertype-table-in-skype-for-business-server-2015"></a>Tabela DeRegisterType no Skype for Business Server 2015
 
A tabela DeRegisterType é uma tabela estática que armazena a lista de possíveis tipos de registro de usuários, como 'iniciado pelo cliente', 'registro expirado' ou 'cliente parou de responder'.
  
|**Column**|**Tipo de dados**|**Chave/Índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**DeRegisterTypeId** <br/> |tinyint  <br/> |Primário  <br/> ||
|**DeRegisterReason** <br/> |nvarchar(256)  <br/> || Valores permitidos: <br/>  0 -- Desconhecido <br/>  Iniciado o cancelamento do registro pelo cliente <br/>  2 -- Registro expirado <br/>  3 - Cliente que caiu <br/>  Atributos do usuário mudaram <br/>  5 - Registrador Preferencial Alterado <br/>  6 -- Cliente herdado em Modo de sobrevivência <br/> |
   

