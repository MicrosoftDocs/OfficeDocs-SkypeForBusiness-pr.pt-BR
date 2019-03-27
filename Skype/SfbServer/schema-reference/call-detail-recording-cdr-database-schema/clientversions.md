---
title: Tabela ClientVersions Skype para Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 542316cf-a6db-4d52-ab28-8bf6d27a3b48
description: A tabela ClientVersions é uma tabela de suporte que armazena uma lista dos vários tipos de cliente e de versões que tenham participado em sessões gravadas no banco de dados. Cada registro na tabela representa uma versão de cliente.
ms.openlocfilehash: df80e907359297c9cdb518562fdeea54d31a2a47
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30898526"
---
# <a name="clientversions-table-in-skype-for-business-server-2015"></a>Tabela ClientVersions Skype para Business Server 2015
 
A tabela ClientVersions é uma tabela de suporte que armazena uma lista dos vários tipos de cliente e de versões que tenham participado em sessões gravadas no banco de dados. Cada registro na tabela representa uma versão de cliente.
  
|**Coluna**|**Tipo de dados**|**Chave/índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**VersionId** <br/> |**int** <br/> |Primária  <br/> |Número exclusivo identificando este tipo de cliente e versão.  <br/> |
|**Versão** <br/> |**nvarchar(256)** <br/> ||Nome da versão.  <br/> |
|**ClientType** <br/> |int  <br/> ||Especifica o tipo do cliente usado na sessão. Consulte a [tabela UserAgentDef](useragentdef.md) para obter mais informações. <br/> Este campo foi introduzido no Microsoft Lync Server 2013.  <br/> |
   

