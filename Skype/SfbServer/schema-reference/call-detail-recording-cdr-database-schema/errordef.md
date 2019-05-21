---
title: Tabela ErrorDef no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6acf3b86-da61-4923-9812-300db6f66dec
description: A tabela ErrorDef armazena informações sobre cada tipo de erro que pode ocorrer. Cada registro é um tipo de erro.
ms.openlocfilehash: c6157bb62df47b8fcb1cd158605c5a357e623adf
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296277"
---
# <a name="errordef-table-in-skype-for-business-server-2015"></a>Tabela ErrorDef no Skype for Business Server 2015
 
A tabela ErrorDef armazena informações sobre cada tipo de erro que pode ocorrer. Cada registro é um tipo de erro.
  
|**Coluna**|**Tipo de dados**|**Chave/índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**ErrorID** <br/> |int  <br/> |Primária  <br/> |Número de identificação exclusivo que identifica esse tipo de erro.  <br/> |
|**ResponseCode** <br/> |int  <br/> | <br/> |Código de resposta SIP padrão associado a esse erro.  <br/> |
|**MsDiagId** <br/> |int  <br/> | <br/> |IDENTIFICAÇÃO do diagnóstico da Microsoft.  <br/> |
|**Callid** <br/> |Núm  <br/> |Exterior  <br/> |Tipo de chamada. Consulte a [tabela CallType no Skype for Business Server 2015](calltype.md) para obter mais informações. <br/> |
|**RequestType** <br/> |varbinary (33)  <br/> | <br/> |Tipo de solicitação que falhou.  <br/> Esses dados podem ser convertidos em um formato de texto usando esta sintaxe:  <br/>  `cast(cast(RequestType as varbinary(max)) as varchar(max))` <br/> |
|**ContentType** <br/> |varbinary (257)  <br/> | <br/> |Tipo de conteúdo da solicitação que falhou.  <br/> Esses dados podem ser convertidos em um formato de texto usando esta sintaxe:  <br/>  `cast(cast(ContentType as varbinary(max)) as varchar(max))` <br/> |
   

