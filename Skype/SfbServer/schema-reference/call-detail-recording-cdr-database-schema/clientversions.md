---
title: Tabela ClientVersions Skype para Business Server 2015
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
ms.openlocfilehash: 488c7f4211eacb6fc496d6198258c119641ebd14
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="clientversions-table-in-skype-for-business-server-2015"></a>Tabela ClientVersions Skype para Business Server 2015
 
A tabela ClientVersions é uma tabela de suporte que armazena uma lista dos vários tipos de cliente e de versões que tenham participado em sessões gravadas no banco de dados. Cada registro na tabela representa uma versão de cliente.
  
|**Coluna**|**Tipo de dados**|**Índice de chaves /**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**VersionId** <br/> |**int** <br/> |Primária  <br/> |Número exclusivo identificando este tipo de cliente e versão.  <br/> |
|**Versão** <br/> |**nvarchar(256)** <br/> ||Nome da versão.  <br/> |
|**ClientType** <br/> |int  <br/> ||Especifica o tipo do cliente usado na sessão. Consulte a [tabela UserAgentDef](useragentdef.md) para obter mais informações. <br/> Este campo foi introduzido no Microsoft Lync Server 2013.  <br/> |
   

