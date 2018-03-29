---
title: tblPrincipalInvites
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 548ec156-4d1a-469d-a804-62cff226e5c2
description: tblPrincipalInvites inclui convites para todos os usuários provisionados de todos os nós com convite automático ativada.
ms.openlocfilehash: ae33d45e14340b6374299343f13c8352db1a5021
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="tblprincipalinvites"></a>tblPrincipalInvites
 
tblPrincipalInvites inclui convites para todos os usuários provisionados de todos os nós com convite automático ativada.
  
**Colunas**

|**Coluna**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|
|prinID  <br/> |int, não nulo  <br/> |ID principal.  <br/> |
|invID  <br/> |int, não nulo  <br/> |Número sequencial exclusivo (por ID de entidade) gerado a partir da tabela tblLastInviteId.  <br/> |
|nodeID  <br/> |int, não nulo  <br/> |ID do nó (somente sala de chat).  <br/> |
|createdOn  <br/> |DateTime, não nulo  <br/> |Hora da criação.  <br/> |
   
**Chaves**

|**Coluna**|**Descrição**|
|:-----|:-----|
|\<prinID, nodeID\>  <br/> |Chave primária.  <br/> |
|prinID  <br/> |Chave estrangeira com pesquisa na tabela Tblprincipal.  <br/> |
|nodeID  <br/> |Chave estrangeira com pesquisa na tabela Tblnode.  <br/> |
   

