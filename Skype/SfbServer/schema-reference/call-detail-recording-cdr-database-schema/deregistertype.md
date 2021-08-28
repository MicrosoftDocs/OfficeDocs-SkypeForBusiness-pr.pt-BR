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
ms.localizationpriority: medium
ms.assetid: 09148118-6209-4fd7-a494-99118689a245
description: A tabela DeRegisterType é uma tabela estática que armazena a lista de possíveis tipos de registro de usuários, como 'iniciado pelo cliente', 'registro expirado' ou 'cliente parou de responder'.
ms.openlocfilehash: 93d06117974377b6df489f376aedf4ad88235fa2
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58599876"
---
# <a name="deregistertype-table-in-skype-for-business-server-2015"></a>Tabela DeRegisterType no Skype for Business Server 2015
 
A tabela DeRegisterType é uma tabela estática que armazena a lista de possíveis tipos de registro de usuários, como 'iniciado pelo cliente', 'registro expirado' ou 'cliente parou de responder'.
  
|**Coluna**|**Tipo de dados**|**Chave/Índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**DeRegisterTypeId** <br/> |tinyint  <br/> |Primário  <br/> ||
|**DeRegisterReason** <br/> |nvarchar(256)  <br/> || Valores permitidos: <br/>  0 -- Desconhecido <br/>  Iniciado o cancelamento do registro pelo cliente <br/>  2 -- Registro expirado <br/>  3 - Cliente que caiu <br/>  Atributos do usuário mudaram <br/>  5 - Registrador Preferencial Alterado <br/>  6 -- Cliente herdado em Modo de sobrevivência <br/> |
   

