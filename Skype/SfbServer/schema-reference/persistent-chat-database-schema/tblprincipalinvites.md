---
title: tblPrincipalInvites
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 548ec156-4d1a-469d-a804-62cff226e5c2
description: O tblPrincipalInvites inclui convites para todos os usuários provisionados de todos os nós com a opção de convite automático ativada.
ms.openlocfilehash: 5bbccd582442001bd2122dcbacdbe3634fcfd649
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815851"
---
# <a name="tblprincipalinvites"></a>tblPrincipalInvites
 
O tblPrincipalInvites inclui convites para todos os usuários provisionados de todos os nós com a opção de convite automático ativada.
  
**Columns**

|**Coluna**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|
|prinID  <br/> |int, não nulo  <br/> |ID principal.  <br/> |
|invID  <br/> |int, não nulo  <br/> |Número sequencial exclusivo (por ID de entidade) gerado a partir da tabela tblLastInviteId.  <br/> |
|nodeID  <br/> |int, não nulo  <br/> |ID de nó (somente sala de chat).  <br/> |
|createdOn  <br/> |datetime, não nulo  <br/> |Hora da criação.  <br/> |
   
**Teclas**

|**Coluna**|**Descrição**|
|:-----|:-----|
|\<prinID, nodeID\>  <br/> |Chave primária.  <br/> |
|prinID  <br/> |Chave estrangeira com pesquisa na tabela tblPrincipal.prinID.  <br/> |
|nodeID  <br/> |Chave estrangeira com pesquisa na tabela tblNode.nodeID.  <br/> |
   

