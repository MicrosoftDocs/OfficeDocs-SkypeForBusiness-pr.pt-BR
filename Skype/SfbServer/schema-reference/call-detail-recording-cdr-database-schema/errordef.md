---
title: Tabela ErrorDef no Skype para Business Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6acf3b86-da61-4923-9812-300db6f66dec
description: A tabela ErrorDef armazena informações sobre cada tipo de erro que pode ocorrer. Cada registro é um tipo de erro.
ms.openlocfilehash: 4583e1130d257a99d075f2dec0dea80ee6b1390c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="errordef-table-in-skype-for-business-server-2015"></a>Tabela ErrorDef no Skype para Business Server 2015
 
A tabela ErrorDef armazena informações sobre cada tipo de erro que pode ocorrer. Cada registro é um tipo de erro.
  
|**Coluna**|**Tipo de dados**|**Índice de chaves /**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**Identificação de erro** <br/> |int  <br/> |Primária  <br/> |Número de identificação exclusivo que identifica esse tipo de erro.  <br/> |
|**ResponseCode** <br/> |int  <br/> | <br/> |Código de resposta SIP padrão associado a esse erro.  <br/> |
|**MsDiagId** <br/> |int  <br/> | <br/> |ID de diagnóstico da Microsoft.  <br/> |
|**CallTypeId** <br/> |Int  <br/> |Externa  <br/> |Tipo da chamada. Consulte a [tabela CallType Skype para Business Server 2015](calltype.md) para obter mais informações. <br/> |
|**RequestType** <br/> |varbinary(33)  <br/> | <br/> |Tipo de solicitação que falhou.  <br/> Esses dados podem ser convertidos em formato de texto usando esta sintaxe:  <br/>  `cast(cast(RequestType as varbinary(max)) as varchar(max))` <br/> |
|**ContentType** <br/> |varbinary(257)  <br/> | <br/> |Tipo de conteúdo da solicitação que falhou.  <br/> Esses dados podem ser convertidos em formato de texto usando esta sintaxe:  <br/>  `cast(cast(ContentType as varbinary(max)) as varchar(max))` <br/> |
   

