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
description: A tabela DeRegisterType é uma tabela estática que armazena a lista de possíveis tipos de registro de usuários, como 'iniciado pelo cliente', 'registro expirado' ou 'cliente parou de responder'.
ms.openlocfilehash: 606065f0442043d660c917c61b89111b48679145088b4eba9a7a80e668248161
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54347786"
---
# <a name="deregistertype-table-in-skype-for-business-server-2015"></a>Tabela DeRegisterType no Skype for Business Server 2015
 
A tabela DeRegisterType é uma tabela estática que armazena a lista de possíveis tipos de registro de usuários, como 'iniciado pelo cliente', 'registro expirado' ou 'cliente parou de responder'.
  
|**Coluna**|**Tipo de dados**|**Chave/Índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**DeRegisterTypeId** <br/> |tinyint  <br/> |Primário  <br/> ||
|**DeRegisterReason** <br/> |nvarchar(256)  <br/> || Valores permitidos: <br/>  0 -- Desconhecido <br/>  Iniciado o cancelamento do registro pelo cliente <br/>  2 -- Registro expirado <br/>  3 - Cliente que caiu <br/>  Atributos do usuário mudaram <br/>  5 - Registrador Preferencial Alterado <br/>  6 -- Cliente herdado em Modo de sobrevivência <br/> |
   

