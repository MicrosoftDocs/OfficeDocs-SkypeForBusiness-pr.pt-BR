---
title: Tabela do usuário
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 6b52047e-286d-47ab-b7bc-a9b266f62d82
description: A tabela de Usuário é uma tabela de suporte que armazena uma lista de vários usuários que participaram das sessões registradas no banco de dados. Cada registro da tabela representa um usuário.
ms.openlocfilehash: 3162876221e516110dd7b4062d73756932e80d44
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62403615"
---
# <a name="user-table"></a>Tabela do usuário
 
A tabela de Usuário é uma tabela de suporte que armazena uma lista de vários usuários que participaram das sessões registradas no banco de dados. Cada registro da tabela representa um usuário.
  
|**Coluna**|**Tipo de dados**|**Chave/Índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**UserKey** <br/> |int  <br/> |Primário  <br/> |Número exclusivo identificando este usuário.  <br/> |
|**URI** <br/> |nvarchar(450)  <br/> |Unique  <br/> |Cadeia de caracteres URI.  <br/> |
|**URIType** <br/> |int  <br/> ||1 é o tipo de URI desconhecido.  <br/> 2 é o URI do usuário.  <br/> 4 é o URI de conferência.  <br/> 8 é o URI do telefone.  <br/> |
|**TenantKey** <br/> |int  <br/> |Foreign  <br/> |Locatário do usuário, referenciado da tabela do locatário.  <br/> |
|**LastPoorCallTime** <br/> |datetime  <br/> ||Carimbo de data e hora da última vez em que o usuário teve uma chamada de áudio ruim.  <br/> |
|**NextUpdateTS** <br/> |datetime  <br/> ||Apenas para uso interno.  <br/> |
   

