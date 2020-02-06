---
title: tblPrincipalRole
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
ms.assetid: dcd16dc1-a66c-4720-a48f-ec8b28337383
description: tblPrincipalRole contém funções explícitas atribuídas a nós.
ms.openlocfilehash: 1cc606ec3825bb664d4123154e97fabb15678cfd
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813359"
---
# <a name="tblprincipalrole"></a>tblPrincipalRole
 
tblPrincipalRole contém funções explícitas atribuídas a nós.
  
**Colunas**

|**Coluna**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|
|prinRoleNodeID  <br/> |int, não nulo  <br/> |ID do nó ao qual a função se aplica.  <br/> |
|prinRolePrinID  <br/> |int, não nulo  <br/> |ID da entidade de segurança.  <br/> |
|prinRoleTypeID  <br/> |int, não nulo  <br/> |ID do tipo de função (de tblRoleType).  <br/> |
|prinRoleUpdatedBy  <br/> |int, não nulo  <br/> |ID da entidade de segurança que atualizou pela última vez esta entrada.  <br/> |
   
**As**

|**Coluna**|**Descrição**|
|:-----|:-----|
|\<prinRoleNodeID, prinRolePrinID, prinRoleTypeID\>  <br/> |Chave primária.  <br/> |
|prinRoleNodeID  <br/> |Chave estrangeira com Lookup na tabela tblNode. NodeId.  <br/> |
|prinRolePrinID  <br/> |Chave estrangeira com Lookup na tabela tblPrincipal. retoid.  <br/> |
|prinRoleTypeID  <br/> |Chave estrangeira com Lookup na tabela tblRoleType. rtypeID.  <br/> |
   

