---
title: tblPrincipalInvites
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 548ec156-4d1a-469d-a804-62cff226e5c2
description: tblPrincipalInvites contém convites para todos os usuários provisionados para todos os nós com convite automático ativado.
ms.openlocfilehash: dfa41ec5715c7c5255b26fcdb32561e74c4f08df
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814179"
---
# <a name="tblprincipalinvites"></a>tblPrincipalInvites
 
tblPrincipalInvites contém convites para todos os usuários provisionados para todos os nós com convite automático ativado.
  
**Colunas**

|**Coluna**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|
|multiimprimir  <br/> |int, não nulo  <br/> |ID da entidade de segurança.  <br/> |
|invID  <br/> |int, não nulo  <br/> |Número seqüencial exclusivo (por ID da entidade) gerado pela tabela tblLastInviteId.  <br/> |
|NodeId  <br/> |int, não nulo  <br/> |ID do nó (somente sala de chat).  <br/> |
|criar  <br/> |DateTime, não nulo  <br/> |Hora da criação.  <br/> |
   
**As**

|**Coluna**|**Descrição**|
|:-----|:-----|
|\<, NodeId\>  <br/> |Chave primária.  <br/> |
|multiimprimir  <br/> |Chave estrangeira com Lookup na tabela tblPrincipal. retoid.  <br/> |
|NodeId  <br/> |Chave estrangeira com Lookup na tabela tblNode. NodeId.  <br/> |
   

