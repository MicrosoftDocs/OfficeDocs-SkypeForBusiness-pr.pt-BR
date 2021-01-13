---
title: Tabela User
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6b52047e-286d-47ab-b7bc-a9b266f62d82
description: A tabela de Usuário é uma tabela de suporte que armazena uma lista de vários usuários que participaram das sessões registradas no banco de dados. Cada registro da tabela representa um usuário.
ms.openlocfilehash: 5c84f0b947199fa497964cb1689dccc571a98d14
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49800071"
---
# <a name="user-table"></a>Tabela User
 
A tabela de Usuário é uma tabela de suporte que armazena uma lista de vários usuários que participaram das sessões registradas no banco de dados. Cada registro da tabela representa um usuário.
  
|**Coluna**|**Tipo de dados**|**Chave/Índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**UserKey** <br/> |int  <br/> |Primário  <br/> |Número exclusivo identificando este usuário.  <br/> |
|**URI** <br/> |nvarchar(450)  <br/> |Exclusivo  <br/> |Cadeia de caracteres URI.  <br/> |
|**URIType** <br/> |int  <br/> ||1 é o tipo de URI desconhecido.  <br/> 2 é o URI do usuário.  <br/> 4 é o URI de conferência.  <br/> 8 é o URI do telefone.  <br/> |
|**TenantKey** <br/> |int  <br/> |Externo  <br/> |Locatário do usuário, referenciado da tabela do locatário.  <br/> |
|**LastPoorCallTime** <br/> |datetime  <br/> ||Carimbo de data e hora da última vez em que o usuário teve uma chamada de áudio ruim.  <br/> |
|**NextUpdateTS** <br/> |datetime  <br/> ||Apenas para uso interno.  <br/> |
   

