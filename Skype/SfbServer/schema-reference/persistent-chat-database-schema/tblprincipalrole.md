---
title: tblPrincipalRole
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dcd16dc1-a66c-4720-a48f-ec8b28337383
description: tblPrincipalRole contém funções explícitas atribuídas a nós.
ms.openlocfilehash: 69cfb0cb2b821064801a07510758514bb5d33128
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30890766"
---
# <a name="tblprincipalrole"></a>tblPrincipalRole
 
tblPrincipalRole contém funções explícitas atribuídas a nós.
  
**Colunas**

|**Coluna**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|
|prinRoleNodeID  <br/> |int, não nulo  <br/> |ID do nó ao qual se aplica a função.  <br/> |
|prinRolePrinID  <br/> |int, não nulo  <br/> |ID principal.  <br/> |
|prinRoleTypeID  <br/> |int, não nulo  <br/> |ID do tipo de função (de tblRoleType).  <br/> |
|prinRoleUpdatedBy  <br/> |int, não nulo  <br/> |ID da entidade que atualizada pela última vez essa entrada.  <br/> |
   
**Chaves**

|**Coluna**|**Descrição**|
|:-----|:-----|
|\<prinRoleNodeID, prinRolePrinID, prinRoleTypeID\>  <br/> |Chave primária.  <br/> |
|prinRoleNodeID  <br/> |Chave estrangeira com pesquisa na tabela Tblnode.  <br/> |
|prinRolePrinID  <br/> |Chave estrangeira com pesquisa na tabela Tblprincipal.  <br/> |
|prinRoleTypeID  <br/> |Chave estrangeira com pesquisa na tabela Tblroletype.  <br/> |
   

