---
title: tblPrincipalRole
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
ms.openlocfilehash: 0e6c7f60f372bc14542567ccaa1b1b1a837c6c6d
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
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
   

