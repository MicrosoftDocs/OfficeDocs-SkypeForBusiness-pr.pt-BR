---
title: Tabela DeRegisterType no Skype for Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
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
ms.openlocfilehash: d56f5cc639051bb679a3ec5c2ab5b80fce60c18a
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62402715"
---
# <a name="deregistertype-table-in-skype-for-business-server-2015"></a>Tabela DeRegisterType no Skype for Business Server 2015
 
A tabela DeRegisterType é uma tabela estática que armazena a lista de possíveis tipos de registro de usuários, como 'iniciado pelo cliente', 'registro expirado' ou 'cliente parou de responder'.
  
|**Coluna**|**Tipo de dados**|**Chave/Índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**DeRegisterTypeId** <br/> |tinyint  <br/> |Primário  <br/> ||
|**DeRegisterReason** <br/> |nvarchar(256)  <br/> || Valores permitidos: <br/>  0 -- Desconhecido <br/>  Iniciado o cancelamento do registro pelo cliente <br/>  2 -- Registro expirado <br/>  3 - Cliente que caiu <br/>  Atributos do usuário mudaram <br/>  5 - Registrador Preferencial Alterado <br/>  6 -- Cliente herdado em Modo de sobrevivência <br/> |
   

