---
title: Tabela User
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6b52047e-286d-47ab-b7bc-a9b266f62d82
description: A tabela de usuário é uma tabela de suporte que armazena uma lista dos diversos usuários que tenham participado em sessões gravadas no banco de dados. Cada registro na tabela representa um usuário.
ms.openlocfilehash: 3261133b8c36fe96fd847c075dce0be2a903c417
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="user-table"></a>Tabela User
 
A tabela de usuário é uma tabela de suporte que armazena uma lista dos diversos usuários que tenham participado em sessões gravadas no banco de dados. Cada registro na tabela representa um usuário.
  
|**Coluna**|**Tipo de dados**|**Índice de chaves /**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**UserKey** <br/> |int  <br/> |Primária  <br/> |Número exclusivo que identifica este usuário.  <br/> |
|**URI** <br/> |nvarchar(450)  <br/> |Exclusivo  <br/> |Cadeia de caracteres do URI.  <br/> |
|**URIType** <br/> |int  <br/> ||1 é o tipo URI desconhecido.  <br/> 2 é o URI do usuário.  <br/> 4 é o URI de conferência.  <br/> 8 é o URI do telefone.  <br/> |
|**TenantKey** <br/> |int  <br/> |Externa  <br/> |Locatário do usuário, referenciado da tabela do locatário.  <br/> |
|**LastPoorCallTime** <br/> |datetime  <br/> ||Carimbo de hora mais recente que o usuário teve uma chamada de áudio ruim.  <br/> |
|**NextUpdateTS** <br/> |datetime  <br/> ||Somente para uso interno.  <br/> |
   

