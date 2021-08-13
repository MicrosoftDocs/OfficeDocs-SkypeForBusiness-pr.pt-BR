---
title: tblPrincipalRole
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
ms.assetid: dcd16dc1-a66c-4720-a48f-ec8b28337383
description: tblPrincipalRole contém funções explícitas atribuídas aos nós.
ms.openlocfilehash: 28e639a4894b89e449a70fc527b7c4315be57403e15bb582bcdae3933e3790a7
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54336381"
---
# <a name="tblprincipalrole"></a>tblPrincipalRole
 
tblPrincipalRole contém funções explícitas atribuídas aos nós.
  
**Columns**

|**Coluna**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|
|prinRoleNodeID  <br/> |int, not null  <br/> |ID do nó à que a função se aplica.  <br/> |
|prinRolePrinID  <br/> |int, not null  <br/> |ID principal.  <br/> |
|prinRoleTypeID  <br/> |int, not null  <br/> |ID do tipo de função (de tblRoleType).  <br/> |
|prinRoleUpdatedBy  <br/> |int, not null  <br/> |ID da entidade de segurança da última atualização dessa entrada.  <br/> |
   
**Teclas**

|**Coluna**|**Descrição**|
|:-----|:-----|
|\<prinRoleNodeID, prinRolePrinID, prinRoleTypeID\>  <br/> |Chave primária.  <br/> |
|prinRoleNodeID  <br/> |Chave estrangeira com pesquisa na tabela tblNode.nodeID.  <br/> |
|prinRolePrinID  <br/> |Chave estrangeira com pesquisa na tabela tblPrincipal.prinID.  <br/> |
|prinRoleTypeID  <br/> |Chave estrangeira com lookup na tabela tblRoleType.rtypeID.  <br/> |
   

