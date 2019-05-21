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
localization_priority: Normal
ms.assetid: dcd16dc1-a66c-4720-a48f-ec8b28337383
description: tblPrincipalRole contém funções explícitas atribuídas a nós.
ms.openlocfilehash: 9675713afba5753378f4d01b70489d0eee93b8bf
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295234"
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
   

