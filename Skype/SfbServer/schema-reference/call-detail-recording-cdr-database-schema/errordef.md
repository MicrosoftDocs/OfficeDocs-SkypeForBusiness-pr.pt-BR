---
title: Tabela ErrorDef no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 6acf3b86-da61-4923-9812-300db6f66dec
description: A tabela ErrorDef armazena informações sobre cada tipo de erro que pode ocorrer. Cada registro é um tipo de erro.
ms.openlocfilehash: c725baeeefa750d8feded45483c74ec849b7842a
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60858188"
---
# <a name="errordef-table-in-skype-for-business-server-2015"></a>Tabela ErrorDef no Skype for Business Server 2015
 
A tabela ErrorDef armazena informações sobre cada tipo de erro que pode ocorrer. Cada registro é um tipo de erro.
  
|**Column**|**Tipo de dados**|**Chave/Índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**ErrorId** <br/> |int  <br/> |Primário  <br/> |Número de identificação exclusivo que identifica esse tipo de erro.  <br/> |
|**ResponseCode** <br/> |int  <br/> | <br/> |Código de resposta SIP padrão associado a esse erro.  <br/> |
|**MsDiagId** <br/> |int  <br/> | <br/> |ID de Diagnóstico da Microsoft.  <br/> |
|**CallTypeId** <br/> |Int  <br/> |Foreign  <br/> |Tipo da chamada. Consulte a [tabela CallType no Skype for Business Server 2015](calltype.md) para obter mais informações. <br/> |
|**RequestType** <br/> |varbinary(33)  <br/> | <br/> |Tipo de solicitação que falhou.  <br/> Esses dados podem ser convertidos em formato de texto usando esta sintaxe:  <br/>  `cast(cast(RequestType as varbinary(max)) as varchar(max))` <br/> |
|**ContentType** <br/> |varbinary(257)  <br/> | <br/> |Tipo de conteúdo da solicitação que falhou.  <br/> Esses dados podem ser convertidos em formato de texto usando esta sintaxe:  <br/>  `cast(cast(ContentType as varbinary(max)) as varchar(max))` <br/> |
   

