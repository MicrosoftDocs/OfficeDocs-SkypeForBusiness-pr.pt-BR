---
title: tblPrincipalInvites
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 548ec156-4d1a-469d-a804-62cff226e5c2
description: O tblPrincipalInvites inclui convites para todos os usuários provisionados de todos os nós com a opção de convite automático ativada.
ms.openlocfilehash: 91eb45208243a9949725b77005b46692a46561e3
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60749750"
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
   

